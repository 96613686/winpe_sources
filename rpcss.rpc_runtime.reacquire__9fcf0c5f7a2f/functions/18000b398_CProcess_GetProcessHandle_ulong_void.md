# CProcess::GetProcessHandle(ulong,void * *)

- ea: `0x18000b398`
- end: `0x18000b612`
- name: `?GetProcessHandle@CProcess@@QEBAJKPEAPEAX@Z`
- size: `634`
- prototype: `int(CProcess *__hidden this, unsigned int, void **)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009054`
- `0x18000b15c`
- `0x18002b624`
- `0x18002d440`
- `0x180059760`
- `0x180070a98`
- `0x1800c44ec`

## callees

- `0x18000b398`
- `0x18000ce5c`
- `0x1800210f8`
- `0x18002f670`
- `0x180034260`
- `0x18006016c`
- `0x1800a7388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b53c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b53c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b41a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b4e6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b41a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b4e6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b52a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b52a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b3da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b3ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b3da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b3ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4b9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b5ca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b5ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b3bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b3bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b432`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b478`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b432`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b478`

## string_xrefs

- `0x18000b453`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18000b504`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18000b5ab`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x18000b585`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18000b57e`: `CToken::Impersonate`

## pseudocode

```c
__int64 __fastcall CProcess::GetProcessHandle(CProcess *this, DWORD a2, void **a3)
{
  RTL_SRWLOCK *v3; // rsi
  bool v7; // zf
  HANDLE v8; // rax
  void *v9; // rdi
  void *v10; // rbx
  HANDLE v11; // rax
  __int64 v13; // rdx
  signed int LastError; // ebx
  BOOL v15; // esi
  HANDLE CurrentProcess; // rax
  void *v17; // rdi
  void *v18; // rbx
  HANDLE v19; // rax
  const char *v20; // r9
  __int64 v21; // rdx
  bool v22; // sf
  HANDLE v23; // rax
  int dwDesiredAccess; // [rsp+20h] [rbp-58h]
  __int64 bInheritHandle; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  RTL_SRWLOCK *v27; // [rsp+80h] [rbp+8h] BYREF

  v3 = (RTL_SRWLOCK *)((char *)this + 544);
  *a3 = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 68);
  v7 = *((_QWORD *)this + 15) == 0;
  v27 = v3;
  if ( v7
    || (v8 = GetCurrentProcess(),
        v9 = (void *)*((_QWORD *)this + 15),
        v10 = v8,
        v11 = GetCurrentProcess(),
        !DuplicateHandle(v11, v9, v10, a3, a2, 0, 0)) )
  {
    v13 = *((_QWORD *)this + 3);
    if ( !v13 )
    {
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35F,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
        (const char *)0x8000FFFFLL,
        dwDesiredAccess);
      if ( v3 )
        ReleaseSRWLockShared(v3);
      return (unsigned int)LastError;
    }
    if ( NtCurrentTeb()->IsImpersonating )
    {
      v15 = 0;
      goto LABEL_11;
    }
    LastError = 0;
    v15 = SetThreadToken(0, *(HANDLE *)(v13 + 72));
    if ( !v15 )
    {
      LastError = GetLastError();
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
      {
        LODWORD(bInheritHandle) = LastError;
        ComTraceMessageT<int>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
          (unsigned int)"CToken::Impersonate",
          1317,
          0,
          (__int64)L"%!WINERROR!",
          bInheritHandle);
      }
      v22 = LastError < 0;
      if ( LastError <= 0 )
      {
LABEL_23:
        if ( v22 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x362,
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
            (const char *)(unsigned int)LastError,
            dwDesiredAccess);
          goto LABEL_28;
        }
LABEL_11:
        if ( *((_QWORD *)this + 15) )
        {
          CurrentProcess = GetCurrentProcess();
          v17 = (void *)*((_QWORD *)this + 15);
          v18 = CurrentProcess;
          v19 = GetCurrentProcess();
          if ( !DuplicateHandle(v19, v17, v18, a3, a2, 0, 0) )
          {
            v21 = 873;
LABEL_14:
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)v21,
                          (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
                          v20);
            CToken::Revert(*((CToken **)this + 3), v15);
LABEL_28:
            Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v27);
            return (unsigned int)LastError;
          }
        }
        else
        {
          v23 = OpenProcess(a2, 0, *((_DWORD *)this + 22));
          *a3 = v23;
          if ( !v23 )
          {
            v21 = 880;
            goto LABEL_14;
          }
        }
        CToken::Revert(*((CToken **)this + 3), v15);
        LastError = 0;
        goto LABEL_28;
      }
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v22 = LastError < 0;
    goto LABEL_23;
  }
  if ( v3 )
    ReleaseSRWLockShared(v3);
  return 0;
}

