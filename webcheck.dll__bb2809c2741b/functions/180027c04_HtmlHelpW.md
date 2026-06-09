# HtmlHelpW

- ea: `0x180027c04`
- end: `0x180027d04`
- name: `HtmlHelpW`
- size: `256`
- prototype: `HWND __stdcall(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a6d4`

## callees

- `0x180027ae8`
- `0x180027c04`
- `0x18002924e`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180027cac`
- `KERNEL32!GetProcAddress` at `0x180027cac`
- `KERNEL32!LoadLibraryExA` at `0x180027c60`
- `KERNEL32!LoadLibraryExA` at `0x180027c87`
- `KERNEL32!LoadLibraryExA` at `0x180027c60`
- `KERNEL32!LoadLibraryExA` at `0x180027c87`

## pseudocode

```c
HWND __stdcall HtmlHelpW(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)
{
  HMODULE Library; // rax
  HWND (*v6)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64); // r10
  CHAR LibFileName[272]; // [rsp+30h] [rbp-128h] BYREF

  Library = hModule;
  if ( hModule
    || dword_180034AC8
    || ((memset_0(LibFileName, 0, 0x104u), !(unsigned int)GetRegisteredLocation(LibFileName))
      ? (Library = hModule)
      : (Library = LoadLibraryExA(LibFileName, 0, 0), hModule = Library),
        Library || (Library = LoadLibraryExA("hhctrl.ocx", 0, 0), (hModule = Library) != 0)) )
  {
    v6 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, const wchar_t *, _QWORD, const wchar_t *))v6)(
                     hwndCaller,
                     L"iexplore.chm > iedefault",
                     0,
                     L"subs_upd.htm");
    pHtmlHelpW = (HWND (*)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64))GetProcAddress(
                                                                                             Library,
                                                                                             (LPCSTR)0xF);
    v6 = pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, const wchar_t *, _QWORD, const wchar_t *))v6)(
                     hwndCaller,
                     L"iexplore.chm > iedefault",
                     0,
                     L"subs_upd.htm");
  }
  dword_180034AC8 = 1;
  return 0;
}

```

## disassembly

```asm
0x180027c04  push    rbx
0x180027c06  sub     rsp, 150h
0x180027c0d  mov     rax, cs:__security_cookie
0x180027c14  xor     rax, rsp
0x180027c17  mov     [rsp+158h+var_18], rax
0x180027c1f  mov     rax, cs:hModule
0x180027c26  mov     rbx, rcx
0x180027c29  test    rax, rax
0x180027c2c  jnz     short loc_180027C99
0x180027c2e  cmp     cs:dword_180034AC8, eax
0x180027c34  jnz     short loc_180027C99
0x180027c36  xor     edx, edx; Val
0x180027c38  lea     rcx, [rsp+158h+LibFileName]; void *
0x180027c3d  mov     r8d, 104h; Size
0x180027c43  call    memset_0
0x180027c48  lea     rcx, [rsp+158h+LibFileName]; char *
0x180027c4d  call    GetRegisteredLocation
0x180027c52  test    eax, eax
0x180027c54  jz      short loc_180027C6F
0x180027c56  xor     r8d, r8d; dwFlags
0x180027c59  lea     rcx, [rsp+158h+LibFileName]; lpLibFileName
0x180027c5e  xor     edx, edx; hFile
0x180027c60  call    cs:__imp_LoadLibraryExA
0x180027c66  mov     cs:hModule, rax
0x180027c6d  jmp     short loc_180027C76
0x180027c6f  mov     rax, cs:hModule
0x180027c76  test    rax, rax
0x180027c79  jnz     short loc_180027C99
0x180027c7b  xor     r8d, r8d; dwFlags
0x180027c7e  lea     rcx, aHhctrlOcx; "hhctrl.ocx"
0x180027c85  xor     edx, edx; hFile
0x180027c87  call    cs:__imp_LoadLibraryExA
0x180027c8d  mov     cs:hModule, rax
0x180027c94  test    rax, rax
0x180027c97  jz      short loc_180027CC1
0x180027c99  mov     r10, cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x180027ca0  test    r10, r10
0x180027ca3  jnz     short loc_180027CCF
0x180027ca5  lea     edx, [r10+0Fh]; lpProcName
0x180027ca9  mov     rcx, rax; hModule
0x180027cac  call    cs:__imp_GetProcAddress
0x180027cb2  mov     cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA, rax; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x180027cb9  mov     r10, rax
0x180027cbc  test    rax, rax
0x180027cbf  jnz     short loc_180027CCF
0x180027cc1  mov     cs:dword_180034AC8, 1
0x180027ccb  xor     eax, eax
0x180027ccd  jmp     short loc_180027CEB
0x180027ccf  lea     r9, aSubsUpdHtm; "subs_upd.htm"
0x180027cd6  xor     r8d, r8d
0x180027cd9  lea     rdx, aIexploreChmIed; "iexplore.chm > iedefault"
0x180027ce0  mov     rcx, rbx
0x180027ce3  mov     rax, r10
0x180027ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ceb  mov     rcx, [rsp+158h+var_18]
0x180027cf3  xor     rcx, rsp; StackCookie
0x180027cf6  call    __security_check_cookie
0x180027cfb  add     rsp, 150h
0x180027d02  pop     rbx
0x180027d03  retn
```
