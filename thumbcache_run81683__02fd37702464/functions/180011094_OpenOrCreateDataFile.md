# _OpenOrCreateDataFile

- ea: `0x180011094`
- end: `0x1800112c1`
- name: `_OpenOrCreateDataFile`
- size: `557`
- prototype: `__int64 __fastcall(PCWSTR pszPath)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e6a0`
- `0x180010e00`
- `0x180010ee8`
- `0x180028fb8`

## callees

- `0x180003320`
- `0x1800034f8`
- `0x18000bfd8`
- `0x180011094`
- `0x18002b290`
- `0x1800346ec`
- `0x180035830`
- `0x18004097c`
- `0x1800433f8`
- `0x180045af0`
- `0x180046fac`
- `0x180047240`
- `0x18004751c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001111e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001111e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800110f6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800110f6`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180011221`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180011221`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180011202`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180011202`
- `ntdll!NtSetInformationFile` at `0x180011187`
- `ntdll!NtSetInformationFile` at `0x180011187`
- `ntdll!RtlNtStatusToDosError` at `0x1800111dd`
- `ntdll!RtlNtStatusToDosError` at `0x1800111dd`

## string_xrefs

- `0x180011233`: `onecoreuap\shell\ext\thumbnailcache\common\util.cpp`
- `0x180011294`: `onecoreuap\shell\ext\thumbnailcache\common\util.cpp`
- `0x1800112ad`: `onecoreuap\shell\ext\thumbnailcache\common\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OpenOrCreateDataFile(PCWSTR pszPath, int a2, _QWORD *a3)
{
  HANDLE v6; // rdi
  signed int LastError; // eax
  unsigned int v8; // ebx
  NTSTATUS v9; // eax
  ULONG v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  const char *v14; // r9
  int LockingApplication; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-49h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-49h]
  HANDLE FileHandle; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int16 *FileW; // [rsp+50h] [rbp-19h] BYREF
  int FileInformation; // [rsp+58h] [rbp-11h] BYREF
  _OWORD v22[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v23; // [rsp+80h] [rbp+17h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a3 = -1;
  FileW = (unsigned __int16 *)CreateFileW(pszPath, 0xC0000000, 7u, 0, 4 - (unsigned int)(a2 != 0), 0x10000000u, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
    &FileHandle,
    &FileW);
  v6 = FileHandle;
  if ( (((unsigned __int64)FileHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 == -2147024891 )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&FileW);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &FileW,
        0);
      LockingApplication = FindLockingApplication(pszPath, &FileW);
      if ( LockingApplication < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x88,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\util.cpp",
          (const char *)(unsigned int)LockingApplication,
          dwCreationDisposition);
      v19 = FileW;
      ThumbnailCacheTelemetry::LockingApplicationOnDataFile<unsigned short *>(&v19);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&FileW);
    }
    else if ( (v8 & 0x80000000) == 0 )
    {
      goto LABEL_6;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\util.cpp",
      (const char *)v8,
      dwCreationDisposition);
    goto LABEL_9;
  }
LABEL_6:
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  if ( a2
    || !GetFileInformationByHandleEx(v6, FileBasicInfo, v22, 0x28u)
    || (LODWORD(v23) = v23 | 0x2000, SetFileInformationByHandle(v6, FileBasicInfo, v22, 0x28u)) )
  {
    IoStatusBlock = 0;
    FileInformation = 2;
    v9 = NtSetInformationFile(v6, &IoStatusBlock, &FileInformation, 4u, FileRenameInformation|0x40);
    if ( (int)(v9 + 0x80000000) >= 0 && v9 != -1073740626 )
    {
      v11 = RtlNtStatusToDosError(v9);
      wil::details::in1diag3::Log_Win32(retaddr, v12, v13, (const char *)v11, dwCreationDispositiona);
    }
    FileHandle = (HANDLE)-1LL;
    *a3 = v6;
    v8 = 0;
  }
  else
  {
    v8 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x92,
           (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\util.cpp",
           v14);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
  return v8;
}

```

## disassembly

