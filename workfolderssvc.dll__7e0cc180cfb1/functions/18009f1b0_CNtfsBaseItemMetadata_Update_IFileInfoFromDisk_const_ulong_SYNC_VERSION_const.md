# CNtfsBaseItemMetadata::Update(IFileInfoFromDisk const *,ulong,_SYNC_VERSION const *)

- ea: `0x18009f1b0`
- end: `0x18009fa7f`
- name: `?Update@CNtfsBaseItemMetadata@@UEAAJPEBUIFileInfoFromDisk@@KPEBU_SYNC_VERSION@@@Z`
- size: `2255`
- prototype: `__int64 __fastcall(CNtfsBaseItemMetadata *__hidden this, const struct IFileInfoFromDisk *, unsigned int, const struct _SYNC_VERSION *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180007b9c`
- `0x180007e10`
- `0x180009188`
- `0x180011314`
- `0x18004af44`
- `0x180059d50`
- `0x18009b270`
- `0x18009f1b0`
- `0x18009fc60`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x18009f361`
- `KERNEL32!GetComputerNameExW` at `0x18009f361`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009f77d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009f77d`

## string_xrefs

- `0x18009f248`: `CNtfsBaseItemMetadata::Update`
- `0x18009f658`: `LastWriteTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CNtfsBaseItemMetadata::Update(
        CNtfsBaseItemMetadata *this,
        const struct IFileInfoFromDisk *a2,
        char a3,
        const struct _SYNC_VERSION *a4)
{
  _BYTE *v8; // rax
  char v9; // cl
  __int16 v10; // ax
  char *v11; // r15
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, const wchar_t *, __int64); // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, const wchar_t *, __int64); // rbx
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, const wchar_t *, _QWORD); // rbx
  char v21; // al
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, const unsigned __int16 *, __int64); // rbx
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // r13d
  int v27; // r12d
  int v28; // r15d
  int v29; // r14d
  int v30; // esi
  const struct IFileInfoFromDisk *v31; // rbx
  int v32; // edi
  int v33; // eax
  int v34; // edx
  int v35; // r8d
  unsigned int v36; // ebx
  HRESULT LastFailureAsHRESULT; // [rsp+A0h] [rbp-80h] BYREF
  int v39; // [rsp+A4h] [rbp-7Ch]
  char v40; // [rsp+A8h] [rbp-78h]
  const char *v41; // [rsp+B0h] [rbp-70h]
  __int64 v42; // [rsp+B8h] [rbp-68h]
  unsigned int v43; // [rsp+C0h] [rbp-60h] BYREF
  unsigned int v44; // [rsp+C4h] [rbp-5Ch]
  int v45; // [rsp+C8h] [rbp-58h] BYREF
  DWORD nSize[2]; // [rsp+D0h] [rbp-50h] BYREF
  _DWORD v47[2]; // [rsp+D8h] [rbp-48h] BYREF
  _DWORD v48[2]; // [rsp+E0h] [rbp-40h] BYREF
  const struct IFileInfoFromDisk *v49; // [rsp+E8h] [rbp-38h]
  __int64 v50; // [rsp+F0h] [rbp-30h]
  __int64 v51; // [rsp+F8h] [rbp-28h]
  GUID v52; // [rsp+100h] [rbp-20h] BYREF
  _BYTE v53[8]; // [rsp+110h] [rbp-10h] BYREF
  _BYTE v54[8]; // [rsp+118h] [rbp-8h] BYREF
  _BYTE v55[8]; // [rsp+120h] [rbp+0h] BYREF
  _BYTE v56[8]; // [rsp+128h] [rbp+8h] BYREF
  _BYTE v57[8]; // [rsp+130h] [rbp+10h] BYREF
  _BYTE v58[8]; // [rsp+138h] [rbp+18h] BYREF
  GUID pguid; // [rsp+140h] [rbp+20h] BYREF
  __int64 v60; // [rsp+150h] [rbp+30h] BYREF
  __int64 v61; // [rsp+158h] [rbp+38h]
  __int64 v62; // [rsp+160h] [rbp+40h] BYREF
  __int64 v63; // [rsp+168h] [rbp+48h]
  WCHAR Buffer[64]; // [rsp+170h] [rbp+50h] BYREF

  v49 = a2;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_cc6e7d16659736a40182b1383c2d93e5_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (v8[68] & 0x40) == 0 || (v9 = 1, v8[65] < 6u) )
    v9 = 0;
  v39 = 561;
  v40 = v9;
  v41 = "CNtfsBaseItemMetadata::Update";
  v42 = 0;
  v10 = 566;
  if ( !a2 || (LOWORD(v39) = 566, v10 = 567, !a4) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_56;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v39) = 567;
  CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free((char *)this - 80);
  v11 = (char *)this - 120;
  *((_OWORD *)v11 + 1) = CFileSyncItemMetadata::m_csUninitializedGid;
  *((_QWORD *)v11 + 4) = 0;
  CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free((char *)this - 72);
  CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free((char *)this - 64);
  ATL::CComPtrBase<IFileConcurrencyBlob>::Release((char *)this + 8);
  if ( (a3 & 1) != 0 )
  {
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const struct _SYNC_VERSION *))(**((_QWORD **)this - 7)
                                                                                           + 64LL))(
                             *((_QWORD *)this - 7),
                             a4);
    v10 = 579;
    if ( LastFailureAsHRESULT < 0 )
    {
LABEL_56:
      HIWORD(v39) = v10;
      goto LABEL_57;
    }
    LOWORD(v39) = 579;
  }
  else if ( (a3 & 2) == 0 )
  {
    goto LABEL_25;
  }
  v43 = 0;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(char *, unsigned int *))(*(_QWORD *)v11 + 40LL))(
                           (char *)this - 120,
                           &v43);
  v10 = 586;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 586;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const struct _SYNC_VERSION *))(**((_QWORD **)this - 7) + 48LL))(
                           *((_QWORD *)this - 7),
                           a4);
  v10 = 589;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 589;
  nSize[0] = 64;
  if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, nSize) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    v10 = 597;
    goto LABEL_56;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v39) = 597;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, WCHAR *))(**((_QWORD **)this - 7) + 192LL))(
                           *((_QWORD *)this - 7),
                           L"LastUpdatingDeviceName",
                           Buffer);
  v10 = 598;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 598;
  if ( !v43 )
  {
    v45 = 0;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this - 4) + 176LL))(
                             *((_QWORD *)this - 4),
                             &v45);
    v10 = 607;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_56;
    LOWORD(v39) = 607;
    if ( v45 )
    {
      pguid = 0;
      LastFailureAsHRESULT = (*(__int64 (__fastcall **)(char *, GUID *))(*((_QWORD *)this - 15) + 296LL))(
                               (char *)this - 120,
                               &pguid);
      v10 = 614;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_56;
      LOWORD(v39) = 614;
      pguid.Data1 |= 1u;
      LastFailureAsHRESULT = (*(__int64 (__fastcall **)(char *, GUID *))(*((_QWORD *)this - 15) + 288LL))(
                               (char *)this - 120,
                               &pguid);
      v10 = 616;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_56;
      LOWORD(v39) = 616;
    }
  }
LABEL_25:
  v12 = *((_QWORD *)this - 7);
  v13 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v12 + 192LL);
  v14 = (*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *))(*(_QWORD *)a2 + 104LL))(a2);
  LastFailureAsHRESULT = v13(v12, L"FileName", v14);
  v10 = 622;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 622;
  (*(void (__fastcall **)(const struct IFileInfoFromDisk *, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v60);
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *const, __int64 *, __int64))(**((_QWORD **)this - 7) + 176LL))(
                           *((_QWORD *)this - 7),
                           c_szFileIdFieldName,
                           &v60,
                           16);
  v10 = 628;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 628;
  *(_QWORD *)nSize = 0;
  v15 = (*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *, GUID *))(*(_QWORD *)a2 + 112LL))(a2, &pguid);
  LastFailureAsHRESULT = CFileIDType<_FILE_ID_128,INtfsBaseFileID128>::CreateInstance(v15, nSize);
  if ( LastFailureAsHRESULT < 0 )
  {
    HIWORD(v39) = 635;
LABEL_29:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(nSize);
    goto LABEL_57;
  }
  LOWORD(v39) = 635;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this - 15) + 128LL))(
                           (char *)this - 120,
                           *(_QWORD *)nSize);
  if ( LastFailureAsHRESULT < 0 )
  {
    HIWORD(v39) = 637;
    goto LABEL_29;
  }
  LOWORD(v39) = 637;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(nSize);
  (*(void (__fastcall **)(const struct IFileInfoFromDisk *, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v43);
  LastFailureAsHRESULT = 0;
  LOWORD(v39) = 642;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this - 7)
                                                                                              + 224LL))(
                           *((_QWORD *)this - 7),
                           L"ChangeTime",
                           v43 + ((unsigned __int64)v44 << 32));
  v10 = 643;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 643;
  (*(void (__fastcall **)(const struct IFileInfoFromDisk *, _DWORD *))(*(_QWORD *)a2 + 40LL))(a2, v47);
  LastFailureAsHRESULT = 0;
  LOWORD(v39) = 647;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this - 7)
                                                                                              + 224LL))(
                           *((_QWORD *)this - 7),
                           L"CreationTime",
                           v47[0] + ((unsigned __int64)v47[1] << 32));
  v10 = 648;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 648;
  (*(void (__fastcall **)(const struct IFileInfoFromDisk *, _DWORD *))(*(_QWORD *)a2 + 48LL))(a2, v48);
  LastFailureAsHRESULT = 0;
  LOWORD(v39) = 652;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this - 7)
                                                                                              + 224LL))(
                           *((_QWORD *)this - 7),
                           L"LastWriteTime",
                           v48[0] + ((unsigned __int64)v48[1] << 32));
  v10 = 653;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 653;
  v16 = *((_QWORD *)this - 7);
  v17 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v16 + 224LL);
  v18 = (*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *))(*(_QWORD *)a2 + 72LL))(a2);
  LastFailureAsHRESULT = v17(v16, L"UsnId", v18);
  v10 = 656;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 656;
  v19 = *((_QWORD *)this - 7);
  v20 = *(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v19 + 216LL);
  v21 = (*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *))(*(_QWORD *)a2 + 32LL))(a2);
  LastFailureAsHRESULT = v20(v19, L"Attributes", v21 & 0x17);
  v10 = 659;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 659;
  v22 = *((_QWORD *)this - 7);
  v23 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v22 + 224LL);
  v24 = (*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *))(*(_QWORD *)a2 + 64LL))(a2);
  LastFailureAsHRESULT = v23(v22, L"FileSize", v24);
  v10 = 663;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_56;
  LOWORD(v39) = 663;
  if ( (a3 & 1) != 0 || (a3 & 4) != 0 )
  {
    pguid = 0;
    if ( ((*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *))(*(_QWORD *)a2 + 32LL))(a2) & 0x10) == 0 )
    {
      LastFailureAsHRESULT = CoCreateGuid(&pguid);
      v10 = 674;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_56;
      LOWORD(v39) = 674;
    }
    v25 = *((_QWORD *)this - 7);
    v52 = pguid;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *))(*(_QWORD *)v25 + 184LL))(
                             v25,
                             L"StreamIdentifier",
                             &v52);
    v10 = 677;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_56;
    LOWORD(v39) = 677;
    if ( (a3 & 1) != 0 )
      goto LABEL_60;
  }
  if ( (a3 & 8) != 0 )
  {
LABEL_60:
    LastFailureAsHRESULT = 0;
    LOWORD(v39) = 684;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this - 7)
                                                                                                + 224LL))(
                             *((_QWORD *)this - 7),
                             L"NamespaceChangeTime",
                             v43 + ((unsigned __int64)v44 << 32));
    v10 = 685;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_56;
    LOWORD(v39) = 685;
    if ( (a3 & 1) != 0 )
      goto LABEL_49;
  }
  if ( (a3 & 0x10) != 0 )
  {
LABEL_49:
    LastFailureAsHRESULT = 0;
    LOWORD(v39) = 692;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this - 7)
                                                                                                + 224LL))(
                             *((_QWORD *)this - 7),
                             L"AttributeChangeTime",
                             v43 + ((unsigned __int64)v44 << 32));
    v10 = 693;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_56;
    LOWORD(v39) = 693;
  }
  (*(void (__fastcall **)(const struct IFileInfoFromDisk *, __int64 *))(*(_QWORD *)a2 + 112LL))(a2, &v62);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    v50 = (*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *))(*(_QWORD *)a2 + 104LL))(a2);
    nSize[0] = (*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *))(*(_QWORD *)a2 + 32LL))(a2) & 0x17;
    v51 = (*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *))(*(_QWORD *)a2 + 64LL))(a2);
    v45 = *(_DWORD *)(*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)a2 + 40LL))(
                       a2,
                       v53);
    v26 = *(_DWORD *)((*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)a2 + 40LL))(
                        a2,
                        v54)
                    + 4);
    v27 = *(_DWORD *)(*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)a2 + 48LL))(
                       a2,
                       v55);
    v28 = *(_DWORD *)((*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)a2 + 48LL))(
                        a2,
                        v56)
                    + 4);
    v29 = *(_DWORD *)(*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)a2 + 56LL))(
                       a2,
                       v57);
    v30 = *(_DWORD *)((*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)a2 + 56LL))(
                        a2,
                        v58)
                    + 4);
    v31 = v49;
    v32 = *(_DWORD *)(*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *, GUID *))(*(_QWORD *)v49 + 56LL))(
                       v49,
                       &v52);
    LODWORD(v31) = *(_DWORD *)((*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *, GUID *))(*(_QWORD *)v31 + 56LL))(
                                 v31,
                                 &pguid)
                             + 4);
    v33 = (*(__int64 (__fastcall **)(const struct IFileInfoFromDisk *))(*(_QWORD *)v49 + 72LL))(v49);
    WPP_SF_iiiDDDDDDDDiDiiS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      v34,
      v35,
      v33,
      v61,
      v60,
      (char)v31,
      v32,
      v30,
      v29,
      v28,
      v27,
      v26,
      v45,
      v51,
      nSize[0],
      v63,
      v62,
      v50);
  }
LABEL_57:
  v36 = LastFailureAsHRESULT;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return v36;
}

```

