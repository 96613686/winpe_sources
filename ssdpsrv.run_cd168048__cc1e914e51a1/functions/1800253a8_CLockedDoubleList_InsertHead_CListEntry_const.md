# CLockedDoubleList::InsertHead(CListEntry * const)

- ea: `0x1800253a8`
- end: `0x18002544a`
- name: `?InsertHead@CLockedDoubleList@@QEAAXQEAVCListEntry@@@Z`
- size: `162`
- prototype: `void __fastcall(CLockedDoubleList *__hidden this, struct CListEntry *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022dd4`
- `0x180037580`

## callees

- `0x1800253a8`
- `0x180037b8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800253be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800253e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800253be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800253e2`

## pseudocode

```c
void __fastcall CLockedDoubleList::InsertHead(CLockedDoubleList *this, struct CListEntry *const a2)
{
  __int64 v4; // rax

  if ( *(_DWORD *)this
    || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFF | 0x10000000, 0) )
  {
    if ( (*(_DWORD *)this & 0xFFFFFFF) == (GetCurrentThreadId() & 0xFFFFFFF) )
      _InterlockedExchange((volatile __int32 *)this, *(_DWORD *)this + 0x10000000);
    else
      CSpinLock::_LockSpin(this);
  }
  *((_QWORD *)a2 + 1) = (char *)this + 8;
  v4 = *((_QWORD *)this + 1);
  *(_QWORD *)a2 = v4;
  *(_QWORD *)(v4 + 8) = a2;
  *((_QWORD *)this + 1) = a2;
  _InterlockedExchange(
    (volatile __int32 *)this,
    ((*(_DWORD *)this - 0x10000000) & 0xF0000000) != 0 ? *(_DWORD *)this - 0x10000000 : 0);
}

```

## disassembly

```asm
0x1800253a8  mov     [rsp+arg_8], rbx
0x1800253ad  push    rdi
0x1800253ae  sub     rsp, 20h
0x1800253b2  mov     eax, [rcx]
0x1800253b4  mov     rdi, rdx
0x1800253b7  mov     rbx, rcx
0x1800253ba  test    eax, eax
0x1800253bc  jnz     short loc_1800253E2
0x1800253be  call    cs:__imp_GetCurrentThreadId
0x1800253c5  nop     dword ptr [rax+rax+00h]
0x1800253ca  mov     r8d, eax
0x1800253cd  and     r8d, 0FFFFFFFh
0x1800253d4  bts     r8d, 1Ch
0x1800253d9  xor     eax, eax
0x1800253db  lock cmpxchg [rbx], r8d
0x1800253e0  jz      short loc_180025412
0x1800253e2  call    cs:__imp_GetCurrentThreadId
0x1800253e9  nop     dword ptr [rax+rax+00h]
0x1800253ee  mov     ecx, [rbx]
0x1800253f0  and     eax, 0FFFFFFFh
0x1800253f5  and     ecx, 0FFFFFFFh
0x1800253fb  cmp     ecx, eax
0x1800253fd  jnz     short loc_18002540A
0x1800253ff  mov     eax, [rbx]
0x180025401  add     eax, 10000000h
0x180025406  xchg    eax, [rbx]
0x180025408  jmp     short loc_180025412
0x18002540a  mov     rcx, rbx; this
0x18002540d  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x180025412  lea     rcx, [rbx+8]
0x180025416  mov     [rdi+8], rcx
0x18002541a  mov     rax, [rcx]
0x18002541d  mov     [rdi], rax
0x180025420  mov     [rax+8], rdi
0x180025424  mov     [rcx], rdi
0x180025427  mov     edx, [rbx]
0x180025429  add     edx, 0F0000000h
0x18002542f  mov     eax, edx
0x180025431  and     eax, 0F0000000h
0x180025436  neg     eax
0x180025438  sbb     ecx, ecx
0x18002543a  and     ecx, edx
0x18002543c  xchg    ecx, [rbx]
0x18002543e  mov     rbx, [rsp+28h+arg_8]
0x180025443  add     rsp, 20h
0x180025447  pop     rdi
0x180025448  retn
```
