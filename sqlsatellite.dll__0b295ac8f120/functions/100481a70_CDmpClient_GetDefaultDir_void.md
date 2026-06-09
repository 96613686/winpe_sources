# CDmpClient::GetDefaultDir(void)

- ea: `0x100481a70`
- end: `0x100481bc6`
- name: `?GetDefaultDir@CDmpClient@@AEAAJXZ`
- size: `342`
- prototype: `__int64 __fastcall(CDmpClient *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1004818c0`
- `0x100481be0`

## callees

- `0x100403b90`
- `0x100481a70`
- `0x100486af0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x100481aaa`
- `KERNEL32!GetModuleFileNameW` at `0x100481aaa`
- `KERNEL32!GetModuleHandleW` at `0x100481a96`
- `KERNEL32!GetModuleHandleW` at `0x100481a96`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100481b67`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100481b67`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x100481b5a`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x100481b5a`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x100481b18`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x100481b18`

## pseudocode

```c
__int64 __fastcall CDmpClient::GetDefaultDir(CDmpClient *this)
{
  HMODULE ModuleHandleW; // rax
  struct __crt_locale_pointers *DefaultLocale; // rax
  WCHAR Filename[264]; // [rsp+50h] [rbp-A68h] BYREF
  wchar_t Dir[264]; // [rsp+260h] [rbp-858h] BYREF
  wchar_t Drive[264]; // [rsp+470h] [rbp-648h] BYREF
  wchar_t Ext[264]; // [rsp+680h] [rbp-438h] BYREF
  wchar_t v9[264]; // [rsp+890h] [rbp-228h] BYREF

  ModuleHandleW = GetModuleHandleW(0);
  if ( !GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) )
    return 0;
  Filename[260] = 0;
  _wsplitpath_s(Filename, Drive, 0x105u, Dir, 0x105u, v9, 0x105u, Ext, 0x105u);
  Drive[3] = 0;
  Dir[256] = 0;
  *((_WORD *)this + 3340) = 0;
  _wmakepath_s((wchar_t *)this + 3340, 0x104u, Drive, Dir, 0, 0);
  *((_WORD *)this + 3599) = 0;
  DefaultLocale = GetDefaultLocale();
  return StringCchPrintf_lW(
           (wchar_t *)this + 3080,
           0x104u,
           L"%ls\\%ls",
           DefaultLocale,
           (char *)this + 6680,
           L"SQLDUMPER.EXE");
}

```

## disassembly

```asm
0x100481a70  mov     [rsp+arg_10], rsi
0x100481a75  push    rdi
0x100481a76  sub     rsp, 0AB0h
0x100481a7d  mov     rax, cs:__security_cookie
0x100481a84  xor     rax, rsp
0x100481a87  mov     [rsp+0AB8h+var_18], rax
0x100481a8f  mov     rdi, rcx
0x100481a92  xor     esi, esi
0x100481a94  xor     ecx, ecx; lpModuleName
0x100481a96  call    cs:__imp_GetModuleHandleW
0x100481a9c  mov     r8d, 104h; nSize
0x100481aa2  lea     rdx, [rsp+0AB8h+Filename]; lpFilename
0x100481aa7  mov     rcx, rax; hModule
0x100481aaa  call    cs:__imp_GetModuleFileNameW
0x100481ab0  test    eax, eax
0x100481ab2  jz      loc_100481BA3
0x100481ab8  mov     [rsp+0AB8h+ExtCount], 105h; ExtCount
0x100481ac1  lea     rax, [rsp+0AB8h+var_438]
0x100481ac9  mov     [rsp+0AB8h+Ext], rax; Ext
0x100481ace  lea     r9, [rsp+0AB8h+Dir]; Dir
0x100481ad6  lea     rax, [rsp+0AB8h+var_228]
0x100481ade  mov     [rsp+0AB8h+FilenameCount], 105h; FilenameCount
0x100481ae7  mov     [rsp+0AB8h+var_A90], rax; Filename
0x100481aec  lea     rdx, [rsp+0AB8h+Drive]; Drive
0x100481af4  mov     r8d, 105h; DriveCount
0x100481afa  mov     [rsp+0AB8h+DirCount], 105h; DirCount
0x100481b03  lea     rcx, [rsp+0AB8h+Filename]; FullPath
0x100481b08  mov     [rsp+0AB8h+arg_8], rbx
0x100481b10  mov     [rsp+0AB8h+var_860], si
0x100481b18  call    cs:__imp__wsplitpath_s
0x100481b1e  lea     rbx, [rdi+1A18h]
0x100481b25  mov     [rsp+0AB8h+var_A90], rsi; Ext
0x100481b2a  mov     rcx, rbx; Buffer
0x100481b2d  mov     [rsp+0AB8h+var_642], si
0x100481b35  lea     r9, [rsp+0AB8h+Dir]; Dir
0x100481b3d  mov     [rsp+0AB8h+var_658], si
0x100481b45  lea     r8, [rsp+0AB8h+Drive]; Drive
0x100481b4d  mov     [rbx], si
0x100481b50  mov     edx, 104h; BufferCount
0x100481b55  mov     [rsp+0AB8h+DirCount], rsi; Filename
0x100481b5a  call    cs:__imp__wmakepath_s
0x100481b60  mov     [rdi+1C1Eh], si
0x100481b67  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100481b6d  lea     rcx, [rdi+1810h]; Buffer
0x100481b74  mov     edx, 104h; unsigned __int64
0x100481b79  mov     r9, rax; struct __crt_locale_pointers *
0x100481b7c  lea     r8, aLsLs_0; "%ls\\%ls"
0x100481b83  lea     rax, aSqldumperExe; "SQLDUMPER.EXE"
0x100481b8a  mov     [rsp+0AB8h+var_A90], rax
0x100481b8f  mov     [rsp+0AB8h+DirCount], rbx
0x100481b94  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100481b99  mov     rbx, [rsp+0AB8h+arg_8]
0x100481ba1  jmp     short loc_100481BA5
0x100481ba3  mov     eax, esi
0x100481ba5  mov     rcx, [rsp+0AB8h+var_18]
0x100481bad  xor     rcx, rsp; StackCookie
0x100481bb0  call    __security_check_cookie
0x100481bb5  mov     rsi, [rsp+0AB8h+arg_10]
0x100481bbd  add     rsp, 0AB0h
0x100481bc4  pop     rdi
0x100481bc5  retn
```
