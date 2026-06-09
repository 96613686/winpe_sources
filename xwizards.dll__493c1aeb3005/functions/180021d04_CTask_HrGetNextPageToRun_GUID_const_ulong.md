# CTask::HrGetNextPageToRun(_GUID const *,ulong *)

- ea: `0x180021d04`
- end: `0x180022f15`
- name: `?HrGetNextPageToRun@CTask@@AEAAJPEBU_GUID@@PEAK@Z`
- size: `4625`
- prototype: `__int64 __fastcall(CTask *__hidden this, const struct _GUID *, unsigned int *)`
- caller_count: `3`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021c98`
- `0x180024074`
- `0x180025780`

## callees

- `0x180001200`
- `0x1800015b4`
- `0x1800085a8`
- `0x180008634`
- `0x18000addc`
- `0x18000ae04`
- `0x18000ae44`
- `0x18000c3ac`
- `0x18000df3c`
- `0x18000e098`
- `0x180011cc8`
- `0x18002042c`
- `0x1800204b0`
- `0x180020b3c`
- `0x180021d04`
- `0x180022f1c`
- `0x180022fec`
- `0x18002336c`
- `0x180023a64`
- `0x180023b88`
- `0x180023c5c`
- `0x180023d80`
- `0x180024b44`
- `0x180024c90`
- `0x18003174c`
- `0x180031b98`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800225dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800229b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800225dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800229b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d65`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTask::HrGetNextPageToRun(CTask *this, const struct _GUID *a2, unsigned int *a3)
{
  CTask *v5; // rsi
  int SpecifiedWizardModule; // edi
  PVOID *v7; // rcx
  __int64 v8; // rdx
  const struct _GUID *v9; // rax
  __int64 v10; // rax
  unsigned int *v11; // r8
  const struct _GUID *v12; // rdx
  int v14; // r13d
  int v15; // edx
  unsigned int PageToParsingStack; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20; // eax
  unsigned int ParentPage; // eax
  struct _XWIZARD_PAGE_DATA *v22; // r13
  int v23; // eax
  _QWORD *v24; // rdx
  __int64 v25; // rax
  int v26; // r8d
  struct _GUID *v27; // r13
  __int64 v28; // rax
  int RecycledPage; // eax
  struct _XWIZARD_PAGE_DATA *v30; // rax
  struct _XWIZARD_PAGE_DATA *v31; // r14
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  CPXWizardSemaphoreLock *v35; // rax
  unsigned __int16 *v36; // rdx
  int v37; // r8d
  int v38; // r9d
  CPXWizardSemaphoreLock *v39; // rax
  int v40; // eax
  int Page; // eax
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  struct _XWIZARD_PAGE_DATA *v44; // r14
  __int128 v45; // xmm0
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rdx
  unsigned __int64 v54; // rax
  char *v55; // rcx
  char *v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rcx
  unsigned __int64 v60; // r13
  unsigned __int16 *v61; // rax
  unsigned __int16 *v62; // r11
  unsigned __int16 *v63; // r11
  struct CUnknown *v64; // rdx
  int v65; // eax
  int v66; // eax
  int v67; // eax
  PVOID *v68; // rcx
  struct _XWIZARD_PAGE_DATA *v69; // rcx
  PVOID *v70; // rcx
  __int128 v71; // xmm0
  __int64 v72; // [rsp+0h] [rbp-158h] BYREF
  int v73; // [rsp+50h] [rbp-108h]
  struct _XWIZARD_PAGE_DATA *v74; // [rsp+58h] [rbp-100h] BYREF
  struct CUnknown *v75; // [rsp+60h] [rbp-F8h] BYREF
  unsigned int v76; // [rsp+68h] [rbp-F0h] BYREF
  int v77; // [rsp+6Ch] [rbp-ECh]
  CPXWizardSemaphoreLock *v78; // [rsp+70h] [rbp-E8h] BYREF
  unsigned __int16 *v79; // [rsp+78h] [rbp-E0h] BYREF
  LPVOID v80; // [rsp+80h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-D0h]
  CTask *v82; // [rsp+90h] [rbp-C8h]
  struct CUnknown *v83; // [rsp+98h] [rbp-C0h] BYREF
  unsigned int *p_Data1; // [rsp+A0h] [rbp-B8h]
  __int64 v85; // [rsp+A8h] [rbp-B0h]
  LPVOID *v86; // [rsp+B0h] [rbp-A8h]
  const struct _GUID *v87; // [rsp+B8h] [rbp-A0h]
  struct _GUID v88; // [rsp+C0h] [rbp-98h] BYREF
  LPVOID *v89; // [rsp+D0h] [rbp-88h]
  void *v90; // [rsp+D8h] [rbp-80h]
  const struct _GUID *v91; // [rsp+E0h] [rbp-78h]
  struct _GUID *v92; // [rsp+E8h] [rbp-70h]
  CPXWizardSemaphoreLock **v93; // [rsp+F0h] [rbp-68h]
  _QWORD *v94; // [rsp+F8h] [rbp-60h]
  struct _GUID v95; // [rsp+100h] [rbp-58h] BYREF

  p_Data1 = a3;
  v87 = a2;
  v5 = this;
  v82 = this;
  v91 = a2;
  v74 = 0;
  if ( a2 && *((_DWORD *)this + 255) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids);
    SpecifiedWizardModule = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, unsigned int *))(**((_QWORD **)v5 + 37) + 104LL))(
                              *((_QWORD *)v5 + 37),
                              a2,
                              a3);
    if ( SpecifiedWizardModule )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v8 = 84;
        goto LABEL_264;
      }
    }
    return (unsigned int)SpecifiedWizardModule;
  }
  v88 = 0;
  v9 = 0;
  v75 = 0;
  v95 = 0;
  if ( a2 )
  {
    v10 = *(_QWORD *)&a2->Data1 - *((_QWORD *)this + 2);
    if ( *(_QWORD *)&a2->Data1 == *((_QWORD *)this + 2) )
      v10 = *(_QWORD *)a2->Data4 - *((_QWORD *)this + 3);
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, a2->Data1);
      v11 = a3;
      v12 = a2;
      return CTask::HrGetPreviousPageToRun(v5, v12, v11);
    }
    v88 = *a2;
    v9 = &v88;
    v75 = (struct CUnknown *)&v88;
  }
  SpecifiedWizardModule = 1;
  v77 = *((_DWORD *)this + 104);
  LODWORD(v79) = v77;
  v86 = (LPVOID *)((char *)this + 424);
  pv = (LPVOID)*((_QWORD *)this + 53);
  v73 = 0;
  v76 = 0;
  v14 = 0;
  v15 = 3;
  LODWORD(v78) = 3;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  do
  {
    if ( !v15 )
      goto LABEL_257;
    PageToParsingStack = CTask::HrAddNextPageToParsingStack(v5, v9, 0, 0);
    SpecifiedWizardModule = PageToParsingStack;
    if ( PageToParsingStack )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_62;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
        PageToParsingStack);
      goto LABEL_61;
    }
    v17 = *((_QWORD *)v5 + 32);
    if ( !v17 || v14 )
      goto LABEL_66;
    v95 = *(struct _GUID *)*(_QWORD *)(*((_QWORD *)v5 + 40) - 8LL);
    if ( (*((_BYTE *)v5 + 116) & 0x20) != 0
      || ((v18 = *((_QWORD *)v5 + 43), *((_QWORD *)v5 + 42) != v18) ? (v19 = *(_QWORD *)(v18 - 8) + 4LL) : (v19 = 0),
          v20 = (*(__int64 (__fastcall **)(__int64, __int64, struct _GUID *))(*(_QWORD *)v17 + 80LL))(v17, v19, &v95),
          (SpecifiedWizardModule = v20) == 0) )
    {
      v95 = *(struct _GUID *)*(_QWORD *)(*((_QWORD *)v5 + 40) - 8LL);
      ParentPage = CTask::HrGetParentPage(v5, &v95, &v74, v17);
      SpecifiedWizardModule = ParentPage;
      if ( ParentPage )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            87,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            ParentPage);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        SpecifiedWizardModule = 0;
        goto LABEL_48;
      }
      v22 = v74;
      if ( (*((_BYTE *)v74 + 48) & 0x20) == 0 )
      {
        v23 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)v74 + 4) + 80LL))(
                *((_QWORD *)v74 + 4),
                &v95);
        SpecifiedWizardModule = v23;
        if ( v23 )
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_43;
          WPP_SF_ddD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            86,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            *((unsigned int *)v22 + 1),
            v95.Data1,
            v23);
        }
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_43:
      v74 = 0;
      goto LABEL_48;
    }
    if ( v20 == 262912 )
    {
      v14 = 1;
      SpecifiedWizardModule = 1;
LABEL_32:
      v88 = v95;
      v75 = (struct CUnknown *)&v88;
LABEL_57:
      CTask::PopPageFromParsingStack(v5);
LABEL_61:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_62;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_ddD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
        *((unsigned int *)v5 + 4),
        v95.Data1,
        v20);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_48:
    v14 = 0;
    if ( SpecifiedWizardModule != 1 )
    {
      if ( !SpecifiedWizardModule )
      {
LABEL_62:
        v26 = v73;
        goto LABEL_63;
      }
      goto LABEL_57;
    }
    v24 = *(_QWORD **)(*((_QWORD *)v5 + 40) - 8LL);
    v25 = *(_QWORD *)&v95.Data1 - *v24;
    if ( *(_QWORD *)&v95.Data1 == *v24 )
      v25 = *(_QWORD *)v95.Data4 - v24[1];
    if ( v25 )
      goto LABEL_32;
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    {
      WPP_SF_d(v7[2], 89, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *(_QWORD *)&v95.Data1);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v26 = 1;
    v73 = 1;
    v76 = 1;
    SpecifiedWizardModule = 0;
LABEL_63:
    v15 = (_DWORD)v78 - 1;
    LODWORD(v78) = (_DWORD)v78 - 1;
    v9 = (const struct _GUID *)v75;
  }
  while ( SpecifiedWizardModule == 1 );
  if ( SpecifiedWizardModule )
  {
LABEL_257:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    {
      WPP_SF_d(v7[2], 91, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, (unsigned int)SpecifiedWizardModule);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( SpecifiedWizardModule == 1 )
    {
      SpecifiedWizardModule = 262657;
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
      {
        v8 = 92;
LABEL_264:
        WPP_SF_d(v7[2], v8, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, (unsigned int)SpecifiedWizardModule);
      }
    }
    return (unsigned int)SpecifiedWizardModule;
  }
  v73 = v26;
  v76 = v26;
LABEL_66:
  v94 = (_QWORD *)((char *)v5 + 320);
  v27 = *(struct _GUID **)(*((_QWORD *)v5 + 40) - 8LL);
  v92 = v27;
  v75 = (CTask *)((char *)v5 + 336);
  v28 = *((_QWORD *)v5 + 43);
  if ( *((_QWORD *)v5 + 42) == v28 )
    v85 = 0;
  else
    v85 = *(_QWORD *)(v28 - 8);
  if ( (*((_BYTE *)v5 + 112) & 0x40) != 0 )
  {
    *((_DWORD *)v5 + 24) = 0;
    *((_DWORD *)v5 + 25) = 0;
    *((_QWORD *)v5 + 13) = v27;
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v5 + 33) + 40LL))(*((_QWORD *)v5 + 33), 3);
  }
  if ( !CTask::FindProcessedPage(v5, v27) )
  {
LABEL_78:
    RecycledPage = CTask::HrGetRecycledPage(v5, v27, &v74, 0);
    SpecifiedWizardModule = RecycledPage;
    if ( RecycledPage >= 0 )
    {
      if ( RecycledPage != 1 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        {
          v31 = v74;
        }
        else
        {
          v31 = v74;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            98,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            *((unsigned int *)v74 + 1));
        }
        goto LABEL_103;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          96,
          &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
          (unsigned int)RecycledPage);
      SpecifiedWizardModule = 1;
    }
    v30 = (struct _XWIZARD_PAGE_DATA *)CoTaskMemAlloc(0xA8u);
    v31 = v30;
    v74 = v30;
    if ( !v30 )
    {
      SpecifiedWizardModule = -2147024882;
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_256;
      v33 = 97;
      goto LABEL_97;
    }
    memset_0(v30, 0, 0xA8u);
    *(_DWORD *)v31 = 168;
