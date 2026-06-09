# GetCurrentSidString(ushort *,ulong)

- ea: `0x180046270`
- end: `0x180046405`
- name: `?GetCurrentSidString@@YAJPEAGK@Z`
- size: `405`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180046a40`

## callees

- `0x180002584`
- `0x180046270`
- `0x180046410`
- `0x18004bfdd`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800462fc`
- `KERNEL32!CloseHandle` at `0x1800463bb`
- `KERNEL32!CloseHandle` at `0x1800463cb`
- `KERNEL32!CloseHandle` at `0x1800462fc`
- `KERNEL32!CloseHandle` at `0x1800463bb`
- `KERNEL32!CloseHandle` at `0x1800463cb`
- `KERNEL32!GetCurrentProcess` at `0x1800462b2`
- `KERNEL32!GetCurrentProcess` at `0x18004630e`
- `KERNEL32!GetCurrentProcess` at `0x1800462b2`
- `KERNEL32!GetCurrentProcess` at `0x18004630e`
- `KERNEL32!LocalFree` at `0x1800463db`
- `KERNEL32!LocalFree` at `0x1800463db`
- `ADVAPI32!SetThreadToken` at `0x1800462ef`
- `ADVAPI32!SetThreadToken` at `0x1800463a9`
- `ADVAPI32!SetThreadToken` at `0x1800462ef`
- `ADVAPI32!SetThreadToken` at `0x1800463a9`
- `ADVAPI32!OpenProcessToken` at `0x1800462c5`
- `ADVAPI32!OpenProcessToken` at `0x180046321`
- `ADVAPI32!OpenProcessToken` at `0x1800462c5`
- `ADVAPI32!OpenProcessToken` at `0x180046321`
- `ADVAPI32!GetTokenInformation` at `0x180046364`
- `ADVAPI32!GetTokenInformation` at `0x180046364`

## pseudocode

