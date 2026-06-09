# CImpDyn::EnumPropDoFunc(long,IWbemClassObject *,FUNCTYPE,ushort *,CIndexCache *,IWbemClassObject *)

- ea: `0x1800038e0`
- end: `0x180003f30`
- name: `?EnumPropDoFunc@CImpDyn@@QEAAJJPEAUIWbemClassObject@@W4FUNCTYPE@@PEAGPEAVCIndexCache@@0@Z`
- size: `1616`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, __int64, int, unsigned __int16 *, struct CIndexCache *, struct IWbemClassObject *)`
- caller_count: `4`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003440`
- `0x180003700`
- `0x18000e2b0`
- `0x18000e370`

## callees

- `0x180001100`
- `0x180001490`
- `0x180002e10`
- `0x1800038e0`
- `0x180003f40`
- `0x1800040c8`
- `0x1800091e0`
- `0x180009d80`
- `0x18000b178`
- `0x180017010`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003cbe`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003e24`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003e90`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003e9e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003eb1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003cbe`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003e24`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003e90`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003e9e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180003eb1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003b0c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003bcc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003ce4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003b0c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003bcc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003ce4`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003e3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003e3b`
- `OLEAUT32!__imp_VariantInit` at `0x18000393a`
- `OLEAUT32!__imp_VariantInit` at `0x18000395f`
- `OLEAUT32!__imp_VariantInit` at `0x180003a50`
- `OLEAUT32!__imp_VariantInit` at `0x18000393a`
- `OLEAUT32!__imp_VariantInit` at `0x18000395f`
- `OLEAUT32!__imp_VariantInit` at `0x180003a50`
- `OLEAUT32!__imp_VariantClear` at `0x1800039e7`
- `OLEAUT32!__imp_VariantClear` at `0x1800039e7`

## pseudocode

```c
__int64 __fastcall CImpDyn::EnumPropDoFunc(
        _QWORD *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        unsigned __int16 *a5,
        struct CIndexCache *a6,
        struct IWbemClassObject *a7)
{
  unsigned __int16 *v11; // r14
  int v12; // ebx
  __int64 v13; // rcx
  struct IWbemClassObject *v15; // rbx
  unsigned __int16 *v16; // rsi
  int v17; // ebx
  CImpDyn *v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // ebx
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rdi
  OLECHAR *KeyName; // r13
  int v24; // ebx
  __int64 v25; // rcx
  unsigned int v26; // ebx
  unsigned __int16 *v27; // rax
  int v28; // ebx
  int v29; // r13d
  CImpDyn *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  char v33; // al
  CProvObj *v34; // rcx
  int v35; // eax
  unsigned int Status; // eax
  __int64 v37; // r9
  int v38; // eax
  int v39; // eax
  char v40; // dl
  char v41; // [rsp+50h] [rbp-91h]
  CProvObj *v42; // [rsp+58h] [rbp-89h]
  int v43; // [rsp+60h] [rbp-81h]
  BSTR bstrString; // [rsp+68h] [rbp-79h] BYREF
  unsigned __int16 *v45; // [rsp+70h] [rbp-71h] BYREF
  unsigned __int16 *v46; // [rsp+78h] [rbp-69h] BYREF
  unsigned __int16 *v47; // [rsp+80h] [rbp-61h]
  __int64 v48; // [rsp+88h] [rbp-59h] BYREF
  VARIANTARG v49; // [rsp+90h] [rbp-51h] BYREF
  void **v50; // [rsp+B0h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-29h] BYREF
  int v52; // [rsp+D0h] [rbp-11h]
  BOOL v53; // [rsp+D4h] [rbp-Dh]
  __int64 v54; // [rsp+D8h] [rbp-9h] BYREF
  CProvObj *v55; // [rsp+E0h] [rbp-1h]

  v11 = 0;
  bstrString = 0;
  v47 = 0;
  v43 = 0;
  v50 = &CVariant::`vftable';
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  if ( a7 )
    goto LABEL_8;
  memset(&v49, 0, sizeof(v49));
  VariantInit(&v49);
  v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a3 + 32LL))(
          a3,
          L"__Class",
          0,
          &v49,
          0,
          0);
  if ( !v12 )
  {
    v13 = a1[3];
    if ( !v13 )
    {
LABEL_5:
      CVariant::~CVariant((CVariant *)&v50);
      return 2147749889LL;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, LONGLONG, _QWORD, _QWORD, struct IWbemClassObject **, _QWORD))(*(_QWORD *)v13 + 48LL))(
            v13,
            v49.llVal,
            0,
            0,
            &a7,
            0);
    VariantClear(&v49);
    if ( v12 < 0 )
      goto LABEL_3;
    v43 = 1;