LABEL_103:
    v89 = v86;
    v90 = pv;
    v83 = v75;
    v80 = v27;
    p_Data1 = &v27->Data1;
    v93 = (CPXWizardSemaphoreLock **)((char *)v31 + 104);
    if ( *((_QWORD *)v31 + 13) )
    {
      if ( SpecifiedWizardModule >= 0 )
      {
LABEL_275:
        try
        {
          std::vector<_XWIZARD_PAGE_DATA *>::push_back(v75, &v74);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              101,
              &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
              *(unsigned int *)v80);
        }
        catch ( std::bad_alloc )
        {
          LODWORD(v79) = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_DD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              102,
              &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
              *((unsigned int *)v74 + 1),
              -2147024882);
          SpecifiedWizardModule = (int)v79;
          v5 = v82;
          goto LABEL_256;
        }
        Page = CTask::HrRecalculateLastPage(v5);
        SpecifiedWizardModule = Page;
        if ( Page < 0 )
        {
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_128;
          v43 = 103;
          goto LABEL_127;
        }
        v44 = v74;
        v45 = *(_OWORD *)v80;
        *(_OWORD *)((char *)v74 + 4) = *(_OWORD *)v80;
        *((_DWORD *)v44 + 12) = v27[3].Data1;
        v46 = v85;
        if ( v85 )
        {
          if ( *(int *)(v85 + 20) >= 2 )
          {
            if ( *(int *)(v85 + 20) > 2 )
              *(_OWORD *)((char *)v5 + 140) = v45;
            *(_OWORD *)((char *)v5 + 172) = *(_OWORD *)((char *)v44 + 4);
          }
          if ( *(_DWORD *)(v46 + 88) && !*(_DWORD *)(v46 + 64) )
            *(_OWORD *)((char *)v5 + 172) = *(_OWORD *)((char *)v44 + 4);
        }
        v47 = *(_QWORD *)((char *)v44 + 4) - *(_QWORD *)((char *)v5 + 124);
        if ( !v47 )
          v47 = *(_QWORD *)((char *)v44 + 12) - *(_QWORD *)((char *)v5 + 132);
        *((_DWORD *)v44 + 19) = v47 == 0;
        v48 = *(_QWORD *)((char *)v44 + 4) - *(_QWORD *)((char *)v5 + 140);
        if ( !v48 )
          v48 = *(_QWORD *)((char *)v44 + 12) - *(_QWORD *)((char *)v5 + 148);
        *((_DWORD *)v44 + 20) = v48 == 0;
        v49 = *(_QWORD *)((char *)v44 + 4) - *(_QWORD *)((char *)v5 + 156);
        if ( !v49 )
          v49 = *(_QWORD *)((char *)v44 + 12) - *(_QWORD *)((char *)v5 + 164);
        *((_DWORD *)v44 + 21) = v49 == 0;
        v50 = *(_QWORD *)((char *)v44 + 4) - *(_QWORD *)((char *)v5 + 172);
        if ( !v50 )
          v50 = *(_QWORD *)((char *)v44 + 12) - *(_QWORD *)((char *)v5 + 180);
        *((_DWORD *)v44 + 22) = v50 == 0;
        *((_DWORD *)v44 + 33) = *((_DWORD *)v5 + 96);
        *((_DWORD *)v44 + 34) = *((_DWORD *)v5 + 97);
        v75 = 0;
        SpecifiedWizardModule = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct CUnknown **))(**((_QWORD **)v5 + 31) + 152LL))(
                                  *((_QWORD *)v5 + 31),
                                  (__int64)v44 + 4,
                                  0,
                                  &v75);
        if ( SpecifiedWizardModule >= 0 )
        {
          v80 = 0;
          SpecifiedWizardModule = (*(__int64 (__fastcall **)(struct CUnknown *, __int64, LPVOID *))(*(_QWORD *)v75 + 24LL))(
                                    v75,
                                    1,
                                    &v80);
          *((_DWORD *)v44 + 23) = SpecifiedWizardModule == 0;
          CoTaskMemFree(v80);
          (*(void (__fastcall **)(struct CUnknown *))(*(_QWORD *)v75 + 16LL))(v75);
        }
        v51 = *(_QWORD *)v27[2].Data4;
        *((_QWORD *)v44 + 4) = v51;
        if ( v51 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids);
          v73 = 1;
        }
        if ( (*((_BYTE *)v44 + 48) & 0x20) != 0 )
        {
          v52 = *(_QWORD *)&v27[2].Data1;
          *((_QWORD *)v44 + 3) = v52;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
        }
        if ( SpecifiedWizardModule < 0 )
          goto LABEL_128;
        if ( !*((_QWORD *)v44 + 5) )
        {
          Page = CXWizardSource::HrCreateInstance(
                   v5,
                   v44,
                   (const struct _GUID *)((char *)v44 + 4),
                   (struct IXWizardSource **)v44 + 5);
          SpecifiedWizardModule = Page;
          if ( Page < 0 )
          {
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_128;
            v43 = 105;
LABEL_127:
            WPP_SF_d(v42[2], v43, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, (unsigned int)Page);
            goto LABEL_128;
          }
        }
        v80 = 0;
        v53 = *((_QWORD *)v5 + 39);
        v54 = (*((_QWORD *)v5 + 40) - v53) >> 3;
        if ( v54 > 2 && (v55 = *(char **)(v53 + 8 * (v54 - 2)), (v80 = v55) != 0) )
        {
          v56 = v55;
        }
        else
        {
          v56 = (char *)v5 + 16;
          if ( v5 == (CTask *)-16LL )
            goto LABEL_187;
        }
        LODWORD(v78) = 0;
        v79 = 0;
        SpecifiedWizardModule = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, CPXWizardSemaphoreLock **, unsigned __int16 **))(**((_QWORD **)v5 + 38) + 80LL))(
                                  *((_QWORD *)v5 + 38),
                                  v56,
                                  (__int64)v44 + 4,
                                  &v78,
                                  &v79);
        if ( SpecifiedWizardModule < 0 )
          goto LABEL_128;
        v77 |= (unsigned int)v78;
        if ( !v79 )
          goto LABEL_188;
        v57 = *((_QWORD *)v5 + 53);
        if ( v57 )
        {
          v58 = -1;
          do
            ++v58;
          while ( *(_WORD *)(v57 + 2 * v58) );
        }
        else
        {
          LODWORD(v58) = 0;
        }
        v59 = -1;
        do
          ++v59;
        while ( v79[v59] );
        v60 = (unsigned int)(v58 + v59 + 2);
        v61 = (unsigned __int16 *)CoTaskMemAlloc(2 * v60);
        v62 = v61;
        pv = v61;
        if ( v61 )
        {
          *v61 = 0;
          if ( *((_QWORD *)v5 + 53) )
          {
            StringCchCopyW(v61, (unsigned int)v60, *((const unsigned __int16 **)v5 + 53));
            StringCchCatW(v63, (unsigned int)v60, L" ");
            v62 = (unsigned __int16 *)pv;
          }
          StringCchCatW(v62, v60, v79);
        }
        else
        {
          SpecifiedWizardModule = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              106,
              &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
              2147942414LL);
        }
        CoTaskMemFree(v79);
