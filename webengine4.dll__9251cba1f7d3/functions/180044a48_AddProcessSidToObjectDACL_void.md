# AddProcessSidToObjectDACL(void *)

- ea: `0x180044a48`
- end: `0x180044bd6`
- name: `?AddProcessSidToObjectDACL@@YAJPEAX@Z`
- size: `398`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180045600`

## callees

- `0x180021ca8`
- `0x180044a48`
- `0x180046410`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180044ae9`
- `KERNEL32!CloseHandle` at `0x180044b9a`
- `KERNEL32!CloseHandle` at `0x180044baa`
- `KERNEL32!CloseHandle` at `0x180044ae9`
- `KERNEL32!CloseHandle` at `0x180044b9a`
- `KERNEL32!CloseHandle` at `0x180044baa`
- `KERNEL32!GetCurrentProcess` at `0x180044a95`
- `KERNEL32!GetCurrentProcess` at `0x180044afb`
- `KERNEL32!GetCurrentProcess` at `0x180044a95`
- `KERNEL32!GetCurrentProcess` at `0x180044afb`
- `ADVAPI32!SetThreadToken` at `0x180044adc`
- `ADVAPI32!SetThreadToken` at `0x180044b88`
- `ADVAPI32!SetThreadToken` at `0x180044adc`
- `ADVAPI32!SetThreadToken` at `0x180044b88`
- `ADVAPI32!OpenProcessToken` at `0x180044aa8`
- `ADVAPI32!OpenProcessToken` at `0x180044b0e`
- `ADVAPI32!OpenProcessToken` at `0x180044aa8`
- `ADVAPI32!OpenProcessToken` at `0x180044b0e`
- `ADVAPI32!GetTokenInformation` at `0x180044b55`
- `ADVAPI32!GetTokenInformation` at `0x180044b55`

## pseudocode

