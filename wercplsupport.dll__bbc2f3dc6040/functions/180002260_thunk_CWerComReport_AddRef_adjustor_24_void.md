# [thunk]:CWerComReport::AddRef`adjustor{24}' (void)

- ea: `0x180002260`
- end: `0x180002269`
- name: `?AddRef@CWerComReport@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002240`

## pseudocode

```c
__int64 __fastcall CWerComReport::AddRef(__int64 a1)
{
  return CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x180002260  sub     rcx, 18h
0x180002264  jmp     ?AddRef@?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@UEAAKXZ; CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::AddRef(void)
```
