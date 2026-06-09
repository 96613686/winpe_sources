# CNtfsBaseItemMetadata::Update(IChangeUpdateFileEnumItem const *,ulong,_SYNC_VERSION const *)

- ea: `0x18009ea20`
- end: `0x18009f1a9`
- name: `?Update@CNtfsBaseItemMetadata@@UEAAJPEBUIChangeUpdateFileEnumItem@@KPEBU_SYNC_VERSION@@@Z`
- size: `1929`
- prototype: `__int64 __fastcall(CNtfsBaseItemMetadata *__hidden this, const struct IChangeUpdateFileEnumItem *, unsigned int, const struct _SYNC_VERSION *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180007b9c`
- `0x180007e10`
- `0x180009188`
- `0x180011314`
- `0x180059d50`
- `0x18009b270`
- `0x18009ea20`
- `0x18009fa88`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x18009ebfa`
- `KERNEL32!GetComputerNameExW` at `0x18009ebfa`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009ef7b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009ef7b`

## string_xrefs

- `0x18009eab7`: `CNtfsBaseItemMetadata::Update`
- `0x18009ee78`: `LastWriteTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNtfsBaseItemMetadata::Update(
        CNtfsBaseItemMetadata *this,
        const struct IChangeUpdateFileEnumItem *a2,
        char a3,
        const struct _SYNC_VERSION *a4)
{
  _BYTE *v8; // rax
  char v9; // cl
  __int16 v10; // ax
  char *v11; // rsi
  GUID v12; // xmm0
  __int64 v13; // rcx
  int v14; // r8d
  unsigned int v15; // ebx
  HRESULT LastFailureAsHRESULT; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+74h] [rbp-8Ch]
  char v19; // [rsp+78h] [rbp-88h]
  const char *v20; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  int v22; // [rsp+90h] [rbp-70h] BYREF
  int v23; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v24; // [rsp+98h] [rbp-68h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h] BYREF
  DWORD nSize[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v30; // [rsp+D8h] [rbp-28h] BYREF
  GUID pguid; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v32; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v33; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Buffer[64]; // [rsp+110h] [rbp+10h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_cc6e7d16659736a40182b1383c2d93e5_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (v8[68] & 0x40) == 0 || (v9 = 1, v8[65] < 6u) )
    v9 = 0;
  v18 = 386;
  v19 = v9;
  v20 = "CNtfsBaseItemMetadata::Update";
  v21 = 0;
  v29 = 0;
  v30 = 0;
  v22 = 0;
  v32 = 0;
  v33 = 0;
  v27 = 0;
  v28 = 0;
  v24 = 0;
  v25 = 0;
  v10 = 400;
  if ( !a2 || (LOWORD(v18) = 400, v10 = 401, !a4) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_64;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v18) = 401;
  CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free((char *)this - 80);
  v11 = (char *)this - 120;
  *((_OWORD *)v11 + 1) = CFileSyncItemMetadata::m_csUninitializedGid;
  *((_QWORD *)v11 + 4) = 0;
  CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free((char *)this - 72);
  CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free((char *)this - 64);
  if ( (a3 & 1) != 0 )
  {
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const struct _SYNC_VERSION *))(**((_QWORD **)this - 7)
                                                                                           + 64LL))(
                             *((_QWORD *)this - 7),
                             a4);
    v10 = 412;
    if ( LastFailureAsHRESULT < 0 )
    {
LABEL_64:
      HIWORD(v18) = v10;
      goto LABEL_65;
    }
    LOWORD(v18) = 412;
  }
  else if ( (a3 & 2) == 0 )
  {
    goto LABEL_23;
  }
  v23 = 0;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v11 + 40LL))((char *)this - 120, &v23);
  v10 = 420;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 420;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const struct _SYNC_VERSION *))(**((_QWORD **)this - 7) + 48LL))(
                           *((_QWORD *)this - 7),
                           a4);
  v10 = 422;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 422;
  nSize[0] = 64;
  if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, nSize) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    v10 = 430;
    goto LABEL_64;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v18) = 430;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, WCHAR *))(**((_QWORD **)this - 7) + 192LL))(
                           *((_QWORD *)this - 7),
                           L"LastUpdatingDeviceName",
                           Buffer);
  v10 = 431;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 431;
  if ( !v23 )
  {
    pguid = 0;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(char *, GUID *))(*((_QWORD *)this - 15) + 296LL))(
                             (char *)this - 120,
                             &pguid);
    v10 = 440;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_64;
    LOWORD(v18) = 440;
    pguid.Data1 |= 1u;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(char *, GUID *))(*((_QWORD *)this - 15) + 288LL))(
                             (char *)this - 120,
                             &pguid);
    v10 = 442;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_64;
    LOWORD(v18) = 442;
  }
LABEL_23:
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(const struct IChangeUpdateFileEnumItem *, __int64 *))(*(_QWORD *)a2 + 8LL))(
                           a2,
                           &v29);
  v10 = 447;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 447;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this - 7) + 192LL))(
                           *((_QWORD *)this - 7),
                           L"FileName",
                           v29);
  v10 = 448;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 448;
  *(_QWORD *)nSize = 0;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(const struct IChangeUpdateFileEnumItem *, __int128 *))(*(_QWORD *)a2 + 80LL))(
                           a2,
                           &v32);
  if ( LastFailureAsHRESULT < 0 )
  {
    HIWORD(v18) = 454;
LABEL_27:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(nSize);
    goto LABEL_65;
  }
  LOWORD(v18) = 454;
  LastFailureAsHRESULT = CFileIDType<_FILE_ID_128,INtfsBaseFileID128>::CreateInstance(&v32, nSize);
  if ( LastFailureAsHRESULT < 0 )
  {
    HIWORD(v18) = 457;
    goto LABEL_27;
  }
  LOWORD(v18) = 457;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this - 15) + 128LL))(
                           (char *)this - 120,
                           *(_QWORD *)nSize);
  if ( LastFailureAsHRESULT < 0 )
  {
    HIWORD(v18) = 460;
    goto LABEL_27;
  }
  LOWORD(v18) = 460;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(nSize);
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(const struct IChangeUpdateFileEnumItem *, __int64 *))(*(_QWORD *)a2 + 32LL))(
                           a2,
                           &v24);
  if ( LastFailureAsHRESULT < 0 )
  {
    v10 = 464;
    goto LABEL_64;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v18) = 465;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this - 7)
                                                                                              + 224LL))(
                           *((_QWORD *)this - 7),
                           L"CreationTime",
                           (unsigned int)v24 + ((unsigned __int64)HIDWORD(v24) << 32));
  v10 = 466;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 466;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(const struct IChangeUpdateFileEnumItem *, __int64 *))(*(_QWORD *)a2 + 40LL))(
                           a2,
                           &v25);
  if ( LastFailureAsHRESULT < 0 )
  {
    v10 = 469;
    goto LABEL_64;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v18) = 470;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this - 7)
                                                                                              + 224LL))(
                           *((_QWORD *)this - 7),
                           L"LastWriteTime",
                           (unsigned int)v25 + ((unsigned __int64)HIDWORD(v25) << 32));
  v10 = 471;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 471;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(const struct IChangeUpdateFileEnumItem *, int *))(*(_QWORD *)a2 + 64LL))(
                           a2,
                           &v22);
  v10 = 474;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 474;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this - 7) + 216LL))(
                           *((_QWORD *)this - 7),
                           L"Attributes",
                           v22 & 0x17);
  v10 = 475;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 475;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(const struct IChangeUpdateFileEnumItem *, __int64 *))(*(_QWORD *)a2 + 56LL))(
                           a2,
                           &v30);
  v10 = 478;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 478;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64))(**((_QWORD **)this - 7)
                                                                                              + 224LL))(
                           *((_QWORD *)this - 7),
                           L"FileSize",
                           v30);
  v10 = 480;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_64;
  LOWORD(v18) = 480;
  if ( (a3 & 1) != 0 || (a3 & 4) != 0 )
  {
    v12 = 0;
    pguid = 0;
    if ( (v22 & 0x10) == 0 )
    {
      LastFailureAsHRESULT = CoCreateGuid(&pguid);
      v10 = 491;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_64;
      LOWORD(v18) = 491;
      v12 = pguid;
    }
    v13 = *((_QWORD *)this - 7);
    *(GUID *)nSize = v12;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(__int64, const wchar_t *, DWORD *))(*(_QWORD *)v13 + 184LL))(
                             v13,
                             L"StreamIdentifier",
                             nSize);
    v10 = 494;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_64;
    LOWORD(v18) = 494;
    if ( (a3 & 1) != 0 )
      goto LABEL_68;
  }
  if ( (a3 & 8) != 0 )
  {
LABEL_68:
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(const struct IChangeUpdateFileEnumItem *, __int64 *))(*(_QWORD *)a2 + 48LL))(
                             a2,
                             &v27);
    if ( LastFailureAsHRESULT < 0 )
    {
      v10 = 501;
      goto LABEL_64;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v18) = 502;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this - 7)
                                                                                                + 224LL))(
                             *((_QWORD *)this - 7),
                             L"NamespaceChangeTime",
                             (unsigned int)v27 + ((unsigned __int64)HIDWORD(v27) << 32));
    v10 = 503;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_64;
    LOWORD(v18) = 503;
    if ( (a3 & 1) != 0 )
      goto LABEL_55;
  }
  if ( (a3 & 0x10) != 0 )
  {
LABEL_55:
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(const struct IChangeUpdateFileEnumItem *, __int64 *))(*(_QWORD *)a2 + 48LL))(
                             a2,
                             &v28);
    if ( LastFailureAsHRESULT < 0 )
    {
      v10 = 510;
      goto LABEL_64;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v18) = 511;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this - 7)
                                                                                                + 224LL))(
                             *((_QWORD *)this - 7),
                             L"AttributeChangeTime",
                             (unsigned int)v28 + ((unsigned __int64)HIDWORD(v28) << 32));
    v10 = 512;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_64;
    LOWORD(v18) = 512;
  }
  (*(void (__fastcall **)(const struct IChangeUpdateFileEnumItem *, __int128 *))(*(_QWORD *)a2 + 72LL))(a2, &v33);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_iiDDDDiDiiS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      v22 & 0x17,
      v14,
      DWORD2(v33),
      v33,
      SBYTE4(v25),
      v25,
      SBYTE4(v24),
      v24,
      v30,
      v22 & 0x17,
      SBYTE8(v32),
      v32,
      v29);
  }
LABEL_65:
  v15 = LastFailureAsHRESULT;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return v15;
}

```

