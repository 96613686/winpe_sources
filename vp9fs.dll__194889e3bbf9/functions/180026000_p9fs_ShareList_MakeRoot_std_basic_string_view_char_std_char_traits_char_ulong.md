# p9fs::ShareList::MakeRoot(std::basic_string_view<char,std::char_traits<char>>,ulong)

- ea: `0x180026000`
- end: `0x18002669e`
- name: `?MakeRoot@ShareList@p9fs@@UEAA?AV?$BasicExpected@V?$shared_ptr@$$CBVIRoot@p9fs@@@std@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@K@Z`
- size: `1694`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path`

## callees

- `0x180004120`
- `0x180004c5c`
- `0x18000be58`
- `0x18000c208`
- `0x180025914`
- `0x180026000`
- `0x1800266a4`
- `0x180026e1c`
- `0x180028824`
- `0x180034010`

## string_xrefs

- `0x1800264b9`: `symlinkroot`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall p9fs::ShareList::MakeRoot(__int64 a1, __int64 a2, __int64 *a3)
{
  int v5; // r14d
  volatile signed __int32 *v6; // rsi
  int v7; // r15d
  __int128 v8; // kr10_16
  void *v9; // rsi
  const void *v10; // rbx
  __int64 v11; // rdx
  int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rdx
  bool v15; // cf
  int v16; // eax
  __int64 v17; // rdx
  int v18; // ebx
  bool v19; // zf
  bool v20; // cf
  int v21; // eax
  __int64 v22; // rdx
  bool v23; // cf
  int v24; // ecx
  bool v25; // cf
  int v26; // eax
  char v27; // al
  volatile signed __int32 *v28; // r14
  char v29; // cl
  int v30; // eax
  volatile signed __int32 *v31; // r14
  __int128 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-90h] BYREF
  void *Buf1[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+A0h] [rbp-60h]
  int v38; // [rsp+A4h] [rbp-5Ch]
  int v39; // [rsp+A8h] [rbp-58h]
  int v40; // [rsp+ACh] [rbp-54h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  __int128 v42; // [rsp+C0h] [rbp-40h] BYREF
  const char *v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v45; // [rsp+E0h] [rbp-20h]
  const char *v46; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v47; // [rsp+F8h] [rbp-8h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  char v49; // [rsp+110h] [rbp+10h] BYREF
  __int64 v50; // [rsp+118h] [rbp+18h]
  volatile signed __int32 *v51; // [rsp+120h] [rbp+20h]

  v48 = a1;
  v41 = a2;
  v44 = *a3;
  v45 = a3[1];
  v33 = 0;
  Buf1[0] = ";";
  Buf1[1] = (void *)1;
  p9fs::NextToken(&v33, &v44, Buf1);
  v34 = 0;
  v42 = v33;
  p9fs::ShareList::Get(a1, &v34, &v42);
  if ( !(_QWORD)v34 )
  {
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -2;
    v6 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
    if ( !*((_QWORD *)&v34 + 1) )
      return a2;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL), 0xFFFFFFFF) != 1 )
      return a2;
    (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
    if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) != 1 )
      return a2;
    goto LABEL_90;
  }
  v5 = *(_DWORD *)(v34 + 8);
  if ( (v5 & 0x20) == 0 && v45 )
  {
LABEL_4:
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -22;
LABEL_5:
    v6 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
    if ( !*((_QWORD *)&v34 + 1) )
      return a2;
LABEL_6:
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) != 1 )
      return a2;
    (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
    if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) != 1 )
      return a2;
LABEL_90:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    return a2;
  }
  v43 = 0;
  v41 = 0;
  v40 = 0;
  v7 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v8 = 0u;
  while ( v45 )
  {
    v33 = 0;
    v46 = ";";
    v47 = 1;
    p9fs::NextToken(&v33, &v44, &v46);
    *(_OWORD *)Buf1 = 0;
    *(_QWORD *)&v42 = "=";
    *((_QWORD *)&v42 + 1) = 1;
    p9fs::NextToken(Buf1, &v33, &v42);
    v9 = Buf1[1];
    v10 = Buf1[0];
    if ( Buf1[1] == (void *)8 )
    {
      if ( memcmp_0(Buf1[0], "metadata", 8u) )
        goto LABEL_66;
      if ( *((_QWORD *)&v33 + 1) )
        goto LABEL_4;
      v5 |= 4u;
    }
    else if ( Buf1[1] == (void *)4 )
    {
      if ( !memcmp_0(Buf1[0], "case", 4u) )
      {
        if ( *((_QWORD *)&v33 + 1) != 3 )
          goto LABEL_69;
        v23 = *(_BYTE *)v33 < 0x64u;
        if ( *(_BYTE *)v33 == 100
          && (v23 = *(_BYTE *)(v33 + 1) < 0x69u, *(_BYTE *)(v33 + 1) == 105)
          && (v23 = *(_BYTE *)(v33 + 2) < 0x72u, *(_BYTE *)(v33 + 2) == 114) )
        {
          v24 = 0;
        }
        else
        {
          v24 = v23 ? -1 : 1;
        }
        if ( v24 )
        {
          v25 = *(_BYTE *)v33 < 0x6Fu;
          if ( *(_BYTE *)v33 == 111
            && (v25 = *(_BYTE *)(v33 + 1) < 0x66u, *(_BYTE *)(v33 + 1) == 102)
            && (v25 = *(_BYTE *)(v33 + 2) < 0x66u, *(_BYTE *)(v33 + 2) == 102) )
          {
            v26 = 0;
          }
          else
          {
            v26 = v25 ? -1 : 1;
          }
          if ( v26 )
          {
LABEL_69:
            *(_BYTE *)a2 = 0;
            *(_DWORD *)(a2 + 8) = -95;
            goto LABEL_5;
          }
          v5 &= ~8u;
        }
        else
        {
          v5 |= 8u;
        }
      }
      else
      {
        if ( memcmp_0(v10, "path", 4u) || (v5 & 0x40) == 0 )
          goto LABEL_69;
        v41 = *((_QWORD *)&v33 + 1);
        v43 = (const char *)v33;
      }
    }
    else if ( Buf1[1] == (void *)3 )
    {
      v15 = *(_BYTE *)Buf1[0] < 0x75u;
      if ( *(_BYTE *)Buf1[0] == 117
        && (v15 = *((_BYTE *)Buf1[0] + 1) < 0x69u, *((_BYTE *)Buf1[0] + 1) == 105)
        && (v15 = *((_BYTE *)Buf1[0] + 2) < 0x64u, *((_BYTE *)Buf1[0] + 2) == 100) )
      {
        v16 = 0;
      }
      else
      {
        v16 = v15 ? -1 : 1;
      }
      if ( v16 )
      {
        v20 = *(_BYTE *)Buf1[0] < 0x67u;
        if ( *(_BYTE *)Buf1[0] == 103
          && (v20 = *((_BYTE *)Buf1[0] + 1) < 0x69u, *((_BYTE *)Buf1[0] + 1) == 105)
          && (v20 = *((_BYTE *)Buf1[0] + 2) < 0x64u, *((_BYTE *)Buf1[0] + 2) == 100) )
        {
          v21 = 0;
        }
        else
        {
          v21 = v20 ? -1 : 1;
        }
        if ( v21 )
          goto LABEL_69;
        if ( !*((_QWORD *)&v33 + 1) )
          goto LABEL_4;
        *(_OWORD *)Buf1 = 0;
        v36 = 0;
        std::string::_Construct<1,char const *>(Buf1, v33, *((_QWORD *)&v33 + 1));
        v7 = std::stoul(Buf1, v22, 10);
        std::string::~string(Buf1);
        v19 = v7 == -1;
      }
      else
      {
        if ( !*((_QWORD *)&v33 + 1) )
          goto LABEL_4;
        *(_OWORD *)Buf1 = 0;
        v36 = 0;
        std::string::_Construct<1,char const *>(Buf1, v33, *((_QWORD *)&v33 + 1));
        v18 = std::stoul(Buf1, v17, 10);
        v40 = v18;
        std::string::~string(Buf1);
        v19 = v18 == -1;
      }
      if ( v19 )
        goto LABEL_4;
    }
    else if ( Buf1[1] == (void *)5 )
    {
      if ( !memcmp_0(Buf1[0], "umask", 5u) )
      {
        if ( !*((_QWORD *)&v33 + 1) )
          goto LABEL_4;
        *(_OWORD *)Buf1 = 0;
        v36 = 0;
        std::string::_Construct<1,char const *>(Buf1, v33, *((_QWORD *)&v33 + 1));
        v12 = std::stoul(Buf1, v11, 8);
        v39 = v12;
      }
      else if ( !memcmp_0(v10, "dmask", 5u) )
      {
        if ( !*((_QWORD *)&v33 + 1) )
          goto LABEL_4;
        *(_OWORD *)Buf1 = 0;
        v36 = 0;
        std::string::_Construct<1,char const *>(Buf1, v33, *((_QWORD *)&v33 + 1));
        v12 = std::stoul(Buf1, v13, 8);
        v38 = v12;
      }
      else
      {
        if ( memcmp_0(v10, "fmask", 5u) )
          goto LABEL_69;
        if ( !*((_QWORD *)&v33 + 1) )
          goto LABEL_4;
        *(_OWORD *)Buf1 = 0;
        v36 = 0;
        std::string::_Construct<1,char const *>(Buf1, v33, *((_QWORD *)&v33 + 1));
        v12 = std::stoul(Buf1, v14, 8);
        v37 = v12;
      }
      std::string::~string(Buf1);
      if ( (v12 & 0xFFFFFE00) != 0 )
        goto LABEL_4;
    }
    else
    {
LABEL_66:
      if ( v9 != (void *)11 || memcmp_0(v10, "symlinkroot", 0xBu) )
        goto LABEL_69;
      v8 = v33;
    }
  }
  v27 = *(_BYTE *)(v48 + 40);
  v6 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
  if ( *((_QWORD *)&v34 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL));
  *(_OWORD *)Buf1 = v34;
  v42 = v8;
  v46 = v43;
  v47 = v41;
  p9fs::MakeRoot(
    (unsigned int)&v49,
    (unsigned int)Buf1,
    (unsigned int)&v46,
    v5,
    v40,
    v7,
    v39,
    v38,
    v37,
    v27,
    (__int64)&v42);
  v28 = (volatile signed __int32 *)Buf1[1];
  if ( Buf1[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Buf1[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
  }
  v29 = v49;
  if ( v49 )
  {
    v31 = v51;
    if ( v51 )
    {
      _InterlockedIncrement(v51 + 2);
      v31 = v51;
      v29 = v49;
    }
    *(_BYTE *)a2 = 1;
    *(_QWORD *)(a2 + 8) = v50;
    *(_QWORD *)(a2 + 16) = v31;
    if ( v29 )
    {
      if ( v31 )
      {
        if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
          if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        }
      }
    }
  }
  else
  {
    v30 = v50;
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = v30;
  }
  if ( v6 )
    goto LABEL_6;
  return a2;
}

```

