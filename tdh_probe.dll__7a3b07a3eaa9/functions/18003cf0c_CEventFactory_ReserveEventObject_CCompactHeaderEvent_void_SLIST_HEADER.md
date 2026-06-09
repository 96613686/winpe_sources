# CEventFactory::ReserveEventObject<CCompactHeaderEvent>(void *,_SLIST_HEADER *)

- ea: `0x18003cf0c`
- end: `0x18003cfeb`
- name: `??$ReserveEventObject@VCCompactHeaderEvent@@@CEventFactory@@QEAAPEAVCEventBase@@PEAXPEAT_SLIST_HEADER@@@Z`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800126d4`
- `0x180012814`

## callees

- `0x18001d440`
- `0x180020c74`
- `0x180020c98`
- `0x180021268`
- `0x18003cf0c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003cf24`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003cf24`

## pseudocode

```c
__int64 __fastcall CEventFactory::ReserveEventObject<CCompactHeaderEvent>(
        __int64 a1,
        void *a2,
        union _SLIST_HEADER *a3)
{
  PSLIST_ENTRY v5; // rax
  _QWORD *p_Next; // rbx
  CSystemTraceHeaderEvent *v8; // rcx
  void *v9; // r8
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rax

  v5 = InterlockedPopEntrySList(a3);
  p_Next = &v5->Next;
  if ( v5 )
  {
    v12 = *((_QWORD *)&v5[1].Next + 1);
    *(_WORD *)(v12 + 136) = 0;
    *(_QWORD *)(v12 + 160) = 0;
  }
  else
  {
    p_Next = operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !p_Next )
      return 0;
    v8 = (CSystemTraceHeaderEvent *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      CSystemTraceHeaderEvent::CSystemTraceHeaderEvent(v8, a2, v9);
      *(_DWORD *)(v10 + 172) = 6;
      *(_QWORD *)v10 = &CCompactHeaderEvent::`vftable';
    }
    else
    {
      v10 = 0;
    }
    v11 = p_Next + 3;
    p_Next[3] = v10;
    if ( !v10 )
    {
      operator delete(p_Next);
      return 0;
    }
    *(_QWORD *)(v10 + 144) = v11;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
    p_Next[2] = a3;
  }
  return p_Next[3];
}

```

## disassembly

```asm
0x18003cf0c  mov     [rsp+arg_0], rbx
0x18003cf11  mov     [rsp+arg_8], rsi
0x18003cf16  push    rdi
0x18003cf17  sub     rsp, 20h
0x18003cf1b  mov     rcx, r8; ListHead
0x18003cf1e  mov     rdi, r8
0x18003cf21  mov     rsi, rdx
0x18003cf24  call    cs:__imp_InterlockedPopEntrySList
0x18003cf2a  mov     rbx, rax
0x18003cf2d  test    rax, rax
0x18003cf30  jnz     loc_18003CFBF
0x18003cf36  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cf3d  lea     ecx, [rax+20h]; unsigned __int64
0x18003cf40  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003cf45  mov     rbx, rax
0x18003cf48  test    rax, rax
0x18003cf4b  jnz     short loc_18003CF54
0x18003cf4d  xor     eax, eax
0x18003cf4f  jmp     loc_18003CFDB
0x18003cf54  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cf5b  mov     ecx, 0B8h; unsigned __int64
0x18003cf60  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003cf65  mov     rcx, rax; this
0x18003cf68  test    rax, rax
0x18003cf6b  jz      short loc_18003CF8B
0x18003cf6d  mov     rdx, rsi; void *
0x18003cf70  call    ??0CSystemTraceHeaderEvent@@QEAA@PEAX0@Z; CSystemTraceHeaderEvent::CSystemTraceHeaderEvent(void *,void *)
0x18003cf75  lea     rdx, ??_7CCompactHeaderEvent@@6B@; const CCompactHeaderEvent::`vftable'
0x18003cf7c  mov     dword ptr [rcx+0ACh], 6
0x18003cf86  mov     [rcx], rdx
0x18003cf89  jmp     short loc_18003CF8D
0x18003cf8b  xor     ecx, ecx
0x18003cf8d  lea     rax, [rbx+18h]
0x18003cf91  mov     [rax], rcx
0x18003cf94  test    rcx, rcx
0x18003cf97  jnz     short loc_18003CFA3
0x18003cf99  mov     rcx, rbx; Block
0x18003cf9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003cfa1  jmp     short loc_18003CF4D
0x18003cfa3  mov     [rcx+90h], rax
0x18003cfaa  mov     rcx, [rax]
0x18003cfad  mov     rax, [rcx]
0x18003cfb0  mov     rax, [rax+8]
0x18003cfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfb9  mov     [rbx+10h], rdi
0x18003cfbd  jmp     short loc_18003CFD7
0x18003cfbf  mov     rax, [rax+18h]
0x18003cfc3  mov     word ptr [rax+88h], 0
0x18003cfcc  mov     qword ptr [rax+0A0h], 0
0x18003cfd7  mov     rax, [rbx+18h]
0x18003cfdb  mov     rbx, [rsp+28h+arg_0]
0x18003cfe0  mov     rsi, [rsp+28h+arg_8]
0x18003cfe5  add     rsp, 20h
0x18003cfe9  pop     rdi
0x18003cfea  retn
```
