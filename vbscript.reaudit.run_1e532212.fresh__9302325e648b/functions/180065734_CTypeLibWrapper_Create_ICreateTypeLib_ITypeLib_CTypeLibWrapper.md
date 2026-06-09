# CTypeLibWrapper::Create(ICreateTypeLib *,ITypeLib *,CTypeLibWrapper * *)

- ea: `0x180065734`
- end: `0x180065b78`
- name: `?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeLib@@PEAPEAV1@@Z`
- size: `1092`
- prototype: `__int64 __fastcall(struct ICreateTypeLib *, struct ITypeLib *, struct CTypeLibWrapper **)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800650fc`

## callees

- `0x180045490`
- `0x180064db4`
- `0x180064ecc`
- `0x180064ef4`
- `0x180064f98`
- `0x18006500c`
- `0x180065470`
- `0x180065734`
- `0x180065fc0`
- `0x18007673a`
- `0x180076746`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180065944`
- `OLEAUT32!__imp_SysFreeString` at `0x180065944`
- `OLEAUT32!__imp_VariantCopy` at `0x180065ab1`
- `OLEAUT32!__imp_VariantCopy` at `0x180065ab1`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800657f3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800657f3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180065985`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180065985`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180065a11`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180065a11`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::Create(struct ICreateTypeLib *a1, struct ITypeLib *a2, struct CTypeLibWrapper **a3)
{
  struct ITypeLibVtbl *lpVtbl; // rax
  struct CTypeLibWrapper *v5; // rdi
  UINT (__stdcall *GetTypeInfoCount)(ITypeLib *); // rax
  CHashTable *v7; // r14
  unsigned int v8; // eax
  ULONG v9; // esi
  unsigned int i; // r15d
  HRESULT v11; // ebx
  SAFEARRAY *v13; // rax
  int v14; // eax
  CHashTable *v15; // r13
  __int64 v16; // r15
  unsigned int j; // ebx
  int v18; // eax
  _QWORD *v19; // rbx
  struct CTypeLibWrapper *v20; // rdx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  SAFEARRAY *v23; // r12
  unsigned int v24; // edx
  unsigned int v25; // r15d
  char *v26; // r14
  size_t v27; // rbx
  unsigned int v28; // r9d
  ULONG k; // eax
  _QWORD *v30; // r8
  struct CHashTable *v31; // rcx
  struct CTypeLibWrapper *v32; // rdx
  __int64 v33; // rax
  CTypeLibWrapper *v34; // rax
  CTypeLibWrapper *v35; // rax
  struct CTypeLibWrapper **v36; // rax
  unsigned int v37; // [rsp+40h] [rbp-39h]
  unsigned int v38; // [rsp+40h] [rbp-39h]
  unsigned int v39; // [rsp+44h] [rbp-35h]
  int v40; // [rsp+44h] [rbp-35h]
  int v41; // [rsp+48h] [rbp-31h]
  ULONG v42; // [rsp+48h] [rbp-31h]
  SAFEARRAY *psa; // [rsp+50h] [rbp-29h]
  struct CTypeLibWrapper *v44; // [rsp+58h] [rbp-21h] BYREF
  struct ITypeInfo *v45; // [rsp+60h] [rbp-19h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp-11h] BYREF
  struct CHashTable *v47; // [rsp+70h] [rbp-9h] BYREF
  _QWORD *pvData; // [rsp+78h] [rbp-1h]
  BSTR bstrString[10]; // [rsp+80h] [rbp+7h] BYREF
  CHashTable *v51; // [rsp+E8h] [rbp+6Fh] BYREF
  struct CTypeLibWrapper **v52; // [rsp+F0h] [rbp+77h]
  int v53; // [rsp+F8h] [rbp+7Fh] BYREF

  v52 = a3;
  lpVtbl = a2->lpVtbl;
  v53 = 0;
  rgsabound = 0;
  bstrString[0] = 0;
  v5 = 0;
  GetTypeInfoCount = lpVtbl->GetTypeInfoCount;
  v7 = 0;
  v44 = 0;
  v45 = 0;
  v51 = 0;
  v47 = 0;
  *a3 = 0;
  v8 = ((__int64 (__fastcall *)(struct ITypeLib *))GetTypeInfoCount)(a2);
  v37 = v8;
  v9 = 0;
  for ( i = 0; i < v8; ++i )
  {
    v11 = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, int *))a2->lpVtbl->GetTypeInfoType)(a2, i, &v53);
    if ( v11 < 0 )
      goto LABEL_34;
    if ( (v53 & 0xFFFFFFFD) == 0 )
      ++v9;
    v8 = v37;
  }
  if ( !v9 )
    return 1;
  rgsabound.cElements = v9;
  rgsabound.lLbound = 0;
  v13 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  psa = v13;
  if ( v13 )
  {
    pvData = v13->pvData;
    v14 = CHashTable::Create(v9, &v51);
    v15 = v51;
    v11 = v14;
    if ( v14 >= 0 )
    {
      v16 = 0;
      LODWORD(v51) = 0;
      for ( j = 0; ; ++j )
      {
        v39 = j;
        if ( j >= v37 )
          break;
        ((void (__fastcall *)(struct ITypeLib *, _QWORD, int *))a2->lpVtbl->GetTypeInfoType)(a2, j, &v53);
        if ( (v53 & 0xFFFFFFFD) == 0 )
        {
          v11 = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, struct ITypeInfo **))a2->lpVtbl->GetTypeInfo)(
                  a2,
                  j,
                  &v45);
          if ( v11 < 0 )
            goto LABEL_28;
          v18 = CTypeLibWrapper::Create(a1, v45, &v44);
          v11 = v18;
          if ( v18 < 0 )
          {
            v5 = v44;
            goto LABEL_28;
          }
          if ( v18 == 1 )
          {
            if ( --v9 != (_DWORD)v16 )
            {
              v19 = pvData;
              memmove_0(&pvData[3 * v16], &pvData[3 * (unsigned int)(v16 + 1)], 24LL * (v9 - (unsigned int)v16));
              LOWORD(v19[3 * v9 - 3]) = 0;
            }
            v5 = v44;
          }
          else
          {
            v20 = v44;
            v21 = 3 * v16;
            v5 = 0;
            v44 = 0;
            v41 = *((_DWORD *)v20 + 3);
            v22 = pvData;
            pvData[v21 + 1] = v20;
            LOWORD(v22[v21]) = 9;
            v11 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, BSTR *, _QWORD, _QWORD, _QWORD))v45->lpVtbl->GetDocumentation)(
                    v45,
                    0xFFFFFFFFLL,
                    bstrString,
                    0,
                    0,
                    0);
            if ( v11 < 0 )
              goto LABEL_28;
            v11 = CHashTable::Add(v15, bstrString[0]);
            SysFreeString(bstrString[0]);
            if ( v11 < 0 )
              goto LABEL_28;
            LODWORD(v51) = v41 + (_DWORD)v51;
            v16 = (unsigned int)(v16 + 1);
          }
          ((void (__fastcall *)(struct ITypeInfo *))v45->lpVtbl->Release)(v45);
          v45 = 0;
          if ( (_DWORD)v16 == v9 )
            break;
          j = v39;
        }
      }
      v25 = v9 + (_DWORD)v51;
      if ( v9 + (_DWORD)v51 )
      {
        v23 = psa;
        v11 = CHashTable::Create(v25, &v47);
        if ( v11 < 0 || (rgsabound.cElements = v25, v11 = SafeArrayRedim(psa, &rgsabound), v11 < 0) )
        {
          v7 = v47;
        }
        else
        {
          pvData = psa->pvData;
          v26 = (char *)pvData;
          v27 = 24LL * (unsigned int)v51;
          memmove_0(&v26[v27], v26, 24LL * v9);
          memset_0(v26, 0, v27);
          v7 = v47;
          v28 = 0;
          v38 = 0;
          for ( k = 0; ; k = v42 + 1 )
          {
            v42 = k;
            if ( k >= v9 )
              break;
            v30 = pvData;
            v31 = (struct CHashTable *)pvData[3 * (unsigned int)v51 + 1 + 3 * k];
            v47 = v31;
            v32 = *(struct CTypeLibWrapper **)(*((_QWORD *)v31 + 3) + 16LL);
            v33 = 0;
            v44 = v32;
            while ( 1 )
            {
              v40 = v33;
              if ( (unsigned int)v33 >= *((_DWORD *)v31 + 3) )
                break;
              v11 = VariantCopy((VARIANTARG *)&v30[3 * v28], (const VARIANTARG *)v32 + v33);
              if ( v11 < 0 )
                goto LABEL_29;
              v31 = v47;
              v33 = (unsigned int)(v40 + 1);
              v30 = pvData;
              v28 = v38 + 1;
              v32 = v44;
              ++v38;
            }
            v11 = CHashTable::Add(v7, *((struct CHashTable **)v31 + 2));
            if ( v11 < 0 )
              goto LABEL_29;
            v28 = v38;
          }
          CHashTable::Add(v7, v15);
          v34 = (CTypeLibWrapper *)operator new(0x60u);
          if ( v34 )
          {
            v35 = CTypeLibWrapper::CTypeLibWrapper(v34);
            v5 = v35;
            if ( v35 )
            {
              *((_QWORD *)v35 + 3) = psa;
              *((_DWORD *)v35 + 3) = v25;
              *((_QWORD *)v35 + 2) = v7;
              v7 = 0;
              ((void (__fastcall *)(struct ICreateTypeLib *))a1->lpVtbl->AddRef)(a1);
              v36 = v52;
              *((_QWORD *)v5 + 4) = a1;
              *v36 = v5;
              v5 = 0;
              v11 = 0;
              goto LABEL_30;
            }
          }
          else
          {
            v5 = 0;
          }
          v11 = -2147024882;
        }
LABEL_29:
        SafeArrayDestroy(v23);
LABEL_30:
        if ( v7 )
          CHashTable::`scalar deleting destructor'(v7, v24);
        if ( v15 )
          CHashTable::`scalar deleting destructor'(v15, v24);
        goto LABEL_34;
      }
      v11 = 1;
    }
LABEL_28:
    v23 = psa;
    goto LABEL_29;
  }
  v11 = -2147024882;
LABEL_34:
  if ( v45 )
    ((void (__fastcall *)(struct ITypeInfo *))v45->lpVtbl->Release)(v45);
  if ( v5 )
    CTypeLibWrapper::Release(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180065734  mov     [rsp-8+arg_10], r8
0x180065739  mov     [rsp-8+arg_0], rcx
0x18006573e  push    rbp
0x18006573f  push    rbx
0x180065740  push    rsi
0x180065741  push    rdi
0x180065742  push    r12
0x180065744  push    r13
0x180065746  push    r14
0x180065748  push    r15
0x18006574a  lea     rbp, [rsp-1Fh]
0x18006574f  sub     rsp, 98h
0x180065756  mov     rax, [rdx]
0x180065759  xor     ebx, ebx
0x18006575b  mov     rcx, rdx
0x18006575e  mov     [rbp+57h+arg_18], ebx
0x180065761  mov     r12, rdx
0x180065764  mov     qword ptr [rbp+57h+rgsabound.cElements], rbx
0x180065768  mov     [rbp+57h+bstrString], rbx
0x18006576c  mov     edi, ebx
0x18006576e  mov     rax, [rax+18h]
0x180065772  mov     r14d, ebx
0x180065775  mov     [rbp+57h+var_78], rbx
0x180065779  mov     [rbp+57h+var_70], rbx
0x18006577d  mov     [rbp+57h+arg_8], rbx
0x180065781  mov     [rbp+57h+var_60], rbx
0x180065785  mov     [r8], rbx
0x180065788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006578d  mov     [rbp+57h+var_90], eax
0x180065790  lea     r13d, [rbx+1]
0x180065794  mov     esi, ebx
0x180065796  mov     r15d, ebx
0x180065799  cmp     r15d, eax
0x18006579c  jnb     short loc_1800657D3
0x18006579e  mov     rcx, [r12]
0x1800657a2  lea     r8, [rbp+57h+arg_18]
0x1800657a6  mov     edx, r15d
0x1800657a9  mov     rax, [rcx+28h]
0x1800657ad  mov     rcx, r12
0x1800657b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800657b5  mov     ebx, eax
0x1800657b7  test    eax, eax
0x1800657b9  js      loc_1800659A5
0x1800657bf  test    [rbp+57h+arg_18], 0FFFFFFFDh
0x1800657c6  jnz     short loc_1800657CB
0x1800657c8  add     esi, r13d
0x1800657cb  mov     eax, [rbp+57h+var_90]
0x1800657ce  add     r15d, r13d
0x1800657d1  jmp     short loc_180065799
0x1800657d3  xor     ebx, ebx
0x1800657d5  test    esi, esi
0x1800657d7  jnz     short loc_1800657E1
0x1800657d9  mov     eax, r13d
0x1800657dc  jmp     loc_1800659C9
0x1800657e1  mov     ecx, 0Ch; vt
0x1800657e6  mov     [rbp+57h+rgsabound.cElements], esi
0x1800657e9  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800657ed  mov     [rbp+57h+rgsabound.lLbound], ebx
0x1800657f0  mov     edx, r13d; cDims
0x1800657f3  call    cs:__imp_SafeArrayCreate
0x1800657f9  mov     [rbp+57h+psa], rax
0x1800657fd  test    rax, rax
0x180065800  jnz     short loc_18006580C
0x180065802  mov     ebx, 8007000Eh
0x180065807  jmp     loc_1800659A5
0x18006580c  mov     rcx, [rax+10h]
0x180065810  lea     rdx, [rbp+57h+arg_8]; struct CHashTable **
0x180065814  mov     [rbp+57h+var_58], rcx
0x180065818  mov     ecx, esi; unsigned int
0x18006581a  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x18006581f  mov     r13, [rbp+57h+arg_8]
0x180065823  mov     ebx, eax
0x180065825  test    eax, eax
0x180065827  js      loc_18006597E
0x18006582d  xor     r15d, r15d
0x180065830  mov     dword ptr [rbp+57h+arg_8], edi
0x180065833  xor     ebx, ebx
0x180065835  mov     [rbp+57h+var_8C], ebx
0x180065838  cmp     ebx, [rbp+57h+var_90]
0x18006583b  jnb     loc_1800659DD
0x180065841  mov     rax, [r12]
0x180065845  lea     r8, [rbp+57h+arg_18]
0x180065849  mov     edx, ebx
0x18006584b  mov     rcx, r12
0x18006584e  mov     rax, [rax+28h]
0x180065852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065857  test    [rbp+57h+arg_18], 0FFFFFFFDh
0x18006585e  jnz     loc_180065973
0x180065864  mov     rax, [r12]
0x180065868  lea     r8, [rbp+57h+var_70]
0x18006586c  mov     edx, ebx
0x18006586e  mov     rcx, r12
0x180065871  mov     rax, [rax+20h]
0x180065875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006587a  mov     ebx, eax
0x18006587c  test    eax, eax
0x18006587e  js      loc_18006597E
0x180065884  mov     rdx, [rbp+57h+var_70]; struct ITypeInfo *
0x180065888  lea     r8, [rbp+57h+var_78]; struct CTypeLibWrapper **
0x18006588c  mov     rcx, [rbp+57h+arg_0]; struct ICreateTypeLib *
0x180065890  call    ?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeInfo@@PEAPEAV1@@Z; CTypeLibWrapper::Create(ICreateTypeLib *,ITypeInfo *,CTypeLibWrapper * *)
0x180065895  mov     ebx, eax
0x180065897  test    eax, eax
0x180065899  js      loc_18006597A
0x18006589f  cmp     eax, 1
0x1800658a2  jnz     short loc_1800658E5
0x1800658a4  dec     esi
0x1800658a6  mov     eax, esi
0x1800658a8  sub     eax, r15d
0x1800658ab  jz      short loc_1800658DF
0x1800658ad  mov     rbx, [rbp+57h+var_58]
0x1800658b1  lea     r8, [rax+rax*2]
0x1800658b5  lea     eax, [r15+1]
0x1800658b9  shl     r8, 3; Size
0x1800658bd  lea     rax, [rax+rax*2]
0x1800658c1  lea     rcx, [r15+r15*2]
0x1800658c5  lea     rdx, [rbx+rax*8]; Src
0x1800658c9  lea     rcx, [rbx+rcx*8]; void *
0x1800658cd  call    memmove_0
0x1800658d2  lea     eax, [rsi-1]
0x1800658d5  lea     rdx, [rax+rax*2]
0x1800658d9  xor     eax, eax
0x1800658db  mov     [rbx+rdx*8], ax
0x1800658df  mov     rdi, [rbp+57h+var_78]
0x1800658e3  jmp     short loc_180065957
0x1800658e5  mov     rdx, [rbp+57h+var_78]
0x1800658e9  lea     rcx, [r15+r15*2]
0x1800658ed  xor     edi, edi
0x1800658ef  lea     r8, [rbp+57h+bstrString]
0x1800658f3  mov     [rsp+0D0h+var_A8], rdi
0x1800658f8  xor     r9d, r9d
0x1800658fb  mov     [rbp+57h+var_78], rdi
0x1800658ff  mov     eax, [rdx+0Ch]
0x180065902  mov     [rbp+57h+var_88], eax
0x180065905  mov     rax, [rbp+57h+var_58]
0x180065909  mov     [rsp+0D0h+var_B0], rdi
0x18006590e  mov     [rax+rcx*8+8], rdx
0x180065913  or      edx, 0FFFFFFFFh
0x180065916  mov     word ptr [rax+rcx*8], 9
0x18006591c  mov     rcx, [rbp+57h+var_70]
0x180065920  mov     rax, [rcx]
0x180065923  mov     rax, [rax+60h]
0x180065927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006592c  mov     ebx, eax
0x18006592e  test    eax, eax
0x180065930  js      short loc_18006597E
0x180065932  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180065936  mov     rcx, r13; this
0x180065939  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x18006593e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180065942  mov     ebx, eax
0x180065944  call    cs:__imp_SysFreeString
0x18006594a  test    ebx, ebx
0x18006594c  js      short loc_18006597E
0x18006594e  mov     eax, [rbp+57h+var_88]
0x180065951  add     dword ptr [rbp+57h+arg_8], eax
0x180065954  inc     r15d
0x180065957  mov     rcx, [rbp+57h+var_70]
0x18006595b  mov     rax, [rcx]
0x18006595e  mov     rax, [rax+10h]
0x180065962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065967  mov     [rbp+57h+var_70], r14
0x18006596b  cmp     r15d, esi
0x18006596e  jz      short loc_1800659DD
0x180065970  mov     ebx, [rbp+57h+var_8C]
0x180065973  inc     ebx
0x180065975  jmp     loc_180065835
0x18006597a  mov     rdi, [rbp+57h+var_78]
0x18006597e  mov     r12, [rbp+57h+psa]
0x180065982  mov     rcx, r12; psa
0x180065985  call    cs:__imp_SafeArrayDestroy
0x18006598b  test    r14, r14
0x18006598e  jz      short loc_180065998
0x180065990  mov     rcx, r14; this
0x180065993  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180065998  test    r13, r13
0x18006599b  jz      short loc_1800659A5
0x18006599d  mov     rcx, r13; this
0x1800659a0  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800659a5  mov     rcx, [rbp+57h+var_70]
0x1800659a9  test    rcx, rcx
0x1800659ac  jz      short loc_1800659BA
0x1800659ae  mov     rax, [rcx]
0x1800659b1  mov     rax, [rax+10h]
0x1800659b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800659ba  test    rdi, rdi
0x1800659bd  jz      short loc_1800659C7
0x1800659bf  mov     rcx, rdi; this
0x1800659c2  call    ?Release@CTypeLibWrapper@@UEAAKXZ; CTypeLibWrapper::Release(void)
0x1800659c7  mov     eax, ebx
0x1800659c9  add     rsp, 98h
0x1800659d0  pop     r15
0x1800659d2  pop     r14
0x1800659d4  pop     r13
0x1800659d6  pop     r12
0x1800659d8  pop     rdi
0x1800659d9  pop     rsi
0x1800659da  pop     rbx
0x1800659db  pop     rbp
0x1800659dc  retn
0x1800659dd  mov     r15d, dword ptr [rbp+57h+arg_8]
0x1800659e1  add     r15d, esi
0x1800659e4  jnz     short loc_1800659EC
0x1800659e6  lea     ebx, [r15+1]
0x1800659ea  jmp     short loc_18006597E
0x1800659ec  lea     rdx, [rbp+57h+var_60]; struct CHashTable **
0x1800659f0  mov     ecx, r15d; unsigned int
0x1800659f3  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x1800659f8  mov     r12, [rbp+57h+psa]
0x1800659fc  mov     ebx, eax
0x1800659fe  test    eax, eax
0x180065a00  js      loc_180065B6F
0x180065a06  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x180065a0a  mov     [rbp+57h+rgsabound.cElements], r15d
0x180065a0e  mov     rcx, r12; psa
0x180065a11  call    cs:__imp_SafeArrayRedim
0x180065a17  mov     ebx, eax
0x180065a19  test    eax, eax
0x180065a1b  js      loc_180065B6F
0x180065a21  mov     r14, [r12+10h]
0x180065a26  mov     eax, dword ptr [rbp+57h+arg_8]
0x180065a29  mov     rdx, r14; Src
0x180065a2c  mov     [rbp+57h+var_58], r14
0x180065a30  lea     rcx, [rax+rax*2]
0x180065a34  mov     eax, esi
0x180065a36  lea     rbx, ds:0[rcx*8]
0x180065a3e  lea     rcx, [rbx+r14]; void *
0x180065a42  lea     r8, [rax+rax*2]
0x180065a46  shl     r8, 3; Size
0x180065a4a  call    memmove_0
0x180065a4f  mov     r8, rbx; Size
0x180065a52  xor     edx, edx; Val
0x180065a54  mov     rcx, r14; void *
0x180065a57  call    memset_0
0x180065a5c  mov     r14, [rbp+57h+var_60]
0x180065a60  xor     r9d, r9d
0x180065a63  mov     [rbp+57h+var_90], r9d
0x180065a67  xor     eax, eax
0x180065a69  mov     [rbp+57h+var_88], eax
0x180065a6c  cmp     eax, esi
0x180065a6e  jnb     loc_180065B03
0x180065a74  add     eax, dword ptr [rbp+57h+arg_8]
0x180065a77  mov     r8, [rbp+57h+var_58]
0x180065a7b  lea     rax, [rax+rax*2]
0x180065a7f  mov     rcx, [r8+rax*8+8]
0x180065a84  mov     [rbp+57h+var_60], rcx
0x180065a88  mov     rax, [rcx+18h]
0x180065a8c  mov     rdx, [rax+10h]
0x180065a90  xor     eax, eax
0x180065a92  mov     [rbp+57h+var_78], rdx
0x180065a96  mov     [rbp+57h+var_8C], eax
0x180065a99  cmp     eax, [rcx+0Ch]
0x180065a9c  jnb     short loc_180065ADF
0x180065a9e  lea     rcx, [rax+rax*2]
0x180065aa2  mov     eax, r9d
0x180065aa5  lea     rdx, [rdx+rcx*8]; pvargSrc
0x180065aa9  lea     rcx, [rax+rax*2]
0x180065aad  lea     rcx, [r8+rcx*8]; pvargDest
0x180065ab1  call    cs:__imp_VariantCopy
0x180065ab7  mov     ebx, eax
0x180065ab9  test    eax, eax
0x180065abb  js      loc_180065982
0x180065ac1  mov     r9d, [rbp+57h+var_90]
0x180065ac5  mov     eax, [rbp+57h+var_8C]
0x180065ac8  mov     rcx, [rbp+57h+var_60]
0x180065acc  inc     eax
0x180065ace  mov     r8, [rbp+57h+var_58]
0x180065ad2  inc     r9d
0x180065ad5  mov     rdx, [rbp+57h+var_78]
0x180065ad9  mov     [rbp+57h+var_90], r9d
0x180065add  jmp     short loc_180065A96
0x180065adf  mov     rdx, [rcx+10h]; struct CHashTable *
0x180065ae3  mov     rcx, r14; this
0x180065ae6  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180065aeb  mov     ebx, eax
0x180065aed  test    eax, eax
0x180065aef  js      loc_180065982
0x180065af5  mov     eax, [rbp+57h+var_88]
0x180065af8  mov     r9d, [rbp+57h+var_90]
0x180065afc  inc     eax
0x180065afe  jmp     loc_180065A69
0x180065b03  mov     rdx, r13; struct CHashTable *
0x180065b06  mov     rcx, r14; this
0x180065b09  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180065b0e  mov     ecx, 60h ; '`'; Size
0x180065b13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065b18  test    rax, rax
0x180065b1b  jz      short loc_180065B63
0x180065b1d  mov     rcx, rax; this
0x180065b20  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x180065b25  mov     rdi, rax
0x180065b28  test    rax, rax
0x180065b2b  jz      short loc_180065B65
0x180065b2d  mov     rbx, [rbp+57h+arg_0]
0x180065b31  mov     [rax+18h], r12
0x180065b35  mov     rcx, rbx
0x180065b38  mov     [rax+0Ch], r15d
0x180065b3c  mov     [rax+10h], r14
0x180065b40  xor     r14d, r14d
0x180065b43  mov     rax, [rbx]
  ... truncated ...
```
