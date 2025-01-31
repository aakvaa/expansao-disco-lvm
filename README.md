# Expansão de disco LVM XCP-NG

> Expandir a partição com parted
```
parted /dev/xvdb
```

> Dentro do parted, executar:
```
print
resizepart 3 100%
quit
```

> Confirmar que a partição expandiu:
```
lsblk
```

> Expandir o volume lógico
```
lvdisplay
```

> Redimensionar o volume físico:
```
pvresize /dev/xvdb3
```

```
lvextend -l 100%FREE /dev/ubuntu-vg/ubuntu-lvdisplay
```
> Expandir o sistema de arquivos:
```
resize2fs /dev/ubuntu-vg/ubuntu-lv
```
> Por fim verificar se funcionou:
```
lsblk

df -h
```
