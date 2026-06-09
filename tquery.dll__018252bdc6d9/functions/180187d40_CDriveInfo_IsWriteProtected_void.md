# CDriveInfo::IsWriteProtected(void)

- ea: `0x180187d40`
- end: `0x180187f28`
- name: `?IsWriteProtected@CDriveInfo@@QEAAHXZ`
- size: `488`
- prototype: `__int64 __fastcall(CDriveInfo *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180074fac`
- `0x180075d8c`
- `0x180187d40`
- `0x180188d90`
- `0x18019b924`
- `0x18019c834`
- `0x1801b83cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180187e2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180187ee0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180187e2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180187ee0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180187efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180187efa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180187e1b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180187e1b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180187eda`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180187eda`

## string_xrefs

- `0x180187e40`: `[Index] CDriveInfo::IsWriteProtected[%wc]: dwError is %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDriveInfo::IsWriteProtected(CDriveInfo *this)
{
  char *v2; // rcx
  int v3; // eax
  HANDLE FileW; // rdi
  DWORD LastError; // esi
  BOOL v6; // ecx
  int dwCreationDisposition; // [rsp+20h] [rbp-2C8h]
  DWORD BytesReturned[2]; // [rsp+40h] [rbp-2A8h] BYREF
  unsigned __int64 v10; // [rsp+48h] [rbp-2A0h] BYREF
  WCHAR FileName[56]; // [rsp+50h] [rbp-298h] BYREF
  wchar_t v12[264]; // [rsp+C0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  if ( !*((_DWORD *)this + 8) )
  {
    *((_DWORD *)this + 8) = 1;
    *(_QWORD *)BytesReturned = 0;
    v2 = (char *)this + 120;
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(char **)v2;
    if ( (int)GetVolumeInformationFromPath((const wchar_t *)v2, &v10, v12, (unsigned __int64 *)BytesReturned, FileName) < 0 )
    {
      v3 = StringCchCopyW(FileName, 0x32u, L"\\\\.\\a:");
      if ( v3 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\driveinf.cxx",
          (const char *)(unsigned int)v3,
          dwCreationDisposition);
      FileName[4] = *((_WORD *)this + 6);
    }
    FileW = CreateFileW(FileName, 0x80u, 3u, 0, 3u, 0, 0);
    v10 = (unsigned __int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      SearchIndexerDebug::Information(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\driveinf.cxx",
        (const wchar_t *)0xC5,
        (unsigned int)L"[Index] CDriveInfo::IsWriteProtected[%wc]: dwError is %d\n",
        (const wchar_t *)*((unsigned __int16 *)this + 6));
      if ( LastError != 5 && LastError != 19 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xC8,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\driveinf.cxx",
          (const char *)LastError,
          LastError);
      v6 = 0;
    }
    else
    {
      SearchIndexerDebug::Information(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\qlib2\\driveinf.cxx",
        (const wchar_t *)0xCE,
        (unsigned int)L"[Index] Get volume handle succeeded for volume %wc\n",
        (const wchar_t *)*((unsigned __int16 *)this + 6));
      BytesReturned[0] = 0;
      DeviceIoControl(FileW, 0x70024u, 0, 0, 0, 0, BytesReturned, 0);
      v6 = GetLastError() == 19;
    }
    *((_DWORD *)this + 7) = v6;
    if ( FileW != (HANDLE)-1LL )
      CloseHandle(FileW);
  }
  return *((unsigned int *)this + 7);
}

