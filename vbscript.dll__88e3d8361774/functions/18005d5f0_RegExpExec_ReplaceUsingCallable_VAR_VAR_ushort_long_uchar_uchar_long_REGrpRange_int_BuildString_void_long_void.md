# RegExpExec::ReplaceUsingCallable(VAR *,VAR *,ushort *,long,uchar * *,uchar *,long,REGrpRange * *,int,BuildString *,void *,long (*)(void *,VAR *,int,VAR *))

- ea: `0x18005d5f0`
- end: `0x18005da63`
- name: `?ReplaceUsingCallable@RegExpExec@@IEAAJPEAVVAR@@0PEAGJPEAPEAEPEAEJPEAPEAUREGrpRange@@HPEAVBuildString@@PEAXP6AJ60H0@Z@Z`
- size: `1139`
- prototype: `__int64 __fastcall(_JBTYPE *this, struct VAR *, struct VAR *, unsigned __int16 *, int, unsigned __int8 **, unsigned __int8 *, int, struct REGrpRange **, unsigned int, struct BuildString *, void *, int (*)(void *, struct VAR *, int, struct VAR *))`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18005da6c`

## callees

- `0x18001b960`
- `0x180022b20`
- `0x180032320`
- `0x18003bc44`
- `0x180045484`
- `0x1800454d0`
- `0x18005d568`
- `0x18005d5f0`
- `0x180076722`
- `0x18007672e`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!malloc` at `0x18005d6ca`
- `msvcrt!malloc` at `0x18005d6ca`
- `msvcrt!free` at `0x18005da2d`
- `msvcrt!free` at `0x18005da2d`
- `OLEAUT32!__imp_VariantInit` at `0x18005d6a1`
- `OLEAUT32!__imp_VariantInit` at `0x18005d6a1`
- `OLEAUT32!__imp_VariantClear` at `0x18005d814`
- `OLEAUT32!__imp_VariantClear` at `0x18005d9ec`
- `OLEAUT32!__imp_VariantClear` at `0x18005d814`
- `OLEAUT32!__imp_VariantClear` at `0x18005d9ec`

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
    v16 = RegExpExec::Exec(this, a4, a5, 0, a7, a8, *a9);
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
        v32 = RegExpExec::Exec(this, a4, a5, v30, a7, a8, a9[v35]);
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
0x18005d5f0  mov     [rsp-8+arg_8], rbx
0x18005d5f5  push    rbp
0x18005d5f6  push    rsi
0x18005d5f7  push    rdi
0x18005d5f8  push    r12
0x18005d5fa  push    r13
0x18005d5fc  push    r14
0x18005d5fe  push    r15
0x18005d600  lea     rbp, [rsp-7]
0x18005d605  sub     rsp, 0E0h
0x18005d60c  mov     rax, cs:__security_cookie
0x18005d613  xor     rax, rsp
0x18005d616  mov     [rbp+37h+var_38], rax
0x18005d61a  mov     rax, [rbp+37h+arg_50]
0x18005d621  xorps   xmm0, xmm0
0x18005d624  mov     rbx, [rbp+37h+arg_40]
0x18005d62b  mov     rdi, [rbp+37h+arg_28]
0x18005d62f  mov     rsi, [rbp+37h+arg_30]
0x18005d633  movsxd  r14, [rbp+37h+arg_38]
0x18005d637  mov     [rbp+37h+var_A0], rax
0x18005d63b  mov     rax, [rbp+37h+arg_58]
0x18005d642  mov     [rbp+37h+var_70], rax
0x18005d646  mov     rax, [rbp+37h+arg_60]
0x18005d64d  mov     [rbp+37h+var_68], rax
0x18005d651  xor     eax, eax
0x18005d653  mov     qword ptr [rbp+37h+pvarg+10h], rax
0x18005d657  mov     eax, [rbp+37h+arg_48]
0x18005d65d  mov     [rbp+37h+var_90], r9
0x18005d661  mov     [rsp+110h+var_B8], r8
0x18005d666  mov     [rbp+37h+var_78], rdx
0x18005d66a  lea     r15d, [rax+2]
0x18005d66e  mov     [rbp+37h+Buf], rcx
0x18005d672  mov     [rbp+37h+var_98], rbx
0x18005d676  mov     [rbp+37h+var_58], rdi
0x18005d67a  mov     [rbp+37h+Buf1], rsi
0x18005d67e  mov     [rsp+110h+var_D0], r14d
0x18005d683  movups  xmmword ptr [rbp+37h+pvarg], xmm0
0x18005d687  cmp     r15d, eax
0x18005d68a  jb      loc_18005DA37
0x18005d690  cmp     r15d, 7FFFFFFFh
0x18005d697  ja      loc_18005DA37
0x18005d69d  lea     rcx, [rbp+37h+pvarg]; pvarg
0x18005d6a1  call    cs:__imp_VariantInit
0x18005d6a7  xor     ecx, ecx
0x18005d6a9  mov     [rbp+37h+var_80], rcx
0x18005d6ad  test    r14d, r14d
0x18005d6b0  jle     loc_18005DA03
0x18005d6b6  test    rdi, rdi
0x18005d6b9  jnz     short loc_18005D6C4
0x18005d6bb  cmp     [rdi], rcx
0x18005d6be  jz      loc_18005DA03
0x18005d6c4  mov     rcx, r14; Size
0x18005d6c7  mov     r12, r14
0x18005d6ca  call    cs:__imp_malloc
0x18005d6d0  mov     r14, rax
0x18005d6d3  test    rax, rax
0x18005d6d6  jnz     short loc_18005D6E2
0x18005d6d8  mov     ebx, 8007000Eh
0x18005d6dd  jmp     loc_18005DA0B
0x18005d6e2  mov     r8, r12; Size
0x18005d6e5  xor     edx, edx; Val
0x18005d6e7  mov     rcx, r14; void *
0x18005d6ea  call    memset_0
0x18005d6ef  mov     rdx, [rdi]; Src
0x18005d6f2  mov     r8, r12; Size
0x18005d6f5  mov     rcx, r14; void *
0x18005d6f8  call    memcpy_0
0x18005d6fd  mov     r13, [rbx]
0x18005d700  mov     eax, r12d
0x18005d703  mov     r8d, [rbp+37h+arg_20]; int
0x18005d707  xor     r9d, r9d; int
0x18005d70a  mov     rdx, [rbp+37h+var_90]; unsigned __int16 *
0x18005d70e  mov     rcx, [rbp+37h+Buf]; Buf
0x18005d712  mov     [rsp+110h+var_E0], r13; struct REGrpRange *
0x18005d717  mov     [rsp+110h+var_E8], eax; int
0x18005d71b  mov     [rsp+110h+var_F0], rsi; unsigned __int8 *
0x18005d720  mov     [rsp+110h+var_C0], r13
0x18005d725  call    ?Exec@RegExpExec@@QEAAJPEBGJJPEAEJPEAUREGrpRange@@@Z; RegExpExec::Exec(ushort const *,long,long,uchar *,long,REGrpRange *)
0x18005d72a  mov     ebx, eax
0x18005d72c  test    eax, eax
0x18005d72e  jnz     loc_18005DA0B
0x18005d734  movsxd  rcx, r15d
0x18005d737  lea     eax, [rbx+18h]
0x18005d73a  mul     rcx
0x18005d73d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005d744  cmovb   rax, rcx
0x18005d748  mov     rcx, rax; unsigned __int64
0x18005d74b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005d750  xor     r8d, r8d
0x18005d753  mov     r12, rax
0x18005d756  test    rax, rax
0x18005d759  jz      loc_18005D6D8
0x18005d75f  mov     [rsp+110h+var_C8], r8d
0x18005d764  mov     edx, r8d
0x18005d767  test    r15d, r15d
0x18005d76a  jle     short loc_18005D77E
0x18005d76c  mov     eax, edx
0x18005d76e  inc     edx
0x18005d770  lea     rcx, [rax+rax*2]
0x18005d774  mov     [r12+rcx*8], r8w
0x18005d779  cmp     edx, r15d
0x18005d77c  jl      short loc_18005D76C
0x18005d77e  mov     edi, r8d
0x18005d781  test    rsi, rsi
0x18005d784  jnz     short loc_18005D78D
0x18005d786  mov     [rsp+110h+var_CC], r8d
0x18005d78b  jmp     short loc_18005D79A
0x18005d78d  movzx   eax, byte ptr [rsi+20h]
0x18005d791  shr     eax, 1
0x18005d793  and     eax, 1
0x18005d796  mov     [rsp+110h+var_CC], eax
0x18005d79a  mov     eax, [rbp+37h+arg_48]
0x18005d7a0  mov     esi, 2
0x18005d7a5  dec     eax
0x18005d7a7  mov     [rbp+37h+var_B0], eax
0x18005d7aa  mov     ebx, [r13+0]
0x18005d7ae  mov     eax, [r13+4]
0x18005d7b2  mov     [rbp+37h+var_A8], ebx
0x18005d7b5  mov     [rbp+37h+var_AC], eax
0x18005d7b8  cmp     edi, ebx
0x18005d7ba  jge     short loc_18005D7DB
0x18005d7bc  mov     rax, [rsp+110h+var_B8]
0x18005d7c1  mov     r8d, ebx
0x18005d7c4  movsxd  rcx, edi
0x18005d7c7  sub     r8d, edi; int
0x18005d7ca  mov     rax, [rax+8]
0x18005d7ce  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x18005d7d2  mov     rcx, [rbp+37h+var_A0]; this
0x18005d7d6  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18005d7db  mov     rax, [rbp+37h+var_78]
0x18005d7df  mov     r13d, esi
0x18005d7e2  mov     edi, [rbp+37h+var_B0]
0x18005d7e5  movups  xmm0, xmmword ptr [rax]
0x18005d7e8  movups  xmmword ptr [r12], xmm0
0x18005d7ed  movsd   xmm1, qword ptr [rax+10h]
0x18005d7f2  movsd   qword ptr [r12+10h], xmm1
0x18005d7f9  mov     word ptr [r12+18h], 3
0x18005d801  mov     [r12+20h], ebx
0x18005d806  movsxd  rax, r13d
0x18005d809  lea     rcx, [rax+rax*2]
0x18005d80d  lea     rbx, [r12+rcx*8]
0x18005d811  mov     rcx, rbx; pvarg
0x18005d814  call    cs:__imp_VariantClear
0x18005d81a  mov     r8, rbx; struct VAR *
0x18005d81d  test    edi, edi
0x18005d81f  jle     short loc_18005D84C
0x18005d821  mov     rcx, [rsp+110h+var_C0]
0x18005d826  movsxd  rax, edi
0x18005d829  lea     rcx, [rcx+rax*8]; struct REGrpRange *
0x18005d82d  mov     rax, [rsp+110h+var_B8]
0x18005d832  mov     rdx, [rax+8]; unsigned __int16 *
0x18005d836  call    ?PvarAllocFromSubstr@@YAJPEAUREGrpRange@@PEBGPEAVVAR@@@Z; PvarAllocFromSubstr(REGrpRange *,ushort const *,VAR *)
0x18005d83b  mov     ebx, eax
0x18005d83d  test    eax, eax
0x18005d83f  js      loc_18005D9DD
0x18005d845  inc     r13d
0x18005d848  dec     edi
0x18005d84a  jmp     short loc_18005D806
0x18005d84c  mov     rax, [rsp+110h+var_B8]
0x18005d851  mov     r13, [rsp+110h+var_C0]
0x18005d856  mov     rcx, r13; struct REGrpRange *
0x18005d859  mov     rdx, [rax+8]; unsigned __int16 *
0x18005d85d  call    ?PvarAllocFromSubstr@@YAJPEAUREGrpRange@@PEBGPEAVVAR@@@Z; PvarAllocFromSubstr(REGrpRange *,ushort const *,VAR *)
0x18005d862  mov     ebx, eax
0x18005d864  test    eax, eax
0x18005d866  js      loc_18005D9DD
0x18005d86c  mov     rcx, [rbp+37h+var_70]
0x18005d870  lea     rdx, [rbp+37h+pvarg]
0x18005d874  mov     rax, [rbp+37h+var_68]
0x18005d878  mov     r9, r12
0x18005d87b  mov     r8d, r15d
0x18005d87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d883  xor     r8d, r8d
0x18005d886  mov     ebx, eax
0x18005d888  test    eax, eax
0x18005d88a  js      loc_18005D9DD
0x18005d890  cmp     word ptr [rbp+37h+pvarg], r8w
0x18005d895  jz      short loc_18005D8E2
0x18005d897  lea     rax, [rbp+37h+pvarg]
0x18005d89b  mov     word ptr [rsp+110h+var_F0], 8; unsigned __int16
0x18005d8a2  xor     r9d, r9d; unsigned __int16
0x18005d8a5  mov     [rbp+37h+var_80], rax
0x18005d8a9  mov     r8d, 400h; unsigned int
0x18005d8af  lea     rdx, [rbp+37h+pvarg]; pvarSrc
0x18005d8b3  lea     rcx, [rbp+37h+pvarg]; pvargDest
0x18005d8b7  call    ?rtVariantChangeTypeEx@@YAJPEAUtagVARIANT@@0KGG@Z; rtVariantChangeTypeEx(tagVARIANT *,tagVARIANT *,ulong,ushort,ushort)
0x18005d8bc  xor     r8d, r8d
0x18005d8bf  mov     ebx, eax
0x18005d8c1  test    eax, eax
0x18005d8c3  js      loc_18005D9DD
0x18005d8c9  mov     rdx, qword ptr [rbp+37h+pvarg+8]; unsigned __int16 *
0x18005d8cd  test    rdx, rdx
0x18005d8d0  jz      short loc_18005D8D6
0x18005d8d2  mov     r8d, [rdx-4]
0x18005d8d6  mov     rcx, [rbp+37h+var_A0]; this
0x18005d8da  shr     r8d, 1; int
0x18005d8dd  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18005d8e2  mov     rbx, [rbp+37h+Buf1]
0x18005d8e6  test    rbx, rbx
0x18005d8e9  jz      loc_18005D9D8
0x18005d8ef  mov     rax, [rbp+37h+var_58]
0x18005d8f3  cmp     [rax], rbx
0x18005d8f6  jnz     loc_18005D9D8
0x18005d8fc  movsxd  r8, [rsp+110h+var_D0]; Size
0x18005d901  mov     rdx, r14; Buf2
0x18005d904  mov     rcx, rbx; Buf1
0x18005d907  call    memcmp_0
0x18005d90c  xor     r8d, r8d
0x18005d90f  test    eax, eax
0x18005d911  jnz     loc_18005D9D8
0x18005d917  movsxd  rdx, [rbp+37h+var_AC]
0x18005d91b  mov     eax, [rbp+37h+var_A8]
0x18005d91e  mov     rdi, rdx
0x18005d921  cmp     edx, eax
0x18005d923  jg      short loc_18005D928
0x18005d925  lea     edx, [rax+1]
0x18005d928  mov     ecx, [rbp+37h+arg_20]
0x18005d92b  cmp     [rsp+110h+var_CC], r8d
0x18005d930  jz      short loc_18005D995
0x18005d932  cmp     edx, ecx
0x18005d934  jg      short loc_18005D995
0x18005d936  mov     eax, 1
0x18005d93b  mov     r9d, edx; int
0x18005d93e  sub     eax, [rsp+110h+var_C8]
0x18005d942  mov     r8d, ecx; int
0x18005d945  mov     rdx, [rbp+37h+var_90]; unsigned __int16 *
0x18005d949  mov     rcx, [rbp+37h+Buf]; Buf
0x18005d94d  mov     [rsp+110h+var_C8], eax
0x18005d951  movsxd  r13, eax
0x18005d954  mov     rax, [rbp+37h+var_98]
0x18005d958  mov     rax, [rax+r13*8]
0x18005d95c  mov     [rsp+110h+var_E0], rax; struct REGrpRange *
0x18005d961  mov     eax, [rsp+110h+var_D0]
0x18005d965  mov     [rsp+110h+var_E8], eax; int
0x18005d969  mov     [rsp+110h+var_F0], rbx; unsigned __int8 *
0x18005d96e  call    ?Exec@RegExpExec@@QEAAJPEBGJJPEAEJPEAUREGrpRange@@@Z; RegExpExec::Exec(ushort const *,long,long,uchar *,long,REGrpRange *)
0x18005d973  mov     ebx, eax
0x18005d975  test    eax, eax
0x18005d977  jnz     short loc_18005D98B
0x18005d979  mov     rax, [rbp+37h+var_98]
0x18005d97d  mov     r13, [rax+r13*8]
0x18005d981  mov     [rsp+110h+var_C0], r13
0x18005d986  jmp     loc_18005D7AA
0x18005d98b  js      short loc_18005D9DD
0x18005d98d  mov     ecx, [rbp+37h+arg_20]
0x18005d990  mov     r13, [rsp+110h+var_C0]
0x18005d995  cmp     edi, ecx
0x18005d997  jge     short loc_18005D9B4
0x18005d999  mov     rax, [rsp+110h+var_B8]
0x18005d99e  sub     ecx, edi
0x18005d9a0  mov     r8d, ecx; int
0x18005d9a3  mov     rcx, [rbp+37h+var_A0]; this
0x18005d9a7  mov     rax, [rax+8]
0x18005d9ab  lea     rdx, [rax+rdi*2]; unsigned __int16 *
0x18005d9af  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18005d9b4  mov     rax, [rbp+37h+var_98]
0x18005d9b8  cmp     r13, [rax]
0x18005d9bb  jz      short loc_18005D9D4
0x18005d9bd  movsxd  r8, [rbp+37h+arg_48]
0x18005d9c4  mov     rdx, [rax+8]; Src
0x18005d9c8  mov     rcx, [rax]; void *
0x18005d9cb  shl     r8, 3; Size
0x18005d9cf  call    memcpy_0
0x18005d9d4  xor     ebx, ebx
0x18005d9d6  jmp     short loc_18005D9DD
0x18005d9d8  mov     ebx, 80004005h
0x18005d9dd  cmp     r15d, esi
0x18005d9e0  jle     short loc_18005D9F9
0x18005d9e2  mov     eax, esi
0x18005d9e4  lea     rcx, [rax+rax*2]
0x18005d9e8  lea     rcx, [r12+rcx*8]; pvarg
0x18005d9ec  call    cs:__imp_VariantClear
0x18005d9f2  inc     esi
0x18005d9f4  cmp     esi, r15d
0x18005d9f7  jl      short loc_18005D9E2
0x18005d9f9  mov     rcx, r12; Block
0x18005d9fc  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18005da01  jmp     short loc_18005DA0B
0x18005da03  mov     r14, rcx
0x18005da06  mov     ebx, 80070057h
0x18005da0b  lea     rcx, [rbp+37h+pvarg]; this
0x18005da0f  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x18005da14  mov     rax, [rbp+37h+var_80]
0x18005da18  test    rax, rax
0x18005da1b  jz      short loc_18005DA25
0x18005da1d  mov     rcx, rax; this
0x18005da20  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x18005da25  test    r14, r14
0x18005da28  jz      short loc_18005DA33
0x18005da2a  mov     rcx, r14; Block
0x18005da2d  call    cs:__imp_free
0x18005da33  mov     eax, ebx
0x18005da35  jmp     short loc_18005DA3C
0x18005da37  mov     eax, 80070216h
0x18005da3c  mov     rcx, [rbp+37h+var_38]
0x18005da40  xor     rcx, rsp; StackCookie
0x18005da43  call    __security_check_cookie
0x18005da48  mov     rbx, [rsp+110h+arg_8]
0x18005da50  add     rsp, 0E0h
0x18005da57  pop     r15
  ... truncated ...
```
