# wil_QueryFeatureState

- ea: `0x18000e1e8`
- end: `0x18000e34e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180008e50`

## callees

- `0x1800020e0`
- `0x18000e1e8`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e26d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e26d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e284`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e284`

## string_xrefs

- `0x18000e266`: `ntdll.dll`
- `0x18000e27a`: `RtlQueryFeatureConfiguration`

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
0x18000e1e8  mov     [rsp+arg_10], rbx
0x18000e1ed  mov     [rsp+arg_18], rbp
0x18000e1f2  push    rsi
0x18000e1f3  push    rdi
0x18000e1f4  push    r14
0x18000e1f6  sub     rsp, 50h
0x18000e1fa  mov     rax, cs:__security_cookie
0x18000e201  xor     rax, rsp
0x18000e204  mov     [rsp+68h+var_20], rax
0x18000e209  mov     rdi, [rsp+68h+arg_20]
0x18000e211  mov     r14d, edx
0x18000e214  mov     rax, [rsp+68h+arg_28]
0x18000e21c  mov     rsi, rcx
0x18000e21f  test    rdi, rdi
0x18000e222  jz      short loc_18000E22A
0x18000e224  mov     dword ptr [rdi], 0
0x18000e22a  xor     ebp, ebp
0x18000e22c  mov     [rsp+68h+var_38], 0
0x18000e235  test    r8d, r8d
0x18000e238  mov     ebx, 1
0x18000e23d  mov     [rax], ebx
0x18000e23f  setz    bpl
0x18000e243  xor     eax, eax
0x18000e245  mov     [rsp+68h+var_30], rax
0x18000e24a  mov     [rsp+68h+var_28], eax
0x18000e24e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000e255  test    rax, rax
0x18000e258  jnz     short loc_18000E2D5
0x18000e25a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e261  test    rax, rax
0x18000e264  jnz     short loc_18000E27A
0x18000e266  lea     rcx, ModuleName; "ntdll.dll"
0x18000e26d  call    cs:__imp_GetModuleHandleW
0x18000e273  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e27a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000e281  mov     rcx, rax; hModule
0x18000e284  call    cs:__imp_GetProcAddress
0x18000e28a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000e291  test    rax, rax
0x18000e294  jnz     short loc_18000E2D5
0x18000e296  mov     r8d, 0C0000139h
0x18000e29c  xor     ebx, ebx
0x18000e29e  test    rdi, rdi
0x18000e2a1  jz      short loc_18000E2B1
0x18000e2a3  xor     ecx, ecx
0x18000e2a5  cmp     r8d, 80000022h
0x18000e2ac  setnz   cl
0x18000e2af  mov     [rdi], ecx
0x18000e2b1  mov     eax, ebx
0x18000e2b3  mov     rcx, [rsp+68h+var_20]
0x18000e2b8  xor     rcx, rsp; StackCookie
0x18000e2bb  call    __security_check_cookie
0x18000e2c0  lea     r11, [rsp+68h+var_18]
0x18000e2c5  mov     rbx, [r11+30h]
0x18000e2c9  mov     rbp, [r11+38h]
0x18000e2cd  mov     rsp, r11
0x18000e2d0  pop     r14
0x18000e2d2  pop     rdi
0x18000e2d3  pop     rsi
0x18000e2d4  retn
0x18000e2d5  lea     r9, [rsp+68h+var_30]
0x18000e2da  mov     edx, ebp
0x18000e2dc  lea     r8, [rsp+68h+var_38]
0x18000e2e1  mov     ecx, r14d
0x18000e2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2e9  mov     r8d, eax
0x18000e2ec  test    eax, eax
0x18000e2ee  jnz     short loc_18000E332
0x18000e2f0  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000e2f4  mov     ecx, edx
0x18000e2f6  mov     eax, [rsp+68h+var_28]
0x18000e2fa  mov     [rsi+0Ch], eax
0x18000e2fd  mov     eax, edx
0x18000e2ff  shr     eax, 0Eh
0x18000e302  shr     ecx, 4
0x18000e305  and     eax, 3
0x18000e308  and     ecx, 3
0x18000e30b  mov     [rsi+8], eax
0x18000e30e  mov     [rsi], ecx
0x18000e310  mov     eax, edx
0x18000e312  mov     ecx, edx
0x18000e314  shr     eax, 6
0x18000e317  shr     ecx, 8
0x18000e31a  and     eax, ebx
0x18000e31c  and     cl, 3Fh
0x18000e31f  shr     edx, 7
0x18000e322  and     edx, ebx
0x18000e324  mov     [rsi+4], cl
0x18000e327  mov     [rsi+10h], edx
0x18000e32a  mov     [rsi+14h], eax
0x18000e32d  jmp     loc_18000E29E
0x18000e332  cmp     eax, 117h
0x18000e337  jnz     loc_18000E29C
0x18000e33d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000e341  shr     eax, 7
0x18000e344  and     eax, ebx
0x18000e346  mov     [rsi+10h], eax
0x18000e349  jmp     loc_18000E29E
```
