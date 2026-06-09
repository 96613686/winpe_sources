# CDlpTransportBits::HandleJobError(IDlpTask *,IBackgroundCopyJob *,IBackgroundCopyError *,BG_JOB_STATE,int,long *,ushort * *)

- ea: `0x180061f64`
- end: `0x180063093`
- name: `?HandleJobError@CDlpTransportBits@@AEAAJPEAVIDlpTask@@PEAUIBackgroundCopyJob@@PEAUIBackgroundCopyError@@W4BG_JOB_STATE@@HPEAJPEAPEAG@Z`
- size: `4399`
- prototype: `__int64 __usercall@<rax>(CDlpTransportBits *__hidden this@<rcx>, struct IDlpTask *@<rdx>, struct IBackgroundCopyJob *@<r8>, struct IBackgroundCopyError *@<r9>, BG_JOB_STATE, int, int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800670e4`
- `0x180067614`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001cd24`
- `0x18001fd60`
- `0x18005ab94`
- `0x18005ad48`
- `0x180061f64`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180062415`
- `OLEAUT32!__imp_SysFreeString` at `0x18006242e`
- `OLEAUT32!__imp_SysFreeString` at `0x180062445`
- `OLEAUT32!__imp_SysFreeString` at `0x180062456`
- `OLEAUT32!__imp_SysFreeString` at `0x1800629fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180062a38`
- `OLEAUT32!__imp_SysFreeString` at `0x180062ac0`
- `OLEAUT32!__imp_SysFreeString` at `0x180062415`
- `OLEAUT32!__imp_SysFreeString` at `0x18006242e`
- `OLEAUT32!__imp_SysFreeString` at `0x180062445`
- `OLEAUT32!__imp_SysFreeString` at `0x180062456`
- `OLEAUT32!__imp_SysFreeString` at `0x1800629fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180062a38`
- `OLEAUT32!__imp_SysFreeString` at `0x180062ac0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800623c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800623ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800623c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800623ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800623d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800623fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800623d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800623fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062e3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062e3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062e65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062e65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006246e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006249c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800624b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006246e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006249c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800624b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180062a71`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180062a84`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180062d48`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180062a71`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180062a84`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180062d48`

## string_xrefs

- `0x180062818`: `Bits Error: Unable to obtain IBackgroundCopyFile2 interface, hr = [0x%X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CDlpTransportBits::HandleJobError(
        CDlpTransportBits *this,
        struct IDlpTask *a2,
        struct IBackgroundCopyJob *a3,
        struct IBackgroundCopyError *a4,
        BG_JOB_STATE a5,
        int a6,
        int *a7,
        unsigned __int16 **a8)
{
  struct IDlpTask *v9; // r12
  int v11; // r15d
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rdi
  OLECHAR *v13; // rsi
  int BitsJobErrorContextString; // r14d
  char *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  char *v19; // rdi
  char *v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  char *v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // eax
  unsigned __int16 *v31; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v33; // rbx
  HANDLE v34; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  unsigned __int64 v38; // rax
  __int64 v39; // r9
  char *v40; // rsi
  __int64 v41; // rax
  const wchar_t *v42; // r12
  unsigned int v43; // ebx
  unsigned __int16 *v44; // rdi
  __int64 v45; // rax
  const wchar_t *v46; // r9
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  LPVOID v50; // rbx
  LPCWSTR v51; // rdi
  __int64 v52; // rax
  unsigned int v53; // ebx
  BSTR v54; // rdi
  __int64 v55; // rax
  __int64 v56; // rcx
  int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rcx
  int v60; // eax
  int v61; // eax
  char *v62; // rcx
  bool v63; // zf
  __int64 (__fastcall *v64)(char *); // rax
  BSTR v65; // rbx
  __int64 v66; // rax
  BSTR v67; // rbx
  __int64 v68; // rax
  __int64 v69; // rax
  unsigned __int16 **v70; // rdi
  void *v71; // rbx
  int StringCch; // eax
  __int64 v73; // [rsp+20h] [rbp-E0h]
  int v74; // [rsp+20h] [rbp-E0h]
  int v75; // [rsp+20h] [rbp-E0h]
  __int64 v76; // [rsp+28h] [rbp-D8h]
  int v77; // [rsp+28h] [rbp-D8h]
  int v78; // [rsp+28h] [rbp-D8h]
  __int64 (__fastcall ***v79)(_QWORD, _QWORD, _QWORD); // [rsp+40h] [rbp-C0h]
  OLECHAR *v80; // [rsp+48h] [rbp-B8h]
  unsigned int v81; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v82; // [rsp+54h] [rbp-ACh] BYREF
  __int64 (__fastcall ***v83)(_QWORD, _QWORD, _QWORD); // [rsp+58h] [rbp-A8h] BYREF
  BSTR v84; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v85; // [rsp+68h] [rbp-98h] BYREF
  BSTR v86; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  LPVOID Src; // [rsp+80h] [rbp-80h] BYREF
  __int64 v89; // [rsp+88h] [rbp-78h] BYREF
  BG_ERROR_CONTEXT v90; // [rsp+90h] [rbp-70h] BYREF
  int v91; // [rsp+94h] [rbp-6Ch] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpString2; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v94; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v95; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v96; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v97; // [rsp+C0h] [rbp-40h] BYREF
  int *v98; // [rsp+C8h] [rbp-38h]
  __int128 v99; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v100; // [rsp+E0h] [rbp-20h] BYREF
  struct IDlpTask *v101; // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall ***v102)(_QWORD, _QWORD, _QWORD); // [rsp+F8h] [rbp-8h]
  unsigned __int16 **v103; // [rsp+100h] [rbp+0h]
  int v104; // [rsp+118h] [rbp+18h]
  __int128 v105; // [rsp+128h] [rbp+28h] BYREF
  __int64 v106; // [rsp+138h] [rbp+38h]

  v9 = a2;
  v101 = a2;
  v98 = a7;
  v103 = a8;
  v11 = 0;
  v91 = 0;
  v81 = 0;
  v85 = 0;
  v82 = 0;
  v105 = 0;
  v106 = 0;
  v95 = 0;
  v89 = 0;
  v83 = 0;
  v12 = 0;
  v79 = 0;
  v102 = 0;
  v94 = 0;
  Src = 0;
  lpString2 = 0;
  pv = 0;
  v84 = 0;
  v13 = 0;
  v80 = 0;
  v86 = 0;
  bstrString = 0;
  v97 = 0;
  v96 = 0;
  v100 = 0;
  v99 = 0;
  v90 = BG_ERROR_CONTEXT_NONE;
  if ( !a3 )
  {
    BitsJobErrorContextString = -2147024809;
    v15 = (char *)this + 168;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
    {
LABEL_8:
      v12 = 0;
      goto LABEL_46;
    }
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))((char *)this + 168);
    v17 = 0;
    if ( !v16 )
    {
LABEL_7:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
      goto LABEL_8;
    }
    v77 = -2147024809;
    v74 = 1914;
LABEL_5:
    v18 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v16,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpTransportBits::HandleJobError",
            v74,
            v77);
    v17 = (unsigned int)v18;
    if ( v18 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
    goto LABEL_7;
  }
  if ( !a4 )
  {
    BitsJobErrorContextString = -2147024809;
    v19 = (char *)this + 168;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_8;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v19 + 16LL))((char *)this + 168);
    v17 = 0;
    if ( !v16 )
      goto LABEL_7;
    v77 = -2147024809;
    v74 = 1915;
    goto LABEL_5;
  }
  if ( !a7 )
  {
    BitsJobErrorContextString = -2147024809;
    v20 = (char *)this + 168;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_8;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v20 + 16LL))((char *)this + 168);
    v17 = 0;
    if ( !v16 )
      goto LABEL_7;
    v77 = -2147024809;
    v74 = 1916;
    goto LABEL_5;
  }
  BitsJobErrorContextString = ((__int64 (__fastcall *)(struct IBackgroundCopyError *, BG_ERROR_CONTEXT *, unsigned int *))a4->lpVtbl->GetError)(
                                a4,
                                &v90,
                                &v81);
  if ( BitsJobErrorContextString < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_46;
    v21 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v22 = 0;
    if ( !v21 )
      goto LABEL_23;
    v78 = BitsJobErrorContextString;
    v75 = 1920;
    goto LABEL_21;
  }
  ((void (__fastcall *)(struct IBackgroundCopyError *, __int64, LPVOID *))a4->lpVtbl->GetErrorDescription)(
    a4,
    1033,
    &v94);
  ((void (__fastcall *)(struct IBackgroundCopyError *, __int64, LPVOID *))a4->lpVtbl->GetErrorDescription)(
    a4,
    1024,
    &Src);
  v24 = ((__int64 (__fastcall *)(struct IBackgroundCopyError *, __int64 *))a4->lpVtbl->GetFile)(a4, &v95);
  BitsJobErrorContextString = v24;
  if ( v24 == -2145386492 || v24 >= 0 )
  {
    if ( a5 == BG_JOB_STATE_TRANSIENT_ERROR )
    {
      BitsJobErrorContextString = CDword::Increment((CDlpTransportBits *)((char *)this + 520), &v82);
      v25 = (char *)this + 168;
      v26 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
      if ( BitsJobErrorContextString < 0 )
      {
        if ( !v26 )
          goto LABEL_8;
        v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v25 + 16LL))((char *)this + 168);
        v17 = 0;
        if ( !v16 )
          goto LABEL_7;
        v77 = BitsJobErrorContextString;
        v74 = 1941;
        goto LABEL_5;
      }
      if ( v26 )
      {
        v27 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v25 + 16LL))((char *)this + 168);
        CDlpLogT<CEmptyType>::DlpLogFormat(v27, 1u, (__int64)L"Bits Error: Transient Error [%d]", v82);
      }
      if ( v95 )
      {
        BitsJobErrorContextString = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v95 + 40LL))(v95, &v105);
        if ( BitsJobErrorContextString < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v25 + 16LL))((char *)this + 168) )
          {
LABEL_44:
            v12 = v79;
LABEL_45:
            v13 = v80;
            goto LABEL_46;
          }
          v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v25 + 16LL))((char *)this + 168);
          v29 = 0;
          if ( !v28 )
          {
LABEL_43:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v29);
            goto LABEL_44;
          }
          LODWORD(v76) = BitsJobErrorContextString;
          LODWORD(v73) = 1948;
