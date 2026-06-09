# HcsClient::NotificationWorker::NotificationWorker(std::shared_ptr<HcsClient::OperationTracker>)

- ea: `0x18003bab4`
- end: `0x18003bbe1`
- name: `??0NotificationWorker@HcsClient@@QEAA@V?$shared_ptr@VOperationTracker@HcsClient@@@std@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003dc18`

## callees

- `0x18000d0ec`
- `0x18003bab4`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bb5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bb5a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003bb4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003bb4c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003bb23`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003bb23`

## string_xrefs

- `0x18003bbcf`: `onecore\vm\compute\dll\lib\core\operationtracker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall HcsClient::NotificationWorker::NotificationWorker(_QWORD *pv, _QWORD *a2)
{
  __int64 v4; // rax
  PTP_WORK ThreadpoolWork; // rbp
  const char *v6; // r9
  struct _TP_WORK *v7; // r14
  DWORD LastError; // ebx
  volatile signed __int32 *v9; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *pv = 0;
  pv[1] = 0;
  pv[2] = 0;
  *((_BYTE *)pv + 24) = 0;
  pv[4] = 0;
  pv[5] = 0;
  pv[6] = 0;
  pv[7] = 0;
  pv[8] = 0;
  pv[9] = 0;
  if ( a2[1] )
  {
    pv[8] = *a2;
    v4 = a2[1];
    pv[9] = v4;
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 12));
  }
  ThreadpoolWork = CreateThreadpoolWork(HcsClient::NotificationWorker::Worker, pv, 0);
  v7 = (struct _TP_WORK *)pv[4];
  if ( v7 )
  {
    LastError = GetLastError();
    CloseThreadpoolWork(v7);
    SetLastError(LastError);
  }
  pv[4] = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\operationtracker.cpp",
      v6);
  v9 = (volatile signed __int32 *)a2[1];
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return pv;
}

```

## disassembly

```asm
0x18003bab4  mov     rax, rsp
0x18003bab7  mov     [rax+18h], rbx
0x18003babb  mov     [rax+20h], rbp
0x18003babf  mov     [rax+10h], rdx
0x18003bac3  mov     [rax+8], rcx
0x18003bac7  push    rsi
0x18003bac8  push    rdi
0x18003bac9  push    r14
0x18003bacb  sub     rsp, 20h
0x18003bacf  mov     rsi, rdx
0x18003bad2  mov     rdi, rcx
0x18003bad5  xor     eax, eax
0x18003bad7  mov     [rcx], rax
0x18003bada  mov     [rcx+8], rax
0x18003bade  mov     [rcx+10h], rax
0x18003bae2  mov     [rcx+18h], al
0x18003bae5  mov     [rcx+20h], rax
0x18003bae9  mov     [rcx+28h], rax
0x18003baed  mov     [rcx+30h], rax
0x18003baf1  mov     [rcx+38h], rax
0x18003baf5  mov     [rcx+40h], rax
0x18003baf9  mov     [rcx+48h], rax
0x18003bafd  cmp     [rdx+8], rax
0x18003bb01  jz      short loc_18003BB16
0x18003bb03  mov     rax, [rdx]
0x18003bb06  mov     [rcx+40h], rax
0x18003bb0a  mov     rax, [rdx+8]
0x18003bb0e  mov     [rcx+48h], rax
0x18003bb12  lock inc dword ptr [rax+0Ch]
0x18003bb16  xor     r8d, r8d; pcbe
0x18003bb19  mov     rdx, rdi; pv
0x18003bb1c  lea     rcx, ?Worker@NotificationWorker@HcsClient@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18003bb23  call    cs:__imp_CreateThreadpoolWork
0x18003bb2a  nop     dword ptr [rax+rax+00h]
0x18003bb2f  mov     rbp, rax
0x18003bb32  mov     r14, [rdi+20h]
0x18003bb36  test    r14, r14
0x18003bb39  jz      short loc_18003BB66
0x18003bb3b  call    cs:__imp_GetLastError
0x18003bb42  nop     dword ptr [rax+rax+00h]
0x18003bb47  mov     ebx, eax
0x18003bb49  mov     rcx, r14; pwk
0x18003bb4c  call    cs:__imp_CloseThreadpoolWork
0x18003bb53  nop     dword ptr [rax+rax+00h]
0x18003bb58  mov     ecx, ebx; dwErrCode
0x18003bb5a  call    cs:__imp_SetLastError
0x18003bb61  nop     dword ptr [rax+rax+00h]
0x18003bb66  mov     [rdi+20h], rbp
0x18003bb6a  test    rbp, rbp
0x18003bb6d  setz    al
0x18003bb70  mov     rcx, [rsp+38h]; this
0x18003bb75  test    al, al
0x18003bb77  jnz     short loc_18003BBCF
0x18003bb79  mov     rbx, [rsi+8]
0x18003bb7d  test    rbx, rbx
0x18003bb80  jz      short loc_18003BBB8
0x18003bb82  or      esi, 0FFFFFFFFh
0x18003bb85  mov     eax, esi
0x18003bb87  lock xadd [rbx+8], eax
0x18003bb8c  add     eax, esi
0x18003bb8e  jnz     short loc_18003BBB8
0x18003bb90  mov     rax, [rbx]
0x18003bb93  mov     rcx, rbx
0x18003bb96  mov     rax, [rax]
0x18003bb99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb9e  mov     eax, esi
0x18003bba0  lock xadd [rbx+0Ch], eax
0x18003bba5  add     eax, esi
0x18003bba7  jnz     short loc_18003BBB8
0x18003bba9  mov     rax, [rbx]
0x18003bbac  mov     rcx, rbx
0x18003bbaf  mov     rax, [rax+8]
0x18003bbb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbb8  mov     rax, rdi
0x18003bbbb  mov     rbx, [rsp+38h+arg_10]
0x18003bbc0  mov     rbp, [rsp+38h+arg_18]
0x18003bbc5  add     rsp, 20h
0x18003bbc9  pop     r14
0x18003bbcb  pop     rdi
0x18003bbcc  pop     rsi
0x18003bbcd  retn
0x18003bbcf  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\core\\o"...
0x18003bbd6  mov     edx, 72h ; 'r'; void *
0x18003bbdb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
