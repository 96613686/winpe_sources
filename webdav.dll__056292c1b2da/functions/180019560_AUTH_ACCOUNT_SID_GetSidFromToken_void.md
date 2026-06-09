# AUTH_ACCOUNT_SID::GetSidFromToken(void *)

- ea: `0x180019560`
- end: `0x18001968d`
- name: `?GetSidFromToken@AUTH_ACCOUNT_SID@@QEAAJPEAX@Z`
- size: `301`
- prototype: `int(AUTH_ACCOUNT_SID *__hidden this, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800021c4`

## callees

- `0x180019560`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019592`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019642`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019592`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001964c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001964c`
- `iisutil!PuDbgPrintError` at `0x1800195f9`
- `iisutil!PuDbgPrintError` at `0x1800195f9`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001960a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001960a`

## string_xrefs

- `0x1800195d6`: `Failed to get token info for %p (GetTokenInformation() failed)\n`
- `0x1800195e2`: `AUTH_ACCOUNT_SID::GetSidFromToken`

## pseudocode

```c
int __fastcall AUTH_ACCOUNT_SID::GetSidFromToken(AUTH_ACCOUNT_SID *this, void *a2)
{
  DWORD v2; // r9d
  void *v3; // r8
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // r8
  int result; // eax
  signed int v10; // eax
  DWORD ReturnLength; // [rsp+50h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 10);
  v3 = (void *)*((_QWORD *)this + 4);
  ReturnLength = 0;
  if ( GetTokenInformation(a2, TokenUser, v3, v2, &ReturnLength) )
  {
LABEL_17:
    result = 0;
    *((_QWORD *)this + 6) = **((_QWORD **)this + 4);
    return result;
  }
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      return v7;
    v8 = 325;
LABEL_7:
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\auth_util.cxx",
      v8,
      "AUTH_ACCOUNT_SID::GetSidFromToken",
      v7,
      "Failed to get token info for %p (GetTokenInformation() failed)\n",
      a2);
    return v7;
  }
  if ( BUFFER::Resize(this, ReturnLength) )
  {
    if ( !GetTokenInformation(a2, TokenUser, *((LPVOID *)this + 4), *((_DWORD *)this + 10), &ReturnLength) )
    {
      v10 = GetLastError();
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return v7;
      v8 = 360;
      goto LABEL_7;
    }
    goto LABEL_17;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180019560  mov     [rsp+arg_8], rbx
0x180019565  push    rdi
0x180019566  sub     rsp, 40h
0x18001956a  mov     r9d, [rcx+28h]; TokenInformationLength
0x18001956e  lea     rax, [rsp+48h+arg_0]
0x180019573  mov     r8, [rcx+20h]; TokenInformation
0x180019577  mov     rdi, rdx
0x18001957a  mov     rbx, rcx
0x18001957d  mov     [rsp+48h+arg_0], 0
0x180019585  mov     rcx, rdi; TokenHandle
0x180019588  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001958d  mov     edx, 1; TokenInformationClass
0x180019592  call    cs:__imp_GetTokenInformation
0x180019598  test    eax, eax
0x18001959a  jnz     loc_180019675
0x1800195a0  call    cs:__imp_GetLastError
0x1800195a6  cmp     eax, 7Ah ; 'z'
0x1800195a9  jz      short loc_180019603
0x1800195ab  call    cs:__imp_GetLastError
0x1800195b1  mov     ebx, eax
0x1800195b3  test    eax, eax
0x1800195b5  jle     short loc_1800195C0
0x1800195b7  movzx   ebx, ax
0x1800195ba  or      ebx, 80070000h
0x1800195c0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800195c7  jz      short loc_1800195FF
0x1800195c9  mov     r8d, 145h
0x1800195cf  mov     rcx, cs:g_pDebug
0x1800195d6  lea     rax, aFailedToGetTok; "Failed to get token info for %p (GetTok"...
0x1800195dd  mov     [rsp+48h+var_18], rdi
0x1800195e2  lea     r9, aAuthAccountSid_0; "AUTH_ACCOUNT_SID::GetSidFromToken"
0x1800195e9  mov     [rsp+48h+var_20], rax
0x1800195ee  lea     rdx, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x1800195f5  mov     dword ptr [rsp+48h+ReturnLength], ebx
0x1800195f9  call    cs:__imp_PuDbgPrintError
0x1800195ff  mov     eax, ebx
0x180019601  jmp     short loc_180019682
0x180019603  mov     edx, [rsp+48h+arg_0]
0x180019607  mov     rcx, rbx
0x18001960a  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180019610  test    al, al
0x180019612  jnz     short loc_180019628
0x180019614  call    cs:__imp_GetLastError
0x18001961a  test    eax, eax
0x18001961c  jle     short loc_180019682
0x18001961e  movzx   eax, ax
0x180019621  or      eax, 80070000h
0x180019626  jmp     short loc_180019682
0x180019628  mov     r9d, [rbx+28h]; TokenInformationLength
0x18001962c  lea     rax, [rsp+48h+arg_0]
0x180019631  mov     r8, [rbx+20h]; TokenInformation
0x180019635  mov     edx, 1; TokenInformationClass
0x18001963a  mov     rcx, rdi; TokenHandle
0x18001963d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180019642  call    cs:__imp_GetTokenInformation
0x180019648  test    eax, eax
0x18001964a  jnz     short loc_180019675
0x18001964c  call    cs:__imp_GetLastError
0x180019652  mov     ebx, eax
0x180019654  test    eax, eax
0x180019656  jle     short loc_180019661
0x180019658  movzx   ebx, ax
0x18001965b  or      ebx, 80070000h
0x180019661  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180019668  jz      short loc_1800195FF
0x18001966a  mov     r8d, 168h
0x180019670  jmp     loc_1800195CF
0x180019675  mov     rax, [rbx+20h]
0x180019679  mov     rcx, [rax]
0x18001967c  xor     eax, eax
0x18001967e  mov     [rbx+30h], rcx
0x180019682  mov     rbx, [rsp+48h+arg_8]
0x180019687  add     rsp, 40h
0x18001968b  pop     rdi
0x18001968c  retn
```
