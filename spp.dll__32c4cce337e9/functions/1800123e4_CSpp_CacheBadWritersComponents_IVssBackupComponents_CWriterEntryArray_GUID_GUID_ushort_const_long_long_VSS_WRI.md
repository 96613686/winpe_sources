# CSpp::_CacheBadWritersComponents(IVssBackupComponents *,CWriterEntryArray *,_GUID,_GUID,ushort const *,long,long,_VSS_WRITER_STATE,ushort const *,ushort const *,long,ushort const *)

- ea: `0x1800123e4`
- end: `0x180012ca3`
- name: `?_CacheBadWritersComponents@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@U_GUID@@2PEBGJJW4_VSS_WRITER_STATE@@33J3@Z`
- size: `2239`
- prototype: `__int64 __fastcall(CSpp *this, struct IVssBackupComponents *, struct CWriterEntryArray *, struct _GUID *, struct _GUID *, unsigned __int16 *, unsigned int, int, enum _VSS_WRITER_STATE, unsigned __int16 *, unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x1800131f0`
- `0x180016258`

## callees

- `0x1800021f8`
- `0x18000220c`
- `0x18000232c`
- `0x180002338`
- `0x180003a28`
- `0x180008d8c`
- `0x18000dce0`
- `0x18000dd10`
- `0x1800102e4`
- `0x1800123e4`
- `0x18001b36c`
- `0x18001b668`
- `0x18001b834`
- `0x18001b9d4`
- `0x180020738`
- `0x180020778`
- `0x180020968`
- `0x180020af4`
- `0x180020ba0`
- `0x180020c60`
- `0x1800268b4`
- `0x1800269ac`
- `0x1800272dc`
- `0x180035b76`
- `0x180035b9a`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800124ca`
- `OLEAUT32!__imp_SysFreeString` at `0x180012596`
- `OLEAUT32!__imp_SysFreeString` at `0x1800125a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800125ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800126a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800126b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800129d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800129e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800129f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124ca`
- `OLEAUT32!__imp_SysFreeString` at `0x180012596`
- `OLEAUT32!__imp_SysFreeString` at `0x1800125a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800125ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800126a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800126b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800129d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800129e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800129f6`

## string_xrefs

- `0x1800124d6`: `CSpp::_CacheBadWritersComponents`

## pseudocode

```c
__int64 __fastcall CSpp::_CacheBadWritersComponents(
        CSpp *this,
        struct IVssBackupComponents *a2,
        struct CWriterEntryArray *a3,
        struct _GUID *a4,
        struct _GUID *a5,
        unsigned __int16 *a6,
        unsigned int a7,
        int a8,
        enum _VSS_WRITER_STATE a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11,
        int a12,
        const unsigned __int16 *a13)
{
  char v16; // di
  ATL::CComBSTR *v17; // rax
  __int16 v18; // ax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  CSpp *v23; // rcx
  __int64 v24; // rbx
  __int128 *v25; // rdi
  __int64 v26; // r9
  __int128 v27; // xmm1
  struct _SPP_WRITER_ERROR_INFO *v28; // rbx
  int v29; // r8d
  struct _GUID *v30; // rbx
  __int64 v31; // xmm0_8
  CSpp *v32; // rcx
  struct _GUID v33; // xmm0
  __int128 v34; // xmm1
  __int128 *v35; // r12
  int IsWriterSystemState; // eax
  CSpp *v37; // r13
  __int64 v38; // rcx
  struct _SPP_WRITER_ERROR_INFO *v39; // rdi
  CSpp *v40; // rcx
  __int128 v41; // xmm1
  int IsComponentSystemState; // eax
  __int16 v43; // si
  unsigned int i; // ebx
  unsigned int v45; // ebx
  CSpp *v46; // rcx
  __int128 v47; // xmm1
  unsigned __int8 v48; // si
  PVOID *v49; // rcx
  unsigned __int64 v50; // rcx
  int v51; // edx
  int v52; // r8d
  int v53; // r9d
  CSpp *v54; // rcx
  CSpp *v55; // [rsp+50h] [rbp-B0h] BYREF
  int v56; // [rsp+58h] [rbp-A8h]
  BSTR v57; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v58; // [rsp+68h] [rbp-98h] BYREF
  int v59; // [rsp+70h] [rbp-90h] BYREF
  __int16 v60; // [rsp+74h] [rbp-8Ch]
  __int16 v61; // [rsp+76h] [rbp-8Ah]
  BSTR v62; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v63; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v65; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v66; // [rsp+C4h] [rbp-3Ch] BYREF
  int v67; // [rsp+C8h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+D0h] [rbp-30h] BYREF
  void *Buf2; // [rsp+D8h] [rbp-28h]
  struct _GUID *v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h] BYREF
  BSTR v72[2]; // [rsp+F0h] [rbp-10h] BYREF
  CSpp *v73; // [rsp+100h] [rbp+0h]
  struct CWriterEntryArray *v74; // [rsp+108h] [rbp+8h]
  BSTR v75[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v76; // [rsp+120h] [rbp+20h]
  struct _GUID v77; // [rsp+130h] [rbp+30h] BYREF
  unsigned int Data1; // [rsp+140h] [rbp+40h] BYREF
  __int64 v79; // [rsp+144h] [rbp+44h] BYREF
  int v80; // [rsp+14Ch] [rbp+4Ch]
  __int128 v81; // [rsp+150h] [rbp+50h]
  unsigned __int16 *v82; // [rsp+160h] [rbp+60h] BYREF
  enum _VSS_WRITER_STATE v83; // [rsp+168h] [rbp+68h]
  bool v84; // [rsp+16Ch] [rbp+6Ch]
  unsigned int v85; // [rsp+170h] [rbp+70h]
  int v86; // [rsp+174h] [rbp+74h]
  __int128 Buf1; // [rsp+190h] [rbp+90h] BYREF
  __int128 v88; // [rsp+1A0h] [rbp+A0h] BYREF

  v70 = a5;
  v16 = 0;
  v76 = a6;
  v56 = a12;
  *(_QWORD *)&v77.Data1 = a13;
  Buf2 = a4;
  v74 = a3;
  v73 = this;
  v67 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    v17 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a4);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
      *(_QWORD *)v17,
      a7);
    v16 = 1;
  }
  if ( (v16 & 1) != 0 )
  {
    v16 &= ~1u;
    SysFreeString(bstrString);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v59, "CSpp::_CacheBadWritersComponents", 4878, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v64);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v63);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v71);
  v65 = 0;
  v66 = 0;
  v55 = 0;
  v62 = 0;
  Buf1 = 0;
  v58 = 0;
  v88 = 0;
  v57 = 0;
  v67 = 0;
  Data1 = 0;
  memset_0(&v79, 0, 0x4Cu);
  LODWORD(bstrString) = 0;
  if ( !a2 && !a10 && !a11 )
  {
    v18 = 4906;
LABEL_10:
    v59 = -2147024809;
    goto LABEL_11;
  }
  v60 = 4906;
  v18 = 4907;
  if ( !a3 )
    goto LABEL_10;
  v59 = 0;
  v60 = 4907;
  v23 = (CSpp *)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    v16 |= 6u;
    v24 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v72, a4);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v75, (const struct _GUID *)Buf2);
    WPP_SF_SSDSDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, a7, (__int64)v76, a8, a9);
  }
  if ( (v16 & 4) != 0 )
  {
    v16 &= ~4u;
    SysFreeString(v75[0]);
  }
  if ( (v16 & 2) != 0 )
    SysFreeString(v72[0]);
  v25 = (__int128 *)Buf2;
  v26 = *((_QWORD *)v73 + 4);
  v27 = *(_OWORD *)Buf2;
  *(struct _GUID *)v72 = *v70;
  v28 = *(struct _SPP_WRITER_ERROR_INFO **)(v26 + 8);
  LODWORD(v26) = *(_DWORD *)(v26 + 16);
  *(_OWORD *)v75 = v27;
  if ( (unsigned int)CSpp::_IsWriterAlreadyInBadWritersList(
                       v23,
                       (struct _GUID *)v75,
                       (struct _GUID *)v72,
                       v26,
                       v28,
                       (unsigned int *)&bstrString) )
  {
    v35 = (__int128 *)Buf2;
    v37 = v73;
    v39 = (struct _SPP_WRITER_ERROR_INFO *)((char *)v28 + 80 * (unsigned int)bstrString);
  }
  else
  {
    v30 = v70;
    v81 = *v25;
    v31 = *(_QWORD *)&v70->Data2;
    Data1 = v70->Data1;
    v80 = *(_DWORD *)&v70->Data4[4];
    v79 = v31;
    v59 = SdSafeDuplicateStr(&v82, v76);
    v18 = 4924;
    if ( v59 < 0 )
      goto LABEL_11;
    v33 = *v30;
    v34 = *v25;
    v60 = 4924;
    v83 = a9;
    v35 = v25;
    v85 = a7;
    *(struct _GUID *)v72 = v33;
    *(_OWORD *)v75 = v34;
    v86 = a8;
    IsWriterSystemState = CSpp::_IsWriterSystemState(v32, v74, (struct _GUID *)v75, (struct _GUID *)v72);
    v37 = v73;
    v84 = IsWriterSystemState == 0;
    v59 = CSxArrayBuilder<_SPP_COMPONENT_PROP,&void Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *),&void SxDefaultInit<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *),&void SxDefaultTransfer<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *,_SPP_COMPONENT_PROP *)>::Append(
            *((_QWORD *)v73 + 4),
            &Data1);
    v18 = 4932;
    if ( v59 < 0 )
      goto LABEL_11;
    v38 = *((_QWORD *)v37 + 4);
    v60 = 4932;
    v39 = (struct _SPP_WRITER_ERROR_INFO *)(*(_QWORD *)(v38 + 8) + 80LL * (unsigned int)(*(_DWORD *)(v38 + 16) - 1));
  }
  if ( !a10 )
  {
    v59 = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, unsigned int *))(*(_QWORD *)a2 + 24LL))(a2, &v65);
    v18 = 4963;
    if ( v59 < 0 )
      goto LABEL_11;
    v60 = 4963;
    v43 = 4970;
    for ( i = 0; i < v65; ++i )
    {
      ATL::CComPtrBase<IVssWriterComponentsExt>::Release(&v64);
      v59 = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD, __int64 *))(*(_QWORD *)a2 + 32LL))(
              a2,
              i,
              &v64);
      if ( v59 < 0 )
      {
        v61 = 4969;
        goto LABEL_12;
      }
      v60 = 4969;
      v59 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v64 + 8LL))(v64, &v88, &Buf1);
      if ( v59 < 0 )
      {
LABEL_39:
        v61 = v43;
        goto LABEL_12;
      }
      v60 = 4970;
      if ( !memcmp_0(&Buf1, v35, 0x10u) )
        break;
    }
    v59 = (**(__int64 (__fastcall ***)(__int64, unsigned int *))v64)(v64, &v66);
    v18 = 4977;
    if ( v59 < 0 )
      goto LABEL_11;
    v45 = 0;
    v60 = 4977;
    while ( 1 )
    {
      v43 = 4988;
      if ( v45 >= v66 )
        goto LABEL_12;
      ATL::CComPtrBase<IVssWMComponent>::Release(&v63);
      v59 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v64 + 16LL))(v64, v45, &v63);
      v18 = 4981;
      if ( v59 < 0 )
        goto LABEL_11;
      v60 = 4981;
      SysFreeString(v58);
      v58 = 0;
      SysFreeString(v57);
      v57 = 0;
      SysFreeString(v62);
      v62 = 0;
      v55 = 0;
      v59 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v63 + 40LL))(v63, &v58);
      if ( v59 < 0 )
        goto LABEL_39;
      v60 = 4988;
      v59 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v63 + 24LL))(v63, &v57);
      v18 = 4989;
      if ( v59 < 0 )
        goto LABEL_11;
      v47 = *v35;
      v60 = 4989;
      *(_OWORD *)v72 = v47;
      v77 = *v70;
      v48 = (unsigned int)CSpp::_IsComponentSystemState(v46, v74, (struct _GUID *)v72, &v77, v58, v57) == 0;
      v49 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          73,
          (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
          (_DWORD)v58,
          (__int64)v57);
        v49 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( a7 != -2147212490 )
        break;
      ATL::CComPtrBase<IVssWMComponent>::Release(&v71);
      v59 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v63)(
              v63,
              &GUID_3b5be0f2_07a9_4e4b_bdd3_cfdc8e2c0d2d,
              &v71);
      v18 = 5008;
      if ( v59 < 0 )
        goto LABEL_11;
      v60 = 5008;
      v59 = (*(__int64 (__fastcall **)(__int64, CSpp **, char *, BSTR *, int *))(*(_QWORD *)v71 + 392LL))(
              v71,
              &v55,
              (char *)&v55 + 4,
              &v62,
              &v67);
      v18 = 5011;
      if ( v59 < 0 )
        goto LABEL_11;
      v53 = (int)v55;
      v60 = 5011;
      if ( (int)v55 < 0 )
      {
        v54 = (CSpp *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_DDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v51, v52, (_DWORD)v55, SBYTE4(v55), (__int64)v62);
          v53 = (int)v55;
        }
        if ( (unsigned int)CSpp::_IsRetryableError(v54, &dword_18003BB60, 3u, v53) || *((_DWORD *)v37 + 30) >= 4u )
        {
          v50 = (unsigned int)v55;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              76,
              &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
              (unsigned int)v55);
          v50 = (unsigned int)v55;
          v18 = 5031;
          v59 = (int)v55;
          if ( (int)v55 < 0 )
            goto LABEL_11;
          v60 = 5031;
        }
        goto LABEL_69;
      }