```c
__int64 __fastcall AddProcessSidToObjectDACL(void *a1)
{
  void *CurrentToken; // rdi
  HANDLE CurrentProcess; // rax
  unsigned int LastWin32Error; // ebx
  HANDLE v6; // rax
  unsigned int v7; // eax
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  DWORD TokenInformationLength; // [rsp+34h] [rbp-CCh] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenInformation[256]; // [rsp+40h] [rbp-C0h] BYREF

  if ( !a1 )
    return 2147942487LL;
  TokenHandle = 0;
  CurrentToken = 0;
  TokenInformationLength = 2048;
  CurrentProcess = GetCurrentProcess();
  v8 = OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle);
  if ( v8 )
    goto LABEL_11;
  GetLastWin32Error();
  CurrentToken = GetCurrentToken();
  if ( CurrentToken )
  {
    if ( !SetThreadToken(0, 0) )
    {
      CloseHandle(CurrentToken);
      LastWin32Error = GetLastWin32Error();
      goto LABEL_18;
    }
    v6 = GetCurrentProcess();
    v8 = OpenProcessToken(v6, 0x20008u, &TokenHandle);
    if ( !v8 )
    {
      LastWin32Error = GetLastWin32Error();
      goto LABEL_15;
    }
LABEL_11:
    memset_0(TokenInformation, 0, sizeof(TokenInformation));
    v8 = GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength);
    if ( v8 )
      v7 = CRegAccount::AddSidToToken(a1, TokenInformation[0], &v8);
    else
      v7 = GetLastWin32Error();
    LastWin32Error = v7;
    if ( !CurrentToken )
      goto LABEL_18;
LABEL_15:
    if ( !SetThreadToken(0, CurrentToken) )
      GetLastWin32Error();
    CloseHandle(CurrentToken);
    goto LABEL_18;
  }
  LastWin32Error = -2147024891;
LABEL_18:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180044a48  mov     [rsp-8+arg_8], rbx
0x180044a4d  mov     [rsp-8+arg_10], rdi
0x180044a52  push    rbp
0x180044a53  lea     rbp, [rsp-750h]
0x180044a5b  sub     rsp, 850h
0x180044a62  mov     rax, cs:__security_cookie
0x180044a69  xor     rax, rsp
0x180044a6c  mov     [rbp+750h+var_10], rax
0x180044a73  mov     rbx, rcx
0x180044a76  test    rcx, rcx
0x180044a79  jnz     short loc_180044A85
0x180044a7b  mov     eax, 80070057h
0x180044a80  jmp     loc_180044BB2
0x180044a85  and     [rsp+850h+TokenHandle], 0
0x180044a8b  xor     edi, edi
0x180044a8d  mov     [rsp+850h+TokenInformationLength], 800h
0x180044a95  call    cs:__imp_GetCurrentProcess
0x180044a9b  lea     r8, [rsp+850h+TokenHandle]; TokenHandle
0x180044aa0  mov     edx, 20008h; DesiredAccess
0x180044aa5  mov     rcx, rax; ProcessHandle
0x180044aa8  call    cs:__imp_OpenProcessToken
0x180044aae  mov     [rsp+850h+var_820], eax
0x180044ab2  test    eax, eax
0x180044ab4  jnz     short loc_180044B25
0x180044ab6  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180044abb  cmp     [rsp+850h+var_820], edi
0x180044abf  jnz     short loc_180044B25
0x180044ac1  call    ?GetCurrentToken@@YAPEAXXZ; GetCurrentToken(void)
0x180044ac6  mov     rdi, rax
0x180044ac9  test    rax, rax
0x180044acc  jnz     short loc_180044AD8
0x180044ace  mov     ebx, 80070005h
0x180044ad3  jmp     loc_180044BA0
0x180044ad8  xor     edx, edx; Token
0x180044ada  xor     ecx, ecx; Thread
0x180044adc  call    cs:__imp_SetThreadToken
0x180044ae2  test    eax, eax
0x180044ae4  jnz     short loc_180044AFB
0x180044ae6  mov     rcx, rdi; hObject
0x180044ae9  call    cs:__imp_CloseHandle
0x180044aef  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180044af4  mov     ebx, eax
0x180044af6  jmp     loc_180044BA0
0x180044afb  call    cs:__imp_GetCurrentProcess
0x180044b01  lea     r8, [rsp+850h+TokenHandle]; TokenHandle
0x180044b06  mov     edx, 20008h; DesiredAccess
0x180044b0b  mov     rcx, rax; ProcessHandle
0x180044b0e  call    cs:__imp_OpenProcessToken
0x180044b14  mov     [rsp+850h+var_820], eax
0x180044b18  test    eax, eax
0x180044b1a  jnz     short loc_180044B25
0x180044b1c  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180044b21  mov     ebx, eax
0x180044b23  jmp     short loc_180044B83
0x180044b25  xor     edx, edx; Val
0x180044b27  lea     rcx, [rsp+850h+TokenInformation]; void *
0x180044b2c  mov     r8d, 800h; Size
0x180044b32  call    memset_0
0x180044b37  mov     r9d, [rsp+850h+TokenInformationLength]; TokenInformationLength
0x180044b3c  lea     rax, [rsp+850h+TokenInformationLength]
0x180044b41  mov     rcx, [rsp+850h+TokenHandle]; TokenHandle
0x180044b46  lea     r8, [rsp+850h+TokenInformation]; TokenInformation
0x180044b4b  mov     edx, 1; TokenInformationClass
0x180044b50  mov     [rsp+850h+ReturnLength], rax; ReturnLength
0x180044b55  call    cs:__imp_GetTokenInformation
0x180044b5b  mov     [rsp+850h+var_820], eax
0x180044b5f  test    eax, eax
0x180044b61  jnz     short loc_180044B6A
0x180044b63  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180044b68  jmp     short loc_180044B7C
0x180044b6a  mov     rdx, [rsp+850h+TokenInformation]; void *
0x180044b6f  lea     r8, [rsp+850h+var_820]; int *
0x180044b74  mov     rcx, rbx; void *
0x180044b77  call    ?AddSidToToken@CRegAccount@@SAJPEAX0PEAH@Z; CRegAccount::AddSidToToken(void *,void *,int *)
0x180044b7c  mov     ebx, eax
0x180044b7e  test    rdi, rdi
0x180044b81  jz      short loc_180044BA0
0x180044b83  mov     rdx, rdi; Token
0x180044b86  xor     ecx, ecx; Thread
0x180044b88  call    cs:__imp_SetThreadToken
0x180044b8e  test    eax, eax
0x180044b90  jnz     short loc_180044B97
0x180044b92  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180044b97  mov     rcx, rdi; hObject
0x180044b9a  call    cs:__imp_CloseHandle
0x180044ba0  mov     rcx, [rsp+850h+TokenHandle]; hObject
0x180044ba5  test    rcx, rcx
0x180044ba8  jz      short loc_180044BB0
0x180044baa  call    cs:__imp_CloseHandle
0x180044bb0  mov     eax, ebx
0x180044bb2  mov     rcx, [rbp+750h+var_10]
0x180044bb9  xor     rcx, rsp; StackCookie
0x180044bbc  call    __security_check_cookie
0x180044bc1  lea     r11, [rsp+850h+var_s0]
0x180044bc9  mov     rbx, [r11+18h]
0x180044bcd  mov     rdi, [r11+20h]
0x180044bd1  mov     rsp, r11
0x180044bd4  pop     rbp
0x180044bd5  retn
```
