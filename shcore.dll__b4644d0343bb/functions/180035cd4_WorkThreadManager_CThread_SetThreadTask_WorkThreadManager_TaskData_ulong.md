# WorkThreadManager::CThread::SetThreadTask(WorkThreadManager::TaskData &&,ulong)

- ea: `0x180035cd4`
- end: `0x180035e8f`
- name: `?SetThreadTask@CThread@WorkThreadManager@@QEAA?AUTaskData@2@$$QEAU32@K@Z`
- size: `443`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180019918`
- `0x1800536ac`

## callees

- `0x180035cd4`
- `0x18006bc34`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035e59`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035e59`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035e1e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035e1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035d03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035d03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035e30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035e30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035e61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035e61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035e0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035e0c`

## string_xrefs

- `0x180035e7d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WorkThreadManager::CThread::SetThreadTask(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v4; // ebx
  RTL_SRWLOCK *v8; // r14
  _DWORD *v9; // rsi
  HMODULE *v10; // r12
  _QWORD *v11; // rdx
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  HMODULE *v15; // r14
  HMODULE v16; // rax
  HMODULE v17; // r13
  int v18; // ebx
  const char *v19; // r9
  DWORD LastError; // ebx
  char v22; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HMODULE v24; // [rsp+70h] [rbp+8h]

  v4 = a4;
  v8 = (RTL_SRWLOCK *)(a1 + 224);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 224));
  v9 = (_DWORD *)(a1 + 144);
  *(_DWORD *)a2 = *(_DWORD *)(a1 + 144);
  *(_DWORD *)(a2 + 4) = *(_DWORD *)(a1 + 148);
  *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 152);
  *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 160);
  *(_QWORD *)(a2 + 24) = *(_QWORD *)(a1 + 168);
  *(_DWORD *)(a2 + 32) = *(_DWORD *)(a1 + 176);
  v10 = (HMODULE *)(a1 + 184);
  *(_QWORD *)(a2 + 40) = *(_QWORD *)(a1 + 184);
  *(_QWORD *)(a1 + 184) = 0;
  v11 = (_QWORD *)(a1 + 192);
  *(_QWORD *)(a2 + 48) = 0;
  if ( a2 + 48 != a1 + 192 )
  {
    *(_QWORD *)(a2 + 48) = *v11;
    *v11 = 0;
  }
  *(_QWORD *)(a2 + 64) = a2 + 56;
  *(_QWORD *)(a2 + 56) = a2 + 56;
  if ( v9 != (_DWORD *)a3 )
  {
    *v9 = *(_DWORD *)a3;
    *(_DWORD *)(a1 + 148) = *(_DWORD *)(a3 + 4);
    *(_DWORD *)(a1 + 152) = *(_DWORD *)(a3 + 8);
    *(_QWORD *)(a1 + 160) = *(_QWORD *)(a3 + 16);
    v12 = (__int64 *)(a3 + 48);
    v13 = 0;
    if ( &v22 != (char *)(a3 + 48) )
    {
      v13 = *v12;
      *v12 = 0;
    }
    v14 = *v11;
    *v11 = v13;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v15 = (HMODULE *)(a3 + 40);
    if ( v10 != (HMODULE *)(a3 + 40) )
    {
      v16 = *v15;
      v24 = *v15;
      v17 = *v10;
      if ( *v10 )
      {
        LastError = GetLastError();
        FreeLibrary(v17);
        SetLastError(LastError);
        v16 = v24;
        v4 = a4;
      }
      *v10 = v16;
      *v15 = 0;
    }
    *(_QWORD *)(a1 + 168) = *(_QWORD *)(a3 + 24);
    *(_DWORD *)(a1 + 176) = *(_DWORD *)(a3 + 32);
    v8 = (RTL_SRWLOCK *)(a1 + 224);
  }
  *(_DWORD *)(a1 + 216) = v4;
  *(_BYTE *)(a1 + 89) = 0;
  v18 = *(_DWORD *)(a1 + 80);
  if ( GetCurrentThreadId() != v18 && v18 && !SetEvent(*(HANDLE *)(a1 + 104)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v19);
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  return a2;
}

```

## disassembly

