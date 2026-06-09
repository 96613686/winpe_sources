# ATL::AtlModuleGetClassObject(ATL::_ATL_MODULE *,_GUID const &,_GUID const &,void * *)

- ea: `0x180002780`
- end: `0x18000289d`
- name: `?AtlModuleGetClassObject@ATL@@YAJPEAU_ATL_MODULE@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `285`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004910`

## callees

- `0x180002780`
- `0x180006010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002841`
- `KERNEL32!LeaveCriticalSection` at `0x180002841`
- `KERNEL32!LeaveCriticalSection` at `0x18000508b`
- `KERNEL32!EnterCriticalSection` at `0x180002810`
- `KERNEL32!EnterCriticalSection` at `0x180002810`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleGetClassObject(
        struct ATL::_ATL_MODULE *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rdi
  unsigned int v8; // ebx
  _DWORD *v9; // rcx
  _QWORD *v10; // rsi
  __int64 v11; // rax

  v6 = qword_18000A280;
  if ( !qword_18000A280 )
    return 2147746065LL;
  if ( !a4 )
    return 2147500035LL;
  v8 = 0;
  *a4 = 0;
  while ( 1 )
  {
    v9 = *(_DWORD **)v6;
    if ( !*(_QWORD *)v6 )
      break;
    if ( *(_QWORD *)(v6 + 16)
      && a2->Data1 == *v9
      && *(_DWORD *)&a2->Data2 == v9[1]
      && *(_DWORD *)a2->Data4 == v9[2]
      && *(_DWORD *)&a2->Data4[4] == v9[3] )
    {
      v10 = (_QWORD *)(v6 + 32);
      if ( !*(_QWORD *)(v6 + 32) )
      {
        EnterCriticalSection(&CriticalSection);
        if ( !*v10 )
          v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v6 + 16))(
                 *(_QWORD *)(v6 + 24),
                 &IID_IUnknown,
                 v6 + 32);
        LeaveCriticalSection(&CriticalSection);
      }
      if ( *v10 )
        v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v10)(*v10, a3, a4);
      break;
    }
    v11 = 72;
    if ( _Module == 176 )
      v11 = 56;
    v6 += v11;
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return v8;
}

```

## disassembly

```asm
0x180002780  push    rbx
0x180002782  push    rsi
0x180002783  push    rdi
0x180002784  push    r14
0x180002786  push    r15
0x180002788  sub     rsp, 30h
0x18000278c  mov     r14, r9
0x18000278f  mov     r15, r8
0x180002792  mov     rdi, cs:qword_18000A280
0x180002799  test    rdi, rdi
0x18000279c  jnz     short loc_1800027A8
0x18000279e  mov     eax, 80040111h
0x1800027a3  jmp     loc_180002874
0x1800027a8  test    r14, r14
0x1800027ab  jnz     short loc_1800027B7
0x1800027ad  mov     eax, 80004003h
0x1800027b2  jmp     loc_180002874
0x1800027b7  xor     ebx, ebx
0x1800027b9  mov     [r9], rbx
0x1800027bc  mov     rcx, [rdi]
0x1800027bf  test    rcx, rcx
0x1800027c2  jz      loc_180002862
0x1800027c8  cmp     [rdi+10h], rbx
0x1800027cc  jz      loc_180002880
0x1800027d2  mov     eax, [rcx]
0x1800027d4  cmp     [rdx], eax
0x1800027d6  jnz     loc_180002880
0x1800027dc  mov     eax, [rcx+4]
0x1800027df  cmp     [rdx+4], eax
0x1800027e2  jnz     loc_180002880
0x1800027e8  mov     eax, [rcx+8]
0x1800027eb  cmp     [rdx+8], eax
0x1800027ee  jnz     loc_180002880
0x1800027f4  mov     eax, [rcx+0Ch]
0x1800027f7  cmp     [rdx+0Ch], eax
0x1800027fa  jnz     loc_180002880
0x180002800  lea     rsi, [rdi+20h]
0x180002804  cmp     [rsi], rbx
0x180002807  jnz     short loc_180002847
0x180002809  lea     rcx, CriticalSection; lpCriticalSection
0x180002810  call    cs:__imp_EnterCriticalSection
0x180002816  nop
0x180002817  cmp     qword ptr [rsi], 0
0x18000281b  jnz     short loc_18000283A
0x18000281d  mov     r8, rsi
0x180002820  lea     rdx, IID_IUnknown
0x180002827  mov     rcx, [rdi+18h]
0x18000282b  mov     rax, [rdi+10h]
0x18000282f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002834  mov     ebx, eax
0x180002836  mov     [rsp+58h+var_38], eax
0x18000283a  lea     rcx, CriticalSection; lpCriticalSection
0x180002841  call    cs:__imp_LeaveCriticalSection
0x180002847  mov     rcx, [rsi]
0x18000284a  test    rcx, rcx
0x18000284d  jz      short loc_180002862
0x18000284f  mov     rax, [rcx]
0x180002852  mov     r8, r14
0x180002855  mov     rdx, r15
0x180002858  mov     rax, [rax]
0x18000285b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002860  mov     ebx, eax
0x180002862  cmp     qword ptr [r14], 0
0x180002866  jnz     short loc_180002872
0x180002868  mov     eax, 80040111h
0x18000286d  test    ebx, ebx
0x18000286f  cmovz   ebx, eax
0x180002872  mov     eax, ebx
0x180002874  add     rsp, 30h
0x180002878  pop     r15
0x18000287a  pop     r14
0x18000287c  pop     rdi
0x18000287d  pop     rsi
0x18000287e  pop     rbx
0x18000287f  retn
0x180002880  mov     eax, 48h ; 'H'
0x180002885  lea     ecx, [rax-10h]
0x180002888  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180002892  cmovz   eax, ecx
0x180002895  add     rdi, rax
0x180002898  jmp     loc_1800027BC
0x180005076  push    rbp
0x180005078  sub     rsp, 20h
0x18000507c  mov     rbp, rdx
0x18000507f  lea     rcx, CriticalSection
0x180005086  add     rsp, 20h
0x18000508a  pop     rbp
0x18000508b  jmp     cs:__imp_LeaveCriticalSection
```
