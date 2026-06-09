# ConvertDispatchToArray(tagVARIANT *,tagVARIANT *,long,int,ushort)

- ea: `0x180025414`
- end: `0x1800257e4`
- name: `?ConvertDispatchToArray@@YAJPEAUtagVARIANT@@0JHG@Z`
- size: `976`
- prototype: `int(struct tagVARIANT *, struct tagVARIANT *, int, int, unsigned __int16)`
- caller_count: `5`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002df8`
- `0x180020de0`
- `0x180020ff0`
- `0x180023590`
- `0x180025c74`

## callees

- `0x180002ef4`
- `0x18000c0b0`
- `0x180019114`
- `0x180024ff4`
- `0x180025034`
- `0x180025414`
- `0x180025aa4`
- `0x180036010`

## import_xrefs

- `msvcrt!wcstol` at `0x1800255b1`
- `msvcrt!wcstol` at `0x180025659`
- `msvcrt!wcstol` at `0x1800255b1`
- `msvcrt!wcstol` at `0x180025659`
- `OLEAUT32!__imp_SysFreeString` at `0x180025670`
- `OLEAUT32!__imp_SysFreeString` at `0x180025678`
- `OLEAUT32!__imp_SysFreeString` at `0x180025670`
- `OLEAUT32!__imp_SysFreeString` at `0x180025678`
- `OLEAUT32!__imp_VariantInit` at `0x180025514`
- `OLEAUT32!__imp_VariantInit` at `0x18002569d`
- `OLEAUT32!__imp_VariantInit` at `0x18002575d`
- `OLEAUT32!__imp_VariantInit` at `0x180025797`
- `OLEAUT32!__imp_VariantInit` at `0x180025514`
- `OLEAUT32!__imp_VariantInit` at `0x18002569d`
- `OLEAUT32!__imp_VariantInit` at `0x18002575d`
- `OLEAUT32!__imp_VariantInit` at `0x180025797`
- `OLEAUT32!__imp_VariantClear` at `0x180025579`
- `OLEAUT32!__imp_VariantClear` at `0x180025742`
- `OLEAUT32!__imp_VariantClear` at `0x180025579`
- `OLEAUT32!__imp_VariantClear` at `0x180025742`
- `OLEAUT32!__imp_VariantChangeType` at `0x180025705`
- `OLEAUT32!__imp_VariantChangeType` at `0x180025705`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800255de`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800255de`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002576b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002576b`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180025735`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180025735`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConvertDispatchToArray(
        struct tagVARIANT *a1,
        struct tagVARIANT *a2,
        int a3,
        int a4,
        unsigned __int16 a5)
{
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rax
  int v7; // r12d
  LONGLONG llVal; // rsi
  unsigned int v9; // edi
  unsigned __int16 AcceptableQualType; // bx
  signed int v11; // r14d
  SAFEARRAY *v12; // rsi
  int v13; // eax
  HRESULT v14; // r14d
  void *bstrVal; // r8
  __int64 v17; // [rsp+50h] [rbp-41h] BYREF
  wchar_t *String; // [rsp+58h] [rbp-39h] BYREF
  wchar_t *EndPtr; // [rsp+60h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-29h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+80h] [rbp-11h] BYREF
  wchar_t *v22; // [rsp+88h] [rbp-9h] BYREF
  __int64 v23; // [rsp+90h] [rbp-1h] BYREF
  __int128 v24; // [rsp+98h] [rbp+7h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+17h]
  unsigned int v27; // [rsp+F8h] [rbp+67h] BYREF

  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a2->llVal;
  v7 = 0;
  if ( a2->vt != 9 )
  {
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)p_llVal->llVal;
    if ( !p_llVal )
      return 2147749889LL;
  }
  llVal = p_llVal->llVal;
  if ( !p_llVal->llVal )
    return 2147749889LL;
  v9 = -2147217407;
  AcceptableQualType = 10;
  if ( a3 != 4095 )
    AcceptableQualType = CimTypeToVtType(a3);
  ATL::CComQIPtr<IDispatchEx,&__s_GUID const _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9>::CComQIPtr<IDispatchEx,&__s_GUID const _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9>(&v17);
  if ( !v17 )
    goto LABEL_47;
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(
    &v23,
    llVal);
  if ( v23 )
    goto LABEL_46;
  v11 = 0;
  v27 = -1;
  v24 = 0;
  v25 = 0;
  while ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v17 + 104LL))(
             v17,
             2,
             v27,
             &v27) )
  {
    if ( !v11 && AcceptableQualType == 10 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
             v17,
             v27,
             0,
             2,
             &v24,
             &pvarg,
             0,
             0) >= 0 )
      {
        if ( a4 )
        {
          AcceptableQualType = GetAcceptableQualType(pvarg.vt);
        }
        else
        {
          AcceptableQualType = pvarg.vt;
          if ( pvarg.vt == 9 )
            AcceptableQualType = 13;
        }
      }
      VariantClear(&pvarg);
    }
    String = 0;
    EndPtr = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)v17 + 96LL))(v17, v27, &String) >= 0 )
    {
      wcstol(String, &EndPtr, 10);
      if ( !*EndPtr )
        ++v11;
    }
  }
  rgsabound.cElements = v11;
  rgsabound.lLbound = 0;
  v12 = SafeArrayCreate(AcceptableQualType, 1u, &rgsabound);
  if ( v11 <= 0 )
  {
    if ( a4 )
    {
      AcceptableQualType = a5;
      if ( a5 == 1 )
        AcceptableQualType = 3;
    }
    else
    {
      AcceptableQualType = 12;
    }
LABEL_45:
    VariantInit(a1);
    v9 = 0;
    a1->llVal = (LONGLONG)v12;
    a1->vt = AcceptableQualType | 0x2000;
    goto LABEL_46;
  }
  v27 = -1;
  v22 = 0;
  while ( 1 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v17 + 104LL))(
            v17,
            2,
            v27,
            &v27);
    if ( v13 )
      break;
    String = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)v17 + 96LL))(v17, v27, &String) >= 0 )
    {
      LODWORD(EndPtr) = wcstol(String, &v22, 10);
      if ( *v22 )
      {
        SysFreeString(String);
      }
      else
      {
        SysFreeString(String);
        String = 0;
        if ( (_DWORD)EndPtr != v7 )
          goto LABEL_40;
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
               v17,
               v27,
               0,
               2,
               &v24,
               &pvarg,
               0,
               0) < 0 )
          goto LABEL_40;
        ++v7;
        v14 = -2147217407;
        if ( !(unsigned int)MapToCIMOMObject(&pvarg) && !VariantChangeType(&pvarg, &pvarg, 0, AcceptableQualType) )
        {
          if ( AcceptableQualType == 8 )
            goto LABEL_35;
          if ( AcceptableQualType != 13 )
          {
            bstrVal = &pvarg.decVal.8;
LABEL_36:
            v14 = SafeArrayPutElement(v12, (LONG *)&EndPtr, bstrVal);
            goto LABEL_37;
          }
          if ( !a4 )
          {
LABEL_35:
            bstrVal = pvarg.bstrVal;
            goto LABEL_36;
          }
        }
