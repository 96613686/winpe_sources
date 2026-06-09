# [thunk]:CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x18000c480`
- end: `0x18000c489`
- name: `?QueryInterface@?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000c400`

## pseudocode

```c
__int64 __fastcall CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::QueryInterface(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  return CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::QueryInterface(
           a1 - 24,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000c480  sub     rcx, 18h
0x18000c484  jmp     ?QueryInterface@?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::QueryInterface(_GUID const &,void * *)
```
