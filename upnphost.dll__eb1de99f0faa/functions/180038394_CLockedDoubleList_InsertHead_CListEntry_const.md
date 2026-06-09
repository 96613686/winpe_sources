# CLockedDoubleList::InsertHead(CListEntry * const)

- ea: `0x180038394`
- end: `0x180038429`
- name: `?InsertHead@CLockedDoubleList@@QEAAXQEAVCListEntry@@@Z`
- size: `149`
- prototype: `void __fastcall(CLockedDoubleList *__hidden this, struct CListEntry *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800306a8`
- `0x1800327b0`

## callees

- `0x180038394`
- `0x180054074`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383c8`

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
0x180038394  mov     [rsp+arg_8], rbx
0x180038399  push    rdi
0x18003839a  sub     rsp, 20h
0x18003839e  mov     eax, [rcx]
0x1800383a0  mov     rdi, rdx
0x1800383a3  mov     rbx, rcx
0x1800383a6  test    eax, eax
0x1800383a8  jnz     short loc_1800383C8
0x1800383aa  call    cs:__imp_GetCurrentThreadId
0x1800383b0  mov     r8d, eax
0x1800383b3  and     r8d, 0FFFFFFFh
0x1800383ba  bts     r8d, 1Ch
0x1800383bf  xor     eax, eax
0x1800383c1  lock cmpxchg [rbx], r8d
0x1800383c6  jz      short loc_1800383F2
0x1800383c8  call    cs:__imp_GetCurrentThreadId
0x1800383ce  mov     ecx, [rbx]
0x1800383d0  and     eax, 0FFFFFFFh
0x1800383d5  and     ecx, 0FFFFFFFh
0x1800383db  cmp     ecx, eax
0x1800383dd  jnz     short loc_1800383EA
0x1800383df  mov     eax, [rbx]
0x1800383e1  add     eax, 10000000h
0x1800383e6  xchg    eax, [rbx]
0x1800383e8  jmp     short loc_1800383F2
0x1800383ea  mov     rcx, rbx; this
0x1800383ed  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x1800383f2  lea     rcx, [rbx+8]
0x1800383f6  mov     [rdi+8], rcx
0x1800383fa  mov     rax, [rcx]
0x1800383fd  mov     [rdi], rax
0x180038400  mov     [rax+8], rdi
0x180038404  mov     [rcx], rdi
0x180038407  mov     edx, [rbx]
0x180038409  add     edx, 0F0000000h
0x18003840f  mov     eax, edx
0x180038411  and     eax, 0F0000000h
0x180038416  neg     eax
0x180038418  sbb     ecx, ecx
0x18003841a  and     ecx, edx
0x18003841c  xchg    ecx, [rbx]
0x18003841e  mov     rbx, [rsp+28h+arg_8]
0x180038423  add     rsp, 20h
0x180038427  pop     rdi
0x180038428  retn
```
