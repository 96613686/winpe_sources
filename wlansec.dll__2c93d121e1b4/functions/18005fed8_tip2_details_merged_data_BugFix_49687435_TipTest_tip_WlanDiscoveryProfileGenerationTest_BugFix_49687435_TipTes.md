# tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>::Release(void)

- ea: `0x18005fed8`
- end: `0x18005ff17`
- name: `?Release@?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@AEAAKXZ`
- size: `63`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005e72c`
- `0x1800612d4`
- `0x180061dc4`

## callees

- `0x18005e7e0`
- `0x18005fed8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fefd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fefd`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 76);
  if ( !v2 )
  {
    tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>::~merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18005fed8  mov     [rsp+arg_0], rbx
0x18005fedd  push    rdi
0x18005fede  sub     rsp, 20h
0x18005fee2  mov     rdi, rcx
0x18005fee5  or      ebx, 0FFFFFFFFh
0x18005fee8  lock xadd [rcx+130h], ebx
0x18005fef0  sub     ebx, 1
0x18005fef3  jnz     short loc_18005FF09
0x18005fef5  call    ??1?$merged_data@U_tip_WlanDiscoveryProfileGenerationTest@TipTest@BugFix_49687435@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>::~merged_data<BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest,BugFix_49687435::TipTest::_tip_WlanDiscoveryProfileGenerationTest>(void)
0x18005fefa  mov     rcx, rdi; pv
0x18005fefd  call    cs:__imp_CoTaskMemFree
0x18005ff04  nop     dword ptr [rax+rax+00h]
0x18005ff09  mov     eax, ebx
0x18005ff0b  mov     rbx, [rsp+28h+arg_0]
0x18005ff10  add     rsp, 20h
0x18005ff14  pop     rdi
0x18005ff15  retn
```
