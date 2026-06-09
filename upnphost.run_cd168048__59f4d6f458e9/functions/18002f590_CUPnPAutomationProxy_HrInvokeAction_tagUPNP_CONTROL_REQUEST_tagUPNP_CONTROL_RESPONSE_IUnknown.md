# CUPnPAutomationProxy::HrInvokeAction(tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *,IUnknown *)

- ea: `0x18002f590`
- end: `0x180030252`
- name: `?HrInvokeAction@CUPnPAutomationProxy@@AEAAJPEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@PEAUIUnknown@@@Z`
- size: `3266`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, struct tagUPNP_CONTROL_REQUEST *, struct tagUPNP_CONTROL_RESPONSE *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002f4dc`

## callees

- `0x1800200f4`
- `0x18002adc0`
- `0x18002f590`
- `0x180034ec4`
- `0x18003817c`
- `0x18003b1cc`
- `0x18003b904`
- `0x18003bf14`
- `0x18003c018`
- `0x18003d4b0`
- `0x180053e68`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f7bc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f7bc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800300f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030116`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800300f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030116`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f696`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f6d8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f696`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f6d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fb6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fb6e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f906`
- `OLEAUT32!__imp_SysAllocString` at `0x18002fb3e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002feb5`
- `OLEAUT32!__imp_SysAllocString` at `0x180030017`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f906`
- `OLEAUT32!__imp_SysAllocString` at `0x18002fb3e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002feb5`
- `OLEAUT32!__imp_SysAllocString` at `0x180030017`
- `OLEAUT32!__imp_VariantInit` at `0x18002f62d`
- `OLEAUT32!__imp_VariantInit` at `0x18002f77f`
- `OLEAUT32!__imp_VariantInit` at `0x18002fba8`
- `OLEAUT32!__imp_VariantInit` at `0x18002f62d`
- `OLEAUT32!__imp_VariantInit` at `0x18002f77f`
- `OLEAUT32!__imp_VariantInit` at `0x18002fba8`
- `OLEAUT32!__imp_VariantClear` at `0x18002f968`
- `OLEAUT32!__imp_VariantClear` at `0x1800300d6`
- `OLEAUT32!__imp_VariantClear` at `0x18003015b`
- `OLEAUT32!__imp_VariantClear` at `0x18002f968`
- `OLEAUT32!__imp_VariantClear` at `0x1800300d6`
- `OLEAUT32!__imp_VariantClear` at `0x18003015b`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002fbcb`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002fd89`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002fbcb`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002fd89`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002f934`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002f934`
- `OLEAUT32!__imp_VARIANT_UserFree` at `0x1800300c8`
- `OLEAUT32!__imp_VARIANT_UserFree` at `0x180030142`
- `OLEAUT32!__imp_VARIANT_UserFree` at `0x1800300c8`
- `OLEAUT32!__imp_VARIANT_UserFree` at `0x180030142`

## string_xrefs

- `0x18002f89b`: `CUPnPAutomationProxy::HrVariantInitFroXMLType(): Exiting`
- `0x18002fa05`: `CUPnPAutomationProxy::HrInvokeAction(): Failed to initialize for XML data type`
- `0x18002fdf5`: `CUPnPAutomationProxy::HrInvokeAction(): Failed to copy out arg`
- `0x18002fd47`: `CUPnPAutomationProxy::HrInvokeAction(): Failed to copy retval`

## pseudocode

```c
__int64 __fastcall CUPnPAutomationProxy::HrInvokeAction(
        CUPnPAutomationProxy *this,
        struct tagUPNP_CONTROL_REQUEST *a2,
        struct tagUPNP_CONTROL_RESPONSE *a3,
        struct IUnknown *a4)
{
  const unsigned __int16 *v5; // rdx
  struct tagUPNP_CONTROL_RESPONSE *v6; // rsi
  CUPnPAutomationProxy *v7; // r14
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // r8
  struct tagUPNP_ACTION *v10; // r13
  int v11; // edi
  unsigned int v12; // r12d
  unsigned int v13; // ecx
  unsigned int v14; // r11d
  __int64 v15; // rbx
  char *v16; // rax
  char *v17; // rsi
  void *v18; // rax
  void *v19; // r15
  STRSAFE_PCNZWCH v20; // rcx
  unsigned int v21; // r14d
  ULONG v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r12
  int v27; // esi
  int v28; // r15d
  int v29; // eax
  __int64 v30; // rbx
  int v31; // eax
  __int64 v32; // rax
  int v33; // ecx
  _QWORD *v34; // r15
  __int64 v35; // rbx
  __int64 v36; // xmm1_8
  __int64 v37; // rax
  __int64 v38; // rax
  __int16 v39; // r8
  _QWORD *v40; // rdx
  __int16 v41; // cx
  SAFEARRAY *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  int v45; // eax
  unsigned int (__fastcall ***v46)(_QWORD, __int64 *, void **); // rcx
  __int64 v47; // rax
  VARIANT *v48; // r14
  unsigned int v49; // esi
  int v50; // r15d
  __int64 v51; // rbx
  HRESULT v52; // eax
  unsigned int v53; // r9d
  __int64 v54; // r10
  struct tagUPNP_CONTROL_REQUEST *v55; // r12
  struct IUnknown *v56; // rbx
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rbx
  __int64 v61; // rsi
  HRESULT v62; // eax
  STRSAFE_PCNZWCH v63; // rcx
  int v64; // edx
  const char *v65; // r9
  const unsigned __int16 *v66; // rdx
  const unsigned __int16 *v67; // r8
  int v68; // eax
  int v69; // eax
  const unsigned __int16 *v70; // r9
  const unsigned __int16 *v71; // rcx
  const unsigned __int16 *v72; // rdx
  const unsigned __int16 *v73; // r8
  VARIANT *v74; // rdx
  __int64 i; // rbx
  VARIANTARG *v76; // rcx
  CUPnPAutomationProxy *v77; // rcx
  const unsigned __int16 *v78; // rax
  const unsigned __int16 *v79; // r9
  __int128 v80; // xmm1
  __int128 v81; // xmm0
  int v83; // [rsp+28h] [rbp-E0h]
  unsigned int v84; // [rsp+58h] [rbp-B0h]
  unsigned int v85; // [rsp+5Ch] [rbp-ACh]
  _QWORD *Block; // [rsp+60h] [rbp-A8h]
  char *v87; // [rsp+68h] [rbp-A0h]
  VARIANTARG v88; // [rsp+70h] [rbp-98h] BYREF
  __int64 v89; // [rsp+88h] [rbp-80h]
  __int128 v90; // [rsp+90h] [rbp-78h] BYREF
  __int128 v91; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v92; // [rsp+B0h] [rbp-58h]
  SAFEARRAYBOUND rgsabound; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int16 *v95[2]; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int16 *v96[2]; // [rsp+F8h] [rbp-10h]
  __int128 v97; // [rsp+108h] [rbp+0h]
  __int128 v98; // [rsp+118h] [rbp+10h]
  struct tagUPNP_CONTROL_REQUEST *v100; // [rsp+190h] [rbp+88h] BYREF
  struct tagUPNP_CONTROL_RESPONSE *v101; // [rsp+198h] [rbp+90h]
  struct IUnknown *v102; // [rsp+1A0h] [rbp+98h]

