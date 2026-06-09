# AppXVolumeUtil::GetVolumeIdForInstalledPackage(wchar_t const *,wchar_t const *,unsigned __int64,wchar_t *)

- ea: `0x18021fc34`
- end: `0x1802203ae`
- name: `?GetVolumeIdForInstalledPackage@AppXVolumeUtil@@YAJPEB_W0_KPEA_W@Z`
- size: `1914`
- prototype: `int(AppXVolumeUtil *__hidden this, const wchar_t *, const wchar_t *, unsigned __int64, wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180209aa0`

## callees

- `0x18012b618`
- `0x180219790`
- `0x18021a858`
- `0x18021f810`
- `0x18021fc34`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18021fed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18021fed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021fe3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021ff6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021ffd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022006b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802200c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022011a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802201ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022021b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802202cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021fe3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021ff6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021ffd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022006b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802200c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022011a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802201ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022021b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802202cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180220385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220155`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180220155`

## string_xrefs

- `0x1802201d3`: `get_PackageStorePath`
- `0x1802202ff`: `Failed to get the download volume for the installed package %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall AppXVolumeUtil::GetVolumeIdForInstalledPackage(
        AppXVolumeUtil *this,
        wchar_t *a2,
        const wchar_t *a3,
        _WORD *a4)
{
  char v5; // r12
  HSTRING v7; // rdi
  struct CPackageManagerWrapper *v8; // rsi
  int PackageManager; // r14d
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, __int64 *); // r14
  __int64 v13; // rcx
  int i; // eax
  __int64 v15; // rcx
  AppXVolumeUtil *v16; // rbx
  __int64 (__fastcall *v17)(AppXVolumeUtil *, HSTRING, __int64 *); // r14
  __int64 v18; // rcx
  struct ABI::Windows::Management::Deployment::IPackageVolume *v19; // rdx
  AppXVolumeUtil *v20; // rbx
  __int64 (__fastcall *v21)(AppXVolumeUtil *, HSTRING, __int64 *); // r14
  __int64 v22; // rcx
  __int64 v23; // rcx
  AppXVolumeUtil *v24; // rcx
  __int64 v25; // rcx
  AppXVolumeUtil *v26; // rcx
  PCWSTR v27; // rbx
  PCWSTR v28; // rax
  __int64 v29; // rcx
  AppXVolumeUtil *v30; // rcx
  __int64 v31; // rcx
  AppXVolumeUtil *v32; // rcx
  __int64 v33; // rcx
  AppXVolumeUtil *v34; // rcx
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v36; // rax
  __int64 v37; // rcx
  AppXVolumeUtil *v38; // rcx
  __int64 v39; // rcx
  AppXVolumeUtil *v40; // rcx
  __int64 v41; // rcx
  AppXVolumeUtil *v42; // rcx
  __int64 v43; // rcx
  AppXVolumeUtil *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  wchar_t *v48; // [rsp+20h] [rbp-69h]
  HSTRING v49; // [rsp+40h] [rbp-49h] BYREF
  HSTRING v50; // [rsp+48h] [rbp-41h] BYREF
  struct CPackageManagerWrapper *v51; // [rsp+50h] [rbp-39h] BYREF
  HSTRING string; // [rsp+58h] [rbp-31h] BYREF
  AppXVolumeUtil *v53; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v54[8]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v55; // [rsp+70h] [rbp-19h] BYREF
  AppXVolumeUtil *v56; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v57[4]; // [rsp+80h] [rbp-9h] BYREF
  int v58; // [rsp+84h] [rbp-5h] BYREF
  __int64 v59; // [rsp+88h] [rbp-1h] BYREF
  __int64 v60; // [rsp+90h] [rbp+7h] BYREF

  v5 = (char)a3;
  v53 = this;
  string = (HSTRING)a2;
  v49 = 0;
  v7 = 0;
  v50 = 0;
  v8 = 0;
  v51 = 0;
  v60 = 0;
  v59 = 0;
  v54[0] = 0;
  if ( !this )
    goto LABEL_2;
  if ( !a3 )
  {
    PackageManager = -2147024809;
    goto LABEL_108;
  }
  if ( a4 )
  {
    *a4 = 0;
    PackageManager = Windows::Internal::String::Initialize<wchar_t const *>(&v49, &v53);
    if ( PackageManager >= 0 )
    {
      if ( !a2
        || (PackageManager = Windows::Internal::String::Initialize<wchar_t const *>(&v50, &string),
            v7 = v50,
            PackageManager >= 0) )
      {
        PackageManager = GetPackageManager(&v51);
        if ( PackageManager < 0 )
        {
          v8 = v51;
        }
        else
        {
          v10 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
          v8 = v51;
          PackageManager = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v51 + 4) + 88LL))(
                             *((_QWORD *)v51 + 4),
                             &v60);
          if ( PackageManager >= 0 )
          {
            v11 = v60;
            v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 48LL);
            v13 = v59;
            if ( v59 )
            {
              v59 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            }
            PackageManager = v12(v11, &v59);
            if ( PackageManager >= 0 )
            {
              for ( i = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v59 + 56LL))(v59, v54);
                    ;
                    i = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v59 + 64LL))(v59, v54) )
              {
                if ( i < 0 || !v54[0] )
                {
                  PackageManager = -2145116125;
                  goto LABEL_108;
                }
                v56 = 0;
                v57[0] = 0;
                string = 0;
                v55 = 0;
                v58 = 0;
                PackageManager = (*(__int64 (__fastcall **)(__int64, AppXVolumeUtil **))(*(_QWORD *)v59 + 48LL))(
                                   v59,
                                   &v56);
                if ( PackageManager < 0 )
                {
                  WUTrace(0, 0, 4096, 2, PackageManager, L"Failed to get the package volume");
                  v43 = v55;
                  if ( v55 )
                  {
                    v55 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                  }
                  if ( string )
                    WindowsDeleteString(string);
                  v44 = v56;
                  if ( v56 )
                  {
                    v56 = 0;
                    (*(void (__fastcall **)(AppXVolumeUtil *))(*(_QWORD *)v44 + 16LL))(v44);
                  }
                  goto LABEL_108;
                }
                PackageManager = (*(__int64 (__fastcall **)(AppXVolumeUtil *, _BYTE *))(*(_QWORD *)v56 + 48LL))(
                                   v56,
                                   v57);
                if ( PackageManager < 0 )
                {
                  v41 = v55;
                  if ( v55 )
                  {
                    v55 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                  }
                  if ( string )
                    WindowsDeleteString(string);
                  v42 = v56;
                  if ( v56 )
                  {
                    v56 = 0;
                    (*(void (__fastcall **)(AppXVolumeUtil *))(*(_QWORD *)v42 + 16LL))(v42);
                  }
                  goto LABEL_108;
                }
                if ( v57[0] )
                {
                  v15 = v55;
                  if ( v55 )
                  {
                    v55 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                  }
                  if ( string )
                    WindowsDeleteString(string);
                }
                else
                {
                  PackageManager = (*(__int64 (__fastcall **)(AppXVolumeUtil *, HSTRING *))(*(_QWORD *)v56 + 80LL))(
                                     v56,
                                     &string);
                  if ( PackageManager < 0 )
                  {
                    WUTrace(0, 0, 4096, 3, PackageManager, L"get_PackageStorePath");
                    v39 = v55;
                    if ( v55 )
                    {
                      v55 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                    }
                    if ( string )
                      WindowsDeleteString(string);
                    v40 = v56;
                    if ( v56 )
                    {
                      v56 = 0;
                      (*(void (__fastcall **)(AppXVolumeUtil *))(*(_QWORD *)v40 + 16LL))(v40);
                    }
                    goto LABEL_108;
                  }
                  v16 = v56;
                  v17 = *(__int64 (__fastcall **)(AppXVolumeUtil *, HSTRING, __int64 *))(*(_QWORD *)v56 + 112LL);
                  v18 = v55;
                  if ( v55 )
                  {
                    v55 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                  }
                  PackageManager = v17(v16, v49, &v55);
                  if ( PackageManager < 0 )
                  {
                    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                    v36 = WindowsGetStringRawBuffer(v49, 0);
                    WUTrace(
                      0,
                      0,
                      4096,
                      2,
                      PackageManager,
                      L"FindPackagesByPackageFamilyName failed with the family name: %ws on the volume %ws",
                      v36,
                      StringRawBuffer);
                    v37 = v55;
                    if ( v55 )
                    {
                      v55 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                    }
                    if ( string )
                      WindowsDeleteString(string);
                    v38 = v56;
                    if ( v56 )
                    {
                      v56 = 0;
                      (*(void (__fastcall **)(AppXVolumeUtil *))(*(_QWORD *)v38 + 16LL))(v38);
                    }
                    goto LABEL_108;
                  }
                  PackageManager = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 56LL))(v55, &v58);
                  if ( PackageManager < 0 )
                  {
                    v33 = v55;
                    if ( v55 )
                    {
                      v55 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                    }
                    if ( string )
                      WindowsDeleteString(string);
                    v34 = v56;
                    if ( v56 )
                    {
                      v56 = 0;
                      (*(void (__fastcall **)(AppXVolumeUtil *))(*(_QWORD *)v34 + 16LL))(v34);
                    }
                    goto LABEL_108;
                  }
                  if ( v58 )
                    goto LABEL_64;
                  if ( !WindowsIsStringEmpty(v7) )
                  {
                    v20 = v56;
                    v21 = *(__int64 (__fastcall **)(AppXVolumeUtil *, HSTRING, __int64 *))(*(_QWORD *)v56 + 112LL);
                    v22 = v55;
                    if ( v55 )
                    {
                      v55 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                    }
                    PackageManager = v21(v20, v7, &v55);
                    if ( PackageManager < 0 )
                    {
                      v27 = WindowsGetStringRawBuffer(string, 0);
                      v28 = WindowsGetStringRawBuffer(v7, 0);
                      WUTrace(
                        0,
                        0,
                        4096,
                        2,
                        PackageManager,
                        L"FindPackagesByPackageFamilyName failed with the legacy family name: %ws on the volume %ws",
                        v28,
                        v27);
                      v29 = v55;
                      if ( v55 )
                      {
                        v55 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                      }
                      if ( string )
                        WindowsDeleteString(string);
                      v30 = v56;
                      if ( v56 )
                      {
                        v56 = 0;
                        (*(void (__fastcall **)(AppXVolumeUtil *))(*(_QWORD *)v30 + 16LL))(v30);
                      }
                      goto LABEL_108;
                    }
                    PackageManager = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 56LL))(v55, &v58);
                    if ( PackageManager < 0 )
                    {
                      v25 = v55;
                      if ( v55 )
                      {
                        v55 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                      }
                      if ( string )
                        WindowsDeleteString(string);
                      v26 = v56;
                      if ( v56 )
                      {
                        v56 = 0;
                        (*(void (__fastcall **)(AppXVolumeUtil *))(*(_QWORD *)v26 + 16LL))(v26);
                      }
                      goto LABEL_108;
                    }
                  }
                  if ( v58 )
                  {
LABEL_64:
                    LOBYTE(v19) = 1;
                    PackageManager = AppXVolumeUtil::GetVolumeIdFromPackageVolume(
                                       v56,
                                       v19,
                                       v5,
                                       (unsigned __int64)a4,
                                       v48);
                    v31 = v55;
                    if ( v55 )
                    {
                      v55 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                    }
                    if ( string )
                      WindowsDeleteString(string);
                    v32 = v56;
                    if ( v56 )
                    {
                      v56 = 0;
                      (*(void (__fastcall **)(AppXVolumeUtil *))(*(_QWORD *)v32 + 16LL))(v32);
                    }
                    if ( PackageManager >= 0 )
                      goto LABEL_109;
                    goto LABEL_108;
                  }
                  v23 = v55;
                  if ( v55 )
                  {
                    v55 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                  }
                  if ( string )
                    WindowsDeleteString(string);
                }
                v24 = v56;
                if ( v56 )
                {
                  v56 = 0;
                  (*(void (__fastcall **)(AppXVolumeUtil *))(*(_QWORD *)v24 + 16LL))(v24);
                }
              }
            }
            WUTrace(0, 0, 4096, 2, PackageManager, L"Failed to get the package volume iterator");
          }
          else
          {
            WUTrace(0, 0, 4096, 2, PackageManager, L"FindPackageVolumes failed");
          }
        }
      }
    }
  }
  else
  {
LABEL_2:
    PackageManager = -2147467261;
  }
LABEL_108:
  WUTrace(0, 0, 4096, 2, PackageManager, L"Failed to get the download volume for the installed package %ws", v53);
LABEL_109:
  v45 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  if ( v8 )
    (*(void (__fastcall **)(struct CPackageManagerWrapper *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 )
    WindowsDeleteString(v7);
  if ( v49 )
    WindowsDeleteString(v49);
  return (unsigned int)PackageManager;
}

```

