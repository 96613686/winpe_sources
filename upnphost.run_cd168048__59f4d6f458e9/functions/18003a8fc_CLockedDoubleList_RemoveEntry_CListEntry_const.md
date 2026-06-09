# CLockedDoubleList::RemoveEntry(CListEntry * const)

- ea: `0x18003a8fc`
- end: `0x18003a997`
- name: `?RemoveEntry@CLockedDoubleList@@QEAAXQEAVCListEntry@@@Z`
- size: `155`
- prototype: `void __fastcall(CLockedDoubleList *__hidden this, struct CListEntry *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180034578`
- `0x180056bd4`

## callees

- `0x18003a8fc`
- `0x1800579f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a912`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a936`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a912`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a936`

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
0x18003a8fc  mov     [rsp+arg_8], rbx
0x18003a901  push    rdi
0x18003a902  sub     rsp, 20h
0x18003a906  mov     eax, [rcx]
0x18003a908  mov     rdi, rdx
0x18003a90b  mov     rbx, rcx
0x18003a90e  test    eax, eax
0x18003a910  jnz     short loc_18003A936
0x18003a912  call    cs:__imp_GetCurrentThreadId
0x18003a919  nop     dword ptr [rax+rax+00h]
0x18003a91e  mov     r8d, eax
0x18003a921  and     r8d, 0FFFFFFFh
0x18003a928  bts     r8d, 1Ch
0x18003a92d  xor     eax, eax
0x18003a92f  lock cmpxchg [rbx], r8d
0x18003a934  jz      short loc_18003A966
0x18003a936  call    cs:__imp_GetCurrentThreadId
0x18003a93d  nop     dword ptr [rax+rax+00h]
0x18003a942  mov     ecx, [rbx]
0x18003a944  and     eax, 0FFFFFFFh
0x18003a949  and     ecx, 0FFFFFFFh
0x18003a94f  cmp     ecx, eax
0x18003a951  jnz     short loc_18003A95E
0x18003a953  mov     eax, [rbx]
0x18003a955  add     eax, 10000000h
0x18003a95a  xchg    eax, [rbx]
0x18003a95c  jmp     short loc_18003A966
0x18003a95e  mov     rcx, rbx; this
0x18003a961  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x18003a966  mov     rcx, [rdi+8]
0x18003a96a  mov     rax, [rdi]
0x18003a96d  mov     [rcx], rax
0x18003a970  mov     [rax+8], rcx
0x18003a974  mov     edx, [rbx]
0x18003a976  add     edx, 0F0000000h
0x18003a97c  mov     eax, edx
0x18003a97e  and     eax, 0F0000000h
0x18003a983  neg     eax
0x18003a985  sbb     ecx, ecx
0x18003a987  and     ecx, edx
0x18003a989  xchg    ecx, [rbx]
0x18003a98b  mov     rbx, [rsp+28h+arg_8]
0x18003a990  add     rsp, 20h
0x18003a994  pop     rdi
0x18003a995  retn
```
