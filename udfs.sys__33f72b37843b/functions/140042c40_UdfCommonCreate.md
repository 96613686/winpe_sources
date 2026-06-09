# UdfCommonCreate

- ea: `0x140042c40`
- end: `0x14004412e`
- name: `UdfCommonCreate`
- size: `5358`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `26`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x140004340`
- `0x140009014`
- `0x140009148`
- `0x14000a7f8`
- `0x14000c574`
- `0x14000ca10`
- `0x14000cad4`
- `0x14001bc30`
- `0x14001bd80`
- `0x14001c080`
- `0x14002e4fc`
- `0x14002fac4`
- `0x140031144`
- `0x1400312c0`
- `0x140041900`
- `0x140042c40`
- `0x140044134`
- `0x1400444c4`
- `0x140044950`
- `0x140050224`
- `0x140050ce0`
- `0x140050ee0`
- `0x1400537b0`
- `0x140054460`
- `0x1400567cc`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x140043dd2`
- `ntoskrnl!CcUnpinData` at `0x140043dd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043dad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043dad`
- `ntoskrnl!ExRaiseStatus` at `0x140043938`
- `ntoskrnl!ExRaiseStatus` at `0x140043952`
- `ntoskrnl!ExRaiseStatus` at `0x140043f6b`
- `ntoskrnl!ExRaiseStatus` at `0x1400440c0`
- `ntoskrnl!ExRaiseStatus` at `0x140043938`
- `ntoskrnl!ExRaiseStatus` at `0x140043952`
- `ntoskrnl!ExRaiseStatus` at `0x140043f6b`
- `ntoskrnl!ExRaiseStatus` at `0x1400440c0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140042e95`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140042e95`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043e42`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043e55`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059fdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059ff6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043e42`
- `ntoskrnl!ExReleaseResourceLite` at `0x140043e55`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059fdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059ff6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140042f5a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140043605`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140043f15`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140042f5a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140043605`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140043f15`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140043b54`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140043f53`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140043b54`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140043f53`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140043135`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140043135`
- `ntoskrnl!FsRtlLegalAnsiCharacterArray` at `0x1400431f2`

## pseudocode