## disassembly

```asm
0x18021fc34  push    rbp
0x18021fc36  push    rbx
0x18021fc37  push    rsi
0x18021fc38  push    rdi
0x18021fc39  push    r12
0x18021fc3b  push    r13
0x18021fc3d  push    r14
0x18021fc3f  push    r15
0x18021fc41  lea     rbp, [rsp-1Fh]
0x18021fc46  sub     rsp, 0A8h
0x18021fc4d  mov     rax, cs:__security_cookie
0x18021fc54  xor     rax, rsp
0x18021fc57  mov     [rbp+57h+var_48], rax
0x18021fc5b  mov     r15, r9
0x18021fc5e  mov     r12, r8
0x18021fc61  mov     rbx, rdx
0x18021fc64  mov     [rbp+57h+var_80], rcx
0x18021fc68  mov     [rbp+57h+string], rdx
0x18021fc6c  xor     r13d, r13d
0x18021fc6f  mov     [rbp+57h+var_A0], r13
0x18021fc73  mov     edi, r13d
0x18021fc76  mov     [rbp+57h+var_98], r13
0x18021fc7a  mov     esi, r13d
0x18021fc7d  mov     [rbp+57h+var_90], r13
0x18021fc81  mov     [rbp+57h+var_50], r13
0x18021fc85  mov     [rbp+57h+var_58], r13
0x18021fc89  mov     [rbp+57h+var_78], r13b
0x18021fc8d  test    rcx, rcx
0x18021fc90  jnz     short loc_18021FC9D
0x18021fc92  mov     r14d, 80004003h
0x18021fc98  jmp     loc_1802202F6
0x18021fc9d  test    r12, r12
0x18021fca0  jnz     short loc_18021FCAD
0x18021fca2  mov     r14d, 80070057h
0x18021fca8  jmp     loc_1802202F6
0x18021fcad  test    r15, r15
0x18021fcb0  jz      short loc_18021FC92
0x18021fcb2  mov     [r9], r13w
0x18021fcb6  lea     rdx, [rbp+57h+var_80]
0x18021fcba  lea     rcx, [rbp+57h+var_A0]
0x18021fcbe  call    ??$Initialize@PEB_W@String@Internal@Windows@@QEAAJAEBQEB_WUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<wchar_t const *>(wchar_t const * const &,Windows::Internal::_StringDetail::dummy_t)
0x18021fcc3  mov     r14d, eax
0x18021fcc6  test    eax, eax
0x18021fcc8  js      loc_1802202F6
0x18021fcce  test    rbx, rbx
0x18021fcd1  jz      short loc_18021FCEF
0x18021fcd3  lea     rdx, [rbp+57h+string]
0x18021fcd7  lea     rcx, [rbp+57h+var_98]
0x18021fcdb  call    ??$Initialize@PEB_W@String@Internal@Windows@@QEAAJAEBQEB_WUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<wchar_t const *>(wchar_t const * const &,Windows::Internal::_StringDetail::dummy_t)
0x18021fce0  mov     r14d, eax
0x18021fce3  mov     rdi, [rbp+57h+var_98]
0x18021fce7  test    eax, eax
0x18021fce9  js      loc_1802202F6
0x18021fcef  lea     rcx, [rbp+57h+var_90]; struct CPackageManagerWrapper **
0x18021fcf3  call    ?GetPackageManager@@YAJPEAPEAVCPackageManagerWrapper@@@Z; GetPackageManager(CPackageManagerWrapper * *)
0x18021fcf8  mov     r14d, eax
0x18021fcfb  test    eax, eax
0x18021fcfd  js      loc_1802202F2
0x18021fd03  mov     rcx, [rbp+57h+var_50]
0x18021fd07  test    rcx, rcx
0x18021fd0a  jz      short loc_18021FD1D
0x18021fd0c  mov     [rbp+57h+var_50], r13
0x18021fd10  mov     rax, [rcx]
0x18021fd13  mov     rax, [rax+10h]
0x18021fd17  call    _guard_dispatch_icall
0x18021fd1c  nop
0x18021fd1d  mov     rsi, [rbp+57h+var_90]
0x18021fd21  mov     rcx, [rsi+20h]
0x18021fd25  mov     rax, [rcx]
0x18021fd28  lea     rdx, [rbp+57h+var_50]
0x18021fd2c  mov     rax, [rax+58h]
0x18021fd30  call    _guard_dispatch_icall
0x18021fd35  mov     r14d, eax
0x18021fd38  test    eax, eax
0x18021fd3a  jns     short loc_18021FD65
0x18021fd3c  lea     rax, aFindpackagevol; "FindPackageVolumes failed"
0x18021fd43  mov     [rsp+0E0h+var_B8], rax
0x18021fd48  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x18021fd4d  xor     edx, edx
0x18021fd4f  xor     ecx, ecx
0x18021fd51  lea     r9d, [rdx+2]
0x18021fd55  mov     r8d, 1000h
0x18021fd5b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18021fd60  jmp     loc_1802202F6
0x18021fd65  mov     rbx, [rbp+57h+var_50]
0x18021fd69  mov     rax, [rbx]
0x18021fd6c  mov     r14, [rax+30h]
0x18021fd70  mov     rcx, [rbp+57h+var_58]
0x18021fd74  test    rcx, rcx
0x18021fd77  jz      short loc_18021FD8A
0x18021fd79  mov     [rbp+57h+var_58], r13
0x18021fd7d  mov     rdx, [rcx]
0x18021fd80  mov     rax, [rdx+10h]
0x18021fd84  call    _guard_dispatch_icall
0x18021fd89  nop
0x18021fd8a  lea     rdx, [rbp+57h+var_58]
0x18021fd8e  mov     rcx, rbx
0x18021fd91  mov     rax, r14
0x18021fd94  call    _guard_dispatch_icall
0x18021fd99  mov     r14d, eax
0x18021fd9c  test    eax, eax
0x18021fd9e  jns     short loc_18021FDA9
0x18021fda0  lea     rax, aFailedToGetThe_2; "Failed to get the package volume iterat"...
0x18021fda7  jmp     short loc_18021FD43
0x18021fda9  mov     rcx, [rbp+57h+var_58]
0x18021fdad  mov     rax, [rcx]
0x18021fdb0  mov     rax, [rax+38h]
0x18021fdb4  jmp     loc_18021FF9A
0x18021fdb9  cmp     [rbp+57h+var_78], r13b
0x18021fdbd  jz      loc_18021FFAB
0x18021fdc3  mov     [rbp+57h+var_68], r13
0x18021fdc7  mov     [rbp+57h+var_60], r13b
0x18021fdcb  mov     [rbp+57h+string], r13
0x18021fdcf  mov     [rbp+57h+var_70], r13
0x18021fdd3  mov     [rbp+57h+var_5C], r13d
0x18021fdd7  mov     rcx, [rbp+57h+var_58]
0x18021fddb  mov     rax, [rcx]
0x18021fdde  lea     rdx, [rbp+57h+var_68]
0x18021fde2  mov     rax, [rax+30h]
0x18021fde6  call    _guard_dispatch_icall
0x18021fdeb  mov     r14d, eax
0x18021fdee  test    eax, eax
0x18021fdf0  js      loc_180220287
0x18021fdf6  mov     rcx, [rbp+57h+var_68]
0x18021fdfa  mov     rax, [rcx]
0x18021fdfd  lea     rdx, [rbp+57h+var_60]
0x18021fe01  mov     rax, [rax+30h]
0x18021fe05  call    _guard_dispatch_icall
0x18021fe0a  mov     r14d, eax
0x18021fe0d  test    eax, eax
0x18021fe0f  js      loc_180220241
0x18021fe15  cmp     [rbp+57h+var_60], r13b
0x18021fe19  jz      short loc_18021FE4A
0x18021fe1b  mov     rcx, [rbp+57h+var_70]
0x18021fe1f  test    rcx, rcx
0x18021fe22  jz      short loc_18021FE35
0x18021fe24  mov     [rbp+57h+var_70], r13
0x18021fe28  mov     rax, [rcx]
0x18021fe2b  mov     rax, [rax+10h]
0x18021fe2f  call    _guard_dispatch_icall
0x18021fe34  nop
0x18021fe35  mov     rcx, [rbp+57h+string]; string
0x18021fe39  test    rcx, rcx
0x18021fe3c  jz      short loc_18021FE45
0x18021fe3e  call    cs:__imp_WindowsDeleteString
0x18021fe44  nop
0x18021fe45  jmp     loc_18021FF75
0x18021fe4a  mov     rcx, [rbp+57h+var_68]
0x18021fe4e  mov     rax, [rcx]
0x18021fe51  lea     rdx, [rbp+57h+string]
0x18021fe55  mov     rax, [rax+50h]
0x18021fe59  call    _guard_dispatch_icall
0x18021fe5e  mov     r14d, eax
0x18021fe61  test    eax, eax
0x18021fe63  js      loc_1802201D3
0x18021fe69  mov     rbx, [rbp+57h+var_68]
0x18021fe6d  mov     rax, [rbx]
0x18021fe70  mov     r14, [rax+70h]
0x18021fe74  mov     rcx, [rbp+57h+var_70]
0x18021fe78  test    rcx, rcx
0x18021fe7b  jz      short loc_18021FE8E
0x18021fe7d  mov     [rbp+57h+var_70], r13
0x18021fe81  mov     rdx, [rcx]
0x18021fe84  mov     rax, [rdx+10h]
0x18021fe88  call    _guard_dispatch_icall
0x18021fe8d  nop
0x18021fe8e  lea     r8, [rbp+57h+var_70]
0x18021fe92  mov     rdx, [rbp+57h+var_A0]
0x18021fe96  mov     rcx, rbx
0x18021fe99  mov     rax, r14
0x18021fe9c  call    _guard_dispatch_icall
0x18021fea1  mov     r14d, eax
0x18021fea4  test    eax, eax
0x18021fea6  js      loc_180220140
0x18021feac  mov     rcx, [rbp+57h+var_70]
0x18021feb0  mov     rax, [rcx]
0x18021feb3  lea     rdx, [rbp+57h+var_5C]
0x18021feb7  mov     rax, [rax+38h]
0x18021febb  call    _guard_dispatch_icall
0x18021fec0  mov     r14d, eax
0x18021fec3  test    eax, eax
0x18021fec5  js      loc_1802200F7
0x18021fecb  mov     eax, [rbp+57h+var_5C]
0x18021fece  test    eax, eax
0x18021fed0  jnz     loc_180220091
0x18021fed6  mov     rcx, rdi; string
0x18021fed9  call    cs:__imp_WindowsIsStringEmpty
0x18021fedf  test    eax, eax
0x18021fee1  jnz     short loc_18021FF40
0x18021fee3  mov     rbx, [rbp+57h+var_68]
0x18021fee7  mov     rax, [rbx]
0x18021feea  mov     r14, [rax+70h]
0x18021feee  mov     rcx, [rbp+57h+var_70]
0x18021fef2  test    rcx, rcx
0x18021fef5  jz      short loc_18021FF08
0x18021fef7  mov     [rbp+57h+var_70], r13
0x18021fefb  mov     rdx, [rcx]
0x18021fefe  mov     rax, [rdx+10h]
0x18021ff02  call    _guard_dispatch_icall
0x18021ff07  nop
0x18021ff08  lea     r8, [rbp+57h+var_70]
0x18021ff0c  mov     rdx, rdi
0x18021ff0f  mov     rcx, rbx
0x18021ff12  mov     rax, r14
0x18021ff15  call    _guard_dispatch_icall
0x18021ff1a  mov     r14d, eax
0x18021ff1d  test    eax, eax
0x18021ff1f  js      loc_18021FFFF
0x18021ff25  mov     rcx, [rbp+57h+var_70]
0x18021ff29  mov     rax, [rcx]
0x18021ff2c  lea     rdx, [rbp+57h+var_5C]
0x18021ff30  mov     rax, [rax+38h]
0x18021ff34  call    _guard_dispatch_icall
0x18021ff39  mov     r14d, eax
0x18021ff3c  test    eax, eax
0x18021ff3e  js      short loc_18021FFB6
0x18021ff40  mov     eax, [rbp+57h+var_5C]
0x18021ff43  test    eax, eax
0x18021ff45  jnz     loc_180220091
0x18021ff4b  mov     rcx, [rbp+57h+var_70]
0x18021ff4f  test    rcx, rcx
0x18021ff52  jz      short loc_18021FF65
0x18021ff54  mov     [rbp+57h+var_70], r13
0x18021ff58  mov     rax, [rcx]
0x18021ff5b  mov     rax, [rax+10h]
0x18021ff5f  call    _guard_dispatch_icall
0x18021ff64  nop
0x18021ff65  mov     rcx, [rbp+57h+string]; string
0x18021ff69  test    rcx, rcx
0x18021ff6c  jz      short loc_18021FF75
0x18021ff6e  call    cs:__imp_WindowsDeleteString
0x18021ff74  nop
0x18021ff75  mov     rcx, [rbp+57h+var_68]
0x18021ff79  test    rcx, rcx
0x18021ff7c  jz      short loc_18021FF8F
0x18021ff7e  mov     [rbp+57h+var_68], r13
0x18021ff82  mov     rax, [rcx]
0x18021ff85  mov     rax, [rax+10h]
0x18021ff89  call    _guard_dispatch_icall
0x18021ff8e  nop
0x18021ff8f  mov     rcx, [rbp+57h+var_58]
0x18021ff93  mov     rax, [rcx]
0x18021ff96  mov     rax, [rax+40h]
0x18021ff9a  lea     rdx, [rbp+57h+var_78]
0x18021ff9e  call    _guard_dispatch_icall
0x18021ffa3  test    eax, eax
0x18021ffa5  jns     loc_18021FDB9
0x18021ffab  mov     r14d, 80242023h
0x18021ffb1  jmp     loc_1802202F6
0x18021ffb6  mov     rcx, [rbp+57h+var_70]
0x18021ffba  test    rcx, rcx
0x18021ffbd  jz      short loc_18021FFD0
0x18021ffbf  mov     [rbp+57h+var_70], r13
0x18021ffc3  mov     rax, [rcx]
0x18021ffc6  mov     rax, [rax+10h]
0x18021ffca  call    _guard_dispatch_icall
0x18021ffcf  nop
0x18021ffd0  mov     rcx, [rbp+57h+string]; string
0x18021ffd4  test    rcx, rcx
0x18021ffd7  jz      short loc_18021FFE0
0x18021ffd9  call    cs:__imp_WindowsDeleteString
0x18021ffdf  nop
0x18021ffe0  mov     rcx, [rbp+57h+var_68]
0x18021ffe4  test    rcx, rcx
0x18021ffe7  jz      short loc_18021FFFA
0x18021ffe9  mov     [rbp+57h+var_68], r13
0x18021ffed  mov     rax, [rcx]
0x18021fff0  mov     rax, [rax+10h]
0x18021fff4  call    _guard_dispatch_icall
0x18021fff9  nop
0x18021fffa  jmp     loc_1802202F6
0x18021ffff  xor     edx, edx; length
0x180220001  mov     rcx, [rbp+57h+string]; string
0x180220005  call    cs:__imp_WindowsGetStringRawBuffer
0x18022000b  mov     rbx, rax
0x18022000e  xor     edx, edx; length
0x180220010  mov     rcx, rdi; string
0x180220013  call    cs:__imp_WindowsGetStringRawBuffer
0x180220019  mov     [rsp+0E0h+var_A8], rbx
0x18022001e  mov     [rsp+0E0h+var_B0], rax
0x180220023  lea     rax, aFindpackagesby; "FindPackagesByPackageFamilyName failed "...
0x18022002a  mov     [rsp+0E0h+var_B8], rax
0x18022002f  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x180220034  xor     edx, edx
0x180220036  xor     ecx, ecx
0x180220038  lea     r9d, [rdx+2]
0x18022003c  mov     r8d, 1000h
0x180220042  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180220047  nop
0x180220048  mov     rcx, [rbp+57h+var_70]
0x18022004c  test    rcx, rcx
0x18022004f  jz      short loc_180220062
0x180220051  mov     [rbp+57h+var_70], r13
0x180220055  mov     rax, [rcx]
0x180220058  mov     rax, [rax+10h]
0x18022005c  call    _guard_dispatch_icall
0x180220061  nop
0x180220062  mov     rcx, [rbp+57h+string]; string
0x180220066  test    rcx, rcx
0x180220069  jz      short loc_180220072
  ... truncated ...
```
