# LoadACLFromACEArrayVar(tagVARIANT,CNtAcl * *)

- ea: `0x18003e7c4`
- end: `0x18003efee`
- name: `?LoadACLFromACEArrayVar@@YAJUtagVARIANT@@PEAPEAVCNtAcl@@@Z`
- size: `2090`
- prototype: `__int64 __fastcall(struct tagVARIANT *__struct_ptr, struct CNtAcl **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d310`

## callees

- `0x18000a290`
- `0x180013564`
- `0x180014120`
- `0x18001b8a0`
- `0x18001ba10`
- `0x18001c010`
- `0x18001c290`
- `0x18001d250`
- `0x1800269d4`
- `0x180028484`
- `0x18003a748`
- `0x18003ac1c`
- `0x18003ad10`
- `0x18003c6f8`
- `0x18003cb18`
- `0x18003e7c4`
- `0x18003eff4`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003e93f`
- `OLEAUT32!__imp_VariantInit` at `0x18003e93f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003e9c6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003e9c6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003e956`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003e956`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003ea31`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003ea31`

## string_xrefs

- `0x18003eb1f`: `AccessMask`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LoadACLFromACEArrayVar(struct tagVARIANT *a1, struct CNtAcl **a2)
{
  SAFEARRAY *parray; // r14
  signed int AclSize; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // r10
  __int64 v7; // rdx
  __int64 v8; // r9
  CNtAcl *v9; // rax
  __int64 v10; // rdx
  CNtAcl *v11; // rsi
  HRESULT LBound; // eax
  _QWORD *v13; // rax
  __int64 v14; // rdx
  HRESULT UBound; // eax
  LONG i; // eax
  HRESULT Element; // eax
  __int64 v18; // rax
  signed int v19; // eax
  __int64 (__fastcall *v20)(LONGLONG, GUID *, struct IWbemClassObject **); // rbx
  signed int v21; // eax
  __int64 v22; // rax
  signed int v23; // eax
  LONG lVal; // r12d
  __int64 v25; // rax
  signed int v26; // eax
  LONG v27; // r15d
  __int64 v28; // rax
  signed int v29; // eax
  _QWORD *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r9
  _QWORD *v33; // rax
  __int64 v34; // rdx
  _QWORD *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r9
  VARIANTARG pvarg; // [rsp+40h] [rbp-49h] BYREF
  struct CNtSid *v40; // [rsp+58h] [rbp-31h] BYREF
  LONG plLbound; // [rsp+60h] [rbp-29h] BYREF
  LONG plUbound; // [rsp+64h] [rbp-25h] BYREF
  struct CNtSid *v43; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v44[24]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v45[80]; // [rsp+90h] [rbp+7h] BYREF
  unsigned __int64 rgIndices; // [rsp+F0h] [rbp+67h] BYREF
  CNtAcl *pv; // [rsp+100h] [rbp+77h] BYREF
  struct IWbemClassObject *v48; // [rsp+108h] [rbp+7Fh] BYREF

  rgIndices = 0;
  parray = a1->parray;
  AclSize = GetAclSize(parray, &rgIndices);
  v5 = AclSize;
  if ( AclSize < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, AclSize);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 88;
      v8 = v5;
LABEL_6:
      WPP_SF_D(v6[2], v7, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v8);
      return v5;
    }
    return v5;
  }
  v9 = (CNtAcl *)CWin32DefaultArena::WbemMemAlloc(0x10u);
  pv = v9;
  if ( v9 )
    v11 = CNtAcl::CNtAcl(v9, rgIndices);
  else
    v11 = 0;
  if ( v11 )
  {
    MakeGuard<void (*)(CNtAcl const *),CNtAcl *>(v45, v10, v11);
    if ( !parray )
    {
      v5 = -2147217400;
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0x80041008);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids,
          2147749896LL);
      }
      goto LABEL_108;
    }
    VariantInit(&pvarg);
    plLbound = 0;
    LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
    v5 = LBound;
    if ( LBound >= 0 )
    {
      plUbound = 0;
      UBound = SafeArrayGetUBound(parray, 1u, &plUbound);
      v5 = UBound;
      if ( UBound >= 0 )
      {
        for ( i = plLbound; ; i = rgIndices + 1 )
        {
          LODWORD(rgIndices) = i;
          if ( i > plUbound )
            break;
          pv = 0;
          _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&pv);
          pv = 0;
          Element = SafeArrayGetElement(parray, (LONG *)&rgIndices, &pv);
          v5 = Element;
          if ( Element < 0 )
          {
            CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, Element);
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_106;
            }
            v36 = 93;
LABEL_104:
            v37 = v5;
LABEL_105:
            WPP_SF_D(v35[2], v36, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v37);
            goto LABEL_106;
          }
          if ( pv )
          {
            v18 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(&pv);
            v19 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v18 + 32LL))(
                    v18,
                    L"Trustee",
                    0,
                    &pvarg,
                    0,
                    0);
            v5 = v19;
            if ( v19 < 0 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v19);
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_106;
              }
              v36 = 94;
              goto LABEL_104;
            }
            if ( pvarg.vt != 13 )
            {
              v5 = -2147217400;
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0x80041008);
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_106;
              }
              v36 = 95;
              v37 = 2147749896LL;
              goto LABEL_105;
            }
            v48 = 0;
            v20 = **(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IWbemClassObject **))pvarg.llVal;
            _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v48);
            v48 = 0;
            v5 = v20(pvarg.llVal, &IID_IWbemClassObject, &v48);
            if ( (v5 & 0x80000000) != 0 )
            {
              _variant_t::Clear((_variant_t *)&pvarg);
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v5);
              v33 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_91;
              }
              v34 = 96;
