# CLockedDoubleList::RemoveEntry(CListEntry * const)

- ea: `0x180038430`
- end: `0x1800384be`
- name: `?RemoveEntry@CLockedDoubleList@@QEAAXQEAVCListEntry@@@Z`
- size: `142`
- prototype: `void __fastcall(CLockedDoubleList *__hidden this, struct CListEntry *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180032744`
- `0x180053284`

## callees

- `0x180038430`
- `0x180054074`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038464`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038464`

## pseudocode

```c
void __fastcall CLockedDoubleList::RemoveEntry(CLockedDoubleList *this, struct CListEntry *const a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rax

  if ( *(_DWORD *)this
    || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFF | 0x10000000, 0) )
  {
    if ( (*(_DWORD *)this & 0xFFFFFFF) == (GetCurrentThreadId() & 0xFFFFFFF) )
      _InterlockedExchange((volatile __int32 *)this, *(_DWORD *)this + 0x10000000);
    else
      CSpinLock::_LockSpin(this);
  }
  v4 = (_QWORD *)*((_QWORD *)a2 + 1);
  v5 = *(_QWORD *)a2;
  *v4 = *(_QWORD *)a2;
  *(_QWORD *)(v5 + 8) = v4;
  _InterlockedExchange(
    (volatile __int32 *)this,
    ((*(_DWORD *)this - 0x10000000) & 0xF0000000) != 0 ? *(_DWORD *)this - 0x10000000 : 0);
}

```

## disassembly

```asm
0x180038430  mov     [rsp+arg_8], rbx
0x180038435  push    rdi
0x180038436  sub     rsp, 20h
0x18003843a  mov     eax, [rcx]
0x18003843c  mov     rdi, rdx
0x18003843f  mov     rbx, rcx
0x180038442  test    eax, eax
0x180038444  jnz     short loc_180038464
0x180038446  call    cs:__imp_GetCurrentThreadId
0x18003844c  mov     r8d, eax
0x18003844f  and     r8d, 0FFFFFFFh
0x180038456  bts     r8d, 1Ch
0x18003845b  xor     eax, eax
0x18003845d  lock cmpxchg [rbx], r8d
0x180038462  jz      short loc_18003848E
0x180038464  call    cs:__imp_GetCurrentThreadId
0x18003846a  mov     ecx, [rbx]
0x18003846c  and     eax, 0FFFFFFFh
0x180038471  and     ecx, 0FFFFFFFh
0x180038477  cmp     ecx, eax
0x180038479  jnz     short loc_180038486
0x18003847b  mov     eax, [rbx]
0x18003847d  add     eax, 10000000h
0x180038482  xchg    eax, [rbx]
0x180038484  jmp     short loc_18003848E
0x180038486  mov     rcx, rbx; this
0x180038489  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x18003848e  mov     rcx, [rdi+8]
0x180038492  mov     rax, [rdi]
0x180038495  mov     [rcx], rax
0x180038498  mov     [rax+8], rcx
0x18003849c  mov     edx, [rbx]
0x18003849e  add     edx, 0F0000000h
0x1800384a4  mov     eax, edx
0x1800384a6  and     eax, 0F0000000h
0x1800384ab  neg     eax
0x1800384ad  sbb     ecx, ecx
0x1800384af  and     ecx, edx
0x1800384b1  xchg    ecx, [rbx]
0x1800384b3  mov     rbx, [rsp+28h+arg_8]
0x1800384b8  add     rsp, 20h
0x1800384bc  pop     rdi
0x1800384bd  retn
```
