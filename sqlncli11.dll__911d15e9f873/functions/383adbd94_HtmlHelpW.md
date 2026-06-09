# HtmlHelpW

- ea: `0x383adbd94`
- end: `0x383adbe7a`
- name: `HtmlHelpW`
- size: `230`
- prototype: `HWND __stdcall(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x38391d3b0`
- `0x383920e90`
- `0x383921b40`
- `0x383922240`
- `0x383922de0`
- `0x383a9f880`

## callees

- `0x3838434c0`
- `0x383adbc1c`
- `0x383adbd94`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x383adbe3a`
- `KERNEL32!GetProcAddress` at `0x383adbe3a`
- `KERNEL32!LoadLibraryA` at `0x383adbde5`
- `KERNEL32!LoadLibraryA` at `0x383adbe07`
- `KERNEL32!LoadLibraryA` at `0x383adbde5`
- `KERNEL32!LoadLibraryA` at `0x383adbe07`

## pseudocode

```c
HWND __stdcall HtmlHelpW(HWND hwndCaller, LPCWSTR pszFile, UINT uCommand, DWORD_PTR dwData)
{
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // r10
  CHAR LibFileName[272]; // [rsp+20h] [rbp-148h] BYREF

  LibraryA = qword_383B2BDD8;
  if ( qword_383B2BDD8
    || dword_383B2BDD0
    || (!(unsigned int)GetRegisteredLocation(LibFileName)
      ? (LibraryA = qword_383B2BDD8)
      : (LibraryA = LoadLibraryA(LibFileName), qword_383B2BDD8 = LibraryA),
        LibraryA || (LibraryA = LoadLibraryA("hhctrl.ocx"), (qword_383B2BDD8 = LibraryA) != 0)) )
  {
    ProcAddress = (FARPROC)pHtmlHelpW;
    if ( pHtmlHelpW )
      return (HWND)((__int64 (__fastcall *)(HWND, LPCWSTR, _QWORD, DWORD_PTR))ProcAddress)(
                     hwndCaller,
                     pszFile,
                     uCommand,
                     dwData);
    ProcAddress = GetProcAddress(LibraryA, (LPCSTR)0xF);
    pHtmlHelpW = (HWND (*)(HWND, const unsigned __int16 *, unsigned int, unsigned __int64))ProcAddress;
    if ( ProcAddress )
      return (HWND)((__int64 (__fastcall *)(HWND, LPCWSTR, _QWORD, DWORD_PTR))ProcAddress)(
                     hwndCaller,
                     pszFile,
                     uCommand,
                     dwData);
  }
  dword_383B2BDD0 = 1;
  return 0;
}

```

## disassembly

```asm
0x383adbd94  push    rbx
0x383adbd96  push    rbp
0x383adbd97  push    rsi
0x383adbd98  push    rdi
0x383adbd99  sub     rsp, 148h
0x383adbda0  mov     rax, cs:__security_cookie
0x383adbda7  xor     rax, rsp
0x383adbdaa  mov     [rsp+168h+var_38], rax
0x383adbdb2  mov     rax, cs:qword_383B2BDD8
0x383adbdb9  mov     rbp, r9
0x383adbdbc  mov     esi, r8d
0x383adbdbf  mov     rdi, rdx
0x383adbdc2  mov     rbx, rcx
0x383adbdc5  test    rax, rax
0x383adbdc8  jnz     short loc_383ADBE27
0x383adbdca  cmp     cs:dword_383B2BDD0, eax
0x383adbdd0  jnz     short loc_383ADBE27
0x383adbdd2  lea     rcx, [rsp+168h+LibFileName]; lpDst
0x383adbdd7  call    GetRegisteredLocation
0x383adbddc  test    eax, eax
0x383adbdde  jz      short loc_383ADBDF4
0x383adbde0  lea     rcx, [rsp+168h+LibFileName]; lpLibFileName
0x383adbde5  call    cs:__imp_LoadLibraryA
0x383adbdeb  mov     cs:qword_383B2BDD8, rax
0x383adbdf2  jmp     short loc_383ADBDFB
0x383adbdf4  mov     rax, cs:qword_383B2BDD8
0x383adbdfb  test    rax, rax
0x383adbdfe  jnz     short loc_383ADBE27
0x383adbe00  lea     rcx, aHhctrlOcx; "hhctrl.ocx"
0x383adbe07  call    cs:__imp_LoadLibraryA
0x383adbe0d  mov     cs:qword_383B2BDD8, rax
0x383adbe14  test    rax, rax
0x383adbe17  jnz     short loc_383ADBE27
0x383adbe19  mov     cs:dword_383B2BDD0, 1
0x383adbe23  xor     eax, eax
0x383adbe25  jmp     short loc_383ADBE5E
0x383adbe27  mov     r10, cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x383adbe2e  test    r10, r10
0x383adbe31  jnz     short loc_383ADBE4F
0x383adbe33  lea     edx, [r10+0Fh]; lpProcName
0x383adbe37  mov     rcx, rax; hModule
0x383adbe3a  call    cs:__imp_GetProcAddress
0x383adbe40  mov     r10, rax
0x383adbe43  mov     cs:?pHtmlHelpW@@3P6APEAUHWND__@@PEAU1@PEBGI_K@ZEA, rax; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x383adbe4a  test    rax, rax
0x383adbe4d  jz      short loc_383ADBE19
0x383adbe4f  mov     r9, rbp
0x383adbe52  mov     r8d, esi
0x383adbe55  mov     rdx, rdi
0x383adbe58  mov     rcx, rbx
0x383adbe5b  call    r10 ; HWND__ * (*pHtmlHelpW)(HWND__ *,ushort const *,uint,unsigned __int64)
0x383adbe5e  mov     rcx, [rsp+168h+var_38]
0x383adbe66  xor     rcx, rsp; StackCookie
0x383adbe69  call    __security_check_cookie
0x383adbe6e  add     rsp, 148h
0x383adbe75  pop     rdi
0x383adbe76  pop     rsi
0x383adbe77  pop     rbp
0x383adbe78  pop     rbx
0x383adbe79  retn
```
