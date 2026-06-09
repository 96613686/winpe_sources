# CreateBaseImageVHDWithFolders

- ea: `0x180034f50`
- end: `0x1800355e9`
- name: `CreateBaseImageVHDWithFolders`
- size: `1689`
- prototype: `__int64 __usercall@<rax>(PCWSTR Path@<rcx>, __int64, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x180006660`
- `0x18000d0ec`
- `0x18000e8dc`
- `0x18002ca00`
- `0x18002dfb8`
- `0x18002e07c`
- `0x18002e5c4`
- `0x18002fe2c`
- `0x18002ff50`
- `0x18003139c`
- `0x18003150c`
- `0x18003167c`
- `0x18003208c`
- `0x1800321dc`
- `0x18003437c`
- `0x180034f50`
- `0x18005359c`
- `0x180054fa8`
- `0x18005ca68`
- `0x18005d148`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800353e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035469`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800353e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035469`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035487`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035270`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035270`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035338`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035338`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800353ab`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800353ab`

## string_xrefs

- `0x180034fd2`: `GraphDriver_CreateBaseImageVHDWithFolders`
- `0x18003518b`: `GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories`
- `0x1800352c5`: `GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume`
- `0x1800354a6`: `GraphDriver_CreateVirtualDisk`
- `0x18003536e`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x1800355c4`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x1800355d6`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`
- `0x18003535e`: `Failed to open volume root to dismount it`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CreateBaseImageVHDWithFolders(
        PCWSTR Path,
        DWORD a2,
        unsigned int a3,
        __int64 *a4,
        __int64 a5,
        unsigned int a6)
{
  const WCHAR *v10; // rdi
  unsigned __int16 **v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  LPCWSTR *v14; // r9
  unsigned int i; // ebx
  __int64 v16; // r8
  unsigned __int64 v17; // rcx
  _QWORD *v18; // r9
  const WCHAR *v19; // rcx
  const char *v20; // r9
  const WCHAR *v21; // rcx
  __int64 *FileW; // rbx
  const char *v23; // r9
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rdx
  const char *v26; // r9
  __int64 result; // rax
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-6A0h]
  __int64 *v29; // [rsp+58h] [rbp-670h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-668h] BYREF
  DWORD BytesReturned; // [rsp+78h] [rbp-650h] BYREF
  unsigned int v32; // [rsp+80h] [rbp-648h] BYREF
  unsigned __int16 *Src[3]; // [rsp+88h] [rbp-640h] BYREF
  unsigned __int64 v34; // [rsp+A0h] [rbp-628h]
  _QWORD v35[2]; // [rsp+A8h] [rbp-620h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-610h]
  unsigned __int64 v37; // [rsp+C0h] [rbp-608h]
  LPCWSTR lpPathName[5]; // [rsp+C8h] [rbp-600h] BYREF
  HANDLE v39; // [rsp+F0h] [rbp-5D8h] BYREF
  HANDLE hObject; // [rsp+F8h] [rbp-5D0h]
  LPCWSTR lpFileName[2]; // [rsp+100h] [rbp-5C8h] BYREF
  __int64 v42; // [rsp+110h] [rbp-5B8h]
  unsigned __int64 v43; // [rsp+118h] [rbp-5B0h]
  void **v44; // [rsp+140h] [rbp-588h] BYREF
  int v45; // [rsp+148h] [rbp-580h] BYREF
  char v46; // [rsp+14Ch] [rbp-57Ch]
  int v47; // [rsp+170h] [rbp-558h] BYREF
  const char *v48; // [rsp+178h] [rbp-550h]
  __int64 v49; // [rsp+180h] [rbp-548h]
  char v50; // [rsp+188h] [rbp-540h]
  int v51; // [rsp+190h] [rbp-538h]
  _BYTE v52[152]; // [rsp+198h] [rbp-530h] BYREF
  __int128 v53; // [rsp+230h] [rbp-498h]
  int v54; // [rsp+240h] [rbp-488h]
  __int64 v55; // [rsp+248h] [rbp-480h]
  int *v56; // [rsp+250h] [rbp-478h]
  __int64 v57; // [rsp+258h] [rbp-470h]
  __int64 v58; // [rsp+260h] [rbp-468h]
  void ***v59; // [rsp+268h] [rbp-460h]
  __int64 v60; // [rsp+270h] [rbp-458h]
  int v61; // [rsp+278h] [rbp-450h]
  int *v62; // [rsp+280h] [rbp-448h]
  char v63; // [rsp+288h] [rbp-440h]
  _QWORD v64[42]; // [rsp+290h] [rbp-438h] BYREF
  _QWORD v65[42]; // [rsp+3E0h] [rbp-2E8h] BYREF
  _QWORD v66[42]; // [rsp+530h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+0h]

  BytesReturned = a2;
  v32 = a3;
  v29 = a4;
  memset_0(&v44, 0, 0x150u);
  v45 = 0;
  v46 = 0;
  v50 = 0;
  v47 = 0;
  v48 = "GraphDriver_CreateBaseImageVHDWithFolders";
  v49 = 0;
  v51 = 0;
  v53 = 0;
  memset_0(v52, 0, sizeof(v52));
  v54 = 1;
  v55 = 0;
  v56 = &v45;
  v57 = 0;
  v58 = 0;
  v59 = &v44;
  v60 = 0;
  v61 = 0;
  v62 = &v47;
  v63 = 0;
  v44 = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders::`vftable';
  try
  {
    ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders::StartActivity<unsigned long &,unsigned long &,unsigned short const * &,unsigned long &>(
      (__int64)&v44,
      (int *)&BytesReturned,
      (int *)&v32,
      &v29,
      (int *)&a6);
    OsImageUtilities::Helpers::GetTempVhdPath(Src, Path);
    v10 = (const WCHAR *)Src;
    v11 = Src;
    if ( v34 > 7 )
      v11 = (unsigned __int16 **)Src[0];
    CreateBaseVhd(&v39, v11, a2, a3, a4);
    if ( v42 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    v14 = lpFileName;
    if ( v43 > 7 )
      v14 = (LPCWSTR *)lpFileName[0];
    std::wstring::wstring(v35, v12, v13, v14, v42, L"\\", 1);
    memset_0(v65, 0, sizeof(v65));
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
      v65,
      "GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories");
    v65[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories::`vftable';
    ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories::StartActivity(
      (ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories *)v65,
      (const struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders *)&v44);
    for ( i = 0; i < a6; ++i )
    {
      *(_QWORD *)&SecurityAttributes.nLength = 24;
      *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)(a5 + 16LL * i + 8);
      v16 = *(_QWORD *)(a5 + 16LL * i);
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)(v16 + 2 * v17) );
      if ( 0x7FFFFFFFFFFFFFFELL - v36 < v17 )
        std::_Xlen_string();
      v18 = v35;
      if ( v37 > 7 )
        v18 = (_QWORD *)v35[0];
      std::wstring::wstring(lpPathName, v36, v16, v18, v36, v16, v17);
      v19 = (const WCHAR *)lpPathName;
      if ( lpPathName[3] > (LPCWSTR)7 )
        v19 = lpPathName[0];
      if ( !CreateDirectoryW(v19, &SecurityAttributes) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x569,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
          v20);
      std::wstring::~wstring(lpPathName);
    }
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v65);
    memset_0(v64, 0, sizeof(v64));
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
      v64,
      "GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume");
    v64[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume::`vftable';
    ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume::StartActivity(
      (ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume *)v64,
      (const struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders *)&v44);
    v21 = (const WCHAR *)lpFileName;
    if ( v43 > 7 )
      v21 = lpFileName[0];
    FileW = (__int64 *)CreateFileW(v21, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    v29 = FileW;
    wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
      retaddr,
      (void *)0x57E,
      (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
      (const char *)((unsigned __int64)FileW - 1 <= 0xFFFFFFFFFFFFFFFDuLL),
      (bool)"Failed to open volume root to dismount it",
      dwFlagsAndAttributes);
    BytesReturned = 0;
    if ( !DeviceIoControl(FileW, 0x90020u, 0, 0, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x589,
        (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
        v23);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v64);
    if ( (unsigned __int64)FileW - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    v64[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume::`vftable';
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v64);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v64);
    v65[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories::`vftable';
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v65);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v65);
    std::wstring::~wstring(v35);
    std::wstring::~wstring(lpFileName);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( (char *)v39 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v39);
    memset_0(v66, 0, sizeof(v66));
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
      v66,
      "GraphDriver_CreateVirtualDisk");
    v66[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::`vftable';
    ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::StartActivity(
      (ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk *)v66,
      (const struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders *)&v44);
    v24 = (const unsigned __int16 *)Src;
    if ( v34 > 7 )
      v24 = Src[0];
    CreateVhdFromSource(Path, v24, a3);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v66);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v44);
    v66[0] = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::`vftable';
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v66);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v66);
    if ( v34 > 7 )
      v10 = Src[0];
    OsImageUtilities::Helpers::TryDeleteFile(v10, v25);
    std::wstring::~wstring(Src);
    v44 = &ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders::`vftable';
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v44);
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(&v44);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5A8,
                           (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
                           v26);
  }
  return result;
}

