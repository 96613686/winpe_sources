# CSrmFunctionTracerBase::GetCurrentUserName(ushort *,ulong)

- ea: `0x180017820`
- end: `0x1800179f8`
- name: `?GetCurrentUserName@CSrmFunctionTracerBase@@QEAAXPEAGK@Z`
- size: `472`
- prototype: `void __fastcall(CSrmFunctionTracerBase *this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800180a0`
- `0x180019e80`

## callees

- `0x18000f424`
- `0x180017820`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017879`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001786f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001786f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001788a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001788a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001789d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001789d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017858`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800179cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800179cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800178ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800178d2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800178d2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180017973`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180017973`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017990`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017990`

## string_xrefs

- `0x1800179ab`: `Name: %s\%s, SID:%s`

## pseudocode

```c
void __fastcall CSrmFunctionTracerBase::GetCurrentUserName(CSrmFunctionTracerBase *this, unsigned __int16 *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+48h] [rbp-C0h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+54h] [rbp-B4h] BYREF
  DWORD cchName[2]; // [rsp+58h] [rbp-B0h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A8h] BYREF
  PSID TokenInformation[32]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR Name[8]; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v12[496]; // [rsp+178h] [rbp+70h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+368h] [rbp+260h] BYREF
  _BYTE v14[496]; // [rsp+378h] [rbp+270h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || GetLastError() == 1008
    && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)) )
  {
    ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, &ReturnLength) )
    {
      CloseHandle(TokenHandle);
      wcscpy(ReferencedDomainName, L"Unknown");
      memset_0(v14, 0, sizeof(v14));
      wcscpy(Name, L"Unknown");
      memset_0(v12, 0, sizeof(v12));
      cchName[1] = 256;
      cchName[0] = 256;
      peUse = 0;
      if ( LookupAccountSidW(0, TokenInformation[0], Name, &cchName[1], ReferencedDomainName, cchName, &peUse) )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
        {
          StringCchPrintfW(a2, 0x400u, L"Name: %s\\%s, SID:%s", ReferencedDomainName, Name, StringSid);
          LocalFree(StringSid);
        }
      }
    }
    else
    {
      CloseHandle(TokenHandle);
    }
  }
}

```

## disassembly

