# CleanupBrowserCaps(void)

- ea: `0x1800376f8`
- end: `0x18003785a`
- name: `?CleanupBrowserCaps@@YAJXZ`
- size: `354`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18003ef38`

## callees

- `0x180007824`
- `0x1800376f8`
- `0x18003abe4`
- `0x18003cbac`
- `0x18004d030`
- `0x18004d298`
- `0x18004d350`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18003778a`
- `KERNEL32!lstrlenW` at `0x18003778a`
- `KERNEL32!DeleteFileW` at `0x1800377b1`
- `KERNEL32!DeleteFileW` at `0x1800377f6`
- `KERNEL32!DeleteFileW` at `0x1800377b1`
- `KERNEL32!DeleteFileW` at `0x1800377f6`

## string_xrefs

- `0x180037768`: `\config\browsers\`
- `0x180037790`: `ASP.BrowserCapsFactory.dll`

## pseudocode

```c
__int64 CleanupBrowserCaps(void)
{
  unsigned int v0; // ebx
  __int64 v1; // rdi
  WCHAR String[264]; // [rsp+30h] [rbp-228h] BYREF

  CSetupLogging::Log(1, "CleanupBrowserCaps", 0, "Cleanup browser caps files", 0);
  String[0] = 0;
  v0 = StringCchCatW(String, 0x104u, &Names::s_wszInstallDirectory);
  if ( !v0 )
  {
    v0 = StringCchCatW(String, 0x104u, L"\\config\\browsers\\");
    if ( !v0 )
    {
      v1 = lstrlenW(String);
      v0 = StringCchCatW(String, 0x104u, L"ASP.BrowserCapsFactory.dll");
      if ( !v0 )
      {
        if ( !DeleteFileW(String) )
          GetLastWin32Error();
        if ( (unsigned __int64)(2 * v1) >= 0x208 )
          _report_rangecheckfailure();
        String[v1] = 0;
        v0 = StringCchCatW(String, 0x104u, L"BrowserCapsFactory.cs");
        if ( !v0 )
        {
          if ( !DeleteFileW(String) )
            GetLastWin32Error();
          v0 = RemoveBrowserCapsFromGac();
        }
      }
    }
  }
  CSetupLogging::Log(v0, "CleanupBrowserCaps", 0, "Cleanup browser caps files", 0);
  return v0;
}

```

## disassembly

```asm
0x1800376f8  mov     [rsp+arg_0], rbx
0x1800376fd  mov     [rsp+arg_8], rbp
0x180037702  mov     [rsp+arg_10], rsi
0x180037707  push    rdi
0x180037708  sub     rsp, 250h
0x18003770f  mov     rax, cs:__security_cookie
0x180037716  xor     rax, rsp
0x180037719  mov     [rsp+258h+var_18], rax
0x180037721  xor     esi, esi
0x180037723  lea     r9, aCleanupBrowser; "Cleanup browser caps files"
0x18003772a  xor     r8d, r8d; unsigned int
0x18003772d  mov     [rsp+258h+var_238], rsi; unsigned __int16 *
0x180037732  lea     rdx, aCleanupbrowser; "CleanupBrowserCaps"
0x180037739  lea     ecx, [rsi+1]; int
0x18003773c  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180037741  mov     ebp, 104h
0x180037746  mov     [rsp+258h+String], si
0x18003774b  mov     edx, ebp; unsigned __int64
0x18003774d  lea     r8, ?s_wszInstallDirectory@Names@@0PAGA; unsigned __int16 *
0x180037754  lea     rcx, [rsp+258h+String]; unsigned __int16 *
0x180037759  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003775e  mov     ebx, eax
0x180037760  test    eax, eax
0x180037762  jnz     loc_18003780C
0x180037768  lea     r8, aConfigBrowsers; "\\config\\browsers\\"
0x18003776f  mov     edx, ebp; unsigned __int64
0x180037771  lea     rcx, [rsp+258h+String]; unsigned __int16 *
0x180037776  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003777b  mov     ebx, eax
0x18003777d  test    eax, eax
0x18003777f  jnz     loc_18003780C
0x180037785  lea     rcx, [rsp+258h+String]; lpString
0x18003778a  call    cs:__imp_lstrlenW
0x180037790  lea     r8, aAspBrowsercaps; "ASP.BrowserCapsFactory.dll"
0x180037797  mov     edx, ebp; unsigned __int64
0x180037799  lea     rcx, [rsp+258h+String]; unsigned __int16 *
0x18003779e  movsxd  rdi, eax
0x1800377a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800377a6  mov     ebx, eax
0x1800377a8  test    eax, eax
0x1800377aa  jnz     short loc_18003780C
0x1800377ac  lea     rcx, [rsp+258h+String]; lpFileName
0x1800377b1  call    cs:__imp_DeleteFileW
0x1800377b7  test    eax, eax
0x1800377b9  jnz     short loc_1800377C0
0x1800377bb  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800377c0  mov     rax, rdi
0x1800377c3  add     rax, rax
0x1800377c6  cmp     rax, 208h
0x1800377cc  jnb     loc_180037854
0x1800377d2  lea     r8, aBrowsercapsfac; "BrowserCapsFactory.cs"
0x1800377d9  mov     [rsp+rax+258h+String], si
0x1800377de  mov     rdx, rbp; unsigned __int64
0x1800377e1  lea     rcx, [rsp+258h+String]; unsigned __int16 *
0x1800377e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800377eb  mov     ebx, eax
0x1800377ed  test    eax, eax
0x1800377ef  jnz     short loc_18003780C
0x1800377f1  lea     rcx, [rsp+258h+String]; lpFileName
0x1800377f6  call    cs:__imp_DeleteFileW
0x1800377fc  test    eax, eax
0x1800377fe  jnz     short loc_180037805
0x180037800  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180037805  call    ?RemoveBrowserCapsFromGac@@YAJXZ; RemoveBrowserCapsFromGac(void)
0x18003780a  mov     ebx, eax
0x18003780c  lea     r9, aCleanupBrowser; "Cleanup browser caps files"
0x180037813  mov     [rsp+258h+var_238], rsi; unsigned __int16 *
0x180037818  xor     r8d, r8d; unsigned int
0x18003781b  lea     rdx, aCleanupbrowser; "CleanupBrowserCaps"
0x180037822  mov     ecx, ebx; int
0x180037824  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x180037829  mov     eax, ebx
0x18003782b  mov     rcx, [rsp+258h+var_18]
0x180037833  xor     rcx, rsp; StackCookie
0x180037836  call    __security_check_cookie
0x18003783b  lea     r11, [rsp+258h+var_8]
0x180037843  mov     rbx, [r11+10h]
0x180037847  mov     rbp, [r11+18h]
0x18003784b  mov     rsi, [r11+20h]
0x18003784f  mov     rsp, r11
0x180037852  pop     rdi
0x180037853  retn
0x180037854  call    __report_rangecheckfailure
```
