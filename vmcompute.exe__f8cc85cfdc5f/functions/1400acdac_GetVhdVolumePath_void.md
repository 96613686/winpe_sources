# GetVhdVolumePath(void *)

- ea: `0x1400acdac`
- end: `0x1400ad001`
- name: `?GetVhdVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `597`
- prototype: `__int64 __fastcall(LPWSTR lpszVolumeName, HANDLE VirtualDiskHandle)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x1400ab050`
- `0x1400d526c`

## callees

- `0x140017040`
- `0x140024030`
- `0x140031a20`
- `0x140042e70`
- `0x140044974`
- `0x1400acdac`
- `0x1400ad008`
- `0x1400c4154`
- `0x140124b64`
- `0x1401332f0`
- `0x140233510`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400acf95`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400acf95`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400acea7`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400acea7`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1400ace0e`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1400ace0e`

## string_xrefs

- `0x1400ace25`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x1400acf19`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
WCHAR *__fastcall GetVhdVolumePath(WCHAR *lpszVolumeName, HANDLE VirtualDiskHandle)
{
  WCHAR *v4; // r8
  DWORD VirtualDiskPhysicalPath; // eax
  PWSTR *v6; // rax
  __int64 v7; // rdx
  WCHAR *v8; // rdx
  const WCHAR *v9; // rcx
  WCHAR *v10; // rax
  __int64 v11; // rdx
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  PWSTR *v14; // rcx
  const WCHAR *v15; // rcx
  __int64 DiskVolumePath; // rax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  _QWORD v19[2]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v20[32]; // [rsp+58h] [rbp-11h] BYREF
  PWSTR DiskPath[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v22; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 v23; // [rsp+90h] [rbp+27h]
  ULONG DiskPathSizeInBytes; // [rsp+98h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v19[1] = lpszVolumeName;
  std::wstring::wstring(DiskPath, 260);
  DiskPathSizeInBytes = 520;
  v4 = (WCHAR *)DiskPath;
  if ( v23 > 7 )
    v4 = DiskPath[0];
  VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, v4);
  if ( VirtualDiskPhysicalPath )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)VirtualDiskPhysicalPath,
      dwCreationDisposition);
  v6 = DiskPath;
  if ( v23 > 7 )
    v6 = (PWSTR *)DiskPath[0];
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)v6 + v7) );
  std::wstring::resize(DiskPath);
  std::wstring::push_back(DiskPath, 92);
  std::wstring::wstring(lpszVolumeName, 260);
  if ( *((_QWORD *)lpszVolumeName + 3) <= 7u )
    v8 = lpszVolumeName;
  else
    v8 = *(WCHAR **)lpszVolumeName;
  v9 = (const WCHAR *)DiskPath;
  if ( v23 > 7 )
    v9 = DiskPath[0];
  if ( GetVolumeNameForVolumeMountPointW(v9, v8, 0x104u) )
  {
    if ( *((_QWORD *)lpszVolumeName + 3) <= 7u )
      v10 = lpszVolumeName;
    else
      v10 = *(WCHAR **)lpszVolumeName;
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    std::wstring::resize(lpszVolumeName);
    if ( *((_QWORD *)lpszVolumeName + 3) <= 7u )
      wil::details::in1diag3::FailFast_IfMsg(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)(lpszVolumeName[*((_QWORD *)lpszVolumeName + 2) - 1] != 92),
        (bool)"%ls",
        (const char *)lpszVolumeName);
    else
      wil::details::in1diag3::FailFast_IfMsg(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)(*(_WORD *)(*(_QWORD *)lpszVolumeName + 2LL * *((_QWORD *)lpszVolumeName + 2) - 2) != 92),
        (bool)"%ls",
        *(const char **)lpszVolumeName);
    --*((_QWORD *)lpszVolumeName + 2);
    if ( *((_QWORD *)lpszVolumeName + 3) <= 7u )
      v12 = lpszVolumeName;
    else
      v12 = *(WCHAR **)lpszVolumeName;
    v12[*((_QWORD *)lpszVolumeName + 2)] = 0;
  }
  else
  {
    v13 = --v22;
    v14 = DiskPath;
    if ( v23 > 7 )
      v14 = (PWSTR *)DiskPath[0];
    *((_WORD *)v14 + v13) = 0;
    v15 = (const WCHAR *)DiskPath;
    if ( v23 > 7 )
      v15 = DiskPath[0];
    v19[0] = CreateFileW(v15, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
    DiskVolumePath = GetDiskVolumePath(v20);
    std::wstring::operator=(lpszVolumeName, DiskVolumePath);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v20);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v19);
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)DiskPath);
  return lpszVolumeName;
}

