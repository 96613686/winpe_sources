# CSGetBuiltInDomainSid

- ea: `0x18000b9e0`
- end: `0x18000bb0f`
- name: `CSGetBuiltInDomainSid`
- size: `303`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003b10`
- `0x180008ad0`
- `0x180010230`
- `0x180011150`
- `0x180011640`
- `0x180011e80`
- `0x180012acc`

## callees

- `0x18000b9e0`
- `0x18000c240`
- `0x180012f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baa0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000ba86`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000ba86`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ba54`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ba74`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ba54`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ba74`
- `ntdll!RtlSubAuthoritySid` at `0x18000ba41`
- `ntdll!RtlSubAuthoritySid` at `0x18000ba41`
- `ntdll!RtlInitializeSid` at `0x18000ba32`
- `ntdll!RtlInitializeSid` at `0x18000ba32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba5c`

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
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
  {
    v2 = -2147467261;
    goto LABEL_13;
  }
  if ( !byte_1800204C0 )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    RtlInitializeSid(&byte_1800204C0, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(&byte_1800204C0, 0) = 32;
  }
  LengthSid = GetLengthSid(&byte_1800204C0);
  v4 = CoTaskMemAlloc(LengthSid);
  *a1 = v4;
  v5 = v4;
  if ( !v4 )
  {
    v2 = -2147024882;
LABEL_13:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v2);
    return v2;
  }
  v6 = GetLengthSid(&byte_1800204C0);
  if ( CopySid(v6, v5, &byte_1800204C0) )
    return 0;
  CoTaskMemFree(*a1);
  *a1 = 0;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
    goto LABEL_13;
  return v2;
}

```

## disassembly

```asm
0x18000b9e0  mov     [rsp+arg_8], rbx
0x18000b9e5  push    rdi
0x18000b9e6  sub     rsp, 30h
0x18000b9ea  mov     rax, cs:__security_cookie
0x18000b9f1  xor     rax, rsp
0x18000b9f4  mov     [rsp+38h+var_10], rax
0x18000b9f9  mov     rbx, rcx
0x18000b9fc  test    rcx, rcx
0x18000b9ff  jnz     short loc_18000BA0B
0x18000ba01  mov     ebx, 80004003h
0x18000ba06  jmp     loc_18000BAC4
0x18000ba0b  cmp     cs:byte_1800204C0, 0
0x18000ba12  jnz     short loc_18000BA4D
0x18000ba14  mov     r8b, 1; SubAuthorityCount
0x18000ba17  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], 0
0x18000ba1f  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x18000ba24  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x18000ba2b  lea     rcx, byte_1800204C0; Sid
0x18000ba32  call    cs:__imp_RtlInitializeSid
0x18000ba38  xor     edx, edx; SubAuthority
0x18000ba3a  lea     rcx, byte_1800204C0; Sid
0x18000ba41  call    cs:__imp_RtlSubAuthoritySid
0x18000ba47  mov     dword ptr [rax], 20h ; ' '
0x18000ba4d  lea     rcx, byte_1800204C0; pSid
0x18000ba54  call    cs:__imp_GetLengthSid
0x18000ba5a  mov     ecx, eax; cb
0x18000ba5c  call    cs:__imp_CoTaskMemAlloc
0x18000ba62  mov     [rbx], rax
0x18000ba65  mov     rdi, rax
0x18000ba68  test    rax, rax
0x18000ba6b  jz      short loc_18000BABF
0x18000ba6d  lea     rcx, byte_1800204C0; pSid
0x18000ba74  call    cs:__imp_GetLengthSid
0x18000ba7a  lea     r8, byte_1800204C0; pSourceSid
0x18000ba81  mov     rdx, rdi; pDestinationSid
0x18000ba84  mov     ecx, eax; nDestinationSidLength
0x18000ba86  call    cs:__imp_CopySid
0x18000ba8c  test    eax, eax
0x18000ba8e  jnz     short loc_18000BABB
0x18000ba90  mov     rcx, [rbx]; pv
0x18000ba93  call    cs:__imp_CoTaskMemFree
0x18000ba99  mov     qword ptr [rbx], 0
0x18000baa0  call    cs:__imp_GetLastError
0x18000baa6  mov     ebx, eax
0x18000baa8  test    eax, eax
0x18000baaa  jle     short loc_18000BAB5
0x18000baac  movzx   ebx, ax
0x18000baaf  or      ebx, 80070000h
0x18000bab5  test    ebx, ebx
0x18000bab7  js      short loc_18000BAC4
0x18000bab9  jmp     short loc_18000BAF5
0x18000babb  xor     eax, eax
0x18000babd  jmp     short loc_18000BAF7
0x18000babf  mov     ebx, 8007000Eh
0x18000bac4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bacb  lea     rax, WPP_GLOBAL_Control
0x18000bad2  cmp     rcx, rax
0x18000bad5  jz      short loc_18000BAF5
0x18000bad7  test    byte ptr [rcx+1Ch], 2
0x18000badb  jz      short loc_18000BAF5
0x18000badd  mov     rcx, [rcx+10h]
0x18000bae1  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000bae8  mov     edx, 1Fh
0x18000baed  mov     r9d, ebx
0x18000baf0  call    WPP_SF_d
0x18000baf5  mov     eax, ebx
0x18000baf7  mov     rcx, [rsp+38h+var_10]
0x18000bafc  xor     rcx, rsp; StackCookie
0x18000baff  call    __security_check_cookie
0x18000bb04  mov     rbx, [rsp+38h+arg_8]
0x18000bb09  add     rsp, 30h
0x18000bb0d  pop     rdi
0x18000bb0e  retn
```
