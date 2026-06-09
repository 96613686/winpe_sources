# CDmpClient::GetDefaultDir(void)

- ea: `0x1004417c0`
- end: `0x100441917`
- name: `?GetDefaultDir@CDmpClient@@AEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(CDmpClient *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x100441610`
- `0x100441930`

## callees

- `0x100401580`
- `0x100401aa0`
- `0x1004417c0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1004417fa`
- `KERNEL32!GetModuleFileNameW` at `0x1004417fa`
- `KERNEL32!GetModuleHandleW` at `0x1004417e6`
- `KERNEL32!GetModuleHandleW` at `0x1004417e6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004418b7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004418b7`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x100441868`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x100441868`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1004418aa`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x1004418aa`

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
0x1004417c0  mov     [rsp+arg_10], rsi
0x1004417c5  push    rdi
0x1004417c6  sub     rsp, 0AB0h
0x1004417cd  mov     rax, cs:__security_cookie
0x1004417d4  xor     rax, rsp
0x1004417d7  mov     [rsp+0AB8h+var_18], rax
0x1004417df  mov     rdi, rcx
0x1004417e2  xor     esi, esi
0x1004417e4  xor     ecx, ecx; lpModuleName
0x1004417e6  call    cs:__imp_GetModuleHandleW
0x1004417ec  mov     r8d, 104h; nSize
0x1004417f2  lea     rdx, [rsp+0AB8h+Filename]; lpFilename
0x1004417f7  mov     rcx, rax; hModule
0x1004417fa  call    cs:__imp_GetModuleFileNameW
0x100441800  test    eax, eax
0x100441802  jz      loc_1004418F4
0x100441808  mov     [rsp+0AB8h+ExtCount], 105h; ExtCount
0x100441811  lea     rax, [rsp+0AB8h+var_438]
0x100441819  mov     [rsp+0AB8h+Ext], rax; Ext
0x10044181e  lea     r9, [rsp+0AB8h+Dir]; Dir
0x100441826  lea     rax, [rsp+0AB8h+var_228]
0x10044182e  mov     [rsp+0AB8h+FilenameCount], 105h; FilenameCount
0x100441837  mov     [rsp+0AB8h+var_A90], rax; Filename
0x10044183c  lea     rdx, [rsp+0AB8h+Drive]; Drive
0x100441844  mov     r8d, 105h; DriveCount
0x10044184a  mov     [rsp+0AB8h+DirCount], 105h; DirCount
0x100441853  lea     rcx, [rsp+0AB8h+Filename]; FullPath
0x100441858  mov     [rsp+0AB8h+arg_8], rbx
0x100441860  mov     [rsp+0AB8h+var_860], si
0x100441868  call    cs:__imp__wsplitpath_s
0x10044186e  lea     rbx, [rdi+1A18h]
0x100441875  mov     [rsp+0AB8h+var_A90], rsi; Ext
0x10044187a  mov     rcx, rbx; Buffer
0x10044187d  mov     [rsp+0AB8h+var_642], si
0x100441885  lea     r9, [rsp+0AB8h+Dir]; Dir
0x10044188d  mov     [rsp+0AB8h+var_658], si
0x100441895  lea     r8, [rsp+0AB8h+Drive]; Drive
0x10044189d  mov     [rbx], si
0x1004418a0  mov     edx, 104h; BufferCount
0x1004418a5  mov     [rsp+0AB8h+DirCount], rsi; Filename
0x1004418aa  call    cs:__imp__wmakepath_s
0x1004418b0  mov     [rdi+1C1Eh], si
0x1004418b7  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004418bd  lea     rcx, [rdi+1810h]; Buffer
0x1004418c4  mov     edx, 104h; unsigned __int64
0x1004418c9  mov     r9, rax; struct __crt_locale_pointers *
0x1004418cc  lea     r8, aLsLs_1; "%ls\\%ls"
0x1004418d3  lea     rax, aSqldumperExe; "SQLDUMPER.EXE"
0x1004418da  mov     [rsp+0AB8h+var_A90], rax
0x1004418df  mov     [rsp+0AB8h+DirCount], rbx
0x1004418e4  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x1004418e9  mov     rbx, [rsp+0AB8h+arg_8]
0x1004418f1  jmp     short loc_1004418F6
0x1004418f4  mov     eax, esi
0x1004418f6  mov     rcx, [rsp+0AB8h+var_18]
0x1004418fe  xor     rcx, rsp; StackCookie
0x100441901  call    __security_check_cookie
0x100441906  mov     rsi, [rsp+0AB8h+arg_10]
0x10044190e  add     rsp, 0AB0h
0x100441915  pop     rdi
0x100441916  retn
```
