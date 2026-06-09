# wil_QueryFeatureState

- ea: `0x180039d18`
- end: `0x180039e7e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800361e8`

## callees

- `0x180004510`
- `0x180039d18`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039db4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039db4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039d9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039d9d`

## string_xrefs

- `0x180039d96`: `ntdll.dll`
- `0x180039daa`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int v8; // ebx
  BOOL v9; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v12; // r8d
  int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // ecx
  __int64 v17; // [rsp+30h] [rbp-38h] BYREF
  __int64 v18; // [rsp+38h] [rbp-30h] BYREF
  int v19; // [rsp+40h] [rbp-28h]

  if ( a5 )
    *a5 = 0;
  v17 = 0;
  v8 = 1;
  *a6 = 1;
  v9 = a3 == 0;
  v18 = 0;
  v19 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      v12 = -1073741511;
LABEL_8:
      v8 = 0;
      goto LABEL_9;
    }
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v17, &v18);
  v12 = v14;
  if ( v14 )
  {
    if ( v14 != 279 )
      goto LABEL_8;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v18) >> 7) & 1;
  }
  else
  {
    v15 = HIDWORD(v18);
    v16 = HIDWORD(v18);
    *(_DWORD *)(a1 + 12) = v19;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v16 >> 14;
    *(_DWORD *)a1 = (v16 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v15) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v15 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v15 >> 6) & 1;
  }
LABEL_9:
  if ( a5 )
    *a5 = v12 != -2147483614;
  return v8;
}

```

## disassembly

```asm
0x180039d18  mov     [rsp+arg_10], rbx
0x180039d1d  mov     [rsp+arg_18], rbp
0x180039d22  push    rsi
0x180039d23  push    rdi
0x180039d24  push    r14
0x180039d26  sub     rsp, 50h
0x180039d2a  mov     rax, cs:__security_cookie
0x180039d31  xor     rax, rsp
0x180039d34  mov     [rsp+68h+var_20], rax
0x180039d39  mov     rdi, [rsp+68h+arg_20]
0x180039d41  mov     r14d, edx
0x180039d44  mov     rax, [rsp+68h+arg_28]
0x180039d4c  mov     rsi, rcx
0x180039d4f  test    rdi, rdi
0x180039d52  jz      short loc_180039D5A
0x180039d54  mov     dword ptr [rdi], 0
0x180039d5a  xor     ebp, ebp
0x180039d5c  mov     [rsp+68h+var_38], 0
0x180039d65  test    r8d, r8d
0x180039d68  mov     ebx, 1
0x180039d6d  mov     [rax], ebx
0x180039d6f  setz    bpl
0x180039d73  xor     eax, eax
0x180039d75  mov     [rsp+68h+var_30], rax
0x180039d7a  mov     [rsp+68h+var_28], eax
0x180039d7e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180039d85  test    rax, rax
0x180039d88  jnz     short loc_180039E05
0x180039d8a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180039d91  test    rax, rax
0x180039d94  jnz     short loc_180039DAA
0x180039d96  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180039d9d  call    cs:__imp_GetModuleHandleW
0x180039da3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180039daa  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180039db1  mov     rcx, rax; hModule
0x180039db4  call    cs:__imp_GetProcAddress
0x180039dba  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180039dc1  test    rax, rax
0x180039dc4  jnz     short loc_180039E05
0x180039dc6  mov     r8d, 0C0000139h
0x180039dcc  xor     ebx, ebx
0x180039dce  test    rdi, rdi
0x180039dd1  jz      short loc_180039DE1
0x180039dd3  xor     ecx, ecx
0x180039dd5  cmp     r8d, 80000022h
0x180039ddc  setnz   cl
0x180039ddf  mov     [rdi], ecx
0x180039de1  mov     eax, ebx
0x180039de3  mov     rcx, [rsp+68h+var_20]
0x180039de8  xor     rcx, rsp; StackCookie
0x180039deb  call    __security_check_cookie
0x180039df0  lea     r11, [rsp+68h+var_18]
0x180039df5  mov     rbx, [r11+30h]
0x180039df9  mov     rbp, [r11+38h]
0x180039dfd  mov     rsp, r11
0x180039e00  pop     r14
0x180039e02  pop     rdi
0x180039e03  pop     rsi
0x180039e04  retn
0x180039e05  lea     r9, [rsp+68h+var_30]
0x180039e0a  mov     edx, ebp
0x180039e0c  lea     r8, [rsp+68h+var_38]
0x180039e11  mov     ecx, r14d
0x180039e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e19  mov     r8d, eax
0x180039e1c  test    eax, eax
0x180039e1e  jnz     short loc_180039E62
0x180039e20  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180039e24  mov     ecx, edx
0x180039e26  mov     eax, [rsp+68h+var_28]
0x180039e2a  mov     [rsi+0Ch], eax
0x180039e2d  mov     eax, edx
0x180039e2f  shr     eax, 0Eh
0x180039e32  shr     ecx, 4
0x180039e35  and     eax, 3
0x180039e38  and     ecx, 3
0x180039e3b  mov     [rsi+8], eax
0x180039e3e  mov     [rsi], ecx
0x180039e40  mov     eax, edx
0x180039e42  mov     ecx, edx
0x180039e44  shr     eax, 6
0x180039e47  shr     ecx, 8
0x180039e4a  and     eax, ebx
0x180039e4c  and     cl, 3Fh
0x180039e4f  shr     edx, 7
0x180039e52  and     edx, ebx
0x180039e54  mov     [rsi+4], cl
0x180039e57  mov     [rsi+10h], edx
0x180039e5a  mov     [rsi+14h], eax
0x180039e5d  jmp     loc_180039DCE
0x180039e62  cmp     eax, 117h
0x180039e67  jnz     loc_180039DCC
0x180039e6d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180039e71  shr     eax, 7
0x180039e74  and     eax, ebx
0x180039e76  mov     [rsi+10h], eax
0x180039e79  jmp     loc_180039DCE
```
