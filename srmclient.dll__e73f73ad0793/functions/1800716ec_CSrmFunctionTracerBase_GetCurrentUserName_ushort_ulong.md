# CSrmFunctionTracerBase::GetCurrentUserName(ushort *,ulong)

- ea: `0x1800716ec`
- end: `0x1800718c4`
- name: `?GetCurrentUserName@CSrmFunctionTracerBase@@QEAAXPEAGK@Z`
- size: `472`
- prototype: `void(CSrmFunctionTracerBase *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180071efc`
- `0x180072598`
- `0x1800752c0`

## callees

- `0x180017fd8`
- `0x1800716ec`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800717ad`
- `KERNEL32!CloseHandle` at `0x1800717b8`
- `KERNEL32!CloseHandle` at `0x1800717ad`
- `KERNEL32!CloseHandle` at `0x1800717b8`
- `KERNEL32!GetCurrentProcess` at `0x180071756`
- `KERNEL32!GetCurrentProcess` at `0x180071756`
- `KERNEL32!GetLastError` at `0x180071745`
- `KERNEL32!GetLastError` at `0x180071745`
- `KERNEL32!LocalFree` at `0x180071899`
- `KERNEL32!LocalFree` at `0x180071899`
- `KERNEL32!GetCurrentThread` at `0x180071724`
- `KERNEL32!GetCurrentThread` at `0x180071724`
- `ADVAPI32!OpenProcessToken` at `0x180071769`
- `ADVAPI32!OpenProcessToken` at `0x180071769`
- `ADVAPI32!OpenThreadToken` at `0x18007173b`
- `ADVAPI32!OpenThreadToken` at `0x18007173b`
- `ADVAPI32!LookupAccountSidW` at `0x18007183f`
- `ADVAPI32!LookupAccountSidW` at `0x18007183f`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18007185c`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18007185c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007179e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007179e`

## string_xrefs

- `0x180071877`: `Name: %s\%s, SID:%s`

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
0x1800716ec  mov     rax, rsp
0x1800716ef  mov     [rax+8], rbx
0x1800716f3  push    rbp
0x1800716f4  lea     rbp, [rax-488h]
0x1800716fb  sub     rsp, 580h
0x180071702  movaps  xmmword ptr [rax-18h], xmm6
0x180071706  mov     rax, cs:__security_cookie
0x18007170d  xor     rax, rsp
0x180071710  mov     [rbp+480h+var_20], rax
0x180071717  xor     eax, eax
0x180071719  mov     rbx, rdx
0x18007171c  mov     [rdx], ax
0x18007171f  mov     [rsp+580h+TokenHandle], rax
0x180071724  call    cs:__imp_GetCurrentThread
0x18007172a  mov     edx, 8; DesiredAccess
0x18007172f  lea     r9, [rsp+580h+TokenHandle]; TokenHandle
0x180071734  mov     rcx, rax; ThreadHandle
0x180071737  lea     r8d, [rdx-7]; OpenAsSelf
0x18007173b  call    cs:__imp_OpenThreadToken
0x180071741  test    eax, eax
0x180071743  jnz     short loc_180071777
0x180071745  call    cs:__imp_GetLastError
0x18007174b  cmp     eax, 3F0h
0x180071750  jnz     loc_18007189F
0x180071756  call    cs:__imp_GetCurrentProcess
0x18007175c  lea     r8, [rsp+580h+TokenHandle]; TokenHandle
0x180071761  mov     edx, 8; DesiredAccess
0x180071766  mov     rcx, rax; ProcessHandle
0x180071769  call    cs:__imp_OpenProcessToken
0x18007176f  test    eax, eax
0x180071771  jz      loc_18007189F
0x180071777  mov     rcx, [rsp+580h+TokenHandle]; TokenHandle
0x18007177c  lea     rax, [rsp+580h+var_538]
0x180071781  mov     r9d, 100h; TokenInformationLength
0x180071787  mov     [rsp+580h+ReturnLength], rax; ReturnLength
0x18007178c  lea     r8, [rsp+580h+TokenInformation]; TokenInformation
0x180071791  mov     [rsp+580h+var_538], 0
0x180071799  mov     edx, 1; TokenInformationClass
0x18007179e  call    cs:__imp_GetTokenInformation
0x1800717a4  mov     rcx, [rsp+580h+TokenHandle]; hObject
0x1800717a9  test    eax, eax
0x1800717ab  jnz     short loc_1800717B8
0x1800717ad  call    cs:__imp_CloseHandle
0x1800717b3  jmp     loc_18007189F
0x1800717b8  call    cs:__imp_CloseHandle
0x1800717be  movups  xmm6, xmmword ptr cs:aUnknown_0; "Unknown"
0x1800717c5  xor     edx, edx; Val
0x1800717c7  lea     rcx, [rbp+480h+var_210]; void *
0x1800717ce  mov     r8d, 1F0h; Size
0x1800717d4  movdqu  xmmword ptr [rbp+480h+ReferencedDomainName], xmm6
0x1800717dc  call    memset_0
0x1800717e1  xor     edx, edx; Val
0x1800717e3  lea     rcx, [rbp+480h+var_410]; void *
0x1800717e7  mov     r8d, 1F0h; Size
0x1800717ed  movdqu  xmmword ptr [rbp+480h+Name], xmm6
0x1800717f2  call    memset_0
0x1800717f7  mov     rdx, [rsp+580h+TokenInformation]; Sid
0x1800717fc  lea     rax, [rsp+580h+var_534]
0x180071801  mov     [rsp+580h+peUse], rax; peUse
0x180071806  lea     r9, [rsp+580h+cchName+4]; cchName
0x18007180b  lea     rax, [rsp+580h+cchName]
0x180071810  mov     [rsp+580h+cchName+4], 100h
0x180071818  mov     [rsp+580h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18007181d  lea     r8, [rbp+480h+Name]; Name
0x180071821  lea     rax, [rbp+480h+ReferencedDomainName]
0x180071828  mov     [rsp+580h+cchName], 100h
0x180071830  xor     ecx, ecx; lpSystemName
0x180071832  mov     [rsp+580h+ReturnLength], rax; ReferencedDomainName
0x180071837  mov     [rsp+580h+var_534], 0
0x18007183f  call    cs:__imp_LookupAccountSidW
0x180071845  test    eax, eax
0x180071847  jz      short loc_18007189F
0x180071849  mov     rcx, [rsp+580h+TokenInformation]; Sid
0x18007184e  lea     rdx, [rsp+580h+StringSid]; StringSid
0x180071853  mov     [rsp+580h+StringSid], 0
0x18007185c  call    cs:__imp_ConvertSidToStringSidW
0x180071862  test    eax, eax
0x180071864  jz      short loc_18007189F
0x180071866  mov     rax, [rsp+580h+StringSid]
0x18007186b  lea     r9, [rbp+480h+ReferencedDomainName]
0x180071872  mov     [rsp+580h+cchReferencedDomainName], rax
0x180071877  lea     r8, aNameSSSidS; "Name: %s\\%s, SID:%s"
0x18007187e  lea     rax, [rbp+480h+Name]
0x180071882  mov     edx, 400h; unsigned __int64
0x180071887  mov     rcx, rbx; unsigned __int16 *
0x18007188a  mov     [rsp+580h+ReturnLength], rax
0x18007188f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180071894  mov     rcx, [rsp+580h+StringSid]; hMem
0x180071899  call    cs:__imp_LocalFree
0x18007189f  mov     rcx, [rbp+480h+var_20]
0x1800718a6  xor     rcx, rsp; StackCookie
0x1800718a9  call    __security_check_cookie
0x1800718ae  lea     r11, [rsp+580h+var_s0]
0x1800718b6  mov     rbx, [r11+10h]
0x1800718ba  movaps  xmm6, xmmword ptr [r11-10h]
0x1800718bf  mov     rsp, r11
0x1800718c2  pop     rbp
0x1800718c3  retn
```
