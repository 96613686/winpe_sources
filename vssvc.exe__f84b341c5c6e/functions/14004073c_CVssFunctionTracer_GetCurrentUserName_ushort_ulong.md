# CVssFunctionTracer::GetCurrentUserName(ushort *,ulong)

- ea: `0x14004073c`
- end: `0x1400408fc`
- name: `?GetCurrentUserName@CVssFunctionTracer@@QEAAXPEAGK@Z`
- size: `448`
- prototype: `void(CVssFunctionTracer *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400330fc`
- `0x1400ce55c`

## callees

- `0x140010170`
- `0x14004073c`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14004078b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14004078b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140040774`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140040774`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400407a8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400407a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140040795`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140040795`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400407ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400407f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400407ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400407f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400408d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400408d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400407dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400407dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140040894`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140040894`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140040877`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140040877`

## string_xrefs

- `0x1400408af`: `Name: %s\%s, SID:%s`

## pseudocode

```c
void __fastcall CVssFunctionTracer::GetCurrentUserName(CVssFunctionTracer *this, unsigned __int16 *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+38h] [rbp-D0h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-C8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-C4h] BYREF
  DWORD cchReferencedDomainName[2]; // [rsp+48h] [rbp-C0h] BYREF
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
      cchReferencedDomainName[1] = 256;
      cchReferencedDomainName[0] = 256;
      peUse = 0;
      if ( LookupAccountSidLocalW(
             TokenInformation[0],
             Name,
             &cchReferencedDomainName[1],
             ReferencedDomainName,
             cchReferencedDomainName,
             &peUse) )
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
0x14004073c  mov     rax, rsp
0x14004073f  mov     [rax+8], rbx
0x140040743  push    rbp
0x140040744  lea     rbp, [rax-478h]
0x14004074b  sub     rsp, 570h
0x140040752  movaps  xmmword ptr [rax-18h], xmm6
0x140040756  mov     rax, cs:__security_cookie
0x14004075d  xor     rax, rsp
0x140040760  mov     [rbp+470h+var_20], rax
0x140040767  xor     eax, eax
0x140040769  mov     rbx, rdx
0x14004076c  mov     [rdx], ax
0x14004076f  mov     [rsp+570h+TokenHandle], rax
0x140040774  call    cs:__imp_GetCurrentThread
0x14004077a  mov     edx, 8; DesiredAccess
0x14004077f  lea     r9, [rsp+570h+TokenHandle]; TokenHandle
0x140040784  mov     rcx, rax; ThreadHandle
0x140040787  lea     r8d, [rdx-7]; OpenAsSelf
0x14004078b  call    cs:__imp_OpenThreadToken
0x140040791  test    eax, eax
0x140040793  jnz     short loc_1400407B6
0x140040795  call    cs:__imp_GetCurrentProcess
0x14004079b  lea     r8, [rsp+570h+TokenHandle]; TokenHandle
0x1400407a0  mov     edx, 8; DesiredAccess
0x1400407a5  mov     rcx, rax; ProcessHandle
0x1400407a8  call    cs:__imp_OpenProcessToken
0x1400407ae  test    eax, eax
0x1400407b0  jz      loc_1400408D7
0x1400407b6  mov     rcx, [rsp+570h+TokenHandle]; TokenHandle
0x1400407bb  lea     rax, [rsp+570h+var_538]
0x1400407c0  mov     r9d, 100h; TokenInformationLength
0x1400407c6  mov     [rsp+570h+ReturnLength], rax; ReturnLength
0x1400407cb  lea     r8, [rsp+570h+TokenInformation]; TokenInformation
0x1400407d0  mov     [rsp+570h+var_538], 0
0x1400407d8  mov     edx, 1; TokenInformationClass
0x1400407dd  call    cs:__imp_GetTokenInformation
0x1400407e3  mov     rcx, [rsp+570h+TokenHandle]; hObject
0x1400407e8  test    eax, eax
0x1400407ea  jnz     short loc_1400407F7
0x1400407ec  call    cs:__imp_CloseHandle
0x1400407f2  jmp     loc_1400408D7
0x1400407f7  call    cs:__imp_CloseHandle
0x1400407fd  movups  xmm6, xmmword ptr cs:aUnknown_0; "Unknown"
0x140040804  xor     edx, edx; Val
0x140040806  lea     rcx, [rbp+470h+var_210]; void *
0x14004080d  mov     r8d, 1F0h; Size
0x140040813  movdqu  xmmword ptr [rbp+470h+ReferencedDomainName], xmm6
0x14004081b  call    memset_0
0x140040820  xor     edx, edx; Val
0x140040822  lea     rcx, [rbp+470h+var_410]; void *
0x140040826  mov     r8d, 1F0h; Size
0x14004082c  movdqu  xmmword ptr [rbp+470h+Name], xmm6
0x140040831  call    memset_0
0x140040836  mov     rcx, [rsp+570h+TokenInformation]; Sid
0x14004083b  lea     rax, [rsp+570h+var_534]
0x140040840  mov     [rsp+570h+peUse], rax; peUse
0x140040845  lea     r9, [rbp+470h+ReferencedDomainName]; ReferencedDomainName
0x14004084c  lea     rax, [rsp+570h+cchReferencedDomainName]
0x140040851  mov     [rsp+570h+cchReferencedDomainName+4], 100h
0x140040859  lea     r8, [rsp+570h+cchReferencedDomainName+4]; cchName
0x14004085e  mov     [rsp+570h+ReturnLength], rax; cchReferencedDomainName
0x140040863  lea     rdx, [rbp+470h+Name]; Name
0x140040867  mov     [rsp+570h+cchReferencedDomainName], 100h
0x14004086f  mov     [rsp+570h+var_534], 0
0x140040877  call    cs:__imp_LookupAccountSidLocalW
0x14004087d  test    eax, eax
0x14004087f  jz      short loc_1400408D7
0x140040881  mov     rcx, [rsp+570h+TokenInformation]; Sid
0x140040886  lea     rdx, [rsp+570h+StringSid]; StringSid
0x14004088b  mov     [rsp+570h+StringSid], 0
0x140040894  call    cs:__imp_ConvertSidToStringSidW
0x14004089a  test    eax, eax
0x14004089c  jz      short loc_1400408D7
0x14004089e  mov     rax, [rsp+570h+StringSid]
0x1400408a3  lea     r9, [rbp+470h+ReferencedDomainName]
0x1400408aa  mov     [rsp+570h+peUse], rax
0x1400408af  lea     r8, aNameSSSidS; "Name: %s\\%s, SID:%s"
0x1400408b6  lea     rax, [rbp+470h+Name]
0x1400408ba  mov     edx, 400h; unsigned __int64
0x1400408bf  mov     rcx, rbx; unsigned __int16 *
0x1400408c2  mov     [rsp+570h+ReturnLength], rax
0x1400408c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400408cc  mov     rcx, [rsp+570h+StringSid]; hMem
0x1400408d1  call    cs:__imp_LocalFree
0x1400408d7  mov     rcx, [rbp+470h+var_20]
0x1400408de  xor     rcx, rsp; StackCookie
0x1400408e1  call    __security_check_cookie
0x1400408e6  lea     r11, [rsp+570h+var_s0]
0x1400408ee  mov     rbx, [r11+10h]
0x1400408f2  movaps  xmm6, xmmword ptr [r11-10h]
0x1400408f7  mov     rsp, r11
0x1400408fa  pop     rbp
0x1400408fb  retn
```
