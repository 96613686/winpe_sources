# DataObj_SaveToFile

- ea: `0x1801b092c`
- end: `0x1801b0ef2`
- name: `DataObj_SaveToFile`
- size: `1478`
- prototype: `__int64 __fastcall(struct IDataObject *, __int64, const WCHAR *, __int64, struct PROGRESSINFO *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18048d6fc`

## callees

- `0x18000f6cc`
- `0x1800bd488`
- `0x1801b092c`
- `0x1801ef318`
- `0x180249490`
- `0x18024a53c`
- `0x18043ed2c`
- `0x18043ee84`
- `0x18043f1e0`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801b0bf7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801b0d20`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801b0bf7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801b0d20`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b0c33`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b0d9d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b0c33`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b0d9d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801b0c9c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801b0c9c`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1801b0cfe`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1801b0df1`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1801b0cfe`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1801b0df1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801b09b5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801b09b5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801b09d0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801b09d0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801b09fc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801b0e49`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801b09fc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801b0e49`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1801b0e1a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1801b0e1a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801b09df`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801b09df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b0d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b0e30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b0d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b0e30`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801b0c79`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801b0c79`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1801b0c65`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1801b0c65`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801b0cb8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801b0cb8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1801b0adb`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1801b0adb`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1801b0e96`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1801b0eaf`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1801b0e96`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1801b0eaf`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x1801b0ec0`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x1801b0ec0`
- `ole32!StgCreateDocfile` at `0x1801b0a51`
- `ole32!StgCreateDocfile` at `0x1801b0a51`
- `Windows.Storage!SHCopyStreamWithProgress` at `0x1801b0b99`
- `Windows.Storage!SHCopyStreamWithProgress` at `0x1801b0b99`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DataObj_SaveToFile(
        struct IDataObject *a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        struct PROGRESSINFO *a5,
        unsigned int a6)
{
  struct IDataObject v7; // rax
  HRESULT Error; // edi
  LONG v10; // r13d
  HANDLE FirstFileW; // rax
  DWORD FileAttributesW; // eax
  DWORD dwFlagsAndAttributes; // r15d
  int v14; // eax
  int v15; // esi
  HRESULT v16; // eax
  HANDLE FileW; // rsi
  bool v18; // zf
  DWORD v19; // r12d
  const void *v20; // rax
  const unsigned __int16 *v21; // r8
  DWORD dwFileAttributes; // esi
  HANDLE v23; // rax
  void *v24; // r12
  unsigned int DWORD; // eax
  const unsigned __int16 *v26; // r8
  IStorage *ppstgOpen; // [rsp+50h] [rbp-B0h] BYREF
  STGMEDIUM hMem; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF

  v7.lpVtbl = a1->lpVtbl;
  memset(&hMem, 0, sizeof(hMem));
  Error = ((__int64 (__fastcall *)(struct IDataObject *, __int64, STGMEDIUM *))v7.lpVtbl->GetData)(a1, a2, &hMem);
  if ( Error >= 0 )
  {
    v10 = 2;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(a3, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      v10 = 0x2000;
      FindClose(FirstFileW);
    }
    FileAttributesW = GetFileAttributesW(a3);
    if ( FileAttributesW != -1 && (FileAttributesW & 5) != 0 )
      SetFileAttributesW(a3, FileAttributesW & 0xFFFFFFFA);
    dwFlagsAndAttributes = 0;
    if ( (*(_BYTE *)a4 & 4) != 0 )
      dwFlagsAndAttributes = *(_DWORD *)(a4 + 36) & 0xFFFFFFEF;
    switch ( hMem.tymed )
    {
      case 1u:
        FileW = CreateFileW(a3, 0xC0000000, 3u, 0, 2u, dwFlagsAndAttributes, 0);
        if ( FileW != (HANDLE)-1LL )
        {
          v18 = (*(_BYTE *)a4 & 0x40) == 0;
          LODWORD(ppstgOpen) = 0;
          if ( v18 )
            v19 = GlobalSize(hMem.hBitmap);
          else
            v19 = *(_DWORD *)(a4 + 68);
          v20 = GlobalLock(hMem.hBitmap);
          if ( !WriteFile(FileW, v20, v19, (LPDWORD)&ppstgOpen, 0) )
            Error = ResultFromLastError();
          GlobalUnlock(hMem.hBitmap);
          if ( (*(_DWORD *)a4 & 0x38) != 0 )
            SetFileTime(
              FileW,
              (const FILETIME *)((a4 + 40) & -(__int64)((*(_DWORD *)a4 & 8) != 0)),
              (const FILETIME *)((a4 + 48) & -(__int64)((*(_DWORD *)a4 & 0x10) != 0)),
              (const FILETIME *)((a4 + 56) & -(__int64)((*(_DWORD *)a4 & 0x20) != 0)));
          CloseHandle(FileW);
LABEL_35:
          if ( Error < 0 )
          {
            DeleteFileW(a3);
            goto LABEL_54;
          }
LABEL_39:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54794917>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54794917>::GetImpl'::`2'::impl)
            && a6 - 1 <= 0xFFFFFFFD )
          {
            AddZoneIdentifier(a3, a6, v21);
          }
          if ( hMem.tymed != 1 )
          {
            dwFileAttributes = 0;
            if ( (*(_BYTE *)a4 & 0x38) != 0 )
            {
              v23 = CreateFileW(a3, 0x40000000u, 1u, 0, 3u, 0, 0);
              v24 = v23;
              if ( v23 != (HANDLE)-1LL )
              {
                SetFileTime(
                  v23,
                  (const FILETIME *)((a4 + 40) & -(__int64)((*(_DWORD *)a4 & 8) != 0)),
                  (const FILETIME *)((a4 + 48) & -(__int64)((*(_DWORD *)a4 & 0x10) != 0)),
                  (const FILETIME *)((a4 + 56) & -(__int64)((*(_DWORD *)a4 & 0x20) != 0)));
                memset(&FileInformation, 0, sizeof(FileInformation));
                if ( GetFileInformationByHandle(v24, &FileInformation) )
                  dwFileAttributes = FileInformation.dwFileAttributes;
                CloseHandle(v24);
              }
            }
            if ( dwFlagsAndAttributes )
              SetFileAttributesW(a3, dwFlagsAndAttributes | dwFileAttributes);
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54794917>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54794917>::GetImpl'::`2'::impl) )
          {
            DWORD = DataObj_GetDWORD(a1, (unsigned __int16)word_1806F9442, 0);
            if ( DWORD )
              AddZoneIdentifier(a3, DWORD, v26);
          }
          SHChangeNotify(v10, 5u, a3, 0);
          SHChangeNotify(0x40000, 5u, a3, 0);
          goto LABEL_54;
        }
        Error = ResultFromLastError();
        break;
      case 4u:
        ppstgOpen = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstgOpen);
        Error = SHCreateStreamOnFileW(a3, 0x1021u, (IStream **)&ppstgOpen);
        if ( Error >= 0 )
        {
          v31 = 0;
          v10 = 0x2000;
          v14 = (*(__int64 (__fastcall **)(HBITMAP, _QWORD, __int64, __int64 *))(*(_QWORD *)hMem.hBitmap + 40LL))(
                  hMem.hBitmap,
                  0,
                  1,
                  &v31);
          Error = -2147024891;
          v15 = v14;
          if ( v14 == -2147024891 )
            goto LABEL_24;
          if ( v14 >= 0 )
            v15 = (*(__int64 (__fastcall **)(HBITMAP, _QWORD, _QWORD, _QWORD))(*(_QWORD *)hMem.hBitmap + 40LL))(
                    hMem.hBitmap,
                    0,
                    0,
                    0);
          if ( (unsigned int)DataObj_ShouldCopyWithProgress(a1, hMem.pstm, a5) )
            v16 = SHCopyStreamWithProgress(
                    hMem.hBitmap,
                    ppstgOpen,
                    *(_QWORD *)a5,
                    *((_QWORD *)a5 + 2),
                    *((_QWORD *)a5 + 1));
          else
            v16 = (*(__int64 (__fastcall **)(HBITMAP, IStorage *, __int64, _QWORD, _QWORD))(*(_QWORD *)hMem.hBitmap
                                                                                          + 56LL))(
                    hMem.hBitmap,
                    ppstgOpen,
                    -1,
                    0,
                    0);
          Error = v16;
          if ( v15 >= 0 )
            (*(void (__fastcall **)(HBITMAP, __int64, _QWORD, _QWORD))(*(_QWORD *)hMem.hBitmap + 40LL))(
              hMem.hBitmap,
              v31,
              0,
              0);
          if ( Error < 0 )
          {
LABEL_24:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstgOpen);
            DeleteFileW(a3);
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstgOpen);
        break;
      case 8u:
        ppstgOpen = 0;
        Error = StgCreateDocfile(a3, 0x1012u, 0, &ppstgOpen);
        if ( Error < 0 )
        {
LABEL_54:
          ReleaseStgMedium(&hMem);
          return (unsigned int)Error;
        }
        Error = (*(__int64 (__fastcall **)(HBITMAP, _QWORD, _QWORD, _QWORD, IStorage *))(*(_QWORD *)hMem.hBitmap + 56LL))(
                  hMem.hBitmap,
                  0,
                  0,
                  0,
                  ppstgOpen);
        ((void (__fastcall *)(IStorage *, __int64))ppstgOpen->lpVtbl->Commit)(ppstgOpen, 1);
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
        goto LABEL_35;
      default:
        goto LABEL_39;
    }
    if ( Error < 0 )
      goto LABEL_54;
    goto LABEL_39;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1801b092c  push    rbp
