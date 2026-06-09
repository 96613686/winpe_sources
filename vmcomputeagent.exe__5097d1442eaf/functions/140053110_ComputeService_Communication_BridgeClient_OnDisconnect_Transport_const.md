# ComputeService::Communication::BridgeClient::OnDisconnect(Transport const *)

- ea: `0x140053110`
- end: `0x14005322f`
- name: `?OnDisconnect@BridgeClient@Communication@ComputeService@@UEAAXPEBVTransport@@@Z`
- size: `287`
- prototype: `void __fastcall(ComputeService::Communication::BridgeClient *__hidden this, const struct Transport *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400016ec`
- `0x140005360`
- `0x14000aeec`
- `0x140053110`
- `0x1400fe010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400531e3`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400531e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140053165`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140053165`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005313b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005313b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140053207`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140053207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140053141`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140053141`

## pseudocode

```c
void __fastcall ComputeService::Communication::BridgeClient::OnDisconnect(
        ComputeService::Communication::BridgeClient *this,
        const struct Transport *a2)
{
  char v3; // di
  __int64 v4; // rcx
  __int64 v5; // rcx
  char v6; // [rsp+30h] [rbp-58h] BYREF
  __int64 v7; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-48h] BYREF
  char *v9; // [rsp+60h] [rbp-28h]
  __int64 v10; // [rsp+68h] [rbp-20h]

  v3 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 13);
  *((_DWORD *)this + 28) = GetCurrentThreadId();
  if ( *((_DWORD *)this + 30) != 5 )
  {
    *((_DWORD *)this + 30) = 0;
    v3 = 1;
  }
  *((_DWORD *)this + 28) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 13);
  v4 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v4 > 4u && (*(_QWORD *)(v4 + 16) & 4) != 0 && (*(_QWORD *)(v4 + 24) & 4LL) == *(_QWORD *)(v4 + 24) )
  {
    v6 = v3;
    v9 = &v6;
    v10 = 1;
    tlgWriteTransfer_EventWriteTransfer(v4, (int)&word_1401346D6, 0, 0, 3u, &v8);
  }
  v5 = *((_QWORD *)this + 23);
  v7 = 2;
  if ( !v5 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 16LL))(v5, &v7);
  if ( v3 )
    SubmitThreadpoolWork(*((PTP_WORK *)this + 24));
}

```

## disassembly

```asm
0x140053110  mov     [rsp+arg_8], rbx
0x140053115  mov     [rsp+arg_10], rsi
0x14005311a  push    rdi
0x14005311b  sub     rsp, 80h
0x140053122  mov     rax, cs:__security_cookie
0x140053129  xor     rax, rsp
0x14005312c  mov     [rsp+88h+var_18], rax
0x140053131  mov     rbx, rcx
0x140053134  xor     dil, dil
0x140053137  add     rcx, 68h ; 'h'; SRWLock
0x14005313b  call    cs:__imp_AcquireSRWLockExclusive
0x140053141  call    cs:__imp_GetCurrentThreadId
0x140053147  mov     [rbx+70h], eax
0x14005314a  cmp     dword ptr [rbx+78h], 5
0x14005314e  jz      short loc_14005315A
0x140053150  mov     dword ptr [rbx+78h], 0
0x140053157  mov     dil, 1
0x14005315a  lea     rcx, [rbx+68h]; SRWLock
0x14005315e  mov     dword ptr [rbx+70h], 0
0x140053165  call    cs:__imp_ReleaseSRWLockExclusive
0x14005316b  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140053170  mov     rcx, [rax+8]; int
0x140053174  mov     eax, [rcx]
0x140053176  cmp     eax, 4
0x140053179  jbe     short loc_1400531CE
0x14005317b  mov     rdx, [rcx+18h]
0x14005317f  mov     rax, [rcx+10h]
0x140053183  test    al, 4
0x140053185  jz      short loc_1400531CE
0x140053187  mov     rax, rdx
0x14005318a  and     eax, 4
0x14005318d  cmp     rax, rdx
0x140053190  jnz     short loc_1400531CE
0x140053192  lea     rax, [rsp+88h+var_58]
0x140053197  mov     [rsp+88h+var_58], dil
0x14005319c  mov     [rsp+88h+var_28], rax
0x1400531a1  lea     rdx, word_1401346D6; int
0x1400531a8  lea     rax, [rsp+88h+var_48]
0x1400531ad  mov     [rsp+88h+var_20], 1
0x1400531b6  mov     [rsp+88h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x1400531bb  xor     r9d, r9d; int
0x1400531be  xor     r8d, r8d; int
0x1400531c1  mov     [rsp+88h+var_68], 3; ULONG
0x1400531c9  call    _tlgWriteTransfer_EventWriteTransfer
0x1400531ce  mov     rcx, [rbx+0B8h]
0x1400531d5  mov     [rsp+88h+var_50], 2
0x1400531de  test    rcx, rcx
0x1400531e1  jnz     short loc_1400531EA
0x1400531e3  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1400531e9  int     3; Trap to Debugger
0x1400531ea  mov     rax, [rcx]
0x1400531ed  lea     rdx, [rsp+88h+var_50]
0x1400531f2  mov     rax, [rax+10h]
0x1400531f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400531fb  test    dil, dil
0x1400531fe  jz      short loc_14005320D
0x140053200  mov     rcx, [rbx+0C0h]; pwk
0x140053207  call    cs:__imp_SubmitThreadpoolWork
0x14005320d  mov     rcx, [rsp+88h+var_18]
0x140053212  xor     rcx, rsp; StackCookie
0x140053215  call    __security_check_cookie
0x14005321a  lea     r11, [rsp+88h+var_8]
0x140053222  mov     rbx, [r11+18h]
0x140053226  mov     rsi, [r11+20h]
0x14005322a  mov     rsp, r11
0x14005322d  pop     rdi
0x14005322e  retn
```
