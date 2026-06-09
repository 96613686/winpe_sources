# CLockedDoubleList::RemoveEntry(CListEntry * const)

- ea: `0x180036918`
- end: `0x1800369b3`
- name: `?RemoveEntry@CLockedDoubleList@@QEAAXQEAVCListEntry@@@Z`
- size: `155`
- prototype: `void __fastcall(CLockedDoubleList *__hidden this, struct CListEntry *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180036778`
- `0x1800367e4`

## callees

- `0x180036918`
- `0x180037b8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003692e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003692e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036952`

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
0x180036918  mov     [rsp+arg_8], rbx
0x18003691d  push    rdi
0x18003691e  sub     rsp, 20h
0x180036922  mov     eax, [rcx]
0x180036924  mov     rdi, rdx
0x180036927  mov     rbx, rcx
0x18003692a  test    eax, eax
0x18003692c  jnz     short loc_180036952
0x18003692e  call    cs:__imp_GetCurrentThreadId
0x180036935  nop     dword ptr [rax+rax+00h]
0x18003693a  mov     r8d, eax
0x18003693d  and     r8d, 0FFFFFFFh
0x180036944  bts     r8d, 1Ch
0x180036949  xor     eax, eax
0x18003694b  lock cmpxchg [rbx], r8d
0x180036950  jz      short loc_180036982
0x180036952  call    cs:__imp_GetCurrentThreadId
0x180036959  nop     dword ptr [rax+rax+00h]
0x18003695e  mov     ecx, [rbx]
0x180036960  and     eax, 0FFFFFFFh
0x180036965  and     ecx, 0FFFFFFFh
0x18003696b  cmp     ecx, eax
0x18003696d  jnz     short loc_18003697A
0x18003696f  mov     eax, [rbx]
0x180036971  add     eax, 10000000h
0x180036976  xchg    eax, [rbx]
0x180036978  jmp     short loc_180036982
0x18003697a  mov     rcx, rbx; this
0x18003697d  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x180036982  mov     rcx, [rdi+8]
0x180036986  mov     rax, [rdi]
0x180036989  mov     [rcx], rax
0x18003698c  mov     [rax+8], rcx
0x180036990  mov     edx, [rbx]
0x180036992  add     edx, 0F0000000h
0x180036998  mov     eax, edx
0x18003699a  and     eax, 0F0000000h
0x18003699f  neg     eax
0x1800369a1  sbb     ecx, ecx
0x1800369a3  and     ecx, edx
0x1800369a5  xchg    ecx, [rbx]
0x1800369a7  mov     rbx, [rsp+28h+arg_8]
0x1800369ac  add     rsp, 20h
0x1800369b0  pop     rdi
0x1800369b1  retn
```
