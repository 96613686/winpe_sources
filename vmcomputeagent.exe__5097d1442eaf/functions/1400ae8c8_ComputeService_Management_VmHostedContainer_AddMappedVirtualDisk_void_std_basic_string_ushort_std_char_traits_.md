# ComputeService::Management::VmHostedContainer::AddMappedVirtualDisk(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Schema::VirtualMachines::Resources::Storage::MappedVirtualDisk const &,bool,int)

- ea: `0x1400ae8c8`
- end: `0x1400aebdc`
- name: `?AddMappedVirtualDisk@VmHostedContainer@Management@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUMappedVirtualDisk@Storage@Resources@VirtualMachines@Schema@@_NH@Z`
- size: `788`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400a13a8`
- `0x1400ae7f8`

## callees

- `0x140005360`
- `0x140008760`
- `0x140009f8c`
- `0x14000ddac`
- `0x14002dd18`
- `0x1400341ac`
- `0x140041140`
- `0x140041ff0`
- `0x1400438dc`
- `0x1400ae8c8`
- `0x1400aebe4`
- `0x1400aed48`
- `0x1400af510`
- `0x1400d90a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ae9e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400ae9e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400aea7e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400aeacf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400aea7e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400aeacf`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x1400aea9c`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x1400aea9c`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetVolumeMountPointW` at `0x1400aeb30`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetVolumeMountPointW` at `0x1400aeb30`

## string_xrefs

- `0x1400aeba3`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerstorage.cpp`
- `0x1400aebb8`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerstorage.cpp`
- `0x1400aebca`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerstorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ComputeService::Management::VmHostedContainer::AddMappedVirtualDisk(
        __int64 a1,
        __int64 a2,
        ComputeService::Storage **a3,
        const char *a4,
        int a5)
{
  ComputeService::Storage **v5; // rsi
  ComputeService::Storage **v6; // rdi
  int v7; // r14d
  int v8; // eax
  __int64 DiskVolumePath; // rax
  const WCHAR *p_lpszVolumeName; // rdx
  char *v11; // r8
  ComputeService::Storage *v12; // rcx
  bool IsDriveLetter; // r14
  const WCHAR *v14; // rdx
  const WCHAR *v15; // rcx
  const WCHAR *v16; // rcx
  const unsigned __int16 *v17; // rdx
  const WCHAR *v18; // rcx
  const WCHAR *v19; // rcx
  const unsigned __int16 *v20; // rdx
  const WCHAR *v21; // rcx
  unsigned int DirectoryW; // eax
  const WCHAR *v23; // rdx
  const WCHAR *v24; // rcx
  const char *v25; // r9
  const char *v26; // [rsp+20h] [rbp-C8h]
  __int64 v27; // [rsp+28h] [rbp-C0h]
  unsigned int v28; // [rsp+20h] [rbp-C8h]
  unsigned __int16 v29[2]; // [rsp+40h] [rbp-A8h] BYREF
  int v30; // [rsp+44h] [rbp-A4h]
  HANDLE hObject; // [rsp+48h] [rbp-A0h] BYREF
  ComputeService::Storage **v32; // [rsp+50h] [rbp-98h]
  __int64 v33; // [rsp+60h] [rbp-88h]
  __int64 v34; // [rsp+68h] [rbp-80h]
  LPCWSTR pszPath[3]; // [rsp+70h] [rbp-78h] BYREF
  unsigned __int64 v36; // [rsp+88h] [rbp-60h]
  __int128 lpszVolumeName; // [rsp+90h] [rbp-58h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  char v40; // [rsp+108h] [rbp+20h]

  v40 = (char)a4;
  v5 = a3;
  v32 = a3;
  v34 = a1;
  v33 = a2;
  v6 = a3;
  v7 = 0;
  v30 = 0;
  lpszVolumeName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpszVolumeName) = 0;
  v8 = a5;
  while ( 2 )
  {
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
        a4);
    try
    {
      LOBYTE(v29[0]) = *((_BYTE *)v6 + 32);
      hObject = 0;
      ComputeService::Management::VmHostedContainer::OpenDiskByLun(&hObject, LOBYTE(v29[0]));
      DiskVolumePath = GetDiskVolumePath(pszPath, hObject);
      std::wstring::operator=(&lpszVolumeName, DiskVolumePath);
      std::wstring::~wstring(pszPath);
      p_lpszVolumeName = (const WCHAR *)&lpszVolumeName;
      if ( si128.m128i_i64[1] > 7uLL )
        p_lpszVolumeName = (const WCHAR *)lpszVolumeName;
      CommonUtilities::CombineFilePath(pszPath, p_lpszVolumeName, L".\\");
      v30 = v7 | 3;
      std::wstring::operator=(&lpszVolumeName, pszPath);
      std::wstring::~wstring(pszPath);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
    }
    catch ( ... )
    {
      if ( a5 <= 0 )
      {
        LODWORD(v26) = LOBYTE(v29[0]);
        wil::details::in1diag3::Throw_CaughtExceptionMsg(
          retaddr,
          (void *)0x179,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
          "Lun [%d]",
          v26);
      }
      LODWORD(v27) = a5 - 1;
      LODWORD(v26) = LOBYTE(v29[0]);
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x172,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
        "Lun [%d] Retries remaining: [%d]",
        v26,
        v27);
      Sleep(0x1F4u);
      v8 = a5 - 1;
      a5 = v8;
      v5 = v32;
      v6 = v32;
      if ( v8 <= 0 )
        break;
      v7 = v30;
      continue;
    }
    break;
  }
  if ( v40 )
  {
    if ( (unsigned __int64)v6[3] <= 7 )
      v12 = (ComputeService::Storage *)v6;
    else
      v12 = *v5;
    IsDriveLetter = ComputeService::Storage::IsDriveLetter(v12, v29, v11);
    if ( (unsigned __int64)v6[3] <= 7 )
      v14 = (const WCHAR *)v6;
    else
      v14 = (const WCHAR *)*v5;
    CommonUtilities::CombineFilePath(pszPath, v14, L".\\");
    if ( !IsDriveLetter )
    {
      if ( *((_BYTE *)v6 + 33) )
      {
        v15 = (const WCHAR *)pszPath;
        if ( v36 > 7 )
          v15 = pszPath[0];
        if ( PathFileExistsW(v15) )
        {
          v16 = (const WCHAR *)pszPath;
          if ( v36 > 7 )
            v16 = pszPath[0];
          DeleteVolumeMountPointW(v16);
          v18 = (const WCHAR *)pszPath;
          if ( v36 > 7 )
            v18 = pszPath[0];
          CommonUtilities::DeleteDirectory(v18, v17);
        }
      }
      v19 = (const WCHAR *)pszPath;
      if ( v36 > 7 )
        v19 = pszPath[0];
      if ( !PathFileExistsW(v19) )
      {
        v21 = (const WCHAR *)pszPath;
        if ( v36 > 7 )
          v21 = pszPath[0];
        DirectoryW = Vml::CreateDirectoryW(v21, v20);
        if ( DirectoryW )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x19F,
            (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
            (const char *)DirectoryW,
            v28);
      }
    }
    v23 = (const WCHAR *)&lpszVolumeName;
    if ( si128.m128i_i64[1] > 7uLL )
      v23 = (const WCHAR *)lpszVolumeName;
    v24 = (const WCHAR *)pszPath;
    if ( v36 > 7 )
      v24 = pszPath[0];
    if ( !SetVolumeMountPointW(v24, v23) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
        v25);
    std::wstring::~wstring(pszPath);
  }
  else
  {
    ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(v34, v33, &lpszVolumeName, v6, 0, 0);
  }
  std::wstring::~wstring(&lpszVolumeName);
}

```

