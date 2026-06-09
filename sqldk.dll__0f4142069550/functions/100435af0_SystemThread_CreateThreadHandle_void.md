# SystemThread::CreateThreadHandle(void)

- ea: `0x100435af0`
- end: `0x100435bfe`
- name: `?CreateThreadHandle@SystemThread@@AEAAXXZ`
- size: `270`
- prototype: `void __fastcall(SystemThread *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1004267a0`
- `0x100426a00`
- `0x10042b6f0`
- `0x1004359c0`
- `0x100490e60`
- `0x1004b7110`
- `0x1005599c0`

## callees

- `0x100435af0`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x100435b32`
- `KERNEL32!GetCurrentThread` at `0x100435b32`
- `KERNEL32!OpenThread` at `0x100435b16`
- `KERNEL32!OpenThread` at `0x100435b16`
- `KERNEL32!DuplicateHandle` at `0x100435ba8`
- `KERNEL32!DuplicateHandle` at `0x100435ba8`
- `KERNEL32!CloseHandle` at `0x100435be9`
- `KERNEL32!CloseHandle` at `0x10048f378`
- `KERNEL32!CloseHandle` at `0x10048f3d3`
- `KERNEL32!CloseHandle` at `0x100435be9`
- `KERNEL32!CloseHandle` at `0x10048f378`
- `KERNEL32!CloseHandle` at `0x10048f3d3`
- `KERNEL32!GetLastError` at `0x100435b5b`
- `KERNEL32!GetLastError` at `0x10048f39a`
- `KERNEL32!GetLastError` at `0x100435b5b`
- `KERNEL32!GetLastError` at `0x10048f39a`
- `KERNEL32!GetCurrentProcess` at `0x100435b79`
- `KERNEL32!GetCurrentProcess` at `0x100435b82`
- `KERNEL32!GetCurrentProcess` at `0x100435b79`
- `KERNEL32!GetCurrentProcess` at `0x100435b82`
- `ADVAPI32!OpenThreadToken` at `0x100435b4d`
- `ADVAPI32!OpenThreadToken` at `0x100435b4d`
- `ADVAPI32!SetThreadToken` at `0x10048f38c`
- `ADVAPI32!SetThreadToken` at `0x10048f38c`
- `ADVAPI32!RevertToSelf` at `0x10048f359`
- `ADVAPI32!RevertToSelf` at `0x10048f359`

## string_xrefs

- `0x10048f3bb`: `reimpersonated`
- `0x10048f3b4`: `SetThreadToken failed to reimpersonate: %d`

## pseudocode

```c
void __fastcall SystemThread::CreateThreadHandle(SystemThread *this)
{
  DWORD v1; // r8d
  BOOL v3; // edi
  HANDLE v4; // rbp
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v8; // rax
  DWORD v9; // eax
  void *TokenHandle; // [rsp+70h] [rbp+8h] BYREF
  HANDLE TargetHandle; // [rsp+78h] [rbp+10h] BYREF

  v1 = *((_DWORD *)this + 70);
  TargetHandle = 0;
  v3 = 0;
  v4 = OpenThread(0xF0000u, 0, v1);
  if ( v4 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      if ( TokenHandle )
      {
        v3 = RevertToSelf();
        if ( !v3 )
        {
LABEL_8:
          if ( TokenHandle )
            CloseHandle(TokenHandle);
LABEL_10:
          CloseHandle(v4);
          return;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      TokenHandle = 0;
      if ( LastError != 1008 && LastError != 1309 )
        goto LABEL_10;
    }
    CurrentProcess = GetCurrentProcess();
    v8 = GetCurrentProcess();
    if ( DuplicateHandle(v8, v4, CurrentProcess, &TargetHandle, 0x1FFFFFu, 0, 0)
      && _InterlockedCompareExchange64((volatile signed __int64 *)this + 37, (signed __int64)TargetHandle, 0) )
    {
      CloseHandle(TargetHandle);
    }
    if ( v3 && !SetThreadToken(0, TokenHandle) )
    {
      v9 = GetLastError();
      utassert_fail(1u, "reimpersonated", "worker_ext.cpp", 348, "SetThreadToken failed to reimpersonate: %d", v9);
    }
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x100435af0  push    rbp
0x100435af2  push    rsi
0x100435af3  push    rdi
0x100435af4  push    r14
0x100435af6  sub     rsp, 48h
0x100435afa  mov     r8d, [rcx+118h]; dwThreadId
0x100435b01  mov     rsi, rcx
0x100435b04  xor     r14d, r14d
0x100435b07  mov     ecx, 0F0000h; dwDesiredAccess
0x100435b0c  xor     edx, edx; bInheritHandle
0x100435b0e  mov     [rsp+68h+TargetHandle], r14
0x100435b13  mov     edi, r14d
0x100435b16  call    cs:__imp_OpenThread
0x100435b1c  mov     rbp, rax
0x100435b1f  test    rax, rax
0x100435b22  jz      loc_100435BF4
0x100435b28  mov     [rsp+68h+var_28], r15
0x100435b2d  mov     [rsp+68h+TokenHandle], r14
0x100435b32  call    cs:__imp_GetCurrentThread
0x100435b38  mov     r15d, 1
0x100435b3e  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x100435b43  mov     rcx, rax; ThreadHandle
0x100435b46  lea     edx, [r14+0Ch]; DesiredAccess
0x100435b4a  mov     r8d, r15d; OpenAsSelf
0x100435b4d  call    cs:__imp_OpenThreadToken
0x100435b53  test    eax, eax
0x100435b55  jnz     loc_10048F34E
0x100435b5b  call    cs:__imp_GetLastError
0x100435b61  mov     [rsp+68h+TokenHandle], r14
0x100435b66  cmp     eax, 3F0h
0x100435b6b  jnz     loc_10048F33E
0x100435b71  mov     [rsp+68h+arg_10], rbx
0x100435b79  call    cs:__imp_GetCurrentProcess
0x100435b7f  mov     rbx, rax
0x100435b82  call    cs:__imp_GetCurrentProcess
0x100435b88  mov     [rsp+68h+dwOptions], r14d; dwOptions
0x100435b8d  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x100435b92  mov     rcx, rax; hSourceProcessHandle
0x100435b95  mov     [rsp+68h+bInheritHandle], r14d; bInheritHandle
0x100435b9a  mov     r8, rbx; hTargetProcessHandle
0x100435b9d  mov     [rsp+68h+dwDesiredAccess], 1FFFFFh; dwDesiredAccess
0x100435ba5  mov     rdx, rbp; hSourceHandle
0x100435ba8  call    cs:__imp_DuplicateHandle
0x100435bae  mov     rbx, [rsp+68h+arg_10]
0x100435bb6  test    eax, eax
0x100435bb8  jz      short loc_100435BD0
0x100435bba  mov     rcx, [rsp+68h+TargetHandle]
0x100435bbf  xor     eax, eax
0x100435bc1  lock cmpxchg [rsi+128h], rcx
0x100435bca  jnz     loc_10048F373
0x100435bd0  test    edi, edi
0x100435bd2  jnz     loc_10048F385
0x100435bd8  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x100435bdd  test    rcx, rcx
0x100435be0  jnz     loc_10048F3D3
0x100435be6  mov     rcx, rbp; hObject
0x100435be9  call    cs:__imp_CloseHandle
0x100435bef  mov     r15, [rsp+68h+var_28]
0x100435bf4  add     rsp, 48h
0x100435bf8  pop     r14
0x100435bfa  pop     rdi
0x100435bfb  pop     rsi
0x100435bfc  pop     rbp
0x100435bfd  retn
0x10048f33e  cmp     eax, 51Dh
0x10048f343  jz      loc_100435B71
0x10048f349  jmp     loc_100435BE6
0x10048f34e  cmp     [rsp+68h+TokenHandle], rdi
0x10048f353  jz      loc_100435B71
0x10048f359  call    cs:__imp_RevertToSelf
0x10048f35f  test    eax, eax
0x10048f361  cmovnz  edi, r15d
0x10048f365  test    edi, edi
0x10048f367  jnz     loc_100435B71
0x10048f36d  jmp     loc_100435BD8
0x10048f373  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x10048f378  call    cs:__imp_CloseHandle
0x10048f37e  nop
0x10048f37f  jmp     loc_100435BD0
0x10048f385  mov     rdx, [rsp+68h+TokenHandle]; Token
0x10048f38a  xor     ecx, ecx; Thread
0x10048f38c  call    cs:__imp_SetThreadToken
0x10048f392  test    eax, eax
0x10048f394  jnz     loc_100435BD8
0x10048f39a  call    cs:__imp_GetLastError
0x10048f3a0  mov     [rsp+68h+bInheritHandle], eax
0x10048f3a4  mov     r9d, 15Ch; int
0x10048f3aa  lea     r8, aWorkerExtCpp; "worker_ext.cpp"
0x10048f3b1  mov     ecx, r15d; unsigned int
0x10048f3b4  lea     rax, aSetthreadtoken; "SetThreadToken failed to reimpersonate:"...
0x10048f3bb  lea     rdx, aReimpersonated; "reimpersonated"
0x10048f3c2  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; Format
0x10048f3c7  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10048f3cc  nop
0x10048f3cd  jmp     loc_100435BD8
0x10048f3d3  call    cs:__imp_CloseHandle
0x10048f3d9  nop
0x10048f3da  jmp     loc_100435BE6
```
