# RegExpExec::ReplaceUsingCallable(VAR *,VAR *,ushort *,long,uchar * *,uchar *,long,REGrpRange * *,int,BuildString *,void *,long (*)(void *,VAR *,int,VAR *))

- ea: `0x18005f1bc`
- end: `0x18005f64e`
- name: `?ReplaceUsingCallable@RegExpExec@@IEAAJPEAVVAR@@0PEAGJPEAPEAEPEAEJPEAPEAUREGrpRange@@HPEAVBuildString@@PEAXP6AJ60H0@Z@Z`
- size: `1170`
- prototype: `__int64 __fastcall(_JBTYPE *this, struct VAR *, struct VAR *, unsigned __int16 *, int, unsigned __int8 **, unsigned __int8 *, int, struct REGrpRange **, unsigned int, struct BuildString *, void *, int (*)(void *, struct VAR *, int, struct VAR *))`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18005f654`

## callees

- `0x18001a970`
- `0x18001ed10`
- `0x180038e4c`
- `0x18003d310`
- `0x180046878`
- `0x1800468c4`
- `0x18005f130`
- `0x18005f1bc`
- `0x180079412`
- `0x18007941e`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!malloc` at `0x18005f29c`
- `msvcrt!malloc` at `0x18005f29c`
- `msvcrt!free` at `0x18005f611`
- `msvcrt!free` at `0x18005f611`
- `OLEAUT32!__imp_VariantInit` at `0x18005f26d`
- `OLEAUT32!__imp_VariantInit` at `0x18005f26d`
- `OLEAUT32!__imp_VariantClear` at `0x18005f3ec`
- `OLEAUT32!__imp_VariantClear` at `0x18005f5ca`
- `OLEAUT32!__imp_VariantClear` at `0x18005f3ec`
- `OLEAUT32!__imp_VariantClear` at `0x18005f5ca`

## pseudocode