## disassembly

```asm
0x1400ae8c8  mov     r11, rsp
0x1400ae8cb  mov     [r11+20h], r9b
0x1400ae8cf  push    rbx
0x1400ae8d0  push    rsi
0x1400ae8d1  push    rdi
0x1400ae8d2  push    r14
0x1400ae8d4  sub     rsp, 0C8h
0x1400ae8db  mov     rax, cs:__security_cookie
0x1400ae8e2  xor     rax, rsp
0x1400ae8e5  mov     [rsp+0E8h+var_38], rax
0x1400ae8ed  mov     rsi, r8
0x1400ae8f0  mov     [rsp+0E8h+var_98], r8
0x1400ae8f5  mov     [rsp+0E8h+var_80], rcx
0x1400ae8fa  mov     [rsp+0E8h+var_88], rdx
0x1400ae8ff  mov     rdi, r8
0x1400ae902  xor     ebx, ebx
0x1400ae904  mov     r14d, ebx
0x1400ae907  mov     [rsp+0E8h+var_A4], ebx
0x1400ae90b  xorps   xmm0, xmm0
0x1400ae90e  movups  xmmword ptr [r11-58h], xmm0
0x1400ae913  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400ae91b  movdqu  xmmword ptr [r11-48h], xmm1
0x1400ae921  mov     [r11-58h], bx
0x1400ae926  mov     eax, [rsp+0E8h+arg_20]
0x1400ae92d  mov     rcx, [rsp+0E8h]; this
0x1400ae935  shr     eax, 1Fh
0x1400ae938  test    al, al
0x1400ae93a  jnz     loc_1400AEBA3
0x1400ae940  movzx   edx, byte ptr [rdi+20h]
0x1400ae944  mov     byte ptr [rsp+0E8h+var_A8], dl
0x1400ae948  mov     [rsp+0E8h+hObject], rbx
0x1400ae94d  lea     rcx, [rsp+0E8h+hObject]
0x1400ae952  call    ?OpenDiskByLun@VmHostedContainer@Management@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@I@Z; ComputeService::Management::VmHostedContainer::OpenDiskByLun(uint)
0x1400ae957  nop
0x1400ae958  mov     rdx, [rsp+0E8h+hObject]
0x1400ae95d  lea     rcx, [rsp+0E8h+pszPath]
0x1400ae962  call    ?GetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetDiskVolumePath(void *)
0x1400ae967  mov     rdx, rax
0x1400ae96a  lea     rcx, [rsp+0E8h+lpszVolumeName]
0x1400ae972  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400ae977  lea     rcx, [rsp+0E8h+pszPath]; void *
0x1400ae97c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae981  lea     rdx, [rsp+0E8h+lpszVolumeName]
0x1400ae989  cmp     [rsp+0E8h+var_40], 7
0x1400ae992  cmova   rdx, qword ptr [rsp+0E8h+lpszVolumeName]; pszPathIn
0x1400ae99b  lea     r8, pszMore; ".\\"
0x1400ae9a2  lea     rcx, [rsp+0E8h+pszPath]; Src
0x1400ae9a7  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x1400ae9ac  or      r14d, 3
0x1400ae9b0  mov     [rsp+0E8h+var_A4], r14d
0x1400ae9b5  lea     rdx, [rsp+0E8h+pszPath]
0x1400ae9ba  lea     rcx, [rsp+0E8h+lpszVolumeName]
0x1400ae9c2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400ae9c7  lea     rcx, [rsp+0E8h+pszPath]; void *
0x1400ae9cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ae9d1  nop
0x1400ae9d2  mov     rcx, [rsp+0E8h+hObject]; hObject
0x1400ae9d7  lea     rax, [rcx-1]
0x1400ae9db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400ae9df  ja      short loc_1400AE9E8
0x1400ae9e1  call    cs:__imp_CloseHandle
0x1400ae9e7  nop
0x1400ae9e8  jmp     short loc_1400AEA12
0x1400ae9ea  mov     eax, [rsp+0E8h+arg_20]
0x1400ae9f1  dec     eax
0x1400ae9f3  mov     [rsp+0E8h+arg_20], eax
0x1400ae9fa  xor     ebx, ebx
0x1400ae9fc  mov     rsi, [rsp+0E8h+var_98]
0x1400aea01  mov     rdi, rsi
0x1400aea04  test    eax, eax
0x1400aea06  jle     short loc_1400AEA12
0x1400aea08  mov     r14d, [rsp+0E8h+var_A4]
0x1400aea0d  jmp     loc_1400AE92D
0x1400aea12  cmp     [rsp+0E8h+arg_18], bl
0x1400aea19  jz      loc_1400AEB52
0x1400aea1f  cmp     qword ptr [rdi+18h], 7
0x1400aea24  jbe     short loc_1400AEA2B
0x1400aea26  mov     rcx, [rsi]
0x1400aea29  jmp     short loc_1400AEA2E
0x1400aea2b  mov     rcx, rdi; this
0x1400aea2e  lea     rdx, [rsp+0E8h+var_A8]; unsigned __int16 *
0x1400aea33  call    ?IsDriveLetter@Storage@ComputeService@@YA_NPEBGPEAD@Z; ComputeService::Storage::IsDriveLetter(ushort const *,char *)
0x1400aea38  mov     r14b, al
0x1400aea3b  cmp     qword ptr [rdi+18h], 7
0x1400aea40  jbe     short loc_1400AEA47
0x1400aea42  mov     rdx, [rsi]
0x1400aea45  jmp     short loc_1400AEA4A
0x1400aea47  mov     rdx, rdi; pszPathIn
0x1400aea4a  lea     r8, pszMore; ".\\"
0x1400aea51  lea     rcx, [rsp+0E8h+pszPath]; Src
0x1400aea56  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x1400aea5b  nop
0x1400aea5c  test    r14b, r14b
0x1400aea5f  jnz     loc_1400AEB02
0x1400aea65  cmp     [rdi+21h], bl
0x1400aea68  jz      short loc_1400AEABB
0x1400aea6a  lea     rcx, [rsp+0E8h+pszPath]
0x1400aea6f  cmp     [rsp+0E8h+var_60], 7
0x1400aea78  cmova   rcx, [rsp+0E8h+pszPath]; pszPath
0x1400aea7e  call    cs:__imp_PathFileExistsW
0x1400aea84  test    eax, eax
0x1400aea86  jz      short loc_1400AEABB
0x1400aea88  lea     rcx, [rsp+0E8h+pszPath]
0x1400aea8d  cmp     [rsp+0E8h+var_60], 7
0x1400aea96  cmova   rcx, [rsp+0E8h+pszPath]; lpszVolumeMountPoint
0x1400aea9c  call    cs:__imp_DeleteVolumeMountPointW
0x1400aeaa2  lea     rcx, [rsp+0E8h+pszPath]
0x1400aeaa7  cmp     [rsp+0E8h+var_60], 7
0x1400aeab0  cmova   rcx, [rsp+0E8h+pszPath]; this
0x1400aeab6  call    ?DeleteDirectory@CommonUtilities@@YAJPEBG@Z; CommonUtilities::DeleteDirectory(ushort const *)
0x1400aeabb  lea     rcx, [rsp+0E8h+pszPath]
0x1400aeac0  cmp     [rsp+0E8h+var_60], 7
0x1400aeac9  cmova   rcx, [rsp+0E8h+pszPath]; pszPath
0x1400aeacf  call    cs:__imp_PathFileExistsW
0x1400aead5  test    eax, eax
0x1400aead7  jnz     short loc_1400AEB02
0x1400aead9  lea     rcx, [rsp+0E8h+pszPath]
0x1400aeade  cmp     [rsp+0E8h+var_60], 7
0x1400aeae7  cmova   rcx, [rsp+0E8h+pszPath]; lpPathName
0x1400aeaed  call    ?CreateDirectoryW@Vml@@YAKPEBG@Z; Vml::CreateDirectoryW(ushort const *)
0x1400aeaf2  mov     rcx, [rsp+0E8h]; this
0x1400aeafa  test    eax, eax
0x1400aeafc  jnz     loc_1400AEBB5
0x1400aeb02  lea     rdx, [rsp+0E8h+lpszVolumeName]
0x1400aeb0a  cmp     [rsp+0E8h+var_40], 7
0x1400aeb13  cmova   rdx, qword ptr [rsp+0E8h+lpszVolumeName]; lpszVolumeName
0x1400aeb1c  lea     rcx, [rsp+0E8h+pszPath]
0x1400aeb21  cmp     [rsp+0E8h+var_60], 7
0x1400aeb2a  cmova   rcx, [rsp+0E8h+pszPath]; lpszVolumeMountPoint
0x1400aeb30  call    cs:__imp_SetVolumeMountPointW
0x1400aeb36  mov     rcx, [rsp+0E8h]; this
0x1400aeb3e  test    eax, eax
0x1400aeb40  jz      loc_1400AEBCA
0x1400aeb46  lea     rcx, [rsp+0E8h+pszPath]; void *
0x1400aeb4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400aeb50  jmp     short loc_1400AEB79
0x1400aeb52  mov     [rsp+0E8h+var_B0], bl
0x1400aeb56  mov     [rsp+0E8h+var_C0], bl
0x1400aeb5a  mov     [rsp+0E8h+var_C8], bl
0x1400aeb5e  mov     r9, rdi
0x1400aeb61  lea     r8, [rsp+0E8h+lpszVolumeName]
0x1400aeb69  mov     rdx, [rsp+0E8h+var_88]
0x1400aeb6e  mov     rcx, [rsp+0E8h+var_80]
0x1400aeb73  call    ?AddMappedDirectoryFromPaths@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11_N222@Z; ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(void *,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,bool,bool)
0x1400aeb78  nop
0x1400aeb79  lea     rcx, [rsp+0E8h+lpszVolumeName]; void *
0x1400aeb81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400aeb86  mov     rcx, [rsp+0E8h+var_38]
0x1400aeb8e  xor     rcx, rsp; StackCookie
0x1400aeb91  call    __security_check_cookie
0x1400aeb96  add     rsp, 0C8h
0x1400aeb9d  pop     r14
0x1400aeb9f  pop     rdi
0x1400aeba0  pop     rsi
0x1400aeba1  pop     rbx
0x1400aeba2  retn
0x1400aeba3  lea     r8, aOnecoreVmCompu_53; "onecore\\vm\\compute\\management\\orche"...
0x1400aebaa  mov     edx, 15Ch; void *
0x1400aebaf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400aebb5  mov     r9d, eax; char *
0x1400aebb8  lea     r8, aOnecoreVmCompu_53; "onecore\\vm\\compute\\management\\orche"...
0x1400aebbf  mov     edx, 19Fh; void *
0x1400aebc4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400aebca  lea     r8, aOnecoreVmCompu_53; "onecore\\vm\\compute\\management\\orche"...
0x1400aebd1  mov     edx, 1A2h; void *
0x1400aebd6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
