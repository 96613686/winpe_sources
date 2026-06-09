# wil_QueryFeatureState

- ea: `0x18000f16c`
- end: `0x18000f2d2`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000cee8`

## callees

- `0x1800032e0`
- `0x18000f16c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f1f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f1f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f208`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f208`

## string_xrefs

- `0x18000f1ea`: `ntdll.dll`
- `0x18000f1fe`: `RtlQueryFeatureConfiguration`

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
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x18000f16c  mov     [rsp+arg_10], rbx
0x18000f171  mov     [rsp+arg_18], rbp
0x18000f176  push    rsi
0x18000f177  push    rdi
0x18000f178  push    r14
0x18000f17a  sub     rsp, 50h
0x18000f17e  mov     rax, cs:__security_cookie
0x18000f185  xor     rax, rsp
0x18000f188  mov     [rsp+68h+var_20], rax
0x18000f18d  mov     rdi, [rsp+68h+arg_20]
0x18000f195  mov     r14d, edx
0x18000f198  mov     rax, [rsp+68h+arg_28]
0x18000f1a0  mov     rsi, rcx
0x18000f1a3  test    rdi, rdi
0x18000f1a6  jz      short loc_18000F1AE
0x18000f1a8  mov     dword ptr [rdi], 0
0x18000f1ae  xor     ebp, ebp
0x18000f1b0  mov     [rsp+68h+var_38], 0
0x18000f1b9  test    r8d, r8d
0x18000f1bc  mov     ebx, 1
0x18000f1c1  mov     [rax], ebx
0x18000f1c3  setz    bpl
0x18000f1c7  xor     eax, eax
0x18000f1c9  mov     [rsp+68h+var_30], rax
0x18000f1ce  mov     [rsp+68h+var_28], eax
0x18000f1d2  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000f1d9  test    rax, rax
0x18000f1dc  jnz     short loc_18000F259
0x18000f1de  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f1e5  test    rax, rax
0x18000f1e8  jnz     short loc_18000F1FE
0x18000f1ea  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000f1f1  call    cs:__imp_GetModuleHandleW
0x18000f1f7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f1fe  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000f205  mov     rcx, rax; hModule
0x18000f208  call    cs:__imp_GetProcAddress
0x18000f20e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000f215  test    rax, rax
0x18000f218  jnz     short loc_18000F259
0x18000f21a  mov     r8d, 0C0000139h
0x18000f220  xor     ebx, ebx
0x18000f222  test    rdi, rdi
0x18000f225  jz      short loc_18000F235
0x18000f227  xor     ecx, ecx
0x18000f229  cmp     r8d, 80000022h
0x18000f230  setnz   cl
0x18000f233  mov     [rdi], ecx
0x18000f235  mov     eax, ebx
0x18000f237  mov     rcx, [rsp+68h+var_20]
0x18000f23c  xor     rcx, rsp; StackCookie
0x18000f23f  call    __security_check_cookie
0x18000f244  lea     r11, [rsp+68h+var_18]
0x18000f249  mov     rbx, [r11+30h]
0x18000f24d  mov     rbp, [r11+38h]
0x18000f251  mov     rsp, r11
0x18000f254  pop     r14
0x18000f256  pop     rdi
0x18000f257  pop     rsi
0x18000f258  retn
0x18000f259  lea     r9, [rsp+68h+var_30]
0x18000f25e  mov     edx, ebp
0x18000f260  lea     r8, [rsp+68h+var_38]
0x18000f265  mov     ecx, r14d
0x18000f268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f26d  mov     r8d, eax
0x18000f270  test    eax, eax
0x18000f272  jnz     short loc_18000F2B6
0x18000f274  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000f278  mov     ecx, edx
0x18000f27a  mov     eax, [rsp+68h+var_28]
0x18000f27e  mov     [rsi+0Ch], eax
0x18000f281  mov     eax, edx
0x18000f283  shr     eax, 0Eh
0x18000f286  shr     ecx, 4
0x18000f289  and     eax, 3
0x18000f28c  and     ecx, 3
0x18000f28f  mov     [rsi+8], eax
0x18000f292  mov     [rsi], ecx
0x18000f294  mov     eax, edx
0x18000f296  mov     ecx, edx
0x18000f298  shr     eax, 6
0x18000f29b  shr     ecx, 8
0x18000f29e  and     eax, ebx
0x18000f2a0  and     cl, 3Fh
0x18000f2a3  shr     edx, 7
0x18000f2a6  and     edx, ebx
0x18000f2a8  mov     [rsi+4], cl
0x18000f2ab  mov     [rsi+10h], edx
0x18000f2ae  mov     [rsi+14h], eax
0x18000f2b1  jmp     loc_18000F222
0x18000f2b6  cmp     eax, 117h
0x18000f2bb  jnz     loc_18000F220
0x18000f2c1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000f2c5  shr     eax, 7
0x18000f2c8  and     eax, ebx
0x18000f2ca  mov     [rsi+10h], eax
0x18000f2cd  jmp     loc_18000F222
```