  v102 = a4;
  v101 = a3;
  v100 = a2;
  v5 = *(const unsigned __int16 **)a2;
  v6 = a3;
  v7 = this;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v10 = CUPnPAutomationProxy::LookupActionByName(this, v5);
  if ( !v10 )
  {
    v78 = L"Invalid Action";
    v79 = L"401";
    goto LABEL_168;
  }
  if ( *((_DWORD *)v10 + 3) != *((_DWORD *)a2 + 2) )
  {
    v78 = L"Invalid Args";
    v79 = L"402";
LABEL_168:
    v11 = HrBuildFaultResponse((union tagUPNP_CONTROL_RESPONSE_DATA *)&v91, v8, v9, v79, v78);
    goto LABEL_169;
  }
  v11 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  *(_OWORD *)v95 = 0;
  *(_OWORD *)v96 = 0;
  v97 = 0;
  v98 = 0;
  VariantInit(&pvarg);
  v12 = *((_DWORD *)v10 + 6);
  v13 = v12 + *((_DWORD *)v10 + 3);
  v85 = v12;
  if ( *((_QWORD *)v10 + 5) && v12 )
  {
    v85 = --v12;
    --v13;
  }
  v14 = v13 + 1;
  if ( !*((_DWORD *)v10 + 12) )
    v14 = v13;
  v84 = v14;
  if ( !v14 )
  {
    v20 = WPP_GLOBAL_Control;
    v17 = 0;
    v87 = 0;
    Block = 0;
    goto LABEL_60;
  }
  v15 = v14;
  v16 = (char *)malloc(saturated_mul(v14, 0x18u));
  v17 = v16;
  v87 = v16;
  if ( v16 )
    memset_0(v16, 0, 24 * v15);
  if ( v12 )
  {
    v18 = malloc(saturated_mul(v12, 0x18u));
    v19 = v18;
    Block = v18;
    if ( v18 )
      memset_0(v18, 0, 24LL * v12);
  }
  else
  {
    v19 = 0;
    Block = 0;
  }
  if ( !v17 || v12 && !v19 )
  {
    v11 = -2147024882;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        130,
        (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
        (unsigned int)"CUPnPAutomationProxy::HrInvokeAction(): Failed to allocate arguments array",
        14);
      v20 = WPP_GLOBAL_Control;
    }
    v14 = v84;
    goto LABEL_60;
  }
  v20 = WPP_GLOBAL_Control;
  v21 = 0;
  v22 = *((_DWORD *)v10 + 6) - 1;
