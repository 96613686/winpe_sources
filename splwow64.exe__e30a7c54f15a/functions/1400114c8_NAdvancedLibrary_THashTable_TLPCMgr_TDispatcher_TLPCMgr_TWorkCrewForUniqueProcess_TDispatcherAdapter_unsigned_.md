# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::Insert(TLPCMgr::TDispatcher *)

- ea: `0x1400114c8`
- end: `0x1400115ba`
- name: `?Insert@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@QEAAJPEAVTDispatcher@TLPCMgr@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(NAdvancedLibrary::THashTableBase *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14001140c`

## callees

- `0x140001b90`
- `0x140002198`
- `0x1400114c8`
- `0x140014394`
- `0x140016010`

## pseudocode

```c
__int64 __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::Insert(
        NAdvancedLibrary::THashTableBase *this,
        __int64 a2)
{
  struct NAdvancedLibrary::THashElementBase *v4; // rax
  struct NAdvancedLibrary::THashElementBase **v5; // r8
  struct NAdvancedLibrary::THashElementBase *v6; // rbx
  signed __int32 v7; // eax
  int inserted; // edi
  volatile signed __int32 *v9; // rdx
  signed __int32 v10; // r8d
  bool v12; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return (unsigned int)-2147024809;
  v4 = (struct NAdvancedLibrary::THashElementBase *)operator new(
                                                      0x28u,
                                                      (const struct std::nothrow_t *)&NCoreLibrary::nothrow);
  v6 = v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  *((_QWORD *)v4 + 1) = v4;
  *(_QWORD *)v4 = v4;
  *((_QWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 3) = -1;
  *((_QWORD *)v4 + 4) = a2;
  do
    v7 = *(_DWORD *)(a2 + 8);
  while ( v7 != 0x7FFFFFFF && v7 != _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 8), v7 + 1, v7) );
  v12 = 0;
  inserted = NAdvancedLibrary::THashTableBase::InsertElement(this, v6, v5, &v12);
  if ( inserted >= 0 )
  {
    if ( v12 )
      return (unsigned int)inserted;
    inserted = -2147467259;
  }
  v9 = (volatile signed __int32 *)*((_QWORD *)v6 + 4);
  if ( v9 )
  {
    do
      v10 = *((_DWORD *)v9 + 2);
    while ( v10 != 0x7FFFFFFF && v10 != _InterlockedCompareExchange(v9 + 2, v10 - 1, v10) );
    if ( v10 == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  operator delete(v6);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1400114c8  push    rbx
0x1400114ca  push    rsi
0x1400114cb  push    rdi
0x1400114cc  push    r14
0x1400114ce  sub     rsp, 28h
0x1400114d2  mov     rdi, rdx
0x1400114d5  mov     rsi, rcx
0x1400114d8  test    rdx, rdx
0x1400114db  jz      loc_1400115A9
0x1400114e1  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x1400114e8  mov     ecx, 28h ; '('; unsigned __int64
0x1400114ed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400114f2  mov     rbx, rax
0x1400114f5  test    rax, rax
0x1400114f8  jz      loc_1400115A2
0x1400114fe  mov     [rax+8], rax
0x140011502  mov     r14d, 7FFFFFFFh
0x140011508  mov     [rax], rax
0x14001150b  mov     qword ptr [rax+10h], 0
0x140011513  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x14001151b  mov     [rax+20h], rdi
0x14001151f  jmp     short loc_14001152B
0x140011521  lea     ecx, [rax+1]
0x140011524  lock cmpxchg [rdi+8], ecx
0x140011529  jz      short loc_140011533
0x14001152b  mov     eax, [rdi+8]
0x14001152e  cmp     eax, r14d
0x140011531  jnz     short loc_140011521
0x140011533  lea     r9, [rsp+48h+arg_8]; bool *
0x140011538  mov     [rsp+48h+arg_8], 0
0x14001153d  mov     rdx, rbx; struct NAdvancedLibrary::THashElementBase *
0x140011540  mov     rcx, rsi; this
0x140011543  call    ?InsertElement@THashTableBase@NAdvancedLibrary@@QEAAJPEAVTHashElementBase@2@PEAPEAV32@PEA_N@Z; NAdvancedLibrary::THashTableBase::InsertElement(NAdvancedLibrary::THashElementBase *,NAdvancedLibrary::THashElementBase * *,bool *)
0x140011548  mov     edi, eax
0x14001154a  test    eax, eax
0x14001154c  js      short loc_14001155A
0x14001154e  cmp     [rsp+48h+arg_8], 0
0x140011553  jnz     short loc_1400115AE
0x140011555  mov     edi, 80004005h
0x14001155a  mov     rdx, [rbx+20h]
0x14001155e  test    rdx, rdx
0x140011561  jz      short loc_140011593
0x140011563  jmp     short loc_140011573
0x140011565  lea     ecx, [r8-1]
0x140011569  mov     eax, r8d
0x14001156c  lock cmpxchg [rdx+8], ecx
0x140011571  jz      short loc_14001157C
0x140011573  mov     r8d, [rdx+8]
0x140011577  cmp     r8d, r14d
0x14001157a  jnz     short loc_140011565
0x14001157c  lea     eax, [r8-1]
0x140011580  test    eax, eax
0x140011582  jnz     short loc_140011593
0x140011584  mov     rax, [rdx]
0x140011587  mov     rcx, rdx
0x14001158a  mov     rax, [rax+8]
0x14001158e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011593  mov     edx, 28h ; '('
0x140011598  mov     rcx, rbx; Block
0x14001159b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400115a0  jmp     short loc_1400115AE
0x1400115a2  mov     edi, 8007000Eh
0x1400115a7  jmp     short loc_1400115AE
0x1400115a9  mov     edi, 80070057h
0x1400115ae  mov     eax, edi
0x1400115b0  add     rsp, 28h
0x1400115b4  pop     r14
0x1400115b6  pop     rdi
0x1400115b7  pop     rsi
0x1400115b8  pop     rbx
0x1400115b9  retn
```
