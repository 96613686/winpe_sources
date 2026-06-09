# CISAPI::Load(ushort *)

- ea: `0x1800167e8`
- end: `0x180016971`
- name: `?Load@CISAPI@@QEAAHPEAG@Z`
- size: `393`
- prototype: `__int64 __fastcall(CISAPI *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016d20`

## callees

- `0x1800167e8`
- `0x18003c018`
- `0x18003cb60`
- `0x18003d4b0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016854`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001686e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016887`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016854`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001686e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016887`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016820`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016820`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016935`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016935`

## string_xrefs

- `0x18001687d`: `TerminateExtension`
- `0x180016864`: `HttpExtensionProc`
- `0x18001684a`: `GetExtensionVersion`

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
0x1800167e8  mov     [rsp+arg_10], rsi
0x1800167ed  mov     [rsp+arg_18], rdi
0x1800167f2  push    r14
0x1800167f4  sub     rsp, 160h
0x1800167fb  mov     rax, cs:__security_cookie
0x180016802  xor     rax, rsp
0x180016805  mov     [rsp+168h+var_18], rax
0x18001680d  mov     rax, rdx
0x180016810  mov     rdi, rcx
0x180016813  mov     [rsp+168h+var_140], rcx
0x180016818  xor     r8d, r8d; dwFlags
0x18001681b  xor     edx, edx; hFile
0x18001681d  mov     rcx, rax; lpLibFileName
0x180016820  call    cs:__imp_LoadLibraryExW
0x180016827  nop     dword ptr [rax+rax+00h]
0x18001682c  lea     r14, [rdi+8]
0x180016830  mov     [rsp+168h+var_138], r14
0x180016835  mov     [r14], rax
0x180016838  test    rax, rax
0x18001683b  jz      loc_180016948
0x180016841  lea     rsi, [rdi+18h]
0x180016845  cmp     dword ptr [rdi], 1
0x180016848  jnz     short loc_180016897
0x18001684a  lea     rdx, ProcName; "GetExtensionVersion"
0x180016851  mov     rcx, rax; hModule
0x180016854  call    cs:__imp_GetProcAddress
0x18001685b  nop     dword ptr [rax+rax+00h]
0x180016860  mov     [rdi+10h], rax
0x180016864  lea     rdx, aHttpextensionp; "HttpExtensionProc"
0x18001686b  mov     rcx, [r14]; hModule
0x18001686e  call    cs:__imp_GetProcAddress
0x180016875  nop     dword ptr [rax+rax+00h]
0x18001687a  mov     [rsi], rax
0x18001687d  lea     rdx, aTerminateexten; "TerminateExtension"
0x180016884  mov     rcx, [r14]; hModule
0x180016887  call    cs:__imp_GetProcAddress
0x18001688e  nop     dword ptr [rax+rax+00h]
0x180016893  mov     [rdi+20h], rax
0x180016897  mov     [rsp+168h+var_148], rsi
0x18001689c  cmp     qword ptr [rsi], 0
0x1800168a0  jz      short loc_180016915
0x1800168a2  cmp     qword ptr [rdi+10h], 0
0x1800168a7  jz      short loc_180016915
0x1800168a9  cmp     dword ptr [rdi], 1
0x1800168ac  jnz     short loc_1800168CE
0x1800168ae  xor     edx, edx; Val
0x1800168b0  mov     r8d, 104h; Size
0x1800168b6  lea     rcx, [rsp+168h+var_128]; void *
0x1800168bb  call    memset_0
0x1800168c0  lea     rcx, [rsp+168h+var_128]
0x1800168c5  mov     rax, [rdi+10h]
0x1800168c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168ce  mov     eax, 1
0x1800168d3  jmp     short loc_18001694A
0x1800168d5  lea     rax, WPP_GLOBAL_Control
0x1800168dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168e3  cmp     rcx, rax
0x1800168e6  jz      short loc_180016906
0x1800168e8  test    dword ptr [rcx+1Ch], 1000h
0x1800168ef  jz      short loc_180016906
0x1800168f1  mov     edx, 0Fh
0x1800168f6  lea     r8, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids
0x1800168fd  mov     rcx, [rcx+10h]
0x180016901  call    WPP_SF_
0x180016906  mov     rdi, [rsp+168h+var_140]
0x18001690b  mov     rsi, [rsp+168h+var_148]
0x180016910  mov     r14, [rsp+168h+var_138]
0x180016915  mov     qword ptr [rdi+10h], 0
0x18001691d  mov     qword ptr [rsi], 0
0x180016924  mov     qword ptr [rdi+20h], 0
0x18001692c  cmp     qword ptr [r14], 0
0x180016930  jz      short loc_180016941
0x180016932  mov     rcx, [r14]; hLibModule
0x180016935  call    cs:__imp_FreeLibrary
0x18001693c  nop     dword ptr [rax+rax+00h]
0x180016941  mov     qword ptr [r14], 0
0x180016948  xor     eax, eax
0x18001694a  mov     rcx, [rsp+168h+var_18]
0x180016952  xor     rcx, rsp; StackCookie
0x180016955  call    __security_check_cookie
0x18001695a  lea     r11, [rsp+168h+var_8]
0x180016962  mov     rsi, [r11+20h]
0x180016966  mov     rdi, [r11+28h]
0x18001696a  mov     rsp, r11
0x18001696d  pop     r14
0x18001696f  retn
```
