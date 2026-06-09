# CDlpActionWimLayout::DeserializeRoutine(IDlpObjectData *,WINDLP_STATE,int *)

- ea: `0x180012380`
- end: `0x180012c65`
- name: `?DeserializeRoutine@CDlpActionWimLayout@@EEAAJPEAVIDlpObjectData@@W4WINDLP_STATE@@PEAH@Z`
- size: `2277`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012380`
- `0x180012f5c`
- `0x18001fd60`
- `0x18007ec76`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180012bc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180012bd8`
- `OLEAUT32!__imp_SysFreeString` at `0x180012bed`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c02`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c17`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180012bc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180012bd8`
- `OLEAUT32!__imp_SysFreeString` at `0x180012bed`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c02`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c17`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012b4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012b4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012b5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012b5d`

## string_xrefs

- `0x180012452`: `CDlpActionWimLayout::DeserializeRoutine`
- `0x180012507`: `MediaPath`
- `0x180012546`: `LayoutPath`
- `0x180012699`: `LayoutPath`
- `0x1800125ed`: `WimPathX86`
- `0x180012625`: `WimPathX64`
- `0x180012661`: `WimPath`
- `0x180012716`: `CompressionType`
- `0x180012754`: `DeleteSource`
- `0x180012792`: `CleanTargetPath`
- `0x18001289a`: `InstallImagePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDlpActionWimLayout::DeserializeRoutine(_QWORD *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rsi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  bool v16; // cl
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, const wchar_t *, BSTR *); // rax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  _QWORD *v34; // rsi
  __int64 v35; // rbx
  HANDLE ProcessHeap; // rax
  BSTR v37; // rbx
  __int64 v38; // rcx
  int Internal; // eax
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+28h] [rbp-D8h]
  int v43; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v44; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v45; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v46; // [rsp+44h] [rbp-BCh] BYREF
  int v47; // [rsp+48h] [rbp-B8h] BYREF
  int v48; // [rsp+4Ch] [rbp-B4h] BYREF
  int v49; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v50; // [rsp+54h] [rbp-ACh] BYREF
  BSTR v51; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v53; // [rsp+68h] [rbp-98h] BYREF
  BSTR v54; // [rsp+70h] [rbp-90h] BYREF
  BSTR v55; // [rsp+78h] [rbp-88h] BYREF
  BSTR v56; // [rsp+80h] [rbp-80h] BYREF
  __int128 v57; // [rsp+88h] [rbp-78h] BYREF
  __int128 v58; // [rsp+98h] [rbp-68h]
  __int128 v59; // [rsp+A8h] [rbp-58h]
  __int128 v60; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v61; // [rsp+C8h] [rbp-38h]
  __int128 v62; // [rsp+D8h] [rbp-28h]
  __int128 v63; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v64; // [rsp+F8h] [rbp-8h]
  _BOOL8 v65; // [rsp+108h] [rbp+8h]
  __int128 v66; // [rsp+110h] [rbp+10h] BYREF
  __int128 v67; // [rsp+120h] [rbp+20h]
  __int128 v68; // [rsp+130h] [rbp+30h]
  __int128 Buf2; // [rsp+140h] [rbp+40h] BYREF

  v51 = 0;
  v56 = 0;
  v55 = 0;
  v44 = 0;
  v54 = 0;
  v53 = 0;
  bstrString = 0;
  Buf2 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v43 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = a1[11];
    if ( !v8 )
      goto LABEL_88;
    v42 = -2147024809;
    v41 = 677;
LABEL_4:
    v9 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v8,
           4,
           L"%s(%d): Result = 0x%X",
           L"CDlpActionWimLayout::DeserializeRoutine",
           v41,
           v42);
    v10 = (unsigned int)v9;
    if ( v9 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
    goto LABEL_88;
  }
  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = a1[11];
    if ( !v8 )
      goto LABEL_88;
    v42 = -2147024809;
    v41 = 679;
    goto LABEL_4;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *))(*a1 + 56LL))(a1, &Buf2);
  v7 = v11;
  if ( v11 < 0 )
  {
    v8 = a1[11];
    if ( !v8 )
      goto LABEL_88;
    v42 = v11;
    v41 = 690;
    goto LABEL_4;
  }
  if ( !memcmp_0(&WINDLP_ACTION_MEDIALAYOUT, &Buf2, 0x10u) )
  {
    v12 = a2 + 8;
    v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v12 + 16LL))(v12, L"MediaPath", &v54);
    v7 = v13;
    if ( v13 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v13;
      v41 = 693;
      goto LABEL_4;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v12 + 16LL))(
            v12,
            L"LayoutPath",
            &v44);
    v7 = v14;
    if ( v14 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v14;
      v41 = 694;
      goto LABEL_4;
    }
    v15 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))v12)(v12, L"PreserveExistingFiles", &v43);
    v7 = v15;
    if ( v15 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v15;
      v41 = 695;
      goto LABEL_4;
    }
  }
  else
  {
    v16 = memcmp_0(&WINDLP_ACTION_MULTILAYOUT, &Buf2, 0x10u) == 0;
    v17 = a2 + 8;
    v18 = *(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v17 + 16LL);
    if ( v16 )
    {
      v19 = v18(v17, L"WimPathX86", &v56);
      v7 = v19;
      if ( v19 < 0 )
      {
        v8 = a1[11];
        if ( !v8 )
          goto LABEL_88;
        v42 = v19;
        v41 = 702;
        goto LABEL_4;
      }
      v20 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v17 + 16LL))(
              v17,
              L"WimPathX64",
              &v55);
      v7 = v20;
      if ( v20 < 0 )
      {
        v8 = a1[11];
        if ( !v8 )
          goto LABEL_88;
        v42 = v20;
        v41 = 703;
        goto LABEL_4;
      }
    }
    else
    {
      v21 = v18(v17, L"WimPath", &v51);
      v7 = v21;
      if ( v21 < 0 )
      {
        v8 = a1[11];
        if ( !v8 )
          goto LABEL_88;
        v42 = v21;
        v41 = 707;
        goto LABEL_4;
      }
    }
    v22 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v17 + 16LL))(
            v17,
            L"LayoutPath",
            &v44);
    v7 = v22;
    if ( v22 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v22;
      v41 = 710;
      goto LABEL_4;
    }
    v23 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))v17)(v17, L"ImageIndex", &v45);
    v7 = v23;
    if ( v23 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v23;
      v41 = 711;
      goto LABEL_4;
    }
    v24 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))v17)(v17, L"CompressionType", &v46);
    v7 = v24;
    if ( v24 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v24;
      v41 = 712;
      goto LABEL_4;
    }
    v25 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))v17)(v17, L"DeleteSource", &v47);
    v7 = v25;
    if ( v25 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v25;
      v41 = 713;
      goto LABEL_4;
    }
    v26 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))v17)(v17, L"CleanTargetPath", &v48);
    v7 = v26;
    if ( v26 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v26;
      v41 = 714;
      goto LABEL_4;
    }
    v27 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))v17)(v17, L"DisableBootSupport", &v49);
    v7 = v27;
    if ( v27 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v27;
      v41 = 715;
      goto LABEL_4;
    }
    v28 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))v17)(v17, L"PreserveExistingFiles", &v43);
    v7 = v28;
    if ( v28 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v28;
      v41 = 716;
      goto LABEL_4;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v17 + 16LL))(v17, L"FPData", &v53);
    if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147023728 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v7;
      v41 = 721;
      goto LABEL_4;
    }
    v29 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v17 + 16LL))(
            v17,
            L"InstallImagePath",
            &bstrString);
    v7 = v29;
    if ( v29 == -2147023728 )
    {
      v7 = 0;
    }
    else if ( v29 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v29;
      v41 = 726;
      goto LABEL_4;
    }
  }
  if ( !memcmp_0(&WINDLP_ACTION_ESDLAYOUT, &Buf2, 0x10u) )
  {
    v57 = Buf2;
    *(_QWORD *)&v58 = v44;
    *((_QWORD *)&v58 + 1) = v45;
    *(_QWORD *)&v59 = v51;
    *((_QWORD *)&v59 + 1) = v46;
    v30 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64))(*a1 + 32LL))(a1, &v57, 48);
    v7 = v30;
    if ( v30 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v30;
      v41 = 742;
      goto LABEL_4;
    }
  }
  else if ( !memcmp_0(&WINDLP_ACTION_UPGLAYOUT, &Buf2, 0x10u) )
  {
    v66 = Buf2;
    *((_QWORD *)&v67 + 1) = v44;
    *(_QWORD *)&v67 = v51;
    *(_QWORD *)&v68 = v53;
    *((_QWORD *)&v68 + 1) = v43 != 0;
    v31 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64))(*a1 + 32LL))(a1, &v66, 48);
    v7 = v31;
    if ( v31 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v31;
      v41 = 755;
      goto LABEL_4;
    }
  }
  else if ( !memcmp_0(&WINDLP_ACTION_WIMLAYOUT, &Buf2, 0x10u) )
  {
    v60 = Buf2;
    *((_QWORD *)&v61 + 1) = v44;
    *(_QWORD *)&v61 = v51;
    LODWORD(v62) = v47 != 0;
    DWORD1(v62) = v48 != 0;
    *((_QWORD *)&v62 + 1) = v49 != 0;
    v32 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64))(*a1 + 32LL))(a1, &v60, 48);
    v7 = v32;
    if ( v32 < 0 )
    {
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_88;
      v42 = v32;
      v41 = 769;
      goto LABEL_4;
    }
  }
  else if ( memcmp_0(&WINDLP_ACTION_MULTILAYOUT, &Buf2, 0x10u) )
  {
    if ( !memcmp_0(&WINDLP_ACTION_MEDIALAYOUT, &Buf2, 0x10u) )
    {
      v63 = Buf2;
      *(_QWORD *)&v64 = v54;
      *((_QWORD *)&v64 + 1) = v44;
      v65 = v43 != 0;
      v33 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64))(*a1 + 32LL))(a1, &v63, 40);
      v7 = v33;
      if ( v33 < 0 )
      {
        v8 = a1[11];
        if ( !v8 )
          goto LABEL_88;
        v42 = v33;
        v41 = 794;
        goto LABEL_4;
      }
    }
  }
  v34 = a1 + 93;
  v35 = a1[93];
  if ( v35 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v35 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *v34 = 0;
  }
  v37 = bstrString;
  if ( bstrString )
  {
    v50 = 0;
    LODWORD(v38) = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(bstrString, &v50);
    if ( (int)v38 < 0
      || (Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v37, v50, v34),
          v38 = (unsigned int)Internal,
          Internal < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v38);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v38);
  }
  *a4 = 0;
LABEL_88:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v53 )
  {
    SysFreeString(v53);
    v53 = 0;
  }
  if ( v54 )
  {
    SysFreeString(v54);
    v54 = 0;
  }
  if ( v44 )
  {
    SysFreeString(v44);
    v44 = 0;
  }
  if ( v55 )
  {
    SysFreeString(v55);
    v55 = 0;
  }
  if ( v56 )
  {
    SysFreeString(v56);
    v56 = 0;
  }
  if ( v51 )
    SysFreeString(v51);
  return v7;
}

```

