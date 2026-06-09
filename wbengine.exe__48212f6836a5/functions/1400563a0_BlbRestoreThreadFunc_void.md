# BlbRestoreThreadFunc(void *)

- ea: `0x1400563a0`
- end: `0x1400572ba`
- name: `?BlbRestoreThreadFunc@@YAKPEAX@Z`
- size: `3866`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `41`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callees

- `0x140006ca8`
- `0x14000aee8`
- `0x14000b0bc`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140010a08`
- `0x140013008`
- `0x140014200`
- `0x140014260`
- `0x14002cbe8`
- `0x14003c480`
- `0x14003cb70`
- `0x1400563a0`
- `0x1400578e0`
- `0x140057de0`
- `0x140057e70`
- `0x14005914c`
- `0x140059750`
- `0x14005a62c`
- `0x14005b4d8`
- `0x14005b564`
- `0x14005b848`
- `0x14005b8b0`
- `0x14005b944`
- `0x14005baa4`
- `0x140088ba4`
- `0x14008b58c`
- `0x14008fed0`
- `0x1400be63c`
- `0x1400d740c`
- `0x1400d9234`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f4188`
- `0x140102cd8`
- `0x14011cf98`
- `0x14011d420`
- `0x140128d2c`
- `0x1401290a8`
- `0x14012a330`
- `0x140137010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1400569e5`
- `KERNEL32!Sleep` at `0x1400569e5`
- `KERNEL32!LeaveCriticalSection` at `0x140056a10`
- `KERNEL32!LeaveCriticalSection` at `0x140056ef6`
- `KERNEL32!LeaveCriticalSection` at `0x140056a10`
- `KERNEL32!LeaveCriticalSection` at `0x140056ef6`
- `KERNEL32!EnterCriticalSection` at `0x1400569ff`
- `KERNEL32!EnterCriticalSection` at `0x140056ed2`
- `KERNEL32!EnterCriticalSection` at `0x1400569ff`
- `KERNEL32!EnterCriticalSection` at `0x140056ed2`
- `ole32!CoTaskMemFree` at `0x140056c16`
- `ole32!CoTaskMemFree` at `0x140056c32`
- `ole32!CoTaskMemFree` at `0x140056c47`
- `ole32!CoTaskMemFree` at `0x140056c59`
- `ole32!CoTaskMemFree` at `0x140056e76`
- `ole32!CoTaskMemFree` at `0x140056ea6`
- `ole32!CoTaskMemFree` at `0x140056c16`
- `ole32!CoTaskMemFree` at `0x140056c32`
- `ole32!CoTaskMemFree` at `0x140056c47`
- `ole32!CoTaskMemFree` at `0x140056c59`
- `ole32!CoTaskMemFree` at `0x140056e76`
- `ole32!CoTaskMemFree` at `0x140056ea6`
- `RPCRT4!UuidToStringW` at `0x1400567b9`
- `RPCRT4!UuidToStringW` at `0x1400569a1`
- `RPCRT4!UuidToStringW` at `0x1400567b9`
- `RPCRT4!UuidToStringW` at `0x1400569a1`
- `RPCRT4!RpcStringFreeW` at `0x1400567a3`
- `RPCRT4!RpcStringFreeW` at `0x14005698b`
- `RPCRT4!RpcStringFreeW` at `0x140056c69`
- `RPCRT4!RpcStringFreeW` at `0x140056c79`
- `RPCRT4!RpcStringFreeW` at `0x1400567a3`
- `RPCRT4!RpcStringFreeW` at `0x14005698b`
- `RPCRT4!RpcStringFreeW` at `0x140056c69`
- `RPCRT4!RpcStringFreeW` at `0x140056c79`

## string_xrefs