LABEL_19:
  v88.decVal.Hi32 = v22;
  if ( v21 < v12 )
  {
    v23 = v22;
    v24 = *((_QWORD *)v10 + 4);
    v11 = 0;
    *(_OWORD *)&v88.decVal.Lo32 = 0;
    v25 = *(_QWORD *)(v24 + 16 * v23 + 8);
    v89 = 0;
    v26 = *(_QWORD *)(v25 + 8);
    VariantInit((VARIANTARG *)&v88.decVal.8);
    v27 = 0;
    v28 = 23;
    while ( 1 )
    {
      v29 = (v28 + v27) / 2;
      v30 = v29;
      if ( (unsigned int)v29 <= 0x17 )
      {
        v31 = _o__wcsicmp(v26, (&off_18005A520)[2 * v29]);
        if ( v31 >= 0 )
        {
          if ( v31 <= 0 )
          {
            _mm_lfence();
            v32 = (unsigned int)dword_18005A528[4 * v30];
            if ( (unsigned int)v32 > 0x18 )
              goto LABEL_33;
LABEL_28:
            v33 = (unsigned __int16)word_18006C8C0[v32];
            if ( !(_WORD)v33 )
              goto LABEL_33;
            v88.iVal = word_18006C8C0[v32];
            if ( (unsigned __int16)v33 > 0x2000u )
            {
LABEL_48:
              v11 = -2147024809;
            }
            else
            {
              if ( (_WORD)v33 != 0x2000 )
              {
                switch ( v33 )
                {
                  case 2:
                  case 3:
                  case 4:
                  case 5:
                  case 6:
                  case 7:
                  case 11:
                  case 16:
                  case 17:
                  case 18:
                  case 19:
                  case 22:
                  case 23:
                    v88.pRecInfo = 0;
                    goto LABEL_33;
                  case 8:
                    v42 = (SAFEARRAY *)SysAllocString(&Format);
                    goto LABEL_44;
                  default:
                    goto LABEL_48;
                }
              }
              rgsabound = (SAFEARRAYBOUND)1LL;
              v88.iVal = 8209;
              v42 = SafeArrayCreate(0x11u, 1u, &rgsabound);
LABEL_44:
              v11 = -2147024882;
              v88.pRecInfo = (IRecordInfo *)v42;
              if ( v42 )
                v11 = 0;
              if ( v11 >= 0 )
              {
LABEL_33:
                v34 = Block;
                v35 = v21;
                v36 = v89;
                v37 = 3LL * v21;
                *(_OWORD *)&Block[v37] = *(_OWORD *)&v88.decVal.Lo32;
                Block[v37 + 2] = v36;
LABEL_37:
                v20 = WPP_GLOBAL_Control;
                goto LABEL_38;
              }
            }
            VariantClear((VARIANTARG *)&v88.decVal.8);
            v34 = Block;
            v35 = v21;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                126,
                (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                (unsigned int)"CUPnPAutomationProxy::HrVariantInitFroXMLType(): Exiting",
                v11);
              goto LABEL_37;
            }
LABEL_38:
            if ( v11 < 0 )
            {
              if ( v20 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v20[14] & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)v20 + 2),
                  129,
                  (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                  (unsigned int)"CUPnPAutomationProxy::HrInvokeAction(): Failed to initialize for XML data type",
                  v11);
                v20 = WPP_GLOBAL_Control;
              }
              v12 = v85;
              v17 = v87;
              v14 = v84;
              goto LABEL_59;
            }
            v38 = 24 * v35;
            v39 = v34[3 * v35];
            v40 = &v34[3 * v35];
            if ( v39 == 8209 )
            {
              v41 = 16396;
            }
            else
            {
              v41 = v39 | 0x4000;
              ++v40;
            }
            v17 = v87;
            *(_WORD *)&v87[v38] = v41;
            *(_QWORD *)&v87[v38 + 8] = v40;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, v21);
              v20 = WPP_GLOBAL_Control;
            }
            ++v21;
            v12 = v85;
            v22 = v88.decVal.Hi32 - 1;
            goto LABEL_19;
          }
          v27 = v30 + 1;
        }
        else
        {
          v28 = v30 - 1;
        }
      }
      if ( v27 > v28 )
      {
        v32 = 24;
        goto LABEL_28;
      }
    }
  }
  v53 = v12;
  v14 = v84;
  v54 = (unsigned int)(*((_DWORD *)v100 + 2) - 1);
  if ( v12 < v84 )
  {
    v55 = v100;
    v56 = v102;
    do
    {
      if ( *((_DWORD *)v10 + 12) && v53 == v84 - 1 )
      {
        v57 = 3LL * v53;
        *(_QWORD *)&v17[8 * v57 + 8] = v56;
        *(_WORD *)&v17[8 * v57] = 13;
      }
      else
      {
        v58 = *((_QWORD *)v55 + 2);
        v59 = 3LL * v53;
        *(_OWORD *)&v17[8 * v59] = *(_OWORD *)(v58 + 24 * v54);
        *(_QWORD *)&v17[8 * v59 + 16] = *(_QWORD *)(v58 + 24 * v54 + 16);
      }
      ++v53;
      v54 = (unsigned int)(v54 - 1);
    }
    while ( v53 < v84 );
    v20 = WPP_GLOBAL_Control;
    v12 = v85;
  }
