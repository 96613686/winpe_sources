# GetVhdVolumePath(void *)

- ea: `0x18005d3d8`
- end: `0x18005d65e`
- name: `?GetVhdVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `646`
- prototype: `__int64 __fastcall(void *Src, HANDLE VirtualDiskHandle)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180030348`
- `0x180030fb0`
- `0x180035d90`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18000ec20`
- `0x180016058`
- `0x180017344`
- `0x180018bd4`
- `0x180022d10`
- `0x18005d37c`
- `0x18005d3d8`
- `0x180060490`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d60f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d60f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005d5ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005d5ce`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18005d4dd`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18005d4dd`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18005d437`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18005d437`

## string_xrefs

- `0x18005d550`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x18005d64c`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
WCHAR *__fastcall GetVhdVolumePath(WCHAR *Src, HANDLE VirtualDiskHandle)
{
  WCHAR *v4; // r8
  DWORD VirtualDiskPhysicalPath; // eax
  PWSTR *v6; // rax
  __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  PWSTR *v9; // rcx
  WCHAR *v10; // rdx
  const WCHAR *v11; // rcx
  WCHAR *v12; // rax
  __int64 v13; // rdx
  WCHAR *v14; // rcx
  unsigned __int64 v15; // rdx
  PWSTR *v16; // rcx
  const WCHAR *v17; // rcx
  char *FileW; // rbx
  __int64 DiskVolumePath; // rax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-49h]
  _BYTE v22[32]; // [rsp+58h] [rbp-11h] BYREF
  PWSTR DiskPath[2]; // [rsp+78h] [rbp+Fh] BYREF
  unsigned __int64 v24; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 v25; // [rsp+90h] [rbp+27h]
  ULONG DiskPathSizeInBytes; // [rsp+98h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  std::wstring::wstring(DiskPath, 260);
  DiskPathSizeInBytes = 520;
  v4 = (WCHAR *)DiskPath;
  if ( v25 > 7 )
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
  if ( v25 > 7 )
    v6 = (PWSTR *)DiskPath[0];
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)v6 + v7) );
  std::wstring::resize(DiskPath);
  v8 = v24;
  v9 = DiskPath;
  if ( v24 >= v25 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(DiskPath);
  }
  else
  {
    ++v24;
    if ( v25 > 7 )
      v9 = (PWSTR *)DiskPath[0];
    *(_DWORD *)((char *)v9 + 2 * v8) = 92;
  }
  std::wstring::wstring(Src, 260);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v10 = Src;
  else
    v10 = *(WCHAR **)Src;
  v11 = (const WCHAR *)DiskPath;
  if ( v25 > 7 )
    v11 = DiskPath[0];
  if ( GetVolumeNameForVolumeMountPointW(v11, v10, 0x104u) )
  {
    if ( *((_QWORD *)Src + 3) <= 7u )
      v12 = Src;
    else
      v12 = *(WCHAR **)Src;
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    std::wstring::resize(Src);
    if ( *((_QWORD *)Src + 3) <= 7u )
      wil::details::in1diag3::FailFast_IfMsg(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)(Src[*((_QWORD *)Src + 2) - 1] != 92),
        (void *)"%ls",
        (const char *)Src);
    else
      wil::details::in1diag3::FailFast_IfMsg(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)(*(_WORD *)(*(_QWORD *)Src + 2LL * *((_QWORD *)Src + 2) - 2) != 92),
        (void *)"%ls",
        *(const char **)Src);
    --*((_QWORD *)Src + 2);
    if ( *((_QWORD *)Src + 3) <= 7u )
      v14 = Src;
    else
      v14 = *(WCHAR **)Src;
    v14[*((_QWORD *)Src + 2)] = 0;
  }
  else
  {
    v15 = --v24;
    v16 = DiskPath;
    if ( v25 > 7 )
      v16 = (PWSTR *)DiskPath[0];
    *((_WORD *)v16 + v15) = 0;
    v17 = (const WCHAR *)DiskPath;
    if ( v25 > 7 )
      v17 = DiskPath[0];
    FileW = (char *)CreateFileW(v17, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
    DiskVolumePath = GetDiskVolumePath(v22, FileW);
    std::wstring::operator=(Src, DiskVolumePath);
    std::wstring::~wstring(v22);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
  }
  std::wstring::~wstring(DiskPath);
  return Src;
}