## disassembly

```asm
0x180012380  push    rbp
0x180012382  push    rbx
0x180012383  push    rsi
0x180012384  push    rdi
0x180012385  push    r12
0x180012387  push    r14
0x180012389  push    r15
0x18001238b  lea     rbp, [rsp-60h]
0x180012390  sub     rsp, 160h
0x180012397  mov     rax, cs:__security_cookie
0x18001239e  xor     rax, rsp
0x1800123a1  mov     [rbp+90h+var_40], rax
0x1800123a5  mov     r14, r9
0x1800123a8  mov     rsi, rdx
0x1800123ab  mov     rbx, rcx
0x1800123ae  xor     r15d, r15d
0x1800123b1  mov     [rsp+190h+var_138], r15
0x1800123b6  mov     [rbp+90h+var_110], r15
0x1800123ba  mov     [rsp+190h+var_118], r15
0x1800123bf  mov     [rsp+190h+var_158], r15
0x1800123c4  mov     [rsp+190h+var_120], r15
0x1800123c9  mov     [rsp+190h+var_128], r15
0x1800123ce  mov     [rsp+190h+bstrString], r15
0x1800123d3  xorps   xmm0, xmm0
0x1800123d6  movups  [rbp+90h+Buf2], xmm0
0x1800123da  mov     [rsp+190h+var_150], r15d
0x1800123df  mov     [rsp+190h+var_14C], r15d
0x1800123e4  mov     [rsp+190h+var_148], r15d
0x1800123e9  mov     [rsp+190h+var_144], r15d
0x1800123ee  mov     [rsp+190h+var_140], r15d
0x1800123f3  mov     [rsp+190h+var_160], r15d
0x1800123f8  movups  [rbp+90h+var_108], xmm0
0x1800123fc  movups  [rbp+90h+var_F8], xmm0
0x180012400  movups  [rbp+90h+var_E8], xmm0
0x180012404  xorps   xmm1, xmm1
0x180012407  movups  [rbp+90h+var_80], xmm1
0x18001240b  movups  [rbp+90h+var_70], xmm1
0x18001240f  movups  [rbp+90h+var_60], xmm1
0x180012413  movups  [rbp+90h+var_D8], xmm0
0x180012417  movups  [rbp+90h+var_C8], xmm0
0x18001241b  movups  [rbp+90h+var_B8], xmm0
0x18001241f  xor     eax, eax
0x180012421  movups  [rbp+90h+var_A8], xmm1
0x180012425  movups  [rbp+90h+var_98], xmm1
0x180012429  mov     [rbp+90h+var_88], rax
0x18001242d  test    rdx, rdx
0x180012430  jnz     short loc_18001247F
0x180012432  mov     eax, 80070057h
0x180012437  mov     edi, eax
0x180012439  mov     rcx, [rcx+58h]
0x18001243d  test    rcx, rcx
0x180012440  jz      loc_180012BB1
0x180012446  mov     [rsp+190h+var_168], eax
0x18001244a  mov     [rsp+190h+var_170], 2A5h
0x180012452  lea     r9, aCdlpactionwiml_18; "CDlpActionWimLayout::DeserializeRoutine"
0x180012459  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180012460  mov     edx, 4
0x180012465  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001246a  test    eax, eax
0x18001246c  mov     ecx, eax
0x18001246e  jns     short loc_180012475
0x180012470  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012475  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001247a  jmp     loc_180012BB1
0x18001247f  test    r14, r14
0x180012482  jnz     short loc_1800124A6
0x180012484  mov     eax, 80070057h
0x180012489  mov     edi, eax
0x18001248b  mov     rcx, [rcx+58h]
0x18001248f  test    rcx, rcx
0x180012492  jz      loc_180012BB1
0x180012498  mov     [rsp+190h+var_168], eax
0x18001249c  mov     [rsp+190h+var_170], 2A7h
0x1800124a4  jmp     short loc_180012452
0x1800124a6  mov     rax, [rcx]
0x1800124a9  lea     rdx, [rbp+90h+Buf2]
0x1800124ad  mov     rax, [rax+38h]
0x1800124b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124b6  mov     edi, eax
0x1800124b8  test    eax, eax
0x1800124ba  jns     short loc_1800124DA
0x1800124bc  mov     rcx, [rbx+58h]
0x1800124c0  test    rcx, rcx
0x1800124c3  jz      loc_180012BB1
0x1800124c9  mov     [rsp+190h+var_168], eax
0x1800124cd  mov     [rsp+190h+var_170], 2B2h
0x1800124d5  jmp     loc_180012452
0x1800124da  mov     r12d, 10h
0x1800124e0  mov     r8d, r12d; Size
0x1800124e3  lea     rdx, [rbp+90h+Buf2]; Buf2
0x1800124e7  lea     rcx, WINDLP_ACTION_MEDIALAYOUT; Buf1
0x1800124ee  call    memcmp_0
0x1800124f3  test    eax, eax
0x1800124f5  jnz     loc_1800125BF
0x1800124fb  add     rsi, 8
0x1800124ff  mov     rax, [rsi]
0x180012502  lea     r8, [rsp+190h+var_120]
0x180012507  lea     rdx, aMediapath; "MediaPath"
0x18001250e  mov     rcx, rsi
0x180012511  mov     rax, [rax+10h]
0x180012515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001251a  mov     edi, eax
0x18001251c  test    eax, eax
0x18001251e  jns     short loc_18001253E
0x180012520  mov     rcx, [rbx+58h]
0x180012524  test    rcx, rcx
0x180012527  jz      loc_180012BB1
0x18001252d  mov     [rsp+190h+var_168], eax
0x180012531  mov     [rsp+190h+var_170], 2B5h
0x180012539  jmp     loc_180012452
0x18001253e  mov     rax, [rsi]
0x180012541  lea     r8, [rsp+190h+var_158]
0x180012546  lea     rdx, aLayoutpath; "LayoutPath"
0x18001254d  mov     rcx, rsi
0x180012550  mov     rax, [rax+10h]
0x180012554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012559  mov     edi, eax
0x18001255b  test    eax, eax
0x18001255d  jns     short loc_18001257D
0x18001255f  mov     rcx, [rbx+58h]
0x180012563  test    rcx, rcx
0x180012566  jz      loc_180012BB1
0x18001256c  mov     [rsp+190h+var_168], eax
0x180012570  mov     [rsp+190h+var_170], 2B6h
0x180012578  jmp     loc_180012452
0x18001257d  mov     rax, [rsi]
0x180012580  lea     r8, [rsp+190h+var_160]
0x180012585  lea     rdx, aPreserveexisti; "PreserveExistingFiles"
0x18001258c  mov     rcx, rsi
0x18001258f  mov     rax, [rax]
0x180012592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012597  mov     edi, eax
0x180012599  test    eax, eax
0x18001259b  jns     loc_1800128BD
0x1800125a1  mov     rcx, [rbx+58h]
0x1800125a5  test    rcx, rcx
0x1800125a8  jz      loc_180012BB1
0x1800125ae  mov     [rsp+190h+var_168], eax
0x1800125b2  mov     [rsp+190h+var_170], 2B7h
0x1800125ba  jmp     loc_180012452
0x1800125bf  mov     r8, r12; Size
0x1800125c2  lea     rdx, [rbp+90h+Buf2]; Buf2
0x1800125c6  lea     rcx, WINDLP_ACTION_MULTILAYOUT; Buf1
0x1800125cd  call    memcmp_0
0x1800125d2  test    eax, eax
0x1800125d4  setz    cl
0x1800125d7  add     rsi, 8
0x1800125db  mov     rax, [rsi]
0x1800125de  mov     rax, [rax+10h]
0x1800125e2  test    cl, cl
0x1800125e4  mov     rcx, rsi
0x1800125e7  jz      short loc_18001265C
0x1800125e9  lea     r8, [rbp+90h+var_110]
0x1800125ed  lea     rdx, aWimpathx86; "WimPathX86"
0x1800125f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125f9  mov     edi, eax
0x1800125fb  test    eax, eax
0x1800125fd  jns     short loc_18001261D
0x1800125ff  mov     rcx, [rbx+58h]
0x180012603  test    rcx, rcx
0x180012606  jz      loc_180012BB1
0x18001260c  mov     [rsp+190h+var_168], eax
0x180012610  mov     [rsp+190h+var_170], 2BEh
0x180012618  jmp     loc_180012452
0x18001261d  mov     rax, [rsi]
0x180012620  lea     r8, [rsp+190h+var_118]
0x180012625  lea     rdx, aWimpathx64; "WimPathX64"
0x18001262c  mov     rcx, rsi
0x18001262f  mov     rax, [rax+10h]
0x180012633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012638  mov     edi, eax
0x18001263a  test    eax, eax
0x18001263c  jns     short loc_180012691
0x18001263e  mov     rcx, [rbx+58h]
0x180012642  test    rcx, rcx
0x180012645  jz      loc_180012BB1
0x18001264b  mov     [rsp+190h+var_168], eax
0x18001264f  mov     [rsp+190h+var_170], 2BFh
0x180012657  jmp     loc_180012452
0x18001265c  lea     r8, [rsp+190h+var_138]
0x180012661  lea     rdx, aWimpath; "WimPath"
0x180012668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001266d  mov     edi, eax
0x18001266f  test    eax, eax
0x180012671  jns     short loc_180012691
0x180012673  mov     rcx, [rbx+58h]
0x180012677  test    rcx, rcx
0x18001267a  jz      loc_180012BB1
0x180012680  mov     [rsp+190h+var_168], eax
0x180012684  mov     [rsp+190h+var_170], 2C3h
0x18001268c  jmp     loc_180012452
0x180012691  mov     rax, [rsi]
0x180012694  lea     r8, [rsp+190h+var_158]
0x180012699  lea     rdx, aLayoutpath; "LayoutPath"
0x1800126a0  mov     rcx, rsi
0x1800126a3  mov     rax, [rax+10h]
0x1800126a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126ac  mov     edi, eax
0x1800126ae  test    eax, eax
0x1800126b0  jns     short loc_1800126D0
0x1800126b2  mov     rcx, [rbx+58h]
0x1800126b6  test    rcx, rcx
0x1800126b9  jz      loc_180012BB1
0x1800126bf  mov     [rsp+190h+var_168], eax
0x1800126c3  mov     [rsp+190h+var_170], 2C6h
0x1800126cb  jmp     loc_180012452
0x1800126d0  mov     rax, [rsi]
0x1800126d3  lea     r8, [rsp+190h+var_150]
0x1800126d8  lea     rdx, aImageindex; "ImageIndex"
0x1800126df  mov     rcx, rsi
0x1800126e2  mov     rax, [rax]
0x1800126e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126ea  mov     edi, eax
0x1800126ec  test    eax, eax
0x1800126ee  jns     short loc_18001270E
0x1800126f0  mov     rcx, [rbx+58h]
0x1800126f4  test    rcx, rcx
0x1800126f7  jz      loc_180012BB1
0x1800126fd  mov     [rsp+190h+var_168], eax
0x180012701  mov     [rsp+190h+var_170], 2C7h
0x180012709  jmp     loc_180012452
0x18001270e  mov     rax, [rsi]
0x180012711  lea     r8, [rsp+190h+var_14C]
0x180012716  lea     rdx, aCompressiontyp; "CompressionType"
0x18001271d  mov     rcx, rsi
0x180012720  mov     rax, [rax]
0x180012723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012728  mov     edi, eax
0x18001272a  test    eax, eax
0x18001272c  jns     short loc_18001274C
0x18001272e  mov     rcx, [rbx+58h]
0x180012732  test    rcx, rcx
0x180012735  jz      loc_180012BB1
0x18001273b  mov     [rsp+190h+var_168], eax
0x18001273f  mov     [rsp+190h+var_170], 2C8h
0x180012747  jmp     loc_180012452
0x18001274c  mov     rax, [rsi]
0x18001274f  lea     r8, [rsp+190h+var_148]
0x180012754  lea     rdx, aDeletesource; "DeleteSource"
0x18001275b  mov     rcx, rsi
0x18001275e  mov     rax, [rax]
0x180012761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012766  mov     edi, eax
0x180012768  test    eax, eax
0x18001276a  jns     short loc_18001278A
0x18001276c  mov     rcx, [rbx+58h]
0x180012770  test    rcx, rcx
0x180012773  jz      loc_180012BB1
0x180012779  mov     [rsp+190h+var_168], eax
0x18001277d  mov     [rsp+190h+var_170], 2C9h
0x180012785  jmp     loc_180012452
0x18001278a  mov     rax, [rsi]
0x18001278d  lea     r8, [rsp+190h+var_144]
0x180012792  lea     rdx, aCleantargetpat; "CleanTargetPath"
0x180012799  mov     rcx, rsi
0x18001279c  mov     rax, [rax]
0x18001279f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127a4  mov     edi, eax
0x1800127a6  test    eax, eax
0x1800127a8  jns     short loc_1800127C8
0x1800127aa  mov     rcx, [rbx+58h]
0x1800127ae  test    rcx, rcx
0x1800127b1  jz      loc_180012BB1
0x1800127b7  mov     [rsp+190h+var_168], eax
0x1800127bb  mov     [rsp+190h+var_170], 2CAh
0x1800127c3  jmp     loc_180012452
0x1800127c8  mov     rax, [rsi]
0x1800127cb  lea     r8, [rsp+190h+var_140]
0x1800127d0  lea     rdx, aDisablebootsup; "DisableBootSupport"
0x1800127d7  mov     rcx, rsi
0x1800127da  mov     rax, [rax]
0x1800127dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127e2  mov     edi, eax
0x1800127e4  test    eax, eax
0x1800127e6  jns     short loc_180012806
0x1800127e8  mov     rcx, [rbx+58h]
0x1800127ec  test    rcx, rcx
0x1800127ef  jz      loc_180012BB1
0x1800127f5  mov     [rsp+190h+var_168], eax
0x1800127f9  mov     [rsp+190h+var_170], 2CBh
0x180012801  jmp     loc_180012452
0x180012806  mov     rax, [rsi]
0x180012809  lea     r8, [rsp+190h+var_160]
0x18001280e  lea     rdx, aPreserveexisti; "PreserveExistingFiles"
0x180012815  mov     rcx, rsi
0x180012818  mov     rax, [rax]
0x18001281b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012820  mov     edi, eax
0x180012822  test    eax, eax
0x180012824  jns     short loc_180012844
0x180012826  mov     rcx, [rbx+58h]
0x18001282a  test    rcx, rcx
0x18001282d  jz      loc_180012BB1
0x180012833  mov     [rsp+190h+var_168], eax
0x180012837  mov     [rsp+190h+var_170], 2CCh
0x18001283f  jmp     loc_180012452
0x180012844  mov     rax, [rsi]
0x180012847  lea     r8, [rsp+190h+var_128]
0x18001284c  lea     rdx, aFpdata; "FPData"
0x180012853  mov     rcx, rsi
  ... truncated ...
```
