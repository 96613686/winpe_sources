# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18001ab44`
- end: `0x18001ab9d`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f934`

## callees

- `0x1800015f0`
- `0x18001ab44`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001ab81`
- `KERNEL32!SetThreadpoolTimer` at `0x18001ab81`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2)
{
  struct _TP_TIMER *v2; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  v2 = *a1;
  if ( v2 )
  {
    pftDueTime = (struct _FILETIME)-3000000000LL;
    SetThreadpoolTimer(v2, &pftDueTime, 0, 0x124F8u);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x18001ab44  push    rbx
0x18001ab46  sub     rsp, 30h
0x18001ab4a  mov     rax, cs:__security_cookie
0x18001ab51  xor     rax, rsp
0x18001ab54  mov     [rsp+38h+var_10], rax
0x18001ab59  mov     rcx, [rcx]; pti
0x18001ab5c  mov     rbx, rdx
0x18001ab5f  test    rcx, rcx
0x18001ab62  jz      short loc_18001AB8A
0x18001ab64  mov     rax, 0FFFFFFFF4D2FA200h
0x18001ab6e  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18001ab73  mov     r9d, 124F8h; msWindowLength
0x18001ab79  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18001ab7e  xor     r8d, r8d; msPeriod
0x18001ab81  call    cs:__imp_SetThreadpoolTimer
0x18001ab87  mov     byte ptr [rbx], 1
0x18001ab8a  mov     rcx, [rsp+38h+var_10]
0x18001ab8f  xor     rcx, rsp; StackCookie
0x18001ab92  call    __security_check_cookie
0x18001ab97  add     rsp, 30h
0x18001ab9b  pop     rbx
0x18001ab9c  retn
```
