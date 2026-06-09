# CDlpActionLayoutUsb::DeserializeRoutine(IDlpObjectData *,WINDLP_STATE,int *)

- ea: `0x180011170`
- end: `0x180011d8f`
- name: `?DeserializeRoutine@CDlpActionLayoutUsb@@EEAAJPEAVIDlpObjectData@@W4WINDLP_STATE@@PEAH@Z`
- size: `3103`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callees

- `0x180002898`
- `0x180007bbc`
- `0x18000aba4`
- `0x18000ea20`
- `0x180011170`
- `0x180012f5c`
- `0x18001fd60`
- `0x18007ec76`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011b85`
- `OLEAUT32!__imp_SysFreeString` at `0x180011b9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180011baf`
- `OLEAUT32!__imp_SysFreeString` at `0x180011bea`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c2f`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c42`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c55`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c68`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ca2`
- `OLEAUT32!__imp_SysFreeString` at `0x180011cb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180011b85`
- `OLEAUT32!__imp_SysFreeString` at `0x180011b9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180011baf`
- `OLEAUT32!__imp_SysFreeString` at `0x180011bea`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c2f`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c42`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c55`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c68`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ca2`
- `OLEAUT32!__imp_SysFreeString` at `0x180011cb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011bc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011bc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011bd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011bd2`

## string_xrefs

- `0x18001172b`: `LayoutPath`
- `0x180011269`: `CDlpActionLayoutUsb::DeserializeRoutine`
- `0x180011400`: `ReconstructionPathCount`
- `0x18001148e`: `BootWimPath`
- `0x1800114d9`: `InstallWimPath`
- `0x180011523`: `OemWinreWimPath`
- `0x18001156d`: `CustomizationWimPath`
- `0x180011601`: `CustomizationDirPath`
- `0x18001164b`: `OemExtensibilityDirPath`
- `0x180011695`: `AutoApplyDirPath`
- `0x1800116e0`: `CloudDataPath`
- `0x180011ac4`: `ReconstructionPath`
- `0x180011af2`: `ReconstructionPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CDlpActionLayoutUsb::DeserializeRoutine(
        _QWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, _QWORD, _QWORD),
        __int64 a3,
        _DWORD *a4)
{
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 (__fastcall ***v11)(__int64, const wchar_t *, char *); // rsi
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int v22; // r14d
  int v23; // eax
  int v24; // eax
  BSTR v25; // rsi
  int StringCch; // eax
  int v27; // eax
  __int64 v28; // rbx
  HANDLE ProcessHeap; // rax
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+28h] [rbp-D8h]
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  int v34; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v35; // [rsp+3Ch] [rbp-C4h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v37; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v38; // [rsp+50h] [rbp-B0h] BYREF
  int v39; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v40; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v41; // [rsp+68h] [rbp-98h] BYREF
  BSTR v42; // [rsp+70h] [rbp-90h] BYREF
  BSTR v43; // [rsp+78h] [rbp-88h] BYREF
  BSTR v44; // [rsp+80h] [rbp-80h] BYREF
  BSTR v45; // [rsp+88h] [rbp-78h] BYREF
  BSTR v46; // [rsp+90h] [rbp-70h] BYREF
  BSTR v47; // [rsp+98h] [rbp-68h] BYREF
  BSTR v48; // [rsp+A0h] [rbp-60h] BYREF
  BSTR v49; // [rsp+A8h] [rbp-58h] BYREF
  BSTR v50; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v54; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v55; // [rsp+E0h] [rbp-20h]
  __int128 v56; // [rsp+F0h] [rbp-10h]
  __int128 v57; // [rsp+100h] [rbp+0h] BYREF
  BSTR v58; // [rsp+110h] [rbp+10h]
  OLECHAR v59; // [rsp+118h] [rbp+18h]
  __int64 v60; // [rsp+11Ch] [rbp+1Ch]
  BSTR v61; // [rsp+128h] [rbp+28h]
  __int64 v62; // [rsp+130h] [rbp+30h]
  BSTR v63; // [rsp+138h] [rbp+38h]
  __int64 v64; // [rsp+140h] [rbp+40h]
  BOOL v65; // [rsp+148h] [rbp+48h]
  __int128 v66; // [rsp+150h] [rbp+50h] BYREF
  BSTR v67; // [rsp+160h] [rbp+60h]
  OLECHAR v68; // [rsp+168h] [rbp+68h]
  __int64 v69; // [rsp+16Ch] [rbp+6Ch]
  BSTR v70; // [rsp+178h] [rbp+78h]
  BSTR v71; // [rsp+180h] [rbp+80h]
  BSTR v72; // [rsp+188h] [rbp+88h]
  BSTR v73; // [rsp+190h] [rbp+90h]
  BSTR v74; // [rsp+1A8h] [rbp+A8h]
  BSTR v75; // [rsp+1B0h] [rbp+B0h]
  BSTR v76; // [rsp+1B8h] [rbp+B8h]
  __int64 v77; // [rsp+1C0h] [rbp+C0h]
  __int64 v78; // [rsp+1C8h] [rbp+C8h]
  BOOL v79; // [rsp+1D0h] [rbp+D0h]
  BSTR v80; // [rsp+1D8h] [rbp+D8h]
  BSTR v81; // [rsp+1E0h] [rbp+E0h]
  __int128 Buf2; // [rsp+1F0h] [rbp+F0h] BYREF

  v50 = 0;
  v38 = 0;
  v49 = 0;
  v48 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  v37 = 0;
  v35 = 0;
  v42 = 0;
  v53 = 0;
  v41 = 0;
  v40 = 0;
  bstrString = 0;
  Buf2 = 0;
  v33 = 0;
  v51 = 0;
  v52 = 0;
  v34 = 0;
  memset_0(&v57, 0, 0x50u);
  v54 = 0;
  v55 = 0;
  v56 = 0;
  memset_0(&v66, 0, 0x98u);
  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = a1[11];
    if ( v8 )
    {
      v32 = -2147024809;
      v31 = 784;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = a1[11];
    if ( v8 )
    {
      v32 = -2147024809;
      v31 = 786;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v11 = (__int64 (__fastcall ***)(__int64, const wchar_t *, char *))(a2 + 1);
  v12 = (*a2[1])(a2 + 1, L"FileSystemType", &v33);
  v7 = v12;
  if ( v12 < 0 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v12;
      v31 = 788;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v13 = (**v11)((__int64)(a2 + 1), L"Flags", (char *)&v33 + 4);
  v7 = v13;
  if ( v13 < 0 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v13;
      v31 = 789;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v14 = (*v11)[1]((__int64)(a2 + 1), L"MaxVolumeSize", (char *)&v51);
  v7 = v14;
  if ( v14 < 0 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v14;
      v31 = 790;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v15 = (*v11)[1]((__int64)(a2 + 1), L"FileSplitSize", (char *)&v52);
  v7 = v15;
  if ( v15 < 0 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v15;
      v31 = 791;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v16 = (**v11)((__int64)(a2 + 1), L"UseSimplifiedWimSplit", (char *)&v34);
  v7 = v16;
  if ( v16 < 0 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v16;
      v31 = 792;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v17 = (**v11)((__int64)(a2 + 1), L"ReconstructionPathCount", (char *)&v35);
  v7 = v17;
  if ( v17 < 0 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v17;
      v31 = 793;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"UsbDriveLetter", (char *)&v40);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 797;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"BootWimPath", (char *)&v50);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 801;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"InstallWimPath", (char *)&v38);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 805;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"OemWinreWimPath", (char *)&v49);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 809;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"CustomizationWimPath", (char *)&v48);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 813;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"ReconstructionRoot", (char *)&v44);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 817;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"CustomizationDirPath", (char *)&v47);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 821;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"OemExtensibilityDirPath", (char *)&v46);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 825;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"AutoApplyDirPath", (char *)&v45);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 829;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"CloudDataPath", (char *)&v43);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 833;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"LayoutPath", (char *)&v41);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 837;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v7 = (*v11)[2]((__int64)(a2 + 1), L"VolumeLabel", (char *)&bstrString);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v7;
      v31 = 841;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *))(*a1 + 56LL))(a1, &Buf2);
  v7 = v18;
  if ( v18 < 0 )
  {
    v8 = a1[11];
    if ( v8 )
    {
      v32 = v18;
      v31 = 843;
      goto LABEL_4;
    }
    goto LABEL_110;
  }
  if ( !memcmp_0(&WINDLP_ACTION_LAYOUTUSB, &Buf2, 0x10u) )
  {
    memset_0(&v57, 0, 0x50u);
    v57 = WINDLP_ACTION_LAYOUTUSB;
    v58 = v41;
    if ( v40 )
      v59 = *v40;
    else
      v59 = 0;
    v60 = v33;
    v61 = bstrString;
    v62 = v51;
    v64 = v52;
    v63 = v38;
    v65 = v34 != 0;
    v19 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64))(*a1 + 32LL))(a1, &v57, 80);
    v7 = v19;
    if ( v19 < 0 )
    {
      v8 = a1[11];
      if ( v8 )
      {
        v32 = v19;
        v31 = 860;
        goto LABEL_4;
      }
      goto LABEL_110;
    }
    goto LABEL_97;
  }
  if ( !memcmp_0(&WINDLP_ACTION_RECOVEROEM, &Buf2, 0x10u) )
  {
    v54 = WINDLP_ACTION_RECOVEROEM;
    *(_QWORD *)&v55 = v50;
    *((_QWORD *)&v55 + 1) = v38;
    *(_QWORD *)&v56 = v33;
    *((_QWORD *)&v56 + 1) = bstrString;
    v20 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64))(*a1 + 32LL))(a1, &v54, 48);
    v7 = v20;
    if ( v20 < 0 )
    {
      v8 = a1[11];
      if ( v8 )
      {
        v32 = v20;
        v31 = 874;
        goto LABEL_4;
      }
      goto LABEL_110;
    }
    goto LABEL_97;
  }
  if ( memcmp_0(&WINDLP_ACTION_RECOVERUSB, &Buf2, 0x10u) )
    goto LABEL_97;
  memset_0(&v66, 0, 0x98u);
  v66 = WINDLP_ACTION_LAYOUTUSB;
  v67 = v50;
  v70 = v38;
  v80 = v49;
  v71 = v48;
  v73 = v44;
  v74 = v47;
  v75 = v46;
  v76 = v45;
  v81 = v43;
  v68 = v40 ? *v40 : 0;
  v69 = v33;
  v72 = bstrString;
  v77 = v51;
  v78 = v52;
  v79 = v34 != 0;
  v21 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64))(*a1 + 32LL))(a1, &v66, 152);
  v7 = v21;
  if ( v21 >= 0 )
  {
LABEL_97:
    v22 = 0;
    if ( !v35 )
    {
LABEL_109:
      *a4 = 0;
      goto LABEL_110;
    }
    while ( 1 )
    {
      if ( v37 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
        v37 = 0;
      }
      v23 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), const wchar_t *, _QWORD, _QWORD **))(*a2)[4])(
              a2,
              L"ReconstructionPath",
              v22,
              &v37);
      v7 = v23;
      if ( v23 < 0 )
      {
        v8 = a1[11];
        if ( !v8 )
          goto LABEL_110;
        v32 = v23;
        v31 = 907;
LABEL_4:
        v9 = CDlpLogT<CEmptyType>::DlpLogFormat(
               v8,
               4,
               L"%s(%d): Result = 0x%X",
               L"CDlpActionLayoutUsb::DeserializeRoutine",
               v31,
               v32);
        v10 = (unsigned int)v9;
        if ( v9 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
        goto LABEL_110;
      }
      v24 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, BSTR *))(v37[1] + 16LL))(
              v37 + 1,
              L"ReconstructionPath",
              &v42);
      v7 = v24;
      if ( v24 < 0 )
      {
        v8 = a1[11];
        if ( !v8 )
          goto LABEL_110;
        v32 = v24;
        v31 = 909;
        goto LABEL_4;
      }
      v25 = v42;
      if ( !v42 )
        break;
      v39 = 0;
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v42, &v39);
      v7 = StringCch;
      if ( StringCch >= 0 )
        goto LABEL_104;