0x1801b092e  push    rbx
0x1801b092f  push    rsi
0x1801b0930  push    rdi
0x1801b0931  push    r12
0x1801b0933  push    r13
0x1801b0935  push    r14
0x1801b0937  push    r15
0x1801b0939  lea     rbp, [rsp-218h]
0x1801b0941  sub     rsp, 318h
0x1801b0948  mov     rax, cs:__security_cookie
0x1801b094f  xor     rax, rsp
0x1801b0952  mov     [rbp+250h+var_50], rax
0x1801b0959  mov     r12, [rbp+250h+arg_20]
0x1801b0960  xor     eax, eax
0x1801b0962  mov     [rsp+350h+var_2E8], rax
0x1801b0967  mov     rbx, r8
0x1801b096a  mov     rax, [rcx]
0x1801b096d  lea     r8, [rsp+350h+hMem]
0x1801b0972  xorps   xmm0, xmm0
0x1801b0975  mov     [rsp+350h+var_308], rcx
0x1801b097a  mov     r14, r9
0x1801b097d  movups  xmmword ptr [rsp+350h+hMem], xmm0
0x1801b0982  mov     rax, [rax+18h]
0x1801b0986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b098b  mov     edi, eax
0x1801b098d  test    eax, eax
0x1801b098f  js      loc_1801B0ECC
0x1801b0995  mov     esi, 2
0x1801b099a  lea     rcx, [rbp+250h+FindFileData]; void *
0x1801b099e  xor     edx, edx; Val
0x1801b09a0  mov     r8d, 250h; Size
0x1801b09a6  mov     r13d, esi
0x1801b09a9  call    memset_0
0x1801b09ae  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x1801b09b2  mov     rcx, rbx; lpFileName
0x1801b09b5  call    cs:__imp_FindFirstFileW
0x1801b09bc  nop     dword ptr [rax+rax+00h]
0x1801b09c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801b09c5  jz      short loc_1801B09DC
0x1801b09c7  mov     rcx, rax; hFindFile
0x1801b09ca  mov     r13d, 2000h
0x1801b09d0  call    cs:__imp_FindClose
0x1801b09d7  nop     dword ptr [rax+rax+00h]
0x1801b09dc  mov     rcx, rbx; lpFileName
0x1801b09df  call    cs:__imp_GetFileAttributesW
0x1801b09e6  nop     dword ptr [rax+rax+00h]
0x1801b09eb  cmp     eax, 0FFFFFFFFh
0x1801b09ee  jz      short loc_1801B0A08
0x1801b09f0  test    al, 5
0x1801b09f2  jz      short loc_1801B0A08
0x1801b09f4  and     eax, 0FFFFFFFAh
0x1801b09f7  mov     rcx, rbx; lpFileName
0x1801b09fa  mov     edx, eax; dwFileAttributes
0x1801b09fc  call    cs:__imp_SetFileAttributesW
0x1801b0a03  nop     dword ptr [rax+rax+00h]
0x1801b0a08  xor     r15d, r15d
0x1801b0a0b  test    byte ptr [r14], 4
0x1801b0a0f  jz      short loc_1801B0A19
0x1801b0a11  mov     r15d, [r14+24h]
0x1801b0a15  and     r15d, 0FFFFFFEFh
0x1801b0a19  mov     eax, dword ptr [rsp+350h+hMem]
0x1801b0a1d  sub     eax, 1
0x1801b0a20  jz      loc_1801B0C12
0x1801b0a26  sub     eax, 3
0x1801b0a29  jz      loc_1801B0ABB
0x1801b0a2f  cmp     eax, 4
0x1801b0a32  jnz     loc_1801B0D40
0x1801b0a38  lea     r9, [rsp+350h+ppstgOpen]; ppstgOpen
0x1801b0a3d  mov     [rsp+350h+ppstgOpen], 0
0x1801b0a46  xor     r8d, r8d; reserved
0x1801b0a49  mov     edx, 1012h; grfMode
0x1801b0a4e  mov     rcx, rbx; pwcsName
0x1801b0a51  call    cs:__imp_StgCreateDocfile
0x1801b0a58  nop     dword ptr [rax+rax+00h]
0x1801b0a5d  mov     edi, eax
0x1801b0a5f  test    eax, eax
0x1801b0a61  js      loc_1801B0EBB
0x1801b0a67  mov     r10, [rsp+350h+hMem+8]
0x1801b0a6c  xor     r9d, r9d
0x1801b0a6f  mov     rcx, [rsp+350h+ppstgOpen]
0x1801b0a74  xor     r8d, r8d
0x1801b0a77  mov     qword ptr [rsp+350h+dwCreationDisposition], rcx
0x1801b0a7c  xor     edx, edx
0x1801b0a7e  mov     rcx, r10
0x1801b0a81  mov     rax, [r10]
0x1801b0a84  mov     rax, [rax+38h]
0x1801b0a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0a8d  mov     rcx, [rsp+350h+ppstgOpen]
0x1801b0a92  mov     edi, eax
0x1801b0a94  mov     edx, 1
0x1801b0a99  mov     rax, [rcx]
0x1801b0a9c  mov     rax, [rax+48h]
0x1801b0aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0aa5  mov     rcx, [rsp+350h+ppstgOpen]
0x1801b0aaa  mov     rax, [rcx]
0x1801b0aad  mov     rax, [rax+10h]
0x1801b0ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0ab6  jmp     loc_1801B0D19
0x1801b0abb  lea     rcx, [rsp+350h+ppstgOpen]
0x1801b0ac0  mov     [rsp+350h+ppstgOpen], 0
0x1801b0ac9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801b0ace  lea     r8, [rsp+350h+ppstgOpen]; ppstm
0x1801b0ad3  mov     edx, 1021h; grfMode
0x1801b0ad8  mov     rcx, rbx; pszFile
0x1801b0adb  call    cs:__imp_SHCreateStreamOnFileW
0x1801b0ae2  nop     dword ptr [rax+rax+00h]
0x1801b0ae7  mov     edi, eax
0x1801b0ae9  test    eax, eax
0x1801b0aeb  js      loc_1801B0C03
0x1801b0af1  mov     rcx, [rsp+350h+hMem+8]
0x1801b0af6  lea     r9, [rsp+350h+var_2E0]
0x1801b0afb  mov     [rsp+350h+var_2E0], 0
0x1801b0b04  mov     r8d, 1
0x1801b0b0a  mov     [rsp+350h+var_310], 0
0x1801b0b13  mov     r13d, 2000h
0x1801b0b19  mov     rdx, [rsp+350h+var_310]
0x1801b0b1e  mov     rax, [rcx]
0x1801b0b21  mov     rax, [rax+28h]
0x1801b0b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0b2a  mov     edi, 80070005h
0x1801b0b2f  mov     esi, eax
0x1801b0b31  cmp     eax, edi
0x1801b0b33  jz      loc_1801B0BEA
0x1801b0b39  test    eax, eax
0x1801b0b3b  js      short loc_1801B0B5B
0x1801b0b3d  mov     rcx, [rsp+350h+hMem+8]
0x1801b0b42  xor     r9d, r9d
0x1801b0b45  mov     rdx, [rsp+350h+var_310]
0x1801b0b4a  xor     r8d, r8d
0x1801b0b4d  mov     rax, [rcx]
0x1801b0b50  mov     rax, [rax+28h]
0x1801b0b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0b59  mov     esi, eax
0x1801b0b5b  mov     rdx, [rsp+350h+hMem+8]; struct IStream *
0x1801b0b60  or      eax, 0FFFFFFFFh
0x1801b0b63  mov     rcx, [rsp+350h+var_308]; struct IDataObject *
0x1801b0b68  mov     r8, r12; struct PROGRESSINFO *
0x1801b0b6b  mov     dword ptr [rsp+350h+var_310], eax
0x1801b0b6f  mov     dword ptr [rsp+350h+var_310+4], eax
0x1801b0b73  call    ?DataObj_ShouldCopyWithProgress@@YAHPEAUIDataObject@@PEAUIStream@@PEBUPROGRESSINFO@@@Z; DataObj_ShouldCopyWithProgress(IDataObject *,IStream *,PROGRESSINFO const *)
0x1801b0b78  mov     rdx, [rsp+350h+ppstgOpen]
0x1801b0b7d  mov     rcx, [rsp+350h+hMem+8]
0x1801b0b82  test    eax, eax
0x1801b0b84  jz      short loc_1801B0BA7
0x1801b0b86  mov     rax, [r12+8]
0x1801b0b8b  mov     r9, [r12+10h]
0x1801b0b90  mov     r8, [r12]
0x1801b0b94  mov     qword ptr [rsp+350h+dwCreationDisposition], rax
0x1801b0b99  call    cs:__imp_SHCopyStreamWithProgress
0x1801b0ba0  nop     dword ptr [rax+rax+00h]
0x1801b0ba5  jmp     short loc_1801B0BC4
0x1801b0ba7  mov     rax, [rcx]
0x1801b0baa  xor     r9d, r9d
0x1801b0bad  mov     r8, [rsp+350h+var_310]
0x1801b0bb2  mov     qword ptr [rsp+350h+dwCreationDisposition], 0
0x1801b0bbb  mov     rax, [rax+38h]
0x1801b0bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0bc4  mov     edi, eax
0x1801b0bc6  test    esi, esi
0x1801b0bc8  js      short loc_1801B0BE6
0x1801b0bca  mov     rcx, [rsp+350h+hMem+8]
0x1801b0bcf  xor     r9d, r9d
0x1801b0bd2  mov     rdx, [rsp+350h+var_2E0]
0x1801b0bd7  xor     r8d, r8d
0x1801b0bda  mov     rax, [rcx]
0x1801b0bdd  mov     rax, [rax+28h]
0x1801b0be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0be6  test    edi, edi
0x1801b0be8  jns     short loc_1801B0C03
0x1801b0bea  lea     rcx, [rsp+350h+ppstgOpen]
0x1801b0bef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801b0bf4  mov     rcx, rbx; lpFileName
0x1801b0bf7  call    cs:__imp_DeleteFileW
0x1801b0bfe  nop     dword ptr [rax+rax+00h]
0x1801b0c03  lea     rcx, [rsp+350h+ppstgOpen]
0x1801b0c08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801b0c0d  jmp     loc_1801B0D38
0x1801b0c12  xor     r9d, r9d; lpSecurityAttributes
0x1801b0c15  mov     [rsp+350h+hTemplateFile], 0; hTemplateFile
0x1801b0c1e  mov     [rsp+350h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1801b0c23  mov     edx, 0C0000000h; dwDesiredAccess
0x1801b0c28  mov     rcx, rbx; lpFileName
0x1801b0c2b  mov     [rsp+350h+dwCreationDisposition], esi; dwCreationDisposition
0x1801b0c2f  lea     r8d, [r9+3]; dwShareMode
0x1801b0c33  call    cs:__imp_CreateFileW
0x1801b0c3a  nop     dword ptr [rax+rax+00h]
0x1801b0c3f  mov     rsi, rax
0x1801b0c42  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801b0c46  jz      loc_1801B0D31
0x1801b0c4c  test    byte ptr [r14], 40h
0x1801b0c50  mov     dword ptr [rsp+350h+ppstgOpen], 0
0x1801b0c58  jz      short loc_1801B0C60
0x1801b0c5a  mov     r12d, [r14+44h]
0x1801b0c5e  jmp     short loc_1801B0C74
0x1801b0c60  mov     rcx, [rsp+350h+hMem+8]; hMem
0x1801b0c65  call    cs:__imp_GlobalSize
0x1801b0c6c  nop     dword ptr [rax+rax+00h]
0x1801b0c71  mov     r12, rax
0x1801b0c74  mov     rcx, [rsp+350h+hMem+8]; hMem
0x1801b0c79  call    cs:__imp_GlobalLock
0x1801b0c80  nop     dword ptr [rax+rax+00h]
0x1801b0c85  lea     r9, [rsp+350h+ppstgOpen]; lpNumberOfBytesWritten
0x1801b0c8a  mov     qword ptr [rsp+350h+dwCreationDisposition], 0; lpOverlapped
0x1801b0c93  mov     rdx, rax; lpBuffer
0x1801b0c96  mov     r8d, r12d; nNumberOfBytesToWrite
0x1801b0c99  mov     rcx, rsi; hFile
0x1801b0c9c  call    cs:__imp_WriteFile
0x1801b0ca3  nop     dword ptr [rax+rax+00h]
0x1801b0ca8  test    eax, eax
0x1801b0caa  jnz     short loc_1801B0CB3
0x1801b0cac  call    ResultFromLastError
0x1801b0cb1  mov     edi, eax
0x1801b0cb3  mov     rcx, [rsp+350h+hMem+8]; hMem
0x1801b0cb8  call    cs:__imp_GlobalUnlock
0x1801b0cbf  nop     dword ptr [rax+rax+00h]
0x1801b0cc4  mov     edx, [r14]
0x1801b0cc7  test    dl, 38h
0x1801b0cca  jz      short loc_1801B0D0A
0x1801b0ccc  mov     eax, edx
0x1801b0cce  lea     rcx, [r14+38h]
0x1801b0cd2  and     al, 20h
0x1801b0cd4  neg     al
0x1801b0cd6  mov     eax, edx
0x1801b0cd8  sbb     r9, r9
0x1801b0cdb  and     al, 10h
0x1801b0cdd  and     r9, rcx; lpLastWriteTime
0x1801b0ce0  lea     rcx, [r14+30h]
0x1801b0ce4  neg     al
0x1801b0ce6  lea     rax, [r14+28h]
0x1801b0cea  sbb     r8, r8
0x1801b0ced  and     dl, 8
0x1801b0cf0  and     r8, rcx; lpLastAccessTime
0x1801b0cf3  mov     rcx, rsi; hFile
0x1801b0cf6  neg     dl
0x1801b0cf8  sbb     rdx, rdx
0x1801b0cfb  and     rdx, rax; lpCreationTime
0x1801b0cfe  call    cs:__imp_SetFileTime
0x1801b0d05  nop     dword ptr [rax+rax+00h]
0x1801b0d0a  mov     rcx, rsi; hObject
0x1801b0d0d  call    cs:__imp_CloseHandle
0x1801b0d14  nop     dword ptr [rax+rax+00h]
0x1801b0d19  test    edi, edi
0x1801b0d1b  jns     short loc_1801B0D40
0x1801b0d1d  mov     rcx, rbx; lpFileName
0x1801b0d20  call    cs:__imp_DeleteFileW
0x1801b0d27  nop     dword ptr [rax+rax+00h]
0x1801b0d2c  jmp     loc_1801B0EBB
0x1801b0d31  call    ResultFromLastError
0x1801b0d36  mov     edi, eax
0x1801b0d38  test    edi, edi
0x1801b0d3a  js      loc_1801B0EBB
0x1801b0d40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54794917@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54794917@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54794917> `wil::Feature<__WilFeatureTraits_Feature_54794917>::GetImpl(void)'::`2'::impl
0x1801b0d47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54794917@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54794917>::__private_IsEnabled(void)
0x1801b0d4c  test    al, al
0x1801b0d4e  jz      short loc_1801B0D66
0x1801b0d50  mov     edx, [rbp+250h+arg_28]; unsigned int
0x1801b0d56  lea     eax, [rdx-1]
0x1801b0d59  cmp     eax, 0FFFFFFFDh
0x1801b0d5c  ja      short loc_1801B0D66
0x1801b0d5e  mov     rcx, rbx; unsigned __int16 *
0x1801b0d61  call    ?AddZoneIdentifier@@YAJPEBGK0@Z; AddZoneIdentifier(ushort const *,ulong,ushort const *)
0x1801b0d66  cmp     dword ptr [rsp+350h+hMem], 1
0x1801b0d6b  jz      loc_1801B0E55
0x1801b0d71  xor     esi, esi
0x1801b0d73  test    byte ptr [r14], 38h
0x1801b0d77  jz      loc_1801B0E3C
0x1801b0d7d  mov     [rsp+350h+hTemplateFile], rsi; hTemplateFile
0x1801b0d82  lea     r8d, [rsi+1]; dwShareMode
0x1801b0d86  mov     [rsp+350h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x1801b0d8a  xor     r9d, r9d; lpSecurityAttributes
0x1801b0d8d  mov     edx, 40000000h; dwDesiredAccess
0x1801b0d92  mov     [rsp+350h+dwCreationDisposition], 3; dwCreationDisposition
0x1801b0d9a  mov     rcx, rbx; lpFileName
0x1801b0d9d  call    cs:__imp_CreateFileW
0x1801b0da4  nop     dword ptr [rax+rax+00h]
0x1801b0da9  mov     r12, rax
0x1801b0dac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801b0db0  jz      loc_1801B0E3C
0x1801b0db6  mov     r10d, [r14]
0x1801b0db9  lea     rdx, [r14+38h]
0x1801b0dbd  mov     ecx, r10d
0x1801b0dc0  lea     rax, [r14+30h]
0x1801b0dc4  and     cl, 20h
0x1801b0dc7  neg     cl
0x1801b0dc9  mov     ecx, r10d
0x1801b0dcc  sbb     r9, r9
0x1801b0dcf  and     cl, 10h
0x1801b0dd2  and     r9, rdx; lpLastWriteTime
0x1801b0dd5  neg     cl
0x1801b0dd7  mov     rcx, r12; hFile
0x1801b0dda  sbb     r8, r8
0x1801b0ddd  and     r10b, 8
0x1801b0de1  and     r8, rax; lpLastAccessTime
0x1801b0de4  lea     rax, [r14+28h]
0x1801b0de8  neg     r10b
0x1801b0deb  sbb     rdx, rdx
0x1801b0dee  and     rdx, rax; lpCreationTime
0x1801b0df1  call    cs:__imp_SetFileTime
0x1801b0df8  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
