# [thunk]:CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x18000c510`
- end: `0x18000c519`
- name: `?QueryInterface@?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c490`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::QueryInterface(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  return CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::QueryInterface(
           a1 - 24,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000c510  sub     rcx, 18h
0x18000c514  jmp     ?QueryInterface@?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::QueryInterface(_GUID const &,void * *)
```
