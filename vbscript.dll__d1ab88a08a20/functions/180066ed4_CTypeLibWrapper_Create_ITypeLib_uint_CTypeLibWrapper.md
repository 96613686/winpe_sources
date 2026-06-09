# CTypeLibWrapper::Create(ITypeLib * *,uint,CTypeLibWrapper * *)

- ea: `0x180066ed4`
- end: `0x180067265`
- name: `?Create@CTypeLibWrapper@@SAJPEAPEAUITypeLib@@IPEAPEAV1@@Z`
- size: `913`
- prototype: `static int(struct ITypeLib **, unsigned int, struct CTypeLibWrapper **)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18004ab30`
- `0x180057da0`

## callees

- `0x180046884`
- `0x180066b64`
- `0x180066c94`
- `0x180066cbc`
- `0x180066d64`
- `0x180066dd8`
- `0x180066ed4`
- `0x18006754c`
- `0x18007942a`
- `0x180079436`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006704f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006704f`
- `OLEAUT32!__imp_VariantCopy` at `0x18006714a`
- `OLEAUT32!__imp_VariantCopy` at `0x18006714a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180066f65`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180066f65`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180067228`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180067228`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180067080`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180067080`
- `OLEAUT32!__imp_CreateTypeLib` at `0x180066f3d`
- `OLEAUT32!__imp_CreateTypeLib` at `0x180066f3d`

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
0x180066ed4  mov     [rsp-8+arg_10], r8
0x180066ed9  mov     [rsp-8+arg_0], rcx
0x180066ede  push    rbp
0x180066edf  push    rbx
0x180066ee0  push    rsi
0x180066ee1  push    rdi
0x180066ee2  push    r12
0x180066ee4  push    r13
0x180066ee6  push    r14
0x180066ee8  push    r15
0x180066eea  lea     rbp, [rsp-1Fh]
0x180066eef  sub     rsp, 88h
0x180066ef6  xor     esi, esi
0x180066ef8  mov     r12d, edx
0x180066efb  xor     edi, edi
0x180066efd  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x180066f05  mov     [rbp+57h+var_70], rsi
0x180066f09  mov     [rbp+57h+arg_18], rdi
0x180066f0d  mov     [rbp+57h+var_68], rsi
0x180066f11  mov     [rbp+57h+ppctlib], rsi
0x180066f15  mov     [rbp+57h+bstrString], rsi
0x180066f19  mov     [r8], rsi
0x180066f1c  test    edx, edx
0x180066f1e  jnz     short loc_180066F28
0x180066f20  lea     eax, [rsi+1]
0x180066f23  jmp     loc_180067250
0x180066f28  xor     r15d, r15d
0x180066f2b  lea     r8, [rbp+57h+ppctlib]; ppctlib
0x180066f2f  lea     rdx, aConstdebTlb; "ConstDeb.tlb"
0x180066f36  lea     r14d, [r15+1]
0x180066f3a  mov     ecx, r14d; syskind
0x180066f3d  call    cs:__imp_CreateTypeLib
0x180066f44  nop     dword ptr [rax+rax+00h]
0x180066f49  mov     ebx, eax
0x180066f4b  test    eax, eax
0x180066f4d  js      loc_18006720B
0x180066f53  lea     ecx, [r15+0Ch]; vt
0x180066f57  mov     [rbp+57h+rgsabound.cElements], r12d
0x180066f5b  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180066f5f  mov     [rbp+57h+rgsabound.lLbound], esi
0x180066f62  mov     edx, r14d; cDims
0x180066f65  call    cs:__imp_SafeArrayCreate
0x180066f6c  nop     dword ptr [rax+rax+00h]
0x180066f71  mov     r15, rax
0x180066f74  test    rax, rax
0x180066f77  jnz     short loc_180066F83
0x180066f79  mov     ebx, 8007000Eh
0x180066f7e  jmp     loc_18006720B
0x180066f83  mov     rax, [rax+10h]
0x180066f87  lea     rdx, [rbp+57h+arg_18]; struct CHashTable **
0x180066f8b  mov     ecx, r12d; unsigned int
0x180066f8e  mov     [rbp+57h+var_58], rax
0x180066f92  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x180066f97  mov     rdi, [rbp+57h+arg_18]
0x180066f9b  mov     ebx, eax
0x180066f9d  test    eax, eax
0x180066f9f  js      loc_18006720B
0x180066fa5  mov     [rbp+57h+arg_8], esi
0x180066fa8  xor     r13d, r13d
0x180066fab  cmp     r13d, r12d
0x180066fae  jnb     loc_18006706B
0x180066fb4  mov     rcx, [rbp+57h+arg_0]
0x180066fb8  lea     r8, [rbp+57h+var_68]; struct CTypeLibWrapper **
0x180066fbc  mov     eax, r12d
0x180066fbf  sub     eax, r13d
0x180066fc2  sub     eax, r14d
0x180066fc5  mov     rax, [rcx+rax*8]
0x180066fc9  mov     rcx, [rbp+57h+ppctlib]; struct ICreateTypeLib *
0x180066fcd  mov     rdx, rax; struct ITypeLib *
0x180066fd0  mov     [rbp+57h+arg_18], rax
0x180066fd4  call    ?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeLib@@PEAPEAV1@@Z; CTypeLibWrapper::Create(ICreateTypeLib *,ITypeLib *,CTypeLibWrapper * *)
0x180066fd9  mov     ebx, eax
0x180066fdb  test    eax, eax
0x180066fdd  js      loc_18006720B
0x180066fe3  mov     rdx, [rbp+57h+var_58]
0x180066fe7  lea     rcx, ds:0[r13*2]
0x180066fef  mov     rax, [rbp+57h+var_68]
0x180066ff3  add     rcx, r13
0x180066ff6  mov     word ptr [rdx+rcx*8], 9
0x180066ffc  mov     [rdx+rcx*8+8], rax
0x180067001  test    rax, rax
0x180067004  jz      short loc_18006700F
0x180067006  mov     ecx, [rbp+57h+arg_8]
0x180067009  add     ecx, [rax+0Ch]
0x18006700c  mov     [rbp+57h+arg_8], ecx
0x18006700f  mov     rcx, [rbp+57h+arg_18]
0x180067013  lea     r8, [rbp+57h+bstrString]
0x180067017  mov     [rsp+0C0h+var_98], rsi
0x18006701c  xor     r9d, r9d
0x18006701f  or      edx, 0FFFFFFFFh
0x180067022  mov     [rsp+0C0h+var_A0], rsi
0x180067027  mov     rax, [rcx]
0x18006702a  mov     rax, [rax+48h]
0x18006702e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067033  mov     ebx, eax
0x180067035  test    eax, eax
0x180067037  js      loc_18006720B
0x18006703d  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180067041  mov     rcx, rdi; this
0x180067044  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x180067049  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18006704d  mov     ebx, eax
0x18006704f  call    cs:__imp_SysFreeString
0x180067056  nop     dword ptr [rax+rax+00h]
0x18006705b  test    ebx, ebx
0x18006705d  js      loc_18006720B
0x180067063  add     r13d, r14d
0x180067066  jmp     loc_180066FAB
0x18006706b  mov     r13d, [rbp+57h+arg_8]
0x18006706f  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x180067073  mov     rcx, r15; psa
0x180067076  lea     eax, [r12+r13]
0x18006707a  mov     dword ptr [rbp+57h+var_68], eax
0x18006707d  mov     [rbp+57h+rgsabound.cElements], eax
0x180067080  call    cs:__imp_SafeArrayRedim
0x180067087  nop     dword ptr [rax+rax+00h]
0x18006708c  mov     ebx, eax
0x18006708e  test    eax, eax
0x180067090  js      loc_18006720B
0x180067096  mov     rsi, [r15+10h]
0x18006709a  lea     rdx, [rbp+57h+var_70]; struct CHashTable **
0x18006709e  lea     ecx, [r12+r13]; unsigned int
0x1800670a2  mov     [rbp+57h+var_58], rsi
0x1800670a6  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x1800670ab  mov     ebx, eax
0x1800670ad  test    eax, eax
0x1800670af  js      loc_180067207
0x1800670b5  lea     rcx, ds:0[r13*2]
0x1800670bd  mov     rdx, rsi; Src
0x1800670c0  add     rcx, r13
0x1800670c3  lea     r8, [r12+r12*2]
0x1800670c7  shl     r8, 3; Size
0x1800670cb  lea     rbx, ds:0[rcx*8]
0x1800670d3  lea     rcx, [rbx+rsi]; void *
0x1800670d7  call    memmove_0
0x1800670dc  mov     r8, rbx; Size
0x1800670df  xor     edx, edx; Val
0x1800670e1  mov     rcx, rsi; void *
0x1800670e4  call    memset_0
0x1800670e9  mov     rsi, [rbp+57h+var_70]
0x1800670ed  xor     r9d, r9d
0x1800670f0  mov     dword ptr [rbp+57h+arg_18], r9d
0x1800670f4  xor     eax, eax
0x1800670f6  mov     [rbp+57h+var_80], eax
0x1800670f9  cmp     eax, r12d
0x1800670fc  jnb     loc_1800671A1
0x180067102  mov     r8, [rbp+57h+var_58]
0x180067106  add     eax, r13d
0x180067109  lea     rax, [rax+rax*2]
0x18006710d  mov     rcx, [r8+rax*8+8]
0x180067112  mov     [rbp+57h+var_70], rcx
0x180067116  test    rcx, rcx
0x180067119  jz      short loc_180067196
0x18006711b  mov     rax, [rcx+18h]
0x18006711f  xor     r13d, r13d
0x180067122  mov     rdx, [rax+10h]
0x180067126  mov     [rbp+57h+var_48], rdx
0x18006712a  cmp     r13d, [rcx+0Ch]
0x18006712e  jnb     short loc_18006717C
0x180067130  mov     eax, r9d
0x180067133  lea     rcx, ds:0[r13*2]
0x18006713b  add     rcx, r13
0x18006713e  lea     rdx, [rdx+rcx*8]; pvargSrc
0x180067142  lea     rcx, [rax+rax*2]
0x180067146  lea     rcx, [r8+rcx*8]; pvargDest
0x18006714a  call    cs:__imp_VariantCopy
0x180067151  nop     dword ptr [rax+rax+00h]
0x180067156  mov     ebx, eax
0x180067158  test    eax, eax
0x18006715a  js      loc_18006720B
0x180067160  mov     r9d, dword ptr [rbp+57h+arg_18]
0x180067164  add     r13d, r14d
0x180067167  mov     rcx, [rbp+57h+var_70]
0x18006716b  add     r9d, r14d
0x18006716e  mov     r8, [rbp+57h+var_58]
0x180067172  mov     rdx, [rbp+57h+var_48]
0x180067176  mov     dword ptr [rbp+57h+arg_18], r9d
0x18006717a  jmp     short loc_18006712A
0x18006717c  mov     rdx, [rcx+10h]; struct CHashTable *
0x180067180  mov     rcx, rsi; this
0x180067183  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180067188  mov     ebx, eax
0x18006718a  test    eax, eax
0x18006718c  js      short loc_18006720B
0x18006718e  mov     r13d, [rbp+57h+arg_8]
0x180067192  mov     r9d, dword ptr [rbp+57h+arg_18]
0x180067196  mov     eax, [rbp+57h+var_80]
0x180067199  add     eax, r14d
0x18006719c  jmp     loc_1800670F6
0x1800671a1  mov     rdx, rdi; struct CHashTable *
0x1800671a4  mov     rcx, rsi; this
0x1800671a7  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x1800671ac  mov     ebx, eax
0x1800671ae  test    eax, eax
0x1800671b0  js      short loc_18006720B
0x1800671b2  mov     ecx, 60h ; '`'; Size
0x1800671b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800671bc  test    rax, rax
0x1800671bf  jz      loc_180066F79
0x1800671c5  mov     rcx, rax; this
0x1800671c8  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x1800671cd  mov     rbx, rax
0x1800671d0  test    rax, rax
0x1800671d3  jz      loc_180066F79
0x1800671d9  test    rdi, rdi
0x1800671dc  jz      short loc_1800671E6
0x1800671de  mov     rcx, rdi; this
0x1800671e1  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800671e6  mov     eax, dword ptr [rbp+57h+var_68]
0x1800671e9  mov     [rbx+18h], r15
0x1800671ed  mov     [rbx+0Ch], eax
0x1800671f0  mov     [rbx+10h], rsi
0x1800671f4  mov     rax, [rbp+57h+ppctlib]
0x1800671f8  mov     [rbx+20h], rax
0x1800671fc  mov     rax, [rbp+57h+arg_10]
0x180067200  mov     [rax], rbx
0x180067203  xor     eax, eax
0x180067205  jmp     short loc_180067250
0x180067207  mov     rsi, [rbp+57h+var_70]
0x18006720b  mov     rcx, [rbp+57h+ppctlib]
0x18006720f  test    rcx, rcx
0x180067212  jz      short loc_180067220
0x180067214  mov     rax, [rcx]
0x180067217  mov     rax, [rax+10h]
0x18006721b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067220  test    r15, r15
0x180067223  jz      short loc_180067234
0x180067225  mov     rcx, r15; psa
0x180067228  call    cs:__imp_SafeArrayDestroy
0x18006722f  nop     dword ptr [rax+rax+00h]
0x180067234  test    rdi, rdi
0x180067237  jz      short loc_180067241
0x180067239  mov     rcx, rdi; this
0x18006723c  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180067241  test    rsi, rsi
0x180067244  jz      short loc_18006724E
0x180067246  mov     rcx, rsi; this
0x180067249  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x18006724e  mov     eax, ebx
0x180067250  add     rsp, 88h
0x180067257  pop     r15
0x180067259  pop     r14
0x18006725b  pop     r13
0x18006725d  pop     r12
0x18006725f  pop     rdi
0x180067260  pop     rsi
0x180067261  pop     rbx
0x180067262  pop     rbp
0x180067263  retn
```
