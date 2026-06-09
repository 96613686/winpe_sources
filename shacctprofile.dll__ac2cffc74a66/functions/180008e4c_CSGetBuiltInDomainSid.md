# CSGetBuiltInDomainSid

- ea: `0x180008e4c`
- end: `0x180008f78`
- name: `CSGetBuiltInDomainSid`
- size: `300`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008f80`

## callees

- `0x180002230`
- `0x180008e4c`
- `0x1800090dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f04`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008ec0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008edc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008ec0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180008edc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180008eea`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180008eea`
- `ntdll!RtlInitializeSid` at `0x180008ea6`
- `ntdll!RtlInitializeSid` at `0x180008ea6`
- `ntdll!RtlSubAuthoritySid` at `0x180008eb1`
- `ntdll!RtlSubAuthoritySid` at `0x180008eb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ef7`

## pseudocode

```c
__int64 __fastcall CSGetBuiltInDomainSid(LPVOID *a1)
{
  unsigned int v2; // ebx
  DWORD LengthSid; // eax
  LPVOID v4; // rax
  void *v5; // rdi
  DWORD v6; // eax
  signed int LastError; // eax
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
  {
    v2 = -2147467261;
LABEL_13:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v2);
    return v2;
  }
  if ( !byte_18000FC18 )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    RtlInitializeSid(&byte_18000FC18, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(&byte_18000FC18, 0) = 32;
  }
  LengthSid = GetLengthSid(&byte_18000FC18);
  v4 = CoTaskMemAlloc(LengthSid);
  *a1 = v4;
  v5 = v4;
  if ( !v4 )
  {
    v2 = -2147024882;
    goto LABEL_13;
  }
  v6 = GetLengthSid(&byte_18000FC18);
  if ( CopySid(v6, v5, &byte_18000FC18) )
  {
    v2 = 0;
  }
  else
  {
    CoTaskMemFree(*a1);
    *a1 = 0;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (v2 & 0x80000000) != 0 )
    goto LABEL_13;
  return v2;
}

```

## disassembly

```asm
0x180008e4c  mov     [rsp+arg_8], rbx
0x180008e51  mov     [rsp+arg_10], rbp
0x180008e56  push    rdi
0x180008e57  sub     rsp, 30h
0x180008e5b  mov     rax, cs:__security_cookie
0x180008e62  xor     rax, rsp
0x180008e65  mov     [rsp+38h+var_10], rax
0x180008e6a  mov     rbx, rcx
0x180008e6d  test    rcx, rcx
0x180008e70  jnz     short loc_180008E7C
0x180008e72  mov     ebx, 80004003h
0x180008e77  jmp     loc_180008F28
0x180008e7c  cmp     cs:byte_18000FC18, 0
0x180008e83  lea     rbp, byte_18000FC18
0x180008e8a  jnz     short loc_180008EBD
0x180008e8c  mov     r8b, 1; SubAuthorityCount
0x180008e8f  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], 0
0x180008e97  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x180008e9c  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x180008ea3  mov     rcx, rbp; Sid
0x180008ea6  call    cs:__imp_RtlInitializeSid
0x180008eac  xor     edx, edx; SubAuthority
0x180008eae  mov     rcx, rbp; Sid
0x180008eb1  call    cs:__imp_RtlSubAuthoritySid
0x180008eb7  mov     dword ptr [rax], 20h ; ' '
0x180008ebd  mov     rcx, rbp; pSid
0x180008ec0  call    cs:__imp_GetLengthSid
0x180008ec6  mov     ecx, eax; cb
0x180008ec8  call    cs:__imp_CoTaskMemAlloc
0x180008ece  mov     [rbx], rax
0x180008ed1  mov     rdi, rax
0x180008ed4  test    rax, rax
0x180008ed7  jz      short loc_180008F23
0x180008ed9  mov     rcx, rbp; pSid
0x180008edc  call    cs:__imp_GetLengthSid
0x180008ee2  mov     r8, rbp; pSourceSid
0x180008ee5  mov     rdx, rdi; pDestinationSid
0x180008ee8  mov     ecx, eax; nDestinationSidLength
0x180008eea  call    cs:__imp_CopySid
0x180008ef0  test    eax, eax
0x180008ef2  jnz     short loc_180008F1B
0x180008ef4  mov     rcx, [rbx]; pv
0x180008ef7  call    cs:__imp_CoTaskMemFree
0x180008efd  mov     qword ptr [rbx], 0
0x180008f04  call    cs:__imp_GetLastError
0x180008f0a  mov     ebx, eax
0x180008f0c  test    eax, eax
0x180008f0e  jle     short loc_180008F1D
0x180008f10  movzx   ebx, ax
0x180008f13  or      ebx, 80070000h
0x180008f19  jmp     short loc_180008F1D
0x180008f1b  xor     ebx, ebx
0x180008f1d  test    ebx, ebx
0x180008f1f  jns     short loc_180008F59
0x180008f21  jmp     short loc_180008F28
0x180008f23  mov     ebx, 8007000Eh
0x180008f28  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f2f  lea     rax, WPP_GLOBAL_Control
0x180008f36  cmp     rcx, rax
0x180008f39  jz      short loc_180008F59
0x180008f3b  test    byte ptr [rcx+1Ch], 2
0x180008f3f  jz      short loc_180008F59
0x180008f41  mov     rcx, [rcx+10h]
0x180008f45  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180008f4c  mov     edx, 1Fh
0x180008f51  mov     r9d, ebx
0x180008f54  call    WPP_SF_D
0x180008f59  mov     eax, ebx
0x180008f5b  mov     rcx, [rsp+38h+var_10]
0x180008f60  xor     rcx, rsp; StackCookie
0x180008f63  call    __security_check_cookie
0x180008f68  mov     rbx, [rsp+38h+arg_8]
0x180008f6d  mov     rbp, [rsp+38h+arg_10]
0x180008f72  add     rsp, 30h
0x180008f76  pop     rdi
0x180008f77  retn
```
