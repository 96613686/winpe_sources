# wil_QueryFeatureState

- ea: `0x18000a838`
- end: `0x18000a99e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180006e10`

## callees

- `0x180002590`
- `0x18000a838`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8d4`

## string_xrefs

- `0x18000a8b6`: `ntdll.dll`
- `0x18000a8ca`: `RtlQueryFeatureConfiguration`

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
0x18000a838  mov     [rsp+arg_10], rbx
0x18000a83d  mov     [rsp+arg_18], rbp
0x18000a842  push    rsi
0x18000a843  push    rdi
0x18000a844  push    r14
0x18000a846  sub     rsp, 50h
0x18000a84a  mov     rax, cs:__security_cookie
0x18000a851  xor     rax, rsp
0x18000a854  mov     [rsp+68h+var_20], rax
0x18000a859  mov     rdi, [rsp+68h+arg_20]
0x18000a861  mov     r14d, edx
0x18000a864  mov     rax, [rsp+68h+arg_28]
0x18000a86c  mov     rsi, rcx
0x18000a86f  test    rdi, rdi
0x18000a872  jz      short loc_18000A87A
0x18000a874  mov     dword ptr [rdi], 0
0x18000a87a  xor     ebp, ebp
0x18000a87c  mov     [rsp+68h+var_38], 0
0x18000a885  test    r8d, r8d
0x18000a888  mov     ebx, 1
0x18000a88d  mov     [rax], ebx
0x18000a88f  setz    bpl
0x18000a893  xor     eax, eax
0x18000a895  mov     [rsp+68h+var_30], rax
0x18000a89a  mov     [rsp+68h+var_28], eax
0x18000a89e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000a8a5  test    rax, rax
0x18000a8a8  jnz     short loc_18000A925
0x18000a8aa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a8b1  test    rax, rax
0x18000a8b4  jnz     short loc_18000A8CA
0x18000a8b6  lea     rcx, ModuleName; "ntdll.dll"
0x18000a8bd  call    cs:__imp_GetModuleHandleW
0x18000a8c3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a8ca  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000a8d1  mov     rcx, rax; hModule
0x18000a8d4  call    cs:__imp_GetProcAddress
0x18000a8da  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000a8e1  test    rax, rax
0x18000a8e4  jnz     short loc_18000A925
0x18000a8e6  mov     r8d, 0C0000139h
0x18000a8ec  xor     ebx, ebx
0x18000a8ee  test    rdi, rdi
0x18000a8f1  jz      short loc_18000A901
0x18000a8f3  xor     ecx, ecx
0x18000a8f5  cmp     r8d, 80000022h
0x18000a8fc  setnz   cl
0x18000a8ff  mov     [rdi], ecx
0x18000a901  mov     eax, ebx
0x18000a903  mov     rcx, [rsp+68h+var_20]
0x18000a908  xor     rcx, rsp; StackCookie
0x18000a90b  call    __security_check_cookie
0x18000a910  lea     r11, [rsp+68h+var_18]
0x18000a915  mov     rbx, [r11+30h]
0x18000a919  mov     rbp, [r11+38h]
0x18000a91d  mov     rsp, r11
0x18000a920  pop     r14
0x18000a922  pop     rdi
0x18000a923  pop     rsi
0x18000a924  retn
0x18000a925  lea     r9, [rsp+68h+var_30]
0x18000a92a  mov     edx, ebp
0x18000a92c  lea     r8, [rsp+68h+var_38]
0x18000a931  mov     ecx, r14d
0x18000a934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a939  mov     r8d, eax
0x18000a93c  test    eax, eax
0x18000a93e  jnz     short loc_18000A982
0x18000a940  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000a944  mov     ecx, edx
0x18000a946  mov     eax, [rsp+68h+var_28]
0x18000a94a  mov     [rsi+0Ch], eax
0x18000a94d  mov     eax, edx
0x18000a94f  shr     eax, 0Eh
0x18000a952  shr     ecx, 4
0x18000a955  and     eax, 3
0x18000a958  and     ecx, 3
0x18000a95b  mov     [rsi+8], eax
0x18000a95e  mov     [rsi], ecx
0x18000a960  mov     eax, edx
0x18000a962  mov     ecx, edx
0x18000a964  shr     eax, 6
0x18000a967  shr     ecx, 8
0x18000a96a  and     eax, ebx
0x18000a96c  and     cl, 3Fh
0x18000a96f  shr     edx, 7
0x18000a972  and     edx, ebx
0x18000a974  mov     [rsi+4], cl
0x18000a977  mov     [rsi+10h], edx
0x18000a97a  mov     [rsi+14h], eax
0x18000a97d  jmp     loc_18000A8EE
0x18000a982  cmp     eax, 117h
0x18000a987  jnz     loc_18000A8EC
0x18000a98d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000a991  shr     eax, 7
0x18000a994  and     eax, ebx
0x18000a996  mov     [rsi+10h], eax
0x18000a999  jmp     loc_18000A8EE
```