```c
__int64 __fastcall GetCurrentSidString(unsigned __int16 *a1, unsigned int a2)
{
  void *CurrentToken; // rdi
  unsigned __int64 v4; // rsi
  HANDLE CurrentProcess; // rax
  unsigned int LastWin32Error; // ebx
  HANDLE v7; // rax
  unsigned int v8; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  PSID TokenInformation[256]; // [rsp+50h] [rbp-B0h] BYREF

  TokenHandle = 0;
  CurrentToken = 0;
  StringSid = 0;
  v4 = a2;
  TokenInformationLength = 2048;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    goto LABEL_8;
  GetLastWin32Error();
  CurrentToken = GetCurrentToken();
  if ( !CurrentToken )
  {
    LastWin32Error = -2147024891;
    goto LABEL_17;
  }
  if ( !SetThreadToken(0, 0) )
  {
    CloseHandle(CurrentToken);
    LastWin32Error = GetLastWin32Error();
    goto LABEL_17;
  }
  v7 = GetCurrentProcess();
  if ( OpenProcessToken(v7, 0x20008u, &TokenHandle) )
  {
LABEL_8:
    memset_0(TokenInformation, 0, sizeof(TokenInformation));
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength)
      && ConvertSidToStringSidW_0(TokenInformation[0], &StringSid)
      && StringSid )
    {
      v8 = StringCchCopyW(a1, v4, StringSid);
    }
    else
    {
      v8 = GetLastWin32Error();
    }
    LastWin32Error = v8;
    if ( !CurrentToken )
      goto LABEL_17;
  }
  else
  {
    LastWin32Error = GetLastWin32Error();
  }
  if ( !SetThreadToken(0, CurrentToken) )
    GetLastWin32Error();
  CloseHandle(CurrentToken);
LABEL_17:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( StringSid )
    LocalFree(StringSid);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180046270  mov     [rsp-8+arg_10], rbx
0x180046275  push    rbp
0x180046276  push    rsi
0x180046277  push    rdi
0x180046278  lea     rbp, [rsp-760h]
0x180046280  sub     rsp, 860h
0x180046287  mov     rax, cs:__security_cookie
0x18004628e  xor     rax, rsp
0x180046291  mov     [rbp+770h+var_20], rax
0x180046298  and     [rsp+870h+TokenHandle], 0
0x18004629e  xor     edi, edi
0x1800462a0  and     [rsp+870h+StringSid], rdi
0x1800462a5  mov     rbx, rcx
0x1800462a8  mov     esi, edx
0x1800462aa  mov     [rsp+870h+TokenInformationLength], 800h
0x1800462b2  call    cs:__imp_GetCurrentProcess
0x1800462b8  lea     r8, [rsp+870h+TokenHandle]; TokenHandle
0x1800462bd  mov     edx, 20008h; DesiredAccess
0x1800462c2  mov     rcx, rax; ProcessHandle
0x1800462c5  call    cs:__imp_OpenProcessToken
0x1800462cb  test    eax, eax
0x1800462cd  jnz     short loc_180046334
0x1800462cf  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800462d4  call    ?GetCurrentToken@@YAPEAXXZ; GetCurrentToken(void)
0x1800462d9  mov     rdi, rax
0x1800462dc  test    rax, rax
0x1800462df  jnz     short loc_1800462EB
0x1800462e1  mov     ebx, 80070005h
0x1800462e6  jmp     loc_1800463C1
0x1800462eb  xor     edx, edx; Token
0x1800462ed  xor     ecx, ecx; Thread
0x1800462ef  call    cs:__imp_SetThreadToken
0x1800462f5  test    eax, eax
0x1800462f7  jnz     short loc_18004630E
0x1800462f9  mov     rcx, rdi; hObject
0x1800462fc  call    cs:__imp_CloseHandle
0x180046302  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180046307  mov     ebx, eax
0x180046309  jmp     loc_1800463C1
0x18004630e  call    cs:__imp_GetCurrentProcess
0x180046314  lea     r8, [rsp+870h+TokenHandle]; TokenHandle
0x180046319  mov     edx, 20008h; DesiredAccess
0x18004631e  mov     rcx, rax; ProcessHandle
0x180046321  call    cs:__imp_OpenProcessToken
0x180046327  test    eax, eax
0x180046329  jnz     short loc_180046334
0x18004632b  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180046330  mov     ebx, eax
0x180046332  jmp     short loc_1800463A4
0x180046334  xor     edx, edx; Val
0x180046336  lea     rcx, [rsp+870h+TokenInformation]; void *
0x18004633b  mov     r8d, 800h; Size
0x180046341  call    memset_0
0x180046346  mov     r9d, [rsp+870h+TokenInformationLength]; TokenInformationLength
0x18004634b  lea     rax, [rsp+870h+TokenInformationLength]
0x180046350  mov     rcx, [rsp+870h+TokenHandle]; TokenHandle
0x180046355  lea     r8, [rsp+870h+TokenInformation]; TokenInformation
0x18004635a  mov     edx, 1; TokenInformationClass
0x18004635f  mov     [rsp+870h+ReturnLength], rax; ReturnLength
0x180046364  call    cs:__imp_GetTokenInformation
0x18004636a  test    eax, eax
0x18004636c  jz      short loc_180046398
0x18004636e  mov     rcx, [rsp+870h+TokenInformation]; Sid
0x180046373  lea     rdx, [rsp+870h+StringSid]; StringSid
0x180046378  call    ConvertSidToStringSidW_0
0x18004637d  test    eax, eax
0x18004637f  jz      short loc_180046398
0x180046381  mov     r8, [rsp+870h+StringSid]; unsigned __int16 *
0x180046386  test    r8, r8
0x180046389  jz      short loc_180046398
0x18004638b  mov     rdx, rsi; unsigned __int64
0x18004638e  mov     rcx, rbx; unsigned __int16 *
0x180046391  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180046396  jmp     short loc_18004639D
0x180046398  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18004639d  mov     ebx, eax
0x18004639f  test    rdi, rdi
0x1800463a2  jz      short loc_1800463C1
0x1800463a4  mov     rdx, rdi; Token
0x1800463a7  xor     ecx, ecx; Thread
0x1800463a9  call    cs:__imp_SetThreadToken
0x1800463af  test    eax, eax
0x1800463b1  jnz     short loc_1800463B8
0x1800463b3  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800463b8  mov     rcx, rdi; hObject
0x1800463bb  call    cs:__imp_CloseHandle
0x1800463c1  mov     rcx, [rsp+870h+TokenHandle]; hObject
0x1800463c6  test    rcx, rcx
0x1800463c9  jz      short loc_1800463D1
0x1800463cb  call    cs:__imp_CloseHandle
0x1800463d1  mov     rcx, [rsp+870h+StringSid]; hMem
0x1800463d6  test    rcx, rcx
0x1800463d9  jz      short loc_1800463E1
0x1800463db  call    cs:__imp_LocalFree
0x1800463e1  mov     eax, ebx
0x1800463e3  mov     rcx, [rbp+770h+var_20]
0x1800463ea  xor     rcx, rsp; StackCookie
0x1800463ed  call    __security_check_cookie
0x1800463f2  mov     rbx, [rsp+870h+arg_10]
0x1800463fa  add     rsp, 860h
0x180046401  pop     rdi
0x180046402  pop     rsi
0x180046403  pop     rbp
0x180046404  retn
```