LABEL_187:
        if ( SpecifiedWizardModule < 0 )
          goto LABEL_128;
LABEL_188:
        v74 = 0;
        v76 = *((_DWORD *)v5 + 55);
        *((_DWORD *)v44 + 35) = IsFactoryRegisteredWizardComponent((const struct _GUID *)((char *)v44 + 4));
        v64 = (CTask *)((char *)v5 + 408);
LABEL_189:
        v75 = v64;
        while ( !v73 )
        {
          v65 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID, _QWORD, int, LPVOID, _DWORD, _QWORD, struct _XWIZARD_PAGE_DATA **))(**((_QWORD **)v44 + 4) + 56LL))(
                  *((_QWORD *)v44 + 4),
                  (__int64)v5 + 16,
                  v80,
                  v76,
                  v77,
                  pv,
                  **(_DWORD **)v64,
                  *((_QWORD *)v44 + 5),
                  &v74);
          SpecifiedWizardModule = v65;
          if ( v65 != -2147467263 )
          {
            if ( v65 != 1 )
            {
              if ( v65 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_DD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    114,
                    &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
                    *((unsigned int *)v44 + 1),
                    v65);
                goto LABEL_128;
              }
              if ( v65 )
                goto LABEL_249;
              SpecifiedWizardModule = HrGetSpecifiedWizardModule(
                                        (char *)v44 + 4,
                                        (unsigned int)(*((_DWORD *)v44 + 35) != 0) + 1,
                                        (char *)v44 + 144);
              v69 = v74;
              if ( SpecifiedWizardModule >= 0 )
              {
                if ( v74 )
                {
                  _InterlockedAdd((volatile signed __int32 *)v5 + 256, 1u);
                  SpecifiedWizardModule = (*(__int64 (__fastcall **)(_QWORD, struct _XWIZARD_PAGE_DATA *, __int64, _QWORD, _DWORD))(**((_QWORD **)v5 + 36) + 80LL))(
                                            *((_QWORD *)v5 + 36),
                                            v74,
                                            (__int64)v44 + 152,
                                            *((_QWORD *)v5 + 55),
                                            *((_DWORD *)v5 + 30));
                  if ( SpecifiedWizardModule >= 0 )
                  {
                    if ( *((_QWORD *)v44 + 19) )
                    {
                      SpecifiedWizardModule = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v5 + 36)
                                                                                                + 104LL))(
                                                *((_QWORD *)v5 + 36),
                                                *((_QWORD *)v44 + 19),
                                                *((unsigned int *)v5 + 30));
                      if ( SpecifiedWizardModule >= 0 )
                        *((_DWORD *)v44 + 16) = 1;
                    }
                  }
                  _InterlockedDecrement((volatile signed __int32 *)v5 + 256);
