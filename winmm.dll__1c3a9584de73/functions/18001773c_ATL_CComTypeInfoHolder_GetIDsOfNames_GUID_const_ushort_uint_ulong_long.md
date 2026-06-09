# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x18001773c`
- end: `0x180017811`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `213`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017730`

## callees

- `0x180016da4`
- `0x18001773c`
- `0x18001a805`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        unsigned int a5,
        int *a6)
{
  __int64 result; // rax
  struct ITypeInfo *v9; // r15
  __int64 v10; // rbp
  _WORD *v11; // r14
  __int64 v12; // rsi
  int v13; // edi

  result = ATL::CComTypeInfoHolder::EnsureTI(this, a5);
  v9 = qword_180025078;
  if ( qword_180025078 )
  {
    v10 = qword_180025088;
    if ( qword_180025088 && a4 == 1 )
    {
      v11 = *a3;
      if ( *a3 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
      }
      else
      {
        LODWORD(v12) = 0;
      }
      v13 = dword_180025090;
      while ( --v13 >= 0 )
      {
        if ( (_DWORD)v12 == *(_DWORD *)(v10 + 16LL * v13 + 8)
          && !memcmp_0(*(const void **)(v10 + 16LL * v13), v11, 2LL * *(int *)(v10 + 16LL * v13 + 8)) )
        {
          *a6 = *(_DWORD *)(v10 + 16LL * v13 + 12);
          return 0;
        }
      }
    }
    return ((__int64 (__fastcall *)(struct ITypeInfo *, unsigned __int16 **, _QWORD, int *))v9->lpVtbl->GetIDsOfNames)(
             v9,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x18001773c  push    rbx
0x18001773e  push    rbp
0x18001773f  push    rsi
0x180017740  push    rdi
0x180017741  push    r12
0x180017743  push    r13
0x180017745  push    r14
0x180017747  push    r15
0x180017749  sub     rsp, 38h
0x18001774d  mov     edx, [rsp+78h+arg_20]; unsigned int
0x180017754  mov     r12d, r9d
0x180017757  mov     r13, r8
0x18001775a  call    ?EnsureTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::EnsureTI(ulong)
0x18001775f  mov     r15, cs:qword_180025078
0x180017766  xor     edx, edx
0x180017768  test    r15, r15
0x18001776b  jz      loc_180017800
0x180017771  mov     rbp, cs:qword_180025088
0x180017778  test    rbp, rbp
0x18001777b  jz      short loc_1800177E3
0x18001777d  cmp     r12d, 1
0x180017781  jnz     short loc_1800177E3
0x180017783  mov     r14, [r13+0]
0x180017787  test    r14, r14
0x18001778a  jnz     short loc_180017790
0x18001778c  mov     esi, edx
0x18001778e  jmp     short loc_18001779E
0x180017790  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017794  inc     rsi
0x180017797  cmp     [r14+rsi*2], dx
0x18001779c  jnz     short loc_180017794
0x18001779e  mov     edi, cs:dword_180025090
0x1800177a4  dec     edi
0x1800177a6  test    edi, edi
0x1800177a8  js      short loc_1800177E3
0x1800177aa  movsxd  rbx, edi
0x1800177ad  add     rbx, rbx
0x1800177b0  cmp     esi, [rbp+rbx*8+8]
0x1800177b4  jnz     short loc_1800177A4
0x1800177b6  movsxd  r8, dword ptr [rbp+rbx*8+8]
0x1800177bb  mov     rdx, r14; Buf2
0x1800177be  mov     rcx, [rbp+rbx*8+0]; Buf1
0x1800177c3  add     r8, r8; Size
0x1800177c6  call    memcmp_0
0x1800177cb  xor     edx, edx
0x1800177cd  test    eax, eax
0x1800177cf  jnz     short loc_1800177A4
0x1800177d1  mov     rax, [rsp+78h+arg_28]
0x1800177d9  mov     ecx, [rbp+rbx*8+0Ch]
0x1800177dd  mov     [rax], ecx
0x1800177df  mov     eax, edx
0x1800177e1  jmp     short loc_180017800
0x1800177e3  mov     rax, [r15]
0x1800177e6  mov     r8d, r12d
0x1800177e9  mov     r9, [rsp+78h+arg_28]
0x1800177f1  mov     rdx, r13
0x1800177f4  mov     rcx, r15
0x1800177f7  mov     rax, [rax+50h]
0x1800177fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017800  add     rsp, 38h
0x180017804  pop     r15
0x180017806  pop     r14
0x180017808  pop     r13
0x18001780a  pop     r12
0x18001780c  pop     rdi
0x18001780d  pop     rsi
0x18001780e  pop     rbp
0x18001780f  pop     rbx
0x180017810  retn
```
