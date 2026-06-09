# CWerComReport::SubmitReport(ushort *,ulong,IWerReportSubmitCallback *,ushort * *,ulong *)

- ea: `0x18000de10`
- end: `0x18000de16`
- name: `?SubmitReport@CWerComReport@@UEAAJPEAGKPEAUIWerReportSubmitCallback@@PEAPEAGPEAK@Z`
- size: `6`
- prototype: `__int64 __fastcall(CWerComReport *this, unsigned __int16 *, __int64, struct IWerReportSubmitCallback *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CWerComReport::SubmitReport(
        CWerComReport *this,
        unsigned __int16 *a2,
        __int64 a3,
        struct IWerReportSubmitCallback *a4)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000de10  mov     eax, 80004001h
0x18000de15  retn
```
