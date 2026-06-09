# CThreadSecurityToken::Initialize(void)

- ea: `0x38388c350`
- end: `0x38388c3e0`
- name: `?Initialize@CThreadSecurityToken@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3838826e0`
- `0x38388b730`
- `0x3839d42a0`

## callees

- `0x38388c350`
- `0x38391ac10`
- `0x38391aed0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x38388c37c`
- `KERNEL32!GetLastError` at `0x3838d74c4`
- `KERNEL32!GetLastError` at `0x3838d7500`
- `KERNEL32!GetLastError` at `0x38388c37c`
- `KERNEL32!GetLastError` at `0x3838d74c4`
- `KERNEL32!GetLastError` at `0x3838d7500`
- `KERNEL32!GetCurrentProcess` at `0x38388c3a8`
- `KERNEL32!GetCurrentProcess` at `0x38388c3a8`
- `KERNEL32!GetCurrentThread` at `0x38388c359`
- `KERNEL32!GetCurrentThread` at `0x3838d7463`
- `KERNEL32!GetCurrentThread` at `0x38388c359`
- `KERNEL32!GetCurrentThread` at `0x3838d7463`
- `ADVAPI32!OpenThreadToken` at `0x38388c36e`
- `ADVAPI32!OpenThreadToken` at `0x3838d7476`
- `ADVAPI32!OpenThreadToken` at `0x38388c36e`
- `ADVAPI32!OpenThreadToken` at `0x3838d7476`
- `ADVAPI32!OpenProcessToken` at `0x38388c3b9`
- `ADVAPI32!OpenProcessToken` at `0x38388c3b9`

## pseudocode

```c
__int64 __fastcall CThreadSecurityToken::Initialize(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v4; // r9
  HANDLE CurrentProcess; // rax
  HANDLE v7; // rax
  DWORD v8; // eax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, TokenHandle) )
  {
    if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Initialize'::`66'::_bidPtrSA_030_3175[0] || bidID == -1 )
      return 0;