LABEL_59:
  v7 = this;
LABEL_60:
  if ( v11 >= 0 )
  {
    v43 = *((_QWORD *)v7 + 11);
    *(_OWORD *)&v88.decVal.Lo32 = (unsigned __int64)v17;
    v44 = *((unsigned int *)v10 + 2);
    v89 = v14;
    LOWORD(v83) = 1;
    v45 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64, int, CY *, VARIANTARG *, unsigned __int16 **, _QWORD))(*(_QWORD *)v43 + 48LL))(
            v43,
            v44,
            &GUID_NULL,
            2048,
            v83,
            &v88.cyVal,
            &pvarg,
            v95,
            0);
    v11 = v45;
    if ( v45 == -2147023174 || (unsigned int)(v45 + 2147023170) <= 1 || v45 == -2147417848 )
    {
      v46 = (unsigned int (__fastcall ***)(_QWORD, __int64 *, void **))*((_QWORD *)v7 + 11);
      if ( !v46 || (**v46)(v46, bogusIID, &pBogusInterface) != -2147467262 )
        HrUnregisterDeviceByUDN(*((unsigned __int16 **)v7 + 17));
    }
    if ( v11 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          131,
          WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          *(_QWORD *)v10);
      *(_QWORD *)&v90 = SysAllocString(*(const OLECHAR **)v10);
      if ( (_QWORD)v90 )
      {
        v47 = *((unsigned int *)v10 + 6);
        DWORD2(v90) = 1;
        if ( !(_DWORD)v47 )
        {
          *((_QWORD *)&v91 + 1) = 0;
          LODWORD(v91) = 0;
          goto LABEL_151;
        }
        *((_QWORD *)&v91 + 1) = CoTaskMemAlloc(24 * v47);
        v48 = (VARIANT *)*((_QWORD *)&v91 + 1);
        if ( *((_QWORD *)&v91 + 1) )
        {
          v49 = *((_DWORD *)v10 + 6);
          v50 = 0;
          v51 = 0;
          for ( LODWORD(v91) = v49; (unsigned int)v51 < v49; v51 = (unsigned int)(v51 + 1) )
            VariantInit(&v48[v51]);
          if ( !*((_QWORD *)v10 + 5) )
          {
LABEL_97:
            v60 = 0;
            v61 = v12 + v50 - 1;
            while ( (unsigned int)v60 < v12 )
            {
              v62 = VariantCopyInd(&v48[v61], (const VARIANTARG *)&Block[3 * v60]);
              v11 = v62;
              if ( v62 < 0 )
              {
                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  WPP_SF_sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    135,
                    (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                    (unsigned int)"CUPnPAutomationProxy::HrInvokeAction(): Failed to copy out arg",
                    v62);
                goto LABEL_151;
              }
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  134,
                  WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                  (unsigned int)v61);
              v60 = (unsigned int)(v60 + 1);
              v61 = (unsigned int)(v61 - 1);
            }
            goto LABEL_151;
          }
          v52 = VariantCopyInd(v48, &pvarg);
          v11 = v52;
          if ( v52 >= 0 )
          {
            v50 = 1;
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids);
            goto LABEL_97;
          }
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              133,
              (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
              (unsigned int)"CUPnPAutomationProxy::HrInvokeAction(): Failed to copy retval",
              v52);
          goto LABEL_151;
        }
        v11 = -2147024882;
        v63 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_151;
        v64 = 136;
        v65 = "CUPnPAutomationProxy::HrInvokeAction(): Failed to allocate memory for out args";
LABEL_150:
        WPP_SF_sd(
          *((_QWORD *)v63 + 2),
          v64,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (_DWORD)v65,
          14);
        goto LABEL_151;
      }
      v11 = -2147024882;
      v63 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_151;
      v64 = 137;