```

## disassembly

```asm
0x18000b398  push    rbx
0x18000b39a  push    rbp
0x18000b39b  push    rsi
0x18000b39c  push    rdi
0x18000b39d  push    r14
0x18000b39f  push    r15
0x18000b3a1  sub     rsp, 48h
0x18000b3a5  lea     rsi, [rcx+220h]
0x18000b3ac  mov     qword ptr [r8], 0
0x18000b3b3  mov     rbp, rcx
0x18000b3b6  mov     r14, r8
0x18000b3b9  mov     rcx, rsi; SRWLock
0x18000b3bc  mov     r15d, edx
0x18000b3bf  call    cs:__imp_AcquireSRWLockShared
0x18000b3c6  nop     dword ptr [rax+rax+00h]
0x18000b3cb  cmp     qword ptr [rbp+78h], 0
0x18000b3d0  mov     [rsp+78h+arg_0], rsi
0x18000b3d8  jz      short loc_18000B445
0x18000b3da  call    cs:__imp_GetCurrentProcess
0x18000b3e1  nop     dword ptr [rax+rax+00h]
0x18000b3e6  mov     rdi, [rbp+78h]
0x18000b3ea  mov     rbx, rax
0x18000b3ed  call    cs:__imp_GetCurrentProcess
0x18000b3f4  nop     dword ptr [rax+rax+00h]
0x18000b3f9  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18000b401  mov     r9, r14; lpTargetHandle
0x18000b404  mov     rcx, rax; hSourceProcessHandle
0x18000b407  mov     dword ptr [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18000b40f  mov     r8, rbx; hTargetProcessHandle
0x18000b412  mov     [rsp+78h+dwDesiredAccess], r15d; dwDesiredAccess
0x18000b417  mov     rdx, rdi; hSourceHandle
0x18000b41a  call    cs:__imp_DuplicateHandle
0x18000b421  nop     dword ptr [rax+rax+00h]
0x18000b426  test    eax, eax
0x18000b428  jz      short loc_18000B445
0x18000b42a  test    rsi, rsi
0x18000b42d  jz      short loc_18000B43E
0x18000b42f  mov     rcx, rsi; SRWLock
0x18000b432  call    cs:__imp_ReleaseSRWLockShared
0x18000b439  nop     dword ptr [rax+rax+00h]
0x18000b43e  xor     eax, eax
0x18000b440  jmp     loc_18000B604
0x18000b445  mov     rdx, [rbp+18h]
0x18000b449  test    rdx, rdx
0x18000b44c  jnz     short loc_18000B489
0x18000b44e  mov     rcx, [rsp+78h]; this
0x18000b453  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x18000b45a  mov     ebx, 8000FFFFh
0x18000b45f  mov     edx, 35Fh; void *
0x18000b464  mov     r9d, ebx; char *
0x18000b467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b46c  test    rsi, rsi
0x18000b46f  jz      loc_18000B602
0x18000b475  mov     rcx, rsi; SRWLock
0x18000b478  call    cs:__imp_ReleaseSRWLockShared
0x18000b47f  nop     dword ptr [rax+rax+00h]
0x18000b484  jmp     loc_18000B602
0x18000b489  mov     eax, gs:179Ch
0x18000b491  test    eax, eax
0x18000b493  jz      loc_18000B522
0x18000b499  xor     esi, esi
0x18000b49b  cmp     qword ptr [rbp+78h], 0
0x18000b4a0  jz      loc_18000B5C1
0x18000b4a6  call    cs:__imp_GetCurrentProcess
0x18000b4ad  nop     dword ptr [rax+rax+00h]
0x18000b4b2  mov     rdi, [rbp+78h]
0x18000b4b6  mov     rbx, rax
0x18000b4b9  call    cs:__imp_GetCurrentProcess
0x18000b4c0  nop     dword ptr [rax+rax+00h]
0x18000b4c5  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18000b4cd  mov     r9, r14; lpTargetHandle
0x18000b4d0  mov     rcx, rax; hSourceProcessHandle
0x18000b4d3  mov     dword ptr [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18000b4db  mov     r8, rbx; hTargetProcessHandle
0x18000b4de  mov     [rsp+78h+dwDesiredAccess], r15d; dwDesiredAccess
0x18000b4e3  mov     rdx, rdi; hSourceHandle
0x18000b4e6  call    cs:__imp_DuplicateHandle
0x18000b4ed  nop     dword ptr [rax+rax+00h]
0x18000b4f2  test    eax, eax
0x18000b4f4  jnz     loc_18000B5E8
0x18000b4fa  mov     edx, 369h; void *
0x18000b4ff  mov     rcx, [rsp+78h]; this
0x18000b504  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x18000b50b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b510  mov     rcx, [rbp+18h]; this
0x18000b514  mov     edx, esi; int
0x18000b516  mov     ebx, eax
0x18000b518  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18000b51d  jmp     loc_18000B5F5
0x18000b522  mov     rdx, [rdx+48h]; Token
0x18000b526  xor     ecx, ecx; Thread
0x18000b528  xor     ebx, ebx
0x18000b52a  call    cs:__imp_SetThreadToken
0x18000b531  nop     dword ptr [rax+rax+00h]
0x18000b536  mov     esi, eax
0x18000b538  test    eax, eax
0x18000b53a  jnz     short loc_18000B59E
0x18000b53c  call    cs:__imp_GetLastError
0x18000b543  nop     dword ptr [rax+rax+00h]
0x18000b548  mov     ecx, cs:dword_1801574B8
0x18000b54e  mov     ebx, eax
0x18000b550  test    ecx, ecx
0x18000b552  jnz     short loc_18000B565
0x18000b554  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18000b55a  jz      short loc_18000B591
0x18000b55c  call    IsWppLevelEnabled
0x18000b561  test    al, al
0x18000b563  jz      short loc_18000B591
0x18000b565  lea     rax, aWinerror; "%!WINERROR!"
0x18000b56c  mov     dword ptr [rsp+78h+bInheritHandle], ebx
0x18000b570  xor     r9d, r9d
0x18000b573  mov     qword ptr [rsp+78h+dwDesiredAccess], rax; int
0x18000b578  mov     r8d, 525h
0x18000b57e  lea     rdx, aCtokenImperson; "CToken::Impersonate"
0x18000b585  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000b58c  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18000b591  test    ebx, ebx
0x18000b593  jle     short loc_18000B5A0
0x18000b595  movzx   ebx, bx
0x18000b598  or      ebx, 80070000h
0x18000b59e  test    ebx, ebx
0x18000b5a0  jns     loc_18000B49B
0x18000b5a6  mov     rcx, [rsp+78h]; this
0x18000b5ab  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x18000b5b2  mov     r9d, ebx; char *
0x18000b5b5  mov     edx, 362h; void *
0x18000b5ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5bf  jmp     short loc_18000B5F5
0x18000b5c1  mov     r8d, [rbp+58h]; dwProcessId
0x18000b5c5  xor     edx, edx; bInheritHandle
0x18000b5c7  mov     ecx, r15d; dwDesiredAccess
0x18000b5ca  call    cs:__imp_OpenProcess
0x18000b5d1  nop     dword ptr [rax+rax+00h]
0x18000b5d6  mov     [r14], rax
0x18000b5d9  test    rax, rax
0x18000b5dc  jnz     short loc_18000B5E8
0x18000b5de  mov     edx, 370h
0x18000b5e3  jmp     loc_18000B4FF
0x18000b5e8  mov     rcx, [rbp+18h]; this
0x18000b5ec  mov     edx, esi; int
0x18000b5ee  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18000b5f3  xor     ebx, ebx
0x18000b5f5  lea     rcx, [rsp+78h+arg_0]; this
0x18000b5fd  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x18000b602  mov     eax, ebx
0x18000b604  add     rsp, 48h
0x18000b608  pop     r15
0x18000b60a  pop     r14
0x18000b60c  pop     rdi
0x18000b60d  pop     rsi
0x18000b60e  pop     rbp
0x18000b60f  pop     rbx
0x18000b610  retn
```
