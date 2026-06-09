# RdVhd::Uvhd::CUvhdDiskManager::AttachCloudUvhdForUser(ushort const *,ushort const *,ushort const *,ulong *,CPathString *)

- ea: `0x180050360`
- end: `0x180050935`
- name: `?AttachCloudUvhdForUser@CUvhdDiskManager@Uvhd@RdVhd@@UEBAJPEBG00PEAKPEAVCPathString@@@Z`
- size: `1493`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdDiskManager *this, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, unsigned int *, struct CPathString *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x1800141e8`
- `0x180019b38`
- `0x18001a280`
- `0x18001a8d0`
- `0x18001ad5c`
- `0x180048180`
- `0x18004876c`
- `0x1800488e4`
- `0x180048ab0`
- `0x180049470`
- `0x180050360`
- `0x180051c70`
- `0x1800549f8`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050563`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050563`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050902`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005057c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005057c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005052d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005052d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800503bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005041d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800508f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800503bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005041d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800508f7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005053c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005053c`

## string_xrefs

- `0x180050454`: `szUserSID`
- `0x1800504cd`: `pstrUvhdVolumeGuidPath`
- `0x180050559`: `MountXDrive`
- `0x180050594`: `[%s] Failed to find MountXDrive function call.`
- `0x180050618`: `[%s] Unable to mount the disk for the user`
- `0x1800506c4`: `[%s] User has a mounted Xdrive [%d]`
- `0x1800507bf`: `[%s] User Xdrive is online and ready`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::AttachCloudUvhdForUser(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        struct CPathString *a6)
{
  unsigned __int16 *v8; // rbx
  RdVhd::Uvhd::CUvhdDiskManager *v9; // rcx
  __int64 v10; // rdx
  const wchar_t *v11; // r9
  signed int v12; // edi
  HMODULE LibraryW; // rdi
  const unsigned __int16 *v14; // r12
  FARPROC ProcAddress; // r14
  signed int LastError; // eax
  const unsigned __int16 *v17; // r9
  RdVhd::Uvhd::CUvhdDiskManager *v18; // rcx
  int v19; // edx
  int v20; // r9d
  int v21; // eax
  const unsigned __int16 *v22; // r9
  int v23; // eax
  unsigned int v24; // eax
  const unsigned __int16 *v25; // r9
  RdVhd::Util::CVhdHelper *v26; // rcx
  int FirstVolumeForDiskNumber; // eax
  int v28; // edx
  int v29; // r8d
  const unsigned __int16 *v30; // r9
  const unsigned __int16 *v31; // r9
  const unsigned __int16 *v32; // rax
  int v33; // eax
  __int64 v34; // rax
  const unsigned __int16 *v35; // rax
  int v36; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v37; // rcx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int v40; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  RdVhd::Uvhd::CUvhdDiskManager *v42; // [rsp+50h] [rbp-B0h]
  HMODULE hLibModule; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v44; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v45; // [rsp+68h] [rbp-98h]
  WCHAR LibFileName[264]; // [rsp+70h] [rbp-90h] BYREF

  v40 = 0;
  *(_QWORD *)pcbData = 0;
  v44 = a4;
  v45 = a3;
  v42 = this;
  GetTickCount();
  PIIHandler::Set((PIIHandler *)pcbData, a2);
  v8 = *(unsigned __int16 **)pcbData;
  if ( a2 )
  {
    if ( !a3 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      v10 = 210;
      v11 = L"szUserSID";
      goto LABEL_6;
    }
    if ( !a5 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      v10 = 211;
      v11 = L"pulDiskNumber";
      goto LABEL_6;
    }
    if ( !a6 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      v10 = 212;
      v11 = L"pstrUvhdVolumeGuidPath";
      goto LABEL_6;
    }
    memset_0(LibFileName, 0, 0x208u);
    pcbData[0] = 520;
    hLibModule = 0;
    LibraryW = 0;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\CloudSettings",
            L"RdvCloud",
            2u,
            0,
            LibFileName,
            pcbData) )
    {
      LibraryW = LoadLibraryW(LibFileName);
      hLibModule = LibraryW;
    }
    if ( !LibraryW )
    {
      v12 = -2147418113;
      goto LABEL_8;
    }
    v14 = &qword_180063A68;
    ProcAddress = GetProcAddress(LibraryW, "MountXDrive");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      v17 = &qword_180063A68;
      if ( v8 )
        v17 = v8;
      _TraceNrmRdvVmEx(L"UVHD", v12, L"[%s] Failed to find MountXDrive function call.", v17);
      if ( v12 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_93;
        }
        v19 = 213;
        goto LABEL_38;
      }
    }
    v21 = ((__int64 (__fastcall *)(const unsigned __int16 *, unsigned int *))ProcAddress)(v44, &v40);
    v22 = &qword_180063A68;
    if ( v8 )
      v22 = v8;
    v12 = v21;
    _TraceNrmRdvVmEx(L"UVHD", v21, L"[%s] Unable to mount the disk for the user", v22);
    if ( v23 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_93;
      }
      v19 = 214;
      goto LABEL_38;
    }
    v24 = v40;
    *a5 = v40;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        215,
        (unsigned int)WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
        (_DWORD)a2,
        v24);
      v24 = v40;
    }
    LODWORD(pdwType) = v24;
    v25 = &qword_180063A68;
    if ( v8 )
      v25 = v8;
    _TraceNrmRdvVmEx(L"UVHD", v12, L"[%s] User has a mounted Xdrive [%d]", v25, pdwType);
    FirstVolumeForDiskNumber = RdVhd::Util::CVhdHelper::FindFirstVolumeForDiskNumber(v26, v40, a6);
    v12 = FirstVolumeForDiskNumber;
    if ( FirstVolumeForDiskNumber < 0 )
    {
      v28 = HIWORD(FirstVolumeForDiskNumber) & 0x7FF;
      if ( (FirstVolumeForDiskNumber & 0x78000000) != 0x50000000 )
        v28 = 0;
      if ( !v28 )
      {
        v29 = (FirstVolumeForDiskNumber >> 16) & 0x1FFF;
        if ( v29 == 7 || !v29 && (FirstVolumeForDiskNumber & 0x10000000) == 0 )
        {
          v12 = (unsigned __int16)FirstVolumeForDiskNumber;
          if ( (_WORD)FirstVolumeForDiskNumber )
            v12 = (unsigned __int16)FirstVolumeForDiskNumber | 0xD0910000;
        }
      }
    }
    v30 = &qword_180063A68;
    if ( v8 )
      v30 = v8;
    _TraceNrmRdvVmEx(L"UVHD", v12, L"[%s] Unable to find a valid volume in this UVHD", v30);
    if ( v12 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_93;
      }
      v19 = 216;
LABEL_38:
      v20 = (int)a2;
LABEL_39:
      WPP_SF_Sd(*((_QWORD *)v18 + 2), v19, (unsigned int)WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v20, v12);
LABEL_93:
      GetTickCount();
      FreeLibrary(hLibModule);
      goto LABEL_94;
    }
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, a2);
    }
    v31 = &qword_180063A68;
    if ( v8 )
      v31 = v8;
    _TraceNrmRdvVmEx(L"UVHD", v12, L"[%s] User Xdrive is online and ready", v31);
    v32 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(a6);
    v12 = RdVhd::Uvhd::CUvhdDiskManager::SetUvhdVolumePermissions(v42, v45, v32);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_93;
      }
      v33 = CBaseStringT<unsigned short>::PContents(a6);
      v18 = WPP_GLOBAL_Control;
      v19 = 218;
      v20 = v33;
      goto LABEL_39;
    }
    v34 = CBaseStringT<unsigned short>::PContents(a6);
    _TraceNrmRdvVmEx(L"UVHD", v12, L"SetUvhdVolumePermissions(%s)", v34);
    v35 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(a6);
    v36 = RdVhd::Uvhd::CUvhdDiskManager::DeleteUvhdMountPoints(v42, v35);
    if ( v36 < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control )
      {
LABEL_90:
        if ( v8 )
          v14 = v8;
        _TraceNrmRdvVmEx(L"UVHD", v12, L"[%s] Userdisk correctly setup", v14);
        goto LABEL_93;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
LABEL_86:
        if ( v37 != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)v37 + 28) & 4) != 0
          && *((_BYTE *)v37 + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)v37 + 2), 220, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, a2);
        }
        goto LABEL_90;
      }
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        219,
        WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
        (unsigned int)v36,
        v12);
    }
    v37 = WPP_GLOBAL_Control;
    goto LABEL_86;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_7;
  }
  v10 = 209;
  v11 = L"szUserUPN";
LABEL_6:
  WPP_SF_S(*((_QWORD *)v9 + 2), v10, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v11);
LABEL_7:
  v12 = -2147024809;
LABEL_8:
  GetTickCount();
LABEL_94:
  operator delete(v8);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180050360  push    rbp
0x180050362  push    rbx
0x180050363  push    rsi
0x180050364  push    rdi
0x180050365  push    r12
0x180050367  push    r13
0x180050369  push    r14
0x18005036b  push    r15
0x18005036d  lea     rbp, [rsp-198h]
0x180050375  sub     rsp, 298h
0x18005037c  mov     rax, cs:__security_cookie
0x180050383  xor     rax, rsp
0x180050386  mov     [rbp+1D0h+var_50], rax
0x18005038d  mov     rsi, [rbp+1D0h+arg_20]
0x180050394  xor     r14d, r14d
0x180050397  mov     r13, [rbp+1D0h+arg_28]
0x18005039e  mov     rdi, r8
0x1800503a1  mov     [rsp+2D0h+var_290], r14d
0x1800503a6  mov     r15, rdx
0x1800503a9  mov     qword ptr [rsp+2D0h+var_288], r14
0x1800503ae  mov     [rsp+2D0h+var_270], r9
0x1800503b3  mov     [rsp+2D0h+var_268], r8
0x1800503b8  mov     [rsp+2D0h+var_280], rcx
0x1800503bd  call    cs:__imp_GetTickCount
0x1800503c3  mov     rdx, r15; unsigned __int16 *
0x1800503c6  lea     rcx, [rsp+2D0h+var_288]; this
0x1800503cb  call    ?Set@PIIHandler@@QEAAJPEBG@Z; PIIHandler::Set(ushort const *)
0x1800503d0  mov     rbx, qword ptr [rsp+2D0h+var_288]
0x1800503d5  test    r15, r15
0x1800503d8  jnz     short loc_180050428
0x1800503da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800503e1  lea     r14, WPP_GLOBAL_Control
0x1800503e8  cmp     rcx, r14
0x1800503eb  jz      short loc_180050418
0x1800503ed  mov     sil, 4
0x1800503f0  test    [rcx+1Ch], sil
0x1800503f4  jz      short loc_180050418
0x1800503f6  cmp     byte ptr [rcx+19h], 2
0x1800503fa  jb      short loc_180050418
0x1800503fc  mov     edx, 0D1h
0x180050401  lea     r9, aSzuserupn; "szUserUPN"
0x180050408  mov     rcx, [rcx+10h]
0x18005040c  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180050413  call    WPP_SF_S
0x180050418  mov     edi, 80070057h
0x18005041d  call    cs:__imp_GetTickCount
0x180050423  jmp     loc_180050908
0x180050428  test    rdi, rdi
0x18005042b  jnz     short loc_18005045D
0x18005042d  mov     rcx, cs:WPP_GLOBAL_Control
0x180050434  lea     r14, WPP_GLOBAL_Control
0x18005043b  cmp     rcx, r14
0x18005043e  jz      short loc_180050418
0x180050440  mov     sil, 4
0x180050443  test    [rcx+1Ch], sil
0x180050447  jz      short loc_180050418
0x180050449  cmp     byte ptr [rcx+19h], 2
0x18005044d  jb      short loc_180050418
0x18005044f  mov     edx, 0D2h
0x180050454  lea     r9, aSzusersid_0; "szUserSID"
0x18005045b  jmp     short loc_180050408
0x18005045d  test    rsi, rsi
0x180050460  jnz     short loc_180050495
0x180050462  mov     rcx, cs:WPP_GLOBAL_Control
0x180050469  lea     r14, WPP_GLOBAL_Control
0x180050470  cmp     rcx, r14
0x180050473  jz      short loc_180050418
0x180050475  mov     sil, 4
0x180050478  test    [rcx+1Ch], sil
0x18005047c  jz      short loc_180050418
0x18005047e  cmp     byte ptr [rcx+19h], 2
0x180050482  jb      short loc_180050418
0x180050484  mov     edx, 0D3h
0x180050489  lea     r9, aPuldisknumber; "pulDiskNumber"
0x180050490  jmp     loc_180050408
0x180050495  test    r13, r13
0x180050498  jnz     short loc_1800504D9
0x18005049a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800504a1  lea     r14, WPP_GLOBAL_Control
0x1800504a8  cmp     rcx, r14
0x1800504ab  jz      loc_180050418
0x1800504b1  mov     sil, 4
0x1800504b4  test    [rcx+1Ch], sil
0x1800504b8  jz      loc_180050418
0x1800504be  cmp     byte ptr [rcx+19h], 2
0x1800504c2  jb      loc_180050418
0x1800504c8  mov     edx, 0D4h
0x1800504cd  lea     r9, aPstruvhdvolume; "pstrUvhdVolumeGuidPath"
0x1800504d4  jmp     loc_180050408
0x1800504d9  mov     edi, 208h
0x1800504de  lea     rcx, [rsp+2D0h+LibFileName]; void *
0x1800504e3  mov     r8d, edi; Size
0x1800504e6  xor     edx, edx; Val
0x1800504e8  call    memset_0
0x1800504ed  lea     rax, [rsp+2D0h+var_288]
0x1800504f2  mov     [rsp+2D0h+var_288], edi
0x1800504f6  mov     [rsp+2D0h+pcbData], rax; pcbData
0x1800504fb  lea     r8, aRdvcloud; "RdvCloud"
0x180050502  lea     rax, [rsp+2D0h+LibFileName]
0x180050507  mov     [rsp+2D0h+hLibModule], r14
0x18005050c  mov     [rsp+2D0h+pvData], rax; pvData
0x180050511  lea     rdx, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180050518  mov     r9d, 2; dwFlags
0x18005051e  mov     [rsp+2D0h+pdwType], r14; pdwType
0x180050523  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005052a  mov     rdi, r14
0x18005052d  call    cs:__imp_RegGetValueW
0x180050533  test    eax, eax
0x180050535  jnz     short loc_18005054A
0x180050537  lea     rcx, [rsp+2D0h+LibFileName]; lpLibFileName
0x18005053c  call    cs:__imp_LoadLibraryW
0x180050542  mov     rdi, rax
0x180050545  mov     [rsp+2D0h+hLibModule], rax
0x18005054a  test    rdi, rdi
0x18005054d  jnz     short loc_180050559
0x18005054f  mov     edi, 8000FFFFh
0x180050554  jmp     loc_18005041D
0x180050559  lea     rdx, aMountxdrive; "MountXDrive"
0x180050560  mov     rcx, rdi; hModule
0x180050563  call    cs:__imp_GetProcAddress
0x180050569  lea     r12, qword_180063A68
0x180050570  mov     r14, rax
0x180050573  test    rax, rax
0x180050576  jnz     loc_180050603
0x18005057c  call    cs:__imp_GetLastError
0x180050582  mov     edi, eax
0x180050584  test    eax, eax
0x180050586  jle     short loc_180050591
0x180050588  movzx   edi, ax
0x18005058b  or      edi, 80070000h
0x180050591  test    rbx, rbx
0x180050594  lea     r8, aSFailedToFindM; "[%s] Failed to find MountXDrive functio"...
0x18005059b  mov     r9, r12
0x18005059e  lea     rcx, aUvhd; "UVHD"
0x1800505a5  cmovnz  r9, rbx
0x1800505a9  mov     edx, edi; int
0x1800505ab  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800505b0  test    edi, edi
0x1800505b2  jns     short loc_180050603
0x1800505b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800505bb  lea     r14, WPP_GLOBAL_Control
0x1800505c2  cmp     rcx, r14
0x1800505c5  jz      loc_1800508F7
0x1800505cb  mov     sil, 4
0x1800505ce  test    [rcx+1Ch], sil
0x1800505d2  jz      loc_1800508F7
0x1800505d8  cmp     byte ptr [rcx+19h], 2
0x1800505dc  jb      loc_1800508F7
0x1800505e2  mov     edx, 0D5h
0x1800505e7  mov     r9, r15
0x1800505ea  mov     rcx, [rcx+10h]
0x1800505ee  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800505f5  mov     dword ptr [rsp+2D0h+pdwType], edi
0x1800505f9  call    WPP_SF_Sd
0x1800505fe  jmp     loc_1800508F7
0x180050603  mov     rcx, [rsp+2D0h+var_270]
0x180050608  lea     rdx, [rsp+2D0h+var_290]
0x18005060d  mov     rax, r14
0x180050610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050615  test    rbx, rbx
0x180050618  lea     r8, aSUnableToMount; "[%s] Unable to mount the disk for the u"...
0x18005061f  mov     r9, r12
0x180050622  lea     rcx, aUvhd; "UVHD"
0x180050629  cmovnz  r9, rbx
0x18005062d  mov     edx, eax; int
0x18005062f  mov     edi, eax
0x180050631  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180050636  test    eax, eax
0x180050638  jns     short loc_180050672
0x18005063a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050641  lea     r14, WPP_GLOBAL_Control
0x180050648  cmp     rcx, r14
0x18005064b  jz      loc_1800508F7
0x180050651  mov     sil, 4
0x180050654  test    [rcx+1Ch], sil
0x180050658  jz      loc_1800508F7
0x18005065e  cmp     byte ptr [rcx+19h], 2
0x180050662  jb      loc_1800508F7
0x180050668  mov     edx, 0D6h
0x18005066d  jmp     loc_1800505E7
0x180050672  mov     eax, [rsp+2D0h+var_290]
0x180050676  mov     [rsi], eax
0x180050678  mov     rcx, cs:WPP_GLOBAL_Control
0x18005067f  lea     r14, WPP_GLOBAL_Control
0x180050686  mov     sil, 4
0x180050689  cmp     rcx, r14
0x18005068c  jz      short loc_1800506BA
0x18005068e  test    [rcx+1Ch], sil
0x180050692  jz      short loc_1800506BA
0x180050694  cmp     [rcx+19h], sil
0x180050698  jb      short loc_1800506BA
0x18005069a  mov     rcx, [rcx+10h]
0x18005069e  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800506a5  mov     edx, 0D7h
0x1800506aa  mov     dword ptr [rsp+2D0h+pdwType], eax
0x1800506ae  mov     r9, r15
0x1800506b1  call    WPP_SF_Sd
0x1800506b6  mov     eax, [rsp+2D0h+var_290]
0x1800506ba  test    rbx, rbx
0x1800506bd  mov     dword ptr [rsp+2D0h+pdwType], eax
0x1800506c1  mov     r9, r12
0x1800506c4  lea     r8, aSUserHasAMount; "[%s] User has a mounted Xdrive [%d]"
0x1800506cb  cmovnz  r9, rbx
0x1800506cf  lea     rcx, aUvhd; "UVHD"
0x1800506d6  mov     edx, edi; int
0x1800506d8  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800506dd  mov     edx, [rsp+2D0h+var_290]; unsigned int
0x1800506e1  mov     r8, r13; struct CPathString *
0x1800506e4  call    ?FindFirstVolumeForDiskNumber@CVhdHelper@Util@RdVhd@@QEBAJKPEAVCPathString@@@Z; RdVhd::Util::CVhdHelper::FindFirstVolumeForDiskNumber(ulong,CPathString *)
0x1800506e9  mov     edi, eax
0x1800506eb  test    eax, eax
0x1800506ed  jns     short loc_18005073B
0x1800506ef  mov     r8d, eax
0x1800506f2  mov     ecx, eax
0x1800506f4  sar     r8d, 10h
0x1800506f8  xor     eax, eax
0x1800506fa  and     ecx, 78000000h
0x180050700  mov     edx, r8d
0x180050703  and     edx, 7FFh
0x180050709  cmp     ecx, 50000000h
0x18005070f  cmovnz  edx, eax
0x180050712  test    edx, edx
0x180050714  jnz     short loc_18005073B
0x180050716  and     r8d, 1FFFh
0x18005071d  cmp     r8d, 7
0x180050721  jz      short loc_18005072E
0x180050723  test    r8d, r8d
0x180050726  jnz     short loc_18005073B
0x180050728  bt      edi, 1Ch
0x18005072c  jb      short loc_18005073B
0x18005072e  movzx   edi, di
0x180050731  test    edi, edi
0x180050733  jz      short loc_18005073B
0x180050735  or      edi, 0D0910000h
0x18005073b  test    rbx, rbx
0x18005073e  lea     r8, aSUnableToFindA; "[%s] Unable to find a valid volume in t"...
0x180050745  mov     r9, r12
0x180050748  lea     rcx, aUvhd; "UVHD"
0x18005074f  cmovnz  r9, rbx
0x180050753  mov     edx, edi; int
0x180050755  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18005075a  test    edi, edi
0x18005075c  jns     short loc_18005078C
0x18005075e  mov     rcx, cs:WPP_GLOBAL_Control
0x180050765  cmp     rcx, r14
0x180050768  jz      loc_1800508F7
0x18005076e  test    [rcx+1Ch], sil
0x180050772  jz      loc_1800508F7
0x180050778  cmp     byte ptr [rcx+19h], 2
0x18005077c  jb      loc_1800508F7
0x180050782  mov     edx, 0D8h
0x180050787  jmp     loc_1800505E7
0x18005078c  mov     rcx, cs:WPP_GLOBAL_Control
0x180050793  cmp     rcx, r14
0x180050796  jz      short loc_1800507BC
0x180050798  test    [rcx+1Ch], sil
0x18005079c  jz      short loc_1800507BC
0x18005079e  cmp     [rcx+19h], sil
0x1800507a2  jb      short loc_1800507BC
0x1800507a4  mov     rcx, [rcx+10h]
0x1800507a8  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800507af  mov     edx, 0D9h
0x1800507b4  mov     r9, r15
0x1800507b7  call    WPP_SF_S
0x1800507bc  test    rbx, rbx
0x1800507bf  lea     r8, aSUserXdriveIsO; "[%s] User Xdrive is online and ready"
0x1800507c6  mov     r9, r12
0x1800507c9  lea     rcx, aUvhd; "UVHD"
0x1800507d0  cmovnz  r9, rbx
0x1800507d4  mov     edx, edi; int
0x1800507d6  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800507db  mov     rcx, r13
0x1800507de  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800507e3  mov     rdx, [rsp+2D0h+var_268]; unsigned __int16 *
0x1800507e8  mov     r8, rax; unsigned __int16 *
0x1800507eb  mov     rcx, [rsp+2D0h+var_280]; this
0x1800507f0  call    ?SetUvhdVolumePermissions@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBG0@Z; RdVhd::Uvhd::CUvhdDiskManager::SetUvhdVolumePermissions(ushort const *,ushort const *)
0x1800507f5  mov     edi, eax
0x1800507f7  test    eax, eax
0x1800507f9  jns     short loc_18005083B
0x1800507fb  mov     rax, cs:WPP_GLOBAL_Control
0x180050802  cmp     rax, r14
0x180050805  jz      loc_1800508F7
0x18005080b  test    [rax+1Ch], sil
0x18005080f  jz      loc_1800508F7
0x180050815  cmp     byte ptr [rax+19h], 2
0x180050819  jb      loc_1800508F7
0x18005081f  mov     rcx, r13
0x180050822  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180050827  mov     rcx, cs:WPP_GLOBAL_Control
0x18005082e  mov     edx, 0DAh
0x180050833  mov     r9, rax
0x180050836  jmp     loc_1800505EA
0x18005083b  mov     rcx, r13
0x18005083e  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180050843  mov     r9, rax
0x180050846  lea     r8, aSetuvhdvolumep; "SetUvhdVolumePermissions(%s)"
0x18005084d  mov     edx, edi; int
0x18005084f  lea     rcx, aUvhd; "UVHD"
0x180050856  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
  ... truncated ...
```
