# CLogConfigurableFilter::AddClause(tagLOG_FILTER_RULE *,ushort const *,ushort const *,ushort const *,ILogContext *)

- ea: `0x180025630`
- end: `0x180025822`
- name: `?AddClause@CLogConfigurableFilter@@IEAAHPEAUtagLOG_FILTER_RULE@@PEBG11PEAVILogContext@@@Z`
- size: `498`
- prototype: `int(CLogConfigurableFilter *__hidden this, struct tagLOG_FILTER_RULE *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct ILogContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180025ce8`

## callees

- `0x180001144`
- `0x18001fe2c`
- `0x180025630`
- `0x180025978`
- `0x1800264cc`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025689`
- `msvcrt!_wcsicmp` at `0x180025689`

## pseudocode

```c
__int64 __fastcall CLogConfigurableFilter::AddClause(
        unsigned __int64 this,
        struct tagLOG_FILTER_RULE *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct ILogContext *a6)
{
  unsigned int v9; // r14d
  _QWORD *v10; // rbx
  int i; // edi
  struct ILogContext *v12; // rdi
  __int64 v13; // rdi
  int v14; // ecx
  _QWORD *v15; // rsi
  __int64 j; // rdx
  unsigned int v17; // r8d
  unsigned int v18; // edx
  __int64 k; // rdi
  bool v20; // zf
  unsigned int v22; // [rsp+24h] [rbp-44h]
  unsigned __int64 v23; // [rsp+70h] [rbp+8h] BYREF

  v23 = this;
  v9 = 0;
  v10 = 0;
  for ( i = 0; (unsigned __int64)i < 7; ++i )
  {
    if ( !_wcsicmp(a4, (&off_18002B750)[2 * i]) )
    {
      v22 = *((_DWORD *)&off_18002B750 + 4 * i + 2);
      LODWORD(v23) = 0;
      v12 = a6;
      if ( !(*(unsigned int (__fastcall **)(struct ILogContext *, const unsigned __int16 *, unsigned __int64 *))(*(_QWORD *)a6 + 40LL))(
              a6,
              a3,
              &v23) )
        break;
      v13 = (*(__int64 (__fastcall **)(struct ILogContext *, _QWORD))(*(_QWORD *)v12 + 48LL))(v12, (unsigned int)v23);
      this = *(unsigned int *)(v13 + 520);
      if ( (_DWORD)this )
      {
        v14 = this - 1;
        if ( v14 && v14 != 2 )
        {
          this = 0;
LABEL_11:
          if ( !(_DWORD)this )
            break;
        }
        v10 = operator new(0x18u);
        if ( v10 )
        {
          *(_OWORD *)v10 = 0;
          v10[2] = 0;
          *(_DWORD *)v10 = v23;
          *((_DWORD *)v10 + 1) = v22;
          *((_DWORD *)v10 + 2) = *(_DWORD *)(v13 + 520);
          if ( CLogConfigurableFilter::StoreClauseData(
                 (CLogConfigurableFilter *)this,
                 a5,
                 (struct tagLOG_FILTER_CLAUSE *)v10) )
          {
            v15 = (_QWORD *)((char *)a2 + 8);
            for ( j = 0; ; j = (unsigned int)(j + 1) )
            {
              v17 = *((_DWORD *)a2 + 4);
              if ( (unsigned int)j >= v17 )
                break;
              if ( *(_QWORD **)(*v15 + 8 * j) == v10 )
                goto LABEL_26;
            }
            v18 = 0;
            for ( k = 0; ; k = (unsigned int)(k + 1) )
            {
              v20 = (_DWORD)k == v17;
              if ( (unsigned int)k >= v17 )
                break;
              if ( !*(_QWORD *)(*v15 + 8 * k) )
              {
                v18 = k;
                v20 = (_DWORD)k == v17;
                break;
              }
            }
            if ( v20 )
            {
              if ( !(unsigned int)CPtrList<tagLOG_OUTPUT_STACK *>::SetSize((char *)a2 + 8, v17 + 1) )
                break;
              v18 = k;
            }
            this = v18;
            *(_QWORD *)(*v15 + 8LL * v18) = v10;
LABEL_26:
            v9 = 1;
          }
        }
        break;
      }
      if ( v22 > 1 )
        break;
      this = 1;
      goto LABEL_11;
    }
  }
  if ( !v9 && v10 )
    CLogConfigurableFilter::DestroyClause((CLogConfigurableFilter *)this, (struct tagLOG_FILTER_CLAUSE *)v10);
  return v9;
}

