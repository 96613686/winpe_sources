# _COutofProcReportManager::CreateAndSubmitReport_::_1_::dtor$0

- ea: `0x14001cd7f`
- end: `0x14001cd8b`
- name: `_COutofProcReportManager::CreateAndSubmitReport_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400151c8`

## pseudocode

```c
void __fastcall COutofProcReportManager::CreateAndSubmitReport_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  utl::unique_ptr<_WER_REPORT_INFORMATION_V5,utl::default_delete<_WER_REPORT_INFORMATION_V5>>::~unique_ptr<_WER_REPORT_INFORMATION_V5,utl::default_delete<_WER_REPORT_INFORMATION_V5>>((void **)(a2 + 64));
}

```

## disassembly

```asm
0x14001cd7f  lea     rcx, [rdx+40h]
0x14001cd86  jmp     ??1?$unique_ptr@U_WER_REPORT_INFORMATION_V5@@U?$default_delete@U_WER_REPORT_INFORMATION_V5@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<_WER_REPORT_INFORMATION_V5,utl::default_delete<_WER_REPORT_INFORMATION_V5>>::~unique_ptr<_WER_REPORT_INFORMATION_V5,utl::default_delete<_WER_REPORT_INFORMATION_V5>>(void)
```