LABEL_230:
                  v69 = v74;
                }
                else
                {
                  SpecifiedWizardModule = 262656;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    WPP_SF_DD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      115,
                      &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
                      *((unsigned int *)v44 + 1),
                      262656);
                    goto LABEL_230;
                  }
                }
              }
              if ( v69 != *((struct _XWIZARD_PAGE_DATA **)v44 + 19) && ((unsigned __int8)v69 & 3) == 0 )
                CoTaskMemFree(v69);
              if ( SpecifiedWizardModule >= 0 )
                goto LABEL_249;
LABEL_128:
              CTask::PopPageFromProcessedStack(v5, 0, 0x101u);
              CTask::PopPageFromParsingStack(v5);
              CTask::HrRecalculateLastPage(v5);
LABEL_129:
              if ( pv != *v86 )
                CoTaskMemFree(pv);
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v8 = 117;
                goto LABEL_264;
              }
              return (unsigned int)SpecifiedWizardModule;
            }
LABEL_239:
            v70 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_240;
          }
          v82 = v75;
          if ( (**(_BYTE **)v75 & 0x10) != 0 )
          {
            (*(void (__fastcall **)(_QWORD, unsigned int *, _QWORD))(**((_QWORD **)v5 + 36) + 152LL))(
              *((_QWORD *)v5 + 36),
              &v76,
              *((unsigned int *)v5 + 30));
            v64 = v82;
            v75 = v82;
            if ( *((_DWORD *)v5 + 55) != v76 )
              continue;
          }
          if ( *((_DWORD *)v44 + 35) )
            goto LABEL_209;
          v75 = 0;
          v66 = CWPage::CreateComponentInstance((const struct _GUID *)((char *)v44 + 4), 0, &v75);
          SpecifiedWizardModule = v66;
          if ( v66 >= 0 )
          {
            v83 = 0;
            v67 = (**(__int64 (__fastcall ***)(struct CUnknown *, GUID *, struct CUnknown **))v75)(
                    v75,
                    &IID_IXWizardPageEvent,
                    &v83);
            SpecifiedWizardModule = v67;
            if ( v67 >= 0 )
            {
              *((_DWORD *)v44 + 35) = 1;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  108,
                  &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
                  *((unsigned int *)v44 + 1));
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v44 + 4) + 16LL))(*((_QWORD *)v44 + 4));
              *((_QWORD *)v44 + 4) = v83;
              v76 = *((_DWORD *)v5 + 55);
              (*(void (__fastcall **)(struct CUnknown *))(*(_QWORD *)v75 + 16LL))(v75);
              v64 = v82;
              goto LABEL_189;
            }
            v68 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                109,
                &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
                (unsigned int)v67);
              v68 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v75 )
            {
              (*(void (__fastcall **)(struct CUnknown *, __int64))(*(_QWORD *)v75 + 24LL))(v75, 1);
              goto LABEL_209;
            }
            goto LABEL_210;
          }
          v68 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                110,
                &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
                (unsigned int)v66);