LABEL_37:
        VariantClear(&pvarg);
        if ( v14 < 0 )
          goto LABEL_40;
      }
    }
  }
  if ( v13 == 1 )
    goto LABEL_45;
LABEL_40:
  SafeArrayDestroy(v12);
  v9 = -2147217400;
LABEL_46:
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v23);
LABEL_47:
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v17);
  return v9;
}

```

## disassembly

```asm
0x180025414  mov     [rsp-8+arg_10], rbx
0x180025419  mov     [rsp-8+arg_0], rcx
0x18002541e  push    rbp
0x18002541f  push    rsi
0x180025420  push    rdi
0x180025421  push    r12
0x180025423  push    r13
0x180025425  push    r14
0x180025427  push    r15
0x180025429  lea     rbp, [rsp-1Fh]
0x18002542e  sub     rsp, 0B0h
0x180025435  mov     r13d, r9d
0x180025438  lea     rax, [rdx+8]
0x18002543c  mov     ecx, 9
0x180025441  xor     r12d, r12d
0x180025444  cmp     cx, [rdx]
0x180025447  jz      short loc_180025455
0x180025449  mov     rax, [rax]
0x18002544c  test    rax, rax
0x18002544f  jz      loc_1800257C4
0x180025455  mov     rsi, [rax]
0x180025458  test    rsi, rsi
0x18002545b  jz      loc_1800257C4
0x180025461  mov     edi, 80041001h
0x180025466  mov     ebx, 0Ah
0x18002546b  cmp     r8d, 0FFFh
0x180025472  jz      short loc_18002547F
0x180025474  mov     ecx, r8d; int
0x180025477  call    ?CimTypeToVtType@@YAGJ@Z; CimTypeToVtType(long)
0x18002547c  movzx   ebx, ax
0x18002547f  mov     rdx, rsi
0x180025482  lea     rcx, [rbp+4Fh+var_90]
0x180025486  call    ??0?$CComQIPtr@UIDispatchEx@@$1?_GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IDispatchEx,&__s_GUID const _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9>::CComQIPtr<IDispatchEx,&__s_GUID const _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9>(IUnknown *)
0x18002548b  nop
0x18002548c  cmp     [rbp+4Fh+var_90], r12
0x180025490  jz      loc_1800257B7
0x180025496  mov     rdx, rsi
0x180025499  lea     rcx, [rbp+4Fh+var_50]
0x18002549d  call    ??0?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(IUnknown *)
0x1800254a2  nop
0x1800254a3  cmp     [rbp+4Fh+var_50], r12
0x1800254a7  jnz     loc_1800257AD
0x1800254ad  mov     r14d, r12d
0x1800254b0  mov     [rbp+4Fh+arg_8], 0FFFFFFFFh
0x1800254b7  xorps   xmm0, xmm0
0x1800254ba  movdqu  [rbp+4Fh+var_48], xmm0
0x1800254bf  mov     [rbp+4Fh+var_38], r12
0x1800254c3  mov     esi, 1
0x1800254c8  lea     edi, [rsi+8]
0x1800254cb  lea     r15d, [rsi+9]
0x1800254cf  mov     rcx, [rbp+4Fh+var_90]
0x1800254d3  mov     rax, [rcx]
0x1800254d6  lea     r9, [rbp+4Fh+arg_8]
0x1800254da  mov     r8d, [rbp+4Fh+arg_8]
0x1800254de  mov     edx, 2
0x1800254e3  mov     rax, [rax+68h]
0x1800254e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254ec  test    eax, eax
0x1800254ee  jnz     loc_1800255CD
0x1800254f4  test    r14d, r14d
0x1800254f7  jnz     loc_18002557F
0x1800254fd  cmp     r15w, bx
0x180025501  jnz     short loc_18002557F
0x180025503  xorps   xmm0, xmm0
0x180025506  xor     eax, eax
0x180025508  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x18002550c  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x180025510  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180025514  call    cs:__imp_VariantInit
0x18002551a  mov     rcx, [rbp+4Fh+var_90]
0x18002551e  mov     rax, [rcx]
0x180025521  lea     r9d, [r14+2]
0x180025525  mov     [rsp+0E0h+var_A8], r12
0x18002552a  mov     [rsp+0E0h+var_B0], r12
0x18002552f  lea     rdx, [rbp+4Fh+pvarg]
0x180025533  mov     [rsp+0E0h+var_B8], rdx
0x180025538  lea     rdx, [rbp+4Fh+var_48]
0x18002553c  mov     [rsp+0E0h+var_C0], rdx
0x180025541  xor     r8d, r8d
0x180025544  mov     edx, [rbp+4Fh+arg_8]
0x180025547  mov     rax, [rax+40h]
0x18002554b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025550  test    eax, eax
0x180025552  js      short loc_180025575
0x180025554  test    r13d, r13d
0x180025557  jz      short loc_180025567
0x180025559  movzx   ecx, word ptr [rbp+4Fh+pvarg]; unsigned __int16
0x18002555d  call    ?GetAcceptableQualType@@YAGG@Z; GetAcceptableQualType(ushort)
0x180025562  movzx   ebx, ax
0x180025565  jmp     short loc_180025575
0x180025567  movzx   ebx, word ptr [rbp+4Fh+pvarg]
0x18002556b  cmp     di, bx
0x18002556e  jnz     short loc_180025575
0x180025570  mov     ebx, 0Dh
0x180025575  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180025579  call    cs:__imp_VariantClear
0x18002557f  mov     [rbp+4Fh+String], r12
0x180025583  mov     [rbp+4Fh+EndPtr], r12
0x180025587  mov     rcx, [rbp+4Fh+var_90]
0x18002558b  mov     rax, [rcx]
0x18002558e  lea     r8, [rbp+4Fh+String]
0x180025592  mov     edx, [rbp+4Fh+arg_8]
0x180025595  mov     rax, [rax+60h]
0x180025599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002559e  test    eax, eax
0x1800255a0  js      loc_1800254CF
0x1800255a6  mov     r8d, r15d; Radix
0x1800255a9  lea     rdx, [rbp+4Fh+EndPtr]; EndPtr
0x1800255ad  mov     rcx, [rbp+4Fh+String]; String
0x1800255b1  call    cs:__imp_wcstol
0x1800255b7  mov     rax, [rbp+4Fh+EndPtr]
0x1800255bb  cmp     r12w, [rax]
0x1800255bf  jnz     loc_1800254CF
0x1800255c5  add     r14d, esi
0x1800255c8  jmp     loc_1800254CF
0x1800255cd  mov     [rbp+4Fh+rgsabound.cElements], r14d
0x1800255d1  mov     [rbp+4Fh+rgsabound.lLbound], r12d
0x1800255d5  lea     r8, [rbp+4Fh+rgsabound]; rgsabound
0x1800255d9  mov     edx, esi; cDims
0x1800255db  movzx   ecx, bx; vt
0x1800255de  call    cs:__imp_SafeArrayCreate
0x1800255e4  mov     rsi, rax
0x1800255e7  test    r14d, r14d
0x1800255ea  mov     edi, 80041001h
0x1800255ef  mov     r15, [rbp+4Fh+arg_0]
0x1800255f3  jle     loc_180025778
0x1800255f9  mov     [rbp+4Fh+arg_8], 0FFFFFFFFh
0x180025600  xor     r14d, r14d
0x180025603  mov     [rbp+4Fh+var_58], r14
0x180025607  mov     rcx, [rbp+4Fh+var_90]
0x18002560b  mov     rax, [rcx]
0x18002560e  lea     r9, [rbp+4Fh+arg_8]
0x180025612  mov     r8d, [rbp+4Fh+arg_8]
0x180025616  mov     edx, 2
0x18002561b  mov     rax, [rax+68h]
0x18002561f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025624  test    eax, eax
0x180025626  jnz     loc_180025755
0x18002562c  mov     [rbp+4Fh+String], r14
0x180025630  mov     rcx, [rbp+4Fh+var_90]
0x180025634  mov     rax, [rcx]
0x180025637  lea     r8, [rbp+4Fh+String]
0x18002563b  mov     edx, [rbp+4Fh+arg_8]
0x18002563e  mov     rax, [rax+60h]
0x180025642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025647  test    eax, eax
0x180025649  js      short loc_180025607
0x18002564b  mov     r8d, 0Ah; Radix
0x180025651  lea     rdx, [rbp+4Fh+var_58]; EndPtr
0x180025655  mov     rcx, [rbp+4Fh+String]; String
0x180025659  call    cs:__imp_wcstol
0x18002565f  mov     dword ptr [rbp+4Fh+EndPtr], eax
0x180025662  mov     rax, [rbp+4Fh+var_58]
0x180025666  mov     rcx, [rbp+4Fh+String]; bstrString
0x18002566a  cmp     r14w, [rax]
0x18002566e  jz      short loc_180025678
0x180025670  call    cs:__imp_SysFreeString
0x180025676  jmp     short loc_180025607
0x180025678  call    cs:__imp_SysFreeString
0x18002567e  mov     [rbp+4Fh+String], r14
0x180025682  cmp     dword ptr [rbp+4Fh+EndPtr], r12d
0x180025686  jnz     loc_180025768
0x18002568c  xorps   xmm0, xmm0
0x18002568f  xor     eax, eax
0x180025691  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x180025695  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x180025699  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18002569d  call    cs:__imp_VariantInit
0x1800256a3  mov     rcx, [rbp+4Fh+var_90]
0x1800256a7  mov     rax, [rcx]
0x1800256aa  mov     r9d, 2
0x1800256b0  mov     [rsp+0E0h+var_A8], r14
0x1800256b5  mov     [rsp+0E0h+var_B0], r14
0x1800256ba  lea     rdx, [rbp+4Fh+pvarg]
0x1800256be  mov     [rsp+0E0h+var_B8], rdx
0x1800256c3  lea     rdx, [rbp+4Fh+var_48]
0x1800256c7  mov     [rsp+0E0h+var_C0], rdx
0x1800256cc  xor     r8d, r8d
0x1800256cf  mov     edx, [rbp+4Fh+arg_8]
0x1800256d2  mov     rax, [rax+40h]
0x1800256d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256db  test    eax, eax
0x1800256dd  js      loc_180025768
0x1800256e3  inc     r12d
0x1800256e6  mov     r14d, edi
0x1800256e9  lea     rcx, [rbp+4Fh+pvarg]; struct tagVARIANT *
0x1800256ed  call    ?MapToCIMOMObject@@YAJPEAUtagVARIANT@@@Z; MapToCIMOMObject(tagVARIANT *)
0x1800256f2  test    eax, eax
0x1800256f4  jnz     short loc_18002573E
0x1800256f6  xor     r8d, r8d; wFlags
0x1800256f9  movzx   r9d, bx; vt
0x1800256fd  lea     rdx, [rbp+4Fh+pvarg]; pvarSrc
0x180025701  lea     rcx, [rbp+4Fh+pvarg]; pvargDest
0x180025705  call    cs:__imp_VariantChangeType
0x18002570b  test    eax, eax
0x18002570d  jnz     short loc_18002573E
0x18002570f  cmp     bx, 8
0x180025713  jz      short loc_18002572A
0x180025715  mov     eax, 0Dh
0x18002571a  cmp     bx, ax
0x18002571d  jz      short loc_180025725
0x18002571f  lea     r8, [rbp+4Fh+pvarg+8]
0x180025723  jmp     short loc_18002572E
0x180025725  test    r13d, r13d
0x180025728  jnz     short loc_18002573E
0x18002572a  mov     r8, qword ptr [rbp+4Fh+pvarg+8]; pv
0x18002572e  lea     rdx, [rbp+4Fh+EndPtr]; rgIndices
0x180025732  mov     rcx, rsi; psa
0x180025735  call    cs:__imp_SafeArrayPutElement
0x18002573b  mov     r14d, eax
0x18002573e  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180025742  call    cs:__imp_VariantClear
0x180025748  test    r14d, r14d
0x18002574b  js      short loc_180025768
0x18002574d  xor     r14d, r14d
0x180025750  jmp     loc_180025607
0x180025755  cmp     eax, 1
0x180025758  jnz     short loc_180025768
0x18002575a  mov     rcx, r15; pvarg
0x18002575d  call    cs:__imp_VariantInit
0x180025763  mov     edi, r14d
0x180025766  jmp     short loc_1800257A0
0x180025768  mov     rcx, rsi; psa
0x18002576b  call    cs:__imp_SafeArrayDestroy
0x180025771  mov     edi, 80041008h
0x180025776  jmp     short loc_1800257AD
0x180025778  test    r13d, r13d
0x18002577b  jnz     short loc_180025783
0x18002577d  lea     ebx, [r13+0Ch]
0x180025781  jmp     short loc_180025794
0x180025783  movzx   ebx, [rbp+4Fh+arg_20]
0x180025787  mov     eax, 1
0x18002578c  cmp     ax, bx
0x18002578f  jnz     short loc_180025794
0x180025791  lea     ebx, [rax+2]
0x180025794  mov     rcx, r15; pvarg
0x180025797  call    cs:__imp_VariantInit
0x18002579d  mov     edi, r12d
0x1800257a0  or      bx, 2000h
0x1800257a5  mov     [r15+8], rsi
0x1800257a9  mov     [r15], bx
0x1800257ad  lea     rcx, [rbp+4Fh+var_50]
0x1800257b1  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x1800257b6  nop
0x1800257b7  lea     rcx, [rbp+4Fh+var_90]
0x1800257bb  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x1800257c0  mov     eax, edi
0x1800257c2  jmp     short loc_1800257C9
0x1800257c4  mov     eax, 80041001h
0x1800257c9  mov     rbx, [rsp+0E0h+arg_10]
0x1800257d1  add     rsp, 0B0h
0x1800257d8  pop     r15
0x1800257da  pop     r14
0x1800257dc  pop     r13
0x1800257de  pop     r12
0x1800257e0  pop     rdi
0x1800257e1  pop     rsi
0x1800257e2  pop     rbp
0x1800257e3  retn
```