```

## disassembly

```asm
0x18005d3d8  mov     [rsp-8+arg_10], rbx
0x18005d3dd  push    rbp
0x18005d3de  push    rdi
0x18005d3df  push    r14
0x18005d3e1  lea     rbp, [rsp-47h]
0x18005d3e6  sub     rsp, 0B0h
0x18005d3ed  mov     rax, cs:__security_cookie
0x18005d3f4  xor     rax, rsp
0x18005d3f7  mov     [rbp+57h+var_20], rax
0x18005d3fb  mov     rbx, rdx
0x18005d3fe  mov     rdi, rcx
0x18005d401  mov     [rbp+57h+var_78], rcx
0x18005d405  xor     r14d, r14d
0x18005d408  mov     [rbp+57h+var_80], r14d
0x18005d40c  mov     edx, 104h
0x18005d411  lea     rcx, [rbp+57h+DiskPath]
0x18005d415  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005d41a  nop
0x18005d41b  mov     [rbp+57h+DiskPathSizeInBytes], 208h
0x18005d422  lea     r8, [rbp+57h+DiskPath]
0x18005d426  cmp     [rbp+57h+var_30], 7
0x18005d42b  cmova   r8, [rbp+57h+DiskPath]; DiskPath
0x18005d430  lea     rdx, [rbp+57h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x18005d434  mov     rcx, rbx; VirtualDiskHandle
0x18005d437  call    cs:__imp_GetVirtualDiskPhysicalPath
0x18005d43e  nop     dword ptr [rax+rax+00h]
0x18005d443  mov     rcx, [rbp+5Fh]; this
0x18005d447  test    eax, eax
0x18005d449  jnz     loc_18005D649
0x18005d44f  lea     rax, [rbp+57h+DiskPath]
0x18005d453  cmp     [rbp+57h+var_30], 7
0x18005d458  cmova   rax, [rbp+57h+DiskPath]
0x18005d45d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005d461  inc     rdx
0x18005d464  cmp     [rax+rdx*2], r14w
0x18005d469  jnz     short loc_18005D461
0x18005d46b  lea     rcx, [rbp+57h+DiskPath]; Src
0x18005d46f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18005d474  mov     rdx, [rbp+57h+var_38]
0x18005d478  lea     rcx, [rbp+57h+DiskPath]; Src
0x18005d47c  mov     ebx, 5Ch ; '\'
0x18005d481  cmp     rdx, [rbp+57h+var_30]
0x18005d485  jnb     short loc_18005D49E
0x18005d487  lea     rax, [rdx+1]
0x18005d48b  mov     [rbp+57h+var_38], rax
0x18005d48f  cmp     [rbp+57h+var_30], 7
0x18005d494  cmova   rcx, [rbp+57h+DiskPath]
0x18005d499  mov     [rcx+rdx*2], ebx
0x18005d49c  jmp     short loc_18005D4A6
0x18005d49e  mov     r9d, ebx
0x18005d4a1  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18005d4a6  mov     edx, 104h
0x18005d4ab  mov     rcx, rdi
0x18005d4ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005d4b3  mov     [rbp+57h+var_80], 1
0x18005d4ba  cmp     qword ptr [rdi+18h], 7
0x18005d4bf  jbe     short loc_18005D4C6
0x18005d4c1  mov     rdx, [rdi]
0x18005d4c4  jmp     short loc_18005D4C9
0x18005d4c6  mov     rdx, rdi; lpszVolumeName
0x18005d4c9  lea     rcx, [rbp+57h+DiskPath]
0x18005d4cd  cmp     [rbp+57h+var_30], 7
0x18005d4d2  cmova   rcx, [rbp+57h+DiskPath]; lpszVolumeMountPoint
0x18005d4d7  mov     r8d, 104h; cchBufferLength
0x18005d4dd  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18005d4e4  nop     dword ptr [rax+rax+00h]
0x18005d4e9  test    eax, eax
0x18005d4eb  jz      loc_18005D582
0x18005d4f1  cmp     qword ptr [rdi+18h], 7
0x18005d4f6  jbe     short loc_18005D4FD
0x18005d4f8  mov     rax, [rdi]
0x18005d4fb  jmp     short loc_18005D500
0x18005d4fd  mov     rax, rdi
0x18005d500  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005d504  inc     rdx
0x18005d507  cmp     [rax+rdx*2], r14w
0x18005d50c  jnz     short loc_18005D504
0x18005d50e  mov     rcx, rdi; Src
0x18005d511  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18005d516  cmp     qword ptr [rdi+18h], 7
0x18005d51b  jbe     short loc_18005D525
0x18005d51d  mov     rdx, [rdi]
0x18005d520  mov     rcx, rdx
0x18005d523  jmp     short loc_18005D52B
0x18005d525  mov     rdx, rdi
0x18005d528  mov     rcx, rdi
0x18005d52b  mov     rax, [rdi+10h]
0x18005d52f  cmp     [rcx+rax*2-2], bx
0x18005d534  setnz   al
0x18005d537  mov     rcx, [rbp+5Fh]; this
0x18005d53b  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rdx; char *
0x18005d540  lea     rdx, aLs; "%ls"
0x18005d547  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdx; void *
0x18005d54c  movzx   r9d, al; char *
0x18005d550  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d557  mov     edx, 1C7h; void *
0x18005d55c  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x18005d561  dec     qword ptr [rdi+10h]
0x18005d565  mov     rdx, [rdi+10h]
0x18005d569  cmp     qword ptr [rdi+18h], 7
0x18005d56e  jbe     short loc_18005D575
0x18005d570  mov     rcx, [rdi]
0x18005d573  jmp     short loc_18005D578
0x18005d575  mov     rcx, rdi
0x18005d578  mov     [rcx+rdx*2], r14w
0x18005d57d  jmp     loc_18005D61C
0x18005d582  mov     rdx, [rbp+57h+var_38]
0x18005d586  dec     rdx
0x18005d589  mov     [rbp+57h+var_38], rdx
0x18005d58d  lea     rcx, [rbp+57h+DiskPath]
0x18005d591  cmp     [rbp+57h+var_30], 7
0x18005d596  cmova   rcx, [rbp+57h+DiskPath]
0x18005d59b  mov     [rcx+rdx*2], r14w
0x18005d5a0  lea     rcx, [rbp+57h+DiskPath]
0x18005d5a4  cmp     [rbp+57h+var_30], 7
0x18005d5a9  cmova   rcx, [rbp+57h+DiskPath]; lpFileName
0x18005d5ae  mov     [rsp+0C0h+hTemplateFile], r14; hTemplateFile
0x18005d5b3  mov     [rsp+0C0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18005d5bb  mov     r8d, 3; dwShareMode
0x18005d5c1  mov     [rsp+0C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18005d5c6  xor     r9d, r9d; lpSecurityAttributes
0x18005d5c9  mov     edx, 0C0000000h; dwDesiredAccess
0x18005d5ce  call    cs:__imp_CreateFileW
0x18005d5d5  nop     dword ptr [rax+rax+00h]
0x18005d5da  mov     rbx, rax
0x18005d5dd  mov     [rbp+57h+var_70], rax
0x18005d5e1  mov     rdx, rax
0x18005d5e4  lea     rcx, [rbp+57h+var_68]
0x18005d5e8  call    ?GetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetDiskVolumePath(void *)
0x18005d5ed  mov     rdx, rax
0x18005d5f0  mov     rcx, rdi
0x18005d5f3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005d5f8  lea     rcx, [rbp+57h+var_68]
0x18005d5fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d601  nop
0x18005d602  lea     rcx, [rbx-1]
0x18005d606  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005d60a  ja      short loc_18005D61C
0x18005d60c  mov     rcx, rbx; hObject
0x18005d60f  call    cs:__imp_CloseHandle
0x18005d616  nop     dword ptr [rax+rax+00h]
0x18005d61b  nop
0x18005d61c  lea     rcx, [rbp+57h+DiskPath]
0x18005d620  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d625  mov     rax, rdi
0x18005d628  mov     rcx, [rbp+57h+var_20]
0x18005d62c  xor     rcx, rsp; StackCookie
0x18005d62f  call    __security_check_cookie
0x18005d634  mov     rbx, [rsp+0C0h+arg_10]
0x18005d63c  add     rsp, 0B0h
0x18005d643  pop     r14
0x18005d645  pop     rdi
0x18005d646  pop     rbp
0x18005d647  retn
0x18005d649  mov     r9d, eax; char *
0x18005d64c  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d653  mov     edx, 1BDh; void *
0x18005d658  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
