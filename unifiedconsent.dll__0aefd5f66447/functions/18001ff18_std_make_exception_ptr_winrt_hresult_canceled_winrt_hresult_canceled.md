# std::make_exception_ptr<winrt::hresult_canceled>(winrt::hresult_canceled)

- ea: `0x18001ff18`
- end: `0x18001ff81`
- name: `??$make_exception_ptr@Uhresult_canceled@winrt@@@std@@YA?AVexception_ptr@0@Uhresult_canceled@winrt@@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023f50`

## callees

- `0x1800035c3`
- `0x18000ed24`
- `0x18001ff18`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18001ff4a`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18001ff4a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001ff37`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001ff37`

## pseudocode

```c
_QWORD *__fastcall std::make_exception_ptr<winrt::hresult_canceled>(_QWORD *a1, BSTR *a2)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  __ExceptionPtrCopyException(a1, a2, &TI2_AUhresult_canceled_winrt__);
  if ( a2[2] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2 + 2);
  if ( *a2 )
  {
    WINRT_IMPL_SysFreeString(*a2);
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001ff18  mov     [rsp+arg_8], rbx
0x18001ff1d  push    rdi
0x18001ff1e  sub     rsp, 20h
0x18001ff22  mov     rdi, rdx
0x18001ff25  mov     qword ptr [rcx], 0
0x18001ff2c  mov     rbx, rcx
0x18001ff2f  mov     qword ptr [rcx+8], 0
0x18001ff37  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001ff3d  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x18001ff44  mov     rdx, rdi
0x18001ff47  mov     rcx, rbx
0x18001ff4a  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x18001ff50  lea     rcx, [rdi+10h]
0x18001ff54  cmp     qword ptr [rcx], 0
0x18001ff58  jz      short loc_18001FF5F
0x18001ff5a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ff5f  mov     rcx, [rdi]; bstrString
0x18001ff62  test    rcx, rcx
0x18001ff65  jz      short loc_18001FF73
0x18001ff67  call    WINRT_IMPL_SysFreeString
0x18001ff6c  mov     qword ptr [rdi], 0
0x18001ff73  mov     rax, rbx
0x18001ff76  mov     rbx, [rsp+28h+arg_8]
0x18001ff7b  add     rsp, 20h
0x18001ff7f  pop     rdi
0x18001ff80  retn
```