LABEL_105:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
LABEL_106:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
      if ( (v7 & 0x80000000) != 0 )
      {
        v8 = a1[11];
        if ( !v8 )
          goto LABEL_110;
        v32 = v7;
        v31 = 910;
        goto LABEL_4;
      }
      v27 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(a1 + 143, &v53);
      v7 = v27;
      if ( v27 < 0 )
      {
        v8 = a1[11];
        if ( !v8 )
          goto LABEL_110;
        v32 = v27;
        v31 = 911;
        goto LABEL_4;
      }
      if ( ++v22 >= v35 )
        goto LABEL_109;
    }
    v25 = 0;
LABEL_104:
    StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v25);
    v7 = StringCch;
    if ( StringCch >= 0 )
      goto LABEL_106;
    goto LABEL_105;
  }
  v8 = a1[11];
  if ( v8 )
  {
    v32 = v21;
    v31 = 899;
    goto LABEL_4;
  }
LABEL_110:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v40 )
  {
    SysFreeString(v40);
    v40 = 0;
  }
  if ( v41 )
  {
    SysFreeString(v41);
    v41 = 0;
  }
  v28 = v53;
  if ( v53 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v28 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v42 )
  {
    SysFreeString(v42);
    v42 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v43 )
  {
    SysFreeString(v43);
    v43 = 0;
  }
  if ( v44 )
  {
    SysFreeString(v44);
    v44 = 0;
  }
  if ( v45 )
  {
    SysFreeString(v45);
    v45 = 0;
  }
  if ( v46 )
  {
    SysFreeString(v46);
    v46 = 0;
  }
  if ( v47 )
  {
    SysFreeString(v47);
    v47 = 0;
  }
  if ( v48 )
  {
    SysFreeString(v48);
    v48 = 0;
  }
  if ( v49 )
  {
    SysFreeString(v49);
    v49 = 0;
  }
  if ( v38 )
  {
    SysFreeString(v38);
    v38 = 0;
  }
  if ( v50 )
    SysFreeString(v50);
  return v7;
}

