# NSecurityLibrary::TUserContext::Initialize(int,int,ulong)

- ea: `0x140056f9c`
- end: `0x14005703c`
- name: `?Initialize@TUserContext@NSecurityLibrary@@AEAAJHHK@Z`
- size: `160`
- prototype: `int(NSecurityLibrary::TUserContext *__hidden this, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140056ec8`

## callees

- `0x1400087c8`
- `0x140056f9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140056fe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140056ff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140056ff7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140056fcc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140056fcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140056fb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140056fb1`
- `ADVAPI32!OpenProcessToken` at `0x14005700c`
- `ADVAPI32!OpenProcessToken` at `0x14005700c`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::TUserContext::Initialize(HANDLE *this, __int64 a2, __int64 a3, DWORD a4)
{
  HANDLE CurrentThread; // rax
  BOOL v7; // eax
  int v8; // edx
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  v7 = OpenThreadToken(CurrentThread, a4, 1, this + 2);
  v8 = *((_DWORD *)this + 7);
  if ( v7 )
  {
    *((_DWORD *)this + 7) = v8 & 0xFFFFFFFB;
  }
  else
  {
    if ( (v8 & 4) == 0 )
      return GetLastErrorAsHResult();
    if ( GetLastError() != 1008 )
      return GetLastErrorAsHResult();
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, a4, this + 2) )
      return GetLastErrorAsHResult();
  }
  return 0;
}

```

## disassembly

```asm
0x140056f9c  mov     [rsp+arg_0], rbx
0x140056fa1  mov     [rsp+arg_8], rsi
0x140056fa6  push    rdi
0x140056fa7  sub     rsp, 20h
0x140056fab  mov     edi, r9d
0x140056fae  mov     rbx, rcx
0x140056fb1  call    cs:__imp_GetCurrentThread
0x140056fb8  nop     dword ptr [rax+rax+00h]
0x140056fbd  lea     r9, [rbx+10h]; TokenHandle
0x140056fc1  mov     r8d, 1; OpenAsSelf
0x140056fc7  mov     rcx, rax; ThreadHandle
0x140056fca  mov     edx, edi; DesiredAccess
0x140056fcc  call    cs:__imp_OpenThreadToken
0x140056fd3  nop     dword ptr [rax+rax+00h]
0x140056fd8  mov     edx, [rbx+1Ch]
0x140056fdb  test    eax, eax
0x140056fdd  jnz     short loc_140057023
0x140056fdf  test    dl, 4
0x140056fe2  jz      short loc_14005701C
0x140056fe4  call    cs:__imp_GetLastError
0x140056feb  nop     dword ptr [rax+rax+00h]
0x140056ff0  cmp     eax, 3F0h
0x140056ff5  jnz     short loc_14005701C
0x140056ff7  call    cs:__imp_GetCurrentProcess
0x140056ffe  nop     dword ptr [rax+rax+00h]
0x140057003  lea     r8, [rbx+10h]; TokenHandle
0x140057007  mov     edx, edi; DesiredAccess
0x140057009  mov     rcx, rax; ProcessHandle
0x14005700c  call    cs:__imp_OpenProcessToken
0x140057013  nop     dword ptr [rax+rax+00h]
0x140057018  test    eax, eax
0x14005701a  jnz     short loc_140057029
0x14005701c  call    GetLastErrorAsHResult
0x140057021  jmp     short loc_14005702B
0x140057023  and     edx, 0FFFFFFFBh
0x140057026  mov     [rbx+1Ch], edx
0x140057029  xor     eax, eax
0x14005702b  mov     rbx, [rsp+28h+arg_0]
0x140057030  mov     rsi, [rsp+28h+arg_8]
0x140057035  add     rsp, 20h
0x140057039  pop     rdi
0x14005703a  retn
```
