# NSecurityLibrary::TUserContext::TUserContext(int,int,ulong)

- ea: `0x140051ef8`
- end: `0x140051fb2`
- name: `??0TUserContext@NSecurityLibrary@@QEAA@HHK@Z`
- size: `186`
- prototype: `_QWORD(NSecurityLibrary::TUserContext *__hidden this, int, int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400146cc`
- `0x140051bd4`

## callees

- `0x140007bdc`
- `0x140051ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051f68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140051f75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140051f75`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140051f56`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140051f56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140051f42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140051f42`
- `ADVAPI32!OpenProcessToken` at `0x140051f83`
- `ADVAPI32!OpenProcessToken` at `0x140051f83`

## pseudocode

```c
NSecurityLibrary::TUserContext *__fastcall NSecurityLibrary::TUserContext::TUserContext(
        NSecurityLibrary::TUserContext *this,
        int a2,
        __int64 a3,
        DWORD a4)
{
  HANDLE *v4; // rdi
  HANDLE CurrentThread; // rax
  BOOL v8; // eax
  int v9; // ecx
  HANDLE CurrentProcess; // rax
  int LastErrorAsHResult; // eax

  *(_QWORD *)this = &NSecurityLibrary::TUserContext::`vftable';
  v4 = (HANDLE *)((char *)this + 16);
  *((_DWORD *)this + 2) = 1685222261;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 7) = a2 != 0 ? 4 : 0;
  *((_DWORD *)this + 6) = -2147467259;
  *((_QWORD *)this + 4) = 0;
  CurrentThread = GetCurrentThread();
  v8 = OpenThreadToken(CurrentThread, a4, 1, v4);
  v9 = *((_DWORD *)this + 7);
  if ( v8 )
  {
    *((_DWORD *)this + 7) = v9 & 0xFFFFFFFB;
LABEL_7:
    LastErrorAsHResult = 0;
    goto LABEL_8;
  }
  if ( (v9 & 4) != 0 && GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, a4, v4) )
      goto LABEL_7;
  }
  LastErrorAsHResult = GetLastErrorAsHResult();
LABEL_8:
  *((_DWORD *)this + 6) = LastErrorAsHResult;
  return this;
}

```

## disassembly

```asm
0x140051ef8  mov     [rsp+arg_0], rbx
0x140051efd  mov     [rsp+arg_8], rsi
0x140051f02  push    rdi
0x140051f03  sub     rsp, 20h
0x140051f07  lea     rax, ??_7TUserContext@NSecurityLibrary@@6B@; const NSecurityLibrary::TUserContext::`vftable'
0x140051f0e  neg     edx
0x140051f10  mov     [rcx], rax
0x140051f13  lea     rdi, [rcx+10h]
0x140051f17  mov     dword ptr [rcx+8], 64727375h
0x140051f1e  sbb     eax, eax
0x140051f20  and     eax, 4
0x140051f23  mov     qword ptr [rdi], 0
0x140051f2a  mov     [rcx+1Ch], eax
0x140051f2d  mov     esi, r9d
0x140051f30  mov     rbx, rcx
0x140051f33  mov     dword ptr [rcx+18h], 80004005h
0x140051f3a  mov     qword ptr [rcx+20h], 0
0x140051f42  call    cs:__imp_GetCurrentThread
0x140051f48  mov     r9, rdi; TokenHandle
0x140051f4b  mov     r8d, 1; OpenAsSelf
0x140051f51  mov     rcx, rax; ThreadHandle
0x140051f54  mov     edx, esi; DesiredAccess
0x140051f56  call    cs:__imp_OpenThreadToken
0x140051f5c  mov     ecx, [rbx+1Ch]
0x140051f5f  test    eax, eax
0x140051f61  jnz     short loc_140051F94
0x140051f63  test    cl, 4
0x140051f66  jz      short loc_140051F8D
0x140051f68  call    cs:__imp_GetLastError
0x140051f6e  cmp     eax, 3F0h
0x140051f73  jnz     short loc_140051F8D
0x140051f75  call    cs:__imp_GetCurrentProcess
0x140051f7b  mov     r8, rdi; TokenHandle
0x140051f7e  mov     edx, esi; DesiredAccess
0x140051f80  mov     rcx, rax; ProcessHandle
0x140051f83  call    cs:__imp_OpenProcessToken
0x140051f89  test    eax, eax
0x140051f8b  jnz     short loc_140051F9A
0x140051f8d  call    GetLastErrorAsHResult
0x140051f92  jmp     short loc_140051F9C
0x140051f94  and     ecx, 0FFFFFFFBh
0x140051f97  mov     [rbx+1Ch], ecx
0x140051f9a  xor     eax, eax
0x140051f9c  mov     rsi, [rsp+28h+arg_8]
0x140051fa1  mov     [rbx+18h], eax
0x140051fa4  mov     rax, rbx
0x140051fa7  mov     rbx, [rsp+28h+arg_0]
0x140051fac  add     rsp, 20h
0x140051fb0  pop     rdi
0x140051fb1  retn
```
