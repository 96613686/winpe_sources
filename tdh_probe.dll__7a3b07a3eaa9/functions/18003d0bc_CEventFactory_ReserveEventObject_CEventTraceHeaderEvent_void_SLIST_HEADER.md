# CEventFactory::ReserveEventObject<CEventTraceHeaderEvent>(void *,_SLIST_HEADER *)

- ea: `0x18003d0bc`
- end: `0x18003d17c`
- name: `??$ReserveEventObject@VCEventTraceHeaderEvent@@@CEventFactory@@QEAAPEAVCEventBase@@PEAXPEAT_SLIST_HEADER@@@Z`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800126d4`
- `0x180012814`

## callees

- `0x180020c74`
- `0x180020c98`
- `0x180021268`
- `0x18003d0bc`
- `0x18003d290`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003d0d4`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003d0d4`

## pseudocode

```c
__int64 __fastcall CEventFactory::ReserveEventObject<CEventTraceHeaderEvent>(
        __int64 a1,
        void *a2,
        union _SLIST_HEADER *a3)
{
  PSLIST_ENTRY v5; // rax
  _QWORD *p_Next; // rbx
  CEventTraceHeaderEvent *v8; // rax
  void *v9; // r8
  _QWORD *v10; // rcx
  __int64 v11; // rax

  v5 = InterlockedPopEntrySList(a3);
  p_Next = &v5->Next;
  if ( v5 )
  {
    v11 = *((_QWORD *)&v5[1].Next + 1);
    *(_WORD *)(v11 + 136) = 0;
    *(_QWORD *)(v11 + 160) = 0;
  }
  else
  {
    p_Next = operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !p_Next )
      return 0;
    v8 = (CEventTraceHeaderEvent *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
      v8 = CEventTraceHeaderEvent::CEventTraceHeaderEvent(v8, a2, v9);
    v10 = p_Next + 3;
    p_Next[3] = v8;
    if ( !v8 )
    {
      operator delete(p_Next);
      return 0;
    }
    *((_QWORD *)v8 + 18) = v10;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
    p_Next[2] = a3;
  }
  return p_Next[3];
}

```

## disassembly

```asm
0x18003d0bc  mov     [rsp+arg_0], rbx
0x18003d0c1  mov     [rsp+arg_8], rsi
0x18003d0c6  push    rdi
0x18003d0c7  sub     rsp, 20h
0x18003d0cb  mov     rcx, r8; ListHead
0x18003d0ce  mov     rdi, r8
0x18003d0d1  mov     rsi, rdx
0x18003d0d4  call    cs:__imp_InterlockedPopEntrySList
0x18003d0da  mov     rbx, rax
0x18003d0dd  test    rax, rax
0x18003d0e0  jnz     short loc_18003D150
0x18003d0e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d0e9  lea     ecx, [rax+20h]; unsigned __int64
0x18003d0ec  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003d0f1  mov     rbx, rax
0x18003d0f4  test    rax, rax
0x18003d0f7  jnz     short loc_18003D0FD
0x18003d0f9  xor     eax, eax
0x18003d0fb  jmp     short loc_18003D16C
0x18003d0fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d104  mov     ecx, 0B8h; unsigned __int64
0x18003d109  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003d10e  test    rax, rax
0x18003d111  jz      short loc_18003D11E
0x18003d113  mov     rdx, rsi; void *
0x18003d116  mov     rcx, rax; this
0x18003d119  call    ??0CEventTraceHeaderEvent@@QEAA@PEAX0@Z; CEventTraceHeaderEvent::CEventTraceHeaderEvent(void *,void *)
0x18003d11e  lea     rcx, [rbx+18h]
0x18003d122  mov     [rcx], rax
0x18003d125  test    rax, rax
0x18003d128  jnz     short loc_18003D134
0x18003d12a  mov     rcx, rbx; Block
0x18003d12d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d132  jmp     short loc_18003D0F9
0x18003d134  mov     [rax+90h], rcx
0x18003d13b  mov     rcx, [rcx]
0x18003d13e  mov     rax, [rcx]
0x18003d141  mov     rax, [rax+8]
0x18003d145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d14a  mov     [rbx+10h], rdi
0x18003d14e  jmp     short loc_18003D168
0x18003d150  mov     rax, [rax+18h]
0x18003d154  mov     word ptr [rax+88h], 0
0x18003d15d  mov     qword ptr [rax+0A0h], 0
0x18003d168  mov     rax, [rbx+18h]
0x18003d16c  mov     rbx, [rsp+28h+arg_0]
0x18003d171  mov     rsi, [rsp+28h+arg_8]
0x18003d176  add     rsp, 20h
0x18003d17a  pop     rdi
0x18003d17b  retn
```