LABEL_149:
      v65 = "CUPnPAutomationProxy::HrInvokeAction(): Failed to allocate memory for action name";
      goto LABEL_150;
    }
    v20 = WPP_GLOBAL_Control;
  }
  if ( v11 != -2147352567 )
  {
    if ( v20 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v20[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)v20 + 2),
        143,
        (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
        (unsigned int)"CUPnPAutomationProxy::HrInvokeAction(): Failed to invoke action",
        v11);
    *(_QWORD *)&v90 = SysAllocString(*(const OLECHAR **)v10);
    if ( (_QWORD)v90 )
    {
      DWORD2(v90) = 0;
      v11 = HrBuildFaultResponse((union tagUPNP_CONTROL_RESPONSE_DATA *)&v91, v72, v73, L"501", L"Action Failed");
      goto LABEL_151;
    }
    v11 = -2147024882;
    v63 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_151;
    v64 = 144;
    goto LABEL_149;
  }
  if ( v20 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v20[14] & 0x40) != 0 )
    WPP_SF_S(*((_QWORD *)v20 + 2), 138, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, *(_QWORD *)v10);
  *(_QWORD *)&v90 = SysAllocString(*(const OLECHAR **)v10);
  if ( !(_QWORD)v90 )
  {
    v11 = -2147024882;
    v63 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_151;
    v64 = 142;
    goto LABEL_149;
  }
  DWORD2(v90) = 0;
  if ( (_QWORD)v98 )
  {
    v68 = ValidateCallerAccess();
    if ( v68 < 0 )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          141,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::HrInvokeAction(): Deferred exception info failed,  Caller has incorrect privelege",
          v68);
    }
    else
    {
      v69 = ((__int64 (__fastcall *)(unsigned __int16 **))v98)(v95);
      v11 = v69;
      if ( v69 < 0 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            140,
            (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
            (unsigned int)"CUPnPAutomationProxy::HrInvokeAction(): Failed to fill in deferred exception info",
            v69);
        goto LABEL_151;
      }
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids);
    }
  }
  v70 = L"501";
  v71 = L"Action Failed";
  if ( v95[1] )
    v70 = v95[1];
  if ( v96[0] )
    v71 = v96[0];
  v11 = HrBuildFaultResponse((union tagUPNP_CONTROL_RESPONSE_DATA *)&v91, v66, v67, v70, v71);
LABEL_151:
  v74 = (VARIANT *)Block;
  if ( Block )
  {
    for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
    {
      v76 = &v74[i];
      if ( v76 )
      {
        if ( (v76->vt & 0x4000) != 0 )
        {
          LODWORD(v100) = 0;
          VARIANT_UserFree((unsigned int *)&v100, &v74[i]);
        }
        else
        {
          VariantClear(v76);
        }
        v74 = (VARIANT *)Block;
      }
    }
    free(v74);
  }
  if ( v87 )
    free(v87);
  if ( (pvarg.vt & 0x4000) != 0 )
  {
    LODWORD(v100) = 0;
    VARIANT_UserFree((unsigned int *)&v100, &pvarg);
  }
  else
  {
    VariantClear(&pvarg);
  }
  v6 = v101;