```asm
0x180011094  mov     [rsp-8+arg_8], rbx
0x180011099  push    rbp
0x18001109a  push    rsi
0x18001109b  push    rdi
0x18001109c  push    r14
0x18001109e  push    r15
0x1800110a0  lea     rbp, [rsp-37h]
0x1800110a5  sub     rsp, 0A0h
0x1800110ac  mov     rax, cs:__security_cookie
0x1800110b3  xor     rax, rsp
0x1800110b6  mov     [rbp+57h+var_28], rax
0x1800110ba  mov     r15, r8
0x1800110bd  mov     esi, edx
0x1800110bf  mov     r14, rcx
0x1800110c2  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x1800110c9  mov     eax, edx
0x1800110cb  neg     eax
0x1800110cd  sbb     ecx, ecx
0x1800110cf  add     ecx, 4
0x1800110d2  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1800110db  mov     [rsp+0C0h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x1800110e3  mov     [rsp+0C0h+dwCreationDisposition], ecx; int
0x1800110e7  xor     r9d, r9d; lpSecurityAttributes
0x1800110ea  mov     edx, 0C0000000h; dwDesiredAccess
0x1800110ef  lea     r8d, [r9+7]; dwShareMode
0x1800110f3  mov     rcx, r14; lpFileName
0x1800110f6  call    cs:__imp_CreateFileW
0x1800110fc  mov     [rbp+57h+var_70], rax
0x180011100  lea     rdx, [rbp+57h+var_70]
0x180011104  lea     rcx, [rbp+57h+FileHandle]
0x180011108  call    ??$?0AEAPEAG$$V@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@AEAPEAG@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(ushort * &)
0x18001110d  nop
0x18001110e  mov     rdi, [rbp+57h+FileHandle]
0x180011112  lea     rax, [rdi+1]
0x180011116  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001111c  jnz     short loc_180011147
0x18001111e  call    cs:__imp_GetLastError
0x180011124  mov     ebx, eax
0x180011126  test    eax, eax
0x180011128  jle     short loc_180011133
0x18001112a  movzx   ebx, ax
0x18001112d  or      ebx, 80070000h
0x180011133  cmp     ebx, 80070005h
0x180011139  jz      loc_180011249
0x18001113f  test    ebx, ebx
0x180011141  js      loc_18001128D
0x180011147  xorps   xmm0, xmm0
0x18001114a  xor     eax, eax
0x18001114c  movups  [rbp+57h+var_60], xmm0
0x180011150  movups  [rbp+57h+var_50], xmm0
0x180011154  mov     [rbp+57h+var_40], rax
0x180011158  test    esi, esi
0x18001115a  jz      loc_1800111F1
0x180011160  xorps   xmm0, xmm0
0x180011163  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180011167  mov     [rbp+57h+FileInformation], 2
0x18001116e  mov     [rsp+0C0h+dwCreationDisposition], 4Ah ; 'J'; unsigned int
0x180011176  mov     r9d, 4; Length
0x18001117c  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180011180  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180011184  mov     rcx, rdi; FileHandle
0x180011187  call    cs:__imp_NtSetInformationFile
0x18001118d  mov     edx, 80000000h
0x180011192  lea     ecx, [rax+rdx]
0x180011195  test    edx, ecx
0x180011197  jz      short loc_1800111D4
0x180011199  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800111a1  mov     [r15], rdi
0x1800111a4  xor     ebx, ebx
0x1800111a6  lea     rcx, [rbp+57h+FileHandle]
0x1800111aa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800111af  mov     eax, ebx
0x1800111b1  mov     rcx, [rbp+57h+var_28]
0x1800111b5  xor     rcx, rsp; StackCookie
0x1800111b8  call    __security_check_cookie
0x1800111bd  mov     rbx, [rsp+0C0h+arg_8]
0x1800111c5  add     rsp, 0A0h
0x1800111cc  pop     r15
0x1800111ce  pop     r14
0x1800111d0  pop     rdi
0x1800111d1  pop     rsi
0x1800111d2  pop     rbp
0x1800111d3  retn
0x1800111d4  cmp     eax, 0C00004AEh
0x1800111d9  jz      short loc_180011199
0x1800111db  mov     ecx, eax; Status
0x1800111dd  call    cs:__imp_RtlNtStatusToDosError
0x1800111e3  mov     r9d, eax; char *
0x1800111e6  mov     rcx, [rbp+5Fh]; this
0x1800111ea  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800111ef  jmp     short loc_180011199
0x1800111f1  mov     ebx, 28h ; '('
0x1800111f6  mov     r9d, ebx; dwBufferSize
0x1800111f9  lea     r8, [rbp+57h+var_60]; lpFileInformation
0x1800111fd  xor     edx, edx; FileInformationClass
0x1800111ff  mov     rcx, rdi; hFile
0x180011202  call    cs:__imp_GetFileInformationByHandleEx
0x180011208  test    eax, eax
0x18001120a  jz      loc_180011160
0x180011210  bts     dword ptr [rbp+57h+var_40], 0Dh
0x180011215  mov     r9d, ebx; dwBufferSize
0x180011218  lea     r8, [rbp+57h+var_60]; lpFileInformation
0x18001121c  xor     edx, edx; FileInformationClass
0x18001121e  mov     rcx, rdi; hFile
0x180011221  call    cs:__imp_SetFileInformationByHandle
0x180011227  test    eax, eax
0x180011229  jnz     loc_180011160
0x18001122f  mov     rcx, [rbp+5Fh]; this
0x180011233  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001123a  lea     edx, [rbx+6Ah]; void *
0x18001123d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011242  mov     ebx, eax
0x180011244  jmp     loc_1800111A6
0x180011249  lea     rcx, [rbp+57h+var_70]
0x18001124d  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180011252  nop
0x180011253  xor     edx, edx
0x180011255  lea     rcx, [rbp+57h+var_70]
0x180011259  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001125e  lea     rdx, [rbp+57h+var_70]; unsigned __int16 **
0x180011262  mov     rcx, r14; pszPath
0x180011265  call    ?FindLockingApplication@@YAJPEBGPEAPEAG@Z; FindLockingApplication(ushort const *,ushort * *)
0x18001126a  mov     rcx, [rbp+5Fh]; this
0x18001126e  test    eax, eax
0x180011270  js      short loc_1800112AA
0x180011272  mov     rax, [rbp+57h+var_70]
0x180011276  mov     [rbp+57h+var_78], rax
0x18001127a  lea     rcx, [rbp+57h+var_78]
0x18001127e  call    ??$LockingApplicationOnDataFile@PEAG@ThumbnailCacheTelemetry@@SAX$$QEAPEAG@Z; ThumbnailCacheTelemetry::LockingApplicationOnDataFile<ushort *>(ushort * &&)
0x180011283  nop
0x180011284  lea     rcx, [rbp+57h+var_70]
0x180011288  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001128d  mov     rcx, [rbp+5Fh]; this
0x180011291  mov     r9d, ebx; char *
0x180011294  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001129b  mov     edx, 8Ch; void *
0x1800112a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112a5  jmp     loc_1800111A6
0x1800112aa  mov     r9d, eax; char *
0x1800112ad  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800112b4  mov     edx, 88h; void *
0x1800112b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800112be  jmp     short loc_180011272
```