- `0x140056d2e`: `base\stor\blb\engine\service\restore.cpp`
- `0x140056fd9`: `base\stor\blb\engine\service\restore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BlbRestoreThreadFunc(char *Parameter)
{
  CBlbVolumeRestoreContext *v2; // r12
  PVOID *v3; // r13
  int RestoreVolumeNames; // edi
  unsigned __int16 **v5; // r13
  __int64 i; // rbx
  unsigned __int16 **v7; // rdx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _DWORD *v10; // r12
  PVOID *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // r13
  __int64 v14; // rsi
  __int64 v15; // rdi
  unsigned __int16 *v16; // r14
  __int64 v17; // r14
  __int64 v18; // rax
  __int64 v19; // r8
  int v20; // ebx
  __m128i v21; // xmm6
  int v22; // eax
  __int64 j; // rsi
  __int64 v24; // rdx
  PVOID v25; // rcx
  unsigned __int16 **v26; // r12
  __int64 v27; // rax
  CBlbVolumeRestoreContext *v28; // r13
  unsigned __int16 *v29; // rbx
  unsigned int v30; // edi
  unsigned int v31; // ebx
  const wchar_t *v32; // r9
  int v33; // ebx
  unsigned int v34; // esi
  int v35; // r9d
  void *v37; // [rsp+28h] [rbp-E0h]
  unsigned __int16 **v38; // [rsp+78h] [rbp-90h]
  unsigned __int16 **v39; // [rsp+80h] [rbp-88h] BYREF
  RPC_WSTR String; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int16 *v41; // [rsp+90h] [rbp-78h] BYREF
  RPC_WSTR StringUuid; // [rsp+98h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int16 **v44; // [rsp+A8h] [rbp-60h]
  GUID v45; // [rsp+B0h] [rbp-58h]
  __int64 v46; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-40h] BYREF
  struct _GUID v48; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v49; // [rsp+E8h] [rbp-20h] BYREF
  int v50; // [rsp+F8h] [rbp-10h]
  __int64 v51; // [rsp+100h] [rbp-8h]
  int v52; // [rsp+108h] [rbp+0h]
  unsigned int v53; // [rsp+178h] [rbp+70h] BYREF
  int v54; // [rsp+180h] [rbp+78h] BYREF
  unsigned int v55; // [rsp+188h] [rbp+80h] BYREF
  CBlbVolumeRestoreContext *v56; // [rsp+190h] [rbp+88h]

  v54 = 0;
  v2 = 0;
  v56 = 0;
  v41 = 0;
  pv = 0;
  v45 = GUID_NULL;
  String = 0;
  StringUuid = 0;
  v46 = 0;
  v47 = 0;
  v53 = 0;
  v38 = 0;
  v39 = 0;
  v55 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 4u )
      WPP_SF_DDDDDDDDDDD(
        (unsigned int)v3[2],
        128,
        (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
        *((_DWORD *)Parameter + 52),
        *((_WORD *)Parameter + 106),
        *((_WORD *)Parameter + 107),
        Parameter[216],
        Parameter[217],
        Parameter[218],
        Parameter[219],
        Parameter[220],
        Parameter[221],
        Parameter[222],
        Parameter[223]);
  }
  v54 = 0;
  RestoreVolumeNames = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)Parameter + 72LL))(Parameter, &v54);
  if ( RestoreVolumeNames < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
    }
    goto LABEL_113;
  }
  RestoreVolumeNames = CBlbRestoreAsync::GetRestoreVolumeNames((CBlbRestoreAsync *)Parameter, &v39, &v55);
  if ( RestoreVolumeNames < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
    }
    v5 = v39;
    goto LABEL_114;
  }
  v48 = (struct _GUID)*((_OWORD *)Parameter + 13);
  v5 = v39;
  v38 = v39;
  if ( PublishRestoreStartedEvent(&v48, v39, *((_DWORD *)Parameter + 83), *(struct _FILETIME *)(Parameter + 356)) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  CBlbRestoreAsync::SetState(Parameter, 3, 0);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v7 = (unsigned __int16 **)(Parameter + 264);
    v39 = (unsigned __int16 **)(Parameter + 264);
    v44 = (unsigned __int16 **)(Parameter + 264);
    if ( (unsigned int)i >= *((_DWORD *)Parameter + 83) )
      break;
    RestoreVolumeNames = CBlbVolumeRestoreContext::FinalizeContext((CBlbVolumeRestoreContext *)&(*v7)[96 * i]);
    if ( RestoreVolumeNames < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 132;
        goto LABEL_198;
      }
      goto LABEL_114;
    }
  }
  v10 = Parameter + 280;
  *(_QWORD *)&v48.Data1 = *(_QWORD *)v45.Data4;
LABEL_34:
  v11 = (PVOID *)WPP_GLOBAL_Control;
  while ( 1 )
  {
    v12 = (unsigned int)*v10;
    if ( (unsigned int)v12 >= *((_DWORD *)Parameter + 71) )
    {
      if ( *((_DWORD *)Parameter + 84) )
      {
        CBlbRestoreAsync::SetState(Parameter, 4, 0);
        RestoreVolumeNames = CBlbImpersonationHelper::ImpersonateCaller((CBlbImpersonationHelper *)(Parameter + 24), 0);
        if ( RestoreVolumeNames >= 0 )
        {
          RestoreVolumeNames = CBlbRestoreAsync::InitializeExclusions((unsigned __int16 **)Parameter);
          if ( RestoreVolumeNames >= 0 )
          {
            CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(Parameter + 24));
            CExclusionHelper::Init((CExclusionHelper *)&v49, *((struct IExclusionHandler **)Parameter + 47));
            CExclusionHelper::DeleteExcludes((CExclusionHelper *)&v49);
            CBlbAsync::LockedSet((CBlbAsync *)(Parameter + 8), (unsigned int *)Parameter + 68, 0);
            v26 = v44;
            while ( 1 )
            {
              v27 = *((unsigned int *)Parameter + 68);
              if ( (unsigned int)v27 >= *((_DWORD *)Parameter + 83) )
                break;
              v28 = (CBlbVolumeRestoreContext *)&(*v26)[96 * v27];
              v56 = v28;
              if ( (unsigned int)(*((_DWORD *)v28 + 5) - 8) > 1 )
              {
                if ( Parameter[352] || Parameter[353] )
                {
                  if ( v41 )
                  {
                    CoTaskMemFree(v41);
                    v41 = 0;
                  }
                  RestoreVolumeNames = CBlbVolumeRestoreContext::GetRestoreTargetPath(v28, &v41);
                  if ( RestoreVolumeNames < 0 )
                    goto LABEL_170;
                  if ( pv )
                  {
                    CoTaskMemFree(pv);
                    pv = 0;
                  }
                  v29 = v41;
                  RestoreVolumeNames = BlbutilRemoveTrailingBackslash(v41, (unsigned __int16 **)&pv);
                  if ( RestoreVolumeNames < 0 )
                    goto LABEL_171;
                  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 72));
                  CBlbVolumeRestoreContext::SetState(v28, 4);
                  CBlbRestoreAsync::UpdateBytes((CBlbRestoreAsync *)Parameter, 0, 0);
                  LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 72));
                  v30 = BlbimgDeleteOmittedFiles((LPCWSTR)pv, Parameter, (__int64)&v46, (__int64)&v47, (__int64)&v53);
                  CBlbRestoreAsync::UpdateBytes((CBlbRestoreAsync *)Parameter, v47, v46);
                  if ( v30 )
                  {
                    if ( v30 == 1 )
                    {
                      if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)Parameter + 1) + 16LL))(Parameter + 8) )
                        BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0xF51u, "pContext->IsAborted()");
                      RestoreVolumeNames = -2139618969;
LABEL_170:
                      v29 = v41;
LABEL_171:
                      CBlbVolumeRestoreContext::SetAborted(v28, RestoreVolumeNames, v54);
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v32 = L"??";
                        if ( v29 )
                          LODWORD(v32) = (_DWORD)v29;
                        WPP_SF_Sd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          145,
                          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
                          (_DWORD)v32,
                          RestoreVolumeNames);
                      }
                      v2 = v28;
                      goto LABEL_113;
                    }
                    v31 = v53;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_SLd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        144,
                        (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
                        (_DWORD)v41,
                        v30,
                        v53);
                    }
                    RestoreVolumeNames = BlbTranslateBlbimgError(v30, v31, &v54);
                    if ( RestoreVolumeNames < 0 )
                      goto LABEL_170;
                  }
                }
                v54 = 0;
                CBlbVolumeRestoreContext::SetState(v28, 9);
              }
              CBlbAsync::LockedIncrement((CBlbAsync *)(Parameter + 8), (unsigned int *)Parameter + 68);
            }
            v54 = 0;
            RestoreVolumeNames = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)Parameter + 80LL))(
                                   Parameter,
                                   &v54);
            if ( RestoreVolumeNames < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v24 = 146;
              v25 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
              goto LABEL_140;
            }
          }
        }
      }
      else
      {
        RestoreVolumeNames = -2139619299;
        if ( *((_DWORD *)Parameter + 69) != 8 )
          RestoreVolumeNames = -2139619230;
      }
      goto LABEL_112;
    }
    v13 = *((_QWORD *)Parameter + 36) + 108 * v12;
    v56 = 0;
    v14 = 0;
    while ( 1 )
    {
      if ( (unsigned int)v14 >= *((_DWORD *)Parameter + 83) )
        goto LABEL_47;
      v15 = 96 * v14;
      v16 = *v7;
      if ( BlbutilIsVolumeMatch(
             (struct _GUID *)(v13 + 44),
             *(_DWORD *)(v13 + 60),
             (struct _GUID *)&(*v7)[96 * v14 + 30],
             *(_DWORD *)&(*v7)[96 * v14 + 38]) )
      {
        break;
      }
      v14 = (unsigned int)(v14 + 1);
      v7 = v39;
    }
    if ( *(int *)&v16[v15 + 12] >= 0 )
    {
      CBlbAsync::LockedSet((CBlbAsync *)(Parameter + 8), (unsigned int *)Parameter + 68, v14);
      v17 = (__int64)&(*v44)[96 * *((unsigned int *)Parameter + 68)];
      v56 = (CBlbVolumeRestoreContext *)v17;
      v39 = v44;
    }
    else
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 3u )
      {
        WPP_SF_d(v11[2], 133, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( LOBYTE((*v44)[v15 + 76]) )
      {
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 2u )
          WPP_SF_Sd(
            (unsigned int)v11[2],
            134,
            (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
            *(_QWORD *)&(*v44)[v15 + 68],
            *(_DWORD *)&(*v44)[v15 + 12]);
        RestoreVolumeNames = *(_DWORD *)(192 * v14 + *((_QWORD *)Parameter + 33) + 24);
        goto LABEL_112;
      }
      v39 = v44;
LABEL_47:
      v17 = (__int64)v56;
    }
    if ( String )
    {
      RpcStringFreeW(&String);
      String = 0;
    }
    if ( UuidToStringW((const UUID *)(v13 + 16), &String) )
      goto LABEL_135;
    if ( !v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
          (_DWORD)String,
          *v10);
      }
      goto LABEL_56;
    }
    if ( *(int *)(v17 + 24) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
      }
LABEL_56:
      CBlbAsync::LockedIncrement((CBlbAsync *)(Parameter + 8), (unsigned int *)Parameter + 70);
LABEL_57:
      v7 = v39;
      goto LABEL_34;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
        (_DWORD)String,
        *v10);
    }
    if ( !*v10 )
      break;
    v18 = *(_QWORD *)(v13 + 64) - *(_QWORD *)&v45.Data1;
    if ( !v18 )
      v18 = *(_QWORD *)(v13 + 72) - *(_QWORD *)&v48.Data1;
    if ( v18 )
      break;
LABEL_91:
    v22 = CBlbRestoreAsync::RestoreBag((CBlbRestoreAsync *)Parameter);
    RestoreVolumeNames = v22;
    if ( v22 >= 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      v7 = v39;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          143,
          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
          (_DWORD)String,
          *((_DWORD *)Parameter + 70) - 1);
        goto LABEL_57;
      }
    }
    else
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SLd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          140,
          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
          (_DWORD)String,
          *((_DWORD *)Parameter + 70),
          v22);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( RestoreVolumeNames == -2139619299 || RestoreVolumeNames == -2139618969 )
      {
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 2u )
        {
          v24 = 141;
          v25 = v11[2];
LABEL_140:
          WPP_SF_d(v25, v24, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
        }
        goto LABEL_112;
      }
      if ( *(_BYTE *)(v17 + 152) )
        goto LABEL_112;
      v7 = v39;
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
      {
        WPP_SF_(v11[2], 142, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
        goto LABEL_57;
      }
    }
  }
  if ( (Parameter[328] & 2) == 0 )
  {
    RestoreVolumeNames = CBlbImpersonationHelper::ImpersonateCaller((CBlbImpersonationHelper *)(Parameter + 24), 0);
    if ( RestoreVolumeNames < 0 )
      goto LABEL_112;
    RestoreVolumeNames = BlbCheckMediaIdInTarget(*((unsigned __int16 **)Parameter + 32), (struct _GUID *)(v13 + 64));
    if ( RestoreVolumeNames < 0 )
      goto LABEL_112;
    CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(Parameter + 24));
    goto LABEL_91;
  }
  CBlbAsync::SetResult((CBlbAsync *)(Parameter + 8), -2139619278, 0, 0);
  LOBYTE(v19) = 1;
  CBlbRestoreAsync::SetState(Parameter, 6, v19);
  if ( (int)PublishWaitingForShiningMediaEvent() < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  if ( UuidToStringW((const UUID *)(v13 + 64), &StringUuid) )
  {
LABEL_135:
    RestoreVolumeNames = -2147024882;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids, StringUuid);
    }
    while ( 1 )
    {
      Sleep(0x3E8u);
      if ( !CBlbAsync::CheckPoint((CBlbAsync *)(Parameter + 8)) )
        break;
      EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 72));
      v20 = *((_DWORD *)Parameter + 69);
      LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 72));
      if ( v20 == 7 )
      {
        v21 = *(__m128i *)(v13 + 64);
        CBlbAsync::SetResult((CBlbAsync *)(Parameter + 8), 0, 0, 1u);
        CBlbAsync::SetResult((CBlbAsync *)(Parameter + 8), 0, 0, 0);
        *(_QWORD *)&v48.Data1 = _mm_srli_si128(v21, 8).m128i_u64[0];
        *(_QWORD *)&v45.Data1 = v21.m128i_i64[0];
        goto LABEL_91;
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)Parameter + 1) + 16LL))(Parameter + 8) )
      BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0xEA2u, "pContext->IsAborted()");
    RestoreVolumeNames = -2139618969;
  }
LABEL_112:
  v2 = v56;
LABEL_113:
  v5 = v38;
  while ( 1 )
  {
LABEL_114:
    CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(Parameter + 24));
    if ( v5 )
    {
      for ( j = 0; (unsigned int)j < v55; j = (unsigned int)(j + 1) )
      {
        CoTaskMemFree(v5[j]);
        v5[j] = 0;
      }
    }
    CoTaskMemFree(v5);
    v5 = 0;
    if ( pv )
      CoTaskMemFree(pv);
    if ( v41 )
      CoTaskMemFree(v41);
    if ( String )
      RpcStringFreeW(&String);
    if ( StringUuid )
      RpcStringFreeW(&StringUuid);
    if ( RestoreVolumeNames >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
      }
      CBlbRestoreAsync::SetState(Parameter, 9, 0);
    }
    else
    {
      if ( !CBlbAsync::CheckPoint((CBlbAsync *)(Parameter + 8)) )
      {
        RestoreVolumeNames = -2139618969;
        CBlbVolumeRestoreContext::SetResult(v2, -2139618969, 0);
        CBlbAsync::SetResult((CBlbAsync *)(Parameter + 8), -2139618969, 0, 0);
      }
      CBlbRestoreAsync::SetAborted((CBlbRestoreAsync *)Parameter, RestoreVolumeNames, v54);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
      }
    }
    if ( (int)CBlbRestoreAsync::PublishVolumeRestoreStopEvent((CBlbRestoreAsync *)Parameter, RestoreVolumeNames) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
    }
    v33 = *((_DWORD *)Parameter + 4);
    v34 = *((_DWORD *)Parameter + 5);
    LOBYTE(v53) = 0;
    RestoreVolumeNames = BlbutilIsClientSKU((unsigned __int8 *)&v53);
    if ( RestoreVolumeNames >= 0 )
      break;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 150;
LABEL_198:
      WPP_SF_d(v8[2], v9, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
    }
  }
  if ( v33 < 0 && !(_BYTE)v53 )
  {
    if ( IsWERRequiredForError(v33) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
        v35 = 0;
      }
      LODWORD(v37) = v35;
      BlbGenerateErrorReport(*((unsigned int *)Parameter + 81), 2, (unsigned int)v33, v34, v37, v35, v35, v35);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
    }
  }
  CBlbAsync::Done((CBlbAsync *)(Parameter + 8));
  (*(void (__fastcall **)(char *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  CExclusionHelper::~CExclusionHelper((CExclusionHelper *)&v49);
  return 0;
}

```