```

## disassembly

```asm
0x180187d40  mov     [rsp+arg_8], rbx
0x180187d45  mov     [rsp+arg_10], rsi
0x180187d4a  push    rdi
0x180187d4b  sub     rsp, 2E0h
0x180187d52  mov     rax, cs:__security_cookie
0x180187d59  xor     rax, rsp
0x180187d5c  mov     [rsp+2E8h+var_18], rax
0x180187d64  mov     rbx, rcx
0x180187d67  cmp     dword ptr [rcx+20h], 0
0x180187d6b  jnz     loc_180187F00
0x180187d71  mov     dword ptr [rcx+20h], 1
0x180187d78  mov     qword ptr [rsp+2E8h+BytesReturned], 0
0x180187d81  add     rcx, 78h ; 'x'
0x180187d85  cmp     qword ptr [rcx+18h], 7
0x180187d8a  jbe     short loc_180187D8F
0x180187d8c  mov     rcx, [rcx]; wchar_t *
0x180187d8f  lea     rax, [rsp+2E8h+FileName]
0x180187d94  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax; int
0x180187d99  lea     r9, [rsp+2E8h+BytesReturned]; unsigned __int64 *
0x180187d9e  lea     r8, [rsp+2E8h+var_228]; wchar_t *
0x180187da6  lea     rdx, [rsp+2E8h+var_2A0]; unsigned __int64 *
0x180187dab  call    ?GetVolumeInformationFromPath@@YAJPEB_WPEA_KPEA_W12@Z; GetVolumeInformationFromPath(wchar_t const *,unsigned __int64 *,wchar_t *,unsigned __int64 *,wchar_t *)
0x180187db0  test    eax, eax
0x180187db2  jns     short loc_180187DF3
0x180187db4  lea     r8, aA_1; "\\\\.\\a:"
0x180187dbb  mov     edx, 32h ; '2'; unsigned __int64
0x180187dc0  lea     rcx, [rsp+2E8h+FileName]; wchar_t *
0x180187dc5  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180187dca  mov     rcx, [rsp+2E8h]; this
0x180187dd2  test    eax, eax
0x180187dd4  jns     short loc_180187DEA
0x180187dd6  mov     r9d, eax; char *
0x180187dd9  lea     r8, aOnecoreuapBase_137; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180187de0  mov     edx, 0B7h; void *
0x180187de5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180187dea  movzx   eax, word ptr [rbx+0Ch]
0x180187dee  mov     [rsp+2E8h+var_290], ax
0x180187df3  mov     [rsp+2E8h+hTemplateFile], 0; hTemplateFile
0x180187dfc  mov     [rsp+2E8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180187e04  mov     r8d, 3; dwShareMode
0x180187e0a  mov     [rsp+2E8h+dwCreationDisposition], r8d; dwCreationDisposition
0x180187e0f  xor     r9d, r9d; lpSecurityAttributes
0x180187e12  lea     edx, [r8+7Dh]; dwDesiredAccess
0x180187e16  lea     rcx, [rsp+2E8h+FileName]; lpFileName
0x180187e1b  call    cs:__imp_CreateFileW
0x180187e21  mov     rdi, rax
0x180187e24  mov     [rsp+2E8h+var_2A0], rax
0x180187e29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180187e2d  jnz     short loc_180187E83
0x180187e2f  call    cs:__imp_GetLastError
0x180187e35  mov     esi, eax
0x180187e37  movzx   r9d, word ptr [rbx+0Ch]; wchar_t *
0x180187e3c  mov     [rsp+2E8h+dwCreationDisposition], eax; unsigned int
0x180187e40  lea     r8, aIndexCdriveinf; "[Index] CDriveInfo::IsWriteProtected[%w"...
0x180187e47  mov     edx, 0C5h; wchar_t *
0x180187e4c  lea     rcx, aOnecoreuapBase_241; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180187e53  call    ?Information@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Information(wchar_t const *,uint,wchar_t const *,...)
0x180187e58  cmp     esi, 5
0x180187e5b  jz      short loc_180187E7F
0x180187e5d  cmp     esi, 13h
0x180187e60  jz      short loc_180187E7F
0x180187e62  mov     rcx, [rsp+2E8h]; this
0x180187e6a  mov     r9d, esi; char *
0x180187e6d  lea     r8, aOnecoreuapBase_137; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180187e74  mov     edx, 0C8h; void *
0x180187e79  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180187e7f  xor     ecx, ecx
0x180187e81  jmp     short loc_180187EEE
0x180187e83  movzx   r9d, word ptr [rbx+0Ch]; wchar_t *
0x180187e88  lea     r8, aIndexGetVolume; "[Index] Get volume handle succeeded for"...
0x180187e8f  mov     edx, 0CEh; wchar_t *
0x180187e94  lea     rcx, aOnecoreuapBase_241; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180187e9b  call    ?Information@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Information(wchar_t const *,uint,wchar_t const *,...)
0x180187ea0  mov     [rsp+2E8h+BytesReturned], 0
0x180187ea8  mov     [rsp+2E8h+lpOverlapped], 0; lpOverlapped
0x180187eb1  lea     rax, [rsp+2E8h+BytesReturned]
0x180187eb6  mov     [rsp+2E8h+hTemplateFile], rax; lpBytesReturned
0x180187ebb  mov     [rsp+2E8h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180187ec3  mov     qword ptr [rsp+2E8h+dwCreationDisposition], 0; lpOutBuffer
0x180187ecc  xor     r9d, r9d; nInBufferSize
0x180187ecf  xor     r8d, r8d; lpInBuffer
0x180187ed2  mov     edx, 70024h; dwIoControlCode
0x180187ed7  mov     rcx, rdi; hDevice
0x180187eda  call    cs:__imp_DeviceIoControl
0x180187ee0  call    cs:__imp_GetLastError
0x180187ee6  xor     ecx, ecx
0x180187ee8  cmp     eax, 13h
0x180187eeb  setz    cl
0x180187eee  mov     [rbx+1Ch], ecx
0x180187ef1  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180187ef5  jz      short loc_180187F00
0x180187ef7  mov     rcx, rdi; hObject
0x180187efa  call    cs:__imp_CloseHandle
0x180187f00  mov     eax, [rbx+1Ch]
0x180187f03  mov     rcx, [rsp+2E8h+var_18]
0x180187f0b  xor     rcx, rsp; StackCookie
0x180187f0e  call    __security_check_cookie
0x180187f13  lea     r11, [rsp+2E8h+var_8]
0x180187f1b  mov     rbx, [r11+18h]
0x180187f1f  mov     rsi, [r11+20h]
0x180187f23  mov     rsp, r11
0x180187f26  pop     rdi
0x180187f27  retn
```