```

## disassembly

```asm
0x180025630  mov     rax, rsp
0x180025633  mov     [rax+10h], rbx
0x180025637  mov     [rax+18h], rsi
0x18002563b  mov     [rax+8], rcx
0x18002563f  push    rdi
0x180025640  push    r12
0x180025642  push    r13
0x180025644  push    r14
0x180025646  push    r15
0x180025648  sub     rsp, 40h
0x18002564c  mov     r15, r9
0x18002564f  mov     r12, r8
0x180025652  mov     r13, rdx
0x180025655  xor     r14d, r14d
0x180025658  mov     [rax-40h], r14d
0x18002565c  xor     ebx, ebx
0x18002565e  mov     [rax-38h], rbx
0x180025662  mov     [rax-44h], ebx
0x180025665  xor     edi, edi
0x180025667  lea     rax, off_18002B750; "="
0x18002566e  mov     [rsp+68h+var_3C], edi
0x180025672  movsxd  rsi, edi
0x180025675  cmp     rsi, 7
0x180025679  jnb     loc_1800257F2
0x18002567f  add     rsi, rsi
0x180025682  mov     rdx, [rax+rsi*8]; String2
0x180025686  mov     rcx, r15; String1
0x180025689  call    cs:__imp__wcsicmp
0x180025690  nop     dword ptr [rax+rax+00h]
0x180025695  test    eax, eax
0x180025697  jnz     loc_1800257EB
0x18002569d  lea     rax, off_18002B750; "="
0x1800256a4  mov     eax, [rax+rsi*8+8]
0x1800256a8  lea     rcx, [rsp+68h+var_44]
0x1800256ad  mov     [rcx], eax
0x1800256af  mov     dword ptr [rsp+68h+arg_0], 0
0x1800256b7  mov     rdi, [rsp+68h+arg_28]
0x1800256bf  mov     rax, [rdi]
0x1800256c2  lea     r8, [rsp+68h+arg_0]
0x1800256c7  mov     rdx, r12
0x1800256ca  mov     rcx, rdi
0x1800256cd  mov     rax, [rax+28h]
0x1800256d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256d6  test    eax, eax
0x1800256d8  jz      loc_1800257F2
0x1800256de  mov     rax, [rdi]
0x1800256e1  mov     edx, dword ptr [rsp+68h+arg_0]
0x1800256e5  mov     rcx, rdi
0x1800256e8  mov     rax, [rax+30h]
0x1800256ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256f1  mov     rdi, rax
0x1800256f4  mov     ecx, [rax+208h]
0x1800256fa  test    ecx, ecx
0x1800256fc  jz      short loc_18002570C
0x1800256fe  sub     ecx, 1
0x180025701  jz      short loc_180025724
0x180025703  cmp     ecx, 2
0x180025706  jz      short loc_180025724
0x180025708  xor     ecx, ecx
0x18002570a  jmp     short loc_18002571C
0x18002570c  cmp     [rsp+68h+var_44], 1
0x180025711  ja      loc_1800257F2
0x180025717  mov     ecx, 1
0x18002571c  test    ecx, ecx
0x18002571e  jz      loc_1800257F2
0x180025724  mov     ecx, 18h; Size
0x180025729  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002572e  mov     rbx, rax
0x180025731  test    rax, rax
0x180025734  jz      short loc_180025742
0x180025736  xorps   xmm0, xmm0
0x180025739  xor     eax, eax
0x18002573b  movups  xmmword ptr [rbx], xmm0
0x18002573e  mov     [rbx+10h], rax
0x180025742  mov     [rsp+68h+var_38], rbx
0x180025747  test    rbx, rbx
0x18002574a  jz      loc_1800257F2
0x180025750  mov     eax, dword ptr [rsp+68h+arg_0]
0x180025754  mov     [rbx], eax
0x180025756  mov     eax, [rsp+68h+var_44]
0x18002575a  mov     [rbx+4], eax
0x18002575d  mov     eax, [rdi+208h]
0x180025763  mov     [rbx+8], eax
0x180025766  mov     r8, rbx; struct tagLOG_FILTER_CLAUSE *
0x180025769  mov     rdx, [rsp+68h+arg_20]; unsigned __int16 *
0x180025771  call    ?StoreClauseData@CLogConfigurableFilter@@IEAAHPEBGPEAUtagLOG_FILTER_CLAUSE@@@Z; CLogConfigurableFilter::StoreClauseData(ushort const *,tagLOG_FILTER_CLAUSE *)
0x180025776  test    eax, eax
0x180025778  jz      short loc_1800257F2
0x18002577a  lea     rsi, [r13+8]
0x18002577e  mov     [rsp+68h+var_48], 0
0x180025786  xor     edx, edx
0x180025788  mov     [rsp+68h+var_48], edx
0x18002578c  mov     r8d, [rsi+8]
0x180025790  cmp     edx, r8d
0x180025793  jnb     short loc_1800257A2
0x180025795  mov     rax, [rsi]
0x180025798  cmp     [rax+rdx*8], rbx
0x18002579c  jz      short loc_1800257DA
0x18002579e  inc     edx
0x1800257a0  jmp     short loc_180025788
0x1800257a2  xor     edx, edx
0x1800257a4  xor     edi, edi
0x1800257a6  mov     [rsp+68h+var_48], edi
0x1800257aa  cmp     edi, r8d
0x1800257ad  jnb     short loc_1800257BD
0x1800257af  mov     rax, [rsi]
0x1800257b2  cmp     [rax+rdi*8], rdx
0x1800257b6  jnz     short loc_1800257E7
0x1800257b8  mov     edx, edi
0x1800257ba  cmp     edi, r8d
0x1800257bd  jnz     short loc_1800257D1
0x1800257bf  lea     edx, [r8+1]
0x1800257c3  mov     rcx, rsi
0x1800257c6  call    ?SetSize@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAHI@Z; CPtrList<tagLOG_OUTPUT_STACK *>::SetSize(uint)
0x1800257cb  test    eax, eax
0x1800257cd  jz      short loc_1800257F2
0x1800257cf  mov     edx, edi
0x1800257d1  mov     ecx, edx; this
0x1800257d3  mov     rax, [rsi]
0x1800257d6  mov     [rax+rcx*8], rbx
0x1800257da  mov     r14d, 1
0x1800257e0  mov     [rsp+68h+var_40], r14d
0x1800257e5  jmp     short loc_1800257F2
0x1800257e7  inc     edi
0x1800257e9  jmp     short loc_1800257A6
0x1800257eb  inc     edi
0x1800257ed  jmp     loc_180025667
0x1800257f2  test    r14d, r14d
0x1800257f5  jnz     short loc_180025804
0x1800257f7  test    rbx, rbx
0x1800257fa  jz      short loc_180025804
0x1800257fc  mov     rdx, rbx; struct tagLOG_FILTER_CLAUSE *
0x1800257ff  call    ?DestroyClause@CLogConfigurableFilter@@IEAAXPEAUtagLOG_FILTER_CLAUSE@@@Z; CLogConfigurableFilter::DestroyClause(tagLOG_FILTER_CLAUSE *)
0x180025804  mov     eax, r14d
0x180025807  lea     r11, [rsp+68h+var_28]
0x18002580c  mov     rbx, [r11+38h]
0x180025810  mov     rsi, [r11+40h]
0x180025814  mov     rsp, r11
0x180025817  pop     r15
0x180025819  pop     r14
0x18002581b  pop     r13
0x18002581d  pop     r12
0x18002581f  pop     rdi
0x180025820  retn
0x1800296be  push    rbp
0x1800296c0  sub     rsp, 20h
0x1800296c4  mov     rbp, rdx
0x1800296c7  cmp     dword ptr [rbp+28h], 0
0x1800296cb  jnz     short loc_1800296DC
0x1800296cd  mov     rdx, [rbp+30h]; struct tagLOG_FILTER_CLAUSE *
0x1800296d1  test    rdx, rdx
0x1800296d4  jz      short loc_1800296DC
0x1800296d6  call    ?DestroyClause@CLogConfigurableFilter@@IEAAXPEAUtagLOG_FILTER_CLAUSE@@@Z; CLogConfigurableFilter::DestroyClause(tagLOG_FILTER_CLAUSE *)
0x1800296db  nop
0x1800296dc  add     rsp, 20h
0x1800296e0  pop     rbp
0x1800296e1  retn
```
