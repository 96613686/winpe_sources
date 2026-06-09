# CallRegInstall(HINSTANCE__ *,char const *)

- ea: `0x18006b38c`
- end: `0x18006b4de`
- name: `?CallRegInstall@@YAJPEAUHINSTANCE__@@PEBD@Z`
- size: `338`
- prototype: `__int64 __fastcall(HINSTANCE, const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18006b610`
- `0x18006b630`

## callees

- `0x18002ff5c`
- `0x180035590`
- `0x1800513f4`
- `0x18006b38c`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18006b417`
- `KERNEL32!GetProcAddress` at `0x18006b417`
- `KERNEL32!FreeLibrary` at `0x18006b47a`
- `KERNEL32!FreeLibrary` at `0x18006b47a`
- `KERNEL32!GetSystemDirectoryW` at `0x18006b3d3`
- `KERNEL32!GetSystemDirectoryW` at `0x18006b3d3`
- `SHLWAPI!PathAppendW` at `0x18006b3ed`
- `SHLWAPI!PathAppendW` at `0x18006b3ed`

## string_xrefs

- `0x18006b3e1`: `ADVPACK.DLL`
- `0x18006b40d`: `RegInstall`
- `0x18006b457`: `%SystemRoot%\system32`

## pseudocode

```c
__int64 __fastcall CallRegInstall(HINSTANCE a1, const char *a2)
{
  HINSTANCE v2; // r14
  int v4; // ebx
  HMODULE LibraryW; // rax
  HMODULE v6; // rdi
  FARPROC ProcAddress; // rax
  _QWORD v9[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v10[4]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = g_hInst;
  v4 = -2147467259;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) || !PathAppendW(Buffer, L"ADVPACK.DLL") )
    goto LABEL_8;
  LibraryW = (HMODULE)IsolationAwareLoadLibraryW(Buffer);
  v6 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "RegInstall");
    if ( ProcAddress )
    {
      v9[0] = 2;
      v10[0] = "25";
      v10[1] = "%SystemRoot%";
      v10[2] = "11";
      v10[3] = "%SystemRoot%\\system32";
      v9[1] = v10;
      v4 = ((__int64 (__fastcall *)(HINSTANCE, const char *, _QWORD *))ProcAddress)(v2, a2, v9);
    }
  }
  FreeLibrary(v6);
  if ( v4 < 0 )
  {
LABEL_8:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids,
        (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006b38c  mov     [rsp-8+arg_0], rbx
0x18006b391  mov     [rsp-8+arg_10], rsi
0x18006b396  push    rbp
0x18006b397  push    rdi
0x18006b398  push    r14
0x18006b39a  lea     rbp, [rsp-170h]
0x18006b3a2  sub     rsp, 270h
0x18006b3a9  mov     rax, cs:__security_cookie
0x18006b3b0  xor     rax, rsp
0x18006b3b3  mov     [rbp+180h+var_20], rax
0x18006b3ba  mov     r14, cs:g_hInst
0x18006b3c1  lea     rcx, [rsp+280h+Buffer]; lpBuffer
0x18006b3c6  mov     rsi, rdx
0x18006b3c9  mov     ebx, 80004005h
0x18006b3ce  mov     edx, 104h; uSize
0x18006b3d3  call    cs:__imp_GetSystemDirectoryW
0x18006b3d9  test    eax, eax
0x18006b3db  jz      loc_18006B484
0x18006b3e1  lea     rdx, pszMore; "ADVPACK.DLL"
0x18006b3e8  lea     rcx, [rsp+280h+Buffer]; pszPath
0x18006b3ed  call    cs:__imp_PathAppendW
0x18006b3f3  test    eax, eax
0x18006b3f5  jz      loc_18006B484
0x18006b3fb  lea     rcx, [rsp+280h+Buffer]; lpLibFileName
0x18006b400  call    IsolationAwareLoadLibraryW
0x18006b405  mov     rdi, rax
0x18006b408  test    rax, rax
0x18006b40b  jz      short loc_18006B477
0x18006b40d  lea     rdx, aReginstall; "RegInstall"
0x18006b414  mov     rcx, rax; hModule
0x18006b417  call    cs:__imp_GetProcAddress
0x18006b41d  test    rax, rax
0x18006b420  jz      short loc_18006B477
0x18006b422  lea     rcx, a25_0; "25"
0x18006b429  mov     [rsp+280h+var_260], 2
0x18006b432  mov     [rsp+280h+var_250], rcx
0x18006b437  lea     r8, [rsp+280h+var_260]
0x18006b43c  lea     rcx, aSystemroot; "%SystemRoot%"
0x18006b443  mov     rdx, rsi
0x18006b446  mov     [rsp+280h+var_248], rcx
0x18006b44b  lea     rcx, a11; "11"
0x18006b452  mov     [rsp+280h+var_240], rcx
0x18006b457  lea     rcx, aSystemrootSyst; "%SystemRoot%\\system32"
0x18006b45e  mov     [rsp+280h+var_238], rcx
0x18006b463  lea     rcx, [rsp+280h+var_250]
0x18006b468  mov     [rsp+280h+var_258], rcx
0x18006b46d  mov     rcx, r14
0x18006b470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b475  mov     ebx, eax
0x18006b477  mov     rcx, rdi; hLibModule
0x18006b47a  call    cs:__imp_FreeLibrary
0x18006b480  test    ebx, ebx
0x18006b482  jns     short loc_18006B4B5
0x18006b484  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b48b  lea     rax, WPP_GLOBAL_Control
0x18006b492  cmp     rcx, rax
0x18006b495  jz      short loc_18006B4B5
0x18006b497  test    byte ptr [rcx+1Ch], 2
0x18006b49b  jz      short loc_18006B4B5
0x18006b49d  mov     rcx, [rcx+10h]
0x18006b4a1  lea     r8, WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids
0x18006b4a8  mov     edx, 0Fh
0x18006b4ad  mov     r9d, ebx
0x18006b4b0  call    WPP_SF_d
0x18006b4b5  mov     eax, ebx
0x18006b4b7  mov     rcx, [rbp+180h+var_20]
0x18006b4be  xor     rcx, rsp; StackCookie
0x18006b4c1  call    __security_check_cookie
0x18006b4c6  lea     r11, [rsp+280h+var_10]
0x18006b4ce  mov     rbx, [r11+20h]
0x18006b4d2  mov     rsi, [r11+30h]
0x18006b4d6  mov     rsp, r11
0x18006b4d9  pop     r14
0x18006b4db  pop     rdi
0x18006b4dc  pop     rbp
0x18006b4dd  retn
```
