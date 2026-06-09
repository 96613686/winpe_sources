# ComputeService::Communication::BridgeClient::~BridgeClient(void)

- ea: `0x14004efec`
- end: `0x14004f205`
- name: `??1BridgeClient@Communication@ComputeService@@QEAA@XZ`
- size: `537`
- prototype: `void __fastcall(ComputeService::Communication::BridgeClient *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008b80`
- `0x14000999c`
- `0x14000b4fc`

## callees

- `0x14004efec`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004f02a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004f02a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14004f00c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14004f00c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x14004f04c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x14004f04c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14004f059`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14004f059`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004f012`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004f012`

## pseudocode

```c
void __fastcall ComputeService::Communication::BridgeClient::~BridgeClient(
        ComputeService::Communication::BridgeClient *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rbx
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 *v7; // rbx
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx

  *(_QWORD *)this = &ComputeService::Communication::BridgeClient::`vftable';
  AcquireSRWLockExclusive((PSRWLOCK)this + 13);
  GetCurrentThreadId();
  *((_DWORD *)this + 30) = 5;
  *((_DWORD *)this + 28) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 13);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
  CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 25), 0, 0);
  CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 25));
  v3 = *((_QWORD *)this + 23);
  if ( v3 )
  {
    LOBYTE(v2) = v3 != (_QWORD)this + 128;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, v2);
    *((_QWORD *)this + 23) = 0;
  }
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 12);
  if ( v4 )
  {
    if ( !_InterlockedDecrement(v4 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( !_InterlockedDecrement(v4 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 10);
  if ( v5 )
  {
    if ( !_InterlockedDecrement(v5 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( !_InterlockedDecrement(v5 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 8);
  if ( v6 )
  {
    if ( !_InterlockedDecrement(v6 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( !_InterlockedDecrement(v6 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = (volatile signed __int32 *)*((_QWORD *)this + 6);
  if ( v7 )
  {
    if ( !_InterlockedDecrement(v7 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( !_InterlockedDecrement(v7 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v8 )
  {
    if ( !_InterlockedDecrement(v8 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( !_InterlockedDecrement(v8 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v9 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( v9 && !_InterlockedDecrement(v9 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
    if ( !_InterlockedDecrement(v9 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
  }
}

```

## disassembly

```asm
0x14004efec  mov     [rsp+arg_8], rbx
0x14004eff1  mov     [rsp+arg_10], rsi
0x14004eff6  push    rdi
0x14004eff7  sub     rsp, 20h
0x14004effb  mov     rdi, rcx
0x14004effe  lea     rax, ??_7BridgeClient@Communication@ComputeService@@6B@; const ComputeService::Communication::BridgeClient::`vftable'
0x14004f005  mov     [rcx], rax
0x14004f008  add     rcx, 68h ; 'h'; SRWLock
0x14004f00c  call    cs:__imp_AcquireSRWLockExclusive
0x14004f012  call    cs:__imp_GetCurrentThreadId
0x14004f018  mov     dword ptr [rdi+78h], 5
0x14004f01f  mov     dword ptr [rdi+70h], 0
0x14004f026  lea     rcx, [rdi+68h]; SRWLock
0x14004f02a  call    cs:__imp_ReleaseSRWLockExclusive
0x14004f030  mov     rcx, [rdi+18h]
0x14004f034  mov     rax, [rcx]
0x14004f037  mov     rax, [rax+30h]
0x14004f03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f040  xor     r8d, r8d; pvCleanupContext
0x14004f043  xor     edx, edx; fCancelPendingCallbacks
0x14004f045  mov     rcx, [rdi+0C8h]; ptpcg
0x14004f04c  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x14004f052  mov     rcx, [rdi+0C8h]; ptpcg
0x14004f059  call    cs:__imp_CloseThreadpoolCleanupGroup
0x14004f05f  lea     rbx, [rdi+80h]
0x14004f066  mov     rcx, [rbx+38h]
0x14004f06a  test    rcx, rcx
0x14004f06d  jz      short loc_14004F089
0x14004f06f  mov     rax, [rcx]
0x14004f072  cmp     rcx, rbx
0x14004f075  setnz   dl
0x14004f078  mov     rax, [rax+20h]
0x14004f07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f081  mov     qword ptr [rbx+38h], 0
0x14004f089  mov     rbx, [rdi+60h]
0x14004f08d  or      esi, 0FFFFFFFFh
0x14004f090  test    rbx, rbx
0x14004f093  jz      short loc_14004F0C8
0x14004f095  mov     eax, esi
0x14004f097  lock xadd [rbx+8], eax
0x14004f09c  add     eax, esi
0x14004f09e  jnz     short loc_14004F0C8
0x14004f0a0  mov     rax, [rbx]
0x14004f0a3  mov     rcx, rbx
0x14004f0a6  mov     rax, [rax]
0x14004f0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f0ae  mov     eax, esi
0x14004f0b0  lock xadd [rbx+0Ch], eax
0x14004f0b5  add     eax, esi
0x14004f0b7  jnz     short loc_14004F0C8
0x14004f0b9  mov     rax, [rbx]
0x14004f0bc  mov     rcx, rbx
0x14004f0bf  mov     rax, [rax+8]
0x14004f0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f0c8  mov     rbx, [rdi+50h]
0x14004f0cc  test    rbx, rbx
0x14004f0cf  jz      short loc_14004F104
0x14004f0d1  mov     eax, esi
0x14004f0d3  lock xadd [rbx+8], eax
0x14004f0d8  add     eax, esi
0x14004f0da  jnz     short loc_14004F104
0x14004f0dc  mov     rax, [rbx]
0x14004f0df  mov     rcx, rbx
0x14004f0e2  mov     rax, [rax]
0x14004f0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f0ea  mov     eax, esi
0x14004f0ec  lock xadd [rbx+0Ch], eax
0x14004f0f1  add     eax, esi
0x14004f0f3  jnz     short loc_14004F104
0x14004f0f5  mov     rax, [rbx]
0x14004f0f8  mov     rcx, rbx
0x14004f0fb  mov     rax, [rax+8]
0x14004f0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f104  mov     rbx, [rdi+40h]
0x14004f108  test    rbx, rbx
0x14004f10b  jz      short loc_14004F140
0x14004f10d  mov     eax, esi
0x14004f10f  lock xadd [rbx+8], eax
0x14004f114  add     eax, esi
0x14004f116  jnz     short loc_14004F140
0x14004f118  mov     rax, [rbx]
0x14004f11b  mov     rcx, rbx
0x14004f11e  mov     rax, [rax]
0x14004f121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f126  mov     eax, esi
0x14004f128  lock xadd [rbx+0Ch], eax
0x14004f12d  add     eax, esi
0x14004f12f  jnz     short loc_14004F140
0x14004f131  mov     rax, [rbx]
0x14004f134  mov     rcx, rbx
0x14004f137  mov     rax, [rax+8]
0x14004f13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f140  mov     rbx, [rdi+30h]
0x14004f144  test    rbx, rbx
0x14004f147  jz      short loc_14004F17C
0x14004f149  mov     eax, esi
0x14004f14b  lock xadd [rbx+8], eax
0x14004f150  add     eax, esi
0x14004f152  jnz     short loc_14004F17C
0x14004f154  mov     rax, [rbx]
0x14004f157  mov     rcx, rbx
0x14004f15a  mov     rax, [rax]
0x14004f15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f162  mov     eax, esi
0x14004f164  lock xadd [rbx+0Ch], eax
0x14004f169  add     eax, esi
0x14004f16b  jnz     short loc_14004F17C
0x14004f16d  mov     rax, [rbx]
0x14004f170  mov     rcx, rbx
0x14004f173  mov     rax, [rax+8]
0x14004f177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f17c  mov     rbx, [rdi+20h]
0x14004f180  test    rbx, rbx
0x14004f183  jz      short loc_14004F1B8
0x14004f185  mov     eax, esi
0x14004f187  lock xadd [rbx+8], eax
0x14004f18c  add     eax, esi
0x14004f18e  jnz     short loc_14004F1B8
0x14004f190  mov     rax, [rbx]
0x14004f193  mov     rcx, rbx
0x14004f196  mov     rax, [rax]
0x14004f199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f19e  mov     eax, esi
0x14004f1a0  lock xadd [rbx+0Ch], eax
0x14004f1a5  add     eax, esi
0x14004f1a7  jnz     short loc_14004F1B8
0x14004f1a9  mov     rax, [rbx]
0x14004f1ac  mov     rcx, rbx
0x14004f1af  mov     rax, [rax+8]
0x14004f1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f1b8  mov     rbx, [rdi+10h]
0x14004f1bc  test    rbx, rbx
0x14004f1bf  jz      short loc_14004F1F5
0x14004f1c1  mov     eax, esi
0x14004f1c3  lock xadd [rbx+8], eax
0x14004f1c8  add     eax, esi
0x14004f1ca  jnz     short loc_14004F1F5
0x14004f1cc  mov     rax, [rbx]
0x14004f1cf  mov     rcx, rbx
0x14004f1d2  mov     rax, [rax]
0x14004f1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f1da  mov     eax, esi
0x14004f1dc  lock xadd [rbx+0Ch], eax
0x14004f1e1  add     eax, esi
0x14004f1e3  jnz     short loc_14004F1F5
0x14004f1e5  mov     rax, [rbx]
0x14004f1e8  mov     rcx, rbx
0x14004f1eb  mov     rax, [rax+8]
0x14004f1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f1f4  nop
0x14004f1f5  mov     rbx, [rsp+28h+arg_8]
0x14004f1fa  mov     rsi, [rsp+28h+arg_10]
0x14004f1ff  add     rsp, 20h
0x14004f203  pop     rdi
0x14004f204  retn
```