```asm
0x180035cd4  mov     [rsp+arg_8], rbx
0x180035cd9  mov     [rsp+arg_18], r9d
0x180035cde  push    rbp
0x180035cdf  push    rsi
0x180035ce0  push    rdi
0x180035ce1  push    r12
0x180035ce3  push    r13
0x180035ce5  push    r14
0x180035ce7  push    r15
0x180035ce9  sub     rsp, 30h
0x180035ced  mov     ebx, r9d
0x180035cf0  mov     rdi, r8
0x180035cf3  mov     r15, rdx
0x180035cf6  mov     rbp, rcx
0x180035cf9  lea     r14, [rcx+0E0h]
0x180035d00  mov     rcx, r14; SRWLock
0x180035d03  call    cs:__imp_AcquireSRWLockExclusive
0x180035d09  lea     rsi, [rbp+90h]
0x180035d10  mov     eax, [rsi]
0x180035d12  mov     [r15], eax
0x180035d15  mov     eax, [rsi+4]
0x180035d18  mov     [r15+4], eax
0x180035d1c  mov     eax, [rsi+8]
0x180035d1f  mov     [r15+8], eax
0x180035d23  mov     rax, [rsi+10h]
0x180035d27  mov     [r15+10h], rax
0x180035d2b  movsd   xmm0, qword ptr [rsi+18h]
0x180035d30  movsd   qword ptr [r15+18h], xmm0
0x180035d36  mov     eax, [rsi+20h]
0x180035d39  mov     [r15+20h], eax
0x180035d3d  lea     r12, [rsi+28h]
0x180035d41  mov     rax, [r12]
0x180035d45  mov     [r15+28h], rax
0x180035d49  xor     r13d, r13d
0x180035d4c  mov     [r12], r13
0x180035d50  lea     rcx, [r15+30h]
0x180035d54  lea     rdx, [rsi+30h]
0x180035d58  mov     [rcx], r13
0x180035d5b  cmp     rcx, rdx
0x180035d5e  jz      short loc_180035D69
0x180035d60  mov     rax, [rdx]
0x180035d63  mov     [rcx], rax
0x180035d66  mov     [rdx], r13
0x180035d69  lea     rax, [r15+38h]
0x180035d6d  mov     [rax+8], rax
0x180035d71  mov     [rax], rax
0x180035d74  cmp     rsi, rdi
0x180035d77  jz      loc_180035DFF
0x180035d7d  mov     eax, [rdi]
0x180035d7f  mov     [rsi], eax
0x180035d81  mov     eax, [rdi+4]
0x180035d84  mov     [rsi+4], eax
0x180035d87  mov     eax, [rdi+8]
0x180035d8a  mov     [rsi+8], eax
0x180035d8d  mov     rax, [rdi+10h]
0x180035d91  mov     [rsi+10h], rax
0x180035d95  lea     rcx, [rdi+30h]
0x180035d99  mov     rax, r13
0x180035d9c  lea     r8, [rsp+68h+var_48]
0x180035da1  cmp     r8, rcx
0x180035da4  jz      short loc_180035DAC
0x180035da6  mov     rax, [rcx]
0x180035da9  mov     [rcx], r13
0x180035dac  mov     rcx, [rdx]
0x180035daf  mov     [rdx], rax
0x180035db2  test    rcx, rcx
0x180035db5  jz      short loc_180035DC4
0x180035db7  mov     rax, [rcx]
0x180035dba  mov     rax, [rax+10h]
0x180035dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035dc3  nop
0x180035dc4  lea     r14, [rdi+28h]
0x180035dc8  cmp     r12, r14
0x180035dcb  jz      short loc_180035DE8
0x180035dcd  mov     rax, [r14]
0x180035dd0  mov     [rsp+68h+arg_0], rax
0x180035dd5  mov     r13, [r12]
0x180035dd9  test    r13, r13
0x180035ddc  jnz     short loc_180035E4E
0x180035dde  mov     [r12], rax
0x180035de2  xor     r13d, r13d
0x180035de5  mov     [r14], r13
0x180035de8  movsd   xmm0, qword ptr [rdi+18h]
0x180035ded  movsd   qword ptr [rsi+18h], xmm0
0x180035df2  mov     eax, [rdi+20h]
0x180035df5  mov     [rsi+20h], eax
0x180035df8  lea     r14, [rbp+0E0h]
0x180035dff  mov     [rbp+0D8h], ebx
0x180035e05  mov     [rbp+59h], r13b
0x180035e09  mov     ebx, [rbp+50h]
0x180035e0c  call    cs:__imp_GetCurrentThreadId
0x180035e12  cmp     eax, ebx
0x180035e14  jz      short loc_180035E28
0x180035e16  test    ebx, ebx
0x180035e18  jz      short loc_180035E28
0x180035e1a  mov     rcx, [rbp+68h]; hEvent
0x180035e1e  call    cs:__imp_SetEvent
0x180035e24  test    eax, eax
0x180035e26  jz      short loc_180035E78
0x180035e28  test    r14, r14
0x180035e2b  jz      short loc_180035E36
0x180035e2d  mov     rcx, r14; SRWLock
0x180035e30  call    cs:__imp_ReleaseSRWLockExclusive
0x180035e36  mov     rax, r15
0x180035e39  mov     rbx, [rsp+68h+arg_8]
0x180035e3e  add     rsp, 30h
0x180035e42  pop     r15
0x180035e44  pop     r14
0x180035e46  pop     r13
0x180035e48  pop     r12
0x180035e4a  pop     rdi
0x180035e4b  pop     rsi
0x180035e4c  pop     rbp
0x180035e4d  retn
0x180035e4e  call    cs:__imp_GetLastError
0x180035e54  mov     ebx, eax
0x180035e56  mov     rcx, r13; hLibModule
0x180035e59  call    cs:__imp_FreeLibrary
0x180035e5f  mov     ecx, ebx; dwErrCode
0x180035e61  call    cs:__imp_SetLastError
0x180035e67  mov     rax, [rsp+68h+arg_0]
0x180035e6c  mov     ebx, [rsp+68h+arg_18]
0x180035e73  jmp     loc_180035DDE
0x180035e78  mov     rcx, [rsp+68h]; this
0x180035e7d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035e84  mov     edx, 0A01h; void *
0x180035e89  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