LABEL_71:
      ++v45;
    }
    if ( v49 != &WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x2000000) != 0 )
      WPP_SF_D(v49[2], 74, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, (unsigned int)v55);
    v50 = a7;
    LODWORD(v55) = a7;
LABEL_69:
    v59 = CSpp::_AddComponentToComponentList((CSpp *)v50, v39, v58, v57, v48, v50, SHIDWORD(v55), v62);
    v18 = 5037;
    if ( v59 < 0 )
      goto LABEL_11;
    v60 = 5037;
    goto LABEL_71;
  }
  v40 = (CSpp *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, v29, (_DWORD)a10, (__int64)a11, v56);
  v41 = *v35;
  *(struct _GUID *)v72 = *v70;
  *(_OWORD *)v75 = v41;
  IsComponentSystemState = CSpp::_IsComponentSystemState(v40, v74, (struct _GUID *)v75, (struct _GUID *)v72, a10, a11);
  v59 = CSpp::_AddComponentToComponentList(
          *(CSpp **)&v77.Data1,
          v39,
          a10,
          a11,
          IsComponentSystemState == 0,
          v56,
          0,
          *(unsigned __int16 **)&v77.Data1);
  v18 = 4957;
  if ( v59 >= 0 )
  {
    v60 = 4957;
    goto LABEL_12;
  }