LABEL_8:
    v48 = 0;
    v53 = a4 == 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD *, _QWORD, __int64, __int64 *, BOOL))(*a1 + 256LL))(
           a1,
           a2,
           a3,
           &v48,
           v53) )
    {
      goto LABEL_5;
    }
    v42 = 0;
    v15 = a7;
    v54 = 0;
    *(_QWORD *)&v49.vt = &CVariant::`vftable';
    VariantInit((VARIANTARG *)&v49.decVal.8);
    v49.pRecInfo = 0;
    v16 = 0;
    if ( ((int (__fastcall *)(struct IWbemClassObject *, __int64 *))v15->lpVtbl->GetQualifierSet)(v15, &v54) >= 0
      && (v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, CY *, _QWORD))(*(_QWORD *)v54 + 24LL))(
                  v54,
                  L"classcontext",
                  0,
                  &v49.cyVal,
                  0),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54),
          v17 >= 0)
      && v49.iVal == 8 )
    {
      v19 = -1;
      do
        ++v19;
      while ( *((_WORD *)&v49.pRecInfo->lpVtbl + v19) );
      v20 = v19 + 1;
      v21 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v19 + 1), 2u));
      v16 = v21;
      if ( v21 )
        StringCchCopyW(v21, v20, (const unsigned __int16 *)v49.pRecInfo);
      *(_QWORD *)&v49.vt = &CVariant::`vftable';
      OMSVariantClear((struct tagVARIANT *)&v49.decVal.8);
      *(_QWORD *)&v49.vt = &CObject::`vftable';
    }
    else
    {
      CVariant::~CVariant((CVariant *)&v49);
    }
    v22 = a5;
    if ( a5 )
    {
      v11 = a5;
    }
    else
    {
      KeyName = CImpDyn::GetKeyName(v18, a7);
      if ( KeyName )
      {
        v24 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a3 + 32LL))(
                a3,
                KeyName,
                0,
                &pvarg,
                0,
                0);
        SysFreeString(KeyName);
        if ( !v24 && pvarg.vt == 8 && pvarg.llVal )
        {
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)(pvarg.llVal + 2 * v25) );
          v26 = v25 + 1;
          v27 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v25 + 1), 2u));
          v11 = v27;
          if ( !v27 )
          {
            v34 = 0;
            goto LABEL_66;
          }
          StringCchCopyW(v27, v26, pvarg.bstrVal);
        }
        OMSVariantClear(&pvarg);
      }
    }
    v28 = 0;
    v41 = 0;
    v29 = 0;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a3 + 64LL))(a3, 0);
    while ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, BSTR *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a3 + 72LL))(
               a3,
               0,
               &bstrString,
               &pvarg,
               0,
               0) )
    {
      OMSVariantClear(&pvarg);
      v46 = 0;
      if ( (unsigned int)CImpDyn::GetAttString(v30, a7, bstrString, L"propertycontext", &v46, a6, v29) )
      {
        v47 = v46;
      }
      else
      {
        v45 = 0;
        v31 = *a1;
        v47 = v46;
        v32 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int16 **, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *))(v31 + 280))(
                a1,
                &v45,
                v16,
                v11,
                v46);
        v52 = v32;
        if ( v46 )
        {
          CWin32DefaultArena::WbemMemFree(v46);
          v47 = 0;
          v32 = v52;
        }
        if ( !v32 )
        {
          if ( v42 )
          {
            if ( !(unsigned int)CProvObj::Update(v42, v45) )
              break;
          }
          else
          {
            v55 = (CProvObj *)CWin32DefaultArena::WbemMemAlloc(0x68u);
            if ( v55 )
            {
              v33 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 288LL))(a1);
              v34 = CProvObj::CProvObj(v55, v45, 0x7Cu, v33);
            }
            else
            {
              v34 = 0;
            }
            v42 = v34;
            if ( !v34 )
              goto LABEL_61;
          }
          v35 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 232LL))(a1);
          Status = CProvObj::dwGetStatus(v42, v35);
          if ( a4 )
          {
            if ( a4 == 1 && !Status )
            {
              v39 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64, BSTR, __int64, __int64, _QWORD))(*a1 + 248LL))(
                      a1,
                      a2,
                      a3,
                      bstrString,
                      v37,
                      v48,
                      0);
              if ( v39 )
              {
                v40 = v41;
                if ( v39 == 5 )
                  v40 = 1;
                v41 = v40;
              }
              else
              {
                ++v28;
              }
            }
          }
          else if ( !Status )
          {
            v38 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64, BSTR, __int64, __int64, _QWORD, _DWORD))(*a1 + 240LL))(
                    a1,
                    a2,
                    a3,
                    bstrString,
                    v37,
                    v48,
                    0,
                    0);
            if ( v38 )
            {
              if ( v38 == 5 )
                v41 = 1;
            }
            else
            {
              ++v28;
            }
          }
          if ( v45 )
            CWin32DefaultArena::WbemMemFree(v45);
        }
      }
      ++v29;
      SysFreeString(bstrString);
    }
    v34 = v42;
LABEL_61:
    v22 = a5;
    if ( v28 > 0 )
    {
      v12 = 0;
LABEL_67:
      if ( v34 )
        (**(void (__fastcall ***)(CProvObj *, __int64))v34)(v34, 1);
      if ( v47 )
        CWin32DefaultArena::WbemMemFree(v47);
      if ( v16 )
        CWin32DefaultArena::WbemMemFree(v16);
      if ( v11 && !v22 )
        CWin32DefaultArena::WbemMemFree(v11);
      if ( v43 )
        ((void (__fastcall *)(struct IWbemClassObject *))a7->lpVtbl->Release)(a7);
      (*(void (__fastcall **)(_QWORD *, _QWORD, __int64, __int64, BOOL))(*a1 + 264LL))(a1, a2, a3, v48, v53);
      v50 = &CVariant::`vftable';
      OMSVariantClear(&pvarg);
      v50 = &CObject::`vftable';
      return (unsigned int)v12;
    }
    if ( v41 )
    {
      v12 = -2147217405;
      goto LABEL_67;
    }
LABEL_66:
    v12 = -2147217350;
    goto LABEL_67;
  }
LABEL_3:
  CVariant::~CVariant((CVariant *)&v50);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800038e0  mov     [rsp-8+arg_0], rbx
0x1800038e5  mov     [rsp-8+arg_18], r9d
0x1800038ea  mov     [rsp-8+arg_8], edx
0x1800038ee  push    rbp
0x1800038ef  push    rsi
0x1800038f0  push    rdi
0x1800038f1  push    r12
0x1800038f3  push    r13
0x1800038f5  push    r14
0x1800038f7  push    r15
0x1800038f9  lea     rbp, [rsp-0Fh]
0x1800038fe  sub     rsp, 0F0h
0x180003905  mov     esi, r9d
0x180003908  mov     r15, r8
0x18000390b  mov     edi, edx
0x18000390d  mov     r12, rcx
0x180003910  xor     r14d, r14d
0x180003913  mov     [rbp+3Fh+bstrString], r14
0x180003917  mov     [rbp+3Fh+var_A0], r14
0x18000391b  mov     [rsp+120h+var_C0], r14d
0x180003920  lea     r13, ??_7CObject@@6B@; const CObject::`vftable'
0x180003927  mov     [rbp+3Fh+var_70], r13
0x18000392b  lea     rax, ??_7CVariant@@6B@; const CVariant::`vftable'
0x180003932  mov     [rbp+3Fh+var_70], rax
0x180003936  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18000393a  call    cs:__imp_VariantInit
0x180003940  xor     eax, eax
0x180003942  mov     qword ptr [rbp+3Fh+pvarg+8], rax
0x180003946  cmp     [rbp+3Fh+arg_30], rax
0x18000394a  jnz     loc_1800039F9
0x180003950  xorps   xmm0, xmm0
0x180003953  movups  xmmword ptr [rbp+3Fh+var_90], xmm0
0x180003957  mov     qword ptr [rbp+3Fh+var_90+10h], rax
0x18000395b  lea     rcx, [rbp+3Fh+var_90]; pvarg
0x18000395f  call    cs:__imp_VariantInit
0x180003965  mov     rax, [r15]
0x180003968  mov     [rsp+120h+var_F8], r14
0x18000396d  mov     [rsp+120h+var_100], r14
0x180003972  lea     r9, [rbp+3Fh+var_90]
0x180003976  xor     r8d, r8d
0x180003979  lea     rdx, aClass; "__Class"
0x180003980  mov     rcx, r15
0x180003983  mov     rax, [rax+20h]
0x180003987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000398c  mov     ebx, eax
0x18000398e  test    eax, eax
0x180003990  jz      short loc_1800039A0
0x180003992  lea     rcx, [rbp+3Fh+var_70]; this
0x180003996  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x18000399b  jmp     loc_180003F13
0x1800039a0  mov     rcx, [r12+18h]
0x1800039a5  test    rcx, rcx
0x1800039a8  jnz     short loc_1800039BD
0x1800039aa  lea     rcx, [rbp+3Fh+var_70]; this
0x1800039ae  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x1800039b3  mov     eax, 80041001h
0x1800039b8  jmp     loc_180003F15
0x1800039bd  mov     rax, [rcx]
0x1800039c0  mov     [rsp+120h+var_F8], r14
0x1800039c5  lea     rdx, [rbp+3Fh+arg_30]
0x1800039c9  mov     [rsp+120h+var_100], rdx
0x1800039ce  xor     r9d, r9d
0x1800039d1  xor     r8d, r8d
0x1800039d4  mov     rdx, qword ptr [rbp+3Fh+var_90+8]
0x1800039d8  mov     rax, [rax+30h]
0x1800039dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039e1  mov     ebx, eax
0x1800039e3  lea     rcx, [rbp+3Fh+var_90]; pvarg
0x1800039e7  call    cs:__imp_VariantClear
0x1800039ed  test    ebx, ebx
0x1800039ef  js      short loc_180003992
0x1800039f1  mov     [rsp+120h+var_C0], 1
0x1800039f9  mov     [rbp+3Fh+var_98], r14
0x1800039fd  mov     ecx, r14d
0x180003a00  test    esi, esi
0x180003a02  setz    cl
0x180003a05  mov     [rbp+3Fh+var_4C], ecx
0x180003a08  mov     rax, [r12]
0x180003a0c  mov     dword ptr [rsp+120h+var_100], ecx
0x180003a10  lea     r9, [rbp+3Fh+var_98]
0x180003a14  mov     r8, r15
0x180003a17  mov     edx, edi
0x180003a19  mov     rcx, r12
0x180003a1c  mov     rax, [rax+100h]
0x180003a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a28  test    eax, eax
0x180003a2a  jnz     loc_1800039AA
0x180003a30  mov     [rsp+120h+var_C8], r14
0x180003a35  mov     rbx, [rbp+3Fh+arg_30]
0x180003a39  mov     [rbp+3Fh+var_48], r14
0x180003a3d  mov     qword ptr [rbp+3Fh+var_90], r13
0x180003a41  lea     rdi, ??_7CVariant@@6B@; const CVariant::`vftable'
0x180003a48  mov     qword ptr [rbp+3Fh+var_90], rdi
0x180003a4c  lea     rcx, [rbp+3Fh+var_90+8]; pvarg
0x180003a50  call    cs:__imp_VariantInit
0x180003a56  xor     eax, eax
0x180003a58  mov     qword ptr [rbp+3Fh+var_90+10h], rax
0x180003a5c  mov     rsi, r14
0x180003a5f  mov     rax, [rbx]
0x180003a62  lea     rdx, [rbp+3Fh+var_48]
0x180003a66  mov     rcx, rbx
0x180003a69  mov     rax, [rax+18h]
0x180003a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a72  test    eax, eax
0x180003a74  jns     short loc_180003A84
0x180003a76  lea     rcx, [rbp+3Fh+var_90]; this
0x180003a7a  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x180003a7f  jmp     loc_180003B3B
0x180003a84  mov     rcx, [rbp+3Fh+var_48]
0x180003a88  mov     rax, [rcx]
0x180003a8b  mov     [rsp+120h+var_100], r14
0x180003a90  lea     r9, [rbp+3Fh+var_90+8]
0x180003a94  xor     r8d, r8d
0x180003a97  lea     rdx, aClasscontext; "classcontext"
0x180003a9e  mov     rax, [rax+18h]
0x180003aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa7  mov     ebx, eax
0x180003aa9  mov     rcx, [rbp+3Fh+var_48]
0x180003aad  mov     rdx, [rcx]
0x180003ab0  mov     rax, [rdx+10h]
0x180003ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab9  test    ebx, ebx
0x180003abb  jns     short loc_180003AC8
0x180003abd  lea     rcx, [rbp+3Fh+var_90]; this
0x180003ac1  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x180003ac6  jmp     short loc_180003B3B
0x180003ac8  cmp     word ptr [rbp+3Fh+var_90+8], 8
0x180003acd  jz      short loc_180003ADA
0x180003acf  lea     rcx, [rbp+3Fh+var_90]; this
0x180003ad3  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x180003ad8  jmp     short loc_180003B3B
0x180003ada  mov     rcx, qword ptr [rbp+3Fh+var_90+10h]
0x180003ade  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180003ae5  mov     rax, r8
0x180003ae8  nop     dword ptr [rax+rax+00000000h]
0x180003af0  lea     rax, [rax+1]
0x180003af4  cmp     [rcx+rax*2], si
0x180003af8  jnz     short loc_180003AF0
0x180003afa  lea     ebx, [rax+1]
0x180003afd  mov     eax, 2
0x180003b02  mul     rbx
0x180003b05  cmovb   rax, r8
0x180003b09  mov     rcx, rax
0x180003b0c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003b12  mov     rsi, rax
0x180003b15  test    rax, rax
0x180003b18  jz      short loc_180003B29
0x180003b1a  mov     r8, qword ptr [rbp+3Fh+var_90+10h]; unsigned __int16 *
0x180003b1e  mov     edx, ebx; unsigned __int64
0x180003b20  mov     rcx, rax; unsigned __int16 *
0x180003b23  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003b28  nop
0x180003b29  mov     qword ptr [rbp+3Fh+var_90], rdi
0x180003b2d  lea     rcx, [rbp+3Fh+var_90+8]; struct tagVARIANT *
0x180003b31  call    ?OMSVariantClear@@YAJPEAUtagVARIANT@@@Z; OMSVariantClear(tagVARIANT *)
0x180003b36  nop
0x180003b37  mov     qword ptr [rbp+3Fh+var_90], r13
0x180003b3b  mov     rdi, [rbp+3Fh+arg_20]
0x180003b3f  test    rdi, rdi
0x180003b42  jz      short loc_180003B4C
0x180003b44  mov     r14, rdi
0x180003b47  jmp     loc_180003BF5
0x180003b4c  mov     rdx, [rbp+3Fh+arg_30]; struct IWbemClassObject *
0x180003b50  call    ?GetKeyName@CImpDyn@@QEAAPEAGPEAUIWbemClassObject@@@Z; CImpDyn::GetKeyName(IWbemClassObject *)
0x180003b55  mov     r13, rax
0x180003b58  test    rax, rax
0x180003b5b  jz      loc_180003BF5
0x180003b61  mov     rcx, [r15]
0x180003b64  mov     rax, [rcx+20h]
0x180003b68  xor     ecx, ecx
0x180003b6a  mov     [rsp+120h+var_F8], rcx
0x180003b6f  mov     [rsp+120h+var_100], rcx
0x180003b74  lea     r9, [rbp+3Fh+pvarg]
0x180003b78  xor     r8d, r8d
0x180003b7b  mov     rdx, r13
0x180003b7e  mov     rcx, r15
0x180003b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b86  mov     ebx, eax
0x180003b88  mov     rcx, r13; bstrString
0x180003b8b  call    cs:__imp_SysFreeString
0x180003b91  test    ebx, ebx
0x180003b93  jnz     short loc_180003BEC
0x180003b95  cmp     word ptr [rbp+3Fh+pvarg], 8
0x180003b9a  jnz     short loc_180003BEC
0x180003b9c  mov     rdx, qword ptr [rbp+3Fh+pvarg+8]
0x180003ba0  test    rdx, rdx
0x180003ba3  jz      short loc_180003BEC
0x180003ba5  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180003bac  mov     rcx, r8
0x180003baf  lea     rcx, [rcx+1]
0x180003bb3  cmp     word ptr [rdx+rcx*2], 0
0x180003bb8  jnz     short loc_180003BAF
0x180003bba  lea     ebx, [rcx+1]
0x180003bbd  mov     eax, 2
0x180003bc2  mul     rbx
0x180003bc5  cmovb   rax, r8
0x180003bc9  mov     rcx, rax
0x180003bcc  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003bd2  mov     r14, rax
0x180003bd5  test    rax, rax
0x180003bd8  jz      loc_180003E65
0x180003bde  mov     r8, qword ptr [rbp+3Fh+pvarg+8]; unsigned __int16 *
0x180003be2  mov     edx, ebx; unsigned __int64
0x180003be4  mov     rcx, rax; unsigned __int16 *
0x180003be7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003bec  lea     rcx, [rbp+3Fh+pvarg]; struct tagVARIANT *
0x180003bf0  call    ?OMSVariantClear@@YAJPEAUtagVARIANT@@@Z; OMSVariantClear(tagVARIANT *)
0x180003bf5  xor     ebx, ebx
0x180003bf7  mov     [rsp+120h+var_D0], bl
0x180003bfb  xor     r13d, r13d
0x180003bfe  mov     rax, [r15]
0x180003c01  xor     edx, edx
0x180003c03  mov     rcx, r15
0x180003c06  mov     rax, [rax+40h]
0x180003c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c0f  mov     rdi, [rbp+3Fh+arg_28]
0x180003c13  mov     rax, [r15]
0x180003c16  xor     ecx, ecx
0x180003c18  mov     [rsp+120h+var_F8], rcx
0x180003c1d  mov     [rsp+120h+var_100], rcx
0x180003c22  lea     r9, [rbp+3Fh+pvarg]
0x180003c26  lea     r8, [rbp+3Fh+bstrString]
0x180003c2a  xor     edx, edx
0x180003c2c  mov     rcx, r15
0x180003c2f  mov     rax, [rax+48h]
0x180003c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c38  test    eax, eax
0x180003c3a  jnz     loc_180003E46
0x180003c40  lea     rcx, [rbp+3Fh+pvarg]; struct tagVARIANT *
0x180003c44  call    ?OMSVariantClear@@YAJPEAUtagVARIANT@@@Z; OMSVariantClear(tagVARIANT *)
0x180003c49  mov     [rbp+3Fh+var_A8], 0
0x180003c51  mov     [rsp+120h+var_F0], r13d; int
0x180003c56  mov     [rsp+120h+var_F8], rdi; struct CIndexCache *
0x180003c5b  lea     rax, [rbp+3Fh+var_A8]
0x180003c5f  mov     [rsp+120h+var_100], rax; unsigned __int16 **
0x180003c64  lea     r9, aPropertycontex; "propertycontext"
0x180003c6b  mov     r8, [rbp+3Fh+bstrString]; unsigned __int16 *
0x180003c6f  mov     rdx, [rbp+3Fh+arg_30]; struct IWbemClassObject *
0x180003c73  call    ?GetAttString@CImpDyn@@QEAAJPEAUIWbemClassObject@@PEAG1PEAPEAGPEAVCIndexCache@@H@Z; CImpDyn::GetAttString(IWbemClassObject *,ushort *,ushort *,ushort * *,CIndexCache *,int)
0x180003c78  test    eax, eax
0x180003c7a  jnz     loc_180003E2C
0x180003c80  mov     [rbp+3Fh+var_B0], 0
0x180003c88  mov     rax, [r12]
0x180003c8c  mov     rcx, [rbp+3Fh+var_A8]
0x180003c90  mov     [rbp+3Fh+var_A0], rcx
0x180003c94  mov     [rsp+120h+var_100], rcx
0x180003c99  mov     r9, r14
0x180003c9c  mov     r8, rsi
0x180003c9f  lea     rdx, [rbp+3Fh+var_B0]
0x180003ca3  mov     rcx, r12
0x180003ca6  mov     rax, [rax+118h]
0x180003cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb2  mov     [rbp+3Fh+var_50], eax
0x180003cb5  mov     rcx, [rbp+3Fh+var_A8]
0x180003cb9  test    rcx, rcx
0x180003cbc  jz      short loc_180003CCD
0x180003cbe  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180003cc4  xor     eax, eax
0x180003cc6  mov     [rbp+3Fh+var_A0], rax
0x180003cca  mov     eax, [rbp+3Fh+var_50]
0x180003ccd  test    eax, eax
0x180003ccf  jnz     loc_180003E34
0x180003cd5  mov     rcx, [rsp+120h+var_C8]; this
0x180003cda  test    rcx, rcx
0x180003cdd  jnz     short loc_180003D33
0x180003cdf  mov     ecx, 68h ; 'h'
0x180003ce4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003cea  mov     [rbp+3Fh+var_40], rax
0x180003cee  test    rax, rax
0x180003cf1  jz      short loc_180003D22
0x180003cf3  mov     rcx, [r12]
0x180003cf7  mov     rax, [rcx+120h]
0x180003cfe  mov     rcx, r12
0x180003d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d06  mov     r8d, 7Ch ; '|'; unsigned __int16
0x180003d0c  movzx   r9d, al; bool
0x180003d10  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int16 *
0x180003d14  mov     rcx, [rbp+3Fh+var_40]; this
0x180003d18  call    ??0CProvObj@@QEAA@PEBGG_N@Z; CProvObj::CProvObj(ushort const *,ushort,bool)
0x180003d1d  mov     rcx, rax
0x180003d20  jmp     short loc_180003D24
0x180003d22  xor     ecx, ecx
0x180003d24  mov     [rsp+120h+var_C8], rcx
0x180003d29  test    rcx, rcx
0x180003d2c  jnz     short loc_180003D44
0x180003d2e  jmp     loc_180003E4B
0x180003d33  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int16 *
0x180003d37  call    ?Update@CProvObj@@QEAAHPEAG@Z; CProvObj::Update(ushort *)
0x180003d3c  test    eax, eax
0x180003d3e  jz      loc_180003E46
0x180003d44  mov     rax, [r12]
0x180003d48  mov     rcx, r12
0x180003d4b  mov     rax, [rax+0E8h]
0x180003d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d57  mov     edx, eax; int
0x180003d59  mov     r9, [rsp+120h+var_C8]
0x180003d5e  mov     rcx, r9; this
0x180003d61  call    ?dwGetStatus@CProvObj@@QEAAKH@Z; CProvObj::dwGetStatus(int)
0x180003d66  mov     ecx, [rbp+3Fh+arg_18]
0x180003d69  test    ecx, ecx
  ... truncated ...
```