LABEL_209:
              v68 = (PVOID *)WPP_GLOBAL_Control;
            }
LABEL_210:
            if ( v68 != &WPP_GLOBAL_Control && (*((_BYTE *)v68 + 28) & 8) != 0 )
              WPP_SF_ddD(
                v68[2],
                111,
                &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
                *((unsigned int *)v44 + 1),
                *((_DWORD *)v5 + 55),
                SpecifiedWizardModule);
          }
          *((_DWORD *)v44 + 18) = 1;
LABEL_248:
          SpecifiedWizardModule = 262656;
LABEL_249:
          p_Data1[14] = 1;
          if ( v87 )
          {
            v71 = *(_OWORD *)((char *)v44 + 4);
            if ( v85 )
            {
              *(_OWORD *)(v85 + 116) = v71;
            }
            else
            {
              *(_OWORD *)((char *)v5 + 204) = v71;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids);
            }
          }
          CTask::HrRefreshProcessedStackPageProperties(v5);
          goto LABEL_129;
        }
        v70 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids);
          goto LABEL_239;
        }
LABEL_240:
        if ( v74 )
        {
          if ( v70 == &WPP_GLOBAL_Control )
          {
LABEL_247:
            *((_DWORD *)v44 + 18) = 1;
            *(_DWORD *)(*(_QWORD *)(*v94 - 8LL) + 52LL) = 1;
            *((_DWORD *)v44 + 24) = 1;
            goto LABEL_248;
          }
          if ( (*((_BYTE *)v70 + 28) & 8) != 0 )
          {
            WPP_SF_(v70[2], 112, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids);
            v70 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        if ( v70 != &WPP_GLOBAL_Control && (*((_BYTE *)v70 + 28) & 8) != 0 )
          WPP_SF_DD(v70[2], 113, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *((unsigned int *)v44 + 1), 1);
        goto LABEL_247;
      }
      goto LABEL_256;
    }
    v78 = 0;
    try
    {
      v35 = (CPXWizardSemaphoreLock *)operator new(0x28u);
      *(_QWORD *)&v88.Data1 = v35;
      if ( v35 )
        v39 = CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(v35, v36, v27, v38);
      else
        v39 = 0;
      v78 = v39;
    }
    catch ( ... )
    {
      v36 = (unsigned __int16 *)&v72;
      v31 = v74;
      v73 = v76;
      v39 = v78;
      v75 = v83;
      v86 = v89;
      pv = v90;
      v5 = v82;
      v87 = v91;
      v77 = (int)v79;
      v27 = v92;
    }
    if ( v39 )
    {
      *v93 = v39;
      v40 = CPXWizardSemaphoreLock::AddRef(v39, (int *)v36, v37);
      SpecifiedWizardModule = v40;
      if ( v40 >= 0 )
      {
        *((_DWORD *)v31 + 28) = 1;
        goto LABEL_275;
      }
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v33 = 99;
        v34 = (unsigned int)v40;
        goto LABEL_98;
      }
LABEL_256:
      CTask::FreePageDataElement(v5, &v74, 0, 0);
      CTask::PopPageFromParsingStack(v5);
      return (unsigned int)SpecifiedWizardModule;
    }
    SpecifiedWizardModule = -2147024882;
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_256;
    v33 = 100;
LABEL_97:
    v34 = 2147942414LL;
