# AspCompatVariantDictionary::Set(ushort *,tagVARIANT,int,int *)

- ea: `0x180007524`
- end: `0x180007661`
- name: `?Set@AspCompatVariantDictionary@@IEAAJPEAGUtagVARIANT@@HPEAH@Z`
- size: `317`
- prototype: `__int64 __fastcall(AspCompatVariantDictionary *__hidden this, unsigned __int16 *, VARIANTARG *pvargSrc, int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006a40`

## callees

- `0x180005f7c`
- `0x1800074e4`
- `0x180007524`
- `0x180007708`
- `0x180007b0c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800075c6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800075c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000762f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000762f`
- `OLEAUT32!__imp_VariantInit` at `0x18000755b`
- `OLEAUT32!__imp_VariantInit` at `0x18000755b`
- `OLEAUT32!__imp_VariantClear` at `0x18000763a`
- `OLEAUT32!__imp_VariantClear` at `0x18000763a`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800075b7`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800075b7`

## pseudocode

```c
__int64 __fastcall AspCompatVariantDictionary::Set(
        AspCompatVariantDictionary *this,
        unsigned __int16 *a2,
        VARIANTARG *pvargSrc,
        int a4,
        int *a5)
{
  OLECHAR *v9; // rsi
  int v10; // eax
  __int64 v11; // rbp
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int v13; // ebx
  HRESULT v14; // eax
  __int128 v15; // xmm0
  __int64 v16; // rax
  __int64 v17; // rcx
  VARIANT pvarDest; // [rsp+20h] [rbp-58h] BYREF
  struct tagVARIANT v20; // [rsp+40h] [rbp-38h] BYREF

  v9 = 0;
  VariantInit(&pvarDest);
  *a5 = -1;
  v10 = AspCompatVariantDictionary::Find(this, a2);
  LODWORD(v11) = v10;
  if ( v10 >= 0 )
  {
    pRecInfo = pvargSrc->pRecInfo;
    *(_OWORD *)&v20.vt = *(_OWORD *)&pvargSrc->vt;
    v20.pRecInfo = pRecInfo;
    v13 = AspCompatVariantDictionary::Set(this, v10, &v20, a4);
    goto LABEL_11;
  }
  if ( a4 )
    v14 = VariantDereferenceDefaultDispatchProperty(&pvarDest, pvargSrc);
  else
    v14 = VariantCopyInd(&pvarDest, pvargSrc);
  v13 = v14;
  if ( v14 )
    goto LABEL_12;
  v9 = SysAllocString(a2);
  if ( !v9 )
  {
    v13 = -2147024882;
LABEL_12:
    SysFreeString(v9);
    VariantClear(&pvarDest);
    return v13;
  }
  v13 = AspCompatVariantDictionary::SizeTo(this, *((_DWORD *)this + 18) + 1);
  if ( v13 )
    goto LABEL_12;
  v11 = *((int *)this + 18);
  v15 = *(_OWORD *)&pvarDest.vt;
  *((_DWORD *)this + 18) = v11 + 1;
  v16 = *((_QWORD *)this + 10);
  v17 = 3 * v11;
  *(_OWORD *)(v16 + 8 * v17) = v15;
  *(_QWORD *)(v16 + 8 * v17 + 16) = pvarDest.pRecInfo;
  *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v11) = v9;
LABEL_11:
  *a5 = v11;
  if ( v13 )
    goto LABEL_12;
  return v13;
}

```

## disassembly

