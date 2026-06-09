# CISAPI::Load(ushort *)

- ea: `0x180001da8`
- end: `0x180001f12`
- name: `?Load@CISAPI@@QEAAHPEAG@Z`
- size: `362`
- prototype: `int(CISAPI *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002290`

## callees

- `0x180001da8`
- `0x180039a84`
- `0x18003a560`
- `0x18003ae80`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001e35`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001de0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001de0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001edd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001edd`

## string_xrefs

- `0x180001e2b`: `TerminateExtension`
- `0x180001e18`: `HttpExtensionProc`
- `0x180001e04`: `GetExtensionVersion`

## pseudocode

```c
__int64 __fastcall CISAPI::Load(CISAPI *this, unsigned __int16 *a2)
{
  HMODULE Library; // rax
  HMODULE *v4; // r14
  FARPROC *v5; // rsi
  _BYTE v7[272]; // [rsp+40h] [rbp-128h] BYREF

  Library = LoadLibraryExW(a2, 0, 0);
  v4 = (HMODULE *)((char *)this + 8);
  *((_QWORD *)this + 1) = Library;
  if ( !Library )
    return 0;
  v5 = (FARPROC *)((char *)this + 24);
  if ( *(_DWORD *)this == 1 )
  {
    *((_QWORD *)this + 2) = GetProcAddress(Library, "GetExtensionVersion");
    *v5 = GetProcAddress(*v4, "HttpExtensionProc");
    *((_QWORD *)this + 4) = GetProcAddress(*v4, "TerminateExtension");
  }
  if ( !*v5 || !*((_QWORD *)this + 2) )
  {
    *((_QWORD *)this + 2) = 0;
    *v5 = 0;
    *((_QWORD *)this + 4) = 0;
    if ( *v4 )
      FreeLibrary(*v4);
    *v4 = 0;
    return 0;
  }
  if ( *(_DWORD *)this == 1 )
  {
    memset_0(v7, 0, 0x104u);
    (*((void (__fastcall **)(_BYTE *))this + 2))(v7);
  }
  return 1;
}

```

## disassembly

```asm
0x180001da8  mov     [rsp+arg_10], rsi
0x180001dad  mov     [rsp+arg_18], rdi
0x180001db2  push    r14
0x180001db4  sub     rsp, 160h
0x180001dbb  mov     rax, cs:__security_cookie
0x180001dc2  xor     rax, rsp
0x180001dc5  mov     [rsp+168h+var_18], rax
0x180001dcd  mov     rax, rdx
0x180001dd0  mov     rdi, rcx
0x180001dd3  mov     [rsp+168h+var_140], rcx
0x180001dd8  xor     r8d, r8d; dwFlags
0x180001ddb  xor     edx, edx; hFile
0x180001ddd  mov     rcx, rax; lpLibFileName
0x180001de0  call    cs:__imp_LoadLibraryExW
0x180001de6  lea     r14, [rdi+8]
0x180001dea  mov     [rsp+168h+var_138], r14
0x180001def  mov     [r14], rax
0x180001df2  test    rax, rax
0x180001df5  jz      loc_180001EEA
0x180001dfb  lea     rsi, [rdi+18h]
0x180001dff  cmp     dword ptr [rdi], 1
0x180001e02  jnz     short loc_180001E3F
0x180001e04  lea     rdx, ProcName; "GetExtensionVersion"
0x180001e0b  mov     rcx, rax; hModule
0x180001e0e  call    cs:__imp_GetProcAddress
0x180001e14  mov     [rdi+10h], rax
0x180001e18  lea     rdx, aHttpextensionp; "HttpExtensionProc"
0x180001e1f  mov     rcx, [r14]; hModule
0x180001e22  call    cs:__imp_GetProcAddress
0x180001e28  mov     [rsi], rax
0x180001e2b  lea     rdx, aTerminateexten; "TerminateExtension"
0x180001e32  mov     rcx, [r14]; hModule
0x180001e35  call    cs:__imp_GetProcAddress
0x180001e3b  mov     [rdi+20h], rax
0x180001e3f  mov     [rsp+168h+var_148], rsi
0x180001e44  cmp     qword ptr [rsi], 0
0x180001e48  jz      short loc_180001EBD
0x180001e4a  cmp     qword ptr [rdi+10h], 0
0x180001e4f  jz      short loc_180001EBD
0x180001e51  cmp     dword ptr [rdi], 1
0x180001e54  jnz     short loc_180001E76
0x180001e56  xor     edx, edx; Val
0x180001e58  mov     r8d, 104h; Size
0x180001e5e  lea     rcx, [rsp+168h+var_128]; void *
0x180001e63  call    memset_0
0x180001e68  lea     rcx, [rsp+168h+var_128]
0x180001e6d  mov     rax, [rdi+10h]
0x180001e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e76  mov     eax, 1
0x180001e7b  jmp     short loc_180001EEC
0x180001e7d  lea     rax, WPP_GLOBAL_Control
0x180001e84  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e8b  cmp     rcx, rax
0x180001e8e  jz      short loc_180001EAE
0x180001e90  test    dword ptr [rcx+1Ch], 1000h
0x180001e97  jz      short loc_180001EAE
0x180001e99  mov     edx, 0Fh
0x180001e9e  lea     r8, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids
0x180001ea5  mov     rcx, [rcx+10h]
0x180001ea9  call    WPP_SF_
0x180001eae  mov     rdi, [rsp+168h+var_140]
0x180001eb3  mov     rsi, [rsp+168h+var_148]
0x180001eb8  mov     r14, [rsp+168h+var_138]
0x180001ebd  mov     qword ptr [rdi+10h], 0
0x180001ec5  mov     qword ptr [rsi], 0
0x180001ecc  mov     qword ptr [rdi+20h], 0
0x180001ed4  cmp     qword ptr [r14], 0
0x180001ed8  jz      short loc_180001EE3
0x180001eda  mov     rcx, [r14]; hLibModule
0x180001edd  call    cs:__imp_FreeLibrary
0x180001ee3  mov     qword ptr [r14], 0
0x180001eea  xor     eax, eax
0x180001eec  mov     rcx, [rsp+168h+var_18]
0x180001ef4  xor     rcx, rsp; StackCookie
0x180001ef7  call    __security_check_cookie
0x180001efc  lea     r11, [rsp+168h+var_8]
0x180001f04  mov     rsi, [r11+20h]
0x180001f08  mov     rdi, [r11+28h]
0x180001f0c  mov     rsp, r11
0x180001f0f  pop     r14
0x180001f11  retn
```
