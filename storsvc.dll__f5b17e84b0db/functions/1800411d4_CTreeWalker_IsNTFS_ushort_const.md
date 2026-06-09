# CTreeWalker::IsNTFS(ushort const *)

- ea: `0x1800411d4`
- end: `0x180041391`
- name: `?IsNTFS@CTreeWalker@@QEAAHPEBG@Z`
- size: `445`
- prototype: `int(CTreeWalker *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, loader_planting`

## callers

- `0x180040da4`

## callees

- `0x18000d030`
- `0x18000d450`
- `0x18000ddb0`
- `0x180019d4c`
- `0x18001dcf4`
- `0x1800411d4`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004121e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004121e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004126a`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18004126a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800412d9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800412d9`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180041247`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180041247`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180041203`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180041203`

## string_xrefs

- `0x1800411fc`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTreeWalker::IsNTFS(CTreeWalker *this, const unsigned __int16 *a2)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  HANDLE FileW; // rax
  __int64 v9; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v10; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v11[96]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szVolumeName[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  LibraryW = LoadLibraryW(L"ntdll.dll");
  if ( !LibraryW )
    return 0;
  ProcAddress = GetProcAddress(LibraryW, "NtFsControlFile");
  if ( !ProcAddress )
    return 0;
  szVolumePathName[0] = 0;
  if ( !GetVolumePathNameW(a2, szVolumePathName, 0x104u) )
    return 0;
  szVolumeName[0] = 0;
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
    return 0;
  v5 = -1;
  do
    ++v5;
  while ( szVolumeName[v5] );
  if ( v5 )
  {
    v6 = 2 * v5 - 2;
    if ( v6 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v6) = 0;
  }
  else
  {
    szVolumeName[0] = 0;
  }
  v9 = 0;
  FileW = CreateFileW(szVolumeName, 0x80000000, 3u, 0, 3u, 0x30000000u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v9,
    FileW);
  if ( v9 == -1
    || (memset_0(v11, 0, sizeof(v11)),
        v10 = 0,
        ((int (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, __int128 *, int, _QWORD, _DWORD, _BYTE *, int))ProcAddress)(
          v9,
          0,
          0,
          0,
          &v10,
          589924,
          0,
          0,
          v11,
          96) < 0) )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
    return 0;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  return 1;
}

