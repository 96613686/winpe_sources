# Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)

- ea: `0x18001b048`
- end: `0x18001b100`
- name: `?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014054`

## callees

- `0x1800018b8`
- `0x180001f0c`
- `0x180001f7c`
- `0x180007568`
- `0x18001aa14`
- `0x18001b048`

## string_xrefs

- `0x18001b088`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001b0a0`: `Windows::WCP::Implementation::Rtl::GetSystemSecurity`
- `0x18001b0ac`: `g_SystemSecurityStatus`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::GetSystemSecurity(
        Windows::WCP::Implementation::Rtl *this,
        struct _SECURITY_DESCRIPTOR **a2)
{
  __int64 v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // ebx

  v3 = 4;
  v4 = *(unsigned int *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
  if ( dword_18002BB60 > (int)v4 )
  {
    Init_thread_header(&dword_18002BB60);
    if ( dword_18002BB60 == -1 )
    {
      Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()();
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__);
      Init_thread_footer(&dword_18002BB60);
    }
  }
  *(_QWORD *)this = P;
  v5 = dword_18002BB54;
  if ( dword_18002BB54 >= 0 )
    return 0;
  RtlReportErrorOrigination(v3, v4, (unsigned int)dword_18002BB54);
  return v5;
}

```

## disassembly

```asm
0x18001b048  push    rbx
0x18001b04a  sub     rsp, 40h
0x18001b04e  mov     edx, cs:_tls_index
0x18001b054  mov     rbx, rcx
0x18001b057  mov     rax, gs:58h
0x18001b060  mov     ecx, 4
0x18001b065  mov     rax, [rax+rdx*8]
0x18001b069  mov     edx, [rcx+rax]
0x18001b06c  cmp     cs:dword_18002BB60, edx
0x18001b072  jg      short loc_18001B0C9
0x18001b074  mov     rax, qword ptr cs:P
0x18001b07b  mov     [rbx], rax
0x18001b07e  mov     ebx, cs:dword_18002BB54
0x18001b084  test    ebx, ebx
0x18001b086  jns     short loc_18001B0C1
0x18001b088  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18001b08f  mov     [rsp+48h+var_18], 0C2h
0x18001b098  mov     [rsp+48h+var_28], rax
0x18001b09d  mov     r8d, ebx
0x18001b0a0  lea     rax, aWindowsWcpImpl_0; "Windows::WCP::Implementation::Rtl::GetS"...
0x18001b0a7  mov     [rsp+48h+var_20], rax
0x18001b0ac  lea     rax, aGSystemsecurit; "g_SystemSecurityStatus"
0x18001b0b3  mov     [rsp+48h+var_10], rax
0x18001b0b8  call    RtlReportErrorOrigination
0x18001b0bd  mov     eax, ebx
0x18001b0bf  jmp     short loc_18001B0C3
0x18001b0c1  xor     eax, eax
0x18001b0c3  add     rsp, 40h
0x18001b0c7  pop     rbx
0x18001b0c8  retn
0x18001b0c9  lea     rcx, dword_18002BB60
0x18001b0d0  call    _Init_thread_header
0x18001b0d5  cmp     cs:dword_18002BB60, 0FFFFFFFFh
0x18001b0dc  jnz     short loc_18001B074
0x18001b0de  call    _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____lambda_1___operator__
0x18001b0e3  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSecurity____5____dynamic_atexit_destructor_for__g_SystemSecurity__; void (__cdecl *)()
0x18001b0ea  call    atexit
0x18001b0ef  lea     rcx, dword_18002BB60
0x18001b0f6  call    _Init_thread_footer
0x18001b0fb  jmp     loc_18001B074
```