```

## disassembly

```asm
0x180034f50  push    rbx
0x180034f52  push    rsi
0x180034f53  push    rdi
0x180034f54  push    r12
0x180034f56  push    r13
0x180034f58  push    r14
0x180034f5a  push    r15
0x180034f5c  sub     rsp, 690h
0x180034f63  mov     rax, cs:__security_cookie
0x180034f6a  xor     rax, rsp
0x180034f6d  mov     [rsp+6C8h+var_48], rax
0x180034f75  mov     rbx, r9
0x180034f78  mov     r14d, r8d
0x180034f7b  mov     esi, edx
0x180034f7d  mov     r12, rcx
0x180034f80  mov     [rsp+6C8h+BytesReturned], esi
0x180034f84  mov     [rsp+6C8h+var_648], r8d
0x180034f8c  mov     [rsp+6C8h+var_670], rbx
0x180034f91  mov     r15, [rsp+6C8h+arg_20]
0x180034f99  xor     r13d, r13d
0x180034f9c  xor     edx, edx; Val
0x180034f9e  mov     r8d, 150h; Size
0x180034fa4  lea     rcx, [rsp+6C8h+var_588]; void *
0x180034fac  call    memset_0
0x180034fb1  nop
0x180034fb2  mov     [rsp+6C8h+var_580], r13d
0x180034fba  mov     [rsp+6C8h+var_57C], r13b
0x180034fc2  mov     [rsp+6C8h+var_540], r13b
0x180034fca  mov     [rsp+6C8h+var_558], r13d
0x180034fd2  lea     rax, aGraphdriverCre_2; "GraphDriver_CreateBaseImageVHDWithFolde"...
0x180034fd9  mov     [rsp+6C8h+var_550], rax
0x180034fe1  mov     [rsp+6C8h+var_548], r13
0x180034fe9  mov     [rsp+6C8h+var_538], r13d
0x180034ff1  xorps   xmm0, xmm0
0x180034ff4  movdqa  [rsp+6C8h+var_498], xmm0
0x180034ffd  xor     edx, edx; Val
0x180034fff  mov     r8d, 98h; Size
0x180035005  lea     rcx, [rsp+6C8h+var_530]; void *
0x18003500d  call    memset_0
0x180035012  mov     [rsp+6C8h+var_488], 1
0x18003501d  xor     eax, eax
0x18003501f  mov     [rsp+6C8h+var_480], rax
0x180035027  lea     rax, [rsp+6C8h+var_580]
0x18003502f  mov     [rsp+6C8h+var_478], rax
0x180035037  mov     [rsp+6C8h+var_470], r13
0x18003503f  mov     [rsp+6C8h+var_468], r13
0x180035047  lea     rax, [rsp+6C8h+var_588]
0x18003504f  mov     [rsp+6C8h+var_460], rax
0x180035057  mov     [rsp+6C8h+var_458], r13
0x18003505f  mov     [rsp+6C8h+var_450], r13d
0x180035067  lea     rax, [rsp+6C8h+var_558]
0x18003506f  mov     [rsp+6C8h+var_448], rax
0x180035077  mov     [rsp+6C8h+var_440], r13b
0x18003507f  lea     rax, ??_7GraphDriver_CreateBaseImageVHDWithFolders@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders::`vftable'
0x180035086  mov     [rsp+6C8h+var_588], rax
0x18003508e  lea     rax, [rsp+6C8h+arg_28]
0x180035096  mov     qword ptr [rsp+6C8h+dwCreationDisposition], rax
0x18003509b  lea     r9, [rsp+6C8h+var_670]
0x1800350a0  lea     r8, [rsp+6C8h+var_648]
0x1800350a8  lea     rdx, [rsp+6C8h+BytesReturned]
0x1800350ad  lea     rcx, [rsp+6C8h+var_588]
0x1800350b5  call    ??$StartActivity@AEAKAEAKAEAPEBGAEAK@GraphDriver_CreateBaseImageVHDWithFolders@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXAEAK0AEAPEBG0@Z; ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders::StartActivity<ulong &,ulong &,ushort const * &,ulong &>(ulong &,ulong &,ushort const * &,ulong &)
0x1800350ba  nop
0x1800350bb  mov     rdx, r12; pszPath
0x1800350be  lea     rcx, [rsp+6C8h+Src]; Src
0x1800350c6  call    ?GetTempVhdPath@Helpers@OsImageUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; OsImageUtilities::Helpers::GetTempVhdPath(ushort const *)
0x1800350cb  nop
0x1800350cc  lea     rdi, [rsp+6C8h+Src]
0x1800350d4  mov     [rsp+6C8h+var_680], rdi
0x1800350d9  mov     [rsp+6C8h+var_678], 1
0x1800350de  mov     r8d, esi
0x1800350e1  lea     rdx, [rsp+6C8h+Src]
0x1800350e9  cmp     [rsp+6C8h+var_628], 7
0x1800350f2  cmova   rdx, [rsp+6C8h+Src]
0x1800350fb  mov     qword ptr [rsp+6C8h+dwCreationDisposition], rbx
0x180035100  mov     r9d, r14d
0x180035103  lea     rcx, [rsp+6C8h+var_5D8]
0x18003510b  call    ?CreateBaseVhd@@YA?AUMountedVolume@@PEBG_KK0@Z; CreateBaseVhd(ushort const *,unsigned __int64,ulong,ushort const *)
0x180035110  nop
0x180035111  mov     rcx, [rsp+6C8h+var_5B8]
0x180035119  mov     rsi, 7FFFFFFFFFFFFFFEh
0x180035123  mov     rax, rsi
0x180035126  sub     rax, rcx
0x180035129  cmp     rax, 1
0x18003512d  jb      loc_1800355B8
0x180035133  lea     r9, [rsp+6C8h+lpFileName]
0x18003513b  cmp     [rsp+6C8h+var_5B0], 7
0x180035144  cmova   r9, [rsp+6C8h+lpFileName]
0x18003514d  mov     [rsp+6C8h+hTemplateFile], 1
0x180035156  lea     rax, asc_18008E17C; "\\"
0x18003515d  mov     qword ptr [rsp+6C8h+dwFlagsAndAttributes], rax
0x180035162  mov     qword ptr [rsp+6C8h+dwCreationDisposition], rcx
0x180035167  lea     rcx, [rsp+6C8h+var_620]
0x18003516f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180035174  nop
0x180035175  xor     edx, edx; Val
0x180035177  mov     r8d, 150h; Size
0x18003517d  lea     rcx, [rsp+6C8h+var_2E8]; void *
0x180035185  call    memset_0
0x18003518a  nop
0x18003518b  lea     rdx, aGraphdriverCre_1; "GraphDriver_CreateBaseImageVHDWithFolde"...
0x180035192  lea     rcx, [rsp+6C8h+var_2E8]
0x18003519a  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003519f  lea     rax, ??_7GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories::`vftable'
0x1800351a6  mov     [rsp+6C8h+var_2E8], rax
0x1800351ae  lea     rdx, [rsp+6C8h+var_588]; struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders *
0x1800351b6  lea     rcx, [rsp+6C8h+var_2E8]; this
0x1800351be  call    ?StartActivity@GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXAEBVGraphDriver_CreateBaseImageVHDWithFolders@234@@Z; ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories::StartActivity(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders const &)
0x1800351c3  nop
0x1800351c4  mov     ebx, r13d
0x1800351c7  cmp     ebx, [rsp+6C8h+arg_28]
0x1800351ce  jnb     loc_1800352A0
0x1800351d4  mov     qword ptr [rsp+6C8h+SecurityAttributes.nLength], 18h
0x1800351dd  mov     qword ptr [rsp+6C8h+SecurityAttributes.bInheritHandle], r13
0x1800351e2  mov     ecx, ebx
0x1800351e4  add     rcx, rcx
0x1800351e7  mov     rax, [r15+rcx*8+8]
0x1800351ec  mov     [rsp+6C8h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800351f1  mov     r8, [r15+rcx*8]
0x1800351f5  mov     rdx, [rsp+6C8h+var_610]
0x1800351fd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180035201  inc     rcx
0x180035204  cmp     [r8+rcx*2], r13w
0x180035209  jnz     short loc_180035201
0x18003520b  mov     rax, rsi
0x18003520e  sub     rax, rdx
0x180035211  cmp     rax, rcx
0x180035214  jb      loc_1800355BE
0x18003521a  lea     r9, [rsp+6C8h+var_620]
0x180035222  cmp     [rsp+6C8h+var_608], 7
0x18003522b  cmova   r9, [rsp+6C8h+var_620]
0x180035234  mov     [rsp+6C8h+hTemplateFile], rcx
0x180035239  mov     qword ptr [rsp+6C8h+dwFlagsAndAttributes], r8
0x18003523e  mov     qword ptr [rsp+6C8h+dwCreationDisposition], rdx
0x180035243  lea     rcx, [rsp+6C8h+lpPathName]
0x18003524b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180035250  nop
0x180035251  lea     rcx, [rsp+6C8h+lpPathName]
0x180035259  cmp     [rsp+6C8h+var_5E8], 7
0x180035262  cmova   rcx, [rsp+6C8h+lpPathName]; lpPathName
0x18003526b  lea     rdx, [rsp+6C8h+SecurityAttributes]; lpSecurityAttributes
0x180035270  call    cs:__imp_CreateDirectoryW
0x180035277  nop     dword ptr [rax+rax+00h]
0x18003527c  mov     rcx, [rsp+6C8h]; this
0x180035284  test    eax, eax
0x180035286  jz      loc_1800355C4
0x18003528c  lea     rcx, [rsp+6C8h+lpPathName]
0x180035294  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035299  inc     ebx
0x18003529b  jmp     loc_1800351C7
0x1800352a0  lea     rcx, [rsp+6C8h+var_2E8]
0x1800352a8  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800352ad  mov     esi, 150h
0x1800352b2  mov     r8d, esi; Size
0x1800352b5  xor     edx, edx; Val
0x1800352b7  lea     rcx, [rsp+6C8h+var_438]; void *
0x1800352bf  call    memset_0
0x1800352c4  nop
0x1800352c5  lea     rdx, aGraphdriverCre; "GraphDriver_CreateBaseImageVHDWithFolde"...
0x1800352cc  lea     rcx, [rsp+6C8h+var_438]
0x1800352d4  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800352d9  lea     r15, ??_7GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume::`vftable'
0x1800352e0  mov     [rsp+6C8h+var_438], r15
0x1800352e8  lea     rdx, [rsp+6C8h+var_588]; struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders *
0x1800352f0  lea     rcx, [rsp+6C8h+var_438]; this
0x1800352f8  call    ?StartActivity@GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXAEBVGraphDriver_CreateBaseImageVHDWithFolders@234@@Z; ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_DismountVolume::StartActivity(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders const &)
0x1800352fd  nop
0x1800352fe  lea     rcx, [rsp+6C8h+lpFileName]
0x180035306  cmp     [rsp+6C8h+var_5B0], 7
0x18003530f  cmova   rcx, [rsp+6C8h+lpFileName]; lpFileName
0x180035318  mov     [rsp+6C8h+hTemplateFile], r13; hTemplateFile
0x18003531d  mov     [rsp+6C8h+dwFlagsAndAttributes], 80h; char *
0x180035325  mov     r8d, 3; dwShareMode
0x18003532b  mov     [rsp+6C8h+dwCreationDisposition], r8d; dwCreationDisposition
0x180035330  xor     r9d, r9d; lpSecurityAttributes
0x180035333  mov     edx, 0C0000000h; dwDesiredAccess
0x180035338  call    cs:__imp_CreateFileW
0x18003533f  nop     dword ptr [rax+rax+00h]
0x180035344  mov     rbx, rax
0x180035347  mov     [rsp+6C8h+var_670], rax
0x18003534c  dec     rax
0x18003534f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035353  setbe   al
0x180035356  mov     rcx, [rsp+6C8h]; this
0x18003535e  lea     rdx, aFailedToOpenVo; "Failed to open volume root to dismount "...
0x180035365  mov     qword ptr [rsp+6C8h+dwCreationDisposition], rdx; bool
0x18003536a  movzx   r9d, al; char *
0x18003536e  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x180035375  mov     edx, 57Eh; void *
0x18003537a  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x18003537f  mov     [rsp+6C8h+BytesReturned], r13d
0x180035384  mov     [rsp+6C8h+lpOverlapped], r13; lpOverlapped
0x180035389  lea     rax, [rsp+6C8h+BytesReturned]
0x18003538e  mov     [rsp+6C8h+hTemplateFile], rax; lpBytesReturned
0x180035393  mov     [rsp+6C8h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x180035398  mov     qword ptr [rsp+6C8h+dwCreationDisposition], r13; lpOutBuffer
0x18003539d  xor     r9d, r9d; nInBufferSize
0x1800353a0  xor     r8d, r8d; lpInBuffer
0x1800353a3  mov     edx, 90020h; dwIoControlCode
0x1800353a8  mov     rcx, rbx; hDevice
0x1800353ab  call    cs:__imp_DeviceIoControl
0x1800353b2  nop     dword ptr [rax+rax+00h]
0x1800353b7  mov     rcx, [rsp+6C8h]; this
0x1800353bf  test    eax, eax
0x1800353c1  jz      loc_1800355D6
0x1800353c7  lea     rcx, [rsp+6C8h+var_438]
0x1800353cf  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800353d4  nop
0x1800353d5  lea     rax, [rbx-1]
0x1800353d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800353dd  ja      short loc_1800353EF
0x1800353df  mov     rcx, rbx; hObject
0x1800353e2  call    cs:__imp_CloseHandle
0x1800353e9  nop     dword ptr [rax+rax+00h]
0x1800353ee  nop
0x1800353ef  mov     [rsp+6C8h+var_438], r15
0x1800353f7  lea     rcx, [rsp+6C8h+var_438]
0x1800353ff  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180035404  lea     rcx, [rsp+6C8h+var_438]
0x18003540c  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180035411  nop
0x180035412  lea     rax, ??_7GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories::`vftable'
0x180035419  mov     [rsp+6C8h+var_2E8], rax
0x180035421  lea     rcx, [rsp+6C8h+var_2E8]
0x180035429  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003542e  lea     rcx, [rsp+6C8h+var_2E8]
0x180035436  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003543b  nop
0x18003543c  lea     rcx, [rsp+6C8h+var_620]
0x180035444  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035449  nop
0x18003544a  lea     rcx, [rsp+6C8h+lpFileName]
0x180035452  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035457  mov     rcx, [rsp+6C8h+hObject]; hObject
0x18003545f  lea     rax, [rcx-1]
0x180035463  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035467  ja      short loc_180035475
0x180035469  call    cs:__imp_CloseHandle
0x180035470  nop     dword ptr [rax+rax+00h]
0x180035475  mov     rcx, [rsp+6C8h+var_5D8]; hObject
0x18003547d  lea     rax, [rcx-1]
0x180035481  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035485  ja      short loc_180035493
0x180035487  call    cs:__imp_CloseHandle
0x18003548e  nop     dword ptr [rax+rax+00h]
0x180035493  mov     r8, rsi; Size
0x180035496  xor     edx, edx; Val
0x180035498  lea     rcx, [rsp+6C8h+var_198]; void *
0x1800354a0  call    memset_0
0x1800354a5  nop
0x1800354a6  lea     rdx, aGraphdriverCre_0; "GraphDriver_CreateVirtualDisk"
0x1800354ad  lea     rcx, [rsp+6C8h+var_198]
0x1800354b5  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800354ba  lea     rbx, ??_7GraphDriver_CreateVirtualDisk@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::`vftable'
0x1800354c1  mov     [rsp+6C8h+var_198], rbx
0x1800354c9  lea     rdx, [rsp+6C8h+var_588]; struct ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders *
0x1800354d1  lea     rcx, [rsp+6C8h+var_198]; this
0x1800354d9  call    ?StartActivity@GraphDriver_CreateVirtualDisk@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXAEBVGraphDriver_CreateBaseImageVHDWithFolders@234@@Z; ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::StartActivity(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders const &)
0x1800354de  nop
0x1800354df  lea     rdx, [rsp+6C8h+Src]
0x1800354e7  cmp     [rsp+6C8h+var_628], 7
0x1800354f0  cmova   rdx, [rsp+6C8h+Src]; unsigned __int16 *
0x1800354f9  mov     r8d, r14d; unsigned int
0x1800354fc  mov     rcx, r12; Path
0x1800354ff  call    ?CreateVhdFromSource@@YAXPEBG0K@Z; CreateVhdFromSource(ushort const *,ushort const *,ulong)
0x180035504  lea     rcx, [rsp+6C8h+var_198]
0x18003550c  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180035511  lea     rcx, [rsp+6C8h+var_588]
0x180035519  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$00$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003551e  nop
0x18003551f  mov     [rsp+6C8h+var_198], rbx
0x180035527  lea     rcx, [rsp+6C8h+var_198]
0x18003552f  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180035534  lea     rcx, [rsp+6C8h+var_198]
0x18003553c  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180035541  nop
0x180035542  cmp     qword ptr [rdi+18h], 7
0x180035547  jbe     short loc_18003554C
0x180035549  mov     rdi, [rdi]
0x18003554c  mov     rcx, rdi; this
0x18003554f  call    ?TryDeleteFile@Helpers@OsImageUtilities@@YAXPEBG@Z; OsImageUtilities::Helpers::TryDeleteFile(ushort const *)
0x180035554  nop
0x180035555  lea     rcx, [rsp+6C8h+Src]
0x18003555d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035562  nop
0x180035563  lea     rax, ??_7GraphDriver_CreateBaseImageVHDWithFolders@TraceProvider@Diagnostics@ComputeLegacy@@6B@; const ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders::`vftable'
0x18003556a  mov     [rsp+6C8h+var_588], rax
0x180035572  lea     rcx, [rsp+6C8h+var_588]
0x18003557a  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$00$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003557f  lea     rcx, [rsp+6C8h+var_588]
0x180035587  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003558c  xor     eax, eax
0x18003558e  jmp     short loc_180035594
0x180035590  mov     eax, [rsp+6C8h+BytesReturned]
0x180035594  mov     rcx, [rsp+6C8h+var_48]
0x18003559c  xor     rcx, rsp; StackCookie
0x18003559f  call    __security_check_cookie
0x1800355a4  add     rsp, 690h
0x1800355ab  pop     r15
0x1800355ad  pop     r14
  ... truncated ...
```
