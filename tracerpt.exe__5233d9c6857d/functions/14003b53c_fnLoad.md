# fnLoad

- ea: `0x14003b53c`
- end: `0x14003b758`
- name: `fnLoad`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14003a0cc`

## callees

- `0x140002bf0`
- `0x140038850`
- `0x14003b53c`
- `0x14003b760`
- `0x140040130`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x14003b5c8`
- `msvcrt!_wsplitpath_s` at `0x14003b5c8`
- `msvcrt!fprintf` at `0x14003b57f`
- `msvcrt!fprintf` at `0x14003b65a`
- `msvcrt!fprintf` at `0x14003b70a`
- `msvcrt!fprintf` at `0x14003b57f`
- `msvcrt!fprintf` at `0x14003b65a`
- `msvcrt!fprintf` at `0x14003b70a`
- `msvcrt!_wcsicmp` at `0x14003b5f9`
- `msvcrt!_wcsicmp` at `0x14003b5f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b6e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b6e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003b689`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003b689`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14003b697`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14003b697`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b725`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b725`
- `dbghelp!SymLoadModuleExW` at `0x14003b6cb`
- `dbghelp!SymLoadModuleExW` at `0x14003b6cb`

## pseudocode

```c
__int64 __fastcall fnLoad(__int64 a1)
{
  FILE *v1; // rax
  const wchar_t *v3; // rsi
  int v4; // ebx
  DWORD64 v5; // rdi
  DWORD v6; // ebp
  __int64 v7; // r8
  FILE *v8; // rax
  HANDLE FileW; // rbx
  DWORD FileSize; // eax
  DWORD64 Module; // rax
  DWORD LastError; // ebx
  FILE *v13; // rax
  WCHAR ModuleName[264]; // [rsp+50h] [rbp-448h] BYREF
  wchar_t String1[264]; // [rsp+260h] [rbp-238h] BYREF

  if ( !*(_QWORD *)(a1 + 8) )
  {
    v1 = _acrt_iob_func(2u);
    fprintf(v1, "WPPFMT : error : load <modname> - you must specify a module to load\n");
    return 0;
  }
  v3 = *(const wchar_t **)a1;
  v4 = 0;
  _wsplitpath_s(*(const wchar_t **)a1, 0, 0, 0, 0, ModuleName, 0x104u, String1, 0x104u);
  if ( String1[0] )
  {
    v6 = 0;
    if ( _wcsicmp(String1, L".pdb") )
    {
      v5 = gDefaultBase;
    }
    else
    {
      v5 = gDefaultBaseForVirtualMods;
      v4 = 1;
    }
  }
  else
  {
    v5 = gDefaultBaseForVirtualMods;
    v6 = 1;
  }
  fnUnload();
  v7 = -1;
  do
    ++v7;
  while ( ModuleName[v7] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &gModName,
                           ModuleName,
                           v7) )
  {
    v8 = _acrt_iob_func(2u);
    fprintf(v8, "WPPFMT : error : out of memory loading %ls\n", v3);
    return 0;
  }
  if ( v4 )
  {
    FileSize = 0x1000000;
    FileW = 0;
  }
  else
  {
    FileW = CreateFileW(v3, 0x80000000, 0, 0, 3u, 0, 0);
    FileSize = GetFileSize(FileW, 0);
  }
  Module = SymLoadModuleExW(gSymHandle, FileW, v3, ModuleName, v5, FileSize, 0, v6);
  if ( !Module )
  {
    off_1400609C8 = gModName;
    *(_WORD *)gModName = 0;
    LastError = GetLastError();
    v13 = _acrt_iob_func(2u);
    fprintf(v13, "WPPFMT : error : 0x%x loading %ls.\n", LastError, v3);
    return 0;
  }
  gBase = Module;
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x14003b53c  mov     [rsp+arg_8], rbx
0x14003b541  mov     [rsp+arg_10], rbp
0x14003b546  push    rsi
0x14003b547  push    rdi
0x14003b548  push    r14
0x14003b54a  sub     rsp, 480h
0x14003b551  mov     rax, cs:__security_cookie
0x14003b558  xor     rax, rsp
0x14003b55b  mov     [rsp+498h+var_28], rax
0x14003b563  xor     r14d, r14d
0x14003b566  cmp     [rcx+8], r14
0x14003b56a  jnz     short loc_14003B58C
0x14003b56c  lea     ecx, [r14+2]; Ix
0x14003b570  call    __acrt_iob_func
0x14003b575  mov     rcx, rax; Stream
0x14003b578  lea     rdx, aWppfmtErrorLoa; "WPPFMT : error : load <modname> - you m"...
0x14003b57f  call    cs:__imp_fprintf
0x14003b585  xor     eax, eax
0x14003b587  jmp     loc_14003B730
0x14003b58c  mov     rsi, [rcx]
0x14003b58f  lea     rax, [rsp+498h+String1]
0x14003b597  mov     ecx, 104h
0x14003b59c  xor     r9d, r9d; Dir
0x14003b59f  mov     [rsp+498h+ExtCount], rcx; ExtCount
0x14003b5a4  xor     r8d, r8d; DriveCount
0x14003b5a7  mov     [rsp+498h+Ext], rax; Ext
0x14003b5ac  xor     edx, edx; Drive
0x14003b5ae  mov     [rsp+498h+FilenameCount], rcx; FilenameCount
0x14003b5b3  lea     rax, [rsp+498h+ModuleName]
0x14003b5b8  mov     [rsp+498h+Filename], rax; Filename
0x14003b5bd  mov     rcx, rsi; FullPath
0x14003b5c0  mov     [rsp+498h+DirCount], r14; DirCount
0x14003b5c5  mov     ebx, r14d
0x14003b5c8  call    cs:__imp__wsplitpath_s
0x14003b5ce  cmp     [rsp+498h+String1], r14w
0x14003b5d7  jnz     short loc_14003B5E7
0x14003b5d9  mov     rdi, cs:?gDefaultBaseForVirtualMods@@3_KA; unsigned __int64 gDefaultBaseForVirtualMods
0x14003b5e0  mov     ebp, 1
0x14003b5e5  jmp     short loc_14003B616
0x14003b5e7  lea     rdx, aPdb; ".pdb"
0x14003b5ee  mov     ebp, r14d
0x14003b5f1  lea     rcx, [rsp+498h+String1]; String1
0x14003b5f9  call    cs:__imp__wcsicmp
0x14003b5ff  test    eax, eax
0x14003b601  jnz     short loc_14003B60F
0x14003b603  mov     rdi, cs:?gDefaultBaseForVirtualMods@@3_KA; unsigned __int64 gDefaultBaseForVirtualMods
0x14003b60a  lea     ebx, [rax+1]
0x14003b60d  jmp     short loc_14003B616
0x14003b60f  mov     rdi, cs:?gDefaultBase@@3_KA; unsigned __int64 gDefaultBase
0x14003b616  call    fnUnload
0x14003b61b  lea     rax, [rsp+498h+ModuleName]
0x14003b620  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003b624  inc     r8
0x14003b627  cmp     [rax+r8*2], r14w
0x14003b62c  jnz     short loc_14003B624
0x14003b62e  lea     rdx, [rsp+498h+ModuleName]
0x14003b633  lea     rcx, ?gModName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> gModName
0x14003b63a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14003b63f  test    al, al
0x14003b641  jnz     short loc_14003B665
0x14003b643  mov     ecx, 2; Ix
0x14003b648  call    __acrt_iob_func
0x14003b64d  mov     r8, rsi
0x14003b650  lea     rdx, aWppfmtErrorOut; "WPPFMT : error : out of memory loading "...
0x14003b657  mov     rcx, rax; Stream
0x14003b65a  call    cs:__imp_fprintf
0x14003b660  jmp     loc_14003B585
0x14003b665  test    ebx, ebx
0x14003b667  jnz     short loc_14003B69F
0x14003b669  mov     [rsp+498h+FilenameCount], r14; hTemplateFile
0x14003b66e  xor     r9d, r9d; lpSecurityAttributes
0x14003b671  mov     dword ptr [rsp+498h+Filename], r14d; dwFlagsAndAttributes
0x14003b676  xor     r8d, r8d; dwShareMode
0x14003b679  mov     edx, 80000000h; dwDesiredAccess
0x14003b67e  mov     dword ptr [rsp+498h+DirCount], 3; dwCreationDisposition
0x14003b686  mov     rcx, rsi; lpFileName
0x14003b689  call    cs:__imp_CreateFileW
0x14003b68f  mov     rcx, rax; hFile
0x14003b692  xor     edx, edx; lpFileSizeHigh
0x14003b694  mov     rbx, rax
0x14003b697  call    cs:__imp_GetFileSize
0x14003b69d  jmp     short loc_14003B6A7
0x14003b69f  mov     eax, 1000000h
0x14003b6a4  mov     rbx, r14
0x14003b6a7  mov     rcx, cs:?gSymHandle@@3PEAXEA; hProcess
0x14003b6ae  lea     r9, [rsp+498h+ModuleName]; ModuleName
0x14003b6b3  mov     dword ptr [rsp+498h+Ext], ebp; Flags
0x14003b6b7  mov     r8, rsi; ImageName
0x14003b6ba  mov     [rsp+498h+FilenameCount], r14; Data
0x14003b6bf  mov     rdx, rbx; hFile
0x14003b6c2  mov     dword ptr [rsp+498h+Filename], eax; DllSize
0x14003b6c6  mov     [rsp+498h+DirCount], rdi; BaseOfDll
0x14003b6cb  call    cs:__imp_SymLoadModuleExW
0x14003b6d1  test    rax, rax
0x14003b6d4  jnz     short loc_14003B715
0x14003b6d6  mov     rcx, cs:?gModName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> gModName
0x14003b6dd  mov     cs:off_1400609C8, rcx
0x14003b6e4  mov     [rcx], r14w
0x14003b6e8  call    cs:__imp_GetLastError
0x14003b6ee  mov     ecx, 2; Ix
0x14003b6f3  mov     ebx, eax
0x14003b6f5  call    __acrt_iob_func
0x14003b6fa  mov     r9, rsi
0x14003b6fd  lea     rdx, aWppfmtError0xX_4; "WPPFMT : error : 0x%x loading %ls.\n"
0x14003b704  mov     r8d, ebx
0x14003b707  mov     rcx, rax; Stream
0x14003b70a  call    cs:__imp_fprintf
0x14003b710  jmp     loc_14003B585
0x14003b715  mov     cs:?gBase@@3_KA, rax; unsigned __int64 gBase
0x14003b71c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14003b720  jz      short loc_14003B72B
0x14003b722  mov     rcx, rbx; hObject
0x14003b725  call    cs:__imp_CloseHandle
0x14003b72b  mov     eax, 1
0x14003b730  mov     rcx, [rsp+498h+var_28]
0x14003b738  xor     rcx, rsp; StackCookie
0x14003b73b  call    __security_check_cookie
0x14003b740  lea     r11, [rsp+498h+var_18]
0x14003b748  mov     rbx, [r11+28h]
0x14003b74c  mov     rbp, [r11+30h]
0x14003b750  mov     rsp, r11
0x14003b753  pop     r14
0x14003b755  pop     rdi
0x14003b756  pop     rsi
0x14003b757  retn
```
