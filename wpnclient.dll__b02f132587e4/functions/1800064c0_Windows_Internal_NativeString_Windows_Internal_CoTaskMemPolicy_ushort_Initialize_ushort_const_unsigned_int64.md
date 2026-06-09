# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x1800064c0`
- end: `0x1800066a6`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `486`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005f10`
- `0x1800061f0`
- `0x180016e44`
- `0x18001f044`

## callees

- `0x1800064c0`
- `0x1800074d0`
- `0x180013b80`
- `0x180025174`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006675`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180006675`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000654c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000654c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  _WORD *v3; // rbx
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r9
  _WORD *v8; // rax
  int v9; // r15d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rcx
  _WORD *v12; // rax
  _QWORD *v14; // rcx
  __int64 v15; // r9
  unsigned __int64 v16; // rsi
  LPVOID v17; // rax
  unsigned __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v3 = (_WORD *)a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
    return 0;
  }
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a2 + 2 * v5) );
  if ( a3 == -1 )
  {
    a3 = v5;
  }
  else if ( a3 < v5 )
  {
    v5 = a3;
  }
  v6 = a3 + 1;
  if ( a3 + 1 < a3 )
    return 2147942934LL;
  v7 = *(_QWORD *)(a1 + 16);
  if ( v7 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount();
    if ( *v14 )
      v7 = v14[1] + 1LL;
    else
      v7 = 0;
    v14[2] = v7;
  }
  if ( v7 )
  {
    v9 = 0;
    if ( v6 > v7 )
    {
      v18 = 0;
      v9 = ULongLongMult(v7, a2, &v18);
      if ( v9 >= 0 )
      {
        v16 = v18;
        if ( v18 - v15 > 0x800 )
          v16 = v15 + 2048;
        if ( v6 > v16 )
          v16 = v6;
        v17 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v16);
        if ( !v17 )
          return 2147942414LL;
        *(_QWORD *)(a1 + 16) = v16;
        *(_QWORD *)a1 = v17;
        goto LABEL_14;
      }
    }
  }
  else
  {
    if ( !is_mul_ok(v6, 2u) )
      return 2147942934LL;
    v8 = CoTaskMemAlloc(2 * v6);
    if ( v8 )
    {
      *(_QWORD *)(a1 + 16) = v6;
      v9 = 0;
      *(_QWORD *)a1 = v8;
      *v8 = 0;
LABEL_14:
      if ( v6 )
      {
        v10 = *(_WORD **)a1;
        if ( v5 > 0x7FFFFFFE || v6 > 0x7FFFFFFF )
        {
          *v10 = 0;
        }
        else
        {
          v11 = v5;
          do
          {
            if ( !v11 )
              break;
            if ( !*v3 )
              break;
            *v10++ = *v3++;
            --v11;
            --v6;
          }
          while ( v6 );
          v12 = v10 - 1;
          if ( v6 )
            v12 = v10;
          *v12 = 0;
        }
      }
      *(_QWORD *)(a1 + 8) = v5;
      return (unsigned int)v9;
    }
    v9 = -2147024882;
  }
  if ( v9 >= 0 )
    goto LABEL_14;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800064c0  push    rbx
0x1800064c2  push    r12
0x1800064c4  push    r14
0x1800064c6  sub     rsp, 30h
0x1800064ca  mov     rbx, rdx
0x1800064cd  mov     r14, rcx
0x1800064d0  test    rdx, rdx
0x1800064d3  jz      loc_180006696
0x1800064d9  mov     [rsp+48h+arg_0], rbp
0x1800064de  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800064e5  mov     [rsp+48h+var_20], rdi
0x1800064ea  nop     word ptr [rax+rax+00h]
0x1800064f0  inc     rbp
0x1800064f3  cmp     word ptr [rdx+rbp*2], 0
0x1800064f8  jnz     short loc_1800064F0
0x1800064fa  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800064fe  jnz     loc_1800065F9
0x180006504  mov     r8, rbp
0x180006507  lea     rdi, [r8+1]
0x18000650b  cmp     rdi, r8
0x18000650e  jb      loc_1800065E5
0x180006514  mov     r9, [rcx+10h]
0x180006518  xor     r12d, r12d
0x18000651b  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18000651f  jz      loc_180006605
0x180006525  mov     [rsp+48h+arg_10], rsi
0x18000652a  mov     [rsp+48h+var_28], r15
0x18000652f  test    r9, r9
0x180006532  jnz     loc_180006624
0x180006538  mov     eax, 2
0x18000653d  mul     rdi
0x180006540  test    rdx, rdx
0x180006543  jnz     loc_1800065EC
0x180006549  mov     rcx, rax; cb
0x18000654c  call    cs:__imp_CoTaskMemAlloc
0x180006552  test    rax, rax
0x180006555  jz      short loc_180006567
0x180006557  mov     [r14+10h], rdi
0x18000655b  mov     r15d, r12d
0x18000655e  mov     [r14], rax
0x180006561  mov     [rax], r12w
0x180006565  jmp     short loc_180006572
0x180006567  mov     r15d, 8007000Eh
0x18000656d  test    r15d, r15d
0x180006570  js      short loc_1800065C4
0x180006572  test    rdi, rdi
0x180006575  jz      short loc_1800065C0
0x180006577  mov     rdx, [r14]
0x18000657a  cmp     rbp, 7FFFFFFEh
0x180006581  ja      short loc_1800065F3
0x180006583  cmp     rdi, 7FFFFFFFh
0x18000658a  ja      short loc_1800065F3
0x18000658c  mov     rcx, rbp
0x18000658f  nop
0x180006590  test    rcx, rcx
0x180006593  jz      short loc_1800065B1
0x180006595  movzx   eax, word ptr [rbx]
0x180006598  test    ax, ax
0x18000659b  jz      short loc_1800065B1
0x18000659d  mov     [rdx], ax
0x1800065a0  add     rbx, 2
0x1800065a4  add     rdx, 2
0x1800065a8  dec     rcx
0x1800065ab  sub     rdi, 1
0x1800065af  jnz     short loc_180006590
0x1800065b1  test    rdi, rdi
0x1800065b4  lea     rax, [rdx-2]
0x1800065b8  cmovnz  rax, rdx
0x1800065bc  mov     [rax], r12w
0x1800065c0  mov     [r14+8], rbp
0x1800065c4  mov     eax, r15d
0x1800065c7  mov     rsi, [rsp+48h+arg_10]
0x1800065cc  mov     r15, [rsp+48h+var_28]
0x1800065d1  mov     rbp, [rsp+48h+arg_0]
0x1800065d6  mov     rdi, [rsp+48h+var_20]
0x1800065db  add     rsp, 30h
0x1800065df  pop     r14
0x1800065e1  pop     r12
0x1800065e3  pop     rbx
0x1800065e4  retn
0x1800065e5  mov     eax, 80070216h
0x1800065ea  jmp     short loc_1800065D1
0x1800065ec  mov     eax, 80070216h
0x1800065f1  jmp     short loc_1800065C7
0x1800065f3  mov     [rdx], r12w
0x1800065f7  jmp     short loc_1800065C0
0x1800065f9  cmp     r8, rbp
0x1800065fc  cmovb   rbp, r8
0x180006600  jmp     loc_180006507
0x180006605  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000660a  cmp     [rcx], r12
0x18000660d  jz      short loc_180006618
0x18000660f  mov     r9, [rcx+8]
0x180006613  inc     r9
0x180006616  jmp     short loc_18000661B
0x180006618  mov     r9, r12
0x18000661b  mov     [rcx+10h], r9
0x18000661f  jmp     loc_180006525
0x180006624  mov     r15d, r12d
0x180006627  cmp     rdi, r9
0x18000662a  jbe     loc_18000656D
0x180006630  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x180006635  mov     [rsp+48h+arg_8], r12
0x18000663a  mov     rcx, r9; unsigned __int64
0x18000663d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180006642  mov     r15d, eax
0x180006645  test    eax, eax
0x180006647  js      loc_18000656D
0x18000664d  mov     rsi, [rsp+48h+arg_8]
0x180006652  mov     rax, rsi
0x180006655  sub     rax, r9
0x180006658  cmp     rax, 800h
0x18000665e  jbe     short loc_180006667
0x180006660  lea     rsi, [r9+800h]
0x180006667  mov     rcx, [r14]; pv
0x18000666a  cmp     rdi, rsi
0x18000666d  cmova   rsi, rdi
0x180006671  lea     rdx, [rsi+rsi]; cb
0x180006675  call    cs:__imp_CoTaskMemRealloc
0x18000667b  test    rax, rax
0x18000667e  jz      short loc_18000668C
0x180006680  mov     [r14+10h], rsi
0x180006684  mov     [r14], rax
0x180006687  jmp     loc_180006572
0x18000668c  mov     eax, 8007000Eh
0x180006691  jmp     loc_1800065C7
0x180006696  xor     r12d, r12d
0x180006699  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000669e  mov     eax, r12d
0x1800066a1  jmp     loc_1800065DB
```
