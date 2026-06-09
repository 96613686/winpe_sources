# tip2::test_watcher<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(void)

- ea: `0x18000fec4`
- end: `0x18000ff0e`
- name: `??1?$test_watcher@V?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a65b`

## callees

- `0x18000fc3c`
- `0x18000fec4`
- `0x1800103e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fef5`

## pseudocode

```c
void __fastcall tip2::test_watcher<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>>(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 56);
  if ( v1 && _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 312), 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>((struct _RTL_CRITICAL_SECTION *)v1);
    CoTaskMemFree((LPVOID)v1);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 8));
}

```

## disassembly

```asm
0x18000fec4  mov     [rsp+arg_8], rbx
0x18000fec9  push    rdi
0x18000feca  sub     rsp, 20h
0x18000fece  mov     rbx, [rcx+38h]
0x18000fed2  mov     rdi, rcx
0x18000fed5  test    rbx, rbx
0x18000fed8  jz      short loc_18000FEFB
0x18000feda  or      eax, 0FFFFFFFFh
0x18000fedd  lock xadd [rbx+138h], eax
0x18000fee5  cmp     eax, 1
0x18000fee8  jnz     short loc_18000FEFB
0x18000feea  mov     rcx, rbx
0x18000feed  call    ??1?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(void)
0x18000fef2  mov     rcx, rbx; pv
0x18000fef5  call    cs:__imp_CoTaskMemFree
0x18000fefb  lea     rcx, [rdi+8]; this
0x18000feff  mov     rbx, [rsp+28h+arg_8]
0x18000ff04  add     rsp, 20h
0x18000ff08  pop     rdi
0x18000ff09  jmp     ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
```
