# HtmlHelpA

- ea: `0x383adbe80`
- end: `0x383adbf66`
- name: `HtmlHelpA`
- size: `230`
- prototype: `HWND __stdcall(HWND hwndCaller, LPCSTR pszFile, UINT uCommand, DWORD_PTR dwData)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x383a29590`

## callees

- `0x3838434c0`
- `0x383adbc1c`
- `0x383adbe80`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x383adbf26`
- `KERNEL32!GetProcAddress` at `0x383adbf26`
- `KERNEL32!LoadLibraryA` at `0x383adbed1`
- `KERNEL32!LoadLibraryA` at `0x383adbef3`
- `KERNEL32!LoadLibraryA` at `0x383adbed1`
- `KERNEL32!LoadLibraryA` at `0x383adbef3`

## pseudocode

```c
HWND __stdcall HtmlHelpA(HWND hwndCaller, LPCSTR pszFile, UINT uCommand, DWORD_PTR dwData)
{
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // r10
  CHAR LibFileName[272]; // [rsp+20h] [rbp-148h] BYREF

  LibraryA = qword_383B2BDE8;
  if ( qword_383B2BDE8
    || dword_383B2BDE0
    || (!(unsigned int)GetRegisteredLocation(LibFileName)
      ? (LibraryA = qword_383B2BDE8)
      : (LibraryA = LoadLibraryA(LibFileName), qword_383B2BDE8 = LibraryA),
        LibraryA || (LibraryA = LoadLibraryA("hhctrl.ocx"), (qword_383B2BDE8 = LibraryA) != 0)) )
  {
    ProcAddress = (FARPROC)pHtmlHelpA;
    if ( pHtmlHelpA )
      return (HWND)((__int64 (__fastcall *)(HWND, LPCSTR, _QWORD, DWORD_PTR))ProcAddress)(
                     hwndCaller,
                     pszFile,
                     uCommand,
                     dwData);
    ProcAddress = GetProcAddress(LibraryA, (LPCSTR)0xE);
    pHtmlHelpA = (HWND (*)(HWND, const char *, unsigned int, unsigned __int64))ProcAddress;
    if ( ProcAddress )
      return (HWND)((__int64 (__fastcall *)(HWND, LPCSTR, _QWORD, DWORD_PTR))ProcAddress)(
                     hwndCaller,
                     pszFile,
                     uCommand,
                     dwData);
  }
  dword_383B2BDE0 = 1;
  return 0;
}

```

## disassembly

```asm
0x383adbe80  push    rbx
0x383adbe82  push    rbp
0x383adbe83  push    rsi
0x383adbe84  push    rdi
0x383adbe85  sub     rsp, 148h
0x383adbe8c  mov     rax, cs:__security_cookie
0x383adbe93  xor     rax, rsp
0x383adbe96  mov     [rsp+168h+var_38], rax
0x383adbe9e  mov     rax, cs:qword_383B2BDE8
0x383adbea5  mov     rbp, r9
0x383adbea8  mov     esi, r8d
0x383adbeab  mov     rdi, rdx
0x383adbeae  mov     rbx, rcx
0x383adbeb1  test    rax, rax
0x383adbeb4  jnz     short loc_383ADBF13
0x383adbeb6  cmp     cs:dword_383B2BDE0, eax
0x383adbebc  jnz     short loc_383ADBF13
0x383adbebe  lea     rcx, [rsp+168h+LibFileName]; lpDst
0x383adbec3  call    GetRegisteredLocation
0x383adbec8  test    eax, eax
0x383adbeca  jz      short loc_383ADBEE0
0x383adbecc  lea     rcx, [rsp+168h+LibFileName]; lpLibFileName
0x383adbed1  call    cs:__imp_LoadLibraryA
0x383adbed7  mov     cs:qword_383B2BDE8, rax
0x383adbede  jmp     short loc_383ADBEE7
0x383adbee0  mov     rax, cs:qword_383B2BDE8
0x383adbee7  test    rax, rax
0x383adbeea  jnz     short loc_383ADBF13
0x383adbeec  lea     rcx, aHhctrlOcx; "hhctrl.ocx"
0x383adbef3  call    cs:__imp_LoadLibraryA
0x383adbef9  mov     cs:qword_383B2BDE8, rax
0x383adbf00  test    rax, rax
0x383adbf03  jnz     short loc_383ADBF13
0x383adbf05  mov     cs:dword_383B2BDE0, 1
0x383adbf0f  xor     eax, eax
0x383adbf11  jmp     short loc_383ADBF4A
0x383adbf13  mov     r10, cs:?pHtmlHelpA@@3P6APEAUHWND__@@PEAU1@PEBDI_K@ZEA; HWND__ * (*pHtmlHelpA)(HWND__ *,char const *,uint,unsigned __int64)
0x383adbf1a  test    r10, r10
0x383adbf1d  jnz     short loc_383ADBF3B
0x383adbf1f  lea     edx, [r10+0Eh]; lpProcName
0x383adbf23  mov     rcx, rax; hModule
0x383adbf26  call    cs:__imp_GetProcAddress
0x383adbf2c  mov     r10, rax
0x383adbf2f  mov     cs:?pHtmlHelpA@@3P6APEAUHWND__@@PEAU1@PEBDI_K@ZEA, rax; HWND__ * (*pHtmlHelpA)(HWND__ *,char const *,uint,unsigned __int64)
0x383adbf36  test    rax, rax
0x383adbf39  jz      short loc_383ADBF05
0x383adbf3b  mov     r9, rbp
0x383adbf3e  mov     r8d, esi
0x383adbf41  mov     rdx, rdi
0x383adbf44  mov     rcx, rbx
0x383adbf47  call    r10 ; HWND__ * (*pHtmlHelpA)(HWND__ *,char const *,uint,unsigned __int64)
0x383adbf4a  mov     rcx, [rsp+168h+var_38]
0x383adbf52  xor     rcx, rsp; StackCookie
0x383adbf55  call    __security_check_cookie
0x383adbf5a  add     rsp, 148h
0x383adbf61  pop     rdi
0x383adbf62  pop     rsi
0x383adbf63  pop     rbp
0x383adbf64  pop     rbx
0x383adbf65  retn
```