LABEL_90:
              WPP_SF_D(v33[2], v34, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v5);
              goto LABEL_91;
            }
            _variant_t::Clear((_variant_t *)&pvarg);
            v43 = 0;
            v21 = LoadSIDFromTrustee(v48, &v43);
            v5 = v21;
            if ( v21 < 0 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v21);
              v33 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_91;
              }
              v34 = 97;
              goto LABEL_90;
            }
            v40 = v43;
            v22 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(&pv);
            v23 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v22 + 32LL))(
                    v22,
                    L"AccessMask",
                    0,
                    &pvarg,
                    0,
                    0);
            v5 = v23;
            if ( v23 < 0 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v23);
              v30 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_81;
              }
              v31 = 98;
LABEL_79:
              v32 = v5;
LABEL_80:
              WPP_SF_D(v30[2], v31, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v32);
              goto LABEL_81;
            }
            if ( pvarg.vt != 3 )
            {
              v5 = -2147217400;
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0x80041008);
              v30 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_81;
              }
              v31 = 99;
LABEL_74:
              v32 = 2147749896LL;
              goto LABEL_80;
            }
            lVal = pvarg.lVal;
            _variant_t::Clear((_variant_t *)&pvarg);
            v25 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(&pv);
            v26 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v25 + 32LL))(
                    v25,
                    L"AceType",
                    0,
                    &pvarg,
                    0,
                    0);
            v5 = v26;
            if ( v26 < 0 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v26);
              v30 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_81;
              }
              v31 = 100;
              goto LABEL_79;
            }
            if ( pvarg.vt != 3 )
            {
              v5 = -2147217400;
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0x80041008);
              v30 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_81;
              }
              v31 = 101;
              goto LABEL_74;
            }
            v27 = pvarg.lVal;
            _variant_t::Clear((_variant_t *)&pvarg);
            v28 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(&pv);
            v29 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v28 + 32LL))(
                    v28,
                    L"AceFlags",
                    0,
                    &pvarg,
                    0,
                    0);
            v5 = v29;
            if ( v29 < 0 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v29);
              v30 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_81;
              }
              v31 = 102;
              goto LABEL_79;
            }
            if ( pvarg.vt != 3 )
            {
              v5 = -2147217400;
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0x80041008);
              v30 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_81;
              }
              v31 = 103;
              goto LABEL_74;
            }
            CNtAce::CNtAce((CNtAce *)v44, lVal, v27, pvarg.cyVal.Lo, v43);
            if ( !(unsigned int)CNtAcl::AddAce(v11, (struct CNtAce *)v44) )
            {
              v5 = -2147217400;
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0x80041008);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  104,
                  &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids,
                  2147749896LL);
              }
              CNtAce::~CNtAce((CNtAce *)v44);