LABEL_41:
          v30 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v28,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpTransportBits::HandleJobError",
                  v73,
                  v76);
          v29 = (unsigned int)v30;
          if ( v30 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v30);
          goto LABEL_43;
        }
        v36 = *((_QWORD *)&v105 + 1);
        v37 = v105;
      }
      else
      {
        v37 = -1;
        v105 = 0xFFFFFFFFFFFFFFFFuLL;
        v36 = 0;
      }
      v38 = v81 + 2147024894;
      if ( ((unsigned int)v38 <= 0x3E && (v39 = 0x4008000000000003LL, _bittest64(&v39, v38))
         || v81 == -2147023570
         || v81 == -2147024829
         || v81 == -2145844748
         || v81 == -2147012889)
        && !v36
        && v37 == -1 )
      {
        v11 = 1;
      }
      else if ( v9 )
      {
        LODWORD(v100) = 1;
        DWORD1(v100) = v81;
        *((_QWORD *)&v100 + 1) = Src;
        BitsJobErrorContextString = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*((_QWORD *)v9 + 2) + 24LL))(
                                      (__int64)v9 + 16,
                                      5,
                                      &v100);
        if ( BitsJobErrorContextString < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v25 + 16LL))((char *)this + 168) )
            goto LABEL_44;
          v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v25 + 16LL))((char *)this + 168);
          v29 = 0;
          if ( !v28 )
            goto LABEL_43;
          LODWORD(v76) = BitsJobErrorContextString;
          LODWORD(v73) = 1983;
          goto LABEL_41;
        }
      }
    }
    else if ( ((a5 - 4) & 0xFFFFFFFB) == 0 )
    {
      v11 = 1;
    }
    BitsJobErrorContextString = CDlpTransportBits::GetBitsJobErrorContextString(this, v90, &v97);
    v40 = (char *)this + 168;
    if ( BitsJobErrorContextString < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
        goto LABEL_44;
      v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
      v29 = 0;
      if ( !v28 )
        goto LABEL_43;
      LODWORD(v76) = BitsJobErrorContextString;
      LODWORD(v73) = 1992;
      goto LABEL_41;
    }
    BitsJobErrorContextString = CDlpTransportBits::GetBitsJobStateString(this, a5, &v96);
    v41 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
    if ( BitsJobErrorContextString < 0 )
    {
      if ( !v41 )
        goto LABEL_44;
      v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
      v29 = 0;
      if ( !v28 )
        goto LABEL_43;
      LODWORD(v76) = BitsJobErrorContextString;
      LODWORD(v73) = 1993;
      goto LABEL_41;
    }
    if ( v41 )
    {
      v42 = (const wchar_t *)v94;
      if ( !v94 )
        v42 = L"None";
      v43 = v81;
      v44 = v97;
      v45 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
      v46 = L"Yes";
      if ( !v11 )
        v46 = L"No";
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v45,
        v11 + 3,
        (__int64)L"Bits Error: Fatal = [%s], State = [%s], Error_Context = [%s], hr = [0x%X], Description = [%s] ",
        v46,
        v96,
        v44,
        v43,
        v42);
      v9 = v101;
    }
    if ( !v11 )
    {
      *v98 = 0;
      goto LABEL_44;
    }
    if ( a6 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
      {
        v47 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
        CDlpLogT<CEmptyType>::DlpLogFormat(v47, 2u, (__int64)L"Bits Error: Ignoring error...");
      }
    }
    else if ( v95 )
    {
      if ( v9 )
      {
        BitsJobErrorContextString = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v95)(
                                      v95,
                                      &GUID_83e81b93_0873_474d_8a8c_f2018b1a939c,
                                      &v89);
        if ( BitsJobErrorContextString < 0 )
        {
          if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
          {
            v48 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
            CDlpLogT<CEmptyType>::DlpLogFormat(
              v48,
              3u,
              (__int64)L"Bits Error: Unable to obtain IBackgroundCopyFile2 interface, hr = [0x%X]",
              (unsigned int)BitsJobErrorContextString);
          }
          BitsJobErrorContextString = 0;
        }
      }
    }
    if ( v89 && v9 )
    {
      BitsJobErrorContextString = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v89 + 24LL))(
                                    v89,
                                    &lpString2);
      if ( BitsJobErrorContextString < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
          goto LABEL_44;
        v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
        v29 = 0;
        if ( !v28 )
          goto LABEL_43;
        LODWORD(v76) = BitsJobErrorContextString;
        LODWORD(v73) = 2030;
        goto LABEL_41;
      }
      BitsJobErrorContextString = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v89 + 32LL))(v89, &pv);
      v49 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
      if ( BitsJobErrorContextString < 0 )
      {
        if ( !v49 )
          goto LABEL_44;
        v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
        v29 = 0;
        if ( !v28 )
          goto LABEL_43;
        LODWORD(v76) = BitsJobErrorContextString;
        LODWORD(v73) = 2031;
        goto LABEL_41;
      }
      if ( v49 )
      {
        v50 = pv;
        v51 = lpString2;
        v52 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
        CDlpLogT<CEmptyType>::DlpLogFormat(v52, 4u, (__int64)L"Bits Error: File [%s] => [%s]", v51, v50);
      }
      BitsJobErrorContextString = (*(__int64 (__fastcall **)(struct IDlpTask *, unsigned int *))(*(_QWORD *)v9 + 184LL))(
                                    v9,
                                    &v85);
      if ( BitsJobErrorContextString < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
          goto LABEL_44;
        v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
        v29 = 0;
        if ( !v28 )
          goto LABEL_43;
        LODWORD(v76) = BitsJobErrorContextString;
        LODWORD(v73) = 2035;
        goto LABEL_41;
      }
      v53 = 0;
      if ( v85 )
      {
        v12 = 0;
        while ( !v12 )
        {
          if ( v83 )
          {
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v83)[2])(v83);
            v83 = 0;
          }
          BitsJobErrorContextString = (*(__int64 (__fastcall **)(struct IDlpTask *, _QWORD, _QWORD *))(*(_QWORD *)v9 + 168LL))(
                                        v9,
                                        v53,
                                        &v83);
          if ( BitsJobErrorContextString < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
              goto LABEL_45;
            v58 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
            v59 = 0;
            if ( v58 )
            {
              LODWORD(v76) = BitsJobErrorContextString;
              LODWORD(v73) = 2042;
              goto LABEL_162;
            }
            goto LABEL_164;
          }
          if ( v84 )
          {
            SysFreeString(v84);
            v84 = 0;
          }
          BitsJobErrorContextString = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), BSTR *))(*v83)[6])(
                                        v83,
                                        &v84);
          if ( BitsJobErrorContextString < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
              goto LABEL_45;
            v58 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
            v59 = 0;
            if ( v58 )
            {
              LODWORD(v76) = BitsJobErrorContextString;
              LODWORD(v73) = 2045;
              goto LABEL_162;
            }
            goto LABEL_164;
          }
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          BitsJobErrorContextString = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), BSTR *))(*v83)[7])(
                                        v83,
                                        &bstrString);
          if ( BitsJobErrorContextString < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
              goto LABEL_45;
            v58 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
            v59 = 0;
            if ( v58 )
            {
              LODWORD(v76) = BitsJobErrorContextString;
              LODWORD(v73) = 2048;
              goto LABEL_162;
            }
            goto LABEL_164;
          }
          if ( !lstrcmpW(v84, lpString2) && !lstrcmpW(bstrString, (LPCWSTR)pv) )
          {
            v79 = v83;
            v83 = 0;
            v102 = v79;
            v54 = v84;
            v84 = 0;
            if ( v80 )
              SysFreeString(v80);
            v80 = v54;
            v12 = v79;
            BitsJobErrorContextString = (*v79[2])(v79 + 2, v81, Src);
            if ( BitsJobErrorContextString < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
                goto LABEL_45;
              v58 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
              v59 = 0;
              if ( v58 )
              {
                LODWORD(v76) = BitsJobErrorContextString;
                LODWORD(v73) = 2057;
                goto LABEL_162;
              }
              goto LABEL_164;
            }
          }
          if ( ++v53 >= v85 )
            break;
        }
      }
      v99 = (unsigned __int64)v79;
      BitsJobErrorContextString = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*((_QWORD *)v9 + 2) + 24LL))(
                                    (__int64)v9 + 16,
                                    65537,
                                    &v99);
      if ( BitsJobErrorContextString < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
        {
LABEL_158:
          v12 = v79;
          goto LABEL_45;
        }
        v55 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
        v56 = 0;
        if ( !v55 )
        {
LABEL_157:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v56);
          goto LABEL_158;
        }
        LODWORD(v76) = BitsJobErrorContextString;
        LODWORD(v73) = 2071;
