# tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(void)

- ea: `0x18000ff14`
- end: `0x18000ff5e`
- name: `??1?$test_watcher@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a6a3`

## callees

- `0x18000fcd4`
- `0x18000ff14`
- `0x1800103e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff45`

## pseudocode

```c
void __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 56);
  if ( v1 && _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 280), 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
    CoTaskMemFree((LPVOID)v1);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 8));
}

```

## disassembly

```asm
0x18000ff14  mov     [rsp+arg_8], rbx
0x18000ff19  push    rdi
0x18000ff1a  sub     rsp, 20h
0x18000ff1e  mov     rbx, [rcx+38h]
0x18000ff22  mov     rdi, rcx
0x18000ff25  test    rbx, rbx
0x18000ff28  jz      short loc_18000FF4B
0x18000ff2a  or      eax, 0FFFFFFFFh
0x18000ff2d  lock xadd [rbx+118h], eax
0x18000ff35  cmp     eax, 1
0x18000ff38  jnz     short loc_18000FF4B
0x18000ff3a  mov     rcx, rbx
0x18000ff3d  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x18000ff42  mov     rcx, rbx; pv
0x18000ff45  call    cs:__imp_CoTaskMemFree
0x18000ff4b  lea     rcx, [rdi+8]; this
0x18000ff4f  mov     rbx, [rsp+28h+arg_8]
0x18000ff54  add     rsp, 20h
0x18000ff58  pop     rdi
0x18000ff59  jmp     ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
```
