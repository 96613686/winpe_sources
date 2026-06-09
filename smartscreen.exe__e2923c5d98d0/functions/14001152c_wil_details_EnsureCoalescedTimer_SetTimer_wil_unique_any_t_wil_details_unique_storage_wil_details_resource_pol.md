# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x14001152c`
- end: `0x140011585`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000cde8`

## callees

- `0x14001152c`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140011569`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140011569`

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
0x14001152c  push    rbx
0x14001152e  sub     rsp, 30h
0x140011532  mov     rax, cs:__security_cookie
0x140011539  xor     rax, rsp
0x14001153c  mov     [rsp+38h+var_10], rax
0x140011541  mov     rcx, [rcx]; pti
0x140011544  mov     rbx, rdx
0x140011547  test    rcx, rcx
0x14001154a  jz      short loc_140011572
0x14001154c  mov     rax, 0FFFFFFFF4D2FA200h
0x140011556  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x14001155b  mov     r9d, 124F8h; msWindowLength
0x140011561  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140011566  xor     r8d, r8d; msPeriod
0x140011569  call    cs:__imp_SetThreadpoolTimer
0x14001156f  mov     byte ptr [rbx], 1
0x140011572  mov     rcx, [rsp+38h+var_10]
0x140011577  xor     rcx, rsp; StackCookie
0x14001157a  call    __security_check_cookie
0x14001157f  add     rsp, 30h
0x140011583  pop     rbx
0x140011584  retn
```
