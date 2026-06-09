# RdVhd::Uvhd::CUvhdDiskManager::CreateUvhdTemplate(ushort const *,ulong)

- ea: `0x180051560`
- end: `0x180051c5e`
- name: `?CreateUvhdTemplate@CUvhdDiskManager@Uvhd@RdVhd@@UEBAJPEBGK@Z`
- size: `1790`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdDiskManager *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004db0`
- `0x180012d7c`
- `0x1800141e8`
- `0x180019b38`
- `0x18003114c`
- `0x180035d40`
- `0x180043df0`
- `0x1800488e4`
- `0x180048ab0`
- `0x180048b28`
- `0x18004a240`
- `0x18004b0a4`
- `0x18004b600`
- `0x18004b68c`
- `0x180051560`
- `0x180054780`
- `0x180057b48`
- `0x180057f00`
- `0x180058080`
- `0x1800585c4`
- `0x1800589c8`
- `0x180059060`
- `0x1800598a8`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800517e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800517e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051881`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051926`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800515f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051ba9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800515f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051ba9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005186e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005186e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800517c3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800517c3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800517da`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800519cf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180051b8a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800517da`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800519cf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180051b8a`

## string_xrefs

- `0x1800518b9`: `Failed ::CreateFileW(%s)`
- `0x18005176f`: `UVHD-template.vhdx`
- `0x180051c08`: `(UVHD) User VHD template creation`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::CreateUvhdTemplate(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  RdVhd::Util::CVhdCreator *v6; // r13
  RdVhd::Uvhd::CUvhdDiskManager *v7; // rcx
  __int64 v8; // rdx
  const wchar_t *v9; // r9
  signed int v10; // ebx
  int v11; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  const unsigned __int16 *v15; // rax
  const WCHAR *v16; // rax
  const WCHAR *v17; // rax
  signed int LastError; // eax
  const WCHAR *v19; // rax
  HANDLE FileW; // r15
  signed int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  const unsigned __int16 *v24; // rax
  RdVhd::Util::CVhdHelper *v25; // rcx
  const WCHAR *v26; // rax
  int v27; // eax
  const unsigned __int16 *v28; // rax
  int v29; // r9d
  int v30; // eax
  RdVhd::Util::CVhdCreator *v31; // rcx
  RdVhd::Uvhd::CUvhdDiskManager *v32; // rcx
  __int64 v33; // rdx
  const unsigned __int16 *v34; // r8
  int v35; // r9d
  int v36; // eax
  const WCHAR *v37; // rax
  DWORD v38; // eax
  unsigned int v39; // r8d
  struct IVdsVDisk *v41; // [rsp+40h] [rbp-79h] BYREF
  struct IVdsDisk *v42; // [rsp+48h] [rbp-71h] BYREF
  void **v43; // [rsp+50h] [rbp-69h] BYREF
  int v44; // [rsp+58h] [rbp-61h]
  __int64 v45; // [rsp+5Ch] [rbp-5Dh]
  int v46; // [rsp+64h] [rbp-55h]
  __int64 v47; // [rsp+68h] [rbp-51h]
  int v48; // [rsp+70h] [rbp-49h]
  struct _GUID v49; // [rsp+80h] [rbp-39h] BYREF
  void **v50; // [rsp+90h] [rbp-29h] BYREF
  int v51; // [rsp+98h] [rbp-21h]
  __int64 v52; // [rsp+9Ch] [rbp-1Dh]
  int v53; // [rsp+A4h] [rbp-15h]
  __int64 v54; // [rsp+A8h] [rbp-11h]
  int v55; // [rsp+B0h] [rbp-9h]
  void **v56; // [rsp+B8h] [rbp-1h] BYREF
  int v57; // [rsp+C0h] [rbp+7h]
  __int64 v58; // [rsp+C4h] [rbp+Bh]
  int v59; // [rsp+CCh] [rbp+13h]
  __int64 v60; // [rsp+D0h] [rbp+17h]
  int v61; // [rsp+D8h] [rbp+1Fh]
  DWORD TickCount; // [rsp+128h] [rbp+6Fh]
  RdVhd::Util::CVhdCreator *v63; // [rsp+138h] [rbp+7Fh] BYREF

  v52 = 128;
  v54 = 0;
  v53 = 0;
  v51 = 0;
  v49 = GUID_NULL;
  v55 = 0x8000000;
  v50 = &CPathString::`vftable';
  v45 = 128;
  v6 = 0;
  v47 = 0;
  v46 = 0;
  v48 = 0x8000000;
  v44 = 0;
  v43 = &CPathString::`vftable';
  v58 = 128;
  v60 = 0;
  v59 = 0;
  v61 = 0x8000000;
  v57 = 0;
  v56 = &CPathString::`vftable';
  v42 = 0;
  v41 = 0;
  v63 = 0;
  TickCount = GetTickCount();
  if ( !a2 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v8 = 16;
    v9 = L"szUvhdShareUrl";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v7 + 2), v8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v9);
LABEL_7:
    v10 = -2147024809;
LABEL_103:
    v37 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v43);
    DeleteFileW(v37);
    goto LABEL_104;
  }
  if ( !a3 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v8 = 17;
    v9 = L"dwUvhdMaxSizeInGB > 0";
    goto LABEL_6;
  }
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
      a3,
      (__int64)a2);
  }
  v11 = CBaseStringT<unsigned short>::Append(&v50, a2);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_103;
    }
    v13 = 19;
    goto LABEL_22;
  }
  if ( !(unsigned int)CPathString::IsUNC((CPathString *)&v50) )
  {
    v15 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v50);
    v11 = RdVhd::Uvhd::CUvhdDiskManager::SetLocalUvhdStoragePermissions(this, v15);
    v10 = v11;
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      v13 = 20;
      goto LABEL_22;
    }
  }
  v11 = CPathString::BuildPath((CPathString *)&v43, (const struct CPathString *)&v50, L"UVHD-template.vhdx");
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_103;
    }
    v13 = 21;
    goto LABEL_22;
  }
  v16 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v43);
  if ( GetFileAttributesW(v16) != -1 )
  {
    v17 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v43);
    if ( !DeleteFileW(v17) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError && (LastError & 0xFFFF0000) == 0 )
      {
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        v10 = v10 & 0x8000FFFF | 0x504A0000;
      }
      if ( v10 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_103;
        }
        v13 = 22;
        v14 = (unsigned int)v10;
        goto LABEL_23;
      }
    }
  }
  v19 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v43);
  FileW = CreateFileW(v19, 0x1F01FFu, 0, 0, 2u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v21 = GetLastError();
    v10 = v21;
    if ( v21 && (v21 & 0xFFFF0000) == 0 )
    {
      if ( v21 > 0 )
        v10 = (unsigned __int16)v21 | 0x80070000;
      v10 = v10 & 0x8000FFFF | 0x504B0000;
    }
    v22 = CBaseStringT<unsigned short>::PContents(&v43);
    _TraceNrmRdvVmEx(L"UVHD", v10, L"Failed ::CreateFileW(%s)", v22);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = CBaseStringT<unsigned short>::PContents(&v43);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
          v23,
          v10);
      }
      goto LABEL_103;
    }
  }
  CloseHandle(FileW);
  if ( (unsigned int)CPathString::IsUNC((CPathString *)&v43) )
  {
    v24 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v43);
    v11 = RdVhd::Util::CVhdHelper::TranslateLoopbackPath(v25, v24, (struct CPathString *)&v56);
    v10 = v11;
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      v13 = 25;
LABEL_22:
      v14 = (unsigned int)v11;
LABEL_23:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v14);
      goto LABEL_103;
    }
  }
  else
  {
    v11 = CBaseStringT<unsigned short>::Set<unsigned short>(&v56, &v43);
    v10 = v11;
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      v13 = 24;
      goto LABEL_22;
    }
  }
  v26 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v43);
  DeleteFileW(v26);
  v27 = RdVhd::Util::CVhdCreator::CreateInstance(&v63);
  v10 = v27;
  if ( v27 < 0 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
        (unsigned int)v27);
    }
    v6 = v63;
    goto LABEL_103;
  }
  v28 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v56);
  v6 = v63;
  v11 = RdVhd::Util::CVhdCreator::CreateVhdx(v63, v28, a3, v29, &v41);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_103;
    }
    v13 = 27;
    goto LABEL_22;
  }
  v11 = RdVhd::Util::CVhdCreator::AttachVhd(v6, v41, &v42);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_103;
    }
    v13 = 28;
    goto LABEL_22;
  }
  v30 = RdVhd::Util::CVhdCreator::InitializeBasicDisk(v6, v42);
  v10 = v30;
  if ( v30 >= 0 )
  {
    v30 = RdVhd::Util::CVhdCreator::CreatePrimaryPartition(v31, v42, &v49);
    v10 = v30;
    if ( v30 >= 0 )
    {
      v30 = RdVhd::Util::CVhdCreator::FormatVolumeNtfs(v6, &v49, v34, v35);
      v10 = v30;
      if ( v30 < 0 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v33 = 31;
          goto LABEL_100;
        }
      }
    }
    else
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v33 = 30;
        goto LABEL_100;
      }
    }
  }
  else
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = 29;
LABEL_100:
      WPP_SF_d(*((_QWORD *)v32 + 2), v33, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, (unsigned int)v30);
    }
  }
  v36 = RdVhd::Util::CVhdCreator::DetachVhd(v32, v41);
  if ( v10 < 0 )
    goto LABEL_103;
  v10 = v36;
  if ( v36 < 0 )
    goto LABEL_103;
LABEL_104:
  if ( v6 )
    (**(void (__fastcall ***)(RdVhd::Util::CVhdCreator *, __int64))v6)(v6, 1);
  v38 = GetTickCount();
  v39 = v38 - TickCount;
  if ( v38 < TickCount )
    v39 = v38 - TickCount - 1;
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Sdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
      (unsigned int)L"(UVHD) User VHD template creation",
      v39 / 0x3E8,
      v39 % 0x3E8);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  CPathString::~CPathString((CPathString *)&v56);
  CPathString::~CPathString((CPathString *)&v43);
  CPathString::~CPathString((CPathString *)&v50);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180051560  mov     [rsp-8+arg_0], rbx
0x180051565  push    rbp
0x180051566  push    rsi
0x180051567  push    rdi
0x180051568  push    r12
0x18005156a  push    r13
0x18005156c  push    r14
0x18005156e  push    r15
0x180051570  lea     rbp, [rsp-27h]
0x180051575  sub     rsp, 0E0h
0x18005157c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180051583  xor     edi, edi
0x180051585  mov     [rbp+57h+var_74], 80h
0x18005158d  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180051594  mov     [rbp+57h+var_68], rdi
0x180051598  mov     r15, rcx
0x18005159b  mov     [rbp+57h+var_6C], edi
0x18005159e  mov     ecx, 8000000h
0x1800515a3  mov     [rbp+57h+var_78], edi
0x1800515a6  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800515ab  mov     r12d, r8d
0x1800515ae  mov     [rbp+57h+var_60], ecx
0x1800515b1  mov     rbx, rdx
0x1800515b4  mov     [rbp+57h+var_80], rax
0x1800515b8  mov     [rbp+57h+var_B4], 80h
0x1800515c0  mov     r13d, edi
0x1800515c3  mov     [rbp+57h+var_A8], rdi
0x1800515c7  mov     [rbp+57h+var_AC], edi
0x1800515ca  mov     [rbp+57h+var_A0], ecx
0x1800515cd  mov     [rbp+57h+var_B8], edi
0x1800515d0  mov     [rbp+57h+var_C0], rax
0x1800515d4  mov     [rbp+57h+var_4C], 80h
0x1800515dc  mov     [rbp+57h+var_40], rdi
0x1800515e0  mov     [rbp+57h+var_44], edi
0x1800515e3  mov     [rbp+57h+var_38], ecx
0x1800515e6  mov     [rbp+57h+var_50], edi
0x1800515e9  mov     [rbp+57h+var_58], rax
0x1800515ed  mov     [rbp+57h+var_C8], rdi
0x1800515f1  mov     [rbp+57h+var_D0], rdi
0x1800515f5  mov     [rbp+57h+arg_18], rdi
0x1800515f9  call    cs:__imp_GetTickCount
0x1800515ff  mov     [rbp+57h+arg_8], eax
0x180051602  test    rbx, rbx
0x180051605  jnz     short loc_180051650
0x180051607  mov     rcx, cs:WPP_GLOBAL_Control
0x18005160e  lea     rsi, WPP_GLOBAL_Control
0x180051615  lea     r14, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x18005161c  mov     dil, 4
0x18005161f  cmp     rcx, rsi
0x180051622  jz      short loc_180051646
0x180051624  test    [rcx+1Ch], dil
0x180051628  jz      short loc_180051646
0x18005162a  cmp     byte ptr [rcx+19h], 2
0x18005162e  jb      short loc_180051646
0x180051630  lea     edx, [rbx+10h]
0x180051633  lea     r9, aSzuvhdshareurl; "szUvhdShareUrl"
0x18005163a  mov     rcx, [rcx+10h]
0x18005163e  mov     r8, r14
0x180051641  call    WPP_SF_S
0x180051646  mov     ebx, 80070057h
0x18005164b  jmp     loc_180051B7E
0x180051650  test    r12d, r12d
0x180051653  jnz     short loc_18005168C
0x180051655  mov     rcx, cs:WPP_GLOBAL_Control
0x18005165c  lea     rsi, WPP_GLOBAL_Control
0x180051663  lea     r14, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x18005166a  mov     dil, 4
0x18005166d  cmp     rcx, rsi
0x180051670  jz      short loc_180051646
0x180051672  test    [rcx+1Ch], dil
0x180051676  jz      short loc_180051646
0x180051678  cmp     byte ptr [rcx+19h], 2
0x18005167c  jb      short loc_180051646
0x18005167e  lea     edx, [r12+11h]
0x180051683  lea     r9, aDwuvhdmaxsizei; "dwUvhdMaxSizeInGB > 0"
0x18005168a  jmp     short loc_18005163A
0x18005168c  mov     rcx, cs:WPP_GLOBAL_Control
0x180051693  lea     rsi, WPP_GLOBAL_Control
0x18005169a  lea     r14, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800516a1  mov     dil, 4
0x1800516a4  cmp     rcx, rsi
0x1800516a7  jz      short loc_1800516CE
0x1800516a9  test    [rcx+1Ch], dil
0x1800516ad  jz      short loc_1800516CE
0x1800516af  cmp     [rcx+19h], dil
0x1800516b3  jb      short loc_1800516CE
0x1800516b5  mov     rcx, [rcx+10h]
0x1800516b9  mov     edx, 12h
0x1800516be  mov     r9d, r12d
0x1800516c1  mov     qword ptr [rsp+110h+dwCreationDisposition], rbx
0x1800516c6  mov     r8, r14
0x1800516c9  call    WPP_SF_dS
0x1800516ce  mov     rdx, rbx
0x1800516d1  lea     rcx, [rbp+57h+var_80]
0x1800516d5  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x1800516da  mov     ebx, eax
0x1800516dc  test    eax, eax
0x1800516de  jns     short loc_18005171D
0x1800516e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800516e7  cmp     rcx, rsi
0x1800516ea  jz      loc_180051B7E
0x1800516f0  test    [rcx+1Ch], dil
0x1800516f4  jz      loc_180051B7E
0x1800516fa  cmp     byte ptr [rcx+19h], 2
0x1800516fe  jb      loc_180051B7E
0x180051704  mov     edx, 13h
0x180051709  mov     r9d, eax
0x18005170c  mov     rcx, [rcx+10h]
0x180051710  mov     r8, r14
0x180051713  call    WPP_SF_d
0x180051718  jmp     loc_180051B7E
0x18005171d  lea     rcx, [rbp+57h+var_80]; this
0x180051721  call    ?IsUNC@CPathString@@QEAAHXZ; CPathString::IsUNC(void)
0x180051726  test    eax, eax
0x180051728  jnz     short loc_18005176F
0x18005172a  lea     rcx, [rbp+57h+var_80]
0x18005172e  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180051733  mov     rdx, rax; unsigned __int16 *
0x180051736  mov     rcx, r15; this
0x180051739  call    ?SetLocalUvhdStoragePermissions@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBG@Z; RdVhd::Uvhd::CUvhdDiskManager::SetLocalUvhdStoragePermissions(ushort const *)
0x18005173e  mov     ebx, eax
0x180051740  test    eax, eax
0x180051742  jns     short loc_18005176F
0x180051744  mov     rcx, cs:WPP_GLOBAL_Control
0x18005174b  cmp     rcx, rsi
0x18005174e  jz      loc_180051B7E
0x180051754  test    [rcx+1Ch], dil
0x180051758  jz      loc_180051B7E
0x18005175e  cmp     byte ptr [rcx+19h], 2
0x180051762  jb      loc_180051B7E
0x180051768  mov     edx, 14h
0x18005176d  jmp     short loc_180051709
0x18005176f  lea     r8, aUvhdTemplateVh; "UVHD-template.vhdx"
0x180051776  lea     rdx, [rbp+57h+var_80]; struct CPathString *
0x18005177a  lea     rcx, [rbp+57h+var_C0]; this
0x18005177e  call    ?BuildPath@CPathString@@QEAAJAEBV1@PEBG@Z; CPathString::BuildPath(CPathString const &,ushort const *)
0x180051783  mov     ebx, eax
0x180051785  test    eax, eax
0x180051787  jns     short loc_1800517B7
0x180051789  mov     rcx, cs:WPP_GLOBAL_Control
0x180051790  cmp     rcx, rsi
0x180051793  jz      loc_180051B7E
0x180051799  test    [rcx+1Ch], dil
0x18005179d  jz      loc_180051B7E
0x1800517a3  cmp     byte ptr [rcx+19h], 2
0x1800517a7  jb      loc_180051B7E
0x1800517ad  mov     edx, 15h
0x1800517b2  jmp     loc_180051709
0x1800517b7  lea     rcx, [rbp+57h+var_C0]
0x1800517bb  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800517c0  mov     rcx, rax; lpFileName
0x1800517c3  call    cs:__imp_GetFileAttributesW
0x1800517c9  cmp     eax, 0FFFFFFFFh
0x1800517cc  jz      short loc_180051845
0x1800517ce  lea     rcx, [rbp+57h+var_C0]
0x1800517d2  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800517d7  mov     rcx, rax; lpFileName
0x1800517da  call    cs:__imp_DeleteFileW
0x1800517e0  test    eax, eax
0x1800517e2  jnz     short loc_180051845
0x1800517e4  call    cs:__imp_GetLastError
0x1800517ea  mov     ebx, eax
0x1800517ec  test    eax, eax
0x1800517ee  jz      short loc_180051810
0x1800517f0  test    eax, 0FFFF0000h
0x1800517f5  jnz     short loc_180051810
0x1800517f7  test    eax, eax
0x1800517f9  jle     short loc_180051804
0x1800517fb  movzx   ebx, ax
0x1800517fe  or      ebx, 80070000h
0x180051804  and     ebx, 0D04AFFFFh
0x18005180a  or      ebx, 504A0000h
0x180051810  test    ebx, ebx
0x180051812  jns     short loc_180051845
0x180051814  mov     rcx, cs:WPP_GLOBAL_Control
0x18005181b  cmp     rcx, rsi
0x18005181e  jz      loc_180051B7E
0x180051824  test    [rcx+1Ch], dil
0x180051828  jz      loc_180051B7E
0x18005182e  cmp     byte ptr [rcx+19h], 2
0x180051832  jb      loc_180051B7E
0x180051838  mov     edx, 16h
0x18005183d  mov     r9d, ebx
0x180051840  jmp     loc_18005170C
0x180051845  lea     rcx, [rbp+57h+var_C0]
0x180051849  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18005184e  mov     [rsp+110h+hTemplateFile], r13; hTemplateFile
0x180051853  mov     rcx, rax; lpFileName
0x180051856  mov     [rsp+110h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18005185b  xor     r9d, r9d; lpSecurityAttributes
0x18005185e  xor     r8d, r8d; dwShareMode
0x180051861  mov     [rsp+110h+dwCreationDisposition], 2; dwCreationDisposition
0x180051869  mov     edx, 1F01FFh; dwDesiredAccess
0x18005186e  call    cs:__imp_CreateFileW
0x180051874  mov     r15, rax
0x180051877  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005187b  jnz     loc_180051923
0x180051881  call    cs:__imp_GetLastError
0x180051887  mov     ebx, eax
0x180051889  test    eax, eax
0x18005188b  jz      short loc_1800518AD
0x18005188d  test    eax, 0FFFF0000h
0x180051892  jnz     short loc_1800518AD
0x180051894  test    eax, eax
0x180051896  jle     short loc_1800518A1
0x180051898  movzx   ebx, ax
0x18005189b  or      ebx, 80070000h
0x1800518a1  and     ebx, 0D04BFFFFh
0x1800518a7  or      ebx, 504B0000h
0x1800518ad  lea     rcx, [rbp+57h+var_C0]
0x1800518b1  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800518b6  mov     r9, rax
0x1800518b9  lea     r8, aFailedCreatefi; "Failed ::CreateFileW(%s)"
0x1800518c0  mov     edx, ebx; int
0x1800518c2  lea     rcx, aUvhd; "UVHD"
0x1800518c9  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800518ce  test    ebx, ebx
0x1800518d0  jns     short loc_180051923
0x1800518d2  mov     rax, cs:WPP_GLOBAL_Control
0x1800518d9  cmp     rax, rsi
0x1800518dc  jz      loc_180051B7E
0x1800518e2  test    [rax+1Ch], dil
0x1800518e6  jz      loc_180051B7E
0x1800518ec  cmp     byte ptr [rax+19h], 2
0x1800518f0  jb      loc_180051B7E
0x1800518f6  lea     rcx, [rbp+57h+var_C0]
0x1800518fa  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800518ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180051906  mov     edx, 17h
0x18005190b  mov     r9, rax
0x18005190e  mov     [rsp+110h+dwCreationDisposition], ebx
0x180051912  mov     r8, r14
0x180051915  mov     rcx, [rcx+10h]
0x180051919  call    WPP_SF_Sd
0x18005191e  jmp     loc_180051B7E
0x180051923  mov     rcx, r15; hObject
0x180051926  call    cs:__imp_CloseHandle
0x18005192c  lea     rcx, [rbp+57h+var_C0]; this
0x180051930  call    ?IsUNC@CPathString@@QEAAHXZ; CPathString::IsUNC(void)
0x180051935  test    eax, eax
0x180051937  jnz     short loc_18005197A
0x180051939  lea     rdx, [rbp+57h+var_C0]
0x18005193d  lea     rcx, [rbp+57h+var_58]
0x180051941  call    ??$Set@G@?$CBaseStringT@G@@QEAAJAEBV0@@Z; CBaseStringT<ushort>::Set<ushort>(CBaseStringT<ushort> const &)
0x180051946  mov     ebx, eax
0x180051948  test    eax, eax
0x18005194a  jns     short loc_1800519C3
0x18005194c  mov     rcx, cs:WPP_GLOBAL_Control
0x180051953  cmp     rcx, rsi
0x180051956  jz      loc_180051B7E
0x18005195c  test    [rcx+1Ch], dil
0x180051960  jz      loc_180051B7E
0x180051966  cmp     byte ptr [rcx+19h], 2
0x18005196a  jb      loc_180051B7E
0x180051970  mov     edx, 18h
0x180051975  jmp     loc_180051709
0x18005197a  lea     rcx, [rbp+57h+var_C0]
0x18005197e  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180051983  mov     rdx, rax; unsigned __int16 *
0x180051986  lea     r8, [rbp+57h+var_58]; struct CPathString *
0x18005198a  call    ?TranslateLoopbackPath@CVhdHelper@Util@RdVhd@@QEBAJPEBGPEAVCPathString@@@Z; RdVhd::Util::CVhdHelper::TranslateLoopbackPath(ushort const *,CPathString *)
0x18005198f  mov     ebx, eax
0x180051991  test    eax, eax
0x180051993  jns     short loc_1800519C3
0x180051995  mov     rcx, cs:WPP_GLOBAL_Control
0x18005199c  cmp     rcx, rsi
0x18005199f  jz      loc_180051B7E
0x1800519a5  test    [rcx+1Ch], dil
0x1800519a9  jz      loc_180051B7E
0x1800519af  cmp     byte ptr [rcx+19h], 2
0x1800519b3  jb      loc_180051B7E
0x1800519b9  mov     edx, 19h
0x1800519be  jmp     loc_180051709
0x1800519c3  lea     rcx, [rbp+57h+var_C0]
0x1800519c7  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800519cc  mov     rcx, rax; lpFileName
0x1800519cf  call    cs:__imp_DeleteFileW
0x1800519d5  lea     rcx, [rbp+57h+arg_18]; struct RdVhd::Util::CVhdCreator **
0x1800519d9  call    ?CreateInstance@CVhdCreator@Util@RdVhd@@SAJPEAPEAV123@@Z; RdVhd::Util::CVhdCreator::CreateInstance(RdVhd::Util::CVhdCreator * *)
0x1800519de  mov     ebx, eax
0x1800519e0  test    eax, eax
0x1800519e2  jns     short loc_180051A19
0x1800519e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800519eb  cmp     rcx, rsi
0x1800519ee  jz      short loc_180051A10
0x1800519f0  test    [rcx+1Ch], dil
0x1800519f4  jz      short loc_180051A10
0x1800519f6  cmp     byte ptr [rcx+19h], 2
0x1800519fa  jb      short loc_180051A10
0x1800519fc  mov     rcx, [rcx+10h]
0x180051a00  mov     edx, 1Ah
0x180051a05  mov     r9d, eax
0x180051a08  mov     r8, r14
0x180051a0b  call    WPP_SF_d
0x180051a10  mov     r13, [rbp+57h+arg_18]
0x180051a14  jmp     loc_180051B7E
0x180051a19  lea     rcx, [rbp+57h+var_58]
0x180051a1d  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180051a22  mov     r13, [rbp+57h+arg_18]
0x180051a26  lea     rcx, [rbp+57h+var_D0]
  ... truncated ...
```
