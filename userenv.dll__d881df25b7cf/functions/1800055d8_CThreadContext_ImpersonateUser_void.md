# CThreadContext::ImpersonateUser(void *)

- ea: `0x1800055d8`
- end: `0x18000567e`
- name: `?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z`
- size: `166`
- prototype: `int(CThreadContext *__hidden this, void *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004f48`
- `0x180006160`
- `0x180006ce0`
- `0x180006e18`
- `0x1800197f0`

## callees

- `0x1800055d8`
- `0x180005690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005608`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005608`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800055eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800055eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005669`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005669`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000562c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000562c`

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
0x1800055d8  push    rbx
0x1800055da  push    rbp
0x1800055db  push    rsi
0x1800055dc  push    rdi
0x1800055dd  sub     rsp, 28h
0x1800055e1  mov     rbp, rdx
0x1800055e4  lea     rdi, [rcx+8]
0x1800055e8  mov     rsi, rcx
0x1800055eb  call    cs:__imp_GetCurrentThread
0x1800055f2  nop     dword ptr [rax+rax+00h]
0x1800055f7  mov     r9, rdi; TokenHandle
0x1800055fa  mov     edx, 2000Ch; DesiredAccess
0x1800055ff  mov     rcx, rax; ThreadHandle
0x180005602  mov     r8d, 1; OpenAsSelf
0x180005608  call    cs:__imp_OpenThreadToken
0x18000560f  nop     dword ptr [rax+rax+00h]
0x180005614  mov     ecx, eax; int
0x180005616  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000561b  mov     ebx, eax
0x18000561d  mov     eax, 80000000h
0x180005622  lea     ecx, [rbx+rax]
0x180005625  test    eax, ecx
0x180005627  jz      short loc_180005657
0x180005629  mov     rcx, rbp; hToken
0x18000562c  call    cs:__imp_ImpersonateLoggedOnUser
0x180005633  nop     dword ptr [rax+rax+00h]
0x180005638  mov     ecx, eax; int
0x18000563a  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000563f  mov     ebx, eax
0x180005641  test    eax, eax
0x180005643  js      short loc_180005661
0x180005645  mov     dword ptr [rsi], 1
0x18000564b  mov     eax, ebx
0x18000564d  add     rsp, 28h
0x180005651  pop     rdi
0x180005652  pop     rsi
0x180005653  pop     rbp
0x180005654  pop     rbx
0x180005655  retn
0x180005657  cmp     ebx, 800703F0h
0x18000565d  jz      short loc_180005629
0x18000565f  jmp     short loc_18000564B
0x180005661  mov     rcx, [rdi]; hObject
0x180005664  test    rcx, rcx
0x180005667  jz      short loc_18000564B
0x180005669  call    cs:__imp_CloseHandle
0x180005670  nop     dword ptr [rax+rax+00h]
0x180005675  mov     qword ptr [rdi], 0
0x18000567c  jmp     short loc_18000564B
```