## disassembly

```asm
0x1400563a0  mov     rax, rsp
0x1400563a3  push    rbp
0x1400563a4  push    rbx
0x1400563a5  push    rsi
0x1400563a6  push    rdi
0x1400563a7  push    r12
0x1400563a9  push    r13
0x1400563ab  push    r14
0x1400563ad  push    r15
0x1400563af  lea     rbp, [rax-68h]
0x1400563b3  sub     rsp, 128h
0x1400563ba  movaps  xmmword ptr [rax-58h], xmm6
0x1400563be  mov     r15, rcx
0x1400563c1  mov     [rbp+60h+arg_8], 0
0x1400563c8  xor     r12d, r12d
0x1400563cb  mov     [rbp+60h+arg_18], r12
0x1400563d2  mov     [rbp+60h+var_D8], r12
0x1400563d6  mov     [rbp+60h+pv], r12
0x1400563da  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400563e1  movdqu  [rbp+60h+var_B8], xmm0
0x1400563e6  mov     [rbp+60h+String], r12
0x1400563ea  mov     [rbp+60h+StringUuid], r12
0x1400563ee  mov     [rbp+60h+var_A8], r12
0x1400563f2  mov     [rbp+60h+var_A0], r12
0x1400563f6  mov     [rbp+60h+arg_0], r12d
0x1400563fa  xor     eax, eax
0x1400563fc  mov     [rsp+160h+var_F0], rax
0x140056401  mov     [rsp+160h+var_E8], rax
0x140056406  mov     [rbp+60h+arg_10], eax
0x14005640c  xorps   xmm0, xmm0
0x14005640f  movdqu  [rbp+60h+var_80], xmm0
0x140056414  mov     [rbp+60h+var_70], eax
0x140056417  mov     [rbp+60h+var_68], rax
0x14005641b  mov     [rbp+60h+var_60], eax
0x14005641e  lea     rsi, WPP_GLOBAL_Control
0x140056425  lea     r14, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005642c  mov     r13, cs:WPP_GLOBAL_Control
0x140056433  cmp     r13, rsi
0x140056436  jz      loc_140056522
0x14005643c  test    byte ptr [r13+1Ch], 1
0x140056441  jz      short loc_140056460
0x140056443  cmp     byte ptr [r13+19h], 4
0x140056448  jb      short loc_140056460
0x14005644a  lea     edx, [rax+7Fh]
0x14005644d  mov     r8, r14
0x140056450  mov     rcx, [r13+10h]
0x140056454  call    WPP_SF_
0x140056459  mov     r13, cs:WPP_GLOBAL_Control
0x140056460  cmp     r13, rsi
0x140056463  jz      loc_140056522
0x140056469  test    byte ptr [r13+1Ch], 1
0x14005646e  jz      loc_140056522
0x140056474  cmp     byte ptr [r13+19h], 4
0x140056479  jb      loc_140056522
0x14005647f  movzx   eax, byte ptr [r15+0DFh]
0x140056487  movzx   ecx, byte ptr [r15+0DEh]
0x14005648f  movzx   r8d, byte ptr [r15+0DDh]
0x140056497  movzx   r9d, byte ptr [r15+0DCh]
0x14005649f  movzx   r10d, byte ptr [r15+0DBh]
0x1400564a7  movzx   r11d, byte ptr [r15+0DAh]
0x1400564af  movzx   ebx, byte ptr [r15+0D9h]
0x1400564b7  movzx   edi, byte ptr [r15+0D8h]
0x1400564bf  movzx   esi, word ptr [r15+0D6h]
0x1400564c7  movzx   r14d, word ptr [r15+0D4h]
0x1400564cf  mov     edx, 80h
0x1400564d4  mov     dword ptr [rsp+160h+var_F8], eax
0x1400564d8  mov     [rsp+160h+var_100], ecx
0x1400564dc  mov     [rsp+160h+var_108], r8d
0x1400564e1  mov     [rsp+160h+var_110], r9d
0x1400564e6  mov     [rsp+160h+var_118], r10d
0x1400564eb  mov     [rsp+160h+var_120], r11d
0x1400564f0  mov     dword ptr [rsp+160h+var_128], ebx
0x1400564f4  mov     dword ptr [rsp+160h+var_130], edi
0x1400564f8  mov     dword ptr [rsp+160h+var_138], esi
0x1400564fc  mov     dword ptr [rsp+160h+var_140], r14d
0x140056501  mov     r9d, [r15+0D0h]
0x140056508  lea     r14, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005650f  mov     r8, r14
0x140056512  mov     rcx, [r13+10h]
0x140056516  call    WPP_SF_DDDDDDDDDDD
0x14005651b  lea     rsi, WPP_GLOBAL_Control
0x140056522  mov     [rbp+60h+arg_8], 0
0x140056529  mov     rax, [r15]
0x14005652c  lea     rdx, [rbp+60h+arg_8]
0x140056530  mov     rcx, r15
0x140056533  mov     rax, [rax+48h]
0x140056537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005653c  mov     edi, eax
0x14005653e  test    eax, eax
0x140056540  jns     short loc_14005657F
0x140056542  mov     rcx, cs:WPP_GLOBAL_Control
0x140056549  cmp     rcx, rsi
0x14005654c  jz      loc_140056BF4
0x140056552  test    byte ptr [rcx+1Ch], 1
0x140056556  jz      loc_140056BF4
0x14005655c  cmp     byte ptr [rcx+19h], 2
0x140056560  jb      loc_140056BF4
0x140056566  mov     edx, 81h
0x14005656b  mov     r9d, eax
0x14005656e  mov     r8, r14
0x140056571  mov     rcx, [rcx+10h]
0x140056575  call    WPP_SF_d
0x14005657a  jmp     loc_140056BF4
0x14005657f  lea     r8, [rbp+60h+arg_10]; unsigned int *
0x140056586  lea     rdx, [rsp+160h+var_E8]; unsigned __int16 ***
0x14005658b  mov     rcx, r15; this
0x14005658e  call    ?GetRestoreVolumeNames@CBlbRestoreAsync@@QEAAJAEAPEAPEAGPEAK@Z; CBlbRestoreAsync::GetRestoreVolumeNames(ushort * * &,ulong *)
0x140056593  mov     edi, eax
0x140056595  test    eax, eax
0x140056597  jns     short loc_1400565CF
0x140056599  mov     rcx, cs:WPP_GLOBAL_Control
0x1400565a0  cmp     rcx, rsi
0x1400565a3  jz      short loc_1400565C5
0x1400565a5  test    byte ptr [rcx+1Ch], 1
0x1400565a9  jz      short loc_1400565C5
0x1400565ab  cmp     byte ptr [rcx+19h], 2
0x1400565af  jb      short loc_1400565C5
0x1400565b1  mov     edx, 82h
0x1400565b6  mov     r9d, eax
0x1400565b9  mov     r8, r14
0x1400565bc  mov     rcx, [rcx+10h]
0x1400565c0  call    WPP_SF_d
0x1400565c5  mov     r13, [rsp+160h+var_E8]
0x1400565ca  jmp     loc_140056BF9
0x1400565cf  movups  xmm0, xmmword ptr [r15+0D0h]
0x1400565d7  movdqu  xmmword ptr [rbp+60h+var_90.Data1], xmm0
0x1400565dc  mov     r9, [r15+164h]; struct _FILETIME
0x1400565e3  mov     r8d, [r15+14Ch]; unsigned int
0x1400565ea  mov     r13, [rsp+160h+var_E8]
0x1400565ef  mov     [rsp+160h+var_F0], r13
0x1400565f4  mov     rdx, r13; unsigned __int16 **
0x1400565f7  lea     rcx, [rbp+60h+var_90]; struct _GUID
0x1400565fb  call    ?PublishRestoreStartedEvent@@YAJU_GUID@@PEAPEAGIU_FILETIME@@@Z; PublishRestoreStartedEvent(_GUID,ushort * *,uint,_FILETIME)
0x140056600  test    eax, eax
0x140056602  jns     short loc_140056630
0x140056604  mov     rcx, cs:WPP_GLOBAL_Control
0x14005660b  cmp     rcx, rsi
0x14005660e  jz      short loc_140056630
0x140056610  test    byte ptr [rcx+1Ch], 1
0x140056614  jz      short loc_140056630
0x140056616  cmp     byte ptr [rcx+19h], 2
0x14005661a  jb      short loc_140056630
0x14005661c  mov     edx, 83h
0x140056621  mov     r9d, eax
0x140056624  mov     r8, r14
0x140056627  mov     rcx, [rcx+10h]
0x14005662b  call    WPP_SF_d
0x140056630  xor     r8d, r8d
0x140056633  lea     edx, [r8+3]
0x140056637  mov     rcx, r15
0x14005663a  call    ?SetState@CBlbRestoreAsync@@IEAAXW4_BLB_RESTORE_STATE@@E@Z; CBlbRestoreAsync::SetState(_BLB_RESTORE_STATE,uchar)
0x14005663f  xor     ebx, ebx
0x140056641  lea     rdx, [r15+108h]
0x140056648  mov     [rsp+160h+var_E8], rdx
0x14005664d  mov     [rbp+60h+var_C0], rdx
0x140056651  cmp     ebx, [r15+14Ch]
0x140056658  jnb     short loc_1400566A8
0x14005665a  lea     rcx, [rbx+rbx*2]
0x14005665e  shl     rcx, 6
0x140056662  add     rcx, [rdx]; this
0x140056665  call    ?FinalizeContext@CBlbVolumeRestoreContext@@AEAAJXZ; CBlbVolumeRestoreContext::FinalizeContext(void)
0x14005666a  mov     edi, eax
0x14005666c  test    eax, eax
0x14005666e  js      short loc_140056674
0x140056670  inc     ebx
0x140056672  jmp     short loc_140056641
0x140056674  mov     rcx, cs:WPP_GLOBAL_Control
0x14005667b  cmp     rcx, rsi
0x14005667e  jz      loc_140056BF9
0x140056684  test    byte ptr [rcx+1Ch], 1
0x140056688  jz      loc_140056BF9
0x14005668e  cmp     byte ptr [rcx+19h], 2
0x140056692  jb      loc_140056BF9
0x140056698  mov     edx, 84h
0x14005669d  mov     r9d, eax
0x1400566a0  mov     r8, r14
0x1400566a3  jmp     loc_140057180
0x1400566a8  lea     r12, [r15+118h]
0x1400566af  mov     r14, qword ptr [rbp+60h+var_B8+8]
0x1400566b3  mov     qword ptr [rbp+60h+var_90.Data1], r14
0x1400566b7  mov     r14, qword ptr [rbp+60h+var_B8]
0x1400566bb  mov     qword ptr [rbp+60h+var_B8], r14
0x1400566bf  mov     rbx, cs:WPP_GLOBAL_Control
0x1400566c6  mov     eax, [r12]
0x1400566ca  cmp     eax, [r15+11Ch]
0x1400566d1  jnb     loc_140056D88
0x1400566d7  imul    r13, rax, 6Ch ; 'l'
0x1400566db  add     r13, [r15+120h]
0x1400566e2  mov     [rbp+60h+arg_18], 0
0x1400566ed  xor     esi, esi
0x1400566ef  cmp     esi, [r15+14Ch]
0x1400566f6  jnb     loc_140056791
0x1400566fc  lea     rdi, [rsi+rsi*2]
0x140056700  shl     rdi, 6
0x140056704  mov     r14, [rdx]
0x140056707  lea     r8, [r14+3Ch]
0x14005670b  add     r8, rdi; struct _GUID *
0x14005670e  lea     rcx, [r13+2Ch]; struct _GUID *
0x140056712  mov     r9d, [rdi+r14+4Ch]; unsigned int
0x140056717  mov     edx, [r13+3Ch]; unsigned int
0x14005671b  call    ?BlbutilIsVolumeMatch@@YAEPEAU_GUID@@K0K@Z; BlbutilIsVolumeMatch(_GUID *,ulong,_GUID *,ulong)
0x140056720  test    al, al
0x140056722  jnz     short loc_14005672D
0x140056724  inc     esi
0x140056726  mov     rdx, [rsp+160h+var_E8]
0x14005672b  jmp     short loc_1400566EF
0x14005672d  mov     r9d, [rdi+r14+18h]
0x140056732  test    r9d, r9d
0x140056735  jns     loc_140056826
0x14005673b  lea     rax, WPP_GLOBAL_Control
0x140056742  cmp     rbx, rax
0x140056745  jz      short loc_140056776
0x140056747  test    byte ptr [rbx+1Ch], 1
0x14005674b  jz      short loc_140056776
0x14005674d  cmp     byte ptr [rbx+19h], 3
0x140056751  jb      short loc_140056776
0x140056753  mov     edx, 85h
0x140056758  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005675f  mov     rcx, [rbx+10h]
0x140056763  call    WPP_SF_d
0x140056768  mov     rbx, cs:WPP_GLOBAL_Control
0x14005676f  lea     rax, WPP_GLOBAL_Control
0x140056776  mov     rcx, [rbp+60h+var_C0]
0x14005677a  mov     r9, [rcx]
0x14005677d  cmp     byte ptr [rdi+r9+98h], 0
0x140056786  jnz     loc_140056BA3
0x14005678c  mov     [rsp+160h+var_E8], rcx
0x140056791  mov     r14, [rbp+60h+arg_18]
0x140056798  cmp     [rbp+60h+String], 0
0x14005679d  jz      short loc_1400567B1
0x14005679f  lea     rcx, [rbp+60h+String]; String
0x1400567a3  call    cs:__imp_RpcStringFreeW
0x1400567a9  mov     [rbp+60h+String], 0
0x1400567b1  lea     rcx, [r13+10h]; Uuid
0x1400567b5  lea     rdx, [rbp+60h+String]; StringUuid
0x1400567b9  call    cs:__imp_UuidToStringW
0x1400567bf  test    eax, eax
0x1400567c1  jnz     loc_140056D44
0x1400567c7  test    r14, r14
0x1400567ca  jnz     loc_14005685E
0x1400567d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400567d7  lea     r13, WPP_GLOBAL_Control
0x1400567de  cmp     rcx, r13
0x1400567e1  jz      short loc_140056810
0x1400567e3  test    byte ptr [rcx+1Ch], 1
0x1400567e7  jz      short loc_140056810
0x1400567e9  cmp     byte ptr [rcx+19h], 4
0x1400567ed  jb      short loc_140056810
0x1400567ef  mov     edx, 87h
0x1400567f4  mov     eax, [r12]
0x1400567f8  mov     dword ptr [rsp+160h+var_140], eax
0x1400567fc  mov     r9, [rbp+60h+String]
0x140056800  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x140056807  mov     rcx, [rcx+10h]
0x14005680b  call    WPP_SF_Sd
0x140056810  lea     rcx, [r15+8]; this
0x140056814  mov     rdx, r12; unsigned int *
0x140056817  call    ?LockedIncrement@CBlbAsync@@QEAAXAEAK@Z; CBlbAsync::LockedIncrement(ulong &)
0x14005681c  mov     rdx, [rsp+160h+var_E8]
0x140056821  jmp     loc_1400566BF
0x140056826  lea     rbx, [r15+110h]
0x14005682d  lea     rcx, [r15+8]; this
0x140056831  mov     r8d, esi; unsigned int
0x140056834  mov     rdx, rbx; unsigned int *
0x140056837  call    ?LockedSet@CBlbAsync@@QEAAXAEAKK@Z; CBlbAsync::LockedSet(ulong &,ulong)
0x14005683c  mov     eax, [rbx]
0x14005683e  lea     r14, [rax+rax*2]
0x140056842  shl     r14, 6
0x140056846  mov     rcx, [rbp+60h+var_C0]
0x14005684a  add     r14, [rcx]
0x14005684d  mov     [rbp+60h+arg_18], r14
0x140056854  mov     [rsp+160h+var_E8], rcx
0x140056859  jmp     loc_140056798
0x14005685e  mov     r9d, [r14+18h]
0x140056862  test    r9d, r9d
0x140056865  jns     short loc_1400568A0
0x140056867  mov     rcx, cs:WPP_GLOBAL_Control
0x14005686e  lea     r13, WPP_GLOBAL_Control
0x140056875  cmp     rcx, r13
0x140056878  jz      short loc_140056810
0x14005687a  test    byte ptr [rcx+1Ch], 1
0x14005687e  jz      short loc_140056810
0x140056880  cmp     byte ptr [rcx+19h], 3
0x140056884  jb      short loc_140056810
0x140056886  mov     edx, 88h
0x14005688b  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x140056892  mov     rcx, [rcx+10h]
0x140056896  call    WPP_SF_d
0x14005689b  jmp     loc_140056810
0x1400568a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400568a7  lea     rsi, WPP_GLOBAL_Control
0x1400568ae  cmp     rcx, rsi
0x1400568b1  jz      short loc_1400568E0
0x1400568b3  test    byte ptr [rcx+1Ch], 1
0x1400568b7  jz      short loc_1400568E0
0x1400568b9  cmp     byte ptr [rcx+19h], 4
0x1400568bd  jb      short loc_1400568E0
0x1400568bf  mov     edx, 89h
0x1400568c4  mov     eax, [r12]
0x1400568c8  mov     dword ptr [rsp+160h+var_140], eax
  ... truncated ...
```
