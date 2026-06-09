# ProcessWatcherDesc::ProcessWatcherDesc(void *,ulong,std::function<void (ulong)>)

- ea: `0x18000c000`
- end: `0x18000c148`
- name: `??0ProcessWatcherDesc@@QEAA@PEAXKV?$function@$$A6AXK@Z@std@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(PVOID pv, HANDLE h)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c334`

## callees

- `0x18000c000`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c09b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c0f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c09b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c0f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000c0b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000c0b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000c0d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000c10a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000c0d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000c10a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000c0e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000c0e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000c0ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000c0ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c093`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c093`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall ProcessWatcherDesc::ProcessWatcherDesc(_QWORD *pv, HANDLE h, int a3, _QWORD *a4)
{
  int v8; // eax
  _QWORD *v9; // rcx
  _QWORD *v10; // rdx
  char *v11; // rbp
  DWORD LastError; // ebx
  struct _TP_WAIT *ThreadpoolWait; // r14
  struct _TP_WAIT *v14; // rbp
  DWORD v15; // ebx
  __int64 v16; // rdx
  _QWORD *v17; // rcx

  v8 = 2;
  do
  {
    pv[3] = 0;
    --v8;
  }
  while ( v8 );
  pv[4] = 0;
  pv[5] = 0;
  if ( pv != a4 )
  {
    v9 = (_QWORD *)a4[3];
    if ( v9 )
    {
      if ( v9 == a4 )
        v10 = pv;
      else
        v10 = 0;
      pv[3] = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))*v9)(v9, v10);
    }
  }
  *((_BYTE *)pv + 52) = 0;
  v11 = (char *)pv[5];
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v11);
    SetLastError(LastError);
  }
  pv[5] = h;
  *((_DWORD *)pv + 12) = a3;
  ThreadpoolWait = CreateThreadpoolWait(_lambda_b7e262f5e0bdd292e83db4eec345b51b_::_lambda_invoker_cdecl_, pv, 0);
  v14 = (struct _TP_WAIT *)pv[4];
  if ( v14 )
  {
    v15 = GetLastError();
    SetThreadpoolWait(v14, 0, 0);
    WaitForThreadpoolWaitCallbacks(v14, 1);
    CloseThreadpoolWait(v14);
    SetLastError(v15);
  }
  pv[4] = ThreadpoolWait;
  SetThreadpoolWait(ThreadpoolWait, h, 0);
  v17 = (_QWORD *)a4[3];
  if ( v17 )
  {
    LOBYTE(v16) = v17 != a4;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v17 + 32LL))(v17, v16);
    a4[3] = 0;
  }
  return pv;
}

```

## disassembly

```asm
0x18000c000  mov     [rsp+arg_8], rbx
0x18000c005  mov     [rsp+arg_18], r9
0x18000c00a  mov     [rsp+arg_0], rcx
0x18000c00f  push    rbp
0x18000c010  push    rsi
0x18000c011  push    rdi
0x18000c012  push    r14
0x18000c014  push    r15
0x18000c016  sub     rsp, 20h
0x18000c01a  mov     rsi, r9
0x18000c01d  mov     r14d, r8d
0x18000c020  mov     r15, rdx
0x18000c023  mov     rdi, rcx
0x18000c026  mov     eax, 2
0x18000c02b  mov     qword ptr [rcx+18h], 0
0x18000c033  sub     eax, 1
0x18000c036  jnz     short loc_18000C02B
0x18000c038  mov     qword ptr [rcx+20h], 0
0x18000c040  mov     qword ptr [rcx+28h], 0
0x18000c048  cmp     rdi, rsi
0x18000c04b  jz      short loc_18000C076
0x18000c04d  mov     rcx, [r9+18h]
0x18000c051  test    rcx, rcx
0x18000c054  jz      short loc_18000C076
0x18000c056  cmp     rcx, rsi
0x18000c059  setz    dl
0x18000c05c  mov     rax, [rcx]
0x18000c05f  mov     rax, [rax]
0x18000c062  test    dl, dl
0x18000c064  jz      short loc_18000C06B
0x18000c066  mov     rdx, rdi
0x18000c069  jmp     short loc_18000C06D
0x18000c06b  xor     edx, edx
0x18000c06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c072  mov     [rdi+18h], rax
0x18000c076  mov     byte ptr [rdi+34h], 0
0x18000c07a  mov     rbp, [rdi+28h]
0x18000c07e  lea     rax, [rbp-1]
0x18000c082  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c086  ja      short loc_18000C0A1
0x18000c088  call    cs:__imp_GetLastError
0x18000c08e  mov     ebx, eax
0x18000c090  mov     rcx, rbp; hObject
0x18000c093  call    cs:__imp_CloseHandle
0x18000c099  mov     ecx, ebx; dwErrCode
0x18000c09b  call    cs:__imp_SetLastError
0x18000c0a1  mov     [rdi+28h], r15
0x18000c0a5  mov     [rdi+30h], r14d
0x18000c0a9  xor     r8d, r8d; pcbe
0x18000c0ac  mov     rdx, rdi; pv
0x18000c0af  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b7e262f5e0bdd292e83db4eec345b51b_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18000c0b6  call    cs:__imp_CreateThreadpoolWait
0x18000c0bc  mov     r14, rax
0x18000c0bf  mov     rbp, [rdi+20h]
0x18000c0c3  test    rbp, rbp
0x18000c0c6  jz      short loc_18000C0FD
0x18000c0c8  call    cs:__imp_GetLastError
0x18000c0ce  mov     ebx, eax
0x18000c0d0  xor     r8d, r8d; pftTimeout
0x18000c0d3  xor     edx, edx; h
0x18000c0d5  mov     rcx, rbp; pwa
0x18000c0d8  call    cs:__imp_SetThreadpoolWait
0x18000c0de  mov     edx, 1; fCancelPendingCallbacks
0x18000c0e3  mov     rcx, rbp; pwa
0x18000c0e6  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000c0ec  mov     rcx, rbp; pwa
0x18000c0ef  call    cs:__imp_CloseThreadpoolWait
0x18000c0f5  mov     ecx, ebx; dwErrCode
0x18000c0f7  call    cs:__imp_SetLastError
0x18000c0fd  mov     [rdi+20h], r14
0x18000c101  xor     r8d, r8d; pftTimeout
0x18000c104  mov     rdx, r15; h
0x18000c107  mov     rcx, r14; pwa
0x18000c10a  call    cs:__imp_SetThreadpoolWait
0x18000c110  nop
0x18000c111  mov     rcx, [rsi+18h]
0x18000c115  test    rcx, rcx
0x18000c118  jz      short loc_18000C134
0x18000c11a  mov     rax, [rcx]
0x18000c11d  cmp     rcx, rsi
0x18000c120  setnz   dl
0x18000c123  mov     rax, [rax+20h]
0x18000c127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c12c  mov     qword ptr [rsi+18h], 0
0x18000c134  mov     rax, rdi
0x18000c137  mov     rbx, [rsp+48h+arg_8]
0x18000c13c  add     rsp, 20h
0x18000c140  pop     r15
0x18000c142  pop     r14
0x18000c144  pop     rdi
0x18000c145  pop     rsi
0x18000c146  pop     rbp
0x18000c147  retn
```
