# _CThreadInfo::DoWork_::_1_::dtor$2

- ea: `0x18001a6a3`
- end: `0x18001a6af`
- name: `_CThreadInfo::DoWork_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ff14`

## pseudocode

```c
void __fastcall CThreadInfo::DoWork_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(a2 + 80);
}

```

## disassembly

```asm
0x18001a6a3  lea     rcx, [rdx+50h]
0x18001a6aa  jmp     ??1?$test_watcher@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(void)
```