## disassembly

```asm
0x180026000  mov     [rsp-8+arg_10], rbx
0x180026005  push    rbp
0x180026006  push    rsi
0x180026007  push    rdi
0x180026008  push    r12
0x18002600a  push    r13
0x18002600c  push    r14
0x18002600e  push    r15
0x180026010  lea     rbp, [rsp-30h]
0x180026015  sub     rsp, 130h
0x18002601c  mov     rax, cs:__security_cookie
0x180026023  xor     rax, rsp
0x180026026  mov     [rbp+60h+var_38], rax
0x18002602a  mov     rdi, rdx
0x18002602d  mov     rbx, rcx
0x180026030  mov     [rbp+60h+var_58], rcx
0x180026034  mov     [rbp+60h+var_B0], rdx
0x180026038  xor     esi, esi
0x18002603a  mov     rax, [r8]
0x18002603d  mov     [rbp+60h+var_88], rax
0x180026041  mov     rax, [r8+8]
0x180026045  mov     [rbp+60h+var_80], rax
0x180026049  xorps   xmm0, xmm0
0x18002604c  movups  [rsp+160h+var_100], xmm0
0x180026051  lea     rax, asc_180037060; ";"
0x180026058  mov     [rbp+60h+Buf1], rax
0x18002605c  mov     [rbp+60h+Buf1+8], 1
0x180026064  lea     r8, [rbp+60h+Buf1]
0x180026068  lea     rdx, [rbp+60h+var_88]
0x18002606c  lea     rcx, [rsp+160h+var_100]
0x180026071  call    ?NextToken@p9fs@@YA?AV?$basic_string_view@DU?$char_traits@D@std@@@std@@AEAV23@V23@@Z; p9fs::NextToken(std::string_view &,std::string_view)
0x180026076  xorps   xmm0, xmm0
0x180026079  movups  [rsp+160h+var_F0], xmm0
0x18002607e  movaps  xmm1, [rsp+160h+var_100]
0x180026083  movdqa  [rbp+60h+var_A0], xmm1
0x180026088  lea     r8, [rbp+60h+var_A0]
0x18002608c  lea     rdx, [rsp+160h+var_F0]
0x180026091  mov     rcx, rbx
0x180026094  call    ?Get@ShareList@p9fs@@QEAA?AV?$shared_ptr@UShare@p9fs@@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@4@@Z; p9fs::ShareList::Get(std::string_view)
0x180026099  nop
0x18002609a  mov     rax, qword ptr [rsp+160h+var_F0]
0x18002609f  test    rax, rax
0x1800260a2  jz      loc_18002662A
0x1800260a8  mov     r14d, [rax+8]
0x1800260ac  test    r14b, 20h
0x1800260b0  jnz     short loc_18002610B
0x1800260b2  cmp     [rbp+60h+var_80], rsi
0x1800260b6  jz      short loc_18002610B
0x1800260b8  mov     [rdi], sil
0x1800260bb  mov     dword ptr [rdi+8], 0FFFFFFEAh
0x1800260c2  mov     rsi, qword ptr [rsp+160h+var_F0+8]
0x1800260c7  test    rsi, rsi
0x1800260ca  jz      loc_180026674
0x1800260d0  or      ebx, 0FFFFFFFFh
0x1800260d3  mov     eax, ebx
0x1800260d5  lock xadd [rsi+8], eax
0x1800260da  add     eax, ebx
0x1800260dc  jnz     loc_180026674
0x1800260e2  mov     rax, [rsi]
0x1800260e5  mov     rcx, rsi
0x1800260e8  mov     rax, [rax]
0x1800260eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260f0  mov     eax, ebx
0x1800260f2  lock xadd [rsi+0Ch], eax
0x1800260f7  add     eax, ebx
0x1800260f9  jnz     loc_180026674
0x1800260ff  mov     rax, [rsi]
0x180026102  mov     rax, [rax+8]
0x180026106  jmp     loc_18002666C
0x18002610b  mov     [rbp+60h+var_90], rsi
0x18002610f  mov     [rbp+60h+var_B0], rsi
0x180026113  mov     [rbp+60h+var_B4], esi
0x180026116  mov     r15d, esi
0x180026119  mov     [rbp+60h+var_B8], esi
0x18002611c  mov     [rbp+60h+var_BC], esi
0x18002611f  mov     [rbp+60h+var_C0], esi
0x180026122  mov     r12, rsi
0x180026125  mov     r13, rsi
0x180026128  cmp     [rbp+60h+var_80], rsi
0x18002612c  jz      loc_1800264EE
0x180026132  xorps   xmm0, xmm0
0x180026135  movups  [rsp+160h+var_100], xmm0
0x18002613a  lea     rax, asc_180037060; ";"
0x180026141  mov     [rbp+60h+var_70], rax
0x180026145  mov     ebx, 1
0x18002614a  mov     [rbp+60h+var_68], rbx
0x18002614e  lea     r8, [rbp+60h+var_70]
0x180026152  lea     rdx, [rbp+60h+var_88]
0x180026156  lea     rcx, [rsp+160h+var_100]
0x18002615b  call    ?NextToken@p9fs@@YA?AV?$basic_string_view@DU?$char_traits@D@std@@@std@@AEAV23@V23@@Z; p9fs::NextToken(std::string_view &,std::string_view)
0x180026160  xorps   xmm0, xmm0
0x180026163  movups  xmmword ptr [rbp+60h+Buf1], xmm0
0x180026167  lea     rax, asc_18003705C; "="
0x18002616e  mov     qword ptr [rbp+60h+var_A0], rax
0x180026172  mov     qword ptr [rbp+60h+var_A0+8], rbx
0x180026176  lea     r8, [rbp+60h+var_A0]
0x18002617a  lea     rdx, [rsp+160h+var_100]
0x18002617f  lea     rcx, [rbp+60h+Buf1]
0x180026183  call    ?NextToken@p9fs@@YA?AV?$basic_string_view@DU?$char_traits@D@std@@@std@@AEAV23@V23@@Z; p9fs::NextToken(std::string_view &,std::string_view)
0x180026188  mov     rsi, [rbp+60h+Buf1+8]
0x18002618c  mov     rbx, [rbp+60h+Buf1]
0x180026190  cmp     rsi, 8
0x180026194  jz      loc_180026481
0x18002619a  cmp     rsi, 4
0x18002619e  jz      loc_1800263CD
0x1800261a4  cmp     rsi, 3
0x1800261a8  jz      loc_1800262E5
0x1800261ae  cmp     rsi, 5
0x1800261b2  jnz     loc_1800264B0
0x1800261b8  mov     r8, rsi; Size
0x1800261bb  lea     rdx, aUmask; "umask"
0x1800261c2  mov     rcx, rbx; Buf1
0x1800261c5  call    memcmp_0
0x1800261ca  xor     esi, esi
0x1800261cc  test    eax, eax
0x1800261ce  jnz     short loc_180026228
0x1800261d0  mov     r8, qword ptr [rsp+160h+var_100+8]
0x1800261d5  test    r8, r8
0x1800261d8  jz      loc_1800260B8
0x1800261de  xorps   xmm0, xmm0
0x1800261e1  movups  xmmword ptr [rbp+60h+Buf1], xmm0
0x1800261e5  xorps   xmm1, xmm1
0x1800261e8  movdqu  [rbp+60h+var_D0], xmm1
0x1800261ed  mov     rdx, qword ptr [rsp+160h+var_100]
0x1800261f2  lea     rcx, [rbp+60h+Buf1]
0x1800261f6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800261fb  nop
0x1800261fc  lea     r8d, [rsi+8]
0x180026200  lea     rcx, [rbp+60h+Buf1]
0x180026204  call    ?stoul@std@@YAKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@PEA_KH@Z; std::stoul(std::string const &,unsigned __int64 *,int)
0x180026209  mov     ebx, eax
0x18002620b  mov     [rbp+60h+var_B8], eax
0x18002620e  lea     rcx, [rbp+60h+Buf1]
0x180026212  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180026217  test    ebx, 0FFFFFE00h
0x18002621d  jz      loc_180026128
0x180026223  jmp     loc_1800260B8
0x180026228  mov     r8d, 5; Size
0x18002622e  lea     rdx, aDmask; "dmask"
0x180026235  mov     rcx, rbx; Buf1
0x180026238  call    memcmp_0
0x18002623d  test    eax, eax
0x18002623f  jnz     short loc_180026283
0x180026241  mov     r8, qword ptr [rsp+160h+var_100+8]
0x180026246  test    r8, r8
0x180026249  jz      loc_1800260B8
0x18002624f  xorps   xmm0, xmm0
0x180026252  movups  xmmword ptr [rbp+60h+Buf1], xmm0
0x180026256  xorps   xmm1, xmm1
0x180026259  movdqu  [rbp+60h+var_D0], xmm1
0x18002625e  mov     rdx, qword ptr [rsp+160h+var_100]
0x180026263  lea     rcx, [rbp+60h+Buf1]
0x180026267  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002626c  nop
0x18002626d  mov     r8d, 8
0x180026273  lea     rcx, [rbp+60h+Buf1]
0x180026277  call    ?stoul@std@@YAKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@PEA_KH@Z; std::stoul(std::string const &,unsigned __int64 *,int)
0x18002627c  mov     ebx, eax
0x18002627e  mov     [rbp+60h+var_BC], eax
0x180026281  jmp     short loc_18002620E
0x180026283  mov     r8d, 5; Size
0x180026289  lea     rdx, aFmask; "fmask"
0x180026290  mov     rcx, rbx; Buf1
0x180026293  call    memcmp_0
0x180026298  test    eax, eax
0x18002629a  jnz     loc_1800264DF
0x1800262a0  mov     r8, qword ptr [rsp+160h+var_100+8]
0x1800262a5  test    r8, r8
0x1800262a8  jz      loc_1800260B8
0x1800262ae  xorps   xmm0, xmm0
0x1800262b1  movups  xmmword ptr [rbp+60h+Buf1], xmm0
0x1800262b5  xorps   xmm1, xmm1
0x1800262b8  movdqu  [rbp+60h+var_D0], xmm1
0x1800262bd  mov     rdx, qword ptr [rsp+160h+var_100]
0x1800262c2  lea     rcx, [rbp+60h+Buf1]
0x1800262c6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800262cb  nop
0x1800262cc  mov     r8d, 8
0x1800262d2  lea     rcx, [rbp+60h+Buf1]
0x1800262d6  call    ?stoul@std@@YAKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@PEA_KH@Z; std::stoul(std::string const &,unsigned __int64 *,int)
0x1800262db  mov     ebx, eax
0x1800262dd  mov     [rbp+60h+var_C0], eax
0x1800262e0  jmp     loc_18002620E
0x1800262e5  cmp     byte ptr [rbx], 75h ; 'u'
0x1800262e8  jnz     short loc_1800262FC
0x1800262ea  cmp     byte ptr [rbx+1], 69h ; 'i'
0x1800262ee  jnz     short loc_1800262FC
0x1800262f0  cmp     byte ptr [rbx+2], 64h ; 'd'
0x1800262f4  jnz     short loc_1800262FC
0x1800262f6  xor     esi, esi
0x1800262f8  mov     eax, esi
0x1800262fa  jmp     short loc_180026303
0x1800262fc  sbb     eax, eax
0x1800262fe  or      eax, 1
0x180026301  xor     esi, esi
0x180026303  test    eax, eax
0x180026305  jnz     short loc_18002635E
0x180026307  mov     r8, qword ptr [rsp+160h+var_100+8]
0x18002630c  test    r8, r8
0x18002630f  jz      loc_1800260B8
0x180026315  xorps   xmm0, xmm0
0x180026318  movups  xmmword ptr [rbp+60h+Buf1], xmm0
0x18002631c  xorps   xmm1, xmm1
0x18002631f  movdqu  [rbp+60h+var_D0], xmm1
0x180026324  mov     rdx, qword ptr [rsp+160h+var_100]
0x180026329  lea     rcx, [rbp+60h+Buf1]
0x18002632d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026332  nop
0x180026333  mov     r8d, 0Ah
0x180026339  lea     rcx, [rbp+60h+Buf1]
0x18002633d  call    ?stoul@std@@YAKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@PEA_KH@Z; std::stoul(std::string const &,unsigned __int64 *,int)
0x180026342  mov     ebx, eax
0x180026344  mov     [rbp+60h+var_B4], eax
0x180026347  lea     rcx, [rbp+60h+Buf1]
0x18002634b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180026350  cmp     ebx, 0FFFFFFFFh
0x180026353  jnz     loc_180026128
0x180026359  jmp     loc_1800260B8
0x18002635e  cmp     byte ptr [rbx], 67h ; 'g'
0x180026361  jnz     short loc_180026373
0x180026363  cmp     byte ptr [rbx+1], 69h ; 'i'
0x180026367  jnz     short loc_180026373
0x180026369  cmp     byte ptr [rbx+2], 64h ; 'd'
0x18002636d  jnz     short loc_180026373
0x18002636f  mov     eax, esi
0x180026371  jmp     short loc_180026378
0x180026373  sbb     eax, eax
0x180026375  or      eax, 1
0x180026378  test    eax, eax
0x18002637a  jnz     loc_1800264DF
0x180026380  mov     r8, qword ptr [rsp+160h+var_100+8]
0x180026385  test    r8, r8
0x180026388  jz      loc_1800260B8
0x18002638e  xorps   xmm0, xmm0
0x180026391  movups  xmmword ptr [rbp+60h+Buf1], xmm0
0x180026395  xorps   xmm1, xmm1
0x180026398  movdqu  [rbp+60h+var_D0], xmm1
0x18002639d  mov     rdx, qword ptr [rsp+160h+var_100]
0x1800263a2  lea     rcx, [rbp+60h+Buf1]
0x1800263a6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800263ab  nop
0x1800263ac  mov     r8d, 0Ah
0x1800263b2  lea     rcx, [rbp+60h+Buf1]
0x1800263b6  call    ?stoul@std@@YAKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@PEA_KH@Z; std::stoul(std::string const &,unsigned __int64 *,int)
0x1800263bb  mov     r15d, eax
0x1800263be  lea     rcx, [rbp+60h+Buf1]
0x1800263c2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800263c7  cmp     r15d, 0FFFFFFFFh
0x1800263cb  jmp     short loc_180026353
0x1800263cd  mov     r8d, 4; Size
0x1800263d3  lea     rdx, aCase; "case"
0x1800263da  mov     rcx, rbx; Buf1
0x1800263dd  call    memcmp_0
0x1800263e2  xor     esi, esi
0x1800263e4  test    eax, eax
0x1800263e6  jnz     short loc_18002644B
0x1800263e8  cmp     qword ptr [rsp+160h+var_100+8], 3
0x1800263ee  jnz     loc_1800264DF
0x1800263f4  mov     rax, qword ptr [rsp+160h+var_100]
0x1800263f9  cmp     byte ptr [rax], 64h ; 'd'
0x1800263fc  jnz     short loc_18002640E
0x1800263fe  cmp     byte ptr [rax+1], 69h ; 'i'
0x180026402  jnz     short loc_18002640E
0x180026404  cmp     byte ptr [rax+2], 72h ; 'r'
0x180026408  jnz     short loc_18002640E
0x18002640a  mov     ecx, esi
0x18002640c  jmp     short loc_180026413
0x18002640e  sbb     ecx, ecx
0x180026410  or      ecx, 1
0x180026413  test    ecx, ecx
0x180026415  jnz     short loc_180026420
0x180026417  or      r14d, 8
0x18002641b  jmp     loc_180026128
0x180026420  cmp     byte ptr [rax], 6Fh ; 'o'
0x180026423  jnz     short loc_180026435
0x180026425  cmp     byte ptr [rax+1], 66h ; 'f'
0x180026429  jnz     short loc_180026435
0x18002642b  cmp     byte ptr [rax+2], 66h ; 'f'
0x18002642f  jnz     short loc_180026435
0x180026431  mov     eax, esi
0x180026433  jmp     short loc_18002643A
0x180026435  sbb     eax, eax
0x180026437  or      eax, 1
0x18002643a  test    eax, eax
0x18002643c  jnz     loc_1800264DF
0x180026442  and     r14d, 0FFFFFFF7h
0x180026446  jmp     loc_180026128
0x18002644b  mov     r8d, 4; Size
0x180026451  lea     rdx, aPath; "path"
0x180026458  mov     rcx, rbx; Buf1
0x18002645b  call    memcmp_0
0x180026460  test    eax, eax
0x180026462  jnz     short loc_1800264DF
0x180026464  test    r14b, 40h
0x180026468  jz      short loc_1800264DF
0x18002646a  mov     rcx, qword ptr [rsp+160h+var_100]
0x18002646f  mov     [rbp+60h+var_90], rcx
0x180026473  mov     rdx, qword ptr [rsp+160h+var_100+8]
0x180026478  mov     [rbp+60h+var_B0], rdx
0x18002647c  jmp     loc_180026128
  ... truncated ...
```