LABEL_155:
        v57 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v55,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpTransportBits::HandleJobError",
                v73,
                v76);
        v56 = (unsigned int)v57;
        if ( v57 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v57);
        goto LABEL_157;
      }
      if ( v79 )
      {
        if ( DWORD2(v99) )
        {
          BitsJobErrorContextString = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), BSTR *))(*v79)[6])(
                                        v79,
                                        &v86);
          if ( BitsJobErrorContextString < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
              goto LABEL_158;
            v55 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
            v56 = 0;
            if ( !v55 )
              goto LABEL_157;
            LODWORD(v76) = BitsJobErrorContextString;
            LODWORD(v73) = 2081;
            goto LABEL_155;
          }
          v61 = lstrcmpW(v86, v80);
          v62 = (char *)this + 168;
          v63 = v61 == 0;
          v64 = *(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL);
          if ( v63 )
          {
            if ( v64(v62) )
            {
              v67 = v86;
              v68 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
              CDlpLogT<CEmptyType>::DlpLogFormat(v68, 2u, (__int64)L"Bits Error: SourceUrl Unmodified: [%s]", v67);
            }
          }
          else
          {
            if ( v64(v62) )
            {
              v65 = v86;
              v66 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
              CDlpLogT<CEmptyType>::DlpLogFormat(
                v66,
                2u,
                (__int64)L"Bits Error: SourceUrl Modified: [%s] => [%s]",
                v80,
                v65);
            }
            BitsJobErrorContextString = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v89 + 56LL))(v89, v86);
            if ( BitsJobErrorContextString < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
                goto LABEL_44;
              v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
              v29 = 0;
              if ( !v28 )
                goto LABEL_43;
              LODWORD(v76) = BitsJobErrorContextString;
              LODWORD(v73) = 2091;
              goto LABEL_41;
            }
          }
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 408));
          v104 = 1;
          *((_DWORD *)this + 98) = 0;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          if ( v104 )
          {
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 408));
            v104 = 0;
          }
          if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
          {
            v69 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
            CDlpLogT<CEmptyType>::DlpLogFormat(v69, 2u, (__int64)L"Bits Error: Reset retry count to zero.");
          }
          BitsJobErrorContextString = (*(__int64 (__fastcall **)(struct IDlpTask *, int *))(*(_QWORD *)v9 + 24LL))(
                                        v9,
                                        &v91);
          if ( BitsJobErrorContextString < 0 )
          {
            if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
              goto LABEL_44;
            v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
            v29 = 0;
            if ( !v28 )
              goto LABEL_43;
            LODWORD(v76) = BitsJobErrorContextString;
            LODWORD(v73) = 2106;
            goto LABEL_41;
          }
          if ( v91 == 3 )
          {
            BitsJobErrorContextString = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v9 + 2) + 16LL))((__int64)v9 + 16);
            if ( BitsJobErrorContextString < 0 )
            {
              if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
                goto LABEL_44;
              v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
              v29 = 0;
              if ( !v28 )
                goto LABEL_43;
              LODWORD(v76) = BitsJobErrorContextString;
              LODWORD(v73) = 2109;
              goto LABEL_41;
            }
          }
        }
        else
        {
          v12 = v79;
          BitsJobErrorContextString = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64))v79[2][2])(
                                        v79 + 2,
                                        0xFFFFFFFFLL);
          if ( BitsJobErrorContextString < 0 )
          {
            if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
            {
              v58 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
              v59 = 0;
              if ( v58 )
              {
                LODWORD(v76) = BitsJobErrorContextString;
                LODWORD(v73) = 2116;
LABEL_162:
                v60 = CDlpLogT<CEmptyType>::DlpLogFormat(
                        v58,
                        4u,
                        (__int64)L"%s(%d): Result = 0x%X",
                        L"CDlpTransportBits::HandleJobError",
                        v73,
                        v76);
                v59 = (unsigned int)v60;
                if ( v60 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v60);
              }
LABEL_164:
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v59);
            }
            goto LABEL_45;
          }
        }
      }
    }
    *v98 = v81;
    v70 = v103;
    if ( !v103 )
      goto LABEL_44;
    v71 = Src;
    if ( !Src )
      goto LABEL_44;
    v82 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Src, &v82);
    BitsJobErrorContextString = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v71, v82, v70),
          BitsJobErrorContextString = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsJobErrorContextString);
    if ( BitsJobErrorContextString >= 0
      || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168) )
    {
      goto LABEL_44;
    }
    v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))((char *)this + 168);
    v29 = 0;
    if ( !v28 )
      goto LABEL_43;
    LODWORD(v76) = BitsJobErrorContextString;
    LODWORD(v73) = 2129;
    goto LABEL_41;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
  {
    v21 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v22 = 0;
    if ( !v21 )
    {
LABEL_23:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v22);
      goto LABEL_46;
    }
    v78 = BitsJobErrorContextString;
    v75 = 1933;