## disassembly

```asm
0x18009f1b0  mov     [rsp-8+arg_10], rbx
0x18009f1b5  push    rbp
0x18009f1b6  push    rsi
0x18009f1b7  push    rdi
0x18009f1b8  push    r12
0x18009f1ba  push    r13
0x18009f1bc  push    r14
0x18009f1be  push    r15
0x18009f1c0  lea     rbp, [rsp-0E0h]
0x18009f1c8  sub     rsp, 200h
0x18009f1cf  mov     rax, cs:__security_cookie
0x18009f1d6  xor     rax, rsp
0x18009f1d9  mov     [rbp+110h+var_40], rax
0x18009f1e0  mov     rbx, r9
0x18009f1e3  mov     r13d, r8d
0x18009f1e6  mov     rsi, rdx
0x18009f1e9  mov     [rbp+110h+var_148], rdx
0x18009f1ed  mov     r14, rcx
0x18009f1f0  lea     rcx, WPP_GLOBAL_Control
0x18009f1f7  mov     rax, cs:WPP_GLOBAL_Control
0x18009f1fe  cmp     rax, rcx
0x18009f201  jz      short loc_18009F22B
0x18009f203  test    byte ptr [rax+44h], 40h
0x18009f207  jz      short loc_18009F22B
0x18009f209  cmp     byte ptr [rax+41h], 6
0x18009f20d  jb      short loc_18009F22B
0x18009f20f  mov     edx, 14h
0x18009f214  lea     r8, WPP_cc6e7d16659736a40182b1383c2d93e5_Traceguids
0x18009f21b  mov     rcx, [rax+38h]
0x18009f21f  call    WPP_SF_
0x18009f224  mov     rax, cs:WPP_GLOBAL_Control
0x18009f22b  xor     edi, edi
0x18009f22d  test    byte ptr [rax+44h], 40h
0x18009f231  jz      short loc_18009F23B
0x18009f233  cmp     byte ptr [rax+41h], 6
0x18009f237  mov     cl, 1
0x18009f239  jnb     short loc_18009F23E
0x18009f23b  mov     cl, dil
0x18009f23e  mov     [rbp+110h+var_18C], 231h
0x18009f245  mov     [rbp+110h+var_188], cl
0x18009f248  lea     rax, aCntfsbaseitemm_6; "CNtfsBaseItemMetadata::Update"
0x18009f24f  mov     [rbp+110h+var_180], rax
0x18009f253  mov     [rbp+110h+var_178], rdi
0x18009f257  mov     eax, 236h
0x18009f25c  test    rsi, rsi
0x18009f25f  jz      loc_18009FA3C
0x18009f265  mov     word ptr [rbp+110h+var_18C], ax
0x18009f269  mov     eax, 237h
0x18009f26e  test    rbx, rbx
0x18009f271  jz      loc_18009FA3C
0x18009f277  mov     r12d, r13d
0x18009f27a  mov     [rbp+110h+var_190], edi
0x18009f27d  mov     word ptr [rbp+110h+var_18C], ax
0x18009f281  lea     rcx, [r14-50h]
0x18009f285  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x18009f28a  lea     r15, [r14-78h]
0x18009f28e  movups  xmm0, cs:?m_csUninitializedGid@CFileSyncItemMetadata@@1U_SYNC_GID@@B; _SYNC_GID const CFileSyncItemMetadata::m_csUninitializedGid
0x18009f295  movups  xmmword ptr [r15+10h], xmm0
0x18009f29a  movsd   xmm1, cs:qword_18015B9E8
0x18009f2a2  movsd   qword ptr [r15+20h], xmm1
0x18009f2a8  lea     rcx, [r14-48h]
0x18009f2ac  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x18009f2b1  lea     rcx, [r14-40h]
0x18009f2b5  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x18009f2ba  lea     rcx, [r14+8]
0x18009f2be  call    ?Release@?$CComPtrBase@UIFileConcurrencyBlob@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IFileConcurrencyBlob>::Release(void)
0x18009f2c3  and     r12d, 1
0x18009f2c7  jz      short loc_18009F2F2
0x18009f2c9  mov     rcx, [r14-38h]
0x18009f2cd  mov     rax, [rcx]
0x18009f2d0  mov     rdx, rbx
0x18009f2d3  mov     rax, [rax+40h]
0x18009f2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f2dc  mov     [rbp+110h+var_190], eax
0x18009f2df  test    eax, eax
0x18009f2e1  mov     eax, 243h
0x18009f2e6  js      loc_18009FA43
0x18009f2ec  mov     word ptr [rbp+110h+var_18C], ax
0x18009f2f0  jmp     short loc_18009F2FC
0x18009f2f2  test    r13b, 2
0x18009f2f6  jz      loc_18009F458
0x18009f2fc  mov     [rbp+110h+var_170], edi
0x18009f2ff  mov     rax, [r15]
0x18009f302  lea     rdx, [rbp+110h+var_170]
0x18009f306  mov     rcx, r15
0x18009f309  mov     rax, [rax+28h]
0x18009f30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f312  mov     [rbp+110h+var_190], eax
0x18009f315  test    eax, eax
0x18009f317  mov     eax, 24Ah
0x18009f31c  js      loc_18009FA43
0x18009f322  mov     word ptr [rbp+110h+var_18C], ax
0x18009f326  mov     rcx, [r14-38h]
0x18009f32a  mov     rax, [rcx]
0x18009f32d  mov     rdx, rbx
0x18009f330  mov     rax, [rax+30h]
0x18009f334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f339  mov     [rbp+110h+var_190], eax
0x18009f33c  test    eax, eax
0x18009f33e  mov     eax, 24Dh
0x18009f343  js      loc_18009FA43
0x18009f349  mov     word ptr [rbp+110h+var_18C], ax
0x18009f34d  mov     [rbp+110h+nSize], 40h ; '@'
0x18009f354  lea     r8, [rbp+110h+nSize]; nSize
0x18009f358  lea     rdx, [rbp+110h+Buffer]; lpBuffer
0x18009f35c  mov     ecx, 1; NameType
0x18009f361  call    cs:__imp_GetComputerNameExW
0x18009f367  test    eax, eax
0x18009f369  jnz     short loc_18009F37D
0x18009f36b  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18009f370  mov     [rbp+110h+var_190], eax
0x18009f373  mov     eax, 255h
0x18009f378  jmp     loc_18009FA43
0x18009f37d  mov     [rbp+110h+var_190], edi
0x18009f380  mov     eax, 255h
0x18009f385  mov     word ptr [rbp+110h+var_18C], ax
0x18009f389  mov     rcx, [r14-38h]
0x18009f38d  mov     rax, [rcx]
0x18009f390  lea     r8, [rbp+110h+Buffer]
0x18009f394  lea     rdx, aLastupdatingde; "LastUpdatingDeviceName"
0x18009f39b  mov     rax, [rax+0C0h]
0x18009f3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f3a7  mov     [rbp+110h+var_190], eax
0x18009f3aa  test    eax, eax
0x18009f3ac  mov     eax, 256h
0x18009f3b1  js      loc_18009FA43
0x18009f3b7  mov     word ptr [rbp+110h+var_18C], ax
0x18009f3bb  cmp     [rbp+110h+var_170], edi
0x18009f3be  jnz     loc_18009F458
0x18009f3c4  mov     [rbp+110h+var_168], edi
0x18009f3c7  mov     rcx, [r14-20h]
0x18009f3cb  mov     rax, [rcx]
0x18009f3ce  lea     rdx, [rbp+110h+var_168]
0x18009f3d2  mov     rax, [rax+0B0h]
0x18009f3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f3de  mov     [rbp+110h+var_190], eax
0x18009f3e1  test    eax, eax
0x18009f3e3  mov     eax, 25Fh
0x18009f3e8  js      loc_18009FA43
0x18009f3ee  mov     word ptr [rbp+110h+var_18C], ax
0x18009f3f2  cmp     [rbp+110h+var_168], edi
0x18009f3f5  jz      short loc_18009F458
0x18009f3f7  xorps   xmm0, xmm0
0x18009f3fa  movups  xmmword ptr [rbp+110h+pguid.Data1], xmm0
0x18009f3fe  mov     rax, [r14-78h]
0x18009f402  lea     rdx, [rbp+110h+pguid]
0x18009f406  mov     rcx, r15
0x18009f409  mov     rax, [rax+128h]
0x18009f410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f415  mov     [rbp+110h+var_190], eax
0x18009f418  test    eax, eax
0x18009f41a  mov     eax, 266h
0x18009f41f  js      loc_18009FA43
0x18009f425  mov     word ptr [rbp+110h+var_18C], ax
0x18009f429  or      [rbp+110h+pguid.Data1], 1
0x18009f42d  mov     rax, [r14-78h]
0x18009f431  lea     rdx, [rbp+110h+pguid]
0x18009f435  mov     rcx, r15
0x18009f438  mov     rax, [rax+120h]
0x18009f43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f444  mov     [rbp+110h+var_190], eax
0x18009f447  test    eax, eax
0x18009f449  mov     eax, 268h
0x18009f44e  js      loc_18009FA43
0x18009f454  mov     word ptr [rbp+110h+var_18C], ax
0x18009f458  mov     rdi, [r14-38h]
0x18009f45c  mov     rax, [rdi]
0x18009f45f  mov     rbx, [rax+0C0h]
0x18009f466  mov     rdx, [rsi]
0x18009f469  mov     rcx, rsi
0x18009f46c  mov     rax, [rdx+68h]
0x18009f470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f475  mov     r8, rax
0x18009f478  lea     rdx, aFilename; "FileName"
0x18009f47f  mov     rcx, rdi
0x18009f482  mov     rax, rbx
0x18009f485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f48a  mov     [rbp+110h+var_190], eax
0x18009f48d  test    eax, eax
0x18009f48f  mov     eax, 26Eh
0x18009f494  js      loc_18009FA43
0x18009f49a  mov     word ptr [rbp+110h+var_18C], ax
0x18009f49e  mov     rax, [rsi]
0x18009f4a1  lea     rdx, [rbp+110h+var_E0]
0x18009f4a5  mov     rcx, rsi
0x18009f4a8  mov     rax, [rax+18h]
0x18009f4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f4b1  mov     rcx, [r14-38h]
0x18009f4b5  mov     rax, [rcx]
0x18009f4b8  mov     r9d, 10h
0x18009f4be  lea     r8, [rbp+110h+var_E0]
0x18009f4c2  mov     rdx, cs:?c_szFileIdFieldName@@3PEBGEB; ushort const * const c_szFileIdFieldName
0x18009f4c9  mov     rax, [rax+0B0h]
0x18009f4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f4d5  mov     [rbp+110h+var_190], eax
0x18009f4d8  test    eax, eax
0x18009f4da  mov     eax, 274h
0x18009f4df  js      loc_18009FA43
0x18009f4e5  mov     word ptr [rbp+110h+var_18C], ax
0x18009f4e9  mov     qword ptr [rbp+110h+nSize], 0
0x18009f4f1  mov     rax, [rsi]
0x18009f4f4  lea     rdx, [rbp+110h+pguid]
0x18009f4f8  mov     rcx, rsi
0x18009f4fb  mov     rax, [rax+70h]
0x18009f4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f504  lea     rdx, [rbp+110h+nSize]
0x18009f508  mov     rcx, rax
0x18009f50b  call    ?CreateInstance@?$CFileIDType@U_FILE_ID_128@@UINtfsBaseFileID128@@@@SAJAEBU_FILE_ID_128@@PEAPEAUINtfsBaseFileID128@@@Z; CFileIDType<_FILE_ID_128,INtfsBaseFileID128>::CreateInstance(_FILE_ID_128 const &,INtfsBaseFileID128 * *)
0x18009f510  mov     [rbp+110h+var_190], eax
0x18009f513  test    eax, eax
0x18009f515  mov     eax, 27Bh
0x18009f51a  jns     short loc_18009F52E
0x18009f51c  mov     word ptr [rbp+110h+var_18C+2], ax
0x18009f520  lea     rcx, [rbp+110h+nSize]
0x18009f524  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009f529  jmp     loc_18009FA47
0x18009f52e  mov     word ptr [rbp+110h+var_18C], ax
0x18009f532  mov     rax, [r14-78h]
0x18009f536  mov     rdx, qword ptr [rbp+110h+nSize]
0x18009f53a  mov     rcx, r15
0x18009f53d  mov     rax, [rax+80h]
0x18009f544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f549  mov     [rbp+110h+var_190], eax
0x18009f54c  xor     r15d, r15d
0x18009f54f  test    eax, eax
0x18009f551  mov     eax, 27Dh
0x18009f556  jns     short loc_18009F55E
0x18009f558  mov     word ptr [rbp+110h+var_18C+2], ax
0x18009f55c  jmp     short loc_18009F520
0x18009f55e  mov     word ptr [rbp+110h+var_18C], ax
0x18009f562  lea     rcx, [rbp+110h+nSize]
0x18009f566  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009f56b  mov     rax, [rsi]
0x18009f56e  lea     rdx, [rbp+110h+var_170]
0x18009f572  mov     rcx, rsi
0x18009f575  mov     rax, [rax+38h]
0x18009f579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f57e  mov     [rbp+110h+var_190], r15d
0x18009f582  mov     eax, 282h
0x18009f587  mov     word ptr [rbp+110h+var_18C], ax
0x18009f58b  mov     rcx, [r14-38h]
0x18009f58f  mov     r9, [rcx]
0x18009f592  mov     r8d, [rbp+110h+var_16C]
0x18009f596  shl     r8, 20h
0x18009f59a  mov     eax, [rbp+110h+var_170]
0x18009f59d  add     r8, rax
0x18009f5a0  lea     rdx, aChangetime_0; "ChangeTime"
0x18009f5a7  mov     rax, [r9+0E0h]
0x18009f5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f5b3  mov     [rbp+110h+var_190], eax
0x18009f5b6  test    eax, eax
0x18009f5b8  mov     eax, 283h
0x18009f5bd  js      loc_18009FA43
0x18009f5c3  mov     word ptr [rbp+110h+var_18C], ax
0x18009f5c7  mov     rax, [rsi]
0x18009f5ca  lea     rdx, [rbp+110h+var_158]
0x18009f5ce  mov     rcx, rsi
0x18009f5d1  mov     rax, [rax+28h]
0x18009f5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f5da  mov     [rbp+110h+var_190], r15d
0x18009f5de  mov     eax, 287h
0x18009f5e3  mov     word ptr [rbp+110h+var_18C], ax
0x18009f5e7  mov     rcx, [r14-38h]
0x18009f5eb  mov     r9, [rcx]
0x18009f5ee  mov     r8d, [rbp+110h+var_154]
0x18009f5f2  shl     r8, 20h
0x18009f5f6  mov     eax, [rbp+110h+var_158]
0x18009f5f9  add     r8, rax
0x18009f5fc  lea     rdx, aCreationtime; "CreationTime"
0x18009f603  mov     rax, [r9+0E0h]
0x18009f60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f60f  mov     [rbp+110h+var_190], eax
0x18009f612  test    eax, eax
0x18009f614  mov     eax, 288h
0x18009f619  js      loc_18009FA43
0x18009f61f  mov     word ptr [rbp+110h+var_18C], ax
0x18009f623  mov     rax, [rsi]
0x18009f626  lea     rdx, [rbp+110h+var_150]
0x18009f62a  mov     rcx, rsi
0x18009f62d  mov     rax, [rax+30h]
0x18009f631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f636  mov     [rbp+110h+var_190], r15d
0x18009f63a  mov     eax, 28Ch
0x18009f63f  mov     word ptr [rbp+110h+var_18C], ax
0x18009f643  mov     rcx, [r14-38h]
0x18009f647  mov     r9, [rcx]
0x18009f64a  mov     r8d, [rbp+110h+var_14C]
0x18009f64e  shl     r8, 20h
0x18009f652  mov     eax, [rbp+110h+var_150]
0x18009f655  add     r8, rax
0x18009f658  lea     rdx, aLastwritetime; "LastWriteTime"
0x18009f65f  mov     rax, [r9+0E0h]
0x18009f666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f66b  mov     [rbp+110h+var_190], eax
0x18009f66e  test    eax, eax
0x18009f670  mov     eax, 28Dh
0x18009f675  js      loc_18009FA43
0x18009f67b  mov     word ptr [rbp+110h+var_18C], ax
0x18009f67f  mov     rdi, [r14-38h]
0x18009f683  mov     rax, [rdi]
  ... truncated ...
```
