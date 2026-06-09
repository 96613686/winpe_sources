# CTypeLibWrapper::Create(ITypeLib * *,uint,CTypeLibWrapper * *)

- ea: `0x1800650fc`
- end: `0x180065468`
- name: `?Create@CTypeLibWrapper@@SAJPEAPEAUITypeLib@@IPEAPEAV1@@Z`
- size: `876`
- prototype: `static int(struct ITypeLib **, unsigned int, struct CTypeLibWrapper **)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180049560`
- `0x1800563f0`

## callees

- `0x180045490`
- `0x180064db4`
- `0x180064ecc`
- `0x180064ef4`
- `0x180064f98`
- `0x18006500c`
- `0x1800650fc`
- `0x180065734`
- `0x18007673a`
- `0x180076746`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006526b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006526b`
- `OLEAUT32!__imp_VariantCopy` at `0x18006535a`
- `OLEAUT32!__imp_VariantCopy` at `0x18006535a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180065187`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180065187`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180065432`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180065432`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180065296`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180065296`
- `OLEAUT32!__imp_CreateTypeLib` at `0x180065165`
- `OLEAUT32!__imp_CreateTypeLib` at `0x180065165`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::Create(struct ITypeLib **a1, unsigned int a2, struct CTypeLibWrapper **a3)
{
  CHashTable *v3; // rsi
  __int64 v4; // r12
  CHashTable *v5; // rdi
  SAFEARRAY *v7; // r15
  unsigned int v8; // edx
  HRESULT v9; // ebx
  SAFEARRAY *v10; // rax
  int v11; // eax
  __int64 i; // r13
  char *v13; // rdx
  struct CTypeLibWrapper *v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // r13d
  char *v17; // rsi
  unsigned int v18; // r9d
  unsigned int j; // eax
  char *v20; // r8
  struct CHashTable *v21; // rcx
  __int64 v22; // r13
  __int64 v23; // rdx
  CTypeLibWrapper *v24; // rax
  CTypeLibWrapper *v25; // rbx
  int v26; // eax
  unsigned int v27; // [rsp+40h] [rbp-29h]
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp-21h] BYREF
  struct CHashTable *v29; // [rsp+50h] [rbp-19h] BYREF
  struct CTypeLibWrapper *v30; // [rsp+58h] [rbp-11h] BYREF
  ICreateTypeLib *ppctlib; // [rsp+60h] [rbp-9h] BYREF
  char *pvData; // [rsp+68h] [rbp-1h]
  BSTR bstrString; // [rsp+70h] [rbp+7h] BYREF
  __int64 v34; // [rsp+78h] [rbp+Fh]
  unsigned int v36; // [rsp+D8h] [rbp+6Fh]
  CHashTable *v38; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = 0;
  v4 = a2;
  v5 = 0;
  rgsabound = 0;
  v29 = 0;
  v38 = 0;
  v30 = 0;
  ppctlib = 0;
  bstrString = 0;
  *a3 = 0;
  if ( !a2 )
    return 1;
  v7 = 0;
  v9 = CreateTypeLib(SYS_WIN32, L"ConstDeb.tlb", &ppctlib);
  if ( v9 < 0 )
    goto LABEL_34;
  rgsabound.cElements = v4;
  rgsabound.lLbound = 0;
  v10 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  v7 = v10;
  if ( !v10 )
    goto LABEL_5;
  pvData = (char *)v10->pvData;
  v11 = CHashTable::Create(v4, &v38);
  v5 = v38;
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_34;
  v36 = 0;
  for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
  {
    v38 = (CHashTable *)a1[(unsigned int)(v4 - i - 1)];
    v9 = CTypeLibWrapper::Create(ppctlib, (struct ITypeLib *)v38, &v30);
    if ( v9 < 0 )
      goto LABEL_34;
    v13 = pvData;
    v14 = v30;
    v15 = 3 * i;
    *(_WORD *)&pvData[8 * v15] = 9;
    *(_QWORD *)&v13[8 * v15 + 8] = v14;
    if ( v14 )
      v36 += *((_DWORD *)v14 + 3);
    v9 = (*(__int64 (__fastcall **)(CHashTable *, __int64, BSTR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v38 + 72LL))(
           v38,
           0xFFFFFFFFLL,
           &bstrString,
           0,
           0,
           0);
    if ( v9 < 0 )
      goto LABEL_34;
    v9 = CHashTable::Add(v5, bstrString);
    SysFreeString(bstrString);
    if ( v9 < 0 )
      goto LABEL_34;
  }
  v16 = v36;
  LODWORD(v30) = v4 + v36;
  rgsabound.cElements = v4 + v36;
  v9 = SafeArrayRedim(v7, &rgsabound);
  if ( v9 < 0 )
    goto LABEL_34;
  v17 = (char *)v7->pvData;
  pvData = v17;
  v9 = CHashTable::Create((unsigned int)v4 + v36, &v29);
  if ( v9 < 0 )
  {
    v3 = v29;
    goto LABEL_34;
  }
  memmove_0(&v17[24 * v36], v17, 24 * v4);
  memset_0(v17, 0, 24LL * v36);
  v3 = v29;
  v18 = 0;
  LODWORD(v38) = 0;
  for ( j = 0; ; j = v27 + 1 )
  {
    v27 = j;
    if ( j >= (unsigned int)v4 )
      break;
    v20 = pvData;
    v21 = *(struct CHashTable **)&pvData[24 * v16 + 8 + 24 * j];
    v29 = v21;
    if ( v21 )
    {
      v22 = 0;
      v23 = *(_QWORD *)(*((_QWORD *)v21 + 3) + 16LL);
      v34 = v23;
      while ( (unsigned int)v22 < *((_DWORD *)v21 + 3) )
      {
        v9 = VariantCopy((VARIANTARG *)&v20[24 * v18], (const VARIANTARG *)(v23 + 24 * v22));
        if ( v9 < 0 )
          goto LABEL_34;
        v22 = (unsigned int)(v22 + 1);
        v21 = v29;
        v18 = (_DWORD)v38 + 1;
        v20 = pvData;
        v23 = v34;
        LODWORD(v38) = (_DWORD)v38 + 1;
      }
      v9 = CHashTable::Add(v3, *((struct CHashTable **)v21 + 2));
      if ( v9 < 0 )
        goto LABEL_34;
      v16 = v36;
      v18 = (unsigned int)v38;
    }
  }
  v9 = CHashTable::Add(v3, v5);
  if ( v9 < 0 )
    goto LABEL_34;
  v24 = (CTypeLibWrapper *)operator new(0x60u);
  if ( !v24 || (v25 = CTypeLibWrapper::CTypeLibWrapper(v24)) == 0 )
  {
LABEL_5:
    v9 = -2147024882;
LABEL_34:
    if ( ppctlib )
      ((void (__fastcall *)(ICreateTypeLib *))ppctlib->lpVtbl->Release)(ppctlib);
    if ( v7 )
      SafeArrayDestroy(v7);
    if ( v5 )
      CHashTable::`scalar deleting destructor'(v5, v8);
    if ( v3 )
      CHashTable::`scalar deleting destructor'(v3, v8);
    return (unsigned int)v9;
  }
  if ( v5 )
    CHashTable::`scalar deleting destructor'(v5, v8);
  v26 = (int)v30;
  *((_QWORD *)v25 + 3) = v7;
  *((_DWORD *)v25 + 3) = v26;
  *((_QWORD *)v25 + 2) = v3;
  *((_QWORD *)v25 + 4) = ppctlib;
  *a3 = v25;
  return 0;
}

```

## disassembly

```asm
0x1800650fc  mov     [rsp-8+arg_10], r8
0x180065101  mov     [rsp-8+arg_0], rcx
0x180065106  push    rbp
0x180065107  push    rbx
0x180065108  push    rsi
0x180065109  push    rdi
0x18006510a  push    r12
0x18006510c  push    r13
0x18006510e  push    r14
0x180065110  push    r15
0x180065112  lea     rbp, [rsp-1Fh]
0x180065117  sub     rsp, 88h
0x18006511e  xor     esi, esi
0x180065120  mov     r12d, edx
0x180065123  xor     edi, edi
0x180065125  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x18006512d  mov     [rbp+57h+var_70], rsi
0x180065131  mov     [rbp+57h+arg_18], rdi
0x180065135  mov     [rbp+57h+var_68], rsi
0x180065139  mov     [rbp+57h+ppctlib], rsi
0x18006513d  mov     [rbp+57h+bstrString], rsi
0x180065141  mov     [r8], rsi
0x180065144  test    edx, edx
0x180065146  jnz     short loc_180065150
0x180065148  lea     eax, [rsi+1]
0x18006514b  jmp     loc_180065454
0x180065150  xor     r15d, r15d
0x180065153  lea     r8, [rbp+57h+ppctlib]; ppctlib
0x180065157  lea     rdx, aConstdebTlb; "ConstDeb.tlb"
0x18006515e  lea     r14d, [r15+1]
0x180065162  mov     ecx, r14d; syskind
0x180065165  call    cs:__imp_CreateTypeLib
0x18006516b  mov     ebx, eax
0x18006516d  test    eax, eax
0x18006516f  js      loc_180065415
0x180065175  lea     ecx, [r15+0Ch]; vt
0x180065179  mov     [rbp+57h+rgsabound.cElements], r12d
0x18006517d  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180065181  mov     [rbp+57h+rgsabound.lLbound], esi
0x180065184  mov     edx, r14d; cDims
0x180065187  call    cs:__imp_SafeArrayCreate
0x18006518d  mov     r15, rax
0x180065190  test    rax, rax
0x180065193  jnz     short loc_18006519F
0x180065195  mov     ebx, 8007000Eh
0x18006519a  jmp     loc_180065415
0x18006519f  mov     rax, [rax+10h]
0x1800651a3  lea     rdx, [rbp+57h+arg_18]; struct CHashTable **
0x1800651a7  mov     ecx, r12d; unsigned int
0x1800651aa  mov     [rbp+57h+var_58], rax
0x1800651ae  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x1800651b3  mov     rdi, [rbp+57h+arg_18]
0x1800651b7  mov     ebx, eax
0x1800651b9  test    eax, eax
0x1800651bb  js      loc_180065415
0x1800651c1  mov     [rbp+57h+arg_8], esi
0x1800651c4  xor     r13d, r13d
0x1800651c7  cmp     r13d, r12d
0x1800651ca  jnb     loc_180065281
0x1800651d0  mov     rcx, [rbp+57h+arg_0]
0x1800651d4  lea     r8, [rbp+57h+var_68]; struct CTypeLibWrapper **
0x1800651d8  mov     eax, r12d
0x1800651db  sub     eax, r13d
0x1800651de  sub     eax, r14d
0x1800651e1  mov     rax, [rcx+rax*8]
0x1800651e5  mov     rcx, [rbp+57h+ppctlib]; struct ICreateTypeLib *
0x1800651e9  mov     rdx, rax; struct ITypeLib *
0x1800651ec  mov     [rbp+57h+arg_18], rax
0x1800651f0  call    ?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeLib@@PEAPEAV1@@Z; CTypeLibWrapper::Create(ICreateTypeLib *,ITypeLib *,CTypeLibWrapper * *)
0x1800651f5  mov     ebx, eax
0x1800651f7  test    eax, eax
0x1800651f9  js      loc_180065415
0x1800651ff  mov     rdx, [rbp+57h+var_58]
0x180065203  lea     rcx, ds:0[r13*2]
0x18006520b  mov     rax, [rbp+57h+var_68]
0x18006520f  add     rcx, r13
0x180065212  mov     word ptr [rdx+rcx*8], 9
0x180065218  mov     [rdx+rcx*8+8], rax
0x18006521d  test    rax, rax
0x180065220  jz      short loc_18006522B
0x180065222  mov     ecx, [rbp+57h+arg_8]
0x180065225  add     ecx, [rax+0Ch]
0x180065228  mov     [rbp+57h+arg_8], ecx
0x18006522b  mov     rcx, [rbp+57h+arg_18]
0x18006522f  lea     r8, [rbp+57h+bstrString]
0x180065233  mov     [rsp+0C0h+var_98], rsi
0x180065238  xor     r9d, r9d
0x18006523b  or      edx, 0FFFFFFFFh
0x18006523e  mov     [rsp+0C0h+var_A0], rsi
0x180065243  mov     rax, [rcx]
0x180065246  mov     rax, [rax+48h]
0x18006524a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006524f  mov     ebx, eax
0x180065251  test    eax, eax
0x180065253  js      loc_180065415
0x180065259  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x18006525d  mov     rcx, rdi; this
0x180065260  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x180065265  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180065269  mov     ebx, eax
0x18006526b  call    cs:__imp_SysFreeString
0x180065271  test    ebx, ebx
0x180065273  js      loc_180065415
0x180065279  add     r13d, r14d
0x18006527c  jmp     loc_1800651C7
0x180065281  mov     r13d, [rbp+57h+arg_8]
0x180065285  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x180065289  mov     rcx, r15; psa
0x18006528c  lea     eax, [r12+r13]
0x180065290  mov     dword ptr [rbp+57h+var_68], eax
0x180065293  mov     [rbp+57h+rgsabound.cElements], eax
0x180065296  call    cs:__imp_SafeArrayRedim
0x18006529c  mov     ebx, eax
0x18006529e  test    eax, eax
0x1800652a0  js      loc_180065415
0x1800652a6  mov     rsi, [r15+10h]
0x1800652aa  lea     rdx, [rbp+57h+var_70]; struct CHashTable **
0x1800652ae  lea     ecx, [r12+r13]; unsigned int
0x1800652b2  mov     [rbp+57h+var_58], rsi
0x1800652b6  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x1800652bb  mov     ebx, eax
0x1800652bd  test    eax, eax
0x1800652bf  js      loc_180065411
0x1800652c5  lea     rcx, ds:0[r13*2]
0x1800652cd  mov     rdx, rsi; Src
0x1800652d0  add     rcx, r13
0x1800652d3  lea     r8, [r12+r12*2]
0x1800652d7  shl     r8, 3; Size
0x1800652db  lea     rbx, ds:0[rcx*8]
0x1800652e3  lea     rcx, [rbx+rsi]; void *
0x1800652e7  call    memmove_0
0x1800652ec  mov     r8, rbx; Size
0x1800652ef  xor     edx, edx; Val
0x1800652f1  mov     rcx, rsi; void *
0x1800652f4  call    memset_0
0x1800652f9  mov     rsi, [rbp+57h+var_70]
0x1800652fd  xor     r9d, r9d
0x180065300  mov     dword ptr [rbp+57h+arg_18], r9d
0x180065304  xor     eax, eax
0x180065306  mov     [rbp+57h+var_80], eax
0x180065309  cmp     eax, r12d
0x18006530c  jnb     loc_1800653AB
0x180065312  mov     r8, [rbp+57h+var_58]
0x180065316  add     eax, r13d
0x180065319  lea     rax, [rax+rax*2]
0x18006531d  mov     rcx, [r8+rax*8+8]
0x180065322  mov     [rbp+57h+var_70], rcx
0x180065326  test    rcx, rcx
0x180065329  jz      short loc_1800653A0
0x18006532b  mov     rax, [rcx+18h]
0x18006532f  xor     r13d, r13d
0x180065332  mov     rdx, [rax+10h]
0x180065336  mov     [rbp+57h+var_48], rdx
0x18006533a  cmp     r13d, [rcx+0Ch]
0x18006533e  jnb     short loc_180065386
0x180065340  mov     eax, r9d
0x180065343  lea     rcx, ds:0[r13*2]
0x18006534b  add     rcx, r13
0x18006534e  lea     rdx, [rdx+rcx*8]; pvargSrc
0x180065352  lea     rcx, [rax+rax*2]
0x180065356  lea     rcx, [r8+rcx*8]; pvargDest
0x18006535a  call    cs:__imp_VariantCopy
0x180065360  mov     ebx, eax
0x180065362  test    eax, eax
0x180065364  js      loc_180065415
0x18006536a  mov     r9d, dword ptr [rbp+57h+arg_18]
0x18006536e  add     r13d, r14d
0x180065371  mov     rcx, [rbp+57h+var_70]
0x180065375  add     r9d, r14d
0x180065378  mov     r8, [rbp+57h+var_58]
0x18006537c  mov     rdx, [rbp+57h+var_48]
0x180065380  mov     dword ptr [rbp+57h+arg_18], r9d
0x180065384  jmp     short loc_18006533A
0x180065386  mov     rdx, [rcx+10h]; struct CHashTable *
0x18006538a  mov     rcx, rsi; this
0x18006538d  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180065392  mov     ebx, eax
0x180065394  test    eax, eax
0x180065396  js      short loc_180065415
0x180065398  mov     r13d, [rbp+57h+arg_8]
0x18006539c  mov     r9d, dword ptr [rbp+57h+arg_18]
0x1800653a0  mov     eax, [rbp+57h+var_80]
0x1800653a3  add     eax, r14d
0x1800653a6  jmp     loc_180065306
0x1800653ab  mov     rdx, rdi; struct CHashTable *
0x1800653ae  mov     rcx, rsi; this
0x1800653b1  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x1800653b6  mov     ebx, eax
0x1800653b8  test    eax, eax
0x1800653ba  js      short loc_180065415
0x1800653bc  mov     ecx, 60h ; '`'; Size
0x1800653c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800653c6  test    rax, rax
0x1800653c9  jz      loc_180065195
0x1800653cf  mov     rcx, rax; this
0x1800653d2  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x1800653d7  mov     rbx, rax
0x1800653da  test    rax, rax
0x1800653dd  jz      loc_180065195
0x1800653e3  test    rdi, rdi
0x1800653e6  jz      short loc_1800653F0
0x1800653e8  mov     rcx, rdi; this
0x1800653eb  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800653f0  mov     eax, dword ptr [rbp+57h+var_68]
0x1800653f3  mov     [rbx+18h], r15
0x1800653f7  mov     [rbx+0Ch], eax
0x1800653fa  mov     [rbx+10h], rsi
0x1800653fe  mov     rax, [rbp+57h+ppctlib]
0x180065402  mov     [rbx+20h], rax
0x180065406  mov     rax, [rbp+57h+arg_10]
0x18006540a  mov     [rax], rbx
0x18006540d  xor     eax, eax
0x18006540f  jmp     short loc_180065454
0x180065411  mov     rsi, [rbp+57h+var_70]
0x180065415  mov     rcx, [rbp+57h+ppctlib]
0x180065419  test    rcx, rcx
0x18006541c  jz      short loc_18006542A
0x18006541e  mov     rax, [rcx]
0x180065421  mov     rax, [rax+10h]
0x180065425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006542a  test    r15, r15
0x18006542d  jz      short loc_180065438
0x18006542f  mov     rcx, r15; psa
0x180065432  call    cs:__imp_SafeArrayDestroy
0x180065438  test    rdi, rdi
0x18006543b  jz      short loc_180065445
0x18006543d  mov     rcx, rdi; this
0x180065440  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180065445  test    rsi, rsi
0x180065448  jz      short loc_180065452
0x18006544a  mov     rcx, rsi; this
0x18006544d  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180065452  mov     eax, ebx
0x180065454  add     rsp, 88h
0x18006545b  pop     r15
0x18006545d  pop     r14
0x18006545f  pop     r13
0x180065461  pop     r12
0x180065463  pop     rdi
0x180065464  pop     rsi
0x180065465  pop     rbx
0x180065466  pop     rbp
0x180065467  retn
```