```c
__int64 __fastcall RegExpExec::ReplaceUsingCallable(
        _JBTYPE *this,
        struct VAR *a2,
        struct VAR *a3,
        unsigned __int16 *a4,
        int a5,
        unsigned __int8 **a6,
        unsigned __int8 *a7,
        int a8,
        struct REGrpRange **a9,
        unsigned int a10,
        struct BuildString *a11,
        void *a12,
        int (*a13)(void *, struct VAR *, int, struct VAR *))
{
  int v13; // r15d
  void *v14; // rax
  void *v15; // r14
  int v16; // ebx
  struct REGrpRange *v17; // r13
  VARIANTARG *v18; // r12
  int i; // edx
  __int64 v20; // rax
  int v21; // edi
  int v22; // esi
  LONG v23; // ebx
  int v24; // r13d
  int v25; // edi
  struct VAR *v26; // r8
  struct REGrpRange *v27; // r13
  int v28; // eax
  unsigned int v29; // r8d
  int v30; // edx
  int v31; // ecx
  int v32; // eax
  int v34; // [rsp+44h] [rbp-95h]
  int v35; // [rsp+48h] [rbp-91h]
  struct REGrpRange *v36; // [rsp+50h] [rbp-89h]
  int v38; // [rsp+64h] [rbp-75h]
  int v39; // [rsp+68h] [rbp-71h]
  VAR *p_pvarg; // [rsp+90h] [rbp-49h]
  VARIANTARG pvarg; // [rsp+C0h] [rbp-19h] BYREF

  v13 = a10 + 2;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( a10 + 2 < a10 || (unsigned int)v13 > 0x7FFFFFFF )
    return 2147942934LL;
  VariantInit(&pvarg);
  p_pvarg = 0;
  if ( a8 <= 0 || !a6 && !MEMORY[0] )
  {
    v15 = 0;
    v16 = -2147024809;
    goto LABEL_50;
  }
  v14 = malloc(a8);
  v15 = v14;
  if ( v14 )
  {
    memset_0(v14, 0, a8);
    memcpy_0(v15, *a6, a8);
    v17 = *a9;
    v36 = *a9;
    v16 = RegExpExec::Exec(this, a4, a5, 0, (struct RegExpBase::REHead *)a7, a8, *a9);
    if ( v16 )
      goto LABEL_50;
    v18 = (VARIANTARG *)operator new[](saturated_mul(v13, 0x18u));
    if ( v18 )
    {
      v35 = 0;
      for ( i = 0; i < v13; v18[v20].vt = 0 )
        v20 = (unsigned int)i++;
      v21 = 0;
      if ( a7 )
        v34 = (a7[32] >> 1) & 1;
      else
        v34 = 0;
      v22 = 2;
      while ( 1 )
      {
        v23 = *(_DWORD *)v17;
        v39 = *(_DWORD *)v17;
        v38 = *((_DWORD *)v17 + 1);
        if ( v21 < *(_DWORD *)v17 )
          BuildString::AppendSz(a11, (const unsigned __int16 *)(*((_QWORD *)a3 + 1) + 2LL * v21), v23 - v21);
        v24 = 2;
        v25 = a10 - 1;
        *(_OWORD *)&v18->vt = *(_OWORD *)a2;
        v18->pRecInfo = (IRecordInfo *)*((_QWORD *)a2 + 2);
        v18[1].vt = 3;
        v18[1].lVal = v23;
        while ( 1 )
        {
          VariantClear(&v18[v24]);
          v26 = (struct VAR *)&v18[v24];
          if ( v25 <= 0 )
            break;
          v16 = PvarAllocFromSubstr(
                  (struct REGrpRange *)((char *)v36 + 8 * v25),
                  *((const unsigned __int16 **)a3 + 1),
                  v26);
          if ( v16 < 0 )
            goto LABEL_46;
          ++v24;
          --v25;
        }
        v27 = v36;
        v16 = PvarAllocFromSubstr(v36, *((const unsigned __int16 **)a3 + 1), v26);
        if ( v16 < 0 )
          break;
        v16 = ((__int64 (__fastcall *)(void *, VARIANTARG *, _QWORD, VARIANTARG *))a13)(
                a12,
                &pvarg,
                (unsigned int)v13,
                v18);
        if ( v16 < 0 )
          break;
        if ( pvarg.vt )
        {
          p_pvarg = (VAR *)&pvarg;
          v28 = rtVariantChangeTypeEx(&pvarg, &pvarg, 0x400u, 0, 8u);
          v29 = 0;
          v16 = v28;
          if ( v28 < 0 )
            break;
          if ( pvarg.llVal )
            v29 = *(_DWORD *)(pvarg.llVal - 4);
          BuildString::AppendSz(a11, pvarg.bstrVal, v29 >> 1);
        }
        if ( !a7 || *a6 != a7 || memcmp_0(a7, v15, a8) )
        {
          v16 = -2147467259;
          break;
        }
        v30 = v38;
        v21 = v38;
        if ( v38 <= v39 )
          v30 = v39 + 1;
        v31 = a5;
        if ( !v34 || v30 > a5 )
          goto LABEL_40;
        v35 = 1 - v35;
        v32 = RegExpExec::Exec(this, a4, a5, v30, (struct RegExpBase::REHead *)a7, a8, a9[v35]);
        v16 = v32;
        if ( v32 )
        {
          if ( v32 < 0 )
            break;
          v31 = a5;
          v27 = v36;
LABEL_40:
          if ( v38 < v31 )
            BuildString::AppendSz(a11, (const unsigned __int16 *)(*((_QWORD *)a3 + 1) + 2LL * v38), v31 - v38);
          if ( v27 != *a9 )
            memcpy_0(*a9, a9[1], 8LL * (int)a10);
          v16 = 0;
          break;
        }
        v17 = a9[v35];
        v36 = v17;
      }
LABEL_46:
      if ( v13 > 2 )
      {
        do
          VariantClear(&v18[v22++]);
        while ( v22 < v13 );
      }
      operator delete[](v18);
      goto LABEL_50;
    }
  }
  v16 = -2147024882;
LABEL_50:
  VAR::Clear((VAR *)&pvarg);
  if ( p_pvarg )
    VAR::Clear(p_pvarg);
  if ( v15 )
    free(v15);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18005f1bc  mov     [rsp-8+arg_8], rbx
0x18005f1c1  push    rbp
0x18005f1c2  push    rsi
0x18005f1c3  push    rdi
0x18005f1c4  push    r12
0x18005f1c6  push    r13
0x18005f1c8  push    r14
0x18005f1ca  push    r15
0x18005f1cc  lea     rbp, [rsp-7]
0x18005f1d1  sub     rsp, 0E0h
0x18005f1d8  mov     rax, cs:__security_cookie
0x18005f1df  xor     rax, rsp
0x18005f1e2  mov     [rbp+37h+var_38], rax
0x18005f1e6  mov     rax, [rbp+37h+arg_50]
0x18005f1ed  xorps   xmm0, xmm0
0x18005f1f0  mov     rbx, [rbp+37h+arg_40]
0x18005f1f7  mov     rdi, [rbp+37h+arg_28]
0x18005f1fb  mov     rsi, [rbp+37h+arg_30]
0x18005f1ff  movsxd  r14, [rbp+37h+arg_38]
0x18005f203  mov     [rbp+37h+var_A0], rax
0x18005f207  mov     rax, [rbp+37h+arg_58]
0x18005f20e  mov     [rbp+37h+var_70], rax
0x18005f212  mov     rax, [rbp+37h+arg_60]
0x18005f219  mov     [rbp+37h+var_68], rax
0x18005f21d  xor     eax, eax
0x18005f21f  mov     qword ptr [rbp+37h+pvarg+10h], rax
0x18005f223  mov     eax, [rbp+37h+arg_48]
0x18005f229  mov     [rbp+37h+var_90], r9
0x18005f22d  mov     [rsp+110h+var_B8], r8
0x18005f232  mov     [rbp+37h+var_78], rdx
0x18005f236  lea     r15d, [rax+2]
0x18005f23a  mov     [rbp+37h+Buf], rcx
0x18005f23e  mov     [rbp+37h+var_98], rbx
0x18005f242  mov     [rbp+37h+var_58], rdi
0x18005f246  mov     [rbp+37h+Buf1], rsi
0x18005f24a  mov     [rsp+110h+var_D0], r14d
0x18005f24f  movups  xmmword ptr [rbp+37h+pvarg], xmm0
0x18005f253  cmp     r15d, eax
0x18005f256  jb      loc_18005F621
0x18005f25c  cmp     r15d, 7FFFFFFFh
0x18005f263  ja      loc_18005F621
0x18005f269  lea     rcx, [rbp+37h+pvarg]; pvarg
0x18005f26d  call    cs:__imp_VariantInit
0x18005f274  nop     dword ptr [rax+rax+00h]
0x18005f279  xor     ecx, ecx
0x18005f27b  mov     [rbp+37h+var_80], rcx
0x18005f27f  test    r14d, r14d
0x18005f282  jle     loc_18005F5E7
0x18005f288  test    rdi, rdi
0x18005f28b  jnz     short loc_18005F296
0x18005f28d  cmp     [rdi], rcx
0x18005f290  jz      loc_18005F5E7
0x18005f296  mov     rcx, r14; Size
0x18005f299  mov     r12, r14
0x18005f29c  call    cs:__imp_malloc
0x18005f2a3  nop     dword ptr [rax+rax+00h]
0x18005f2a8  mov     r14, rax
0x18005f2ab  test    rax, rax
0x18005f2ae  jnz     short loc_18005F2BA
0x18005f2b0  mov     ebx, 8007000Eh
0x18005f2b5  jmp     loc_18005F5EF
0x18005f2ba  mov     r8, r12; Size
0x18005f2bd  xor     edx, edx; Val
0x18005f2bf  mov     rcx, r14; void *
0x18005f2c2  call    memset_0
0x18005f2c7  mov     rdx, [rdi]; Src
0x18005f2ca  mov     r8, r12; Size
0x18005f2cd  mov     rcx, r14; void *
0x18005f2d0  call    memcpy_0
0x18005f2d5  mov     r13, [rbx]
0x18005f2d8  mov     eax, r12d
0x18005f2db  mov     r8d, [rbp+37h+arg_20]; int
0x18005f2df  xor     r9d, r9d; int
0x18005f2e2  mov     rdx, [rbp+37h+var_90]; unsigned __int16 *
0x18005f2e6  mov     rcx, [rbp+37h+Buf]; Buf
0x18005f2ea  mov     [rsp+110h+var_E0], r13; struct REGrpRange *
0x18005f2ef  mov     [rsp+110h+var_E8], eax; int
0x18005f2f3  mov     [rsp+110h+var_F0], rsi; unsigned __int8 *
0x18005f2f8  mov     [rsp+110h+var_C0], r13
0x18005f2fd  call    ?Exec@RegExpExec@@QEAAJPEBGJJPEAEJPEAUREGrpRange@@@Z; RegExpExec::Exec(ushort const *,long,long,uchar *,long,REGrpRange *)
0x18005f302  mov     ebx, eax
0x18005f304  test    eax, eax
0x18005f306  jnz     loc_18005F5EF
0x18005f30c  movsxd  rcx, r15d
0x18005f30f  lea     eax, [rbx+18h]
0x18005f312  mul     rcx
0x18005f315  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005f31c  cmovb   rax, rcx
0x18005f320  mov     rcx, rax; unsigned __int64
0x18005f323  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005f328  xor     r8d, r8d
0x18005f32b  mov     r12, rax
0x18005f32e  test    rax, rax
0x18005f331  jz      loc_18005F2B0
0x18005f337  mov     [rsp+110h+var_C8], r8d
0x18005f33c  mov     edx, r8d
0x18005f33f  test    r15d, r15d
0x18005f342  jle     short loc_18005F356
0x18005f344  mov     eax, edx
0x18005f346  inc     edx
0x18005f348  lea     rcx, [rax+rax*2]
0x18005f34c  mov     [r12+rcx*8], r8w
0x18005f351  cmp     edx, r15d
0x18005f354  jl      short loc_18005F344
0x18005f356  mov     edi, r8d
0x18005f359  test    rsi, rsi
0x18005f35c  jnz     short loc_18005F365
0x18005f35e  mov     [rsp+110h+var_CC], r8d
0x18005f363  jmp     short loc_18005F372
0x18005f365  movzx   eax, byte ptr [rsi+20h]
0x18005f369  shr     eax, 1
0x18005f36b  and     eax, 1
0x18005f36e  mov     [rsp+110h+var_CC], eax
0x18005f372  mov     eax, [rbp+37h+arg_48]
0x18005f378  mov     esi, 2
0x18005f37d  dec     eax
0x18005f37f  mov     [rbp+37h+var_B0], eax
0x18005f382  mov     ebx, [r13+0]
0x18005f386  mov     eax, [r13+4]
0x18005f38a  mov     [rbp+37h+var_A8], ebx
0x18005f38d  mov     [rbp+37h+var_AC], eax
0x18005f390  cmp     edi, ebx
0x18005f392  jge     short loc_18005F3B3
0x18005f394  mov     rax, [rsp+110h+var_B8]
0x18005f399  mov     r8d, ebx
0x18005f39c  movsxd  rcx, edi
0x18005f39f  sub     r8d, edi; int
0x18005f3a2  mov     rax, [rax+8]
0x18005f3a6  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x18005f3aa  mov     rcx, [rbp+37h+var_A0]; this
0x18005f3ae  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18005f3b3  mov     rax, [rbp+37h+var_78]
0x18005f3b7  mov     r13d, esi
0x18005f3ba  mov     edi, [rbp+37h+var_B0]
0x18005f3bd  movups  xmm0, xmmword ptr [rax]
0x18005f3c0  movups  xmmword ptr [r12], xmm0
0x18005f3c5  movsd   xmm1, qword ptr [rax+10h]
0x18005f3ca  movsd   qword ptr [r12+10h], xmm1
0x18005f3d1  mov     word ptr [r12+18h], 3
0x18005f3d9  mov     [r12+20h], ebx
0x18005f3de  movsxd  rax, r13d
0x18005f3e1  lea     rcx, [rax+rax*2]
0x18005f3e5  lea     rbx, [r12+rcx*8]
0x18005f3e9  mov     rcx, rbx; pvarg
0x18005f3ec  call    cs:__imp_VariantClear
0x18005f3f3  nop     dword ptr [rax+rax+00h]
0x18005f3f8  mov     r8, rbx; struct VAR *
0x18005f3fb  test    edi, edi
0x18005f3fd  jle     short loc_18005F42A
0x18005f3ff  mov     rcx, [rsp+110h+var_C0]
0x18005f404  movsxd  rax, edi
0x18005f407  lea     rcx, [rcx+rax*8]; struct REGrpRange *
0x18005f40b  mov     rax, [rsp+110h+var_B8]
0x18005f410  mov     rdx, [rax+8]; unsigned __int16 *
0x18005f414  call    ?PvarAllocFromSubstr@@YAJPEAUREGrpRange@@PEBGPEAVVAR@@@Z; PvarAllocFromSubstr(REGrpRange *,ushort const *,VAR *)
0x18005f419  mov     ebx, eax
0x18005f41b  test    eax, eax
0x18005f41d  js      loc_18005F5BB
0x18005f423  inc     r13d
0x18005f426  dec     edi
0x18005f428  jmp     short loc_18005F3DE
0x18005f42a  mov     rax, [rsp+110h+var_B8]
0x18005f42f  mov     r13, [rsp+110h+var_C0]
0x18005f434  mov     rcx, r13; struct REGrpRange *
0x18005f437  mov     rdx, [rax+8]; unsigned __int16 *
0x18005f43b  call    ?PvarAllocFromSubstr@@YAJPEAUREGrpRange@@PEBGPEAVVAR@@@Z; PvarAllocFromSubstr(REGrpRange *,ushort const *,VAR *)
0x18005f440  mov     ebx, eax
0x18005f442  test    eax, eax
0x18005f444  js      loc_18005F5BB
0x18005f44a  mov     rcx, [rbp+37h+var_70]
0x18005f44e  lea     rdx, [rbp+37h+pvarg]
0x18005f452  mov     rax, [rbp+37h+var_68]
0x18005f456  mov     r9, r12
0x18005f459  mov     r8d, r15d
0x18005f45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f461  xor     r8d, r8d
0x18005f464  mov     ebx, eax
0x18005f466  test    eax, eax
0x18005f468  js      loc_18005F5BB
0x18005f46e  cmp     word ptr [rbp+37h+pvarg], r8w
0x18005f473  jz      short loc_18005F4C0
0x18005f475  lea     rax, [rbp+37h+pvarg]
0x18005f479  mov     word ptr [rsp+110h+var_F0], 8; unsigned __int16
0x18005f480  xor     r9d, r9d; unsigned __int16
0x18005f483  mov     [rbp+37h+var_80], rax
0x18005f487  mov     r8d, 400h; unsigned int
0x18005f48d  lea     rdx, [rbp+37h+pvarg]; pvarSrc
0x18005f491  lea     rcx, [rbp+37h+pvarg]; pvargDest
0x18005f495  call    ?rtVariantChangeTypeEx@@YAJPEAUtagVARIANT@@0KGG@Z; rtVariantChangeTypeEx(tagVARIANT *,tagVARIANT *,ulong,ushort,ushort)
0x18005f49a  xor     r8d, r8d
0x18005f49d  mov     ebx, eax
0x18005f49f  test    eax, eax
0x18005f4a1  js      loc_18005F5BB
0x18005f4a7  mov     rdx, qword ptr [rbp+37h+pvarg+8]; unsigned __int16 *
0x18005f4ab  test    rdx, rdx
0x18005f4ae  jz      short loc_18005F4B4
0x18005f4b0  mov     r8d, [rdx-4]
0x18005f4b4  mov     rcx, [rbp+37h+var_A0]; this
0x18005f4b8  shr     r8d, 1; int
0x18005f4bb  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18005f4c0  mov     rbx, [rbp+37h+Buf1]
0x18005f4c4  test    rbx, rbx
0x18005f4c7  jz      loc_18005F5B6
0x18005f4cd  mov     rax, [rbp+37h+var_58]
0x18005f4d1  cmp     [rax], rbx
0x18005f4d4  jnz     loc_18005F5B6
0x18005f4da  movsxd  r8, [rsp+110h+var_D0]; Size
0x18005f4df  mov     rdx, r14; Buf2
0x18005f4e2  mov     rcx, rbx; Buf1
0x18005f4e5  call    memcmp_0
0x18005f4ea  xor     r8d, r8d
0x18005f4ed  test    eax, eax
0x18005f4ef  jnz     loc_18005F5B6
0x18005f4f5  movsxd  rdx, [rbp+37h+var_AC]
0x18005f4f9  mov     eax, [rbp+37h+var_A8]
0x18005f4fc  mov     rdi, rdx
0x18005f4ff  cmp     edx, eax
0x18005f501  jg      short loc_18005F506
0x18005f503  lea     edx, [rax+1]
0x18005f506  mov     ecx, [rbp+37h+arg_20]
0x18005f509  cmp     [rsp+110h+var_CC], r8d
0x18005f50e  jz      short loc_18005F573
0x18005f510  cmp     edx, ecx
0x18005f512  jg      short loc_18005F573
0x18005f514  mov     eax, 1
0x18005f519  mov     r9d, edx; int
0x18005f51c  sub     eax, [rsp+110h+var_C8]
0x18005f520  mov     r8d, ecx; int
0x18005f523  mov     rdx, [rbp+37h+var_90]; unsigned __int16 *
0x18005f527  mov     rcx, [rbp+37h+Buf]; Buf
0x18005f52b  mov     [rsp+110h+var_C8], eax
0x18005f52f  movsxd  r13, eax
0x18005f532  mov     rax, [rbp+37h+var_98]
0x18005f536  mov     rax, [rax+r13*8]
0x18005f53a  mov     [rsp+110h+var_E0], rax; struct REGrpRange *
0x18005f53f  mov     eax, [rsp+110h+var_D0]
0x18005f543  mov     [rsp+110h+var_E8], eax; int
0x18005f547  mov     [rsp+110h+var_F0], rbx; unsigned __int8 *
0x18005f54c  call    ?Exec@RegExpExec@@QEAAJPEBGJJPEAEJPEAUREGrpRange@@@Z; RegExpExec::Exec(ushort const *,long,long,uchar *,long,REGrpRange *)
0x18005f551  mov     ebx, eax
0x18005f553  test    eax, eax
0x18005f555  jnz     short loc_18005F569
0x18005f557  mov     rax, [rbp+37h+var_98]
0x18005f55b  mov     r13, [rax+r13*8]
0x18005f55f  mov     [rsp+110h+var_C0], r13
0x18005f564  jmp     loc_18005F382
0x18005f569  js      short loc_18005F5BB
0x18005f56b  mov     ecx, [rbp+37h+arg_20]
0x18005f56e  mov     r13, [rsp+110h+var_C0]
0x18005f573  cmp     edi, ecx
0x18005f575  jge     short loc_18005F592
0x18005f577  mov     rax, [rsp+110h+var_B8]
0x18005f57c  sub     ecx, edi
0x18005f57e  mov     r8d, ecx; int
0x18005f581  mov     rcx, [rbp+37h+var_A0]; this
0x18005f585  mov     rax, [rax+8]
0x18005f589  lea     rdx, [rax+rdi*2]; unsigned __int16 *
0x18005f58d  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18005f592  mov     rax, [rbp+37h+var_98]
0x18005f596  cmp     r13, [rax]
0x18005f599  jz      short loc_18005F5B2
0x18005f59b  movsxd  r8, [rbp+37h+arg_48]
0x18005f5a2  mov     rdx, [rax+8]; Src
0x18005f5a6  mov     rcx, [rax]; void *
0x18005f5a9  shl     r8, 3; Size
0x18005f5ad  call    memcpy_0
0x18005f5b2  xor     ebx, ebx
0x18005f5b4  jmp     short loc_18005F5BB
0x18005f5b6  mov     ebx, 80004005h
0x18005f5bb  cmp     r15d, esi
0x18005f5be  jle     short loc_18005F5DD
0x18005f5c0  mov     eax, esi
0x18005f5c2  lea     rcx, [rax+rax*2]
0x18005f5c6  lea     rcx, [r12+rcx*8]; pvarg
0x18005f5ca  call    cs:__imp_VariantClear
0x18005f5d1  nop     dword ptr [rax+rax+00h]
0x18005f5d6  inc     esi
0x18005f5d8  cmp     esi, r15d
0x18005f5db  jl      short loc_18005F5C0
0x18005f5dd  mov     rcx, r12; Block
0x18005f5e0  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18005f5e5  jmp     short loc_18005F5EF
0x18005f5e7  mov     r14, rcx
0x18005f5ea  mov     ebx, 80070057h
0x18005f5ef  lea     rcx, [rbp+37h+pvarg]; this
0x18005f5f3  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x18005f5f8  mov     rax, [rbp+37h+var_80]
0x18005f5fc  test    rax, rax
0x18005f5ff  jz      short loc_18005F609
0x18005f601  mov     rcx, rax; this
0x18005f604  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x18005f609  test    r14, r14
0x18005f60c  jz      short loc_18005F61D
0x18005f60e  mov     rcx, r14; Block
0x18005f611  call    cs:__imp_free
0x18005f618  nop     dword ptr [rax+rax+00h]
0x18005f61d  mov     eax, ebx
0x18005f61f  jmp     short loc_18005F626
0x18005f621  mov     eax, 80070216h
0x18005f626  mov     rcx, [rbp+37h+var_38]
  ... truncated ...
```
