# Ejercicios

Ejercicios correspondiente a https://jj.github.io/IV/documentos/temas/Intro_concepto_y_soporte_fisico

## Ejercicio 2

Para la comparación voy a usar
[Hetzner](https://www.hetzner.com/dedicated-rootserver/matrix-ax) y [DigitalOcean](https://www.digitalocean.com/pricing/).

Para la comparación he elegido la máquina **EX42-NVMe** de Hetzner y de
DigitalOcean el droplet con 4vCPUs de manera que tienen igual número de CPUs.

A cambio Hetzner provee con

- 64 GB DDR4 
- 2 x 512 GB 

mientras que digitalOcean 

- 8GB
- 160GB

El precio de la máquina en Hetzner es de 39.90 euros frente a 40 dolares de
digitalOcean. En el caso de Hetzner el precio es independiente del tiempo que
tengamos funcionando la máquina. En el caso de DO el precio por hora es de
_0.060_ dolares. En un mes el 1% y 10% de horas son

- 0.1 * 24 * 30 = 72 horas
- 0.01 * 24 * 30 = 7.2 horas

por lo que el coste sería respectivamente

- 72*0.060 = 4.32 dolares
- 7.2*0.060 = 7.2 horas

si es posible arrancar y apagar el _droplet_ de manera adecuada.
El uso de VPS sale mucho más rentable a nivel de tiempos de CPU.

## Ejercicio 3

En `proc/cpuinfo` vemos que aparece mucha información sobre la cpu, en concreto 
aparece el nombre del modelo. Podemos hacer un `grep` para extraer esta información:

    ➜  ~ cat /proc/cpuinfo | grep "model name"
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor
    model name	: AMD Ryzen 5 2600 Six-Core Processor

las flags ativadas en cada uno de los procesadores son

    ➜  ~ egrep '^flags.*(vmx|svm)' /proc/cpuinfo
    flags		: fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx mmxext fxsr_opt pdpe1gb rdtscp lm constant_tsc rep_good nopl nonstop_tsc cpuid extd_apicid aperfmperf pni pclmulqdq monitor ssse3 fma cx16 sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand lahf_lm cmp_legacy svm extapic cr8_legacy abm sse4a misalignsse 3dnowprefetch osvw skinit wdt tce topoext perfctr_core perfctr_nb bpext perfctr_llc mwaitx cpb hw_pstate sme ssbd sev ibpb vmmcall fsgsbase bmi1 avx2 smep bmi2 rdseed adx smap clflushopt sha_ni xsaveopt xsavec xgetbv1 xsaves clzero irperf xsaveerptr arat npt lbrv svm_lock nrip_save tsc_scale vmcb_clean flushbyasid decodeassists pausefilter pfthreshold avic v_vmsave_vmload vgif overflow_recov succor smca