LABEL_98:
    WPP_SF_d(v32[2], v33, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v34);
    goto LABEL_256;
  }
  if ( (v27[3].Data1 & 0xF) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v27->Data1);
    v11 = p_Data1;
    v12 = v27;
    return CTask::HrGetPreviousPageToRun(v5, v12, v11);
  }
  if ( (v27[3].Data1 & 0xF) != 1 )
  {
    if ( (v27[3].Data1 & 0xF) == 2
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v27->Data1);
    }
    goto LABEL_78;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
      v27->Data1,
      -2147221002);
  CTask::PopPageFromParsingStack(v5);
  return 2147746294LL;
}

```

## disassembly

```asm
0x180021d04  push    rbx
0x180021d06  push    rsi
0x180021d07  push    rdi
0x180021d08  push    r12
0x180021d0a  push    r13
0x180021d0c  push    r14
0x180021d0e  push    r15
0x180021d10  sub     rsp, 120h
0x180021d17  mov     rax, cs:__security_cookie
0x180021d1e  xor     rax, rsp
0x180021d21  mov     [rsp+158h+var_48], rax
0x180021d29  mov     rdi, r8
0x180021d2c  mov     [rsp+158h+var_B8], r8
0x180021d34  mov     r14, rdx
0x180021d37  mov     [rsp+158h+var_A0], rdx
0x180021d3f  mov     rsi, rcx
0x180021d42  mov     [rsp+158h+var_C8], rcx
0x180021d4a  mov     [rsp+158h+var_78], rdx
0x180021d52  xor     ebx, ebx
0x180021d54  mov     [rsp+158h+var_100], rbx
0x180021d59  test    rdx, rdx
0x180021d5c  jz      loc_180021DE9
0x180021d62  cmp     [rcx+3FCh], ebx
0x180021d68  jz      short loc_180021DE9
0x180021d6a  lea     r15, WPP_GLOBAL_Control
0x180021d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d78  cmp     rcx, r15
0x180021d7b  jz      short loc_180021D9B
0x180021d7d  test    byte ptr [rcx+1Ch], 10h
0x180021d81  jz      short loc_180021D9B
0x180021d83  lea     edx, [rbx+53h]
0x180021d86  lea     r12, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180021d8d  mov     r8, r12
0x180021d90  mov     rcx, [rcx+10h]
0x180021d94  call    WPP_SF_
0x180021d99  jmp     short loc_180021DA2
0x180021d9b  lea     r12, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180021da2  mov     rcx, [rsi+128h]
0x180021da9  mov     rax, [rcx]
0x180021dac  mov     r8, rdi
0x180021daf  mov     rdx, r14
0x180021db2  mov     rax, [rax+68h]
0x180021db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dbb  mov     edi, eax
0x180021dbd  test    eax, eax
0x180021dbf  jz      loc_180022EF0
0x180021dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021dcc  cmp     rcx, r15
0x180021dcf  jz      loc_180022EF0
0x180021dd5  test    byte ptr [rcx+1Ch], 4
0x180021dd9  jz      loc_180022EF0
0x180021ddf  mov     edx, 54h ; 'T'
0x180021de4  jmp     loc_180022EE1
0x180021de9  xorps   xmm0, xmm0
0x180021dec  movups  [rsp+158h+var_98], xmm0
0x180021df4  mov     rax, rbx
0x180021df7  mov     [rsp+158h+var_F8], rbx
0x180021dfc  xorps   xmm1, xmm1
0x180021dff  movups  xmmword ptr [rsp+158h+var_58.Data1], xmm1
0x180021e07  test    r14, r14
0x180021e0a  jz      short loc_180021E7D
0x180021e0c  mov     rax, [rdx]
0x180021e0f  sub     rax, [rcx+10h]
0x180021e13  jnz     short loc_180021E1D
0x180021e15  mov     rax, [rdx+8]
0x180021e19  sub     rax, [rcx+18h]
0x180021e1d  test    rax, rax
0x180021e20  jnz     short loc_180021E64
0x180021e22  lea     r15, WPP_GLOBAL_Control
0x180021e29  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e30  cmp     rcx, r15
0x180021e33  jz      short loc_180021E51
0x180021e35  test    byte ptr [rcx+1Ch], 8
0x180021e39  jz      short loc_180021E51
0x180021e3b  lea     edx, [rax+55h]
0x180021e3e  mov     r9d, [r14]
0x180021e41  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180021e48  mov     rcx, [rcx+10h]
0x180021e4c  call    WPP_SF_d
0x180021e51  mov     r8, rdi; unsigned int *
0x180021e54  mov     rdx, r14; struct _GUID *
0x180021e57  mov     rcx, rsi; this
0x180021e5a  call    ?HrGetPreviousPageToRun@CTask@@AEAAJPEBU_GUID@@PEAK@Z; CTask::HrGetPreviousPageToRun(_GUID const *,ulong *)
0x180021e5f  jmp     loc_180022EF2
0x180021e64  movups  xmm0, xmmword ptr [rdx]
0x180021e67  movdqu  [rsp+158h+var_98], xmm0
0x180021e70  lea     rax, [rsp+158h+var_98]
0x180021e78  mov     [rsp+158h+var_F8], rax
0x180021e7d  mov     r14d, 1
0x180021e83  mov     edi, r14d
0x180021e86  mov     ecx, [rcx+1A0h]
0x180021e8c  mov     [rsp+158h+var_EC], ecx
0x180021e90  mov     dword ptr [rsp+158h+var_E0], ecx
0x180021e94  lea     rcx, [rsi+1A8h]
0x180021e9b  mov     [rsp+158h+var_A8], rcx
0x180021ea3  mov     rcx, [rcx]
0x180021ea6  mov     [rsp+158h+pv], rcx
0x180021eae  mov     [rsp+158h+var_108], ebx
0x180021eb2  mov     [rsp+158h+var_F0], ebx
0x180021eb6  mov     r13d, ebx
0x180021eb9  lea     edx, [r14+2]
0x180021ebd  mov     dword ptr [rsp+158h+var_E8], edx
0x180021ec1  lea     r15, WPP_GLOBAL_Control
0x180021ec8  lea     r12, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180021ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ed6  test    edx, edx
0x180021ed8  jz      loc_180022EA1
0x180021ede  xor     r9d, r9d; int
0x180021ee1  xor     r8d, r8d; int
0x180021ee4  mov     rdx, rax; struct _GUID *
0x180021ee7  mov     rcx, rsi; this
0x180021eea  call    ?HrAddNextPageToParsingStack@CTask@@AEAAJPEBU_GUID@@HH@Z; CTask::HrAddNextPageToParsingStack(_GUID const *,int,int)
0x180021eef  mov     edi, eax
0x180021ef1  test    eax, eax
0x180021ef3  jnz     loc_18002212E
0x180021ef9  mov     r9, [rsi+100h]; int
0x180021f00  test    r9, r9
0x180021f03  jz      loc_18002218A
0x180021f09  test    r13d, r13d
0x180021f0c  jnz     loc_18002218A
0x180021f12  mov     rax, [rsi+140h]
0x180021f19  mov     rcx, [rax-8]
0x180021f1d  movups  xmm0, xmmword ptr [rcx]
0x180021f20  movdqu  xmmword ptr [rsp+158h+var_58.Data1], xmm0
0x180021f29  test    byte ptr [rsi+74h], 20h
0x180021f2d  jnz     loc_180021FE7
0x180021f33  mov     rax, [r9]
0x180021f36  mov     rdx, [rsi+158h]
0x180021f3d  cmp     [rsi+150h], rdx
0x180021f44  jnz     short loc_180021F4B
0x180021f46  mov     rdx, rbx
0x180021f49  jmp     short loc_180021F53
0x180021f4b  mov     rdx, [rdx-8]
0x180021f4f  add     rdx, 4
0x180021f53  lea     r8, [rsp+158h+var_58]
0x180021f5b  mov     rcx, r9
0x180021f5e  mov     rax, [rax+50h]
0x180021f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f67  mov     edi, eax
0x180021f69  test    eax, eax
0x180021f6b  jz      short loc_180021FE7
0x180021f6d  cmp     eax, 40300h
0x180021f72  jnz     short loc_180021F9D
0x180021f74  mov     r13d, r14d
0x180021f77  mov     edi, r14d
0x180021f7a  movaps  xmm0, xmmword ptr [rsp+158h+var_58.Data1]
0x180021f82  movdqa  [rsp+158h+var_98], xmm0
0x180021f8b  lea     rax, [rsp+158h+var_98]
0x180021f93  mov     [rsp+158h+var_F8], rax
0x180021f98  jmp     loc_180022124
0x180021f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fa4  cmp     rcx, r15
0x180021fa7  jz      loc_1800220B6
0x180021fad  test    byte ptr [rcx+1Ch], 8
0x180021fb1  jz      loc_1800220B6
0x180021fb7  mov     edx, 58h ; 'X'
0x180021fbc  mov     dword ptr [rsp+158h+var_130], eax
0x180021fc0  mov     eax, [rsp+158h+var_58.Data1]
0x180021fc7  mov     dword ptr [rsp+158h+var_138], eax
0x180021fcb  mov     r9d, [rsi+10h]
0x180021fcf  mov     r8, r12
0x180021fd2  mov     rcx, [rcx+10h]
0x180021fd6  call    WPP_SF_ddD
0x180021fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fe2  jmp     loc_1800220B6
0x180021fe7  mov     rax, [rsi+140h]
0x180021fee  mov     rcx, [rax-8]
0x180021ff2  movups  xmm0, xmmword ptr [rcx]
0x180021ff5  movdqu  xmmword ptr [rsp+158h+var_58.Data1], xmm0
0x180021ffe  lea     r8, [rsp+158h+var_100]; struct _XWIZARD_PAGE_DATA **
0x180022003  lea     rdx, [rsp+158h+var_58]; struct _GUID *
0x18002200b  mov     rcx, rsi; this
0x18002200e  call    ?HrGetParentPage@CTask@@AEAAJPEAU_GUID@@PEAPEAU_XWIZARD_PAGE_DATA@@H@Z; CTask::HrGetParentPage(_GUID *,_XWIZARD_PAGE_DATA * *,int)
0x180022013  mov     edi, eax
0x180022015  test    eax, eax
0x180022017  jnz     short loc_180022087
0x180022019  mov     r13, [rsp+158h+var_100]
0x18002201e  test    byte ptr [r13+30h], 20h
0x180022023  jnz     short loc_180022079
0x180022025  mov     rcx, [r13+20h]
0x180022029  mov     rax, [rcx]
0x18002202c  lea     rdx, [rsp+158h+var_58]
0x180022034  mov     rax, [rax+50h]
0x180022038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002203d  mov     edi, eax
0x18002203f  test    eax, eax
0x180022041  jz      short loc_180022079
0x180022043  mov     rcx, cs:WPP_GLOBAL_Control
0x18002204a  cmp     rcx, r15
0x18002204d  jz      short loc_180022080
0x18002204f  test    byte ptr [rcx+1Ch], 8
0x180022053  jz      short loc_180022080
0x180022055  mov     edx, 56h ; 'V'
0x18002205a  mov     dword ptr [rsp+158h+var_130], eax
0x18002205e  mov     eax, [rsp+158h+var_58.Data1]
0x180022065  mov     dword ptr [rsp+158h+var_138], eax
0x180022069  mov     r9d, [r13+4]
0x18002206d  mov     r8, r12
0x180022070  mov     rcx, [rcx+10h]
0x180022074  call    WPP_SF_ddD
0x180022079  mov     rcx, cs:WPP_GLOBAL_Control
0x180022080  mov     [rsp+158h+var_100], rbx
0x180022085  jmp     short loc_1800220B6
0x180022087  mov     rcx, cs:WPP_GLOBAL_Control
0x18002208e  cmp     rcx, r15
0x180022091  jz      short loc_1800220B4
0x180022093  test    byte ptr [rcx+1Ch], 10h
0x180022097  jz      short loc_1800220B4
0x180022099  mov     edx, 57h ; 'W'
0x18002209e  mov     r9d, eax
0x1800220a1  mov     r8, r12
0x1800220a4  mov     rcx, [rcx+10h]
0x1800220a8  call    WPP_SF_d
0x1800220ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220b4  mov     edi, ebx
0x1800220b6  mov     r13d, ebx
0x1800220b9  cmp     edi, r14d
0x1800220bc  jnz     short loc_180022120
0x1800220be  mov     rax, [rsi+140h]
0x1800220c5  mov     rdx, [rax-8]
0x1800220c9  mov     r9, qword ptr [rsp+158h+var_58.Data1]
0x1800220d1  mov     rax, r9
0x1800220d4  sub     rax, [rdx]
0x1800220d7  jnz     short loc_1800220E5
0x1800220d9  mov     rax, qword ptr [rsp+158h+var_58.Data4]
0x1800220e1  sub     rax, [rdx+8]
0x1800220e5  test    rax, rax
0x1800220e8  jnz     loc_180021F7A
0x1800220ee  cmp     rcx, r15
0x1800220f1  jz      short loc_18002210F
0x1800220f3  test    byte ptr [rcx+1Ch], 8
0x1800220f7  jz      short loc_18002210F
0x1800220f9  lea     edx, [rax+59h]
0x1800220fc  mov     r8, r12
0x1800220ff  mov     rcx, [rcx+10h]
0x180022103  call    WPP_SF_d
0x180022108  mov     rcx, cs:WPP_GLOBAL_Control
0x18002210f  mov     r8d, r14d
0x180022112  mov     [rsp+158h+var_108], r14d
0x180022117  mov     [rsp+158h+var_F0], r14d
0x18002211c  mov     edi, ebx
0x18002211e  jmp     short loc_180022160
0x180022120  test    edi, edi
0x180022122  jz      short loc_18002215B
0x180022124  mov     rcx, rsi; this
0x180022127  call    ?PopPageFromParsingStack@CTask@@AEAAXXZ; CTask::PopPageFromParsingStack(void)
0x18002212c  jmp     short loc_180022154
0x18002212e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022135  cmp     rcx, r15
0x180022138  jz      short loc_18002215B
0x18002213a  test    byte ptr [rcx+1Ch], 10h
0x18002213e  jz      short loc_18002215B
0x180022140  mov     edx, 5Ah ; 'Z'
0x180022145  mov     r9d, eax
0x180022148  mov     r8, r12
0x18002214b  mov     rcx, [rcx+10h]
0x18002214f  call    WPP_SF_d
0x180022154  mov     rcx, cs:WPP_GLOBAL_Control
0x18002215b  mov     r8d, [rsp+158h+var_108]
0x180022160  mov     edx, dword ptr [rsp+158h+var_E8]
0x180022164  dec     edx
0x180022166  mov     dword ptr [rsp+158h+var_E8], edx
0x18002216a  cmp     edi, r14d
0x18002216d  mov     rax, [rsp+158h+var_F8]
0x180022172  jz      loc_180021ED6
0x180022178  test    edi, edi
0x18002217a  jnz     loc_180022EA1
0x180022180  mov     [rsp+158h+var_108], r8d
0x180022185  mov     [rsp+158h+var_F0], r8d
0x18002218a  lea     rax, [rsi+140h]
0x180022191  mov     [rsp+158h+var_60], rax
0x180022199  mov     rax, [rax]
0x18002219c  mov     r13, [rax-8]
0x1800221a0  mov     [rsp+158h+var_70], r13
0x1800221a8  lea     rcx, [rsi+150h]
0x1800221af  mov     [rsp+158h+var_F8], rcx
0x1800221b4  mov     rax, [rcx+8]
0x1800221b8  cmp     [rcx], rax
0x1800221bb  jnz     short loc_1800221C7
0x1800221bd  mov     [rsp+158h+var_B0], rbx
0x1800221c5  jmp     short loc_1800221D3
0x1800221c7  mov     rax, [rax-8]
0x1800221cb  mov     [rsp+158h+var_B0], rax
0x1800221d3  test    byte ptr [rsi+70h], 40h
0x1800221d7  jz      short loc_180022200
0x1800221d9  lea     r8, [rsi+28h]
0x1800221dd  mov     [r8+38h], ebx
0x1800221e1  mov     [rsi+64h], ebx
0x1800221e4  mov     [rsi+68h], r13
0x1800221e8  mov     rcx, [rsi+108h]
0x1800221ef  mov     rax, [rcx]
0x1800221f2  mov     edx, 3
0x1800221f7  mov     rax, [rax+28h]
0x1800221fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022200  mov     rdx, r13; struct _GUID *
0x180022203  mov     rcx, rsi; this
0x180022206  call    ?FindProcessedPage@CTask@@AEAAPEAU_XWIZARD_PAGE_DATA@@PEAU_GUID@@@Z; CTask::FindProcessedPage(_GUID *)
0x18002220b  test    rax, rax
0x18002220e  jz      short loc_18002224E
0x180022210  mov     eax, [r13+30h]
  ... truncated ...
```