```c
__int64 __fastcall UdfCommonCreate(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 v5; // r8
  unsigned int v6; // eax
  int v7; // r15d
  char v8; // cl
  char v9; // r11
  int v10; // r9d
  __int64 v11; // r13
  int v12; // edx
  int v13; // r14d
  struct _UNICODE_STRING *v14; // rsi
  __int64 v15; // rbx
  _WORD *v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rsi
  __int64 v19; // r12
  int v20; // eax
  int NewFile; // ebx
  char v22; // di
  __int64 v23; // r14
  __int64 v24; // r8
  char DirEntry; // r12
  struct _ERESOURCE *v26; // rcx
  BOOLEAN v27; // dl
  unsigned __int16 v28; // si
  char v29; // r15
  __int64 Prefix; // r8
  __int64 v31; // rdx
  _WORD *v32; // r8
  _WORD *v33; // rdi
  char v34; // r15
  unsigned int v35; // edx
  unsigned int v36; // ecx
  unsigned int v37; // r14d
  __int64 v38; // r14
  ULONG v39; // esi
  unsigned __int16 *v40; // r9
  unsigned int v41; // eax
  char v42; // r8
  __int64 v43; // rdi
  const void **p_DestinationString; // rdi
  char v45; // cl
  char v46; // r10
  __int64 i; // r8
  unsigned __int64 v48; // rcx
  ULONG v49; // eax
  ULONG v50; // ebx
  struct _ERESOURCE *v51; // rcx
  BOOLEAN v52; // dl
  __int64 v53; // r8
  int v54; // eax
  int v55; // edx
  int v56; // edi
  __int64 v57; // rax
  __int64 v58; // r12
  __int64 v59; // rsi
  unsigned int v61; // edi
  __int64 v62; // rcx
  __int64 v63; // r11
  int v64; // [rsp+88h] [rbp-298h]
  PUNICODE_STRING v65; // [rsp+90h] [rbp-290h]
  int v66; // [rsp+90h] [rbp-290h]
  int v67; // [rsp+A0h] [rbp-280h]
  char v68; // [rsp+C8h] [rbp-258h] BYREF
  unsigned __int8 v69; // [rsp+C9h] [rbp-257h]
  int v70; // [rsp+CCh] [rbp-254h]
  char v71; // [rsp+D0h] [rbp-250h]
  __int64 v72; // [rsp+D8h] [rbp-248h]
  int v73[2]; // [rsp+E0h] [rbp-240h] BYREF
  char v74; // [rsp+E8h] [rbp-238h]
  ULONG v75; // [rsp+ECh] [rbp-234h]
  char v76; // [rsp+F0h] [rbp-230h]
  char v77; // [rsp+F1h] [rbp-22Fh]
  char v78; // [rsp+F3h] [rbp-22Dh]
  char v79; // [rsp+F4h] [rbp-22Ch]
  unsigned int v80; // [rsp+F8h] [rbp-228h]
  __int64 v81[2]; // [rsp+100h] [rbp-220h] BYREF
  __int16 v82; // [rsp+110h] [rbp-210h]
  int v83[2]; // [rsp+118h] [rbp-208h] BYREF
  int v84[2]; // [rsp+120h] [rbp-200h]
  __int64 v85; // [rsp+128h] [rbp-1F8h] BYREF
  unsigned int v86; // [rsp+130h] [rbp-1F0h]
  int v87; // [rsp+134h] [rbp-1ECh]
  __int64 v88; // [rsp+138h] [rbp-1E8h] BYREF
  int v89[2]; // [rsp+140h] [rbp-1E0h]
  char v90; // [rsp+148h] [rbp-1D8h]
  char v91; // [rsp+150h] [rbp-1D0h]
  void *Src[2]; // [rsp+158h] [rbp-1C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+168h] [rbp-1B8h] BYREF
  int v94; // [rsp+178h] [rbp-1A8h]
  int v95; // [rsp+17Ch] [rbp-1A4h]
  __int64 v96; // [rsp+180h] [rbp-1A0h]
  __int64 v97; // [rsp+188h] [rbp-198h]
  _WORD *v98; // [rsp+190h] [rbp-190h]
  unsigned __int16 *v99; // [rsp+198h] [rbp-188h]
  __int64 v100; // [rsp+1A0h] [rbp-180h]
  int v101; // [rsp+1A8h] [rbp-178h]
  int v102; // [rsp+1ACh] [rbp-174h]
  int v103; // [rsp+1B0h] [rbp-170h]
  __int64 v104; // [rsp+1B8h] [rbp-168h]
  __int64 v105; // [rsp+1C0h] [rbp-160h]
  __int64 v106; // [rsp+1C8h] [rbp-158h]
  union _LARGE_INTEGER FileOffset[22]; // [rsp+1D8h] [rbp-148h] BYREF
  char v108; // [rsp+288h] [rbp-98h] BYREF

  v2 = a2;
  v96 = a2;
  v3 = a1;
  *(_QWORD *)v89 = a1;
  v100 = a1;
  v105 = a2;
  v4 = *(_QWORD *)(a2 + 184);
  *(_QWORD *)v84 = v4;
  memset(FileOffset, 0, 0x98u);
  v68 = 0;
  v88 = 0;
  *(_QWORD *)v73 = 0;
  *(_QWORD *)v83 = 0;
  *(_OWORD *)v81 = 0;
  *(_OWORD *)Src = 0;
  DestinationString = 0;
  v5 = *(_QWORD *)(v3 + 16);
  v72 = v5;
  if ( !v5 )
  {
    UdfCompleteRequest(v3, v2, 0);
    return 0;
  }
  v6 = *(_DWORD *)(v4 + 16);
  v80 = v6;
  v75 = HIBYTE(v6);
  v7 = v6 & 0x2000;
  v8 = *(_BYTE *)(v4 + 2);
  v69 = v8 >= 0;
  v9 = v8 & 4;
  v71 = v8 & 4;
  v10 = v6 & 0x1000;
  v87 = v10;
  v106 = v5;
  v11 = *(_QWORD *)(v5 + 288);
  v85 = v11;
  v12 = *(_DWORD *)(v5 + 48);
  if ( (v12 & 0x90) != 0 )
  {
    if ( ((HIBYTE(v6) - 1) & 0xFFFFFFFD) != 0 || v9 || (v6 & 0x1000) != 0 )
    {
      if ( (v12 & 0x80u) != 0 )
      {
        IoSetHardErrorOrVerifyDevice(*(PIRP *)(v3 + 8), *(PDEVICE_OBJECT *)(*(_QWORD *)(v5 + 8) + 16LL));
        *(_DWORD *)(v3 + 24) = -1073741662;
        ExRaiseStatus(-1073741662);
      }
      v61 = -1073739770;
      if ( (v12 & 0x20) == 0 )
        v61 = -1073741790;
      UdfCompleteRequest(v3, v2, v61);
      return v61;
    }
    v6 = v80;
  }
  if ( v10 && (v9 || v7) )
    goto LABEL_257;
  if ( *(_DWORD *)(v4 + 32) || *(_QWORD *)(v2 + 24) )
  {
    UdfCompleteRequest(v3, v2, 3221225551LL);
    return 3221225551LL;
  }
  if ( (v8 & 2) != 0 )
  {
    UdfCompleteRequest(v3, v2, 3221225659LL);
    return 3221225659LL;
  }
  if ( (v6 & 0x10000) != 0 )
    goto LABEL_257;
  v13 = 0;
  v14 = 0;
  v82 = *(_WORD *)(v4 + 24);
  v15 = *(_QWORD *)(v4 + 48);
  v16 = (_WORD *)(v15 + 88);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
  {
    WPP_SF_Z(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      10,
      WPP_962a5ab0fb873cc757a84452495a3943_Traceguids,
      v15 + 88);
  }
  v17 = *(_QWORD *)(v15 + 64);
  if ( v17 && !v7 )
  {
    *(_QWORD *)(v15 + 16) = *(_QWORD *)(v17 + 16);
    v13 = UdfDecodeFileObject(v17, &v85, &v88);
    if ( v13 >= 2 )
    {
      v14 = (struct _UNICODE_STRING *)(v62 + 88);
      if ( *(_QWORD *)&WPP_GLOBAL_Control != v63 && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
        WPP_SF_Z(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          11,
          WPP_962a5ab0fb873cc757a84452495a3943_Traceguids,
          v14);
      v11 = v85;
      goto LABEL_16;
    }
    v3 = *(_QWORD *)v89;
    v2 = v96;
LABEL_257:
    UdfCompleteRequest(v3, v2, 3221225485LL);
    return 3221225485LL;
  }
LABEL_16:
  v65 = v14;
  v18 = v72;
  v19 = *(_QWORD *)v89;
  v20 = UdfNormalizeFileNames(v89[0], v72, v7 != 0, v13, v88, (__int64)v65, v15 + 88, (__int64)v81);
  NewFile = v20;
  v70 = v20;
  if ( v20 < 0 )
  {
    UdfCompleteRequest(v19, v96, (unsigned int)v20);
    return (unsigned int)NewFile;
  }
  if ( v88 && LOWORD(v81[0]) && *(_WORD *)v81[1] == 58 )
    *(_QWORD *)v83 = *(_QWORD *)(v88 + 16);
  if ( *v16 || v13 > 2 || v7 )
  {
    v22 = 0;
    v23 = *(_QWORD *)v89;
    if ( ExAcquireResourceSharedLite((PERESOURCE)(v72 + 1480), (*(_DWORD *)(*(_QWORD *)v89 + 28LL) & 4) != 0) )
      goto LABEL_20;
LABEL_254:
    *(_DWORD *)(v23 + 24) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  v23 = *(_QWORD *)v89;
  if ( !ExAcquireResourceExclusiveLite((PERESOURCE)(v72 + 1480), (*(_DWORD *)(*(_QWORD *)v89 + 28LL) & 4) != 0) )
    goto LABEL_254;
  v22 = 1;
LABEL_20:
  v74 = 0;
  DirEntry = 0;
  v77 = 0;
  v85 = 0;
  LOBYTE(v80) = v80 & 1;
  v95 = v82 & 0xFF7F;
  *(_DWORD *)&DestinationString.Length = 6291456;
  DestinationString.Buffer = (PWSTR)&v108;
  *(_QWORD *)(v96 + 56) = 0;
  UdfVerifyVcb(v23, v18, v24);
  if ( (*(_DWORD *)(v18 + 48) & 1) != 0 )
  {
    NewFile = -1073741790;
    v70 = -1073741790;
    v43 = v72;
    goto LABEL_211;
  }
  if ( v7 )
  {
    if ( ((v75 - 1) & 0xFFFFFFFD) != 0 )
    {
      NewFile = -1073741790;
      v70 = -1073741790;
    }
    else
    {
      NewFile = UdfOpenObjectByFileId(v23, v84[0], v18, v75);
      v70 = NewFile;
    }
    v43 = v72;
    goto LABEL_211;
  }
  if ( v22 )
  {
    v50 = v75;
    if ( ((v75 - 1) & 0xFFFFFFFD) != 0 )
    {
      NewFile = -1073741790;
    }
    else
    {
      if ( (_BYTE)v80 || v71 )
        goto LABEL_106;
      if ( v87 )
      {
        NewFile = -1073741535;
      }
      else
      {
        v51 = (struct _ERESOURCE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v18 + 280) + 136LL) + 80LL) + 8LL);
        v52 = 0;
        v78 = 0;
        if ( (*(_DWORD *)(v23 + 28) & 4) != 0 )
        {
          v52 = 1;
          v78 = 1;
        }
        if ( !ExAcquireResourceExclusiveLite(v51, v52) )
        {
          *(_DWORD *)(v23 + 24) = -1073741608;
          ExRaiseStatus(-1073741608);
        }
        v53 = *(_QWORD *)(v18 + 280);
        *(_QWORD *)v73 = v53;
        v90 = 0;
        v103 = 2;
        FileOffset[20].QuadPart = 0;
        v102 = 0;
        if ( (*(_DWORD *)(*(_QWORD *)(v23 + 16) + 48LL) & 0x10) == 0 )
          goto LABEL_117;
        NewFile = -1073741790;
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v84 + 8LL) + 16LL) & 0x50040) == 0 )
        {
          v50 = v75;
LABEL_117:
          if ( **(_WORD **)v73 != 2355 || (v50 & 0xFFFFFFFA) != 0 || v50 == 1 )
          {
            NewFile = UdfCompleteScbOpen(
                        v23,
                        v84[0],
                        *(_QWORD *)(*(_QWORD *)(v53 + 136) + 8LL),
                        (int)v73,
                        0,
                        0,
                        2u,
                        0,
                        v50,
                        0);
            v70 = NewFile;
            v43 = v72;
          }
          else
          {
            NewFile = -1073741771;
            v70 = -1073741771;
            v43 = v72;
          }
          goto LABEL_211;
        }
      }
    }
LABEL_59:
    v70 = NewFile;
LABEL_60:
    v43 = v72;
    goto LABEL_211;
  }
  v26 = (struct _ERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v11 + 136) + 80LL) + 8LL);
  v27 = 0;
  v79 = 0;
  if ( (*(_DWORD *)(v23 + 28) & 4) != 0 )
  {
    v27 = 1;
    v79 = 1;
  }
  if ( !ExAcquireResourceExclusiveLite(v26, v27) )
  {
    *(_DWORD *)(v23 + 24) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  *(_QWORD *)v73 = v11;
  v28 = v81[0];
  v29 = v69;
  if ( LOWORD(v81[0]) )
  {
    Prefix = UdfFindPrefix(v23, v69, (int)v73, (int)v83, (__int64)v81, &DestinationString, (__int64)&v68);
    v85 = Prefix;
    v104 = Prefix;
    v28 = v81[0];
  }
  else
  {
    Prefix = v85;
  }
  if ( Prefix || !v88 )
  {
    v31 = *(_QWORD *)v83;
  }
  else
  {
    Prefix = *(_QWORD *)(v88 + 16);
    v85 = Prefix;
    v104 = Prefix;
    v31 = *(_QWORD *)(v88 + 24);
    *(_QWORD *)v83 = v31;
  }
  if ( Prefix && (*(_DWORD *)(Prefix + 68) & 2) != 0 )
  {
    NewFile = -1073741738;
    goto LABEL_59;
  }
  if ( *(int *)(*(_QWORD *)v73 + 216LL) >= 2 )
  {
    NewFile = -1073741672;
    if ( *(_DWORD *)(*(_QWORD *)v73 + 216LL) != 2 )
      NewFile = -1073741566;
    v70 = NewFile;
    v43 = v72;
    goto LABEL_211;
  }
  if ( !v28 )
  {
    if ( v71 && (*(_DWORD *)(*(_QWORD *)v73 + 212LL) & 0x18) != 0 )
    {
      NewFile = -1073741811;
      goto LABEL_59;
    }
    if ( **(_WORD **)v73 != 2356 )
    {
      if ( (*(_DWORD *)(*(_QWORD *)v84 + 16LL) & 0x40) != 0 )
      {
        NewFile = -1073741638;
        v70 = -1073741638;
        v43 = v72;
        goto LABEL_211;
      }
      v43 = v72;
      if ( v75 == 2 )
      {
        NewFile = -1073741771;
        v70 = -1073741771;
        goto LABEL_211;
      }
      if ( *(_QWORD *)v73 == *(_QWORD *)(v72 + 288) )
      {
        if ( v71 )
        {
          NewFile = -1073741811;
          v70 = -1073741811;
          goto LABEL_211;
        }
        if ( v87 )
        {
          NewFile = -1073741535;
          v70 = -1073741535;
          goto LABEL_211;
        }
      }
      NewFile = UdfOpenExistingScb(v23, v84[0], (unsigned int)v73, Prefix, 0, 3u, v29, v68, 1, v88, v75);
      v70 = NewFile;
      goto LABEL_211;
    }
    if ( (*(_DWORD *)(v23 + 28) & 0x20000000) == 0 && !(_BYTE)v80 )
    {
      if ( v75 != 2 )
      {
        v54 = UdfOpenExistingScb(v23, v84[0], (unsigned int)v73, Prefix, v31, 4u, v29, v68, 1, v88, v75);
LABEL_138:
        NewFile = v54;
        v70 = v54;
        v43 = v72;
        goto LABEL_211;
      }
      NewFile = -1073741771;
      goto LABEL_59;
    }
LABEL_106:
    NewFile = -1073741565;
    v70 = -1073741565;
    v43 = v72;
    goto LABEL_211;
  }
  v97 = Prefix;
  if ( (*(_DWORD *)(v23 + 28) & 4) == 0 )
    UdfRaiseStatusEx(v23, 3221225688LL, 0);
  memset(FileOffset, 0, 0x98u);
  v74 = 1;
  v32 = (_WORD *)v81[1];
  while ( 1 )
  {
    v68 = 0;
    v86 = 0;
    v33 = v32;
    v98 = v32;
    if ( v28 && *v32 == 58 )
    {
      v34 = 1;
      v33 = v32 + 1;
      v98 = v32 + 1;
      v28 -= 2;
      LOWORD(v81[0]) = v28;
      v81[1] = (__int64)++v32;
    }
    else
    {
      v34 = 0;
    }
    v35 = 0;
    v36 = 0;
    v37 = 0;
    while ( 1 )
    {
      v86 = v35;
      if ( v36 >= v28 || *v33 == 92 || *v33 == 58 )
        break;
      v35 = v36 + 2;
      v37 = v36 + 2;
      v98 = ++v33;
      v36 += 2;
    }
    WORD1(Src[0]) = v35;
    LOWORD(Src[0]) = v35;
    Src[1] = v32;
    UdfEnsureStringBufferEnough(&DestinationString);
    memmove(DestinationString.Buffer, Src[1], LOWORD(Src[0]));
    DestinationString.Length = (USHORT)Src[0];
    RtlUpcaseUnicodeString(&DestinationString, &DestinationString, 0);
    if ( v37 == LOWORD(v81[0]) )
    {
      LOWORD(v81[0]) = 0;
    }
    else
    {
      if ( *v33 != 58 )
      {
        v37 += 2;
        v86 = v37;
      }
      WORD1(v81[0]) -= v37;
      LOWORD(v81[0]) -= v37;
      v81[1] += v37;
    }
    if ( (*(_DWORD *)(*(_QWORD *)v73 + 212LL) & 0x10) != 0 )
    {
      NewFile = -1073741811;
      v70 = -1073741811;
      v43 = v72;
      goto LABEL_211;
    }
    v38 = *(_QWORD *)v89;
    if ( !v34 )
    {
      v39 = v75;
      goto LABEL_48;
    }
    UdfValidateAndRemoveStreamSuffix(*(__int64 *)v89, Src, (UNICODE_STRING *)v81);
    if ( !LOWORD(Src[0]) )
      break;
    if ( v71 )
    {
      NewFile = -1073741811;
      goto LABEL_59;
    }
    v39 = v75;
    NewFile = UdfOpenStreamDirectory(v38, *(__int64 *)v73, v75);
    v70 = NewFile;
    if ( NewFile < 0 )
      goto LABEL_60;
    *(_QWORD *)v73 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v73 + 136LL) + 24LL);
LABEL_48:
    v99 = 0;
    if ( !LOWORD(Src[0]) || ((__int64)Src[0] & 1) != 0 )
    {
LABEL_58:
      NewFile = -1073741773;
      goto LABEL_59;
    }
    v40 = (unsigned __int16 *)Src[1];
    v99 = (unsigned __int16 *)Src[1];
    while ( v40 < (unsigned __int16 *)((char *)Src[1] + LOWORD(Src[0])) )
    {
      v41 = *v40;
      v82 = *v40;
      v42 = 20;
      if ( !v34 )
        v42 = 2;
      if ( (unsigned __int16)v41 < 0xFFu
        && (v41 & 0x80u) == 0
        && ((unsigned __int8)v42 & *((_BYTE *)FsRtlLegalAnsiCharacterArray + v41)) == 0 )
      {
        goto LABEL_58;
      }
      v99 = ++v40;
    }
    if ( v34 )
    {
      if ( LOWORD(Src[0]) >= 8u
        && *(_WORD *)Src[1] == 42
        && *((_WORD *)Src[1] + 1) == 85
        && *((_WORD *)Src[1] + 2) == 68
        && *((_WORD *)Src[1] + 3) == 70 )
      {
        goto LABEL_58;
      }
      if ( (*(_DWORD *)(*(_QWORD *)v73 + 212LL) & 8) == 0 )
      {
LABEL_71:
        NewFile = -1073741766;
        v70 = -1073741766;
        v43 = v72;
        goto LABEL_211;
      }
    }
    else if ( **(_WORD **)v73 != 2355 )
    {
      goto LABEL_71;
    }
    p_DestinationString = (const void **)Src;
    if ( v69 )
      p_DestinationString = (const void **)&DestinationString;
    DirEntry = UdfFindDirEntry(v38, *(__int64 *)v73, p_DestinationString, v69, 0, 0, (union _LARGE_INTEGER)FileOffset);
    v76 = DirEntry;
    if ( DirEntry )
    {
      if ( (*(_DWORD *)(*(_QWORD *)v73 + 212LL) & 8) != 0 && (*(_BYTE *)(FileOffset[4].QuadPart + 18) & 2) != 0 )
      {
        NewFile = -1073741566;
        v70 = -1073741566;
        goto LABEL_60;
      }
LABEL_68:
      v45 = v68;
      goto LABEL_69;
    }
    if ( v34 )
      goto LABEL_68;
    v94 = 0;
    if ( (unsigned __int16)(LOWORD(Src[0]) - 8) > 0x10u )
      goto LABEL_68;
    v46 = 0;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v94 = i;
      v48 = ((unsigned __int64)LOWORD(Src[0]) >> 1) - 4;
      if ( (unsigned int)i > v48 )
        break;
      if ( *((_WORD *)Src[1] + i) == 35 && ((unsigned int)i == v48 || *((_WORD *)Src[1] + (unsigned int)(i + 4)) == 46) )
      {
        v46 = 1;
        break;
      }
    }
    if ( !v46 )
      goto LABEL_68;
    DirEntry = UdfFindDirEntry(v38, *(__int64 *)v73, p_DestinationString, v69, 1, 1, (union _LARGE_INTEGER)FileOffset);
    v76 = DirEntry;
    v45 = DirEntry;
    v68 = DirEntry;
LABEL_69:
    if ( DirEntry )
    {
      v43 = v72;
    }
    else
    {
      if ( LOWORD(v81[0]) )
        goto LABEL_71;
      if ( v71 )
      {
        v54 = UdfOpenExistingScb(v38, v84[0], (unsigned int)v73, v85, 0, 3u, v69, v45, 0, v88, v39);
        goto LABEL_138;
      }
      if ( v39 == 1 || v39 == 4 )
      {
        NewFile = -1073741772;
        v70 = -1073741772;
        v43 = v72;
        goto LABEL_211;
      }
      v43 = v72;
      v55 = *(_DWORD *)(v72 + 48);
      if ( (v55 & 0x80u) != 0 )
      {
        IoSetHardErrorOrVerifyDevice(*(PIRP *)(v38 + 8), *(PDEVICE_OBJECT *)(*(_QWORD *)(v72 + 8) + 16LL));
        UdfRaiseStatusEx(v38, 3221225634LL, 0);
      }
      if ( (v55 & 0x10) != 0 || (*(_DWORD *)(*(_QWORD *)v73 + 212LL) & 0x8000) != 0 )
        goto LABEL_92;
      if ( v87 && (v95 & 1) != 0 )
      {
        v56 = -1073739770;
        if ( (v55 & 0x20) == 0 )
          v56 = -1073741535;
        NewFile = v56;
        goto LABEL_59;
      }
      NewFile = UdfCreateNewFile(v38, v73[0], (int)FileOffset, (__int64)Src, v80, v34, v95);
      v70 = NewFile;
      if ( NewFile < 0 )
        goto LABEL_60;
      v49 = 2;
      v75 = 2;
      v101 = 2;
      DirEntry = 1;
      v76 = 1;
      v77 = 1;
      v91 = 1;
      if ( !v34 )
      {
        v45 = v68;
        goto LABEL_95;
      }
      *(_QWORD *)v83 = v97;
      v45 = v68;
    }
    v49 = v75;
LABEL_95:
    v28 = v81[0];
    if ( !LOWORD(v81[0]) )
      goto LABEL_86;
    if ( LOWORD(v81[0]) > 1u && (v32 = (_WORD *)v81[1], *(_WORD *)v81[1] == 58) && *(_WORD *)(v81[1] + 2) == 58 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
      {
        WPP_SF_Z(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          13,
          WPP_962a5ab0fb873cc757a84452495a3943_Traceguids,
          v81);
        goto LABEL_99;
      }
    }
    else
    {
      LOBYTE(v67) = 0;
      LOBYTE(v66) = v69;
      LOBYTE(v64) = v45;
      NewFile = UdfOpenObjectFromDirContext(v38, *(_QWORD *)v84, v43, v73, v64, v66, FileOffset, v67, 0, v83, v49);
      v70 = NewFile;
      if ( NewFile < 0 )
        goto LABEL_60;
      v97 = *(_QWORD *)v83;
LABEL_99:
      v28 = v81[0];
      v32 = (_WORD *)v81[1];
    }
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 12, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids);
  }
LABEL_86:
  if ( !DirEntry )
    goto LABEL_60;
  if ( ((*(_DWORD *)(v38 + 28) & 0x20000000) != 0 || (_BYTE)v80) && (*(_BYTE *)(FileOffset[4].QuadPart + 18) & 2) == 0 )
    goto LABEL_106;
  if ( (*(_DWORD *)(*(_QWORD *)v84 + 16LL) & 0x40) != 0 && (*(_BYTE *)(FileOffset[4].QuadPart + 18) & 2) != 0 )
  {
    NewFile = -1073741638;
    goto LABEL_59;
  }
  if ( !v77 && (v75 == 2 || (*(_BYTE *)(FileOffset[4].QuadPart + 18) & 2) != 0 && ((v75 - 1) & 0xFFFFFFFD) != 0) )
  {
    NewFile = -1073741771;
    goto LABEL_59;
  }
  v43 = v72;
  if ( (*(_BYTE *)(FileOffset[4].QuadPart + 18) & 0x10) != 0 )
  {
LABEL_92:
    NewFile = -1073741790;
    v70 = -1073741790;
    goto LABEL_211;
  }
  v57 = 0;
  if ( v34 )
    v57 = v97;
  *(_QWORD *)v83 = v57;
  LOBYTE(v67) = 1;
  LOBYTE(v66) = v69;
  LOBYTE(v64) = v68;
  NewFile = UdfOpenObjectFromDirContext(v38, *(_QWORD *)v84, v72, v73, v64, v66, FileOffset, v67, v88, v83, v75);
  v70 = NewFile;
LABEL_211:
  if ( v74 )
  {
    if ( (FileOffset[7].LowPart & 0x40) != 0 && FileOffset[16].QuadPart )
    {
      ExFreePoolWithTag((PVOID)FileOffset[16].QuadPart, 0);
      FileOffset[16].QuadPart = 0;
    }
    if ( FileOffset[1].QuadPart )
    {
      CcUnpinData((PVOID)FileOffset[1].QuadPart);
      FileOffset[1].QuadPart = 0;
    }
    if ( (FileOffset[7].LowPart & 4) != 0 )
      UdfFreePool(&FileOffset[4]);
    memset(FileOffset, 0, 0x98u);
  }
  if ( NewFile == 259 )
  {
    v58 = 0;
    v59 = 0;
  }
  else
  {
    v58 = *(_QWORD *)v89;
    v59 = v96;
  }
  if ( *(_QWORD *)v73 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v73 + 136LL) + 80LL) + 8LL));
  ExReleaseResourceLite((PERESOURCE)(v43 + 1480));
  UdfCompleteRequest(v58, v59, (unsigned int)NewFile);
  if ( v69 )
    UdfFreeStringBuffer(&DestinationString);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 14, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids);
  }
  return (unsigned int)NewFile;
}

```