## disassembly

```asm
0x18009ea20  mov     [rsp-8+arg_10], rbx
0x18009ea25  push    rbp
0x18009ea26  push    rsi
0x18009ea27  push    rdi
0x18009ea28  push    r12
0x18009ea2a  push    r13
0x18009ea2c  push    r14
0x18009ea2e  push    r15
0x18009ea30  lea     rbp, [rsp-0A0h]
0x18009ea38  sub     rsp, 1A0h
0x18009ea3f  mov     rax, cs:__security_cookie
0x18009ea46  xor     rax, rsp
0x18009ea49  mov     [rbp+0D0h+var_40], rax
0x18009ea50  mov     r14, r9
0x18009ea53  mov     r15d, r8d
0x18009ea56  mov     rbx, rdx
0x18009ea59  mov     rdi, rcx
0x18009ea5c  lea     rcx, WPP_GLOBAL_Control
0x18009ea63  mov     rax, cs:WPP_GLOBAL_Control
0x18009ea6a  cmp     rax, rcx
0x18009ea6d  jz      short loc_18009EA97
0x18009ea6f  test    byte ptr [rax+44h], 40h
0x18009ea73  jz      short loc_18009EA97
0x18009ea75  cmp     byte ptr [rax+41h], 6
0x18009ea79  jb      short loc_18009EA97
0x18009ea7b  mov     edx, 12h
0x18009ea80  lea     r8, WPP_cc6e7d16659736a40182b1383c2d93e5_Traceguids
0x18009ea87  mov     rcx, [rax+38h]
0x18009ea8b  call    WPP_SF_
0x18009ea90  mov     rax, cs:WPP_GLOBAL_Control
0x18009ea97  xor     r13d, r13d
0x18009ea9a  test    byte ptr [rax+44h], 40h
0x18009ea9e  jz      short loc_18009EAA8
0x18009eaa0  cmp     byte ptr [rax+41h], 6
0x18009eaa4  mov     cl, 1
0x18009eaa6  jnb     short loc_18009EAAB
0x18009eaa8  mov     cl, r13b
0x18009eaab  mov     [rsp+1D0h+var_15C], 182h
0x18009eab3  mov     [rsp+1D0h+var_158], cl
0x18009eab7  lea     rax, aCntfsbaseitemm_6; "CNtfsBaseItemMetadata::Update"
0x18009eabe  mov     [rbp+0D0h+var_150], rax
0x18009eac2  mov     [rbp+0D0h+var_148], r13
0x18009eac6  mov     [rbp+0D0h+var_100], r13
0x18009eaca  mov     [rbp+0D0h+var_F8], r13
0x18009eace  mov     [rbp+0D0h+var_140], r13d
0x18009ead2  xorps   xmm0, xmm0
0x18009ead5  movups  [rbp+0D0h+var_E0], xmm0
0x18009ead9  xorps   xmm1, xmm1
0x18009eadc  movups  [rbp+0D0h+var_D0], xmm1
0x18009eae0  mov     [rbp+0D0h+var_110], r13
0x18009eae4  mov     [rbp+0D0h+var_108], r13
0x18009eae8  mov     [rbp+0D0h+var_138], r13
0x18009eaec  mov     [rbp+0D0h+var_130], r13
0x18009eaf0  mov     eax, 190h
0x18009eaf5  test    rbx, rbx
0x18009eaf8  jz      loc_18009F162
0x18009eafe  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009eb03  mov     eax, 191h
0x18009eb08  test    r14, r14
0x18009eb0b  jz      loc_18009F162
0x18009eb11  mov     r12d, r15d
0x18009eb14  mov     [rsp+1D0h+var_160], r13d
0x18009eb19  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009eb1e  lea     rcx, [rdi-50h]
0x18009eb22  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x18009eb27  lea     rsi, [rdi-78h]
0x18009eb2b  movups  xmm0, cs:?m_csUninitializedGid@CFileSyncItemMetadata@@1U_SYNC_GID@@B; _SYNC_GID const CFileSyncItemMetadata::m_csUninitializedGid
0x18009eb32  movups  xmmword ptr [rsi+10h], xmm0
0x18009eb36  movsd   xmm1, cs:qword_18015B9E8
0x18009eb3e  movsd   qword ptr [rsi+20h], xmm1
0x18009eb43  lea     rcx, [rdi-48h]
0x18009eb47  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x18009eb4c  lea     rcx, [rdi-40h]
0x18009eb50  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x18009eb55  and     r12d, 1
0x18009eb59  jz      short loc_18009EB86
0x18009eb5b  mov     rcx, [rdi-38h]
0x18009eb5f  mov     rax, [rcx]
0x18009eb62  mov     rdx, r14
0x18009eb65  mov     rax, [rax+40h]
0x18009eb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb6e  mov     [rsp+1D0h+var_160], eax
0x18009eb72  test    eax, eax
0x18009eb74  mov     eax, 19Ch
0x18009eb79  js      loc_18009F16A
0x18009eb7f  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009eb84  jmp     short loc_18009EB90
0x18009eb86  test    r15b, 2
0x18009eb8a  jz      loc_18009ECC5
0x18009eb90  mov     [rbp+0D0h+var_13C], r13d
0x18009eb94  mov     rax, [rsi]
0x18009eb97  lea     rdx, [rbp+0D0h+var_13C]
0x18009eb9b  mov     rcx, rsi
0x18009eb9e  mov     rax, [rax+28h]
0x18009eba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eba7  mov     [rsp+1D0h+var_160], eax
0x18009ebab  test    eax, eax
0x18009ebad  mov     eax, 1A4h
0x18009ebb2  js      loc_18009F16A
0x18009ebb8  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ebbd  mov     rcx, [rdi-38h]
0x18009ebc1  mov     rax, [rcx]
0x18009ebc4  mov     rdx, r14
0x18009ebc7  mov     rax, [rax+30h]
0x18009ebcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ebd0  mov     [rsp+1D0h+var_160], eax
0x18009ebd4  test    eax, eax
0x18009ebd6  mov     eax, 1A6h
0x18009ebdb  js      loc_18009F16A
0x18009ebe1  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ebe6  mov     [rbp+0D0h+nSize], 40h ; '@'
0x18009ebed  lea     r8, [rbp+0D0h+nSize]; nSize
0x18009ebf1  lea     rdx, [rbp+0D0h+Buffer]; lpBuffer
0x18009ebf5  mov     ecx, 1; NameType
0x18009ebfa  call    cs:__imp_GetComputerNameExW
0x18009ec00  test    eax, eax
0x18009ec02  jnz     short loc_18009EC17
0x18009ec04  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18009ec09  mov     [rsp+1D0h+var_160], eax
0x18009ec0d  mov     eax, 1AEh
0x18009ec12  jmp     loc_18009F16A
0x18009ec17  mov     [rsp+1D0h+var_160], r13d
0x18009ec1c  mov     eax, 1AEh
0x18009ec21  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ec26  mov     rcx, [rdi-38h]
0x18009ec2a  mov     rax, [rcx]
0x18009ec2d  lea     r8, [rbp+0D0h+Buffer]
0x18009ec31  lea     rdx, aLastupdatingde; "LastUpdatingDeviceName"
0x18009ec38  mov     rax, [rax+0C0h]
0x18009ec3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ec44  mov     [rsp+1D0h+var_160], eax
0x18009ec48  test    eax, eax
0x18009ec4a  mov     eax, 1AFh
0x18009ec4f  js      loc_18009F16A
0x18009ec55  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ec5a  cmp     [rbp+0D0h+var_13C], r13d
0x18009ec5e  jnz     short loc_18009ECC5
0x18009ec60  xorps   xmm0, xmm0
0x18009ec63  movups  xmmword ptr [rbp+0D0h+pguid.Data1], xmm0
0x18009ec67  mov     rax, [rdi-78h]
0x18009ec6b  lea     rdx, [rbp+0D0h+pguid]
0x18009ec6f  mov     rcx, rsi
0x18009ec72  mov     rax, [rax+128h]
0x18009ec79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ec7e  mov     [rsp+1D0h+var_160], eax
0x18009ec82  test    eax, eax
0x18009ec84  mov     eax, 1B8h
0x18009ec89  js      loc_18009F16A
0x18009ec8f  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ec94  or      [rbp+0D0h+pguid.Data1], 1
0x18009ec98  mov     rax, [rdi-78h]
0x18009ec9c  lea     rdx, [rbp+0D0h+pguid]
0x18009eca0  mov     rcx, rsi
0x18009eca3  mov     rax, [rax+120h]
0x18009ecaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ecaf  mov     [rsp+1D0h+var_160], eax
0x18009ecb3  test    eax, eax
0x18009ecb5  mov     eax, 1BAh
0x18009ecba  js      loc_18009F16A
0x18009ecc0  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ecc5  mov     rax, [rbx]
0x18009ecc8  lea     rdx, [rbp+0D0h+var_100]
0x18009eccc  mov     rcx, rbx
0x18009eccf  mov     rax, [rax+8]
0x18009ecd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ecd8  mov     [rsp+1D0h+var_160], eax
0x18009ecdc  test    eax, eax
0x18009ecde  mov     eax, 1BFh
0x18009ece3  js      loc_18009F16A
0x18009ece9  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ecee  mov     rcx, [rdi-38h]
0x18009ecf2  mov     rax, [rcx]
0x18009ecf5  mov     r8, [rbp+0D0h+var_100]
0x18009ecf9  lea     rdx, aFilename; "FileName"
0x18009ed00  mov     rax, [rax+0C0h]
0x18009ed07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ed0c  mov     [rsp+1D0h+var_160], eax
0x18009ed10  test    eax, eax
0x18009ed12  mov     eax, 1C0h
0x18009ed17  js      loc_18009F16A
0x18009ed1d  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ed22  mov     qword ptr [rbp+0D0h+nSize], r13
0x18009ed26  mov     rax, [rbx]
0x18009ed29  lea     rdx, [rbp+0D0h+var_E0]
0x18009ed2d  mov     rcx, rbx
0x18009ed30  mov     rax, [rax+50h]
0x18009ed34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ed39  mov     [rsp+1D0h+var_160], eax
0x18009ed3d  test    eax, eax
0x18009ed3f  mov     eax, 1C6h
0x18009ed44  jns     short loc_18009ED59
0x18009ed46  mov     word ptr [rsp+1D0h+var_15C+2], ax
0x18009ed4b  lea     rcx, [rbp+0D0h+nSize]
0x18009ed4f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009ed54  jmp     loc_18009F16F
0x18009ed59  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ed5e  lea     rdx, [rbp+0D0h+nSize]
0x18009ed62  lea     rcx, [rbp+0D0h+var_E0]
0x18009ed66  call    ?CreateInstance@?$CFileIDType@U_FILE_ID_128@@UINtfsBaseFileID128@@@@SAJAEBU_FILE_ID_128@@PEAPEAUINtfsBaseFileID128@@@Z; CFileIDType<_FILE_ID_128,INtfsBaseFileID128>::CreateInstance(_FILE_ID_128 const &,INtfsBaseFileID128 * *)
0x18009ed6b  mov     [rsp+1D0h+var_160], eax
0x18009ed6f  test    eax, eax
0x18009ed71  mov     eax, 1C9h
0x18009ed76  jns     short loc_18009ED7F
0x18009ed78  mov     word ptr [rsp+1D0h+var_15C+2], ax
0x18009ed7d  jmp     short loc_18009ED4B
0x18009ed7f  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ed84  mov     rax, [rdi-78h]
0x18009ed88  mov     rdx, qword ptr [rbp+0D0h+nSize]
0x18009ed8c  mov     rcx, rsi
0x18009ed8f  mov     rax, [rax+80h]
0x18009ed96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ed9b  mov     [rsp+1D0h+var_160], eax
0x18009ed9f  test    eax, eax
0x18009eda1  mov     eax, 1CCh
0x18009eda6  jns     short loc_18009EDAF
0x18009eda8  mov     word ptr [rsp+1D0h+var_15C+2], ax
0x18009edad  jmp     short loc_18009ED4B
0x18009edaf  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009edb4  lea     rcx, [rbp+0D0h+nSize]
0x18009edb8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009edbd  mov     rax, [rbx]
0x18009edc0  lea     rdx, [rbp+0D0h+var_138]
0x18009edc4  mov     rcx, rbx
0x18009edc7  mov     rax, [rax+20h]
0x18009edcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009edd0  mov     [rsp+1D0h+var_160], eax
0x18009edd4  test    eax, eax
0x18009edd6  jns     short loc_18009EDE2
0x18009edd8  mov     eax, 1D0h
0x18009eddd  jmp     loc_18009F16A
0x18009ede2  mov     [rsp+1D0h+var_160], r13d
0x18009ede7  mov     eax, 1D1h
0x18009edec  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009edf1  mov     rcx, [rdi-38h]
0x18009edf5  mov     r9, [rcx]
0x18009edf8  mov     r8d, dword ptr [rbp+0D0h+var_138+4]
0x18009edfc  shl     r8, 20h
0x18009ee00  mov     eax, dword ptr [rbp+0D0h+var_138]
0x18009ee03  add     r8, rax
0x18009ee06  lea     rdx, aCreationtime; "CreationTime"
0x18009ee0d  mov     rax, [r9+0E0h]
0x18009ee14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ee19  mov     [rsp+1D0h+var_160], eax
0x18009ee1d  test    eax, eax
0x18009ee1f  mov     eax, 1D2h
0x18009ee24  js      loc_18009F16A
0x18009ee2a  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ee2f  mov     rax, [rbx]
0x18009ee32  lea     rdx, [rbp+0D0h+var_130]
0x18009ee36  mov     rcx, rbx
0x18009ee39  mov     rax, [rax+28h]
0x18009ee3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ee42  mov     [rsp+1D0h+var_160], eax
0x18009ee46  test    eax, eax
0x18009ee48  jns     short loc_18009EE54
0x18009ee4a  mov     eax, 1D5h
0x18009ee4f  jmp     loc_18009F16A
0x18009ee54  mov     [rsp+1D0h+var_160], r13d
0x18009ee59  mov     eax, 1D6h
0x18009ee5e  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ee63  mov     rcx, [rdi-38h]
0x18009ee67  mov     r9, [rcx]
0x18009ee6a  mov     r8d, dword ptr [rbp+0D0h+var_130+4]
0x18009ee6e  shl     r8, 20h
0x18009ee72  mov     eax, dword ptr [rbp+0D0h+var_130]
0x18009ee75  add     r8, rax
0x18009ee78  lea     rdx, aLastwritetime; "LastWriteTime"
0x18009ee7f  mov     rax, [r9+0E0h]
0x18009ee86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ee8b  mov     [rsp+1D0h+var_160], eax
0x18009ee8f  test    eax, eax
0x18009ee91  mov     eax, 1D7h
0x18009ee96  js      loc_18009F16A
0x18009ee9c  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009eea1  mov     rax, [rbx]
0x18009eea4  lea     rdx, [rbp+0D0h+var_140]
0x18009eea8  mov     rcx, rbx
0x18009eeab  mov     rax, [rax+40h]
0x18009eeaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eeb4  mov     [rsp+1D0h+var_160], eax
0x18009eeb8  test    eax, eax
0x18009eeba  mov     eax, 1DAh
0x18009eebf  js      loc_18009F16A
0x18009eec5  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009eeca  mov     rcx, [rdi-38h]
0x18009eece  mov     rax, [rcx]
0x18009eed1  mov     r8d, [rbp+0D0h+var_140]
0x18009eed5  and     r8d, 17h
0x18009eed9  lea     rdx, aAttributes; "Attributes"
0x18009eee0  mov     rax, [rax+0D8h]
0x18009eee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eeec  mov     [rsp+1D0h+var_160], eax
0x18009eef0  test    eax, eax
0x18009eef2  mov     eax, 1DBh
0x18009eef7  js      loc_18009F16A
0x18009eefd  mov     word ptr [rsp+1D0h+var_15C], ax
0x18009ef02  mov     rax, [rbx]
0x18009ef05  lea     rdx, [rbp+0D0h+var_F8]
0x18009ef09  mov     rcx, rbx
0x18009ef0c  mov     rax, [rax+38h]
  ... truncated ...
```
