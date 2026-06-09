# Private::WorkItem<void>::WorkItem<void>(std::weak_ptr<Private::ThreadpoolImpl>)

- ea: `0x140022d60`
- end: `0x140022e55`
- name: `??0?$WorkItem@X@Private@@IEAA@V?$weak_ptr@UThreadpoolImpl@Private@@@std@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x1400206f8`
- `0x140020814`
- `0x14002b078`
- `0x14003cbcc`
- `0x14003cd0c`
- `0x14003ce4c`
- `0x140061c64`
- `0x140061d84`
- `0x14006ade8`
- `0x140085668`
- `0x140085784`

## callees

- `0x140006314`
- `0x140022d60`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x140022df4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x140022df4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140022e05`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140022e05`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Private::WorkItem<void>::WorkItem<void>(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rax
  volatile signed __int32 *v5; // rcx

  *(_BYTE *)(a1 + 24) = 1;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)a1 = &Private::WorkItemBase::`vftable';
  *(_DWORD *)(a1 + 28) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  if ( a2[1] )
  {
    *(_QWORD *)(a1 + 32) = *a2;
    v4 = a2[1];
    *(_QWORD *)(a1 + 40) = v4;
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 12));
  }
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 96) = &Private::FutureData<void>::`vftable';
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 104) = &LockBox<Private::FutureData<void>::ResultInfo,4294967295>::`vftable';
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  memset_0((void *)(a1 + 120), 0, 0x40u);
  __ExceptionPtrCreate((void *)(a1 + 152));
  *(_QWORD *)(a1 + 176) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 112));
  *(_QWORD *)a1 = &Private::WorkItem<void>::`vftable'{for `Private::WorkItemBase'};
  *(_QWORD *)(a1 + 96) = &Private::WorkItem<void>::`vftable'{for `Private::FutureData<void>'};
  v5 = (volatile signed __int32 *)a2[1];
  if ( v5 && _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  return a1;
}

```

## disassembly

```asm
0x140022d60  mov     [rsp+arg_0], rbx
0x140022d65  mov     [rsp+arg_8], rsi
0x140022d6a  push    rdi
0x140022d6b  sub     rsp, 20h
0x140022d6f  xor     esi, esi
0x140022d71  mov     byte ptr [rcx+18h], 1
0x140022d75  mov     [rcx+8], rsi
0x140022d79  lea     rax, ??_7WorkItemBase@Private@@6B@; const Private::WorkItemBase::`vftable'
0x140022d80  mov     [rcx+10h], rsi
0x140022d84  mov     rdi, rdx
0x140022d87  mov     [rcx], rax
0x140022d8a  mov     rbx, rcx
0x140022d8d  mov     [rcx+1Ch], esi
0x140022d90  mov     [rcx+20h], rsi
0x140022d94  mov     [rcx+28h], rsi
0x140022d98  cmp     [rdx+8], rsi
0x140022d9c  jz      short loc_140022DB1
0x140022d9e  mov     rax, [rdx]
0x140022da1  mov     [rcx+20h], rax
0x140022da5  mov     rax, [rdx+8]
0x140022da9  mov     [rcx+28h], rax
0x140022dad  lock inc dword ptr [rax+0Ch]
0x140022db1  lea     rax, ??_7?$FutureData@X@Private@@6B@; const Private::FutureData<void>::`vftable'
0x140022db8  mov     [rcx+30h], rsi
0x140022dbc  mov     [rcx+60h], rax
0x140022dc0  xor     edx, edx; Val
0x140022dc2  lea     rax, ??_7?$LockBox@UResultInfo@?$FutureData@X@Private@@$0PPPPPPPP@@@6B@; const LockBox<Private::FutureData<void>::ResultInfo,4294967295>::`vftable'
0x140022dc9  mov     [rcx+38h], rsi
0x140022dcd  mov     [rcx+68h], rax
0x140022dd1  mov     [rcx+40h], rsi
0x140022dd5  mov     [rcx+48h], esi
0x140022dd8  lea     r8d, [rdx+40h]; Size
0x140022ddc  mov     [rcx+50h], rsi
0x140022de0  mov     [rcx+58h], rsi
0x140022de4  add     rcx, 78h ; 'x'; void *
0x140022de8  call    memset_0
0x140022ded  lea     rcx, [rbx+98h]
0x140022df4  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x140022dfa  lea     rcx, [rbx+70h]; SRWLock
0x140022dfe  mov     [rbx+0B0h], rsi
0x140022e05  call    cs:__imp_InitializeSRWLock
0x140022e0b  lea     rax, ??_7?$WorkItem@X@Private@@6BWorkItemBase@1@@; const Private::WorkItem<void>::`vftable'{for `Private::WorkItemBase'}
0x140022e12  mov     [rbx], rax
0x140022e15  lea     rax, ??_7?$WorkItem@X@Private@@6B?$FutureData@X@1@@; const Private::WorkItem<void>::`vftable'{for `Private::FutureData<void>'}
0x140022e1c  mov     [rbx+60h], rax
0x140022e20  mov     rcx, [rdi+8]
0x140022e24  test    rcx, rcx
0x140022e27  jz      short loc_140022E42
0x140022e29  or      eax, 0FFFFFFFFh
0x140022e2c  lock xadd [rcx+0Ch], eax
0x140022e31  cmp     eax, 1
0x140022e34  jnz     short loc_140022E42
0x140022e36  mov     rax, [rcx]
0x140022e39  mov     rax, [rax+8]
0x140022e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022e42  mov     rsi, [rsp+28h+arg_8]
0x140022e47  mov     rax, rbx
0x140022e4a  mov     rbx, [rsp+28h+arg_0]
0x140022e4f  add     rsp, 20h
0x140022e53  pop     rdi
0x140022e54  retn
```