```

## disassembly

```asm
0x1800411d4  push    rbp
0x1800411d6  push    rbx
0x1800411d7  push    rsi
0x1800411d8  push    rdi
0x1800411d9  lea     rbp, [rsp-418h]
0x1800411e1  sub     rsp, 518h
0x1800411e8  mov     rax, cs:__security_cookie
0x1800411ef  xor     rax, rsp
0x1800411f2  mov     [rbp+430h+var_30], rax
0x1800411f9  mov     rbx, rdx
0x1800411fc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180041203  call    cs:__imp_LoadLibraryW
0x180041209  xor     esi, esi
0x18004120b  test    rax, rax
0x18004120e  jz      loc_1800412FE
0x180041214  lea     rdx, aNtfscontrolfil; "NtFsControlFile"
0x18004121b  mov     rcx, rax; hModule
0x18004121e  call    cs:__imp_GetProcAddress
0x180041224  mov     rdi, rax
0x180041227  test    rax, rax
0x18004122a  jz      loc_1800412FE
0x180041230  mov     [rbp+430h+szVolumePathName], si
0x180041237  mov     r8d, 104h; cchBufferLength
0x18004123d  lea     rdx, [rbp+430h+szVolumePathName]; lpszVolumePathName
0x180041244  mov     rcx, rbx; lpszFileName
0x180041247  call    cs:__imp_GetVolumePathNameW
0x18004124d  test    eax, eax
0x18004124f  jz      loc_1800412FE
0x180041255  mov     [rbp+430h+szVolumeName], si
0x180041259  mov     r8d, 104h; cchBufferLength
0x18004125f  lea     rdx, [rbp+430h+szVolumeName]; lpszVolumeName
0x180041263  lea     rcx, [rbp+430h+szVolumePathName]; lpszVolumeMountPoint
0x18004126a  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180041270  test    eax, eax
0x180041272  jz      loc_1800412FE
0x180041278  lea     rcx, [rbp+430h+szVolumeName]
0x18004127c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041280  inc     rax
0x180041283  cmp     [rcx+rax*2], si
0x180041287  jnz     short loc_180041280
0x180041289  test    rax, rax
0x18004128c  jz      short loc_1800412AC
0x18004128e  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180041296  cmp     rcx, 208h
0x18004129d  jnb     short loc_1800412A6
0x18004129f  mov     [rbp+rcx+430h+szVolumeName], si
0x1800412a4  jmp     short loc_1800412B0
0x1800412a6  call    __report_rangecheckfailure
0x1800412ac  mov     [rbp+430h+szVolumeName], si
0x1800412b0  mov     [rsp+530h+var_4D0], rsi
0x1800412b5  mov     [rsp+530h+hTemplateFile], rsi; hTemplateFile
0x1800412ba  mov     [rsp+530h+dwFlagsAndAttributes], 30000000h; dwFlagsAndAttributes
0x1800412c2  mov     r8d, 3; dwShareMode
0x1800412c8  mov     [rsp+530h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800412cd  xor     r9d, r9d; lpSecurityAttributes
0x1800412d0  mov     edx, 80000000h; dwDesiredAccess
0x1800412d5  lea     rcx, [rbp+430h+szVolumeName]; lpFileName
0x1800412d9  call    cs:__imp_CreateFileW
0x1800412df  mov     rdx, rax
0x1800412e2  lea     rcx, [rsp+530h+var_4D0]
0x1800412e7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800412ec  cmp     [rsp+530h+var_4D0], 0FFFFFFFFFFFFFFFFh
0x1800412f2  jnz     short loc_18004131B
0x1800412f4  lea     rcx, [rsp+530h+var_4D0]
0x1800412f9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800412fe  xor     eax, eax
0x180041300  mov     rcx, [rbp+430h+var_30]
0x180041307  xor     rcx, rsp; StackCookie
0x18004130a  call    __security_check_cookie
0x18004130f  add     rsp, 518h
0x180041316  pop     rdi
0x180041317  pop     rsi
0x180041318  pop     rbx
0x180041319  pop     rbp
0x18004131a  retn
0x18004131b  mov     ebx, 60h ; '`'
0x180041320  mov     r8d, ebx; Size
0x180041323  xor     edx, edx; Val
0x180041325  lea     rcx, [rbp+430h+var_4B0]; void *
0x180041329  call    memset_0
0x18004132e  xorps   xmm0, xmm0
0x180041331  movups  [rsp+530h+var_4C8], xmm0
0x180041336  mov     [rsp+530h+var_4E8], ebx
0x18004133a  lea     rax, [rbp+430h+var_4B0]
0x18004133e  mov     [rsp+530h+var_4F0], rax
0x180041343  mov     [rsp+530h+var_4F8], esi
0x180041347  mov     [rsp+530h+hTemplateFile], rsi
0x18004134c  mov     [rsp+530h+dwFlagsAndAttributes], 90064h
0x180041354  lea     rax, [rsp+530h+var_4C8]
0x180041359  mov     qword ptr [rsp+530h+dwCreationDisposition], rax
0x18004135e  xor     r9d, r9d
0x180041361  xor     r8d, r8d
0x180041364  xor     edx, edx
0x180041366  mov     rcx, [rsp+530h+var_4D0]
0x18004136b  mov     rax, rdi
0x18004136e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041373  nop
0x180041374  test    eax, eax
0x180041376  jns     short loc_18004137D
0x180041378  jmp     loc_1800412F4
0x18004137d  lea     rcx, [rsp+530h+var_4D0]
0x180041382  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180041387  mov     eax, 1
0x18004138c  jmp     loc_180041300
```
