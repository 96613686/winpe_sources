# DataObj_SaveToFile

- ea: `0x18019c70c`
- end: `0x18019cc3d`
- name: `DataObj_SaveToFile`
- size: `1329`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18045a4e4`

## callees

- `0x18000f05c`
- `0x1800748f0`
- `0x18019c70c`
- `0x1801d7e88`
- `0x180233280`
- `0x1802342fc`
- `0x18040fb5c`
- `0x18040fcb0`
- `0x180410004`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18019c7aa`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18019c7aa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18019c9ad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18019caa6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18019c9ad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18019caa6`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18019ca90`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18019cb67`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18019ca90`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18019cb67`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019c7b3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18019c7b3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019c9e3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019cb1d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019c9e3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019cb1d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18019c795`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18019c795`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18019ca3a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18019ca3a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18019cb8a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18019cb8a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18019c7ca`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18019cbad`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18019c7ca`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18019cbad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ca99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019cb9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ca99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019cb9a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18019ca50`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18019ca50`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18019ca0f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18019ca0f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18019ca1d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18019ca1d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18019c89d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18019c89d`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18019cbf4`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18019cc07`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18019cbf4`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18019cc07`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18019cc12`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18019cc12`
- `ole32!StgCreateDocfile` at `0x18019c819`
- `ole32!StgCreateDocfile` at `0x18019c819`
- `Windows.Storage!SHCopyStreamWithProgress` at `0x18019c955`
- `Windows.Storage!SHCopyStreamWithProgress` at `0x18019c955`

## pseudocode

```c
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
            DWORD = DataObj_GetDWORD(a1, (unsigned __int16)word_1806B8482, 0);
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
0x18019c70c  push    rbp
0x18019c70e  push    rbx
0x18019c70f  push    rsi
0x18019c710  push    rdi
0x18019c711  push    r12
0x18019c713  push    r13
0x18019c715  push    r14
0x18019c717  push    r15
0x18019c719  lea     rbp, [rsp-218h]
0x18019c721  sub     rsp, 318h
0x18019c728  mov     rax, cs:__security_cookie
0x18019c72f  xor     rax, rsp
0x18019c732  mov     [rbp+250h+var_50], rax
0x18019c739  mov     r12, [rbp+250h+arg_20]
0x18019c740  xor     eax, eax
0x18019c742  mov     [rsp+350h+var_2E8], rax
0x18019c747  mov     rbx, r8
0x18019c74a  mov     rax, [rcx]
0x18019c74d  lea     r8, [rsp+350h+hMem]
0x18019c752  xorps   xmm0, xmm0
0x18019c755  mov     [rsp+350h+var_308], rcx
0x18019c75a  mov     r14, r9
0x18019c75d  movups  xmmword ptr [rsp+350h+hMem], xmm0
0x18019c762  mov     rax, [rax+18h]
0x18019c766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c76b  mov     edi, eax
0x18019c76d  test    eax, eax
0x18019c76f  js      loc_18019CC18
0x18019c775  mov     esi, 2
0x18019c77a  lea     rcx, [rbp+250h+FindFileData]; void *
0x18019c77e  xor     edx, edx; Val
0x18019c780  mov     r8d, 250h; Size
0x18019c786  mov     r13d, esi
0x18019c789  call    memset_0
0x18019c78e  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18019c792  mov     rcx, rbx; lpFileName
0x18019c795  call    cs:__imp_FindFirstFileW
0x18019c79b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019c79f  jz      short loc_18019C7B0
0x18019c7a1  mov     rcx, rax; hFindFile
0x18019c7a4  mov     r13d, 2000h
0x18019c7aa  call    cs:__imp_FindClose
0x18019c7b0  mov     rcx, rbx; lpFileName
0x18019c7b3  call    cs:__imp_GetFileAttributesW
0x18019c7b9  cmp     eax, 0FFFFFFFFh
0x18019c7bc  jz      short loc_18019C7D0
0x18019c7be  test    al, 5
0x18019c7c0  jz      short loc_18019C7D0
0x18019c7c2  and     eax, 0FFFFFFFAh
0x18019c7c5  mov     rcx, rbx; lpFileName
0x18019c7c8  mov     edx, eax; dwFileAttributes
0x18019c7ca  call    cs:__imp_SetFileAttributesW
0x18019c7d0  xor     r15d, r15d
0x18019c7d3  test    byte ptr [r14], 4
0x18019c7d7  jz      short loc_18019C7E1
0x18019c7d9  mov     r15d, [r14+24h]
0x18019c7dd  and     r15d, 0FFFFFFEFh
0x18019c7e1  mov     eax, dword ptr [rsp+350h+hMem]
0x18019c7e5  sub     eax, 1
0x18019c7e8  jz      loc_18019C9C2
0x18019c7ee  sub     eax, 3
0x18019c7f1  jz      loc_18019C87D
0x18019c7f7  cmp     eax, 4
0x18019c7fa  jnz     loc_18019CAC0
0x18019c800  lea     r9, [rsp+350h+ppstgOpen]; ppstgOpen
0x18019c805  mov     [rsp+350h+ppstgOpen], 0
0x18019c80e  xor     r8d, r8d; reserved
0x18019c811  mov     edx, 1012h; grfMode
0x18019c816  mov     rcx, rbx; pwcsName
0x18019c819  call    cs:__imp_StgCreateDocfile
0x18019c81f  mov     edi, eax
0x18019c821  test    eax, eax
0x18019c823  js      loc_18019CC0D
0x18019c829  mov     r10, [rsp+350h+hMem+8]
0x18019c82e  xor     r9d, r9d
0x18019c831  mov     rcx, [rsp+350h+ppstgOpen]
0x18019c836  xor     r8d, r8d
0x18019c839  mov     qword ptr [rsp+350h+dwCreationDisposition], rcx
0x18019c83e  xor     edx, edx
0x18019c840  mov     rcx, r10
0x18019c843  mov     rax, [r10]
0x18019c846  mov     rax, [rax+38h]
0x18019c84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c84f  mov     rcx, [rsp+350h+ppstgOpen]
0x18019c854  mov     edi, eax
0x18019c856  mov     edx, 1
0x18019c85b  mov     rax, [rcx]
0x18019c85e  mov     rax, [rax+48h]
0x18019c862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c867  mov     rcx, [rsp+350h+ppstgOpen]
0x18019c86c  mov     rax, [rcx]
0x18019c86f  mov     rax, [rax+10h]
0x18019c873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c878  jmp     loc_18019CA9F
0x18019c87d  lea     rcx, [rsp+350h+ppstgOpen]
0x18019c882  mov     [rsp+350h+ppstgOpen], 0
0x18019c88b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019c890  lea     r8, [rsp+350h+ppstgOpen]; ppstm
0x18019c895  mov     edx, 1021h; grfMode
0x18019c89a  mov     rcx, rbx; pszFile
0x18019c89d  call    cs:__imp_SHCreateStreamOnFileW
0x18019c8a3  mov     edi, eax
0x18019c8a5  test    eax, eax
0x18019c8a7  js      loc_18019C9B3
0x18019c8ad  mov     rcx, [rsp+350h+hMem+8]
0x18019c8b2  lea     r9, [rsp+350h+var_2E0]
0x18019c8b7  mov     [rsp+350h+var_2E0], 0
0x18019c8c0  mov     r8d, 1
0x18019c8c6  mov     [rsp+350h+var_310], 0
0x18019c8cf  mov     r13d, 2000h
0x18019c8d5  mov     rdx, [rsp+350h+var_310]
0x18019c8da  mov     rax, [rcx]
0x18019c8dd  mov     rax, [rax+28h]
0x18019c8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c8e6  mov     edi, 80070005h
0x18019c8eb  mov     esi, eax
0x18019c8ed  cmp     eax, edi
0x18019c8ef  jz      loc_18019C9A0
0x18019c8f5  test    eax, eax
0x18019c8f7  js      short loc_18019C917
0x18019c8f9  mov     rcx, [rsp+350h+hMem+8]
0x18019c8fe  xor     r9d, r9d
0x18019c901  mov     rdx, [rsp+350h+var_310]
0x18019c906  xor     r8d, r8d
0x18019c909  mov     rax, [rcx]
0x18019c90c  mov     rax, [rax+28h]
0x18019c910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c915  mov     esi, eax
0x18019c917  mov     rdx, [rsp+350h+hMem+8]; struct IStream *
0x18019c91c  or      eax, 0FFFFFFFFh
0x18019c91f  mov     rcx, [rsp+350h+var_308]; struct IDataObject *
0x18019c924  mov     r8, r12; struct PROGRESSINFO *
0x18019c927  mov     dword ptr [rsp+350h+var_310], eax
0x18019c92b  mov     dword ptr [rsp+350h+var_310+4], eax
0x18019c92f  call    ?DataObj_ShouldCopyWithProgress@@YAHPEAUIDataObject@@PEAUIStream@@PEBUPROGRESSINFO@@@Z; DataObj_ShouldCopyWithProgress(IDataObject *,IStream *,PROGRESSINFO const *)
0x18019c934  mov     rdx, [rsp+350h+ppstgOpen]
0x18019c939  mov     rcx, [rsp+350h+hMem+8]
0x18019c93e  test    eax, eax
0x18019c940  jz      short loc_18019C95D
0x18019c942  mov     rax, [r12+8]
0x18019c947  mov     r9, [r12+10h]
0x18019c94c  mov     r8, [r12]
0x18019c950  mov     qword ptr [rsp+350h+dwCreationDisposition], rax
0x18019c955  call    cs:__imp_SHCopyStreamWithProgress
0x18019c95b  jmp     short loc_18019C97A
0x18019c95d  mov     rax, [rcx]
0x18019c960  xor     r9d, r9d
0x18019c963  mov     r8, [rsp+350h+var_310]
0x18019c968  mov     qword ptr [rsp+350h+dwCreationDisposition], 0
0x18019c971  mov     rax, [rax+38h]
0x18019c975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c97a  mov     edi, eax
0x18019c97c  test    esi, esi
0x18019c97e  js      short loc_18019C99C
0x18019c980  mov     rcx, [rsp+350h+hMem+8]
0x18019c985  xor     r9d, r9d
0x18019c988  mov     rdx, [rsp+350h+var_2E0]
0x18019c98d  xor     r8d, r8d
0x18019c990  mov     rax, [rcx]
0x18019c993  mov     rax, [rax+28h]
0x18019c997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c99c  test    edi, edi
0x18019c99e  jns     short loc_18019C9B3
0x18019c9a0  lea     rcx, [rsp+350h+ppstgOpen]
0x18019c9a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019c9aa  mov     rcx, rbx; lpFileName
0x18019c9ad  call    cs:__imp_DeleteFileW
0x18019c9b3  lea     rcx, [rsp+350h+ppstgOpen]
0x18019c9b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019c9bd  jmp     loc_18019CAB8
0x18019c9c2  xor     r9d, r9d; lpSecurityAttributes
0x18019c9c5  mov     [rsp+350h+hTemplateFile], 0; hTemplateFile
0x18019c9ce  mov     [rsp+350h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18019c9d3  mov     edx, 0C0000000h; dwDesiredAccess
0x18019c9d8  mov     rcx, rbx; lpFileName
0x18019c9db  mov     [rsp+350h+dwCreationDisposition], esi; dwCreationDisposition
0x18019c9df  lea     r8d, [r9+3]; dwShareMode
0x18019c9e3  call    cs:__imp_CreateFileW
0x18019c9e9  mov     rsi, rax
0x18019c9ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019c9f0  jz      loc_18019CAB1
0x18019c9f6  test    byte ptr [r14], 40h
0x18019c9fa  mov     dword ptr [rsp+350h+ppstgOpen], 0
0x18019ca02  jz      short loc_18019CA0A
0x18019ca04  mov     r12d, [r14+44h]
0x18019ca08  jmp     short loc_18019CA18
0x18019ca0a  mov     rcx, [rsp+350h+hMem+8]; hMem
0x18019ca0f  call    cs:__imp_GlobalSize
0x18019ca15  mov     r12, rax
0x18019ca18  mov     rcx, [rsp+350h+hMem+8]; hMem
0x18019ca1d  call    cs:__imp_GlobalLock
0x18019ca23  lea     r9, [rsp+350h+ppstgOpen]; lpNumberOfBytesWritten
0x18019ca28  mov     qword ptr [rsp+350h+dwCreationDisposition], 0; lpOverlapped
0x18019ca31  mov     rdx, rax; lpBuffer
0x18019ca34  mov     r8d, r12d; nNumberOfBytesToWrite
0x18019ca37  mov     rcx, rsi; hFile
0x18019ca3a  call    cs:__imp_WriteFile
0x18019ca40  test    eax, eax
0x18019ca42  jnz     short loc_18019CA4B
0x18019ca44  call    ResultFromLastError
0x18019ca49  mov     edi, eax
0x18019ca4b  mov     rcx, [rsp+350h+hMem+8]; hMem
0x18019ca50  call    cs:__imp_GlobalUnlock
0x18019ca56  mov     edx, [r14]
0x18019ca59  test    dl, 38h
0x18019ca5c  jz      short loc_18019CA96
0x18019ca5e  mov     eax, edx
0x18019ca60  lea     rcx, [r14+38h]
0x18019ca64  and     al, 20h
0x18019ca66  neg     al
0x18019ca68  mov     eax, edx
0x18019ca6a  sbb     r9, r9
0x18019ca6d  and     al, 10h
0x18019ca6f  and     r9, rcx; lpLastWriteTime
0x18019ca72  lea     rcx, [r14+30h]
0x18019ca76  neg     al
0x18019ca78  lea     rax, [r14+28h]
0x18019ca7c  sbb     r8, r8
0x18019ca7f  and     dl, 8
0x18019ca82  and     r8, rcx; lpLastAccessTime
0x18019ca85  mov     rcx, rsi; hFile
0x18019ca88  neg     dl
0x18019ca8a  sbb     rdx, rdx
0x18019ca8d  and     rdx, rax; lpCreationTime
0x18019ca90  call    cs:__imp_SetFileTime
0x18019ca96  mov     rcx, rsi; hObject
0x18019ca99  call    cs:__imp_CloseHandle
0x18019ca9f  test    edi, edi
0x18019caa1  jns     short loc_18019CAC0
0x18019caa3  mov     rcx, rbx; lpFileName
0x18019caa6  call    cs:__imp_DeleteFileW
0x18019caac  jmp     loc_18019CC0D
0x18019cab1  call    ResultFromLastError
0x18019cab6  mov     edi, eax
0x18019cab8  test    edi, edi
0x18019caba  js      loc_18019CC0D
0x18019cac0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54794917@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54794917@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54794917> `wil::Feature<__WilFeatureTraits_Feature_54794917>::GetImpl(void)'::`2'::impl
0x18019cac7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54794917@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54794917>::__private_IsEnabled(void)
0x18019cacc  test    al, al
0x18019cace  jz      short loc_18019CAE6
0x18019cad0  mov     edx, [rbp+250h+arg_28]; unsigned int
0x18019cad6  lea     eax, [rdx-1]
0x18019cad9  cmp     eax, 0FFFFFFFDh
0x18019cadc  ja      short loc_18019CAE6
0x18019cade  mov     rcx, rbx; unsigned __int16 *
0x18019cae1  call    ?AddZoneIdentifier@@YAJPEBGK0@Z; AddZoneIdentifier(ushort const *,ulong,ushort const *)
0x18019cae6  cmp     dword ptr [rsp+350h+hMem], 1
0x18019caeb  jz      loc_18019CBB3
0x18019caf1  xor     esi, esi
0x18019caf3  test    byte ptr [r14], 38h
0x18019caf7  jz      loc_18019CBA0
0x18019cafd  mov     [rsp+350h+hTemplateFile], rsi; hTemplateFile
0x18019cb02  lea     r8d, [rsi+1]; dwShareMode
0x18019cb06  mov     [rsp+350h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18019cb0a  xor     r9d, r9d; lpSecurityAttributes
0x18019cb0d  mov     edx, 40000000h; dwDesiredAccess
0x18019cb12  mov     [rsp+350h+dwCreationDisposition], 3; dwCreationDisposition
0x18019cb1a  mov     rcx, rbx; lpFileName
0x18019cb1d  call    cs:__imp_CreateFileW
0x18019cb23  mov     r12, rax
0x18019cb26  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019cb2a  jz      short loc_18019CBA0
0x18019cb2c  mov     r10d, [r14]
0x18019cb2f  lea     rdx, [r14+38h]
0x18019cb33  mov     ecx, r10d
0x18019cb36  lea     rax, [r14+30h]
0x18019cb3a  and     cl, 20h
0x18019cb3d  neg     cl
0x18019cb3f  mov     ecx, r10d
0x18019cb42  sbb     r9, r9
0x18019cb45  and     cl, 10h
0x18019cb48  and     r9, rdx; lpLastWriteTime
0x18019cb4b  neg     cl
0x18019cb4d  mov     rcx, r12; hFile
0x18019cb50  sbb     r8, r8
0x18019cb53  and     r10b, 8
0x18019cb57  and     r8, rax; lpLastAccessTime
0x18019cb5a  lea     rax, [r14+28h]
0x18019cb5e  neg     r10b
0x18019cb61  sbb     rdx, rdx
0x18019cb64  and     rdx, rax; lpCreationTime
0x18019cb67  call    cs:__imp_SetFileTime
0x18019cb6d  xorps   xmm0, xmm0
0x18019cb70  lea     rdx, [rsp+350h+FileInformation]; lpFileInformation
0x18019cb75  xor     eax, eax
0x18019cb77  mov     rcx, r12; hFile
0x18019cb7a  movups  xmmword ptr [rsp+350h+FileInformation.dwFileAttributes], xmm0
0x18019cb7f  mov     [rbp+250h+FileInformation.nFileIndexLow], eax
0x18019cb82  movups  xmmword ptr [rbp+250h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18019cb86  movups  xmmword ptr [rbp+250h+FileInformation.nFileSizeHigh], xmm0
0x18019cb8a  call    cs:__imp_GetFileInformationByHandle
0x18019cb90  test    eax, eax
0x18019cb92  mov     rcx, r12; hObject
0x18019cb95  cmovnz  esi, [rsp+350h+FileInformation.dwFileAttributes]
0x18019cb9a  call    cs:__imp_CloseHandle
0x18019cba0  test    r15d, r15d
0x18019cba3  jz      short loc_18019CBB3
0x18019cba5  or      esi, r15d
0x18019cba8  mov     rcx, rbx; lpFileName
0x18019cbab  mov     edx, esi; dwFileAttributes
  ... truncated ...
```