LABEL_169:
  if ( v11 < 0 )
  {
    CUPnPAutomationProxy::FreeControlResponse(v77, (struct tagUPNP_CONTROL_RESPONSE *)&v90);
  }
  else
  {
    v80 = v91;
    *(_OWORD *)v6 = v90;
    v81 = v92;
    *((_OWORD *)v6 + 1) = v80;
    *((_OWORD *)v6 + 2) = v81;
    if ( !v11 )
      return 0;
  }
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      145,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (unsigned int)"CUPnPAutomationProxy::HrInvokeAction(): Exiting",
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002f590  mov     rax, rsp
0x18002f593  mov     [rax+20h], r9
0x18002f597  mov     [rax+18h], r8
0x18002f59b  mov     [rax+10h], rdx
0x18002f59f  mov     [rax+8], rcx
0x18002f5a3  push    rbp
0x18002f5a4  push    rsi
0x18002f5a5  push    rdi
0x18002f5a6  push    r15
0x18002f5a8  lea     rbp, [rax-78h]
0x18002f5ac  sub     rsp, 158h
0x18002f5b3  mov     [rax-28h], rbx
0x18002f5b7  xorps   xmm0, xmm0
0x18002f5ba  mov     [rax-38h], r13
0x18002f5be  mov     rbx, rdx
0x18002f5c1  mov     rdx, [rdx]; unsigned __int16 *
0x18002f5c4  mov     rsi, r8
0x18002f5c7  mov     [rax-40h], r14
0x18002f5cb  mov     r14, rcx
0x18002f5ce  movups  [rbp+70h+var_E8], xmm0
0x18002f5d2  movups  [rbp+70h+var_D8], xmm0
0x18002f5d6  movups  [rbp+70h+var_C8], xmm0
0x18002f5da  call    ?LookupActionByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_ACTION@@PEBG@Z; CUPnPAutomationProxy::LookupActionByName(ushort const *)
0x18002f5df  lea     r15, WPP_GLOBAL_Control
0x18002f5e6  mov     r13, rax
0x18002f5e9  test    rax, rax
0x18002f5ec  jz      loc_180030180
0x18002f5f2  mov     eax, [rbx+8]
0x18002f5f5  cmp     [r13+0Ch], eax
0x18002f5f9  jnz     loc_180030170
0x18002f5ff  xorps   xmm1, xmm1
0x18002f602  mov     [rsp+170h+var_28], r12
0x18002f60a  xorps   xmm0, xmm0
0x18002f60d  lea     rcx, [rbp+70h+pvarg]; pvarg
0x18002f611  xor     eax, eax
0x18002f613  xor     edi, edi
0x18002f615  movups  xmmword ptr [rbp+70h+pvarg], xmm0
0x18002f619  mov     qword ptr [rbp+70h+pvarg+10h], rax
0x18002f61d  movups  xmmword ptr [rbp+70h+var_90], xmm1
0x18002f621  movups  xmmword ptr [rbp+70h+var_80], xmm1
0x18002f625  movups  [rbp+70h+var_70], xmm1
0x18002f629  movups  xmmword ptr [rbp+10h], xmm1
0x18002f62d  call    cs:__imp_VariantInit
0x18002f634  nop     dword ptr [rax+rax+00h]
0x18002f639  mov     r12d, [r13+18h]
0x18002f63d  mov     ecx, [r13+0Ch]
0x18002f641  add     ecx, r12d
0x18002f644  mov     dword ptr [rsp+170h+var_120+4], r12d
0x18002f649  cmp     [r13+28h], rdi
0x18002f64d  jz      short loc_18002F65E
0x18002f64f  test    r12d, r12d
0x18002f652  jz      short loc_18002F65E
0x18002f654  dec     r12d
0x18002f657  mov     dword ptr [rsp+170h+var_120+4], r12d
0x18002f65c  dec     ecx
0x18002f65e  cmp     [r13+30h], edi
0x18002f662  lea     r11d, [rcx+1]
0x18002f666  mov     ebx, 1
0x18002f66b  cmovz   r11d, ecx
0x18002f66f  mov     dword ptr [rsp+170h+var_120], r11d
0x18002f674  test    r11d, r11d
0x18002f677  jz      loc_18002FD05
0x18002f67d  mov     ebx, r11d
0x18002f680  mov     eax, 18h
0x18002f685  mul     rbx
0x18002f688  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18002f68f  cmovb   rax, r15
0x18002f693  mov     rcx, rax; Size
0x18002f696  call    cs:__imp_malloc
0x18002f69d  nop     dword ptr [rax+rax+00h]
0x18002f6a2  mov     rsi, rax
0x18002f6a5  mov     [rsp+170h+var_110], rax
0x18002f6aa  test    rax, rax
0x18002f6ad  jz      short loc_18002F6C1
0x18002f6af  lea     r8, [rbx+rbx*2]
0x18002f6b3  xor     edx, edx; Val
0x18002f6b5  shl     r8, 3; Size
0x18002f6b9  mov     rcx, rax; void *
0x18002f6bc  call    memset_0
0x18002f6c1  test    r12d, r12d
0x18002f6c4  jz      short loc_18002F705
0x18002f6c6  mov     ebx, r12d
0x18002f6c9  mov     eax, 18h
0x18002f6ce  mul     rbx
0x18002f6d1  cmovb   rax, r15
0x18002f6d5  mov     rcx, rax; Size
0x18002f6d8  call    cs:__imp_malloc
0x18002f6df  nop     dword ptr [rax+rax+00h]
0x18002f6e4  mov     r15, rax
0x18002f6e7  mov     [rsp+170h+Block], rax
0x18002f6ec  test    rax, rax
0x18002f6ef  jz      short loc_18002F70D
0x18002f6f1  lea     r8, [rbx+rbx*2]
0x18002f6f5  xor     edx, edx; Val
0x18002f6f7  shl     r8, 3; Size
0x18002f6fb  mov     rcx, rax; void *
0x18002f6fe  call    memset_0
0x18002f703  jmp     short loc_18002F70D
0x18002f705  xor     r15d, r15d
0x18002f708  mov     [rsp+170h+Block], r15
0x18002f70d  test    rsi, rsi
0x18002f710  jz      loc_18002FCB6
0x18002f716  test    r12d, r12d
0x18002f719  jz      short loc_18002F724
0x18002f71b  test    r15, r15
0x18002f71e  jz      loc_18002FCB6
0x18002f724  mov     eax, [r13+18h]
0x18002f728  lea     r15, WPP_GLOBAL_Control
0x18002f72f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f736  xor     r14d, r14d
0x18002f739  movaps  [rsp+170h+var_58+8], xmm6
0x18002f741  dec     eax
0x18002f743  xorps   xmm6, xmm6
0x18002f746  mov     dword ptr [rsp+170h+var_108+4], eax
0x18002f74a  mov     dword ptr [rsp+170h+var_108], r14d
0x18002f74f  cmp     r14d, r12d
0x18002f752  jnb     loc_18002FC22
0x18002f758  mov     ecx, eax
0x18002f75a  xorps   xmm0, xmm0
0x18002f75d  mov     rax, [r13+20h]
0x18002f761  add     rcx, rcx
0x18002f764  xor     edi, edi
0x18002f766  movups  xmmword ptr [rsp+170h+var_108+8], xmm0
0x18002f76b  mov     rcx, [rax+rcx*8+8]
0x18002f770  xor     eax, eax
0x18002f772  mov     [rbp+70h+var_F0], rax
0x18002f776  mov     r12, [rcx+8]
0x18002f77a  lea     rcx, [rsp+170h+var_108+8]; pvarg
0x18002f77f  call    cs:__imp_VariantInit
0x18002f786  nop     dword ptr [rax+rax+00h]
0x18002f78b  xor     esi, esi
0x18002f78d  mov     r15d, 17h
0x18002f793  lea     eax, [r15+rsi]
0x18002f797  cdq
0x18002f798  sub     eax, edx
0x18002f79a  sar     eax, 1
0x18002f79c  movsxd  rbx, eax
0x18002f79f  cmp     ebx, 17h
0x18002f7a2  ja      short loc_18002F7D7
0x18002f7a4  lea     rax, __ImageBase
0x18002f7ab  mov     r14, rbx
0x18002f7ae  add     r14, r14
0x18002f7b1  mov     rcx, r12
0x18002f7b4  mov     rdx, ds:rva off_18005A520[rax+r14*8]; "bin.base64" ...
0x18002f7bc  call    cs:__imp__o__wcsicmp
0x18002f7c3  nop     dword ptr [rax+rax+00h]
0x18002f7c8  test    eax, eax
0x18002f7ca  jns     short loc_18002F7D2
0x18002f7cc  lea     r15d, [rbx-1]
0x18002f7d0  jmp     short loc_18002F7D7
0x18002f7d2  jle     short loc_18002F838
0x18002f7d4  lea     esi, [rbx+1]
0x18002f7d7  cmp     esi, r15d
0x18002f7da  jle     short loc_18002F793
0x18002f7dc  mov     eax, 18h
0x18002f7e1  lea     rdx, __ImageBase
0x18002f7e8  movzx   ecx, ds:rva word_18006C8C0[rdx+rax*2]
0x18002f7f0  xor     eax, eax
0x18002f7f2  cmp     ax, cx
0x18002f7f5  jz      short loc_18002F853
0x18002f7f7  mov     eax, 2000h
0x18002f7fc  mov     word ptr [rsp+170h+var_108+8], cx
0x18002f801  cmp     cx, ax
0x18002f804  ja      def_18002F832; jumptable 000000018002F832 default case, cases 9,10,12-15,20,21
0x18002f80a  jz      loc_18002F914
0x18002f810  mov     eax, ecx
0x18002f812  add     eax, 0FFFFFFFEh; switch 22 cases
0x18002f815  cmp     eax, 15h
0x18002f818  ja      def_18002F832; jumptable 000000018002F832 default case, cases 9,10,12-15,20,21
0x18002f81e  cdqe
0x18002f820  movzx   eax, ds:(byte_18003023C - 180000000h)[rdx+rax]
0x18002f828  mov     ecx, ds:(jpt_18002F832 - 180000000h)[rdx+rax*4]
0x18002f82f  add     rcx, rdx
0x18002f832  jmp     rcx; switch jump
0x18002f838  lfence
0x18002f83b  lea     rdx, __ImageBase
0x18002f842  mov     eax, ds:rva dword_18005A528[rdx+r14*8]
0x18002f84a  test    eax, eax
0x18002f84c  js      short loc_18002F853
0x18002f84e  cmp     eax, 18h
0x18002f851  jbe     short loc_18002F7E8
0x18002f853  mov     r14d, dword ptr [rsp+170h+var_108]
0x18002f858  mov     r15, [rsp+170h+Block]
0x18002f85d  mov     ebx, r14d
0x18002f860  movsd   xmm1, [rbp+70h+var_F0]
0x18002f865  movups  xmm0, xmmword ptr [rsp+170h+var_108+8]
0x18002f86a  lea     rax, [r14+r14*2]
0x18002f86e  movups  xmmword ptr [r15+rax*8], xmm0
0x18002f873  movsd   qword ptr [r15+rax*8+10h], xmm1
0x18002f87a  test    edi, edi
0x18002f87c  jz      short loc_18002F8B7
0x18002f87e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f885  lea     rax, WPP_GLOBAL_Control
0x18002f88c  cmp     rcx, rax
0x18002f88f  jz      short loc_18002F8BE
0x18002f891  test    byte ptr [rcx+1Ch], 1
0x18002f895  jz      short loc_18002F8BE
0x18002f897  mov     rcx, [rcx+10h]
0x18002f89b  lea     r9, aCupnpautomatio_1; "CUPnPAutomationProxy::HrVariantInitFroX"...
0x18002f8a2  mov     edx, 7Eh ; '~'
0x18002f8a7  mov     dword ptr [rsp+170h+var_150], edi
0x18002f8ab  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002f8b2  call    WPP_SF_sd
0x18002f8b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8be  test    edi, edi
0x18002f8c0  js      loc_18002F9EF
0x18002f8c6  lea     rax, [rbx+rbx*2]
0x18002f8ca  mov     ecx, 2011h
0x18002f8cf  lea     rax, ds:0[rax*8]
0x18002f8d7  movzx   r8d, word ptr [rax+r15]
0x18002f8dc  lea     rdx, [rax+r15]
0x18002f8e0  cmp     r8w, cx
0x18002f8e4  jnz     loc_18002F986
0x18002f8ea  mov     ecx, 400Ch
0x18002f8ef  jmp     loc_18002F993
0x18002f8f4  movsd   qword ptr [rsp+170h+var_108+10h], xmm6; jumptable 000000018002F832 cases 2-7,11,16-19,22,23
0x18002f8fa  jmp     loc_18002F853
0x18002f8ff  lea     rcx, Format; jumptable 000000018002F832 case 8
0x18002f906  call    cs:__imp_SysAllocString
0x18002f90d  nop     dword ptr [rax+rax+00h]
0x18002f912  jmp     short loc_18002F940
0x18002f914  mov     eax, 2011h
0x18002f919  mov     qword ptr [rbp+70h+rgsabound.cElements], 1
0x18002f921  mov     edx, 1; cDims
0x18002f926  mov     word ptr [rsp+170h+var_108+8], ax
0x18002f92b  mov     ecx, 11h; vt
0x18002f930  lea     r8, [rbp+70h+rgsabound]; rgsabound
0x18002f934  call    cs:__imp_SafeArrayCreate
0x18002f93b  nop     dword ptr [rax+rax+00h]
0x18002f940  mov     rcx, rax
0x18002f943  mov     edi, 8007000Eh
0x18002f948  xor     eax, eax
0x18002f94a  mov     qword ptr [rsp+170h+var_108+10h], rcx
0x18002f94f  test    rcx, rcx
0x18002f952  cmovnz  edi, eax
0x18002f955  test    edi, edi
0x18002f957  js      short loc_18002F963
0x18002f959  jmp     loc_18002F853
0x18002f95e  mov     edi, 80070057h; jumptable 000000018002F832 default case, cases 9,10,12-15,20,21
0x18002f963  lea     rcx, [rsp+170h+var_108+8]; pvarg
0x18002f968  call    cs:__imp_VariantClear
0x18002f96f  nop     dword ptr [rax+rax+00h]
0x18002f974  mov     r14d, dword ptr [rsp+170h+var_108]
0x18002f979  mov     r15, [rsp+170h+Block]
0x18002f97e  mov     ebx, r14d
0x18002f981  jmp     loc_18002F87E
0x18002f986  movzx   ecx, r8w
0x18002f98a  or      cx, 4000h
0x18002f98f  add     rdx, 8
0x18002f993  mov     rsi, [rsp+170h+var_110]
0x18002f998  mov     r8, rsi
0x18002f99b  mov     [rax+rsi], cx
0x18002f99f  mov     [rax+rsi+8], rdx
0x18002f9a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9ab  lea     r15, WPP_GLOBAL_Control
0x18002f9b2  cmp     rcx, r15
0x18002f9b5  jz      short loc_18002F9DC
0x18002f9b7  test    byte ptr [rcx+1Ch], 40h
0x18002f9bb  jz      short loc_18002F9DC
0x18002f9bd  mov     rcx, [rcx+10h]
0x18002f9c1  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002f9c8  mov     edx, 7Fh
0x18002f9cd  mov     r9d, r14d
0x18002f9d0  call    WPP_SF_d
0x18002f9d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9dc  mov     eax, dword ptr [rsp+170h+var_108+4]
0x18002f9e0  inc     r14d
0x18002f9e3  mov     r12d, dword ptr [rsp+170h+var_120+4]
0x18002f9e8  dec     eax
0x18002f9ea  jmp     loc_18002F746
0x18002f9ef  lea     r15, WPP_GLOBAL_Control
0x18002f9f6  cmp     rcx, r15
0x18002f9f9  jz      short loc_18002FA28
0x18002f9fb  test    byte ptr [rcx+1Ch], 1
0x18002f9ff  jz      short loc_18002FA28
0x18002fa01  mov     rcx, [rcx+10h]
0x18002fa05  lea     r9, aCupnpautomatio_34; "CUPnPAutomationProxy::HrInvokeAction():"...
0x18002fa0c  mov     edx, 81h
0x18002fa11  mov     dword ptr [rsp+170h+var_150], edi
0x18002fa15  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002fa1c  call    WPP_SF_sd
0x18002fa21  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa28  mov     r12d, dword ptr [rsp+170h+var_120+4]
0x18002fa2d  mov     rsi, [rsp+170h+var_110]
0x18002fa32  mov     r11d, dword ptr [rsp+170h+var_120]
0x18002fa37  mov     r14, [rbp+70h+arg_0]
0x18002fa3e  movaps  xmm6, [rsp+170h+var_58+8]
0x18002fa46  mov     ebx, 1
0x18002fa4b  test    edi, edi
0x18002fa4d  js      loc_18002FE81
0x18002fa53  mov     rcx, [r14+58h]
0x18002fa57  lea     rdx, [rbp+70h+var_90]
0x18002fa5b  mov     qword ptr [rsp+40h], 0
0x18002fa64  lea     r8, GUID_NULL
0x18002fa6b  mov     [rsp+170h+var_138], rdx
0x18002fa70  mov     r9d, 800h
0x18002fa76  mov     qword ptr [rsp+170h+var_108+8], rsi
0x18002fa7b  lea     rdx, [rbp+70h+pvarg]
0x18002fa7f  mov     [rsp+170h+var_140], rdx
0x18002fa84  lea     rdx, [rsp+170h+var_108+8]
  ... truncated ...
```