## disassembly

```asm
0x140042c40  mov     r11, rsp
0x140042c43  mov     [r11+18h], rbx
0x140042c47  mov     [r11+20h], rsi
0x140042c4b  push    rdi
0x140042c4c  push    r12
0x140042c4e  push    r13
0x140042c50  push    r14
0x140042c52  push    r15
0x140042c54  sub     rsp, 290h
0x140042c5b  mov     rax, cs:__security_cookie
0x140042c62  xor     rax, rsp
0x140042c65  mov     [rsp+2B8h+var_38], rax
0x140042c6d  mov     r14, rdx
0x140042c70  mov     [r11-1A0h], rdx
0x140042c77  mov     rsi, rcx
0x140042c7a  mov     [r11-1E0h], rcx
0x140042c81  mov     [r11-180h], rcx
0x140042c88  mov     [r11-160h], rdx
0x140042c8f  mov     rbx, [rdx+0B8h]
0x140042c96  mov     qword ptr [rsp+2B8h+var_200], rbx
0x140042c9e  xor     edx, edx; Val
0x140042ca0  mov     r8d, 98h; Size
0x140042ca6  lea     rcx, [r11-148h]; void *
0x140042cad  call    memset
0x140042cb2  mov     byte ptr [rsp+2B8h+var_258], 0
0x140042cb7  xor     edi, edi
0x140042cb9  mov     [rsp+2B8h+var_1E8], rdi
0x140042cc1  mov     qword ptr [rsp+2B8h+var_240], rdi
0x140042cc6  mov     qword ptr [rsp+2B8h+var_208], rdi
0x140042cce  xorps   xmm0, xmm0
0x140042cd1  movups  xmmword ptr [rsp+2B8h+var_220], xmm0
0x140042cd9  xorps   xmm1, xmm1
0x140042cdc  movups  xmmword ptr [rsp+2B8h+Src], xmm1
0x140042ce4  movups  xmmword ptr [rsp+2B8h+DestinationString.Length], xmm0
0x140042cec  mov     r8, [rsi+10h]
0x140042cf0  mov     [rsp+2B8h+var_248], r8
0x140042cf5  test    r8, r8
0x140042cf8  jz      loc_140043F31
0x140042cfe  mov     eax, [rbx+10h]
0x140042d01  mov     [rsp+2B8h+var_228], eax
0x140042d08  mov     r10d, eax
0x140042d0b  shr     r10d, 18h
0x140042d0f  mov     [rsp+2B8h+var_234], r10d
0x140042d17  mov     r15d, eax
0x140042d1a  and     r15d, 2000h
0x140042d21  setnz   r12b
0x140042d25  movzx   ecx, byte ptr [rbx+2]
0x140042d29  test    cl, cl
0x140042d2b  setns   byte ptr [rsp+2B8h+var_258+1]
0x140042d30  movzx   r11d, cl
0x140042d34  and     r11b, 4
0x140042d38  mov     [rsp+2B8h+var_250], r11b
0x140042d3d  mov     r9d, eax
0x140042d40  and     r9d, 1000h
0x140042d47  mov     [rsp+2B8h+var_1EC], r9d
0x140042d4f  mov     [rsp+2B8h+var_158], r8
0x140042d57  mov     r13, [r8+120h]
0x140042d5e  mov     [rsp+2B8h+var_1F8], r13
0x140042d66  mov     edx, [r8+30h]
0x140042d6a  test    dl, 90h
0x140042d6d  jz      short loc_140042D97
0x140042d6f  lea     eax, [r10-1]
0x140042d73  test    eax, 0FFFFFFFDh
0x140042d78  jnz     loc_140043F43
0x140042d7e  test    r11b, r11b
0x140042d81  jnz     loc_140043F43
0x140042d87  test    r9d, r9d
0x140042d8a  jnz     loc_140043F43
0x140042d90  mov     eax, [rsp+2B8h+var_228]
0x140042d97  test    r9d, r9d
0x140042d9a  jnz     loc_140043F9D
0x140042da0  cmp     [rbx+20h], edi
0x140042da3  jnz     loc_140044113
0x140042da9  cmp     [r14+18h], rdi
0x140042dad  jnz     loc_140044113
0x140042db3  test    cl, 2
0x140042db6  jnz     loc_140043FB4
0x140042dbc  bt      eax, 10h
0x140042dc0  jb      loc_1400440F9
0x140042dc6  mov     r14d, edi
0x140042dc9  mov     rsi, rdi
0x140042dcc  movzx   eax, word ptr [rbx+18h]
0x140042dd0  mov     [rsp+2B8h+var_210], ax
0x140042dd8  mov     rbx, [rbx+30h]
0x140042ddc  lea     rdi, [rbx+58h]
0x140042de0  lea     r11, WPP_GLOBAL_Control
0x140042de7  mov     rcx, cs:WPP_GLOBAL_Control
0x140042dee  cmp     rcx, r11
0x140042df1  jz      short loc_140042DFE
0x140042df3  mov     eax, [rcx+2Ch]
0x140042df6  test    al, 10h
0x140042df8  jnz     loc_140043FCF
0x140042dfe  mov     rcx, [rbx+40h]
0x140042e02  test    rcx, rcx
0x140042e05  jnz     loc_140043FF3
0x140042e0b  lea     rax, [rsp+2B8h+var_220]
0x140042e13  mov     qword ptr [rsp+2B8h+var_280], rax
0x140042e18  mov     qword ptr [rsp+2B8h+FileOffset], rdi
0x140042e1d  mov     [rsp+2B8h+var_290], rsi
0x140042e22  mov     rax, [rsp+2B8h+var_1E8]
0x140042e2a  mov     qword ptr [rsp+2B8h+var_298], rax
0x140042e2f  mov     r9d, r14d
0x140042e32  movzx   r8d, r12b
0x140042e36  mov     rsi, [rsp+2B8h+var_248]
0x140042e3b  mov     rdx, rsi
0x140042e3e  mov     r12, qword ptr [rsp+2B8h+var_1E0]
0x140042e46  mov     rcx, r12
0x140042e49  call    UdfNormalizeFileNames
0x140042e4e  mov     ebx, eax
0x140042e50  mov     dword ptr [rsp+2B8h+var_258+4], eax
0x140042e54  test    eax, eax
0x140042e56  js      loc_140044062
0x140042e5c  mov     rcx, [rsp+2B8h+var_1E8]
0x140042e64  test    rcx, rcx
0x140042e67  jnz     loc_14004407C
0x140042e6d  cmp     word ptr [rdi], 0
0x140042e71  jz      loc_140043EE7
0x140042e77  xor     dil, dil
0x140042e7a  lea     rcx, [rsi+5C8h]; Resource
0x140042e81  xor     dl, dl
0x140042e83  mov     r14, qword ptr [rsp+2B8h+var_1E0]
0x140042e8b  mov     eax, [r14+1Ch]
0x140042e8f  test    al, 4
0x140042e91  jz      short loc_140042E95
0x140042e93  mov     dl, 1; Wait
0x140042e95  call    cs:__imp_ExAcquireResourceSharedLite
0x140042e9c  nop     dword ptr [rax+rax+00h]
0x140042ea1  test    al, al
0x140042ea3  jz      loc_1400440B3
0x140042ea9  mov     [rsp+2B8h+var_238], 0
0x140042eb1  xor     r12b, r12b
0x140042eb4  mov     [rsp+2B8h+var_22F], r12b
0x140042ebc  xor     r9d, r9d
0x140042ebf  mov     [rsp+2B8h+var_1F8], r9
0x140042ec7  and     byte ptr [rsp+2B8h+var_228], 1
0x140042ecf  movzx   eax, [rsp+2B8h+var_210]
0x140042ed7  btr     eax, 7
0x140042edb  mov     [rsp+2B8h+var_1A4], eax
0x140042ee2  mov     dword ptr [rsp+2B8h+DestinationString.Length], 600000h
0x140042eed  lea     rax, [rsp+2B8h+var_98]
0x140042ef5  mov     [rsp+2B8h+DestinationString.Buffer], rax
0x140042efd  mov     rax, [rsp+2B8h+var_1A0]
0x140042f05  mov     [rax+38h], r9
0x140042f09  mov     rdx, rsi
0x140042f0c  mov     rcx, r14
0x140042f0f  call    UdfVerifyVcb
0x140042f14  mov     eax, [rsi+30h]
0x140042f17  test    al, 1
0x140042f19  jnz     loc_1400438E9
0x140042f1f  test    r15d, r15d
0x140042f22  jnz     loc_1400436D7
0x140042f28  test    dil, dil
0x140042f2b  jnz     loc_1400435A1
0x140042f31  mov     rax, [r13+88h]
0x140042f38  mov     rcx, [rax+50h]
0x140042f3c  add     rcx, 8; Resource
0x140042f40  xor     dl, dl
0x140042f42  mov     [rsp+2B8h+var_22C], dl
0x140042f49  mov     eax, [r14+1Ch]
0x140042f4d  test    al, 4
0x140042f4f  jz      short loc_140042F5A
0x140042f51  mov     dl, 1; Wait
0x140042f53  mov     [rsp+2B8h+var_22C], dl
0x140042f5a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140042f61  nop     dword ptr [rax+rax+00h]
0x140042f66  test    al, al
0x140042f68  jz      loc_140043945
0x140042f6e  mov     qword ptr [rsp+2B8h+var_240], r13
0x140042f73  movzx   esi, word ptr [rsp+2B8h+var_220]
0x140042f7b  movzx   r15d, byte ptr [rsp+2B8h+var_258+1]
0x140042f81  test    si, si
0x140042f84  jz      loc_140043891
0x140042f8a  lea     rax, [rsp+2B8h+var_258]
0x140042f8f  mov     qword ptr [rsp+2B8h+FileOffset], rax; __int64
0x140042f94  lea     rax, [rsp+2B8h+DestinationString]
0x140042f9c  mov     [rsp+2B8h+var_290], rax; DestinationString
0x140042fa1  lea     rax, [rsp+2B8h+var_220]
0x140042fa9  mov     qword ptr [rsp+2B8h+var_298], rax; __int64
0x140042fae  lea     r9, [rsp+2B8h+var_208]; int
0x140042fb6  lea     r8, [rsp+2B8h+var_240]; int
0x140042fbb  movzx   edx, r15b; int
0x140042fbf  mov     rcx, r14; int
0x140042fc2  call    UdfFindPrefix
0x140042fc7  mov     r8, rax
0x140042fca  mov     [rsp+2B8h+var_1F8], rax
0x140042fd2  mov     [rsp+2B8h+var_168], rax
0x140042fda  movzx   esi, word ptr [rsp+2B8h+var_220]
0x140042fe2  mov     r9, [rsp+2B8h+var_1E8]
0x140042fea  test    r8, r8
0x140042fed  jz      loc_140043530
0x140042ff3  mov     rdx, qword ptr [rsp+2B8h+var_208]
0x140042ffb  test    r8, r8
0x140042ffe  jnz     loc_14004395F
0x140043004  mov     rax, qword ptr [rsp+2B8h+var_240]
0x140043009  cmp     dword ptr [rax+0D8h], 2
0x140043010  jge     loc_140043718
0x140043016  test    si, si
0x140043019  jz      loc_14004355E
0x14004301f  mov     [rsp+2B8h+var_198], r8
0x140043027  mov     eax, [r14+1Ch]
0x14004302b  test    al, 4
0x14004302d  jz      loc_1400439AB
0x140043033  xor     edx, edx; Val
0x140043035  mov     r8d, 98h; Size
0x14004303b  lea     rcx, [rsp+2B8h+var_148]; void *
0x140043043  call    memset
0x140043048  mov     al, 1
0x14004304a  mov     [rsp+2B8h+var_238], al
0x140043051  mov     r13d, 2
0x140043057  mov     r8, [rsp+2B8h+var_220+8]
0x14004305f  mov     ecx, 0FFFEh
0x140043064  mov     byte ptr [rsp+2B8h+var_258], 0
0x140043069  mov     [rsp+2B8h+var_1F0], 0
0x140043074  mov     rdi, r8
0x140043077  mov     [rsp+2B8h+var_190], r8
0x14004307f  test    si, si
0x140043082  jz      short loc_140043093
0x140043084  mov     eax, 3Ah ; ':'
0x140043089  cmp     ax, [r8]
0x14004308d  jz      loc_140043755
0x140043093  xor     r15b, r15b
0x140043096  xor     edx, edx
0x140043098  xor     ecx, ecx
0x14004309a  xor     r14d, r14d
0x14004309d  mov     [rsp+2B8h+var_1F0], edx
0x1400430a4  movzx   eax, si
0x1400430a7  cmp     ecx, eax
0x1400430a9  jnb     short loc_1400430CF
0x1400430ab  movzx   eax, word ptr [rdi]
0x1400430ae  cmp     ax, 5Ch ; '\'
0x1400430b2  jz      short loc_1400430CF
0x1400430b4  cmp     ax, 3Ah ; ':'
0x1400430b8  jz      short loc_1400430CF
0x1400430ba  lea     edx, [rcx+2]
0x1400430bd  mov     r14d, edx
0x1400430c0  add     rdi, r13
0x1400430c3  mov     [rsp+2B8h+var_190], rdi
0x1400430cb  mov     ecx, edx
0x1400430cd  jmp     short loc_14004309D
0x1400430cf  mov     word ptr [rsp+2B8h+Src+2], dx
0x1400430d7  mov     word ptr [rsp+2B8h+Src], dx
0x1400430df  mov     [rsp+2B8h+Src+8], r8
0x1400430e7  lea     rcx, [rsp+2B8h+DestinationString]
0x1400430ef  call    UdfEnsureStringBufferEnough
0x1400430f4  movzx   r8d, word ptr [rsp+2B8h+Src]; Size
0x1400430fd  mov     rdx, [rsp+2B8h+Src+8]; Src
0x140043105  mov     rcx, [rsp+2B8h+DestinationString.Buffer]; void *
0x14004310d  call    memmove
0x140043112  movzx   eax, word ptr [rsp+2B8h+Src]
0x14004311a  mov     [rsp+2B8h+DestinationString.Length], ax
0x140043122  xor     r8d, r8d; AllocateDestinationString
0x140043125  lea     rdx, [rsp+2B8h+DestinationString]; SourceString
0x14004312d  lea     rcx, [rsp+2B8h+DestinationString]; DestinationString
0x140043135  call    cs:__imp_RtlUpcaseUnicodeString
0x14004313c  nop     dword ptr [rax+rax+00h]
0x140043141  movzx   eax, word ptr [rsp+2B8h+var_220]
0x140043149  cmp     r14d, eax
0x14004314c  jnz     loc_14004330F
0x140043152  xor     eax, eax
0x140043154  mov     word ptr [rsp+2B8h+var_220], ax
0x14004315c  mov     rax, qword ptr [rsp+2B8h+var_240]
0x140043161  mov     ecx, [rax+0D4h]
0x140043167  test    cl, 10h
0x14004316a  jnz     loc_1400438D6
0x140043170  mov     r14, qword ptr [rsp+2B8h+var_1E0]
0x140043178  test    r15b, r15b
0x14004317b  jnz     loc_1400433CF
0x140043181  mov     esi, [rsp+2B8h+var_234]
0x140043188  mov     [rsp+2B8h+var_188], 0
0x140043194  movzx   r10d, word ptr [rsp+2B8h+Src]
0x14004319d  test    r10w, r10w
0x1400431a1  jz      short loc_14004320F
0x1400431a3  test    r10b, 1
0x1400431a7  jnz     short loc_14004320F
0x1400431a9  mov     r11, [rsp+2B8h+Src+8]
0x1400431b1  mov     r9, r11
0x1400431b4  mov     [rsp+2B8h+var_188], r11
0x1400431bc  nop     dword ptr [rax+00h]
0x1400431c0  lea     rax, [r11+r10]
0x1400431c4  cmp     r9, rax
0x1400431c7  jnb     short loc_140043222
0x1400431c9  movzx   eax, word ptr [r9]
0x1400431cd  mov     [rsp+2B8h+var_210], ax
0x1400431d5  mov     r8d, 14h
0x1400431db  test    r15b, r15b
0x1400431de  cmovz   r8d, r13d
0x1400431e2  mov     ecx, 0FFh
0x1400431e7  cmp     ax, cx
0x1400431ea  jnb     short loc_140043202
0x1400431ec  test    al, al
0x1400431ee  js      short loc_140043202
0x1400431f0  mov     edx, eax
0x1400431f2  mov     rax, cs:FsRtlLegalAnsiCharacterArray
0x1400431f9  mov     rcx, [rax]
0x1400431fc  test    [rdx+rcx], r8b
0x140043200  jz      short loc_14004320F
0x140043202  add     r9, r13
0x140043205  mov     [rsp+2B8h+var_188], r9
0x14004320d  jmp     short loc_1400431C0
0x14004320f  mov     ebx, 0C0000033h
  ... truncated ...
```