```

## disassembly

```asm
0x180011170  mov     [rsp-8+arg_10], rbx
0x180011175  push    rbp
0x180011176  push    rsi
0x180011177  push    rdi
0x180011178  push    r12
0x18001117a  push    r13
0x18001117c  push    r14
0x18001117e  push    r15
0x180011180  lea     rbp, [rsp-110h]
0x180011188  sub     rsp, 210h
0x18001118f  mov     rax, cs:__security_cookie
0x180011196  xor     rax, rsp
0x180011199  mov     [rbp+140h+var_40], rax
0x1800111a0  mov     r15, r9
0x1800111a3  mov     r12, rdx
0x1800111a6  mov     rbx, rcx
0x1800111a9  xor     r13d, r13d
0x1800111ac  mov     [rbp+140h+var_190], r13
0x1800111b0  mov     [rsp+240h+var_1F0], r13
0x1800111b5  mov     [rbp+140h+var_198], r13
0x1800111b9  mov     [rbp+140h+var_1A0], r13
0x1800111bd  mov     [rbp+140h+var_1A8], r13
0x1800111c1  mov     [rbp+140h+var_1B0], r13
0x1800111c5  mov     [rbp+140h+var_1B8], r13
0x1800111c9  mov     [rbp+140h+var_1C0], r13
0x1800111cd  mov     [rsp+240h+var_1C8], r13
0x1800111d2  mov     [rsp+240h+var_1F8], r13
0x1800111d7  mov     [rsp+240h+var_204], r13d
0x1800111dc  mov     [rsp+240h+var_1D0], r13
0x1800111e1  mov     [rbp+140h+var_178], r13
0x1800111e5  mov     [rsp+240h+var_1D8], r13
0x1800111ea  mov     [rsp+240h+var_1E0], r13
0x1800111ef  mov     [rsp+240h+bstrString], r13
0x1800111f4  xorps   xmm0, xmm0
0x1800111f7  movups  [rbp+140h+Buf2], xmm0
0x1800111fe  mov     dword ptr [rsp+240h+var_210+4], r13d
0x180011203  mov     dword ptr [rsp+240h+var_210], r13d
0x180011208  mov     [rbp+140h+var_188], r13
0x18001120c  mov     [rbp+140h+var_180], r13
0x180011210  mov     [rsp+240h+var_208], r13d
0x180011215  xor     edx, edx; Val
0x180011217  lea     r8d, [r13+50h]; Size
0x18001121b  lea     rcx, [rbp+140h+var_140]; void *
0x18001121f  call    memset_0
0x180011224  xorps   xmm0, xmm0
0x180011227  movups  [rbp+140h+var_170], xmm0
0x18001122b  movups  [rbp+140h+var_160], xmm0
0x18001122f  movups  [rbp+140h+var_150], xmm0
0x180011233  xor     edx, edx; Val
0x180011235  mov     r8d, 98h; Size
0x18001123b  lea     rcx, [rbp+140h+var_F0]; void *
0x18001123f  call    memset_0
0x180011244  test    r12, r12
0x180011247  jnz     short loc_180011296
0x180011249  mov     eax, 80070057h
0x18001124e  mov     edi, eax
0x180011250  mov     rcx, [rbx+58h]
0x180011254  test    rcx, rcx
0x180011257  jz      loc_180011B73
0x18001125d  mov     [rsp+240h+var_218], eax
0x180011261  mov     [rsp+240h+var_220], 310h
0x180011269  lea     r9, aCdlpactionlayo_19; "CDlpActionLayoutUsb::DeserializeRoutine"
0x180011270  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180011277  mov     edx, 4
0x18001127c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180011281  test    eax, eax
0x180011283  mov     ecx, eax
0x180011285  jns     short loc_18001128C
0x180011287  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001128c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180011291  jmp     loc_180011B73
0x180011296  test    r15, r15
0x180011299  jnz     short loc_1800112BD
0x18001129b  mov     eax, 80070057h
0x1800112a0  mov     edi, eax
0x1800112a2  mov     rcx, [rbx+58h]
0x1800112a6  test    rcx, rcx
0x1800112a9  jz      loc_180011B73
0x1800112af  mov     [rsp+240h+var_218], eax
0x1800112b3  mov     [rsp+240h+var_220], 312h
0x1800112bb  jmp     short loc_180011269
0x1800112bd  lea     rsi, [r12+8]
0x1800112c2  mov     rax, [rsi]
0x1800112c5  lea     r8, [rsp+240h+var_210]
0x1800112ca  lea     rdx, aFilesystemtype; "FileSystemType"
0x1800112d1  mov     rcx, rsi
0x1800112d4  mov     rax, [rax]
0x1800112d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112dc  mov     edi, eax
0x1800112de  test    eax, eax
0x1800112e0  jns     short loc_180011300
0x1800112e2  mov     rcx, [rbx+58h]
0x1800112e6  test    rcx, rcx
0x1800112e9  jz      loc_180011B73
0x1800112ef  mov     [rsp+240h+var_218], eax
0x1800112f3  mov     [rsp+240h+var_220], 314h
0x1800112fb  jmp     loc_180011269
0x180011300  mov     rax, [rsi]
0x180011303  lea     r8, [rsp+240h+var_210+4]
0x180011308  lea     rdx, aFlags; "Flags"
0x18001130f  mov     rcx, rsi
0x180011312  mov     rax, [rax]
0x180011315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001131a  mov     edi, eax
0x18001131c  test    eax, eax
0x18001131e  jns     short loc_18001133E
0x180011320  mov     rcx, [rbx+58h]
0x180011324  test    rcx, rcx
0x180011327  jz      loc_180011B73
0x18001132d  mov     [rsp+240h+var_218], eax
0x180011331  mov     [rsp+240h+var_220], 315h
0x180011339  jmp     loc_180011269
0x18001133e  mov     rax, [rsi]
0x180011341  lea     r8, [rbp+140h+var_188]
0x180011345  lea     rdx, aMaxvolumesize; "MaxVolumeSize"
0x18001134c  mov     rcx, rsi
0x18001134f  mov     rax, [rax+8]
0x180011353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011358  mov     edi, eax
0x18001135a  test    eax, eax
0x18001135c  jns     short loc_18001137C
0x18001135e  mov     rcx, [rbx+58h]
0x180011362  test    rcx, rcx
0x180011365  jz      loc_180011B73
0x18001136b  mov     [rsp+240h+var_218], eax
0x18001136f  mov     [rsp+240h+var_220], 316h
0x180011377  jmp     loc_180011269
0x18001137c  mov     rax, [rsi]
0x18001137f  lea     r8, [rbp+140h+var_180]
0x180011383  lea     rdx, aFilesplitsize; "FileSplitSize"
0x18001138a  mov     rcx, rsi
0x18001138d  mov     rax, [rax+8]
0x180011391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011396  mov     edi, eax
0x180011398  test    eax, eax
0x18001139a  jns     short loc_1800113BA
0x18001139c  mov     rcx, [rbx+58h]
0x1800113a0  test    rcx, rcx
0x1800113a3  jz      loc_180011B73
0x1800113a9  mov     [rsp+240h+var_218], eax
0x1800113ad  mov     [rsp+240h+var_220], 317h
0x1800113b5  jmp     loc_180011269
0x1800113ba  mov     rax, [rsi]
0x1800113bd  lea     r8, [rsp+240h+var_208]
0x1800113c2  lea     rdx, aUsesimplifiedw; "UseSimplifiedWimSplit"
0x1800113c9  mov     rcx, rsi
0x1800113cc  mov     rax, [rax]
0x1800113cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113d4  mov     edi, eax
0x1800113d6  test    eax, eax
0x1800113d8  jns     short loc_1800113F8
0x1800113da  mov     rcx, [rbx+58h]
0x1800113de  test    rcx, rcx
0x1800113e1  jz      loc_180011B73
0x1800113e7  mov     [rsp+240h+var_218], eax
0x1800113eb  mov     [rsp+240h+var_220], 318h
0x1800113f3  jmp     loc_180011269
0x1800113f8  mov     rax, [rsi]
0x1800113fb  lea     r8, [rsp+240h+var_204]
0x180011400  lea     rdx, aReconstruction_0; "ReconstructionPathCount"
0x180011407  mov     rcx, rsi
0x18001140a  mov     rax, [rax]
0x18001140d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011412  mov     edi, eax
0x180011414  test    eax, eax
0x180011416  jns     short loc_180011436
0x180011418  mov     rcx, [rbx+58h]
0x18001141c  test    rcx, rcx
0x18001141f  jz      loc_180011B73
0x180011425  mov     [rsp+240h+var_218], eax
0x180011429  mov     [rsp+240h+var_220], 319h
0x180011431  jmp     loc_180011269
0x180011436  mov     rax, [rsi]
0x180011439  lea     r8, [rsp+240h+var_1E0]
0x18001143e  lea     rdx, aUsbdriveletter; "UsbDriveLetter"
0x180011445  mov     rcx, rsi
0x180011448  mov     rax, [rax+10h]
0x18001144c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011451  mov     edi, eax
0x180011453  mov     ecx, 80000000h
0x180011458  add     eax, ecx
0x18001145a  mov     r14d, 80070490h
0x180011460  test    ecx, eax
0x180011462  jnz     short loc_180011487
0x180011464  cmp     edi, r14d
0x180011467  jz      short loc_180011487
0x180011469  mov     rcx, [rbx+58h]
0x18001146d  test    rcx, rcx
0x180011470  jz      loc_180011B73
0x180011476  mov     [rsp+240h+var_218], edi
0x18001147a  mov     [rsp+240h+var_220], 31Dh
0x180011482  jmp     loc_180011269
0x180011487  mov     rax, [rsi]
0x18001148a  lea     r8, [rbp+140h+var_190]
0x18001148e  lea     rdx, aBootwimpath; "BootWimPath"
0x180011495  mov     rcx, rsi
0x180011498  mov     rax, [rax+10h]
0x18001149c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114a1  mov     edi, eax
0x1800114a3  mov     ecx, 80000000h
0x1800114a8  add     eax, ecx
0x1800114aa  test    ecx, eax
0x1800114ac  jnz     short loc_1800114D1
0x1800114ae  cmp     edi, r14d
0x1800114b1  jz      short loc_1800114D1
0x1800114b3  mov     rcx, [rbx+58h]
0x1800114b7  test    rcx, rcx
0x1800114ba  jz      loc_180011B73
0x1800114c0  mov     [rsp+240h+var_218], edi
0x1800114c4  mov     [rsp+240h+var_220], 321h
0x1800114cc  jmp     loc_180011269
0x1800114d1  mov     rax, [rsi]
0x1800114d4  lea     r8, [rsp+240h+var_1F0]
0x1800114d9  lea     rdx, aInstallwimpath; "InstallWimPath"
0x1800114e0  mov     rcx, rsi
0x1800114e3  mov     rax, [rax+10h]
0x1800114e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114ec  mov     edi, eax
0x1800114ee  mov     ecx, 80000000h
0x1800114f3  add     eax, ecx
0x1800114f5  test    ecx, eax
0x1800114f7  jnz     short loc_18001151C
0x1800114f9  cmp     edi, r14d
0x1800114fc  jz      short loc_18001151C
0x1800114fe  mov     rcx, [rbx+58h]
0x180011502  test    rcx, rcx
0x180011505  jz      loc_180011B73
0x18001150b  mov     [rsp+240h+var_218], edi
0x18001150f  mov     [rsp+240h+var_220], 325h
0x180011517  jmp     loc_180011269
0x18001151c  mov     rax, [rsi]
0x18001151f  lea     r8, [rbp+140h+var_198]
0x180011523  lea     rdx, aOemwinrewimpat; "OemWinreWimPath"
0x18001152a  mov     rcx, rsi
0x18001152d  mov     rax, [rax+10h]
0x180011531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011536  mov     edi, eax
0x180011538  mov     ecx, 80000000h
0x18001153d  add     eax, ecx
0x18001153f  test    ecx, eax
0x180011541  jnz     short loc_180011566
0x180011543  cmp     edi, r14d
0x180011546  jz      short loc_180011566
0x180011548  mov     rcx, [rbx+58h]
0x18001154c  test    rcx, rcx
0x18001154f  jz      loc_180011B73
0x180011555  mov     [rsp+240h+var_218], edi
0x180011559  mov     [rsp+240h+var_220], 329h
0x180011561  jmp     loc_180011269
0x180011566  mov     rax, [rsi]
0x180011569  lea     r8, [rbp+140h+var_1A0]
0x18001156d  lea     rdx, aCustomizationw; "CustomizationWimPath"
0x180011574  mov     rcx, rsi
0x180011577  mov     rax, [rax+10h]
0x18001157b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011580  mov     edi, eax
0x180011582  mov     ecx, 80000000h
0x180011587  add     eax, ecx
0x180011589  test    ecx, eax
0x18001158b  jnz     short loc_1800115B0
0x18001158d  cmp     edi, r14d
0x180011590  jz      short loc_1800115B0
0x180011592  mov     rcx, [rbx+58h]
0x180011596  test    rcx, rcx
0x180011599  jz      loc_180011B73
0x18001159f  mov     [rsp+240h+var_218], edi
0x1800115a3  mov     [rsp+240h+var_220], 32Dh
0x1800115ab  jmp     loc_180011269
0x1800115b0  mov     rax, [rsi]
0x1800115b3  lea     r8, [rbp+140h+var_1C0]
0x1800115b7  lea     rdx, aReconstruction; "ReconstructionRoot"
0x1800115be  mov     rcx, rsi
0x1800115c1  mov     rax, [rax+10h]
0x1800115c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115ca  mov     edi, eax
0x1800115cc  mov     ecx, 80000000h
0x1800115d1  add     eax, ecx
0x1800115d3  test    ecx, eax
0x1800115d5  jnz     short loc_1800115FA
0x1800115d7  cmp     edi, r14d
0x1800115da  jz      short loc_1800115FA
0x1800115dc  mov     rcx, [rbx+58h]
0x1800115e0  test    rcx, rcx
0x1800115e3  jz      loc_180011B73
0x1800115e9  mov     [rsp+240h+var_218], edi
0x1800115ed  mov     [rsp+240h+var_220], 331h
0x1800115f5  jmp     loc_180011269
0x1800115fa  mov     rax, [rsi]
0x1800115fd  lea     r8, [rbp+140h+var_1A8]
0x180011601  lea     rdx, aCustomizationd; "CustomizationDirPath"
0x180011608  mov     rcx, rsi
0x18001160b  mov     rax, [rax+10h]
0x18001160f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011614  mov     edi, eax
0x180011616  mov     ecx, 80000000h
0x18001161b  add     eax, ecx
0x18001161d  test    ecx, eax
0x18001161f  jnz     short loc_180011644
0x180011621  cmp     edi, r14d
0x180011624  jz      short loc_180011644
  ... truncated ...
```