LABEL_11:
  v61 = v18;
LABEL_12:
  Free_SPP_BAD_WRITER_INFO((struct _SPP_WRITER_ERROR_INFO *)&Data1);
  v19 = v59;
  SysFreeString(v57);
  SysFreeString(v58);
  SysFreeString(v62);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  ATL::CComPtr<IVssWriterComponentsExt>::~CComPtr<IVssWriterComponentsExt>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v59, v20, v21);
  return v19;
}

```

## disassembly

```asm
0x1800123e4  push    rbp
0x1800123e6  push    rbx
0x1800123e7  push    rsi
0x1800123e8  push    rdi
0x1800123e9  push    r12
0x1800123eb  push    r13
0x1800123ed  push    r14
0x1800123ef  push    r15
0x1800123f1  lea     rbp, [rsp-0C8h]
0x1800123f9  sub     rsp, 1C8h
0x180012400  mov     rax, cs:__security_cookie
0x180012407  xor     rax, rsp
0x18001240a  mov     [rbp+100h+var_50], rax
0x180012411  mov     rax, [rbp+100h+arg_20]
0x180012418  xor     r13d, r13d
0x18001241b  mov     rsi, [rbp+100h+arg_48]
0x180012422  mov     rbx, r9
0x180012425  mov     r14, [rbp+100h+arg_50]
0x18001242c  mov     r12, r8
0x18001242f  mov     [rbp+100h+var_120], rax
0x180012433  mov     r15, rdx
0x180012436  mov     rax, [rbp+100h+arg_28]
0x18001243d  mov     edi, r13d
0x180012440  mov     [rbp+100h+var_E0], rax
0x180012444  mov     eax, [rbp+100h+arg_58]
0x18001244a  mov     [rsp+200h+var_1A8], eax
0x18001244e  mov     rax, [rbp+100h+arg_60]
0x180012455  mov     qword ptr [rbp+100h+var_D0.Data1], rax
0x180012459  mov     [rbp+100h+Buf2], rbx
0x18001245d  mov     [rbp+100h+var_F8], r8
0x180012461  mov     [rbp+100h+var_100], rcx
0x180012465  mov     [rbp+100h+var_138], r13d
0x180012469  mov     rax, cs:WPP_GLOBAL_Control
0x180012470  lea     rcx, WPP_GLOBAL_Control
0x180012477  cmp     rax, rcx
0x18001247a  jz      short loc_1800124BD
0x18001247c  test    dword ptr [rax+1Ch], 20000000h
0x180012483  jz      short loc_1800124BD
0x180012485  mov     rdx, rbx; struct _GUID *
0x180012488  lea     rcx, [rbp+100h+bstrString]; this
0x18001248c  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180012491  mov     ecx, dword ptr [rbp+100h+arg_30]
0x180012497  lea     edx, [r13+46h]
0x18001249b  mov     dword ptr [rsp+200h+var_1E0], ecx
0x18001249f  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800124a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124ad  mov     r9, [rax]
0x1800124b0  mov     rcx, [rcx+10h]
0x1800124b4  call    WPP_SF_Sd
0x1800124b9  lea     edi, [r13+1]
0x1800124bd  test    dil, 1
0x1800124c1  jz      short loc_1800124D0
0x1800124c3  mov     rcx, [rbp+100h+bstrString]; bstrString
0x1800124c7  and     edi, 0FFFFFFFEh
0x1800124ca  call    cs:__imp_SysFreeString
0x1800124d0  mov     r9d, 1; unsigned __int16
0x1800124d6  lea     rdx, aCsppCachebadwr; "CSpp::_CacheBadWritersComponents"
0x1800124dd  mov     r8d, 130Eh; unsigned __int16
0x1800124e3  lea     rcx, [rsp+200h+var_190]; this
0x1800124e8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800124ed  lea     rcx, [rbp+100h+var_148]
0x1800124f1  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800124f6  lea     rcx, [rbp+100h+var_150]
0x1800124fa  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800124ff  lea     rcx, [rbp+100h+var_118]
0x180012503  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180012508  xor     edx, edx; Val
0x18001250a  mov     [rbp+100h+var_140], r13d
0x18001250e  xorps   xmm0, xmm0
0x180012511  mov     [rbp+100h+var_13C], r13d
0x180012515  xorps   xmm1, xmm1
0x180012518  mov     dword ptr [rsp+200h+var_1B0+4], r13d
0x18001251d  lea     rcx, [rbp+100h+var_BC]; void *
0x180012521  mov     dword ptr [rsp+200h+var_1B0], r13d
0x180012526  lea     r8d, [rdx+4Ch]; Size
0x18001252a  mov     [rbp+100h+var_158], r13
0x18001252e  movups  [rbp+100h+Buf1], xmm0
0x180012535  mov     [rsp+200h+var_198], r13
0x18001253a  movups  [rbp+100h+var_60], xmm1
0x180012541  mov     [rsp+200h+var_1A0], r13
0x180012546  mov     [rbp+100h+var_138], r13d
0x18001254a  mov     [rbp+100h+var_C0], r13d
0x18001254e  call    memset_0
0x180012553  mov     dword ptr [rbp+100h+bstrString], r13d
0x180012557  test    r15, r15
0x18001255a  jnz     loc_1800125FB
0x180012560  test    rsi, rsi
0x180012563  jnz     loc_1800125FB
0x180012569  test    r14, r14
0x18001256c  jnz     loc_1800125FB
0x180012572  mov     eax, 132Ah
0x180012577  mov     [rsp+200h+var_190], 80070057h
0x18001257f  mov     [rsp+200h+var_18A], ax
0x180012584  lea     rcx, [rbp+100h+var_C0]; struct _SPP_WRITER_ERROR_INFO *
0x180012588  call    ?Free_SPP_BAD_WRITER_INFO@@YAXPEAU_SPP_WRITER_ERROR_INFO@@@Z; Free_SPP_BAD_WRITER_INFO(_SPP_WRITER_ERROR_INFO *)
0x18001258d  mov     rcx, [rsp+200h+var_1A0]; bstrString
0x180012592  mov     ebx, [rsp+200h+var_190]
0x180012596  call    cs:__imp_SysFreeString
0x18001259c  mov     rcx, [rsp+200h+var_198]; bstrString
0x1800125a1  call    cs:__imp_SysFreeString
0x1800125a7  mov     rcx, [rbp+100h+var_158]; bstrString
0x1800125ab  call    cs:__imp_SysFreeString
0x1800125b1  lea     rcx, [rbp+100h+var_118]
0x1800125b5  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x1800125ba  lea     rcx, [rbp+100h+var_150]
0x1800125be  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x1800125c3  lea     rcx, [rbp+100h+var_148]
0x1800125c7  call    ??1?$CComPtr@VIVssWriterComponentsExt@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssWriterComponentsExt>::~CComPtr<IVssWriterComponentsExt>(void)
0x1800125cc  lea     rcx, [rsp+200h+var_190]; this
0x1800125d1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800125d6  mov     eax, ebx
0x1800125d8  mov     rcx, [rbp+100h+var_50]
0x1800125df  xor     rcx, rsp; StackCookie
0x1800125e2  call    __security_check_cookie
0x1800125e7  add     rsp, 1C8h
0x1800125ee  pop     r15
0x1800125f0  pop     r14
0x1800125f2  pop     r13
0x1800125f4  pop     r12
0x1800125f6  pop     rdi
0x1800125f7  pop     rsi
0x1800125f8  pop     rbx
0x1800125f9  pop     rbp
0x1800125fa  retn
0x1800125fb  mov     eax, 132Ah
0x180012600  mov     [rsp+200h+var_18C], ax
0x180012605  mov     eax, 132Bh
0x18001260a  test    r12, r12
0x18001260d  jz      loc_180012577
0x180012613  mov     [rsp+200h+var_190], r13d
0x180012618  mov     [rsp+200h+var_18C], ax
0x18001261d  mov     rax, cs:WPP_GLOBAL_Control
0x180012624  lea     rcx, WPP_GLOBAL_Control
0x18001262b  mov     r12d, [rbp+100h+arg_40]
0x180012632  mov     r13d, dword ptr [rbp+100h+arg_38]
0x180012639  cmp     rax, rcx
0x18001263c  jz      short loc_18001269B
0x18001263e  test    dword ptr [rax+1Ch], 2000000h
0x180012645  jz      short loc_18001269B
0x180012647  mov     rdx, rbx; struct _GUID *
0x18001264a  lea     rcx, [rbp+100h+var_110]; this
0x18001264e  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180012653  mov     rdx, [rbp+100h+Buf2]; struct _GUID *
0x180012657  lea     rcx, [rbp+100h+var_F0]; this
0x18001265b  or      edi, 6
0x18001265e  mov     rbx, [rax]
0x180012661  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180012666  mov     rcx, [rbp+100h+var_E0]
0x18001266a  mov     dword ptr [rsp+200h+var_1C0], r12d; char
0x18001266f  mov     dword ptr [rsp+200h+var_1C8], r13d; char
0x180012674  mov     r9, [rax]
0x180012677  mov     [rsp+200h+var_1D0], rcx; __int64
0x18001267c  mov     ecx, dword ptr [rbp+100h+arg_30]
0x180012682  mov     dword ptr [rsp+200h+var_1D8], ecx; char
0x180012686  mov     rcx, cs:WPP_GLOBAL_Control
0x18001268d  mov     [rsp+200h+var_1E0], rbx; __int64
0x180012692  mov     rcx, [rcx+10h]; LoggerHandle
0x180012696  call    WPP_SF_SSDSDd
0x18001269b  test    dil, 4
0x18001269f  jz      short loc_1800126AE
0x1800126a1  mov     rcx, [rbp+100h+var_F0]; bstrString
0x1800126a5  and     edi, 0FFFFFFFBh
0x1800126a8  call    cs:__imp_SysFreeString
0x1800126ae  test    dil, 2
0x1800126b2  jz      short loc_1800126BE
0x1800126b4  mov     rcx, [rbp+100h+var_110]; bstrString
0x1800126b8  call    cs:__imp_SysFreeString
0x1800126be  mov     rax, [rbp+100h+var_120]
0x1800126c2  lea     r8, [rbp+100h+var_110]; struct _GUID *
0x1800126c6  mov     r9, [rbp+100h+var_100]
0x1800126ca  lea     rdx, [rbp+100h+var_F0]; struct _GUID *
0x1800126ce  mov     rdi, [rbp+100h+Buf2]
0x1800126d2  movaps  xmm0, xmmword ptr [rax]
0x1800126d5  lea     rax, [rbp+100h+bstrString]
0x1800126d9  mov     r9, [r9+20h]
0x1800126dd  movaps  xmm1, xmmword ptr [rdi]
0x1800126e0  mov     [rsp+200h+var_1D8], rax; unsigned int *
0x1800126e5  movdqa  xmmword ptr [rbp+100h+var_110], xmm0
0x1800126ea  mov     rbx, [r9+8]
0x1800126ee  mov     r9d, [r9+10h]; unsigned int
0x1800126f2  mov     [rsp+200h+var_1E0], rbx; struct _SPP_WRITER_ERROR_INFO *
0x1800126f7  movdqa  xmmword ptr [rbp+100h+var_F0], xmm1
0x1800126fc  call    ?_IsWriterAlreadyInBadWritersList@CSpp@@AEAAHU_GUID@@0KPEAU_SPP_WRITER_ERROR_INFO@@PEAK@Z; CSpp::_IsWriterAlreadyInBadWritersList(_GUID,_GUID,ulong,_SPP_WRITER_ERROR_INFO *,ulong *)
0x180012701  test    eax, eax
0x180012703  jnz     loc_1800127C6
0x180012709  mov     rbx, [rbp+100h+var_120]
0x18001270d  lea     rcx, [rbp+100h+var_A0]; unsigned __int16 **
0x180012711  movaps  xmm0, xmmword ptr [rdi]
0x180012714  mov     rdx, [rbp+100h+var_E0]; unsigned __int16 *
0x180012718  movdqu  [rbp+100h+var_B0], xmm0
0x18001271d  mov     eax, [rbx]
0x18001271f  movsd   xmm0, qword ptr [rbx+4]
0x180012724  mov     [rbp+100h+var_C0], eax
0x180012727  mov     eax, [rbx+0Ch]
0x18001272a  mov     [rbp+100h+var_B4], eax
0x18001272d  movsd   [rbp+100h+var_BC], xmm0
0x180012732  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x180012737  mov     [rsp+200h+var_190], eax
0x18001273b  test    eax, eax
0x18001273d  mov     eax, 133Ch
0x180012742  js      loc_18001257F
0x180012748  movaps  xmm0, xmmword ptr [rbx]
0x18001274b  lea     r9, [rbp+100h+var_110]; struct _GUID
0x18001274f  movaps  xmm1, xmmword ptr [rdi]
0x180012752  lea     r8, [rbp+100h+var_F0]; struct _GUID
0x180012756  mov     rdx, [rbp+100h+var_F8]; struct CWriterEntryArray *
0x18001275a  mov     [rsp+200h+var_18C], ax
0x18001275f  mov     eax, dword ptr [rbp+100h+arg_30]
0x180012765  mov     [rbp+100h+var_98], r12d
0x180012769  mov     r12, rdi
0x18001276c  mov     [rbp+100h+var_90], eax
0x18001276f  movdqa  xmmword ptr [rbp+100h+var_110], xmm0
0x180012774  movdqa  xmmword ptr [rbp+100h+var_F0], xmm1
0x180012779  mov     [rbp+100h+var_8C], r13d
0x18001277d  call    ?_IsWriterSystemState@CSpp@@AEAAJPEAVCWriterEntryArray@@U_GUID@@1@Z; CSpp::_IsWriterSystemState(CWriterEntryArray *,_GUID,_GUID)
0x180012782  mov     r13, [rbp+100h+var_100]
0x180012786  lea     rdx, [rbp+100h+var_C0]
0x18001278a  test    eax, eax
0x18001278c  setz    [rbp+100h+var_94]
0x180012790  mov     rcx, [r13+20h]
0x180012794  call    ?Append@?$CSxArrayBuilder@U_SPP_COMPONENT_PROP@@$1?Free_SPP_COMPONENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_COMPONENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_COMPONENT_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_COMPONENT_PROP@@@Z; CSxArrayBuilder<_SPP_COMPONENT_PROP,&Free_SPP_COMPONENT_PROP(_SPP_COMPONENT_PROP *),&SxDefaultInit<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *),&SxDefaultTransfer<_SPP_COMPONENT_PROP>(_SPP_COMPONENT_PROP *,_SPP_COMPONENT_PROP *)>::Append(_SPP_COMPONENT_PROP *)
0x180012799  mov     [rsp+200h+var_190], eax
0x18001279d  test    eax, eax
0x18001279f  mov     eax, 1344h
0x1800127a4  js      loc_18001257F
0x1800127aa  mov     rcx, [r13+20h]
0x1800127ae  mov     [rsp+200h+var_18C], ax
0x1800127b3  mov     eax, [rcx+10h]
0x1800127b6  dec     eax
0x1800127b8  lea     rdi, [rax+rax*4]
0x1800127bc  shl     rdi, 4
0x1800127c0  add     rdi, [rcx+8]
0x1800127c4  jmp     short loc_1800127DC
0x1800127c6  mov     eax, dword ptr [rbp+100h+bstrString]
0x1800127c9  mov     r12, [rbp+100h+Buf2]
0x1800127cd  mov     r13, [rbp+100h+var_100]
0x1800127d1  lea     rdi, [rax+rax*4]
0x1800127d5  shl     rdi, 4
0x1800127d9  add     rdi, rbx
0x1800127dc  test    rsi, rsi
0x1800127df  jz      loc_180012897
0x1800127e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127ec  lea     rax, WPP_GLOBAL_Control
0x1800127f3  mov     ebx, [rsp+200h+var_1A8]
0x1800127f7  cmp     rcx, rax
0x1800127fa  jz      short loc_18001281F
0x1800127fc  test    dword ptr [rcx+1Ch], 2000000h
0x180012803  jz      short loc_18001281F
0x180012805  mov     rcx, [rcx+10h]
0x180012809  mov     edx, 48h ; 'H'
0x18001280e  mov     dword ptr [rsp+200h+var_1D8], ebx
0x180012812  mov     r9, rsi
0x180012815  mov     [rsp+200h+var_1E0], r14
0x18001281a  call    WPP_SF_SSD
0x18001281f  mov     rax, [rbp+100h+var_120]
0x180012823  lea     r9, [rbp+100h+var_110]; struct _GUID *
0x180012827  movaps  xmm1, xmmword ptr [r12]
0x18001282c  lea     r8, [rbp+100h+var_F0]; struct _GUID *
0x180012830  mov     rdx, [rbp+100h+var_F8]; struct CWriterEntryArray *
0x180012834  mov     [rsp+200h+var_1D8], r14; unsigned __int16 *
0x180012839  movaps  xmm0, xmmword ptr [rax]
0x18001283c  movdqa  xmmword ptr [rbp+100h+var_110], xmm0
0x180012841  movdqa  xmmword ptr [rbp+100h+var_F0], xmm1
0x180012846  mov     [rsp+200h+var_1E0], rsi; unsigned __int16 *
0x18001284b  call    ?_IsComponentSystemState@CSpp@@AEAAJPEAVCWriterEntryArray@@U_GUID@@1PEBG2@Z; CSpp::_IsComponentSystemState(CWriterEntryArray *,_GUID,_GUID,ushort const *,ushort const *)
0x180012850  mov     rcx, qword ptr [rbp+100h+var_D0.Data1]; this
0x180012854  test    eax, eax
0x180012856  mov     [rsp+200h+var_1C8], rcx; unsigned __int16 *
0x18001285b  mov     r9, r14; unsigned __int16 *
0x18001285e  setz    al
0x180012861  mov     dword ptr [rsp+200h+var_1D0], 0; int
0x180012869  mov     dword ptr [rsp+200h+var_1D8], ebx; int
0x18001286d  mov     r8, rsi; unsigned __int16 *
0x180012870  mov     rdx, rdi; struct _SPP_WRITER_ERROR_INFO *
0x180012873  mov     byte ptr [rsp+200h+var_1E0], al; unsigned __int8
0x180012877  call    ?_AddComponentToComponentList@CSpp@@AEAAJPEAU_SPP_WRITER_ERROR_INFO@@PEBG1EJJ1@Z; CSpp::_AddComponentToComponentList(_SPP_WRITER_ERROR_INFO *,ushort const *,ushort const *,uchar,long,long,ushort const *)
0x18001287c  mov     [rsp+200h+var_190], eax
0x180012880  test    eax, eax
0x180012882  mov     eax, 135Dh
0x180012887  js      loc_18001257F
0x18001288d  mov     [rsp+200h+var_18C], ax
0x180012892  jmp     loc_180012584
0x180012897  mov     rax, [r15]
0x18001289a  lea     rdx, [rbp+100h+var_140]
0x18001289e  mov     rcx, r15
0x1800128a1  mov     rax, [rax+18h]
0x1800128a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128aa  mov     [rsp+200h+var_190], eax
0x1800128ae  test    eax, eax
0x1800128b0  mov     eax, 1363h
0x1800128b5  js      loc_18001257F
0x1800128bb  mov     [rsp+200h+var_18C], ax
0x1800128c0  lea     esi, [rax+7]
0x1800128c3  xor     ebx, ebx
0x1800128c5  lea     r14d, [rax+6]
0x1800128c9  cmp     ebx, [rbp+100h+var_140]
0x1800128cc  jnb     loc_18001295B
0x1800128d2  lea     rcx, [rbp+100h+var_148]
0x1800128d6  call    ?Release@?$CComPtrBase@VIVssWriterComponentsExt@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVssWriterComponentsExt>::Release(void)
0x1800128db  mov     rax, [r15]
  ... truncated ...
```
