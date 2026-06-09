# CLockedDoubleList::InsertHead(CListEntry * const)

- ea: `0x18003a80c`
- end: `0x18003a8ae`
- name: `?InsertHead@CLockedDoubleList@@QEAAXQEAVCListEntry@@@Z`
- size: `162`
- prototype: `void __fastcall(CLockedDoubleList *__hidden this, struct CListEntry *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003222c`
- `0x180034548`

## callees

- `0x18003a80c`
- `0x1800579f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a846`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a846`

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
0x18003a80c  mov     [rsp+arg_8], rbx
0x18003a811  push    rdi
0x18003a812  sub     rsp, 20h
0x18003a816  mov     eax, [rcx]
0x18003a818  mov     rdi, rdx
0x18003a81b  mov     rbx, rcx
0x18003a81e  test    eax, eax
0x18003a820  jnz     short loc_18003A846
0x18003a822  call    cs:__imp_GetCurrentThreadId
0x18003a829  nop     dword ptr [rax+rax+00h]
0x18003a82e  mov     r8d, eax
0x18003a831  and     r8d, 0FFFFFFFh
0x18003a838  bts     r8d, 1Ch
0x18003a83d  xor     eax, eax
0x18003a83f  lock cmpxchg [rbx], r8d
0x18003a844  jz      short loc_18003A876
0x18003a846  call    cs:__imp_GetCurrentThreadId
0x18003a84d  nop     dword ptr [rax+rax+00h]
0x18003a852  mov     ecx, [rbx]
0x18003a854  and     eax, 0FFFFFFFh
0x18003a859  and     ecx, 0FFFFFFFh
0x18003a85f  cmp     ecx, eax
0x18003a861  jnz     short loc_18003A86E
0x18003a863  mov     eax, [rbx]
0x18003a865  add     eax, 10000000h
0x18003a86a  xchg    eax, [rbx]
0x18003a86c  jmp     short loc_18003A876
0x18003a86e  mov     rcx, rbx; this
0x18003a871  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x18003a876  lea     rcx, [rbx+8]
0x18003a87a  mov     [rdi+8], rcx
0x18003a87e  mov     rax, [rcx]
0x18003a881  mov     [rdi], rax
0x18003a884  mov     [rax+8], rdi
0x18003a888  mov     [rcx], rdi
0x18003a88b  mov     edx, [rbx]
0x18003a88d  add     edx, 0F0000000h
0x18003a893  mov     eax, edx
0x18003a895  and     eax, 0F0000000h
0x18003a89a  neg     eax
0x18003a89c  sbb     ecx, ecx
0x18003a89e  and     ecx, edx
0x18003a8a0  xchg    ecx, [rbx]
0x18003a8a2  mov     rbx, [rsp+28h+arg_8]
0x18003a8a7  add     rsp, 20h
0x18003a8ab  pop     rdi
0x18003a8ac  retn
```
