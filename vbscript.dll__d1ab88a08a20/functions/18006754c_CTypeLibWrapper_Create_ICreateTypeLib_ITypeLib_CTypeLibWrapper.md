# CTypeLibWrapper::Create(ICreateTypeLib *,ITypeLib *,CTypeLibWrapper * *)

- ea: `0x18006754c`
- end: `0x1800679af`
- name: `?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeLib@@PEAPEAV1@@Z`
- size: `1123`
- prototype: `__int64 __fastcall(struct ICreateTypeLib *, struct ITypeLib *, struct CTypeLibWrapper **)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180066ed4`

## callees

- `0x180046884`
- `0x180066b64`
- `0x180066c94`
- `0x180066cbc`
- `0x180066d64`
- `0x180066dd8`
- `0x18006726c`
- `0x18006754c`
- `0x180067e10`
- `0x18007942a`
- `0x180079436`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180067762`
- `OLEAUT32!__imp_SysFreeString` at `0x180067762`
- `OLEAUT32!__imp_VariantCopy` at `0x1800678e2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800678e2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18006760b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18006760b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800677a9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800677a9`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18006783c`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18006783c`

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
0x18006754c  mov     [rsp-8+arg_10], r8
0x180067551  mov     [rsp-8+arg_0], rcx
0x180067556  push    rbp
0x180067557  push    rbx
0x180067558  push    rsi
0x180067559  push    rdi
0x18006755a  push    r12
0x18006755c  push    r13
0x18006755e  push    r14
0x180067560  push    r15
0x180067562  lea     rbp, [rsp-1Fh]
0x180067567  sub     rsp, 98h
0x18006756e  mov     rax, [rdx]
0x180067571  xor     ebx, ebx
0x180067573  mov     rcx, rdx
0x180067576  mov     [rbp+57h+arg_18], ebx
0x180067579  mov     r12, rdx
0x18006757c  mov     qword ptr [rbp+57h+rgsabound.cElements], rbx
0x180067580  mov     [rbp+57h+bstrString], rbx
0x180067584  mov     edi, ebx
0x180067586  mov     rax, [rax+18h]
0x18006758a  mov     r14d, ebx
0x18006758d  mov     [rbp+57h+var_78], rbx
0x180067591  mov     [rbp+57h+var_70], rbx
0x180067595  mov     [rbp+57h+arg_8], rbx
0x180067599  mov     [rbp+57h+var_60], rbx
0x18006759d  mov     [r8], rbx
0x1800675a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675a5  mov     [rbp+57h+var_90], eax
0x1800675a8  lea     r13d, [rbx+1]
0x1800675ac  mov     esi, ebx
0x1800675ae  mov     r15d, ebx
0x1800675b1  cmp     r15d, eax
0x1800675b4  jnb     short loc_1800675EB
0x1800675b6  mov     rcx, [r12]
0x1800675ba  lea     r8, [rbp+57h+arg_18]
0x1800675be  mov     edx, r15d
0x1800675c1  mov     rax, [rcx+28h]
0x1800675c5  mov     rcx, r12
0x1800675c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675cd  mov     ebx, eax
0x1800675cf  test    eax, eax
0x1800675d1  js      loc_1800677CF
0x1800675d7  test    [rbp+57h+arg_18], 0FFFFFFFDh
0x1800675de  jnz     short loc_1800675E3
0x1800675e0  add     esi, r13d
0x1800675e3  mov     eax, [rbp+57h+var_90]
0x1800675e6  add     r15d, r13d
0x1800675e9  jmp     short loc_1800675B1
0x1800675eb  xor     ebx, ebx
0x1800675ed  test    esi, esi
0x1800675ef  jnz     short loc_1800675F9
0x1800675f1  mov     eax, r13d
0x1800675f4  jmp     loc_1800677F3
0x1800675f9  mov     ecx, 0Ch; vt
0x1800675fe  mov     [rbp+57h+rgsabound.cElements], esi
0x180067601  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180067605  mov     [rbp+57h+rgsabound.lLbound], ebx
0x180067608  mov     edx, r13d; cDims
0x18006760b  call    cs:__imp_SafeArrayCreate
0x180067612  nop     dword ptr [rax+rax+00h]
0x180067617  mov     [rbp+57h+psa], rax
0x18006761b  test    rax, rax
0x18006761e  jnz     short loc_18006762A
0x180067620  mov     ebx, 8007000Eh
0x180067625  jmp     loc_1800677CF
0x18006762a  mov     rcx, [rax+10h]
0x18006762e  lea     rdx, [rbp+57h+arg_8]; struct CHashTable **
0x180067632  mov     [rbp+57h+var_58], rcx
0x180067636  mov     ecx, esi; unsigned int
0x180067638  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x18006763d  mov     r13, [rbp+57h+arg_8]
0x180067641  mov     ebx, eax
0x180067643  test    eax, eax
0x180067645  js      loc_1800677A2
0x18006764b  xor     r15d, r15d
0x18006764e  mov     dword ptr [rbp+57h+arg_8], edi
0x180067651  xor     ebx, ebx
0x180067653  mov     [rbp+57h+var_8C], ebx
0x180067656  cmp     ebx, [rbp+57h+var_90]
0x180067659  jnb     loc_180067808
0x18006765f  mov     rax, [r12]
0x180067663  lea     r8, [rbp+57h+arg_18]
0x180067667  mov     edx, ebx
0x180067669  mov     rcx, r12
0x18006766c  mov     rax, [rax+28h]
0x180067670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067675  test    [rbp+57h+arg_18], 0FFFFFFFDh
0x18006767c  jnz     loc_180067797
0x180067682  mov     rax, [r12]
0x180067686  lea     r8, [rbp+57h+var_70]
0x18006768a  mov     edx, ebx
0x18006768c  mov     rcx, r12
0x18006768f  mov     rax, [rax+20h]
0x180067693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067698  mov     ebx, eax
0x18006769a  test    eax, eax
0x18006769c  js      loc_1800677A2
0x1800676a2  mov     rdx, [rbp+57h+var_70]; struct ITypeInfo *
0x1800676a6  lea     r8, [rbp+57h+var_78]; struct CTypeLibWrapper **
0x1800676aa  mov     rcx, [rbp+57h+arg_0]; struct ICreateTypeLib *
0x1800676ae  call    ?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeInfo@@PEAPEAV1@@Z; CTypeLibWrapper::Create(ICreateTypeLib *,ITypeInfo *,CTypeLibWrapper * *)
0x1800676b3  mov     ebx, eax
0x1800676b5  test    eax, eax
0x1800676b7  js      loc_18006779E
0x1800676bd  cmp     eax, 1
0x1800676c0  jnz     short loc_180067703
0x1800676c2  dec     esi
0x1800676c4  mov     eax, esi
0x1800676c6  sub     eax, r15d
0x1800676c9  jz      short loc_1800676FD
0x1800676cb  mov     rbx, [rbp+57h+var_58]
0x1800676cf  lea     r8, [rax+rax*2]
0x1800676d3  lea     eax, [r15+1]
0x1800676d7  shl     r8, 3; Size
0x1800676db  lea     rax, [rax+rax*2]
0x1800676df  lea     rcx, [r15+r15*2]
0x1800676e3  lea     rdx, [rbx+rax*8]; Src
0x1800676e7  lea     rcx, [rbx+rcx*8]; void *
0x1800676eb  call    memmove_0
0x1800676f0  lea     eax, [rsi-1]
0x1800676f3  lea     rdx, [rax+rax*2]
0x1800676f7  xor     eax, eax
0x1800676f9  mov     [rbx+rdx*8], ax
0x1800676fd  mov     rdi, [rbp+57h+var_78]
0x180067701  jmp     short loc_18006777B
0x180067703  mov     rdx, [rbp+57h+var_78]
0x180067707  lea     rcx, [r15+r15*2]
0x18006770b  xor     edi, edi
0x18006770d  lea     r8, [rbp+57h+bstrString]
0x180067711  mov     [rsp+0D0h+var_A8], rdi
0x180067716  xor     r9d, r9d
0x180067719  mov     [rbp+57h+var_78], rdi
0x18006771d  mov     eax, [rdx+0Ch]
0x180067720  mov     [rbp+57h+var_88], eax
0x180067723  mov     rax, [rbp+57h+var_58]
0x180067727  mov     [rsp+0D0h+var_B0], rdi
0x18006772c  mov     [rax+rcx*8+8], rdx
0x180067731  or      edx, 0FFFFFFFFh
0x180067734  mov     word ptr [rax+rcx*8], 9
0x18006773a  mov     rcx, [rbp+57h+var_70]
0x18006773e  mov     rax, [rcx]
0x180067741  mov     rax, [rax+60h]
0x180067745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006774a  mov     ebx, eax
0x18006774c  test    eax, eax
0x18006774e  js      short loc_1800677A2
0x180067750  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180067754  mov     rcx, r13; this
0x180067757  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x18006775c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180067760  mov     ebx, eax
0x180067762  call    cs:__imp_SysFreeString
0x180067769  nop     dword ptr [rax+rax+00h]
0x18006776e  test    ebx, ebx
0x180067770  js      short loc_1800677A2
0x180067772  mov     eax, [rbp+57h+var_88]
0x180067775  add     dword ptr [rbp+57h+arg_8], eax
0x180067778  inc     r15d
0x18006777b  mov     rcx, [rbp+57h+var_70]
0x18006777f  mov     rax, [rcx]
0x180067782  mov     rax, [rax+10h]
0x180067786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006778b  mov     [rbp+57h+var_70], r14
0x18006778f  cmp     r15d, esi
0x180067792  jz      short loc_180067808
0x180067794  mov     ebx, [rbp+57h+var_8C]
0x180067797  inc     ebx
0x180067799  jmp     loc_180067653
0x18006779e  mov     rdi, [rbp+57h+var_78]
0x1800677a2  mov     r12, [rbp+57h+psa]
0x1800677a6  mov     rcx, r12; psa
0x1800677a9  call    cs:__imp_SafeArrayDestroy
0x1800677b0  nop     dword ptr [rax+rax+00h]
0x1800677b5  test    r14, r14
0x1800677b8  jz      short loc_1800677C2
0x1800677ba  mov     rcx, r14; this
0x1800677bd  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800677c2  test    r13, r13
0x1800677c5  jz      short loc_1800677CF
0x1800677c7  mov     rcx, r13; this
0x1800677ca  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800677cf  mov     rcx, [rbp+57h+var_70]
0x1800677d3  test    rcx, rcx
0x1800677d6  jz      short loc_1800677E4
0x1800677d8  mov     rax, [rcx]
0x1800677db  mov     rax, [rax+10h]
0x1800677df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800677e4  test    rdi, rdi
0x1800677e7  jz      short loc_1800677F1
0x1800677e9  mov     rcx, rdi; this
0x1800677ec  call    ?Release@CTypeLibWrapper@@UEAAKXZ; CTypeLibWrapper::Release(void)
0x1800677f1  mov     eax, ebx
0x1800677f3  add     rsp, 98h
0x1800677fa  pop     r15
0x1800677fc  pop     r14
0x1800677fe  pop     r13
0x180067800  pop     r12
0x180067802  pop     rdi
0x180067803  pop     rsi
0x180067804  pop     rbx
0x180067805  pop     rbp
0x180067806  retn
0x180067808  mov     r15d, dword ptr [rbp+57h+arg_8]
0x18006780c  add     r15d, esi
0x18006780f  jnz     short loc_180067817
0x180067811  lea     ebx, [r15+1]
0x180067815  jmp     short loc_1800677A2
0x180067817  lea     rdx, [rbp+57h+var_60]; struct CHashTable **
0x18006781b  mov     ecx, r15d; unsigned int
0x18006781e  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x180067823  mov     r12, [rbp+57h+psa]
0x180067827  mov     ebx, eax
0x180067829  test    eax, eax
0x18006782b  js      loc_1800679A6
0x180067831  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x180067835  mov     [rbp+57h+rgsabound.cElements], r15d
0x180067839  mov     rcx, r12; psa
0x18006783c  call    cs:__imp_SafeArrayRedim
0x180067843  nop     dword ptr [rax+rax+00h]
0x180067848  mov     ebx, eax
0x18006784a  test    eax, eax
0x18006784c  js      loc_1800679A6
0x180067852  mov     r14, [r12+10h]
0x180067857  mov     eax, dword ptr [rbp+57h+arg_8]
0x18006785a  mov     rdx, r14; Src
0x18006785d  mov     [rbp+57h+var_58], r14
0x180067861  lea     rcx, [rax+rax*2]
0x180067865  mov     eax, esi
0x180067867  lea     rbx, ds:0[rcx*8]
0x18006786f  lea     rcx, [rbx+r14]; void *
0x180067873  lea     r8, [rax+rax*2]
0x180067877  shl     r8, 3; Size
0x18006787b  call    memmove_0
0x180067880  mov     r8, rbx; Size
0x180067883  xor     edx, edx; Val
0x180067885  mov     rcx, r14; void *
0x180067888  call    memset_0
0x18006788d  mov     r14, [rbp+57h+var_60]
0x180067891  xor     r9d, r9d
0x180067894  mov     [rbp+57h+var_90], r9d
0x180067898  xor     eax, eax
0x18006789a  mov     [rbp+57h+var_88], eax
0x18006789d  cmp     eax, esi
0x18006789f  jnb     loc_18006793A
0x1800678a5  add     eax, dword ptr [rbp+57h+arg_8]
0x1800678a8  mov     r8, [rbp+57h+var_58]
0x1800678ac  lea     rax, [rax+rax*2]
0x1800678b0  mov     rcx, [r8+rax*8+8]
0x1800678b5  mov     [rbp+57h+var_60], rcx
0x1800678b9  mov     rax, [rcx+18h]
0x1800678bd  mov     rdx, [rax+10h]
0x1800678c1  xor     eax, eax
0x1800678c3  mov     [rbp+57h+var_78], rdx
0x1800678c7  mov     [rbp+57h+var_8C], eax
0x1800678ca  cmp     eax, [rcx+0Ch]
0x1800678cd  jnb     short loc_180067916
0x1800678cf  lea     rcx, [rax+rax*2]
0x1800678d3  mov     eax, r9d
0x1800678d6  lea     rdx, [rdx+rcx*8]; pvargSrc
0x1800678da  lea     rcx, [rax+rax*2]
0x1800678de  lea     rcx, [r8+rcx*8]; pvargDest
0x1800678e2  call    cs:__imp_VariantCopy
0x1800678e9  nop     dword ptr [rax+rax+00h]
0x1800678ee  mov     ebx, eax
0x1800678f0  test    eax, eax
0x1800678f2  js      loc_1800677A6
0x1800678f8  mov     r9d, [rbp+57h+var_90]
0x1800678fc  mov     eax, [rbp+57h+var_8C]
0x1800678ff  mov     rcx, [rbp+57h+var_60]
0x180067903  inc     eax
0x180067905  mov     r8, [rbp+57h+var_58]
0x180067909  inc     r9d
0x18006790c  mov     rdx, [rbp+57h+var_78]
0x180067910  mov     [rbp+57h+var_90], r9d
0x180067914  jmp     short loc_1800678C7
0x180067916  mov     rdx, [rcx+10h]; struct CHashTable *
0x18006791a  mov     rcx, r14; this
0x18006791d  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180067922  mov     ebx, eax
0x180067924  test    eax, eax
0x180067926  js      loc_1800677A6
0x18006792c  mov     eax, [rbp+57h+var_88]
0x18006792f  mov     r9d, [rbp+57h+var_90]
0x180067933  inc     eax
0x180067935  jmp     loc_18006789A
0x18006793a  mov     rdx, r13; struct CHashTable *
0x18006793d  mov     rcx, r14; this
0x180067940  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180067945  mov     ecx, 60h ; '`'; Size
0x18006794a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006794f  test    rax, rax
0x180067952  jz      short loc_18006799A
0x180067954  mov     rcx, rax; this
0x180067957  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x18006795c  mov     rdi, rax
0x18006795f  test    rax, rax
0x180067962  jz      short loc_18006799C
0x180067964  mov     rbx, [rbp+57h+arg_0]
0x180067968  mov     [rax+18h], r12
  ... truncated ...
```