```asm
0x180007524  mov     rax, rsp
0x180007527  mov     [rax+8], rbx
0x18000752b  mov     [rax+10h], rbp
0x18000752f  mov     [rax+18h], rsi
0x180007533  mov     [rax+20h], rdi
0x180007537  push    r12
0x180007539  push    r14
0x18000753b  push    r15
0x18000753d  sub     rsp, 60h
0x180007541  mov     r12, [rsp+78h+arg_20]
0x180007549  mov     rdi, rcx
0x18000754c  lea     rcx, [rax-58h]; pvarg
0x180007550  mov     r14d, r9d
0x180007553  mov     rbx, r8
0x180007556  mov     r15, rdx
0x180007559  xor     esi, esi
0x18000755b  call    cs:__imp_VariantInit
0x180007561  or      dword ptr [r12], 0FFFFFFFFh
0x180007566  mov     rdx, r15; unsigned __int16 *
0x180007569  mov     rcx, rdi; this
0x18000756c  call    ?Find@AspCompatVariantDictionary@@IEAAHPEAG@Z; AspCompatVariantDictionary::Find(ushort *)
0x180007571  mov     ebp, eax
0x180007573  test    eax, eax
0x180007575  js      short loc_1800075A3
0x180007577  movups  xmm0, xmmword ptr [rbx]
0x18000757a  lea     r8, [rsp+78h+var_38]; struct tagVARIANT
0x18000757f  mov     r9d, r14d; int
0x180007582  movsd   xmm1, qword ptr [rbx+10h]
0x180007587  mov     edx, eax; int
0x180007589  mov     rcx, rdi; this
0x18000758c  movaps  xmmword ptr [rsp+78h+var_38], xmm0
0x180007591  movsd   qword ptr [rsp+78h+var_38+10h], xmm1
0x180007597  call    ?Set@AspCompatVariantDictionary@@IEAAJHUtagVARIANT@@H@Z; AspCompatVariantDictionary::Set(int,tagVARIANT,int)
0x18000759c  mov     ebx, eax
0x18000759e  jmp     loc_180007624
0x1800075a3  lea     rcx, [rsp+78h+pvarDest]; pvarg
0x1800075a8  mov     rdx, rbx; pvargSrc
0x1800075ab  test    r14d, r14d
0x1800075ae  jz      short loc_1800075B7
0x1800075b0  call    ?VariantDereferenceDefaultDispatchProperty@@YAJPEAUtagVARIANT@@0@Z; VariantDereferenceDefaultDispatchProperty(tagVARIANT *,tagVARIANT *)
0x1800075b5  jmp     short loc_1800075BD
0x1800075b7  call    cs:__imp_VariantCopyInd
0x1800075bd  mov     ebx, eax
0x1800075bf  test    eax, eax
0x1800075c1  jnz     short loc_18000762C
0x1800075c3  mov     rcx, r15; psz
0x1800075c6  call    cs:__imp_SysAllocString
0x1800075cc  mov     rsi, rax
0x1800075cf  test    rax, rax
0x1800075d2  jnz     short loc_1800075DB
0x1800075d4  mov     ebx, 8007000Eh
0x1800075d9  jmp     short loc_18000762C
0x1800075db  mov     edx, [rdi+48h]
0x1800075de  mov     rcx, rdi; this
0x1800075e1  inc     edx; int
0x1800075e3  call    ?SizeTo@AspCompatVariantDictionary@@IEAAJH@Z; AspCompatVariantDictionary::SizeTo(int)
0x1800075e8  mov     ebx, eax
0x1800075ea  test    eax, eax
0x1800075ec  jnz     short loc_18000762C
0x1800075ee  movsxd  rbp, dword ptr [rdi+48h]
0x1800075f2  movups  xmm0, xmmword ptr [rsp+78h+pvarDest]
0x1800075f7  lea     eax, [rbp+1]
0x1800075fa  mov     [rdi+48h], eax
0x1800075fd  lea     rcx, ds:0[rbp*2]
0x180007605  mov     rax, [rdi+50h]
0x180007609  add     rcx, rbp
0x18000760c  movups  xmmword ptr [rax+rcx*8], xmm0
0x180007610  movsd   xmm1, qword ptr [rsp+78h+pvarDest+10h]
0x180007616  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18000761c  mov     rax, [rdi+58h]
0x180007620  mov     [rax+rbp*8], rsi
0x180007624  mov     [r12], ebp
0x180007628  test    ebx, ebx
0x18000762a  jz      short loc_180007640
0x18000762c  mov     rcx, rsi; bstrString
0x18000762f  call    cs:__imp_SysFreeString
0x180007635  lea     rcx, [rsp+78h+pvarDest]; pvarg
0x18000763a  call    cs:__imp_VariantClear
0x180007640  lea     r11, [rsp+78h+var_18]
0x180007645  mov     eax, ebx
0x180007647  mov     rbx, [r11+20h]
0x18000764b  mov     rbp, [r11+28h]
0x18000764f  mov     rsi, [r11+30h]
0x180007653  mov     rdi, [r11+38h]
0x180007657  mov     rsp, r11
0x18000765a  pop     r15
0x18000765c  pop     r14
0x18000765e  pop     r12
0x180007660  retn
```
