# GetDomainAndUserNames

- ea: `0x18003144c`
- end: `0x18003164a`
- name: `GetDomainAndUserNames`
- size: `510`
- prototype: `__int64 __fastcall(wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800326c0`

## callees

- `0x18002c8d4`
- `0x18003144c`
- `0x18003dc84`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800314ec`
- `KERNEL32!HeapAlloc` at `0x18003155a`
- `KERNEL32!HeapAlloc` at `0x180031581`
- `KERNEL32!HeapAlloc` at `0x1800314ec`
- `KERNEL32!HeapAlloc` at `0x18003155a`
- `KERNEL32!HeapAlloc` at `0x180031581`
- `KERNEL32!GetCurrentProcess` at `0x180031494`
- `KERNEL32!GetCurrentProcess` at `0x180031494`
- `KERNEL32!CloseHandle` at `0x1800314fe`
- `KERNEL32!CloseHandle` at `0x180031629`
- `KERNEL32!CloseHandle` at `0x1800314fe`
- `KERNEL32!CloseHandle` at `0x180031629`
- `KERNEL32!GetLastError` at `0x1800314b0`
- `KERNEL32!GetLastError` at `0x18003152c`
- `KERNEL32!GetLastError` at `0x1800315d1`
- `KERNEL32!GetLastError` at `0x1800314b0`
- `KERNEL32!GetLastError` at `0x18003152c`
- `KERNEL32!GetLastError` at `0x1800315d1`
- `ADVAPI32!LookupAccountSidW` at `0x1800315c7`
- `ADVAPI32!LookupAccountSidW` at `0x1800315c7`
- `ADVAPI32!OpenProcessToken` at `0x1800314a6`
- `ADVAPI32!OpenProcessToken` at `0x1800314a6`
- `ADVAPI32!GetTokenInformation` at `0x180031522`
- `ADVAPI32!GetTokenInformation` at `0x180031522`

## string_xrefs

- `0x180031532`: `GetAccountInfo: GetTokenInformation failed, error=%d`
- `0x1800314b6`: `GetAccountInfo: OpenThreadToken failed, error=%d`
- `0x1800315d7`: `GetAccountInfo: LookupAccountSidW failed, error=%d`

## pseudocode

```c
__int64 __fastcall GetDomainAndUserNames(wchar_t **a1, wchar_t **a2)
{
  unsigned int v4; // ebx
  HANDLE CurrentProcess; // rax
  DWORD v6; // eax
  PSID *v7; // rax
  PSID *v8; // r14
  DWORD LastError; // eax
  wchar_t *v11; // rdi
  wchar_t *v12; // rsi
  DWORD v13; // eax
  DWORD cchName; // [rsp+40h] [rbp-10h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-Ch] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-8h] BYREF
  DWORD ReturnLength; // [rsp+90h] [rbp+40h] BYREF
  DWORD cchReferencedDomainName; // [rsp+98h] [rbp+48h] BYREF

  ReturnLength = 0;
  cchName = 0;
  v4 = -2147483576;
  cchReferencedDomainName = 0;
  TokenHandle = 0;
  peUse = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    ReturnLength = 0;
    v7 = (PSID *)HeapAlloc(ghTapisrvHeap, 8u, 0x3E8u);
    v8 = v7;
    if ( !v7 )
    {
      CloseHandle(TokenHandle);
      return 2147483716LL;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v7, 0x3E8u, &ReturnLength) )
    {
      LastError = GetLastError();
      TRACELogPrint(65538, "GetAccountInfo: GetTokenInformation failed, error=%d", LastError);
LABEL_16:
      CloseHandle(TokenHandle);
      return v4;
    }
    v11 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, 0xC8u);
    if ( v11 )
    {
      v12 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, 0xC8u);
      if ( v12 )
      {
        cchReferencedDomainName = 200;
        cchName = 200;
        if ( LookupAccountSidW(0, *v8, v11, &cchName, v12, &cchReferencedDomainName, &peUse) )
        {
          TRACELogPrint(262146, "GetAccountInfo: User name %ls Domain name %ls", v11, v12);
          v4 = 0;
          *a1 = v12;
          *a2 = v11;
          goto LABEL_15;
        }
        v13 = GetLastError();
        TRACELogPrint(65538, "GetAccountInfo: LookupAccountSidW failed, error=%d", v13);
        ServerFree(v12);
      }
      else
      {
        v4 = -2147483580;
      }
      ServerFree(v11);
    }
    else
    {
      v4 = -2147483580;
    }
LABEL_15:
    ServerFree(v8);
    goto LABEL_16;
  }
  v6 = GetLastError();
  TRACELogPrint(65538, "GetAccountInfo: OpenThreadToken failed, error=%d", v6);
  return v4;
}

