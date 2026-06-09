# _Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()

- ea: `0x18001aa14`
- end: `0x18001ab56`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()`
- size: `322`
- prototype: `PVOID *()`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b048`

## callees

- `0x1800018b8`
- `0x180001f0c`
- `0x180001f7c`
- `0x180007568`
- `0x18001aa14`
- `0x18001aed4`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18001ab2d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001ab2d`

## string_xrefs

- `0x18001aa55`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001aa6d`: `Windows::WCP::Implementation::Rtl::GetSystemSid`
- `0x18001aa79`: `g_SystemSidStatus`

## pseudocode

```c
PVOID *Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()()
{
  __int64 v0; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v2; // rdx
  int SecurityDescriptorFromParts; // ebx

  v0 = (unsigned int)tls_index;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v2 = 4;
  *(_OWORD *)&P = 0;
  if ( dword_18002BB64 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
  {
    Init_thread_header(&dword_18002BB64);
    if ( dword_18002BB64 == -1 )
    {
      Sid = 0;
      dword_18002BB50 = RtlAllocateAndInitializeSid(
                          (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority,
                          1u,
                          0x12u,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          &Sid);
      atexit(Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__);
      Init_thread_footer(&dword_18002BB64);
    }
  }
  SecurityDescriptorFromParts = dword_18002BB50;
  if ( dword_18002BB50 >= 0 )
  {
    dword_18002BB54 = 0;
    SecurityDescriptorFromParts = Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(v0, v2, Sid, Sid);
  }
  else
  {
    RtlReportErrorOrigination(v0, v2, (unsigned int)dword_18002BB50);
  }
  dword_18002BB54 = SecurityDescriptorFromParts;
  return &P;
}

```

## disassembly

```asm
0x18001aa14  push    rbx
0x18001aa16  sub     rsp, 80h
0x18001aa1d  mov     ecx, cs:_tls_index
0x18001aa23  xorps   xmm0, xmm0
0x18001aa26  mov     rax, gs:58h
0x18001aa2f  mov     edx, 4
0x18001aa34  movdqu  cs:P, xmm0
0x18001aa3c  mov     rax, [rax+rcx*8]
0x18001aa40  mov     eax, [rdx+rax]
0x18001aa43  cmp     cs:dword_18002BB64, eax
0x18001aa49  jg      short loc_18001AABD
0x18001aa4b  mov     ebx, cs:dword_18002BB50
0x18001aa51  test    ebx, ebx
0x18001aa53  jns     short loc_18001AA8C
0x18001aa55  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18001aa5c  mov     [rsp+88h+var_18], 77h ; 'w'
0x18001aa65  mov     [rsp+88h+var_28], rax
0x18001aa6a  mov     r8d, ebx
0x18001aa6d  lea     rax, aWindowsWcpImpl_2; "Windows::WCP::Implementation::Rtl::GetS"...
0x18001aa74  mov     [rsp+88h+var_20], rax
0x18001aa79  lea     rax, aGSystemsidstat; "g_SystemSidStatus"
0x18001aa80  mov     [rsp+88h+var_10], rax
0x18001aa85  call    RtlReportErrorOrigination
0x18001aa8a  jmp     short loc_18001AAA7
0x18001aa8c  mov     r8, cs:Sid
0x18001aa93  mov     r9, r8
0x18001aa96  mov     cs:dword_18002BB54, 0
0x18001aaa0  call    ?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z; Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)
0x18001aaa5  mov     ebx, eax
0x18001aaa7  mov     cs:dword_18002BB54, ebx
0x18001aaad  lea     rax, P
0x18001aab4  add     rsp, 80h
0x18001aabb  pop     rbx
0x18001aabc  retn
0x18001aabd  lea     rcx, dword_18002BB64
0x18001aac4  call    _Init_thread_header
0x18001aac9  cmp     cs:dword_18002BB64, 0FFFFFFFFh
0x18001aad0  jnz     loc_18001AA4B
0x18001aad6  lea     rax, Sid
0x18001aadd  mov     cs:Sid, 0
0x18001aae8  mov     [rsp+88h+Sid], rax; Sid
0x18001aaed  lea     rcx, IdentifierAuthority; IdentifierAuthority
0x18001aaf4  mov     [rsp+88h+SubAuthority7], 0; SubAuthority7
0x18001aafc  xor     r9d, r9d; SubAuthority1
0x18001aaff  mov     [rsp+88h+SubAuthority6], 0; SubAuthority6
0x18001ab07  mov     dl, 1; SubAuthorityCount
0x18001ab09  mov     [rsp+88h+SubAuthority5], 0; SubAuthority5
0x18001ab11  mov     [rsp+88h+SubAuthority4], 0; SubAuthority4
0x18001ab19  mov     [rsp+88h+SubAuthority3], 0; SubAuthority3
0x18001ab21  lea     r8d, [r9+12h]; SubAuthority0
0x18001ab25  mov     [rsp+88h+SubAuthority2], 0; SubAuthority2
0x18001ab2d  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001ab33  lea     rcx, _Windows__WCP__Implementation__Rtl__GetSystemSid____5____dynamic_atexit_destructor_for__g_SystemSid__; void (__cdecl *)()
0x18001ab3a  mov     cs:dword_18002BB50, eax
0x18001ab40  call    atexit
0x18001ab45  lea     rcx, dword_18002BB64
0x18001ab4c  call    _Init_thread_footer
0x18001ab51  jmp     loc_18001AA4B
```
