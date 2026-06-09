# CUPnPAutomationProxy::HrInvokeAction(tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *,IUnknown *)

- ea: `0x18002dd70`
- end: `0x18002e9aa`
- name: `?HrInvokeAction@CUPnPAutomationProxy@@AEAAJPEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@PEAUIUnknown@@@Z`
- size: `3130`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, struct tagUPNP_CONTROL_REQUEST *, struct tagUPNP_CONTROL_RESPONSE *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002dcbc`

## callees

- `0x18000db4c`
- `0x180029a50`
- `0x18002dd70`
- `0x180032fd4`
- `0x180035dfc`
- `0x180038ce4`
- `0x180039388`
- `0x18003994c`
- `0x180039a84`
- `0x18003ae80`
- `0x1800507d0`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002df89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002df89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e86b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e883`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e86b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e883`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002de70`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002deac`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002de70`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002deac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e319`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e319`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e0c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e2ef`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e63f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e79b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e0c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e2ef`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e63f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e79b`
- `OLEAUT32!__imp_VariantInit` at `0x18002de0d`
- `OLEAUT32!__imp_VariantInit` at `0x18002df4d`
- `OLEAUT32!__imp_VariantInit` at `0x18002e348`
- `OLEAUT32!__imp_VariantInit` at `0x18002de0d`
- `OLEAUT32!__imp_VariantInit` at `0x18002df4d`
- `OLEAUT32!__imp_VariantInit` at `0x18002e348`
- `OLEAUT32!__imp_VariantClear` at `0x18002e11f`
- `OLEAUT32!__imp_VariantClear` at `0x18002e84f`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8bc`
- `OLEAUT32!__imp_VariantClear` at `0x18002e11f`
- `OLEAUT32!__imp_VariantClear` at `0x18002e84f`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8bc`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002e365`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002e519`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002e365`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002e519`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e0f1`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e0f1`
- `OLEAUT32!__imp_VARIANT_UserFree` at `0x18002e847`
- `OLEAUT32!__imp_VARIANT_UserFree` at `0x18002e8a9`
- `OLEAUT32!__imp_VARIANT_UserFree` at `0x18002e847`
- `OLEAUT32!__imp_VARIANT_UserFree` at `0x18002e8a9`

## string_xrefs

- `0x18002e05e`: `CUPnPAutomationProxy::HrVariantInitFroXMLType(): Exiting`
- `0x18002e1b6`: `CUPnPAutomationProxy::HrInvokeAction(): Failed to initialize for XML data type`
- `0x18002e57f`: `CUPnPAutomationProxy::HrInvokeAction(): Failed to copy out arg`
- `0x18002e4da`: `CUPnPAutomationProxy::HrInvokeAction(): Failed to copy retval`

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
        v31 = _o__wcsicmp(v26, (&off_180056550)[2 * v29]);
        if ( v31 >= 0 )
        {
          if ( v31 <= 0 )
          {
            _mm_lfence();
            v32 = (unsigned int)dword_180056558[4 * v30];
            if ( (unsigned int)v32 > 0x18 )
              goto LABEL_33;
LABEL_28:
            v33 = (unsigned __int16)word_1800688D0[v32];
            if ( !(_WORD)v33 )
              goto LABEL_33;
            v88.iVal = word_1800688D0[v32];
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
0x18002dd70  mov     rax, rsp
0x18002dd73  mov     [rax+20h], r9
0x18002dd77  mov     [rax+18h], r8
0x18002dd7b  mov     [rax+10h], rdx
0x18002dd7f  mov     [rax+8], rcx
0x18002dd83  push    rbp
0x18002dd84  push    rsi
0x18002dd85  push    rdi
0x18002dd86  push    r15
0x18002dd88  lea     rbp, [rax-78h]
0x18002dd8c  sub     rsp, 158h
0x18002dd93  mov     [rax-28h], rbx
0x18002dd97  xorps   xmm0, xmm0
0x18002dd9a  mov     [rax-38h], r13
0x18002dd9e  mov     rbx, rdx
0x18002dda1  mov     rdx, [rdx]; unsigned __int16 *
0x18002dda4  mov     rsi, r8
0x18002dda7  mov     [rax-40h], r14
0x18002ddab  mov     r14, rcx
0x18002ddae  movups  [rbp+70h+var_E8], xmm0
0x18002ddb2  movups  [rbp+70h+var_D8], xmm0
0x18002ddb6  movups  [rbp+70h+var_C8], xmm0
0x18002ddba  call    ?LookupActionByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_ACTION@@PEBG@Z; CUPnPAutomationProxy::LookupActionByName(ushort const *)
0x18002ddbf  lea     r15, WPP_GLOBAL_Control
0x18002ddc6  mov     r13, rax
0x18002ddc9  test    rax, rax
0x18002ddcc  jz      loc_18002E8DB
0x18002ddd2  mov     eax, [rbx+8]
0x18002ddd5  cmp     [r13+0Ch], eax
0x18002ddd9  jnz     loc_18002E8CB
0x18002dddf  xorps   xmm1, xmm1
0x18002dde2  mov     [rsp+170h+var_28], r12
0x18002ddea  xorps   xmm0, xmm0
0x18002dded  lea     rcx, [rbp+70h+pvarg]; pvarg
0x18002ddf1  xor     eax, eax
0x18002ddf3  xor     edi, edi
0x18002ddf5  movups  xmmword ptr [rbp+70h+pvarg], xmm0
0x18002ddf9  mov     qword ptr [rbp+70h+pvarg+10h], rax
0x18002ddfd  movups  xmmword ptr [rbp+70h+var_90], xmm1
0x18002de01  movups  xmmword ptr [rbp+70h+var_80], xmm1
0x18002de05  movups  [rbp+70h+var_70], xmm1
0x18002de09  movups  xmmword ptr [rbp+10h], xmm1
0x18002de0d  call    cs:__imp_VariantInit
0x18002de13  mov     r12d, [r13+18h]
0x18002de17  mov     ecx, [r13+0Ch]
0x18002de1b  add     ecx, r12d
0x18002de1e  mov     dword ptr [rsp+170h+var_120+4], r12d
0x18002de23  cmp     [r13+28h], rdi
0x18002de27  jz      short loc_18002DE38
0x18002de29  test    r12d, r12d
0x18002de2c  jz      short loc_18002DE38
0x18002de2e  dec     r12d
0x18002de31  mov     dword ptr [rsp+170h+var_120+4], r12d
0x18002de36  dec     ecx
0x18002de38  cmp     [r13+30h], edi
0x18002de3c  lea     r11d, [rcx+1]
0x18002de40  mov     ebx, 1
0x18002de45  cmovz   r11d, ecx
0x18002de49  mov     dword ptr [rsp+170h+var_120], r11d
0x18002de4e  test    r11d, r11d
0x18002de51  jz      loc_18002E498
0x18002de57  mov     ebx, r11d
0x18002de5a  mov     eax, 18h
0x18002de5f  mul     rbx
0x18002de62  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18002de69  cmovb   rax, r15
0x18002de6d  mov     rcx, rax; Size
0x18002de70  call    cs:__imp_malloc
0x18002de76  mov     rsi, rax
0x18002de79  mov     [rsp+170h+var_110], rax
0x18002de7e  test    rax, rax
0x18002de81  jz      short loc_18002DE95
0x18002de83  lea     r8, [rbx+rbx*2]
0x18002de87  xor     edx, edx; Val
0x18002de89  shl     r8, 3; Size
0x18002de8d  mov     rcx, rax; void *
0x18002de90  call    memset_0
0x18002de95  test    r12d, r12d
0x18002de98  jz      short loc_18002DED3
0x18002de9a  mov     ebx, r12d
0x18002de9d  mov     eax, 18h
0x18002dea2  mul     rbx
0x18002dea5  cmovb   rax, r15
0x18002dea9  mov     rcx, rax; Size
0x18002deac  call    cs:__imp_malloc
0x18002deb2  mov     r15, rax
0x18002deb5  mov     [rsp+170h+Block], rax
0x18002deba  test    rax, rax
0x18002debd  jz      short loc_18002DEDB
0x18002debf  lea     r8, [rbx+rbx*2]
0x18002dec3  xor     edx, edx; Val
0x18002dec5  shl     r8, 3; Size
0x18002dec9  mov     rcx, rax; void *
0x18002decc  call    memset_0
0x18002ded1  jmp     short loc_18002DEDB
0x18002ded3  xor     r15d, r15d
0x18002ded6  mov     [rsp+170h+Block], r15
0x18002dedb  test    rsi, rsi
0x18002dede  jz      loc_18002E449
0x18002dee4  test    r12d, r12d
0x18002dee7  jz      short loc_18002DEF2
0x18002dee9  test    r15, r15
0x18002deec  jz      loc_18002E449
0x18002def2  mov     eax, [r13+18h]
0x18002def6  lea     r15, WPP_GLOBAL_Control
0x18002defd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df04  xor     r14d, r14d
0x18002df07  movaps  [rsp+170h+var_58+8], xmm6
0x18002df0f  dec     eax
0x18002df11  xorps   xmm6, xmm6
0x18002df14  mov     dword ptr [rsp+170h+var_108+4], eax
0x18002df18  mov     dword ptr [rsp+170h+var_108], r14d
0x18002df1d  cmp     r14d, r12d
0x18002df20  jnb     loc_18002E3B6
0x18002df26  mov     ecx, eax
0x18002df28  xorps   xmm0, xmm0
0x18002df2b  mov     rax, [r13+20h]
0x18002df2f  add     rcx, rcx
0x18002df32  xor     edi, edi
0x18002df34  movups  xmmword ptr [rsp+170h+var_108+8], xmm0
0x18002df39  mov     rcx, [rax+rcx*8+8]
0x18002df3e  xor     eax, eax
0x18002df40  mov     [rbp+70h+var_F0], rax
0x18002df44  mov     r12, [rcx+8]
0x18002df48  lea     rcx, [rsp+170h+var_108+8]; pvarg
0x18002df4d  call    cs:__imp_VariantInit
0x18002df53  xor     esi, esi
0x18002df55  mov     r15d, 17h
0x18002df5b  nop     dword ptr [rax+rax+00h]
0x18002df60  lea     eax, [r15+rsi]
0x18002df64  cdq
0x18002df65  sub     eax, edx
0x18002df67  sar     eax, 1
0x18002df69  movsxd  rbx, eax
0x18002df6c  cmp     ebx, 17h
0x18002df6f  ja      short loc_18002DF9E
0x18002df71  lea     rax, __ImageBase
0x18002df78  mov     r14, rbx
0x18002df7b  add     r14, r14
0x18002df7e  mov     rcx, r12
0x18002df81  mov     rdx, ds:rva off_180056550[rax+r14*8]; "bin.base64" ...
0x18002df89  call    cs:__imp__o__wcsicmp
0x18002df8f  test    eax, eax
0x18002df91  jns     short loc_18002DF99
0x18002df93  lea     r15d, [rbx-1]
0x18002df97  jmp     short loc_18002DF9E
0x18002df99  jle     short loc_18002DFFB
0x18002df9b  lea     esi, [rbx+1]
0x18002df9e  cmp     esi, r15d
0x18002dfa1  jle     short loc_18002DF60
0x18002dfa3  mov     eax, 18h
0x18002dfa8  lea     rdx, __ImageBase
0x18002dfaf  movzx   ecx, ds:rva word_1800688D0[rdx+rax*2]
0x18002dfb7  xor     eax, eax
0x18002dfb9  cmp     ax, cx
0x18002dfbc  jz      short loc_18002E016
0x18002dfbe  mov     eax, 2000h
0x18002dfc3  mov     word ptr [rsp+170h+var_108+8], cx
0x18002dfc8  cmp     cx, ax
0x18002dfcb  ja      def_18002DFF9; jumptable 000000018002DFF9 default case, cases 9,10,12-15,20,21
0x18002dfd1  jz      loc_18002E0D1
0x18002dfd7  mov     eax, ecx
0x18002dfd9  add     eax, 0FFFFFFFEh; switch 22 cases
0x18002dfdc  cmp     eax, 15h
0x18002dfdf  ja      def_18002DFF9; jumptable 000000018002DFF9 default case, cases 9,10,12-15,20,21
0x18002dfe5  cdqe
0x18002dfe7  movzx   eax, ds:(byte_18002E994 - 180000000h)[rdx+rax]
0x18002dfef  mov     ecx, ds:(jpt_18002DFF9 - 180000000h)[rdx+rax*4]
0x18002dff6  add     rcx, rdx
0x18002dff9  jmp     rcx; switch jump
0x18002dffb  lfence
0x18002dffe  lea     rdx, __ImageBase
0x18002e005  mov     eax, ds:rva dword_180056558[rdx+r14*8]
0x18002e00d  test    eax, eax
0x18002e00f  js      short loc_18002E016
0x18002e011  cmp     eax, 18h
0x18002e014  jbe     short loc_18002DFAF
0x18002e016  mov     r14d, dword ptr [rsp+170h+var_108]
0x18002e01b  mov     r15, [rsp+170h+Block]
0x18002e020  mov     ebx, r14d
0x18002e023  movsd   xmm1, [rbp+70h+var_F0]
0x18002e028  movups  xmm0, xmmword ptr [rsp+170h+var_108+8]
0x18002e02d  lea     rax, [r14+r14*2]
0x18002e031  movups  xmmword ptr [r15+rax*8], xmm0
0x18002e036  movsd   qword ptr [r15+rax*8+10h], xmm1
0x18002e03d  test    edi, edi
0x18002e03f  jz      short loc_18002E07A
0x18002e041  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e048  lea     rax, WPP_GLOBAL_Control
0x18002e04f  cmp     rcx, rax
0x18002e052  jz      short loc_18002E081
0x18002e054  test    byte ptr [rcx+1Ch], 1
0x18002e058  jz      short loc_18002E081
0x18002e05a  mov     rcx, [rcx+10h]
0x18002e05e  lea     r9, aCupnpautomatio_1; "CUPnPAutomationProxy::HrVariantInitFroX"...
0x18002e065  mov     edx, 7Eh ; '~'
0x18002e06a  mov     dword ptr [rsp+170h+var_150], edi
0x18002e06e  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002e075  call    WPP_SF_sd
0x18002e07a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e081  test    edi, edi
0x18002e083  js      loc_18002E1A0
0x18002e089  lea     rax, [rbx+rbx*2]
0x18002e08d  mov     ecx, 2011h
0x18002e092  lea     rax, ds:0[rax*8]
0x18002e09a  movzx   r8d, word ptr [rax+r15]
0x18002e09f  lea     rdx, [rax+r15]
0x18002e0a3  cmp     r8w, cx
0x18002e0a7  jnz     loc_18002E137
0x18002e0ad  mov     ecx, 400Ch
0x18002e0b2  jmp     loc_18002E144
0x18002e0b7  movsd   qword ptr [rsp+170h+var_108+10h], xmm6; jumptable 000000018002DFF9 cases 2-7,11,16-19,22,23
0x18002e0bd  jmp     loc_18002E016
0x18002e0c2  lea     rcx, Format; jumptable 000000018002DFF9 case 8
0x18002e0c9  call    cs:__imp_SysAllocString
0x18002e0cf  jmp     short loc_18002E0F7
0x18002e0d1  mov     eax, 2011h
0x18002e0d6  mov     qword ptr [rbp+70h+rgsabound.cElements], 1
0x18002e0de  mov     edx, 1; cDims
0x18002e0e3  mov     word ptr [rsp+170h+var_108+8], ax
0x18002e0e8  mov     ecx, 11h; vt
0x18002e0ed  lea     r8, [rbp+70h+rgsabound]; rgsabound
0x18002e0f1  call    cs:__imp_SafeArrayCreate
0x18002e0f7  mov     rcx, rax
0x18002e0fa  mov     edi, 8007000Eh
0x18002e0ff  xor     eax, eax
0x18002e101  mov     qword ptr [rsp+170h+var_108+10h], rcx
0x18002e106  test    rcx, rcx
0x18002e109  cmovnz  edi, eax
0x18002e10c  test    edi, edi
0x18002e10e  js      short loc_18002E11A
0x18002e110  jmp     loc_18002E016
0x18002e115  mov     edi, 80070057h; jumptable 000000018002DFF9 default case, cases 9,10,12-15,20,21
0x18002e11a  lea     rcx, [rsp+170h+var_108+8]; pvarg
0x18002e11f  call    cs:__imp_VariantClear
0x18002e125  mov     r14d, dword ptr [rsp+170h+var_108]
0x18002e12a  mov     r15, [rsp+170h+Block]
0x18002e12f  mov     ebx, r14d
0x18002e132  jmp     loc_18002E041
0x18002e137  movzx   ecx, r8w
0x18002e13b  or      cx, 4000h
0x18002e140  add     rdx, 8
0x18002e144  mov     rsi, [rsp+170h+var_110]
0x18002e149  mov     r8, rsi
0x18002e14c  mov     [rax+rsi], cx
0x18002e150  mov     [rax+rsi+8], rdx
0x18002e155  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e15c  lea     r15, WPP_GLOBAL_Control
0x18002e163  cmp     rcx, r15
0x18002e166  jz      short loc_18002E18D
0x18002e168  test    byte ptr [rcx+1Ch], 40h
0x18002e16c  jz      short loc_18002E18D
0x18002e16e  mov     rcx, [rcx+10h]
0x18002e172  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002e179  mov     edx, 7Fh
0x18002e17e  mov     r9d, r14d
0x18002e181  call    WPP_SF_d
0x18002e186  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e18d  mov     eax, dword ptr [rsp+170h+var_108+4]
0x18002e191  inc     r14d
0x18002e194  mov     r12d, dword ptr [rsp+170h+var_120+4]
0x18002e199  dec     eax
0x18002e19b  jmp     loc_18002DF14
0x18002e1a0  lea     r15, WPP_GLOBAL_Control
0x18002e1a7  cmp     rcx, r15
0x18002e1aa  jz      short loc_18002E1D9
0x18002e1ac  test    byte ptr [rcx+1Ch], 1
0x18002e1b0  jz      short loc_18002E1D9
0x18002e1b2  mov     rcx, [rcx+10h]
0x18002e1b6  lea     r9, aCupnpautomatio_34; "CUPnPAutomationProxy::HrInvokeAction():"...
0x18002e1bd  mov     edx, 81h
0x18002e1c2  mov     dword ptr [rsp+170h+var_150], edi
0x18002e1c6  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002e1cd  call    WPP_SF_sd
0x18002e1d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e1d9  mov     r12d, dword ptr [rsp+170h+var_120+4]
0x18002e1de  mov     rsi, [rsp+170h+var_110]
0x18002e1e3  mov     r11d, dword ptr [rsp+170h+var_120]
0x18002e1e8  mov     r14, [rbp+70h+arg_0]
0x18002e1ef  movaps  xmm6, [rsp+170h+var_58+8]
0x18002e1f7  mov     ebx, 1
0x18002e1fc  test    edi, edi
0x18002e1fe  js      loc_18002E60B
0x18002e204  mov     rcx, [r14+58h]
0x18002e208  lea     rdx, [rbp+70h+var_90]
0x18002e20c  mov     qword ptr [rsp+40h], 0
0x18002e215  lea     r8, GUID_NULL
0x18002e21c  mov     [rsp+170h+var_138], rdx
0x18002e221  mov     r9d, 800h
0x18002e227  mov     qword ptr [rsp+170h+var_108+8], rsi
0x18002e22c  lea     rdx, [rbp+70h+pvarg]
0x18002e230  mov     [rsp+170h+var_140], rdx
0x18002e235  lea     rdx, [rsp+170h+var_108+8]
0x18002e23a  mov     [rsp+170h+var_148], rdx
0x18002e23f  mov     edx, [r13+8]
0x18002e243  mov     dword ptr [rbp+70h+var_F0], r11d
0x18002e247  mov     qword ptr [rsp+170h+var_108+10h], 0
0x18002e250  mov     dword ptr [rbp+70h+var_F0+4], 0
0x18002e257  mov     rax, [rcx]
0x18002e25a  mov     word ptr [rsp+170h+var_150], bx
  ... truncated ...
```