LABEL_81:
              CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v40);
LABEL_91:
              _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v48);
LABEL_106:
              _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&pv);
              goto LABEL_26;
            }
            _variant_t::Clear((_variant_t *)&pvarg);
            CNtAce::~CNtAce((CNtAce *)v44);
            CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v40);
            _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v48);
          }
          _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&pv);
        }
        *a2 = v11;
        v45[0] = 1;
        _variant_t::~_variant_t((_variant_t *)&pvarg);
        v5 = 0;
        goto LABEL_108;
      }
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, UBound);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      v14 = 92;
    }
    else
    {
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, LBound);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      v14 = 91;
    }
    WPP_SF_D(v13[2], v14, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v5);
LABEL_26:
    _variant_t::~_variant_t((_variant_t *)&pvarg);
LABEL_108:
    ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>(v45);
    return v5;
  }
  v5 = -2147217402;
  CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0x80041006);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 89;
    v8 = 2147749894LL;
    goto LABEL_6;
  }
  return v5;
}

```

## disassembly

```asm
0x18003e7c4  push    rbp
0x18003e7c6  push    rbx
0x18003e7c7  push    rsi
0x18003e7c8  push    r12
0x18003e7ca  push    r13
0x18003e7cc  push    r14
0x18003e7ce  push    r15
0x18003e7d0  lea     rbp, [rsp-27h]
0x18003e7d5  sub     rsp, 0B0h
0x18003e7dc  mov     r13, rdx
0x18003e7df  xor     r15d, r15d
0x18003e7e2  mov     [rbp+57h+rgIndices], r15
0x18003e7e6  mov     r14, [rcx+8]
0x18003e7ea  lea     rdx, [rbp+57h+rgIndices]; unsigned __int64 *
0x18003e7ee  mov     rcx, r14; psa
0x18003e7f1  call    ?GetAclSize@@YAJPEAUtagSAFEARRAY@@PEA_K@Z; GetAclSize(tagSAFEARRAY *,unsigned __int64 *)
0x18003e7f6  mov     ebx, eax
0x18003e7f8  test    eax, eax
0x18003e7fa  jns     short loc_18003E853
0x18003e7fc  mov     edx, eax; int
0x18003e7fe  lea     rcx, unk_18006A9C0; this
0x18003e805  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e80a  lea     rcx, WPP_GLOBAL_Control
0x18003e811  mov     r10, cs:WPP_GLOBAL_Control
0x18003e818  cmp     r10, rcx
0x18003e81b  jz      loc_18003EFD9
0x18003e821  test    byte ptr [r10+1Ch], 1
0x18003e826  jz      loc_18003EFD9
0x18003e82c  cmp     byte ptr [r10+19h], 2
0x18003e831  jb      loc_18003EFD9
0x18003e837  lea     edx, [r15+58h]
0x18003e83b  mov     r9d, ebx
0x18003e83e  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003e845  mov     rcx, [r10+10h]
0x18003e849  call    WPP_SF_D
0x18003e84e  jmp     loc_18003EFD9
0x18003e853  mov     ecx, 10h; unsigned __int64
0x18003e858  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003e85d  mov     [rbp+57h+pv], rax
0x18003e861  test    rax, rax
0x18003e864  jz      short loc_18003E876
0x18003e866  mov     edx, dword ptr [rbp+57h+rgIndices]; unsigned int
0x18003e869  mov     rcx, rax; this
0x18003e86c  call    ??0CNtAcl@@QEAA@K@Z; CNtAcl::CNtAcl(ulong)
0x18003e871  mov     rsi, rax
0x18003e874  jmp     short loc_18003E879
0x18003e876  mov     rsi, r15
0x18003e879  test    rsi, rsi
0x18003e87c  jnz     short loc_18003E8CC
0x18003e87e  mov     ebx, 80041006h
0x18003e883  mov     edx, ebx; int
0x18003e885  lea     rcx, unk_18006A9C0; this
0x18003e88c  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e891  lea     rcx, WPP_GLOBAL_Control
0x18003e898  mov     r10, cs:WPP_GLOBAL_Control
0x18003e89f  cmp     r10, rcx
0x18003e8a2  jz      loc_18003EFD9
0x18003e8a8  test    byte ptr [r10+1Ch], 1
0x18003e8ad  jz      loc_18003EFD9
0x18003e8b3  cmp     byte ptr [r10+19h], 2
0x18003e8b8  jb      loc_18003EFD9
0x18003e8be  lea     edx, [rsi+59h]
0x18003e8c1  mov     r9d, 80041006h
0x18003e8c7  jmp     loc_18003E83E
0x18003e8cc  mov     r8, rsi
0x18003e8cf  lea     rcx, [rbp+57h+var_50]
0x18003e8d3  call    ??$MakeGuard@P6AXPEBVCNtAcl@@@ZPEAV1@@@YA?AV?$ScopeGuardImpl1@P6AXPEBVCNtAcl@@@ZPEAV1@@@P6AXPEBVCNtAcl@@@ZPEAV1@@Z; MakeGuard<void (*)(CNtAcl const *),CNtAcl *>(void (*)(CNtAcl const *),CNtAcl *)
0x18003e8d8  nop
0x18003e8d9  test    r14, r14
0x18003e8dc  jnz     short loc_18003E93B
0x18003e8de  mov     ebx, 80041008h
0x18003e8e3  mov     edx, ebx; int
0x18003e8e5  lea     rcx, unk_18006A9C0; this
0x18003e8ec  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e8f1  lea     rcx, WPP_GLOBAL_Control
0x18003e8f8  mov     rax, cs:WPP_GLOBAL_Control
0x18003e8ff  cmp     rax, rcx
0x18003e902  jz      loc_18003EFD0
0x18003e908  test    byte ptr [rax+1Ch], 1
0x18003e90c  jz      loc_18003EFD0
0x18003e912  cmp     byte ptr [rax+19h], 2
0x18003e916  jb      loc_18003EFD0
0x18003e91c  lea     edx, [r14+5Ah]
0x18003e920  mov     r9d, 80041008h
0x18003e926  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003e92d  mov     rcx, [rax+10h]
0x18003e931  call    WPP_SF_D
0x18003e936  jmp     loc_18003EFD0
0x18003e93b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003e93f  call    cs:__imp_VariantInit
0x18003e945  nop
0x18003e946  mov     [rbp+57h+plLbound], r15d
0x18003e94a  lea     r8, [rbp+57h+plLbound]; plLbound
0x18003e94e  mov     edx, 1; nDim
0x18003e953  mov     rcx, r14; psa
0x18003e956  call    cs:__imp_SafeArrayGetLBound
0x18003e95c  mov     ebx, eax
0x18003e95e  test    eax, eax
0x18003e960  jns     short loc_18003E9B6
0x18003e962  mov     edx, eax; int
0x18003e964  lea     rcx, unk_18006A9C0; this
0x18003e96b  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e970  lea     rcx, WPP_GLOBAL_Control
0x18003e977  mov     rax, cs:WPP_GLOBAL_Control
0x18003e97e  cmp     rax, rcx
0x18003e981  jz      short loc_18003E9A8
0x18003e983  test    byte ptr [rax+1Ch], 1
0x18003e987  jz      short loc_18003E9A8
0x18003e989  cmp     byte ptr [rax+19h], 2
0x18003e98d  jb      short loc_18003E9A8
0x18003e98f  mov     edx, 5Bh ; '['
0x18003e994  mov     r9d, ebx
0x18003e997  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003e99e  mov     rcx, [rax+10h]
0x18003e9a2  call    WPP_SF_D
0x18003e9a7  nop
0x18003e9a8  lea     rcx, [rbp+57h+pvarg]; this
0x18003e9ac  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003e9b1  jmp     loc_18003EFD0
0x18003e9b6  mov     [rbp+57h+plUbound], r15d
0x18003e9ba  lea     r8, [rbp+57h+plUbound]; plUbound
0x18003e9be  mov     edx, 1; nDim
0x18003e9c3  mov     rcx, r14; psa
0x18003e9c6  call    cs:__imp_SafeArrayGetUBound
0x18003e9cc  mov     ebx, eax
0x18003e9ce  test    eax, eax
0x18003e9d0  jns     short loc_18003EA06
0x18003e9d2  mov     edx, eax; int
0x18003e9d4  lea     rcx, unk_18006A9C0; this
0x18003e9db  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e9e0  lea     rcx, WPP_GLOBAL_Control
0x18003e9e7  mov     rax, cs:WPP_GLOBAL_Control
0x18003e9ee  cmp     rax, rcx
0x18003e9f1  jz      short loc_18003E9A8
0x18003e9f3  test    byte ptr [rax+1Ch], 1
0x18003e9f7  jz      short loc_18003E9A8
0x18003e9f9  cmp     byte ptr [rax+19h], 2
0x18003e9fd  jb      short loc_18003E9A8
0x18003e9ff  mov     edx, 5Ch ; '\'
0x18003ea04  jmp     short loc_18003E994
0x18003ea06  mov     eax, [rbp+57h+plLbound]
0x18003ea09  mov     dword ptr [rbp+57h+rgIndices], eax
0x18003ea0c  cmp     eax, [rbp+57h+plUbound]
0x18003ea0f  jg      loc_18003EFBC
0x18003ea15  mov     [rbp+57h+pv], r15
0x18003ea19  lea     rcx, [rbp+57h+pv]
0x18003ea1d  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003ea22  mov     [rbp+57h+pv], r15
0x18003ea26  lea     r8, [rbp+57h+pv]; pv
0x18003ea2a  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x18003ea2e  mov     rcx, r14; psa
0x18003ea31  call    cs:__imp_SafeArrayGetElement
0x18003ea37  mov     ebx, eax
0x18003ea39  test    eax, eax
0x18003ea3b  js      loc_18003EF68
0x18003ea41  cmp     [rbp+57h+pv], r15
0x18003ea45  jz      loc_18003EC4D
0x18003ea4b  lea     rcx, [rbp+57h+pv]
0x18003ea4f  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEBAPEAUIWbemClassObject@@XZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(void)
0x18003ea54  mov     r10, rax
0x18003ea57  mov     rcx, [rax]
0x18003ea5a  mov     rax, [rcx+20h]
0x18003ea5e  mov     [rsp+0E0h+var_B8], r15
0x18003ea63  mov     [rsp+0E0h+var_C0], r15
0x18003ea68  lea     r9, [rbp+57h+pvarg]
0x18003ea6c  xor     r8d, r8d
0x18003ea6f  lea     rdx, aTrustee_0; "Trustee"
0x18003ea76  mov     rcx, r10
0x18003ea79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea7e  mov     ebx, eax
0x18003ea80  test    eax, eax
0x18003ea82  js      loc_18003EF34
0x18003ea88  cmp     word ptr [rbp+57h+pvarg], 0Dh
0x18003ea8d  jnz     loc_18003EEE9
0x18003ea93  mov     [rbp+57h+arg_18], r15
0x18003ea97  mov     rax, qword ptr [rbp+57h+pvarg+8]
0x18003ea9b  mov     rcx, [rax]
0x18003ea9e  mov     rbx, [rcx]
0x18003eaa1  lea     rcx, [rbp+57h+arg_18]
0x18003eaa5  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003eaaa  mov     [rbp+57h+arg_18], r15
0x18003eaae  lea     r8, [rbp+57h+arg_18]
0x18003eab2  lea     rdx, IID_IWbemClassObject
0x18003eab9  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x18003eabd  mov     rax, rbx
0x18003eac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eac5  mov     ebx, eax
0x18003eac7  lea     rcx, [rbp+57h+pvarg]; this
0x18003eacb  test    eax, eax
0x18003eacd  js      loc_18003EE90
0x18003ead3  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003ead8  mov     [rbp+57h+var_78], r15
0x18003eadc  lea     rdx, [rbp+57h+var_78]; struct CNtSid **
0x18003eae0  mov     rcx, [rbp+57h+arg_18]; struct IWbemClassObject *
0x18003eae4  call    ?LoadSIDFromTrustee@@YAJPEAUIWbemClassObject@@PEAPEAVCNtSid@@@Z; LoadSIDFromTrustee(IWbemClassObject *,CNtSid * *)
0x18003eae9  mov     ebx, eax
0x18003eaeb  test    eax, eax
0x18003eaed  js      loc_18003EE5C
0x18003eaf3  mov     rax, [rbp+57h+var_78]
0x18003eaf7  mov     [rbp+57h+var_88], rax
0x18003eafb  lea     rcx, [rbp+57h+pv]
0x18003eaff  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEBAPEAUIWbemClassObject@@XZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(void)
0x18003eb04  mov     r10, rax
0x18003eb07  mov     rcx, [rax]
0x18003eb0a  mov     rax, [rcx+20h]
0x18003eb0e  mov     [rsp+0E0h+var_B8], r15
0x18003eb13  mov     [rsp+0E0h+var_C0], r15
0x18003eb18  lea     r9, [rbp+57h+pvarg]
0x18003eb1c  xor     r8d, r8d
0x18003eb1f  lea     rdx, aAccessmask; "AccessMask"
0x18003eb26  mov     rcx, r10
0x18003eb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb2e  mov     ebx, eax
0x18003eb30  test    eax, eax
0x18003eb32  js      loc_18003EE0B
0x18003eb38  cmp     word ptr [rbp+57h+pvarg], 3
0x18003eb3d  jnz     loc_18003EDCC
0x18003eb43  mov     r12d, dword ptr [rbp+57h+pvarg+8]
0x18003eb47  lea     rcx, [rbp+57h+pvarg]; this
0x18003eb4b  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003eb50  lea     rcx, [rbp+57h+pv]
0x18003eb54  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEBAPEAUIWbemClassObject@@XZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(void)
0x18003eb59  mov     r10, rax
0x18003eb5c  mov     rcx, [rax]
0x18003eb5f  mov     rax, [rcx+20h]
0x18003eb63  mov     [rsp+0E0h+var_B8], r15
0x18003eb68  mov     [rsp+0E0h+var_C0], r15
0x18003eb6d  lea     r9, [rbp+57h+pvarg]
0x18003eb71  xor     r8d, r8d
0x18003eb74  lea     rdx, aAcetype; "AceType"
0x18003eb7b  mov     rcx, r10
0x18003eb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb83  mov     ebx, eax
0x18003eb85  test    eax, eax
0x18003eb87  js      loc_18003ED8C
0x18003eb8d  cmp     word ptr [rbp+57h+pvarg], 3
0x18003eb92  jnz     loc_18003ED47
0x18003eb98  mov     r15d, dword ptr [rbp+57h+pvarg+8]
0x18003eb9c  lea     rcx, [rbp+57h+pvarg]; this
0x18003eba0  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003eba5  lea     rcx, [rbp+57h+pv]
0x18003eba9  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEBAPEAUIWbemClassObject@@XZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(void)
0x18003ebae  mov     r10, rax
0x18003ebb1  mov     rcx, [rax]
0x18003ebb4  mov     rax, [rcx+20h]
0x18003ebb8  mov     [rsp+0E0h+var_B8], 0
0x18003ebc1  mov     [rsp+0E0h+var_C0], 0
0x18003ebca  lea     r9, [rbp+57h+pvarg]
0x18003ebce  xor     r8d, r8d
0x18003ebd1  lea     rdx, aAceflags; "AceFlags"
0x18003ebd8  mov     rcx, r10
0x18003ebdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebe0  mov     ebx, eax
0x18003ebe2  test    eax, eax
0x18003ebe4  js      loc_18003ED04
0x18003ebea  cmp     word ptr [rbp+57h+pvarg], 3
0x18003ebef  jnz     loc_18003ECBC
0x18003ebf5  mov     rax, [rbp+57h+var_78]
0x18003ebf9  mov     [rsp+0E0h+var_C0], rax; struct CNtSid *
0x18003ebfe  mov     r9d, dword ptr [rbp+57h+pvarg+8]; unsigned int
0x18003ec02  mov     r8d, r15d; unsigned int
0x18003ec05  mov     edx, r12d; unsigned int
0x18003ec08  lea     rcx, [rbp+57h+var_68]; this
0x18003ec0c  call    ??0CNtAce@@QEAA@KKKAEAVCNtSid@@@Z; CNtAce::CNtAce(ulong,ulong,ulong,CNtSid &)
0x18003ec11  nop
0x18003ec12  lea     rdx, [rbp+57h+var_68]; struct CNtAce *
0x18003ec16  mov     rcx, rsi; this
0x18003ec19  call    ?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z; CNtAcl::AddAce(CNtAce *)
0x18003ec1e  xor     r15d, r15d
0x18003ec21  test    eax, eax
0x18003ec23  jz      short loc_18003EC60
0x18003ec25  lea     rcx, [rbp+57h+pvarg]; this
0x18003ec29  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003ec2e  nop
0x18003ec2f  lea     rcx, [rbp+57h+var_68]; this
0x18003ec33  call    ??1CNtAce@@UEAA@XZ; CNtAce::~CNtAce(void)
0x18003ec38  nop
0x18003ec39  lea     rcx, [rbp+57h+var_88]
0x18003ec3d  call    ??1?$CDeleteMe@VCNtSid@@@@QEAA@XZ; CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(void)
0x18003ec42  nop
0x18003ec43  lea     rcx, [rbp+57h+arg_18]
0x18003ec47  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003ec4c  nop
0x18003ec4d  lea     rcx, [rbp+57h+pv]
0x18003ec51  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003ec56  mov     eax, dword ptr [rbp+57h+rgIndices]
0x18003ec59  inc     eax
0x18003ec5b  jmp     loc_18003EA09
0x18003ec60  mov     ebx, 80041008h
0x18003ec65  mov     edx, ebx; int
0x18003ec67  lea     rcx, unk_18006A9C0; this
0x18003ec6e  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ec73  lea     rcx, WPP_GLOBAL_Control
0x18003ec7a  mov     rax, cs:WPP_GLOBAL_Control
0x18003ec81  cmp     rax, rcx
0x18003ec84  jz      short loc_18003ECAE
0x18003ec86  test    byte ptr [rax+1Ch], 1
0x18003ec8a  jz      short loc_18003ECAE
0x18003ec8c  cmp     byte ptr [rax+19h], 2
0x18003ec90  jb      short loc_18003ECAE
  ... truncated ...
```
