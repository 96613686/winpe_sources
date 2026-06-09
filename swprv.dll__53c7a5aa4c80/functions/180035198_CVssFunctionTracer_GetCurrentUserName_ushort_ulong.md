# CVssFunctionTracer::GetCurrentUserName(ushort *,ulong)

- ea: `0x180035198`
- end: `0x180035359`
- name: `?GetCurrentUserName@CVssFunctionTracer@@QEAAXPEAGK@Z`
- size: `449`
- prototype: `void __fastcall(CVssFunctionTracer *this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800358f4`
- `0x1800379bc`

## callees

- `0x180001580`
- `0x18000212c`
- `0x18001c208`
- `0x180035198`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035253`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035253`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800351f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800351f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035204`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035204`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800351d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800351d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800351e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800351e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003532d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003532d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035239`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035239`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800352d3`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800352d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800352f0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800352f0`

## string_xrefs

- `0x180035314`: `Name: %s\%s, SID:%s`

## pseudocode

```c
void __fastcall CVssFunctionTracer::GetCurrentUserName(CVssFunctionTracer *this, unsigned __int16 *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+38h] [rbp-D0h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-C8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-C4h] BYREF
  DWORD cchName[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B8h] BYREF
  PSID TokenInformation[32]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR Name[8]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v12[496]; // [rsp+168h] [rbp+60h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+358h] [rbp+250h] BYREF
  _BYTE v14[496]; // [rsp+368h] [rbp+260h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)) )
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
      if ( LookupAccountSidLocalW(TokenInformation[0], Name, &cchName[1], ReferencedDomainName, cchName, &peUse) )
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
0x180035198  mov     rax, rsp
0x18003519b  mov     [rax+8], rbx
0x18003519f  push    rbp
0x1800351a0  lea     rbp, [rax-478h]
0x1800351a7  sub     rsp, 570h
0x1800351ae  movaps  xmmword ptr [rax-18h], xmm6
0x1800351b2  mov     rax, cs:__security_cookie
0x1800351b9  xor     rax, rsp
0x1800351bc  mov     [rbp+470h+var_20], rax
0x1800351c3  mov     rbx, rdx
0x1800351c6  xor     eax, eax
0x1800351c8  mov     [rdx], ax
0x1800351cb  mov     [rsp+570h+TokenHandle], rax
0x1800351d0  call    cs:__imp_GetCurrentThread
0x1800351d6  mov     rcx, rax; ThreadHandle
0x1800351d9  lea     r9, [rsp+570h+TokenHandle]; TokenHandle
0x1800351de  mov     edx, 8; DesiredAccess
0x1800351e3  lea     r8d, [rdx-7]; OpenAsSelf
0x1800351e7  call    cs:__imp_OpenThreadToken
0x1800351ed  test    eax, eax
0x1800351ef  jnz     short loc_180035212
0x1800351f1  call    cs:__imp_GetCurrentProcess
0x1800351f7  mov     rcx, rax; ProcessHandle
0x1800351fa  lea     r8, [rsp+570h+TokenHandle]; TokenHandle
0x1800351ff  mov     edx, 8; DesiredAccess
0x180035204  call    cs:__imp_OpenProcessToken
0x18003520a  test    eax, eax
0x18003520c  jz      loc_180035334
0x180035212  mov     [rsp+570h+var_538], 0
0x18003521a  lea     rax, [rsp+570h+var_538]
0x18003521f  mov     [rsp+570h+ReturnLength], rax; ReturnLength
0x180035224  mov     r9d, 100h; TokenInformationLength
0x18003522a  lea     r8, [rsp+570h+TokenInformation]; TokenInformation
0x18003522f  mov     edx, 1; TokenInformationClass
0x180035234  mov     rcx, [rsp+570h+TokenHandle]; TokenHandle
0x180035239  call    cs:__imp_GetTokenInformation
0x18003523f  mov     rcx, [rsp+570h+TokenHandle]; hObject
0x180035244  test    eax, eax
0x180035246  jnz     short loc_180035253
0x180035248  call    cs:__imp_CloseHandle
0x18003524e  jmp     loc_180035334
0x180035253  call    cs:__imp_CloseHandle
0x180035259  movups  xmm6, xmmword ptr cs:aUnknown; "Unknown"
0x180035260  movdqu  xmmword ptr [rbp+470h+ReferencedDomainName], xmm6
0x180035268  xor     edx, edx; Val
0x18003526a  mov     r8d, 1F0h; Size
0x180035270  lea     rcx, [rbp+470h+var_210]; void *
0x180035277  call    memset_0
0x18003527c  movdqu  xmmword ptr [rbp+470h+Name], xmm6
0x180035281  xor     edx, edx; Val
0x180035283  mov     r8d, 1F0h; Size
0x180035289  lea     rcx, [rbp+470h+var_410]; void *
0x18003528d  call    memset_0
0x180035292  mov     [rsp+570h+cchName+4], 100h
0x18003529a  mov     [rsp+570h+cchName], 100h
0x1800352a2  mov     [rsp+570h+var_534], 0
0x1800352aa  lea     rax, [rsp+570h+var_534]
0x1800352af  mov     [rsp+570h+peUse], rax; peUse
0x1800352b4  lea     rax, [rsp+570h+cchName]
0x1800352b9  mov     [rsp+570h+ReturnLength], rax; cchReferencedDomainName
0x1800352be  lea     r9, [rbp+470h+ReferencedDomainName]; ReferencedDomainName
0x1800352c5  lea     r8, [rsp+570h+cchName+4]; cchName
0x1800352ca  lea     rdx, [rbp+470h+Name]; Name
0x1800352ce  mov     rcx, [rsp+570h+TokenInformation]; Sid
0x1800352d3  call    cs:__imp_LookupAccountSidLocalW
0x1800352d9  test    eax, eax
0x1800352db  jz      short loc_180035334
0x1800352dd  mov     [rsp+570h+StringSid], 0
0x1800352e6  lea     rdx, [rsp+570h+StringSid]; StringSid
0x1800352eb  mov     rcx, [rsp+570h+TokenInformation]; Sid
0x1800352f0  call    cs:__imp_ConvertSidToStringSidW
0x1800352f6  test    eax, eax
0x1800352f8  jz      short loc_180035334
0x1800352fa  mov     rax, [rsp+570h+StringSid]
0x1800352ff  mov     [rsp+570h+peUse], rax
0x180035304  lea     rax, [rbp+470h+Name]
0x180035308  mov     [rsp+570h+ReturnLength], rax
0x18003530d  lea     r9, [rbp+470h+ReferencedDomainName]
0x180035314  lea     r8, aNameSSSidS; "Name: %s\\%s, SID:%s"
0x18003531b  mov     edx, 400h; unsigned __int64
0x180035320  mov     rcx, rbx; unsigned __int16 *
0x180035323  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035328  mov     rcx, [rsp+570h+StringSid]; hMem
0x18003532d  call    cs:__imp_LocalFree
0x180035333  nop
0x180035334  mov     rcx, [rbp+470h+var_20]
0x18003533b  xor     rcx, rsp; StackCookie
0x18003533e  call    __security_check_cookie
0x180035343  lea     r11, [rsp+570h+var_s0]
0x18003534b  mov     rbx, [r11+10h]
0x18003534f  movaps  xmm6, xmmword ptr [r11-10h]
0x180035354  mov     rsp, r11
0x180035357  pop     rbp
0x180035358  retn
```
