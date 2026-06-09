# SvchostEntry_W32Time

- ea: `0x18004d420`
- end: `0x18004d44f`
- name: `SvchostEntry_W32Time`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180039100`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18004d420`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004d42e`
- `api-ms-win-service-private-l1-1-0!I_ScSetServiceBitsW` at `0x18004d43c`

## pseudocode

```c
__int64 SvchostEntry_W32Time()
{
  fnW32TmRegisterServiceCtrlHandlerEx = RegisterServiceCtrlHandlerExW;
  fnW32TmSetServiceStatus = SetServiceStatus;
  fnW32TmI_ScSetServiceBits = (int (*)(struct SERVICE_STATUS_HANDLE__ *, unsigned int, int, int, unsigned __int16 *))I_ScSetServiceBitsW;
  return W32TmServiceMain();
}

```

## disassembly

```asm
0x18004d420  mov     rax, cs:__imp_RegisterServiceCtrlHandlerExW
0x18004d427  mov     cs:?fnW32TmRegisterServiceCtrlHandlerEx@@3P6APEAUSERVICE_STATUS_HANDLE__@@PEBGP6AKKKPEAX1@Z1@ZEA, rax; SERVICE_STATUS_HANDLE__ * (*fnW32TmRegisterServiceCtrlHandlerEx)(ushort const *,ulong (*)(ulong,ulong,void *,void *),void *)
0x18004d42e  mov     rax, cs:__imp_SetServiceStatus
0x18004d435  mov     cs:?fnW32TmSetServiceStatus@@3P6AHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@@ZEA, rax; int (*fnW32TmSetServiceStatus)(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *)
0x18004d43c  mov     rax, cs:__imp_I_ScSetServiceBitsW
0x18004d443  mov     cs:?fnW32TmI_ScSetServiceBits@@3P6AHPEAUSERVICE_STATUS_HANDLE__@@KHHPEAG@ZEA, rax; int (*fnW32TmI_ScSetServiceBits)(SERVICE_STATUS_HANDLE__ *,ulong,int,int,ushort *)
0x18004d44a  jmp     W32TmServiceMain
```