```

## disassembly

```asm
0x18003144c  mov     [rsp-28h+arg_0], rbx
0x180031451  mov     [rsp-28h+arg_8], rsi
0x180031456  push    rbp
0x180031457  push    rdi
0x180031458  push    r12
0x18003145a  push    r14
0x18003145c  push    r15
0x18003145e  mov     rbp, rsp
0x180031461  sub     rsp, 50h
0x180031465  mov     r15, rdx
0x180031468  mov     [rbp+arg_10], 0
0x18003146f  mov     r12, rcx
0x180031472  mov     [rbp+cchName], 0
0x180031479  mov     ebx, 80000048h
0x18003147e  mov     [rbp+arg_18], 0
0x180031485  mov     [rbp+TokenHandle], 0
0x18003148d  mov     [rbp+var_C], 0
0x180031494  call    cs:__imp_GetCurrentProcess
0x18003149a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003149e  mov     edx, 20008h; DesiredAccess
0x1800314a3  mov     rcx, rax; ProcessHandle
0x1800314a6  call    cs:__imp_OpenProcessToken
0x1800314ac  test    eax, eax
0x1800314ae  jnz     short loc_1800314CF
0x1800314b0  call    cs:__imp_GetLastError
0x1800314b6  lea     rdx, aGetaccountinfo_1; "GetAccountInfo: OpenThreadToken failed,"...
0x1800314bd  mov     ecx, 10002h
0x1800314c2  mov     r8d, eax
0x1800314c5  call    TRACELogPrint
0x1800314ca  jmp     loc_18003162F
0x1800314cf  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800314d6  mov     edi, 3E8h
0x1800314db  mov     esi, 8
0x1800314e0  mov     [rbp+arg_10], 0
0x1800314e7  mov     r8d, edi; dwBytes
0x1800314ea  mov     edx, esi; dwFlags
0x1800314ec  call    cs:__imp_HeapAlloc
0x1800314f2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800314f6  mov     r14, rax
0x1800314f9  test    rax, rax
0x1800314fc  jnz     short loc_18003150E
0x1800314fe  call    cs:__imp_CloseHandle
0x180031504  mov     eax, 80000044h
0x180031509  jmp     loc_180031631
0x18003150e  lea     rax, [rbp+arg_10]
0x180031512  mov     r9d, edi; TokenInformationLength
0x180031515  mov     r8, r14; TokenInformation
0x180031518  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18003151d  mov     edx, 1; TokenInformationClass
0x180031522  call    cs:__imp_GetTokenInformation
0x180031528  test    eax, eax
0x18003152a  jnz     short loc_18003154B
0x18003152c  call    cs:__imp_GetLastError
0x180031532  lea     rdx, aGetaccountinfo; "GetAccountInfo: GetTokenInformation fai"...
0x180031539  mov     ecx, 10002h
0x18003153e  mov     r8d, eax
0x180031541  call    TRACELogPrint
0x180031546  jmp     loc_180031625
0x18003154b  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180031552  mov     r8d, 0C8h; dwBytes
0x180031558  mov     edx, esi; dwFlags
0x18003155a  call    cs:__imp_HeapAlloc
0x180031560  mov     rdi, rax
0x180031563  test    rax, rax
0x180031566  jnz     short loc_180031572
0x180031568  mov     ebx, 80000044h
0x18003156d  jmp     loc_18003161D
0x180031572  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180031579  mov     r8d, 0C8h; dwBytes
0x18003157f  mov     edx, esi; dwFlags
0x180031581  call    cs:__imp_HeapAlloc
0x180031587  mov     rsi, rax
0x18003158a  test    rax, rax
0x18003158d  jnz     short loc_180031596
0x18003158f  mov     ebx, 80000044h
0x180031594  jmp     short loc_1800315F3
0x180031596  lea     rax, [rbp+var_C]
0x18003159a  mov     [rbp+arg_18], 0C8h
0x1800315a1  mov     [rsp+50h+peUse], rax; peUse
0x1800315a6  lea     r9, [rbp+cchName]; cchName
0x1800315aa  lea     rax, [rbp+arg_18]
0x1800315ae  mov     [rbp+cchName], 0C8h
0x1800315b5  mov     rdx, [r14]; Sid
0x1800315b8  mov     r8, rdi; Name
0x1800315bb  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800315c0  xor     ecx, ecx; lpSystemName
0x1800315c2  mov     [rsp+50h+ReturnLength], rsi; ReferencedDomainName
0x1800315c7  call    cs:__imp_LookupAccountSidW
0x1800315cd  test    eax, eax
0x1800315cf  jnz     short loc_1800315FD
0x1800315d1  call    cs:__imp_GetLastError
0x1800315d7  lea     rdx, aGetaccountinfo_0; "GetAccountInfo: LookupAccountSidW faile"...
0x1800315de  mov     ecx, 10002h
0x1800315e3  mov     r8d, eax
0x1800315e6  call    TRACELogPrint
0x1800315eb  mov     rcx, rsi; lpMem
0x1800315ee  call    ServerFree
0x1800315f3  mov     rcx, rdi; lpMem
0x1800315f6  call    ServerFree
0x1800315fb  jmp     short loc_18003161D
0x1800315fd  mov     r9, rsi
0x180031600  lea     rdx, aGetaccountinfo_2; "GetAccountInfo: User name %ls Domain na"...
0x180031607  mov     r8, rdi
0x18003160a  mov     ecx, 40002h
0x18003160f  call    TRACELogPrint
0x180031614  xor     ebx, ebx
0x180031616  mov     [r12], rsi
0x18003161a  mov     [r15], rdi
0x18003161d  mov     rcx, r14; lpMem
0x180031620  call    ServerFree
0x180031625  mov     rcx, [rbp+TokenHandle]; hObject
0x180031629  call    cs:__imp_CloseHandle
0x18003162f  mov     eax, ebx
0x180031631  lea     r11, [rsp+50h+var_s0]
0x180031636  mov     rbx, [r11+30h]
0x18003163a  mov     rsi, [r11+38h]
0x18003163e  mov     rsp, r11
0x180031641  pop     r15
0x180031643  pop     r14
0x180031645  pop     r12
0x180031647  pop     rdi
0x180031648  pop     rbp
0x180031649  retn
```
