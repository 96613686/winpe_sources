# CLockedDoubleList::RemoveEntry(CListEntry * const)

- ea: `0x180033e50`
- end: `0x180033ede`
- name: `?RemoveEntry@CLockedDoubleList@@QEAAXQEAVCListEntry@@@Z`
- size: `142`
- prototype: `void __fastcall(CLockedDoubleList *__hidden this, struct CListEntry *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180033cbc`
- `0x180033d28`

## callees

- `0x180033e50`
- `0x180035058`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033e66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033e84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033e66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033e84`

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
0x180033e50  mov     [rsp+arg_8], rbx
0x180033e55  push    rdi
0x180033e56  sub     rsp, 20h
0x180033e5a  mov     eax, [rcx]
0x180033e5c  mov     rdi, rdx
0x180033e5f  mov     rbx, rcx
0x180033e62  test    eax, eax
0x180033e64  jnz     short loc_180033E84
0x180033e66  call    cs:__imp_GetCurrentThreadId
0x180033e6c  mov     r8d, eax
0x180033e6f  and     r8d, 0FFFFFFFh
0x180033e76  bts     r8d, 1Ch
0x180033e7b  xor     eax, eax
0x180033e7d  lock cmpxchg [rbx], r8d
0x180033e82  jz      short loc_180033EAE
0x180033e84  call    cs:__imp_GetCurrentThreadId
0x180033e8a  mov     ecx, [rbx]
0x180033e8c  and     eax, 0FFFFFFFh
0x180033e91  and     ecx, 0FFFFFFFh
0x180033e97  cmp     ecx, eax
0x180033e99  jnz     short loc_180033EA6
0x180033e9b  mov     eax, [rbx]
0x180033e9d  add     eax, 10000000h
0x180033ea2  xchg    eax, [rbx]
0x180033ea4  jmp     short loc_180033EAE
0x180033ea6  mov     rcx, rbx; this
0x180033ea9  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x180033eae  mov     rcx, [rdi+8]
0x180033eb2  mov     rax, [rdi]
0x180033eb5  mov     [rcx], rax
0x180033eb8  mov     [rax+8], rcx
0x180033ebc  mov     edx, [rbx]
0x180033ebe  add     edx, 0F0000000h
0x180033ec4  mov     eax, edx
0x180033ec6  and     eax, 0F0000000h
0x180033ecb  neg     eax
0x180033ecd  sbb     ecx, ecx
0x180033ecf  and     ecx, edx
0x180033ed1  xchg    ecx, [rbx]
0x180033ed3  mov     rbx, [rsp+28h+arg_8]
0x180033ed8  add     rsp, 20h
0x180033edc  pop     rdi
0x180033edd  retn
```
