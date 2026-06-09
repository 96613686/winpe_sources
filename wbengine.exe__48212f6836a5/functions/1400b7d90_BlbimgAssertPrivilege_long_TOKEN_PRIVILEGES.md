# BlbimgAssertPrivilege(long,_TOKEN_PRIVILEGES *)

- ea: `0x1400b7d90`
- end: `0x1400b7f43`
- name: `?BlbimgAssertPrivilege@@YAHJPEAU_TOKEN_PRIVILEGES@@@Z`
- size: `435`
- prototype: `int(int, struct _TOKEN_PRIVILEGES *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b04c4`
- `0x1400b1258`
- `0x1400bf574`
- `0x1400bf788`
- `0x1400c1f5c`

## callees

- `0x14000bb24`
- `0x1400b7d90`
- `0x140134d20`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x1400b7e72`
- `ADVAPI32!DuplicateTokenEx` at `0x1400b7e72`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1400b7eec`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1400b7eec`
- `ADVAPI32!OpenProcessToken` at `0x1400b7e46`
- `ADVAPI32!OpenProcessToken` at `0x1400b7e46`
- `ADVAPI32!OpenThreadToken` at `0x1400b7e19`
- `ADVAPI32!OpenThreadToken` at `0x1400b7e19`
- `ADVAPI32!SetThreadToken` at `0x1400b7e93`
- `ADVAPI32!SetThreadToken` at `0x1400b7e93`
- `KERNEL32!GetCurrentProcess` at `0x1400b7e34`
- `KERNEL32!GetCurrentProcess` at `0x1400b7e34`
- `KERNEL32!GetCurrentThread` at `0x1400b7e03`
- `KERNEL32!GetCurrentThread` at `0x1400b7e03`
- `KERNEL32!CloseHandle` at `0x1400b7e80`
- `KERNEL32!CloseHandle` at `0x1400b7ea1`
- `KERNEL32!CloseHandle` at `0x1400b7ead`
- `KERNEL32!CloseHandle` at `0x1400b7ef8`
- `KERNEL32!CloseHandle` at `0x1400b7e80`
- `KERNEL32!CloseHandle` at `0x1400b7ea1`
- `KERNEL32!CloseHandle` at `0x1400b7ead`
- `KERNEL32!CloseHandle` at `0x1400b7ef8`
- `KERNEL32!GetLastError` at `0x1400b7e27`
- `KERNEL32!GetLastError` at `0x1400b7e27`

## pseudocode

```c
__int64 __fastcall BlbimgAssertPrivilege(int a1, struct _TOKEN_PRIVILEGES *a2)
{
  LUID v2; // rbx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  HANDLE v6; // rcx
  unsigned int v8; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  HANDLE hExistingToken; // [rsp+38h] [rbp-30h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-20h] BYREF

  v2 = (LUID)a1;
  NewState = 0;
  TokenHandle = 0;
  hExistingToken = 0;
  ReturnLength = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 2u, &hExistingToken) )
      return 0;
    if ( !DuplicateTokenEx(hExistingToken, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
    {
      v6 = hExistingToken;
LABEL_10:
      CloseHandle(v6);
      return 0;
    }
    if ( !SetThreadToken(0, TokenHandle) )
    {
      CloseHandle(hExistingToken);
      v6 = TokenHandle;
      goto LABEL_10;
    }
    CloseHandle(hExistingToken);
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = v2;
  NewState.Privileges[0].Attributes = 2;
  v8 = AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, a2, &ReturnLength);
  CloseHandle(TokenHandle);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
  }
  return v8;
}

