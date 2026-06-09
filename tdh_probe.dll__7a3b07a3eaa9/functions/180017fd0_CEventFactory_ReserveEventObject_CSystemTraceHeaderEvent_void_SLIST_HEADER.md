# CEventFactory::ReserveEventObject<CSystemTraceHeaderEvent>(void *,_SLIST_HEADER *)

- ea: `0x180017fd0`
- end: `0x180018090`
- name: `??$ReserveEventObject@VCSystemTraceHeaderEvent@@@CEventFactory@@QEAAPEAVCEventBase@@PEAXPEAT_SLIST_HEADER@@@Z`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800126d4`
- `0x180012814`

## callees

- `0x180017fd0`
- `0x18001d440`
- `0x180020c74`
- `0x180020c98`
- `0x180021268`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180017fe8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180017fe8`

## pseudocode

```c
__int64 __fastcall CEventFactory::ReserveEventObject<CSystemTraceHeaderEvent>(
        __int64 a1,
        void *a2,
        union _SLIST_HEADER *a3)
{
  PSLIST_ENTRY v5; // rax
  _QWORD *p_Next; // rbx
  CSystemTraceHeaderEvent *v8; // rax
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
    v8 = (CSystemTraceHeaderEvent *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
      v8 = CSystemTraceHeaderEvent::CSystemTraceHeaderEvent(v8, a2, v9);
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
0x180017fd0  mov     [rsp+arg_0], rbx
0x180017fd5  mov     [rsp+arg_8], rsi
0x180017fda  push    rdi
0x180017fdb  sub     rsp, 20h
0x180017fdf  mov     rcx, r8; ListHead
0x180017fe2  mov     rdi, r8
0x180017fe5  mov     rsi, rdx
0x180017fe8  call    cs:__imp_InterlockedPopEntrySList
0x180017fee  mov     rbx, rax
0x180017ff1  test    rax, rax
0x180017ff4  jnz     short loc_180018064
0x180017ff6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017ffd  lea     ecx, [rax+20h]; unsigned __int64
0x180018000  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018005  mov     rbx, rax
0x180018008  test    rax, rax
0x18001800b  jnz     short loc_180018011
0x18001800d  xor     eax, eax
0x18001800f  jmp     short loc_180018080
0x180018011  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018018  mov     ecx, 0B8h; unsigned __int64
0x18001801d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018022  test    rax, rax
0x180018025  jz      short loc_180018032
0x180018027  mov     rdx, rsi; void *
0x18001802a  mov     rcx, rax; this
0x18001802d  call    ??0CSystemTraceHeaderEvent@@QEAA@PEAX0@Z; CSystemTraceHeaderEvent::CSystemTraceHeaderEvent(void *,void *)
0x180018032  lea     rcx, [rbx+18h]
0x180018036  mov     [rcx], rax
0x180018039  test    rax, rax
0x18001803c  jnz     short loc_180018048
0x18001803e  mov     rcx, rbx; Block
0x180018041  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018046  jmp     short loc_18001800D
0x180018048  mov     [rax+90h], rcx
0x18001804f  mov     rcx, [rcx]
0x180018052  mov     rax, [rcx]
0x180018055  mov     rax, [rax+8]
0x180018059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001805e  mov     [rbx+10h], rdi
0x180018062  jmp     short loc_18001807C
0x180018064  mov     rax, [rax+18h]
0x180018068  mov     word ptr [rax+88h], 0
0x180018071  mov     qword ptr [rax+0A0h], 0
0x18001807c  mov     rax, [rbx+18h]
0x180018080  mov     rbx, [rsp+28h+arg_0]
0x180018085  mov     rsi, [rsp+28h+arg_8]
0x18001808a  add     rsp, 20h
0x18001808e  pop     rdi
0x18001808f  retn
```