```asm
0x180017820  mov     rax, rsp
0x180017823  mov     [rax+8], rbx
0x180017827  push    rbp
0x180017828  lea     rbp, [rax-488h]
0x18001782f  sub     rsp, 580h
0x180017836  movaps  xmmword ptr [rax-18h], xmm6
0x18001783a  mov     rax, cs:__security_cookie
0x180017841  xor     rax, rsp
0x180017844  mov     [rbp+480h+var_20], rax
0x18001784b  xor     eax, eax
0x18001784d  mov     rbx, rdx
0x180017850  mov     [rdx], ax
0x180017853  mov     [rsp+580h+TokenHandle], rax
0x180017858  call    cs:__imp_GetCurrentThread
0x18001785e  mov     edx, 8; DesiredAccess
0x180017863  lea     r9, [rsp+580h+TokenHandle]; TokenHandle
0x180017868  mov     rcx, rax; ThreadHandle
0x18001786b  lea     r8d, [rdx-7]; OpenAsSelf
0x18001786f  call    cs:__imp_OpenThreadToken
0x180017875  test    eax, eax
0x180017877  jnz     short loc_1800178AB
0x180017879  call    cs:__imp_GetLastError
0x18001787f  cmp     eax, 3F0h
0x180017884  jnz     loc_1800179D3
0x18001788a  call    cs:__imp_GetCurrentProcess
0x180017890  lea     r8, [rsp+580h+TokenHandle]; TokenHandle
0x180017895  mov     edx, 8; DesiredAccess
0x18001789a  mov     rcx, rax; ProcessHandle
0x18001789d  call    cs:__imp_OpenProcessToken
0x1800178a3  test    eax, eax
0x1800178a5  jz      loc_1800179D3
0x1800178ab  mov     rcx, [rsp+580h+TokenHandle]; TokenHandle
0x1800178b0  lea     rax, [rsp+580h+var_538]
0x1800178b5  mov     r9d, 100h; TokenInformationLength
0x1800178bb  mov     [rsp+580h+ReturnLength], rax; ReturnLength
0x1800178c0  lea     r8, [rsp+580h+TokenInformation]; TokenInformation
0x1800178c5  mov     [rsp+580h+var_538], 0
0x1800178cd  mov     edx, 1; TokenInformationClass
0x1800178d2  call    cs:__imp_GetTokenInformation
0x1800178d8  mov     rcx, [rsp+580h+TokenHandle]; hObject
0x1800178dd  test    eax, eax
0x1800178df  jnz     short loc_1800178EC
0x1800178e1  call    cs:__imp_CloseHandle
0x1800178e7  jmp     loc_1800179D3
0x1800178ec  call    cs:__imp_CloseHandle
0x1800178f2  movups  xmm6, xmmword ptr cs:aUnknown; "Unknown"
0x1800178f9  xor     edx, edx; Val
0x1800178fb  lea     rcx, [rbp+480h+var_210]; void *
0x180017902  mov     r8d, 1F0h; Size
0x180017908  movdqu  xmmword ptr [rbp+480h+ReferencedDomainName], xmm6
0x180017910  call    memset_0
0x180017915  xor     edx, edx; Val
0x180017917  lea     rcx, [rbp+480h+var_410]; void *
0x18001791b  mov     r8d, 1F0h; Size
0x180017921  movdqu  xmmword ptr [rbp+480h+Name], xmm6
0x180017926  call    memset_0
0x18001792b  mov     rdx, [rsp+580h+TokenInformation]; Sid
0x180017930  lea     rax, [rsp+580h+var_534]
0x180017935  mov     [rsp+580h+peUse], rax; peUse
0x18001793a  lea     r9, [rsp+580h+cchName+4]; cchName
0x18001793f  lea     rax, [rsp+580h+cchName]
0x180017944  mov     [rsp+580h+cchName+4], 100h
0x18001794c  mov     [rsp+580h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180017951  lea     r8, [rbp+480h+Name]; Name
0x180017955  lea     rax, [rbp+480h+ReferencedDomainName]
0x18001795c  mov     [rsp+580h+cchName], 100h
0x180017964  xor     ecx, ecx; lpSystemName
0x180017966  mov     [rsp+580h+ReturnLength], rax; ReferencedDomainName
0x18001796b  mov     [rsp+580h+var_534], 0
0x180017973  call    cs:__imp_LookupAccountSidW
0x180017979  test    eax, eax
0x18001797b  jz      short loc_1800179D3
0x18001797d  mov     rcx, [rsp+580h+TokenInformation]; Sid
0x180017982  lea     rdx, [rsp+580h+StringSid]; StringSid
0x180017987  mov     [rsp+580h+StringSid], 0
0x180017990  call    cs:__imp_ConvertSidToStringSidW
0x180017996  test    eax, eax
0x180017998  jz      short loc_1800179D3
0x18001799a  mov     rax, [rsp+580h+StringSid]
0x18001799f  lea     r9, [rbp+480h+ReferencedDomainName]
0x1800179a6  mov     [rsp+580h+cchReferencedDomainName], rax
0x1800179ab  lea     r8, aNameSSSidS; "Name: %s\\%s, SID:%s"
0x1800179b2  lea     rax, [rbp+480h+Name]
0x1800179b6  mov     edx, 400h; unsigned __int64
0x1800179bb  mov     rcx, rbx; unsigned __int16 *
0x1800179be  mov     [rsp+580h+ReturnLength], rax
0x1800179c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800179c8  mov     rcx, [rsp+580h+StringSid]; hMem
0x1800179cd  call    cs:__imp_LocalFree
0x1800179d3  mov     rcx, [rbp+480h+var_20]
0x1800179da  xor     rcx, rsp; StackCookie
0x1800179dd  call    __security_check_cookie
0x1800179e2  lea     r11, [rsp+580h+var_s0]
0x1800179ea  mov     rbx, [r11+10h]
0x1800179ee  movaps  xmm6, xmmword ptr [r11-10h]
0x1800179f3  mov     rsp, r11
0x1800179f6  pop     rbp
0x1800179f7  retn
```
