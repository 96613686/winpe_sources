# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180006418`
- end: `0x180006508`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `240`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001210`

## callees

- `0x180001330`
- `0x180006418`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000649f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000649f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064ca`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  const struct _GUID *v6; // r10
  unsigned int v8; // ebx
  __int64 *v9; // r8
  unsigned __int64 v10; // r9
  __int64 v11; // rdi
  _QWORD *v12; // rsi

  v6 = a2;
  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  v9 = (__int64 *)qword_1800153C0;
  v10 = qword_1800153C8;
  while ( (unsigned __int64)v9 < v10 )
  {
    v11 = *v9;
    if ( *v9 && *(_QWORD *)(v11 + 16) && (unsigned int)InlineIsEqualGUID(v6, *(_QWORD *)v11) )
    {
      v12 = (_QWORD *)(v11 + 32);
      if ( !*(_QWORD *)(v11 + 32) )
      {
        EnterCriticalSection(&CriticalSection);
        if ( !*v12 )
          v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v11 + 16))(
                 *(_QWORD *)(v11 + 24),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 v11 + 32);
        LeaveCriticalSection(&CriticalSection);
      }
      if ( *v12 )
        v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v12)(*v12, a3, a4);
      break;
    }
    ++v9;
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return v8;
}

```

## disassembly

```asm
0x180006418  push    rbx
0x18000641a  push    rbp
0x18000641b  push    rsi
0x18000641c  push    rdi
0x18000641d  push    r14
0x18000641f  sub     rsp, 20h
0x180006423  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000642a  mov     r14, r9
0x18000642d  mov     rbp, r8
0x180006430  mov     r10, rdx
0x180006433  jnz     short loc_18000643F
0x180006435  mov     eax, 8000FFFFh
0x18000643a  jmp     loc_1800064FD
0x18000643f  test    r14, r14
0x180006442  jnz     short loc_18000644E
0x180006444  mov     eax, 80004003h
0x180006449  jmp     loc_1800064FD
0x18000644e  mov     qword ptr [r9], 0
0x180006455  xor     ebx, ebx
0x180006457  mov     r8, cs:qword_1800153C0
0x18000645e  mov     r9, cs:qword_1800153C8
0x180006465  jmp     short loc_180006488
0x180006467  mov     rdi, [r8]
0x18000646a  test    rdi, rdi
0x18000646d  jz      short loc_180006484
0x18000646f  cmp     [rdi+10h], rbx
0x180006473  jz      short loc_180006484
0x180006475  mov     rdx, [rdi]
0x180006478  mov     rcx, r10
0x18000647b  call    InlineIsEqualGUID
0x180006480  test    eax, eax
0x180006482  jnz     short loc_18000648F
0x180006484  add     r8, 8
0x180006488  cmp     r8, r9
0x18000648b  jb      short loc_180006467
0x18000648d  jmp     short loc_1800064EB
0x18000648f  lea     rsi, [rdi+20h]
0x180006493  cmp     [rsi], rbx
0x180006496  jnz     short loc_1800064D0
0x180006498  lea     rcx, CriticalSection; lpCriticalSection
0x18000649f  call    cs:__imp_EnterCriticalSection
0x1800064a5  cmp     [rsi], rbx
0x1800064a8  jnz     short loc_1800064C3
0x1800064aa  mov     rcx, [rdi+18h]
0x1800064ae  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800064b5  mov     rax, [rdi+10h]
0x1800064b9  mov     r8, rsi
0x1800064bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c1  mov     ebx, eax
0x1800064c3  lea     rcx, CriticalSection; lpCriticalSection
0x1800064ca  call    cs:__imp_LeaveCriticalSection
0x1800064d0  mov     rcx, [rsi]
0x1800064d3  test    rcx, rcx
0x1800064d6  jz      short loc_1800064EB
0x1800064d8  mov     rax, [rcx]
0x1800064db  mov     r8, r14
0x1800064de  mov     rdx, rbp
0x1800064e1  mov     rax, [rax]
0x1800064e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e9  mov     ebx, eax
0x1800064eb  cmp     qword ptr [r14], 0
0x1800064ef  jnz     short loc_1800064FB
0x1800064f1  test    ebx, ebx
0x1800064f3  mov     eax, 80040111h
0x1800064f8  cmovz   ebx, eax
0x1800064fb  mov     eax, ebx
0x1800064fd  add     rsp, 20h
0x180006501  pop     r14
0x180006503  pop     rdi
0x180006504  pop     rsi
0x180006505  pop     rbp
0x180006506  pop     rbx
0x180006507  retn
```