```

## disassembly

```asm
0x1400b7d90  push    rbp
0x1400b7d92  push    rbx
0x1400b7d93  push    rdi
0x1400b7d94  push    r12
0x1400b7d96  mov     rbp, rsp
0x1400b7d99  sub     rsp, 68h
0x1400b7d9d  mov     rax, cs:__security_cookie
0x1400b7da4  xor     rax, rsp
0x1400b7da7  mov     [rbp+var_10], rax
0x1400b7dab  xorps   xmm0, xmm0
0x1400b7dae  movsxd  rbx, ecx
0x1400b7db1  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1400b7db5  mov     rdi, rdx
0x1400b7db8  mov     [rbp+TokenHandle], 0
0x1400b7dc0  mov     [rbp+hExistingToken], 0
0x1400b7dc8  mov     [rbp+ReturnLength], 0
0x1400b7dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7dd6  lea     r12, WPP_GLOBAL_Control
0x1400b7ddd  cmp     rcx, r12
0x1400b7de0  jz      short loc_1400B7E03
0x1400b7de2  test    byte ptr [rcx+1Ch], 4
0x1400b7de6  jz      short loc_1400B7E03
0x1400b7de8  cmp     byte ptr [rcx+19h], 4
0x1400b7dec  jb      short loc_1400B7E03
0x1400b7dee  mov     rcx, [rcx+10h]
0x1400b7df2  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400b7df9  mov     edx, 0Ah
0x1400b7dfe  call    WPP_SF_
0x1400b7e03  call    cs:__imp_GetCurrentThread
0x1400b7e09  mov     edx, 28h ; '('; DesiredAccess
0x1400b7e0e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1400b7e12  mov     rcx, rax; ThreadHandle
0x1400b7e15  lea     r8d, [rdx-27h]; OpenAsSelf
0x1400b7e19  call    cs:__imp_OpenThreadToken
0x1400b7e1f  test    eax, eax
0x1400b7e21  jnz     loc_1400B7EB3
0x1400b7e27  call    cs:__imp_GetLastError
0x1400b7e2d  cmp     eax, 3F0h
0x1400b7e32  jnz     short loc_1400B7E86
0x1400b7e34  call    cs:__imp_GetCurrentProcess
0x1400b7e3a  lea     r8, [rbp+hExistingToken]; TokenHandle
0x1400b7e3e  mov     edx, 2; DesiredAccess
0x1400b7e43  mov     rcx, rax; ProcessHandle
0x1400b7e46  call    cs:__imp_OpenProcessToken
0x1400b7e4c  test    eax, eax
0x1400b7e4e  jz      short loc_1400B7E86
0x1400b7e50  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x1400b7e54  lea     rax, [rbp+TokenHandle]
0x1400b7e58  mov     r9d, 2; ImpersonationLevel
0x1400b7e5e  mov     [rsp+68h+phNewToken], rax; phNewToken
0x1400b7e63  xor     r8d, r8d; lpTokenAttributes
0x1400b7e66  mov     [rsp+68h+TokenType], 2; TokenType
0x1400b7e6e  lea     edx, [r9+2Ah]; dwDesiredAccess
0x1400b7e72  call    cs:__imp_DuplicateTokenEx
0x1400b7e78  test    eax, eax
0x1400b7e7a  jnz     short loc_1400B7E8D
0x1400b7e7c  mov     rcx, [rbp+hExistingToken]; hObject
0x1400b7e80  call    cs:__imp_CloseHandle
0x1400b7e86  xor     eax, eax
0x1400b7e88  jmp     loc_1400B7F2D
0x1400b7e8d  mov     rdx, [rbp+TokenHandle]; Token
0x1400b7e91  xor     ecx, ecx; Thread
0x1400b7e93  call    cs:__imp_SetThreadToken
0x1400b7e99  mov     rcx, [rbp+hExistingToken]; hObject
0x1400b7e9d  test    eax, eax
0x1400b7e9f  jnz     short loc_1400B7EAD
0x1400b7ea1  call    cs:__imp_CloseHandle
0x1400b7ea7  mov     rcx, [rbp+TokenHandle]
0x1400b7eab  jmp     short loc_1400B7E80
0x1400b7ead  call    cs:__imp_CloseHandle
0x1400b7eb3  lea     rax, [rbp+ReturnLength]
0x1400b7eb7  mov     [rbp+NewState.PrivilegeCount], 1
0x1400b7ebe  mov     [rsp+68h+phNewToken], rax; ReturnLength
0x1400b7ec3  lea     r8, [rbp+NewState]; NewState
0x1400b7ec7  mov     rcx, rbx
0x1400b7eca  mov     [rbp+NewState.Privileges.Luid.LowPart], ebx
0x1400b7ecd  shr     rcx, 20h
0x1400b7ed1  mov     r9d, 10h; BufferLength
0x1400b7ed7  mov     [rbp+NewState.Privileges.Luid.HighPart], ecx
0x1400b7eda  xor     edx, edx; DisableAllPrivileges
0x1400b7edc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400b7ee0  mov     [rbp+NewState.Privileges.Attributes], 2
0x1400b7ee7  mov     qword ptr [rsp+68h+TokenType], rdi; PreviousState
0x1400b7eec  call    cs:__imp_AdjustTokenPrivileges
0x1400b7ef2  mov     rcx, [rbp+TokenHandle]; hObject
0x1400b7ef6  mov     ebx, eax
0x1400b7ef8  call    cs:__imp_CloseHandle
0x1400b7efe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7f05  cmp     rcx, r12
0x1400b7f08  jz      short loc_1400B7F2B
0x1400b7f0a  test    byte ptr [rcx+1Ch], 4
0x1400b7f0e  jz      short loc_1400B7F2B
0x1400b7f10  cmp     byte ptr [rcx+19h], 4
0x1400b7f14  jb      short loc_1400B7F2B
0x1400b7f16  mov     rcx, [rcx+10h]
0x1400b7f1a  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400b7f21  mov     edx, 0Bh
0x1400b7f26  call    WPP_SF_
0x1400b7f2b  mov     eax, ebx
0x1400b7f2d  mov     rcx, [rbp+var_10]
0x1400b7f31  xor     rcx, rsp; StackCookie
0x1400b7f34  call    __security_check_cookie
0x1400b7f39  add     rsp, 68h
0x1400b7f3d  pop     r12
0x1400b7f3f  pop     rdi
0x1400b7f40  pop     rbx
0x1400b7f41  pop     rbp
0x1400b7f42  retn
```
