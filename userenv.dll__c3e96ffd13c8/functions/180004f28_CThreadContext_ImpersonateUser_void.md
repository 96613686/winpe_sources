# CThreadContext::ImpersonateUser(void *)

- ea: `0x180004f28`
- end: `0x180004fb5`
- name: `?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(CThreadContext *this, void *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004938`
- `0x1800059a4`
- `0x1800067b0`
- `0x180006904`
- `0x180017ee0`

## callees

- `0x180004f28`
- `0x180004fc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004f52`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004f52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004f3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004f3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fa6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180004f70`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180004f70`

## pseudocode

```c
__int64 __fastcall CThreadContext::ImpersonateUser(CThreadContext *this, void *a2)
{
  void **v3; // rdi
  HANDLE CurrentThread; // rax
  BOOL v6; // eax
  int v7; // ebx
  BOOL v8; // eax

  v3 = (void **)((char *)this + 8);
  CurrentThread = GetCurrentThread();
  v6 = OpenThreadToken(CurrentThread, 0x2000Cu, 1, v3);
  v7 = ResultFromWin32Bool(v6);
  if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147023888 )
  {
    v8 = ImpersonateLoggedOnUser(a2);
    v7 = ResultFromWin32Bool(v8);
    if ( v7 < 0 )
    {
      if ( *v3 )
      {
        CloseHandle(*v3);
        *v3 = 0;
      }
    }
    else
    {
      *(_DWORD *)this = 1;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004f28  push    rbx
0x180004f2a  push    rbp
0x180004f2b  push    rsi
0x180004f2c  push    rdi
0x180004f2d  sub     rsp, 28h
0x180004f31  mov     rbp, rdx
0x180004f34  lea     rdi, [rcx+8]
0x180004f38  mov     rsi, rcx
0x180004f3b  call    cs:__imp_GetCurrentThread
0x180004f41  mov     r9, rdi; TokenHandle
0x180004f44  mov     edx, 2000Ch; DesiredAccess
0x180004f49  mov     rcx, rax; ThreadHandle
0x180004f4c  mov     r8d, 1; OpenAsSelf
0x180004f52  call    cs:__imp_OpenThreadToken
0x180004f58  mov     ecx, eax; int
0x180004f5a  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180004f5f  mov     ebx, eax
0x180004f61  mov     eax, 80000000h
0x180004f66  lea     ecx, [rbx+rax]
0x180004f69  test    eax, ecx
0x180004f6b  jz      short loc_180004F94
0x180004f6d  mov     rcx, rbp; hToken
0x180004f70  call    cs:__imp_ImpersonateLoggedOnUser
0x180004f76  mov     ecx, eax; int
0x180004f78  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180004f7d  mov     ebx, eax
0x180004f7f  test    eax, eax
0x180004f81  js      short loc_180004F9E
0x180004f83  mov     dword ptr [rsi], 1
0x180004f89  mov     eax, ebx
0x180004f8b  add     rsp, 28h
0x180004f8f  pop     rdi
0x180004f90  pop     rsi
0x180004f91  pop     rbp
0x180004f92  pop     rbx
0x180004f93  retn
0x180004f94  cmp     ebx, 800703F0h
0x180004f9a  jz      short loc_180004F6D
0x180004f9c  jmp     short loc_180004F89
0x180004f9e  mov     rcx, [rdi]; hObject
0x180004fa1  test    rcx, rcx
0x180004fa4  jz      short loc_180004F89
0x180004fa6  call    cs:__imp_CloseHandle
0x180004fac  mov     qword ptr [rdi], 0
0x180004fb3  jmp     short loc_180004F89
```