LABEL_21:
    v23 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v21,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpTransportBits::HandleJobError",
            v75,
            v78);
    v22 = (unsigned int)v23;
    if ( v23 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
    goto LABEL_23;
  }
LABEL_46:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsJobErrorContextString);
  if ( v96 )
  {
    v31 = v96 - 2;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v31);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v33 = v97;
  if ( v97 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v86 )
  {
    SysFreeString(v86);
    v86 = 0;
  }
  if ( v13 )
    SysFreeString(v13);
  if ( v84 )
  {
    SysFreeString(v84);
    v84 = 0;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( lpString2 )
  {
    CoTaskMemFree((LPVOID)lpString2);
    lpString2 = 0;
  }
  if ( Src )
  {
    CoTaskMemFree(Src);
    Src = 0;
  }
  if ( v94 )
  {
    CoTaskMemFree(v94);
    v94 = 0;
  }
  if ( v12 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v12)[2])(v12);
  if ( v83 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v83)[2])(v83);
    v83 = 0;
  }
  if ( v89 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
    v89 = 0;
  }
  if ( v95 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
  return (unsigned int)BitsJobErrorContextString;
}

```

## disassembly

```asm
0x180061f64  mov     [rsp-8+arg_10], rbx
0x180061f69  push    rbp
0x180061f6a  push    rsi
0x180061f6b  push    rdi
0x180061f6c  push    r12
0x180061f6e  push    r13
0x180061f70  push    r14
0x180061f72  push    r15
0x180061f74  lea     rbp, [rsp-50h]
0x180061f79  sub     rsp, 150h
0x180061f80  mov     rax, cs:__security_cookie
0x180061f87  xor     rax, rsp
0x180061f8a  mov     [rbp+80h+var_40], rax
0x180061f8e  mov     rbx, r9
0x180061f91  mov     r12, rdx
0x180061f94  mov     [rbp+80h+var_90], rdx
0x180061f98  mov     r13, rcx
0x180061f9b  mov     rax, [rbp+80h+arg_30]
0x180061fa2  mov     [rbp+80h+var_B8], rax
0x180061fa6  mov     rcx, [rbp+80h+arg_38]
0x180061fad  mov     [rbp+80h+var_80], rcx
0x180061fb1  xor     r15d, r15d
0x180061fb4  mov     [rbp+80h+var_EC], r15d
0x180061fb8  mov     [rsp+180h+var_130], r15d
0x180061fbd  mov     [rsp+180h+var_118], r15d
0x180061fc2  mov     [rsp+180h+var_12C], r15d
0x180061fc7  xorps   xmm0, xmm0
0x180061fca  xor     ecx, ecx
0x180061fcc  movups  [rbp+80h+var_58], xmm0
0x180061fd0  mov     [rbp+80h+var_48], rcx
0x180061fd4  mov     [rbp+80h+var_D0], r15
0x180061fd8  mov     [rbp+80h+var_F8], r15
0x180061fdc  mov     [rsp+180h+var_128], r15
0x180061fe1  mov     edi, r15d
0x180061fe4  mov     [rsp+180h+var_140], r15
0x180061fe9  mov     [rbp+80h+var_88], r15
0x180061fed  mov     [rbp+80h+var_D8], r15
0x180061ff1  mov     [rbp+80h+Src], r15
0x180061ff5  mov     [rbp+80h+lpString2], r15
0x180061ff9  mov     [rbp+80h+pv], r15
0x180061ffd  mov     [rsp+180h+var_120], r15
0x180062002  mov     esi, r15d
0x180062005  mov     [rsp+180h+var_138], r15
0x18006200a  mov     [rsp+180h+var_110], r15
0x18006200f  mov     [rsp+180h+bstrString], r15
0x180062014  mov     [rbp+80h+var_C0], r15
0x180062018  mov     [rbp+80h+var_C8], r15
0x18006201c  movups  [rbp+80h+var_A0], xmm0
0x180062020  xorps   xmm1, xmm1
0x180062023  movups  [rbp+80h+var_B0], xmm1
0x180062027  mov     [rbp+80h+var_F0], r15d
0x18006202b  test    r8, r8
0x18006202e  jnz     short loc_1800620AA
0x180062030  mov     ebx, 80070057h
0x180062035  mov     r14d, ebx
0x180062038  lea     rdi, [r13+0A8h]
0x18006203f  mov     rax, [rdi]
0x180062042  mov     rcx, rdi
0x180062045  mov     rax, [rax+10h]
0x180062049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006204e  test    rax, rax
0x180062051  jz      short loc_1800620A0
0x180062053  mov     rax, [rdi]
0x180062056  mov     rcx, rdi
0x180062059  mov     rax, [rax+10h]
0x18006205d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062062  xor     ecx, ecx
0x180062064  test    rax, rax
0x180062067  jz      short loc_18006209B
0x180062069  mov     dword ptr [rsp+180h+var_158], ebx
0x18006206d  mov     dword ptr [rsp+180h+var_160], 77Ah
0x180062075  lea     r9, aCdlptransportb_1; "CDlpTransportBits::HandleJobError"
0x18006207c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180062083  mov     edx, 4
0x180062088  mov     rcx, rax
0x18006208b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180062090  test    eax, eax
0x180062092  mov     ecx, eax
0x180062094  jns     short loc_18006209B
0x180062096  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006209b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800620a0  mov     rdi, [rsp+180h+var_140]
0x1800620a5  jmp     loc_1800623B3
0x1800620aa  test    rbx, rbx
0x1800620ad  jnz     short loc_1800620F9
0x1800620af  mov     ebx, 80070057h
0x1800620b4  mov     r14d, ebx
0x1800620b7  lea     rdi, [r13+0A8h]
0x1800620be  mov     rax, [rdi]
0x1800620c1  mov     rcx, rdi
0x1800620c4  mov     rax, [rax+10h]
0x1800620c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620cd  test    rax, rax
0x1800620d0  jz      short loc_1800620A0
0x1800620d2  mov     rax, [rdi]
0x1800620d5  mov     rcx, rdi
0x1800620d8  mov     rax, [rax+10h]
0x1800620dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620e1  xor     ecx, ecx
0x1800620e3  test    rax, rax
0x1800620e6  jz      short loc_18006209B
0x1800620e8  mov     dword ptr [rsp+180h+var_158], ebx
0x1800620ec  mov     dword ptr [rsp+180h+var_160], 77Bh
0x1800620f4  jmp     loc_180062075
0x1800620f9  test    rax, rax
0x1800620fc  jnz     short loc_180062150
0x1800620fe  mov     ebx, 80070057h
0x180062103  mov     r14d, ebx
0x180062106  lea     rdi, [r13+0A8h]
0x18006210d  mov     rax, [rdi]
0x180062110  mov     rcx, rdi
0x180062113  mov     rax, [rax+10h]
0x180062117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006211c  test    rax, rax
0x18006211f  jz      loc_1800620A0
0x180062125  mov     rax, [rdi]
0x180062128  mov     rcx, rdi
0x18006212b  mov     rax, [rax+10h]
0x18006212f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062134  xor     ecx, ecx
0x180062136  test    rax, rax
0x180062139  jz      loc_18006209B
0x18006213f  mov     dword ptr [rsp+180h+var_158], ebx
0x180062143  mov     dword ptr [rsp+180h+var_160], 77Ch
0x18006214b  jmp     loc_180062075
0x180062150  mov     rax, [r9]
0x180062153  lea     r8, [rsp+180h+var_130]
0x180062158  lea     rdx, [rbp+80h+var_F0]
0x18006215c  mov     rcx, rbx
0x18006215f  mov     rax, [rax+18h]
0x180062163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062168  mov     r14d, eax
0x18006216b  test    eax, eax
0x18006216d  jns     short loc_1800621E1
0x18006216f  lea     rbx, [r13+0A8h]
0x180062176  mov     rdx, [rbx]
0x180062179  mov     rcx, rbx
0x18006217c  mov     rax, [rdx+10h]
0x180062180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062185  test    rax, rax
0x180062188  jz      loc_1800623B3
0x18006218e  mov     rax, [rbx]
0x180062191  mov     rcx, rbx
0x180062194  mov     rax, [rax+10h]
0x180062198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006219d  xor     ecx, ecx
0x18006219f  test    rax, rax
0x1800621a2  jz      short loc_1800621D7
0x1800621a4  mov     dword ptr [rsp+180h+var_158], r14d
0x1800621a9  mov     dword ptr [rsp+180h+var_160], 780h
0x1800621b1  lea     r9, aCdlptransportb_1; "CDlpTransportBits::HandleJobError"
0x1800621b8  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800621bf  mov     edx, 4
0x1800621c4  mov     rcx, rax
0x1800621c7  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800621cc  test    eax, eax
0x1800621ce  mov     ecx, eax
0x1800621d0  jns     short loc_1800621D7
0x1800621d2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800621d7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800621dc  jmp     loc_1800623B3
0x1800621e1  mov     rax, [rbx]
0x1800621e4  lea     r8, [rbp+80h+var_D8]
0x1800621e8  mov     edx, 409h
0x1800621ed  mov     rcx, rbx
0x1800621f0  mov     rax, [rax+28h]
0x1800621f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621f9  mov     rax, [rbx]
0x1800621fc  lea     r8, [rbp+80h+Src]
0x180062200  mov     edx, 400h
0x180062205  mov     rcx, rbx
0x180062208  mov     rax, [rax+28h]
0x18006220c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062211  mov     rax, [rbx]
0x180062214  lea     rdx, [rbp+80h+var_D0]
0x180062218  mov     rcx, rbx
0x18006221b  mov     rax, [rax+20h]
0x18006221f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062224  mov     r14d, eax
0x180062227  cmp     eax, 80200004h
0x18006222c  jz      short loc_18006227D
0x18006222e  test    eax, eax
0x180062230  jns     short loc_18006227D
0x180062232  lea     rbx, [r13+0A8h]
0x180062239  mov     rax, [rbx]
0x18006223c  mov     rcx, rbx
0x18006223f  mov     rax, [rax+10h]
0x180062243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062248  test    rax, rax
0x18006224b  jz      loc_1800623B3
0x180062251  mov     rax, [rbx]
0x180062254  mov     rcx, rbx
0x180062257  mov     rax, [rax+10h]
0x18006225b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062260  xor     ecx, ecx
0x180062262  test    rax, rax
0x180062265  jz      loc_1800621D7
0x18006226b  mov     dword ptr [rsp+180h+var_158], r14d
0x180062270  mov     dword ptr [rsp+180h+var_160], 78Dh
0x180062278  jmp     loc_1800621B1
0x18006227d  mov     edi, [rbp+80h+arg_20]
0x180062283  cmp     edi, 5
0x180062286  jnz     loc_18006263A
0x18006228c  lea     rcx, [r13+208h]; this
0x180062293  lea     rdx, [rsp+180h+var_12C]; unsigned int *
0x180062298  call    ?Increment@CDword@@QEAAJPEAK@Z; CDword::Increment(ulong *)
0x18006229d  mov     r14d, eax
0x1800622a0  lea     rbx, [r13+0A8h]
0x1800622a7  mov     rax, [rbx]
0x1800622aa  mov     rax, [rax+10h]
0x1800622ae  mov     rcx, rbx
0x1800622b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622b6  test    r14d, r14d
0x1800622b9  jns     short loc_1800622F0
0x1800622bb  test    rax, rax
0x1800622be  jz      loc_1800620A0
0x1800622c4  mov     rax, [rbx]
0x1800622c7  mov     rcx, rbx
0x1800622ca  mov     rax, [rax+10h]
0x1800622ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622d3  xor     ecx, ecx
0x1800622d5  test    rax, rax
0x1800622d8  jz      loc_18006209B
0x1800622de  mov     dword ptr [rsp+180h+var_158], r14d
0x1800622e3  mov     dword ptr [rsp+180h+var_160], 795h
0x1800622eb  jmp     loc_180062075
0x1800622f0  mov     esi, 1
0x1800622f5  test    rax, rax
0x1800622f8  jz      short loc_18006231F
0x1800622fa  mov     rax, [rbx]
0x1800622fd  mov     rcx, rbx
0x180062300  mov     rax, [rax+10h]
0x180062304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062309  mov     r9d, [rsp+180h+var_12C]
0x18006230e  lea     r8, aBitsErrorTrans; "Bits Error: Transient Error [%d]"
0x180062315  mov     edx, esi
0x180062317  mov     rcx, rax
0x18006231a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006231f  mov     rcx, [rbp+80h+var_D0]
0x180062323  test    rcx, rcx
0x180062326  jz      loc_18006255E
0x18006232c  mov     rax, [rcx]
0x18006232f  lea     rdx, [rbp+80h+var_58]
0x180062333  mov     rax, [rax+28h]
0x180062337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006233c  mov     r14d, eax
0x18006233f  test    eax, eax
0x180062341  jns     loc_180062554
0x180062347  mov     rax, [rbx]
0x18006234a  mov     rcx, rbx
0x18006234d  mov     rax, [rax+10h]
0x180062351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062356  test    rax, rax
0x180062359  jz      short loc_1800623A9
0x18006235b  mov     rax, [rbx]
0x18006235e  mov     rcx, rbx
0x180062361  mov     rax, [rax+10h]
0x180062365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006236a  xor     ecx, ecx
0x18006236c  test    rax, rax
0x18006236f  jz      short loc_1800623A4
0x180062371  mov     dword ptr [rsp+180h+var_158], r14d
0x180062376  mov     dword ptr [rsp+180h+var_160], 79Ch
0x18006237e  mov     edx, 4
0x180062383  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006238a  lea     r9, aCdlptransportb_1; "CDlpTransportBits::HandleJobError"
0x180062391  mov     rcx, rax
0x180062394  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180062399  test    eax, eax
0x18006239b  mov     ecx, eax
0x18006239d  jns     short loc_1800623A4
0x18006239f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800623a4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800623a9  mov     rdi, [rsp+180h+var_140]
0x1800623ae  mov     rsi, [rsp+180h+var_138]
0x1800623b3  mov     ecx, r14d
0x1800623b6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800623bb  nop
0x1800623bc  mov     rax, [rbp+80h+var_C8]
0x1800623c0  test    rax, rax
0x1800623c3  jz      short loc_1800623E5
0x1800623c5  lea     rbx, [rax-4]
0x1800623c9  call    cs:__imp_GetProcessHeap
0x1800623cf  mov     rcx, rax; hHeap
0x1800623d2  mov     r8, rbx; lpMem
0x1800623d5  xor     edx, edx; dwFlags
0x1800623d7  call    cs:__imp_HeapFree
0x1800623dd  xor     ecx, ecx
0x1800623df  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800623e4  nop
0x1800623e5  mov     rbx, [rbp+80h+var_C0]
0x1800623e9  test    rbx, rbx
0x1800623ec  jz      short loc_18006240B
0x1800623ee  call    cs:__imp_GetProcessHeap
0x1800623f4  mov     rcx, rax; hHeap
0x1800623f7  lea     r8, [rbx-4]; lpMem
0x1800623fb  xor     edx, edx; dwFlags
0x1800623fd  call    cs:__imp_HeapFree
0x180062403  xor     ecx, ecx
0x180062405  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
  ... truncated ...
```
