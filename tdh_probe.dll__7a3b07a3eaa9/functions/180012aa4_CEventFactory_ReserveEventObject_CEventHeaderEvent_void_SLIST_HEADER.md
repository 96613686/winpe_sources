# CEventFactory::ReserveEventObject<CEventHeaderEvent>(void *,_SLIST_HEADER *)

- ea: `0x180012aa4`
- end: `0x180012b68`
- name: `??$ReserveEventObject@VCEventHeaderEvent@@@CEventFactory@@QEAAPEAVCEventBase@@PEAXPEAT_SLIST_HEADER@@@Z`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800126d4`
- `0x180012814`

## callees

- `0x180012aa4`
- `0x18001d488`
- `0x180020c74`
- `0x180020c98`
- `0x180021268`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180012abc`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180012abc`

## pseudocode

```c
__int64 __fastcall CEventFactory::ReserveEventObject<CEventHeaderEvent>(__int64 a1, void *a2, union _SLIST_HEADER *a3)
{
  PSLIST_ENTRY v5; // rax
  _QWORD *p_Next; // rbx
  __int64 v7; // rax
  CEventHeaderEvent *v9; // rax
  void *v10; // r8
  _QWORD *v11; // rcx

  v5 = InterlockedPopEntrySList(a3);
  p_Next = &v5->Next;
  if ( v5 )
  {
    v7 = *((_QWORD *)&v5[1].Next + 1);
    *(_WORD *)(v7 + 136) = 0;
    *(_QWORD *)(v7 + 160) = 0;
    return p_Next[3];
  }
  p_Next = operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( p_Next )
  {
    v9 = (CEventHeaderEvent *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
      v9 = CEventHeaderEvent::CEventHeaderEvent(v9, a2, v10);
    v11 = p_Next + 3;
    p_Next[3] = v9;
    if ( v9 )
    {
      *((_QWORD *)v9 + 18) = v11;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
      p_Next[2] = a3;
      return p_Next[3];
    }
    operator delete(p_Next);
  }
  return 0;
}

```

## disassembly

```asm
0x180012aa4  mov     [rsp+arg_0], rbx
0x180012aa9  mov     [rsp+arg_8], rsi
0x180012aae  push    rdi
0x180012aaf  sub     rsp, 20h
0x180012ab3  mov     rcx, r8; ListHead
0x180012ab6  mov     rdi, r8
0x180012ab9  mov     rsi, rdx
0x180012abc  call    cs:__imp_InterlockedPopEntrySList
0x180012ac2  mov     rbx, rax
0x180012ac5  test    rax, rax
0x180012ac8  jz      short loc_180012AF6
0x180012aca  mov     rax, [rax+18h]
0x180012ace  mov     word ptr [rax+88h], 0
0x180012ad7  mov     qword ptr [rax+0A0h], 0
0x180012ae2  mov     rax, [rbx+18h]
0x180012ae6  mov     rbx, [rsp+28h+arg_0]
0x180012aeb  mov     rsi, [rsp+28h+arg_8]
0x180012af0  add     rsp, 20h
0x180012af4  pop     rdi
0x180012af5  retn
0x180012af6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012afd  mov     ecx, 20h ; ' '; unsigned __int64
0x180012b02  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012b07  mov     rbx, rax
0x180012b0a  test    rax, rax
0x180012b0d  jnz     short loc_180012B13
0x180012b0f  xor     eax, eax
0x180012b11  jmp     short loc_180012AE6
0x180012b13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012b1a  mov     ecx, 0B8h; unsigned __int64
0x180012b1f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012b24  test    rax, rax
0x180012b27  jz      short loc_180012B5C
0x180012b29  mov     rdx, rsi; void *
0x180012b2c  mov     rcx, rax; this
0x180012b2f  call    ??0CEventHeaderEvent@@QEAA@PEAX0@Z; CEventHeaderEvent::CEventHeaderEvent(void *,void *)
0x180012b34  lea     rcx, [rbx+18h]
0x180012b38  mov     [rcx], rax
0x180012b3b  test    rax, rax
0x180012b3e  jz      short loc_180012B5E
0x180012b40  mov     [rax+90h], rcx
0x180012b47  mov     rcx, [rcx]
0x180012b4a  mov     rax, [rcx]
0x180012b4d  mov     rax, [rax+8]
0x180012b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b56  mov     [rbx+10h], rdi
0x180012b5a  jmp     short loc_180012AE2
0x180012b5c  jmp     short loc_180012B34
0x180012b5e  mov     rcx, rbx; Block
0x180012b61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b66  jmp     short loc_180012B0F
```