```

## disassembly

```asm
0x1400acdac  mov     [rsp-8+arg_10], rbx
0x1400acdb1  mov     [rsp-8+arg_18], rsi
0x1400acdb6  push    rbp
0x1400acdb7  push    rdi
0x1400acdb8  push    r15
0x1400acdba  lea     rbp, [rsp-47h]
0x1400acdbf  sub     rsp, 0B0h
0x1400acdc6  mov     rax, cs:__security_cookie
0x1400acdcd  xor     rax, rsp
0x1400acdd0  mov     [rbp+57h+var_20], rax
0x1400acdd4  mov     rbx, rdx
0x1400acdd7  mov     rdi, rcx
0x1400acdda  mov     [rbp+57h+var_70], rcx
0x1400acdde  xor     esi, esi
0x1400acde0  mov     [rbp+57h+var_80], esi
0x1400acde3  mov     edx, 104h
0x1400acde8  lea     rcx, [rbp+57h+DiskPath]
0x1400acdec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1400acdf1  nop
0x1400acdf2  mov     [rbp+57h+DiskPathSizeInBytes], 208h
0x1400acdf9  lea     r8, [rbp+57h+DiskPath]
0x1400acdfd  cmp     [rbp+57h+var_30], 7
0x1400ace02  cmova   r8, [rbp+57h+DiskPath]; DiskPath
0x1400ace07  lea     rdx, [rbp+57h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1400ace0b  mov     rcx, rbx; VirtualDiskHandle
0x1400ace0e  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1400ace15  nop     dword ptr [rax+rax+00h]
0x1400ace1a  mov     rcx, [rbp+5Fh]; this
0x1400ace1e  test    eax, eax
0x1400ace20  jz      short loc_1400ACE37
0x1400ace22  mov     r9d, eax; char *
0x1400ace25  lea     r8, aOnecoreVmCompu_100; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400ace2c  mov     edx, 1BDh; void *
0x1400ace31  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ace37  lea     rax, [rbp+57h+DiskPath]
0x1400ace3b  cmp     [rbp+57h+var_30], 7
0x1400ace40  cmova   rax, [rbp+57h+DiskPath]
0x1400ace45  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400ace49  mov     rdx, rbx
0x1400ace4c  inc     rdx
0x1400ace4f  cmp     [rax+rdx*2], si
0x1400ace53  jnz     short loc_1400ACE4C
0x1400ace55  lea     rcx, [rbp+57h+DiskPath]
0x1400ace59  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1400ace5e  mov     r15d, 5Ch ; '\'
0x1400ace64  mov     edx, r15d
0x1400ace67  lea     rcx, [rbp+57h+DiskPath]
0x1400ace6b  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1400ace70  mov     edx, 104h
0x1400ace75  mov     rcx, rdi
0x1400ace78  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1400ace7d  mov     [rbp+57h+var_80], 1
0x1400ace84  cmp     qword ptr [rdi+18h], 7
0x1400ace89  jbe     short loc_1400ACE90
0x1400ace8b  mov     rdx, [rdi]
0x1400ace8e  jmp     short loc_1400ACE93
0x1400ace90  mov     rdx, rdi; lpszVolumeName
0x1400ace93  lea     rcx, [rbp+57h+DiskPath]
0x1400ace97  cmp     [rbp+57h+var_30], 7
0x1400ace9c  cmova   rcx, [rbp+57h+DiskPath]; lpszVolumeMountPoint
0x1400acea1  mov     r8d, 104h; cchBufferLength
0x1400acea7  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1400aceae  nop     dword ptr [rax+rax+00h]
0x1400aceb3  test    eax, eax
0x1400aceb5  jz      loc_1400ACF4A
0x1400acebb  cmp     qword ptr [rdi+18h], 7
0x1400acec0  jbe     short loc_1400ACEC7
0x1400acec2  mov     rax, [rdi]
0x1400acec5  jmp     short loc_1400ACECA
0x1400acec7  mov     rax, rdi
0x1400aceca  mov     rdx, rbx
0x1400acecd  inc     rdx
0x1400aced0  cmp     [rax+rdx*2], si
0x1400aced4  jnz     short loc_1400ACECD
0x1400aced6  mov     rcx, rdi
0x1400aced9  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1400acede  cmp     qword ptr [rdi+18h], 7
0x1400acee3  jbe     short loc_1400ACEED
0x1400acee5  mov     rdx, [rdi]
0x1400acee8  mov     rcx, rdx
0x1400aceeb  jmp     short loc_1400ACEF3
0x1400aceed  mov     rdx, rdi
0x1400acef0  mov     rcx, rdi
0x1400acef3  mov     rax, [rdi+10h]
0x1400acef7  cmp     [rcx+rax*2-2], r15w
0x1400acefd  setnz   al
0x1400acf00  mov     rcx, [rbp+5Fh]; this
0x1400acf04  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rdx; char *
0x1400acf09  lea     rdx, aLs; "%ls"
0x1400acf10  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdx; bool
0x1400acf15  movzx   r9d, al; char *
0x1400acf19  lea     r8, aOnecoreVmCompu_100; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400acf20  mov     edx, 1C7h; void *
0x1400acf25  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x1400acf2a  add     [rdi+10h], rbx
0x1400acf2e  mov     rdx, [rdi+10h]
0x1400acf32  cmp     qword ptr [rdi+18h], 7
0x1400acf37  jbe     short loc_1400ACF3E
0x1400acf39  mov     rcx, [rdi]
0x1400acf3c  jmp     short loc_1400ACF41
0x1400acf3e  mov     rcx, rdi
0x1400acf41  mov     [rcx+rdx*2], si
0x1400acf45  jmp     loc_1400ACFD0
0x1400acf4a  mov     rdx, [rbp+57h+var_38]
0x1400acf4e  dec     rdx
0x1400acf51  mov     [rbp+57h+var_38], rdx
0x1400acf55  lea     rcx, [rbp+57h+DiskPath]
0x1400acf59  cmp     [rbp+57h+var_30], 7
0x1400acf5e  cmova   rcx, [rbp+57h+DiskPath]
0x1400acf63  mov     [rcx+rdx*2], si
0x1400acf67  lea     rcx, [rbp+57h+DiskPath]
0x1400acf6b  cmp     [rbp+57h+var_30], 7
0x1400acf70  cmova   rcx, [rbp+57h+DiskPath]; lpFileName
0x1400acf75  mov     [rsp+0C0h+hTemplateFile], rsi; hTemplateFile
0x1400acf7a  mov     [rsp+0C0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x1400acf82  mov     r8d, 3; dwShareMode
0x1400acf88  mov     [rsp+0C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400acf8d  xor     r9d, r9d; lpSecurityAttributes
0x1400acf90  mov     edx, 0C0000000h; dwDesiredAccess
0x1400acf95  call    cs:__imp_CreateFileW
0x1400acf9c  nop     dword ptr [rax+rax+00h]
0x1400acfa1  mov     [rbp+57h+var_78], rax
0x1400acfa5  mov     rdx, rax
0x1400acfa8  lea     rcx, [rbp+57h+var_68]; void *
0x1400acfac  call    ?GetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetDiskVolumePath(void *)
0x1400acfb1  mov     rdx, rax
0x1400acfb4  mov     rcx, rdi
0x1400acfb7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400acfbc  lea     rcx, [rbp+57h+var_68]; this
0x1400acfc0  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400acfc5  nop
0x1400acfc6  lea     rcx, [rbp+57h+var_78]; void *
0x1400acfca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400acfcf  nop
0x1400acfd0  lea     rcx, [rbp+57h+DiskPath]; this
0x1400acfd4  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400acfd9  mov     rax, rdi
0x1400acfdc  mov     rcx, [rbp+57h+var_20]
0x1400acfe0  xor     rcx, rsp; StackCookie
0x1400acfe3  call    __security_check_cookie
0x1400acfe8  lea     r11, [rsp+0C0h+var_10]
0x1400acff0  mov     rbx, [r11+30h]
0x1400acff4  mov     rsi, [r11+38h]
0x1400acff8  mov     rsp, r11
0x1400acffb  pop     r15
0x1400acffd  pop     rdi
0x1400acffe  pop     rbp
0x1400acfff  retn
```
