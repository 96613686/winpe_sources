# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x140011d38`
- end: `0x140011d98`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000d498`

## callees

- `0x140011d38`
- `0x140026c20`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140011d75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140011d75`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2)
{
  struct _TP_TIMER *v2; // rcx
  _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  v2 = *a1;
  if ( v2 )
  {
    pftDueTime = (_FILETIME)-3000000000LL;
    SetThreadpoolTimer(v2, &pftDueTime, 0, 0x124F8u);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x140011d38  push    rbx
0x140011d3a  sub     rsp, 30h
0x140011d3e  mov     rax, cs:__security_cookie
0x140011d45  xor     rax, rsp
0x140011d48  mov     [rsp+38h+var_10], rax
0x140011d4d  mov     rcx, [rcx]; pti
0x140011d50  mov     rbx, rdx
0x140011d53  test    rcx, rcx
0x140011d56  jz      short loc_140011D84
0x140011d58  mov     rax, 0FFFFFFFF4D2FA200h
0x140011d62  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140011d67  mov     r9d, 124F8h; msWindowLength
0x140011d6d  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140011d72  xor     r8d, r8d; msPeriod
0x140011d75  call    cs:__imp_SetThreadpoolTimer
0x140011d7c  nop     dword ptr [rax+rax+00h]
0x140011d81  mov     byte ptr [rbx], 1
0x140011d84  mov     rcx, [rsp+38h+var_10]
0x140011d89  xor     rcx, rsp; StackCookie
0x140011d8c  call    __security_check_cookie
0x140011d91  add     rsp, 30h
0x140011d95  pop     rbx
0x140011d96  retn
```
