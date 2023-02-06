import libvirt
import csv
import datetime as dt
import time

# Nomes das VMs
vm_names = ["java11", "java8"]  

# Tempo de medição em segundos
measurement_time = 5   

# Intervalo de medição em segundos
measurement_interval = 2  

def write_csv(filename, headers, rows):
    with open(filename, 'w', newline='') as file:
        writer = csv.writer(file)
        try:
            writer.writerow(headers)
            writer.writerows(rows)
        except Exception as e:
            print(f'Erro ao escrever arquivo {filename}: {e}')
            exit(1)
        finally:	
            file.close()

def gather_vm_stats(conn, vm):
    stats_cpu = vm.getCPUStats(True)
    stats_mem = vm.memoryStats()
    return {
        "VM": vm.name(), # corrigido a chamada do nome da VM
        "Horário de Medição": dt.datetime.now().strftime("%H:%M:%S"),
        "Tempo de CPU (ns)": stats_cpu[0]['cpu_time'],
        "Tempo de Sistema (ns)": stats_cpu[0]['system_time'],
        "Tempo de Usuário (ns)": stats_cpu[0]['user_time'],
        "Memória Alocada (B)": stats_mem.get("actual"),
        "Memória Não Utilizada (B)": stats_mem.get("unused"),
        "Memória Disponível (B)": stats_mem.get("available"),
        "Memória Usável (B)": stats_mem.get("usable"),
        "Caches de Disco (B)": stats_mem.get("disk_caches", 0) # adicionado um valor padrão ao método get
    }

# Abre conexão com qemu:///system
conn = libvirt.open('qemu:///system')
if not conn:
    raise Exception('Falha ao abrir conexão com qemu:///system')

# Armazena as VMs
vms = []
for name in vm_names:
    vm = conn.lookupByName(name)
    if not vm:
        raise Exception(f'Falha ao encontrar a VM {name}')
    vms.append(vm)

headers = list(gather_vm_stats(conn, vms[0]).keys())
rows = []

end_time = time.time() + measurement_time
while time.time() < end_time:
    for vm in vms:
        rows.append(gather_vm_stats(conn, vm))
    time.sleep(measurement_interval)

write_csv("benchmark.csv", headers, [list(row.values()) for row in rows])
conn.close()
exit(0)
``
