# CLockedDoubleList::InsertHead(CListEntry * const)

- ea: `0x180023984`
- end: `0x180023a19`
- name: `?InsertHead@CLockedDoubleList@@QEAAXQEAVCListEntry@@@Z`
- size: `149`
- prototype: `void __fastcall(CLockedDoubleList *__hidden this, struct CListEntry *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800213d4`
- `0x180034a7c`

## callees

- `0x180023984`
- `0x180035058`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002399a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800239b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002399a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800239b8`

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
0x180023984  mov     [rsp+arg_8], rbx
0x180023989  push    rdi
0x18002398a  sub     rsp, 20h
0x18002398e  mov     eax, [rcx]
0x180023990  mov     rdi, rdx
0x180023993  mov     rbx, rcx
0x180023996  test    eax, eax
0x180023998  jnz     short loc_1800239B8
0x18002399a  call    cs:__imp_GetCurrentThreadId
0x1800239a0  mov     r8d, eax
0x1800239a3  and     r8d, 0FFFFFFFh
0x1800239aa  bts     r8d, 1Ch
0x1800239af  xor     eax, eax
0x1800239b1  lock cmpxchg [rbx], r8d
0x1800239b6  jz      short loc_1800239E2
0x1800239b8  call    cs:__imp_GetCurrentThreadId
0x1800239be  mov     ecx, [rbx]
0x1800239c0  and     eax, 0FFFFFFFh
0x1800239c5  and     ecx, 0FFFFFFFh
0x1800239cb  cmp     ecx, eax
0x1800239cd  jnz     short loc_1800239DA
0x1800239cf  mov     eax, [rbx]
0x1800239d1  add     eax, 10000000h
0x1800239d6  xchg    eax, [rbx]
0x1800239d8  jmp     short loc_1800239E2
0x1800239da  mov     rcx, rbx; this
0x1800239dd  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x1800239e2  lea     rcx, [rbx+8]
0x1800239e6  mov     [rdi+8], rcx
0x1800239ea  mov     rax, [rcx]
0x1800239ed  mov     [rdi], rax
0x1800239f0  mov     [rax+8], rdi
0x1800239f4  mov     [rcx], rdi
0x1800239f7  mov     edx, [rbx]
0x1800239f9  add     edx, 0F0000000h
0x1800239ff  mov     eax, edx
0x180023a01  and     eax, 0F0000000h
0x180023a06  neg     eax
0x180023a08  sbb     ecx, ecx
0x180023a0a  and     ecx, edx
0x180023a0c  xchg    ecx, [rbx]
0x180023a0e  mov     rbx, [rsp+28h+arg_8]
0x180023a13  add     rsp, 20h
0x180023a17  pop     rdi
0x180023a18  retn
```