LABEL_29:
    off_383B15040();
    return 0;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 5 )
    goto LABEL_3;
  v7 = GetCurrentThread();
  if ( OpenThreadToken(v7, 0xEu, 0, TokenHandle) )
  {
    if ( (bidGblFlags & 2) == 0 || !`CThreadSecurityToken::Initialize'::`16'::_bidPtrSA_030_3137[0] || bidID == -1 )
      return 0;
    goto LABEL_29;
  }
  v4 = GetLastError();
LABEL_3:
  if ( (_DWORD)v4 != 1008 )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`57'::_bidPtrSA_030_3168[0] )
    {
      bidTraceW(
        `CThreadSecurityToken::Initialize'::`57'::_bidSrcFileA[0],
        3244032,
        `CThreadSecurityToken::Initialize'::`57'::_bidPtrSA_030_3168[0],
        v4);
      return 2147500037LL;
    }
    return 2147500037LL;
  }
  if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`31'::_bidPtrSA_030_3149[0] )
    bidTraceW(
      `CThreadSecurityToken::Initialize'::`31'::_bidSrcFileA[0],
      3224576,
      `CThreadSecurityToken::Initialize'::`31'::_bidPtrSA_030_3149[0],
      v4);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xEu, TokenHandle) )
  {
    v8 = GetLastError();
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`41'::_bidPtrSA_030_3158[0] )
      bidTraceW(
        `CThreadSecurityToken::Initialize'::`41'::_bidSrcFileA[0],
        3233792,
        `CThreadSecurityToken::Initialize'::`41'::_bidPtrSA_030_3158[0],
        v8);
    return 2147500037LL;
  }
  if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::Initialize'::`48'::_bidPtrSA_030_3163[0] && bidID != -1 )
    off_383B15040();
  *((_BYTE *)TokenHandle + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x38388c350  push    rbx
0x38388c352  sub     rsp, 30h
0x38388c356  mov     rbx, rcx
0x38388c359  call    cs:__imp_GetCurrentThread
0x38388c35f  mov     edx, 0Eh; DesiredAccess
0x38388c364  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x38388c368  mov     rcx, rax; ThreadHandle
0x38388c36b  mov     r9, rbx; TokenHandle
0x38388c36e  call    cs:__imp_OpenThreadToken
0x38388c374  test    eax, eax
0x38388c376  jnz     loc_3838D75C7
0x38388c37c  call    cs:__imp_GetLastError
0x38388c382  mov     r9d, eax
0x38388c385  cmp     eax, 5
0x38388c388  jz      loc_3838D7463
0x38388c38e  cmp     r9d, 3F0h
0x38388c395  jnz     loc_3838D758F
0x38388c39b  test    byte ptr cs:_bidGblFlags, 2
0x38388c3a2  jnz     loc_3838D74D2
0x38388c3a8  call    cs:__imp_GetCurrentProcess
0x38388c3ae  mov     r8, rbx; TokenHandle
0x38388c3b1  mov     edx, 0Eh; DesiredAccess
0x38388c3b6  mov     rcx, rax; ProcessHandle
0x38388c3b9  call    cs:__imp_OpenProcessToken
0x38388c3bf  test    eax, eax
0x38388c3c1  jz      loc_3838D7500
0x38388c3c7  test    byte ptr cs:_bidGblFlags, 2
0x38388c3ce  jnz     loc_3838D7541
0x38388c3d4  mov     byte ptr [rbx+8], 1
0x38388c3d8  xor     eax, eax
0x38388c3da  add     rsp, 30h
0x38388c3de  pop     rbx
0x38388c3df  retn
0x3838d7463  call    cs:__imp_GetCurrentThread
0x3838d7469  xor     r8d, r8d; OpenAsSelf
0x3838d746c  mov     r9, rbx; TokenHandle
0x3838d746f  lea     edx, [r8+0Eh]; DesiredAccess
0x3838d7473  mov     rcx, rax; ThreadHandle
0x3838d7476  call    cs:__imp_OpenThreadToken
0x3838d747c  test    eax, eax
0x3838d747e  jz      short loc_3838D74C4
0x3838d7480  test    byte ptr cs:_bidGblFlags, 2
0x3838d7487  jz      loc_3838D7610
0x3838d748d  mov     rax, cs:?_bidPtrSA_030_3137@?BA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`16'::_bidPtrSA_030_3137
0x3838d7494  test    rax, rax
0x3838d7497  jz      loc_3838D7610
0x3838d749d  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3838d74a5  jz      loc_3838D7610
0x3838d74ab  mov     r9, cs:?_bidPtrSA_030_3137@?BA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`16'::_bidPtrSA_030_3137
0x3838d74b2  mov     rdx, cs:?_bidSrcFileA@?BA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`16'::_bidSrcFileA
0x3838d74b9  mov     r8d, 310400h
0x3838d74bf  jmp     loc_3838D75FA
0x3838d74c4  call    cs:__imp_GetLastError
0x3838d74ca  mov     r9d, eax
0x3838d74cd  jmp     loc_38388C38E
0x3838d74d2  mov     rax, cs:?_bidPtrSA_030_3149@?BP@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`31'::_bidPtrSA_030_3149
0x3838d74d9  test    rax, rax
0x3838d74dc  jz      loc_38388C3A8
0x3838d74e2  mov     r8, cs:?_bidPtrSA_030_3149@?BP@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`31'::_bidPtrSA_030_3149
0x3838d74e9  mov     rcx, cs:?_bidSrcFileA@?BP@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`31'::_bidSrcFileA
0x3838d74f0  mov     edx, 313400h
0x3838d74f5  call    _bidTraceW
0x3838d74fa  nop
0x3838d74fb  jmp     loc_38388C3A8
0x3838d7500  call    cs:__imp_GetLastError
0x3838d7506  test    byte ptr cs:_bidGblFlags, 2
0x3838d750d  jz      short loc_3838D7536
0x3838d750f  mov     rcx, cs:?_bidPtrSA_030_3158@?CJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`41'::_bidPtrSA_030_3158
0x3838d7516  test    rcx, rcx
0x3838d7519  jz      short loc_3838D7536
0x3838d751b  mov     r8, cs:?_bidPtrSA_030_3158@?CJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`41'::_bidPtrSA_030_3158
0x3838d7522  mov     rcx, cs:?_bidSrcFileA@?CJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`41'::_bidSrcFileA
0x3838d7529  mov     r9d, eax
0x3838d752c  mov     edx, 315800h
0x3838d7531  call    _bidTraceW
0x3838d7536  mov     eax, 80004005h
0x3838d753b  add     rsp, 30h
0x3838d753f  pop     rbx
0x3838d7540  retn
0x3838d7541  mov     rax, cs:?_bidPtrSA_030_3163@?DA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`48'::_bidPtrSA_030_3163
0x3838d7548  test    rax, rax
0x3838d754b  jz      loc_38388C3D4
0x3838d7551  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3838d7559  jz      loc_38388C3D4
0x3838d755f  mov     r9, cs:?_bidPtrSA_030_3163@?DA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`48'::_bidPtrSA_030_3163
0x3838d7566  mov     rdx, cs:?_bidSrcFileA@?DA@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`48'::_bidSrcFileA
0x3838d756d  mov     rcx, cs:_bidID
0x3838d7574  mov     r8d, 316C00h
0x3838d757a  mov     [rsp+38h+var_18], 0
0x3838d7583  call    cs:off_383B15040
0x3838d7589  nop
0x3838d758a  jmp     loc_38388C3D4
0x3838d758f  test    byte ptr cs:_bidGblFlags, 2
0x3838d7596  jz      short loc_3838D7536
0x3838d7598  mov     rax, cs:?_bidPtrSA_030_3168@?DJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`57'::_bidPtrSA_030_3168
0x3838d759f  test    rax, rax
0x3838d75a2  jz      short loc_3838D7536
0x3838d75a4  mov     r8, cs:?_bidPtrSA_030_3168@?DJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`57'::_bidPtrSA_030_3168
0x3838d75ab  mov     rcx, cs:?_bidSrcFileA@?DJ@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`57'::_bidSrcFileA
0x3838d75b2  mov     edx, 318000h
0x3838d75b7  call    _bidTraceW
0x3838d75bc  mov     eax, 80004005h
0x3838d75c1  add     rsp, 30h
0x3838d75c5  pop     rbx
0x3838d75c6  retn
0x3838d75c7  test    byte ptr cs:_bidGblFlags, 2
0x3838d75ce  jz      short loc_3838D7610
0x3838d75d0  mov     rax, cs:?_bidPtrSA_030_3175@?EC@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`66'::_bidPtrSA_030_3175
0x3838d75d7  test    rax, rax
0x3838d75da  jz      short loc_3838D7610
0x3838d75dc  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3838d75e4  jz      short loc_3838D7610
0x3838d75e6  mov     r9, cs:?_bidPtrSA_030_3175@?EC@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::Initialize(void)'::`66'::_bidPtrSA_030_3175
0x3838d75ed  mov     rdx, cs:?_bidSrcFileA@?EC@??Initialize@CThreadSecurityToken@@QEAAJXZ@4REBDEB; char const * const `CThreadSecurityToken::Initialize(void)'::`66'::_bidSrcFileA
0x3838d75f4  mov     r8d, 319C00h
0x3838d75fa  mov     rcx, cs:_bidID
0x3838d7601  mov     [rsp+38h+var_18], 0
0x3838d760a  call    cs:off_383B15040
0x3838d7610  xor     eax, eax
0x3838d7612  add     rsp, 30h
0x3838d7616  pop     rbx
0x3838d7617  retn
```
