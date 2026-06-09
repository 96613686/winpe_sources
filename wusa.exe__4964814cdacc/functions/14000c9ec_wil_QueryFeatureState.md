# wil_QueryFeatureState

- ea: `0x14000c9ec`
- end: `0x14000cb52`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400086fc`

## callees

- `0x14000c9ec`
- `0x140014910`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000ca88`
- `KERNEL32!GetProcAddress` at `0x14000ca88`
- `KERNEL32!GetModuleHandleW` at `0x14000ca71`
- `KERNEL32!GetModuleHandleW` at `0x14000ca71`

## string_xrefs

- `0x14000ca6a`: `ntdll.dll`
- `0x14000ca7e`: `RtlQueryFeatureConfiguration`

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
0x14000c9ec  mov     [rsp+arg_10], rbx
0x14000c9f1  mov     [rsp+arg_18], rbp
0x14000c9f6  push    rsi
0x14000c9f7  push    rdi
0x14000c9f8  push    r14
0x14000c9fa  sub     rsp, 50h
0x14000c9fe  mov     rax, cs:__security_cookie
0x14000ca05  xor     rax, rsp
0x14000ca08  mov     [rsp+68h+var_20], rax
0x14000ca0d  mov     rdi, [rsp+68h+arg_20]
0x14000ca15  mov     r14d, edx
0x14000ca18  mov     rax, [rsp+68h+arg_28]
0x14000ca20  mov     rsi, rcx
0x14000ca23  test    rdi, rdi
0x14000ca26  jz      short loc_14000CA2E
0x14000ca28  mov     dword ptr [rdi], 0
0x14000ca2e  xor     ebp, ebp
0x14000ca30  mov     [rsp+68h+var_38], 0
0x14000ca39  test    r8d, r8d
0x14000ca3c  mov     ebx, 1
0x14000ca41  mov     [rax], ebx
0x14000ca43  setz    bpl
0x14000ca47  xor     eax, eax
0x14000ca49  mov     [rsp+68h+var_30], rax
0x14000ca4e  mov     [rsp+68h+var_28], eax
0x14000ca52  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000ca59  test    rax, rax
0x14000ca5c  jnz     short loc_14000CAD9
0x14000ca5e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ca65  test    rax, rax
0x14000ca68  jnz     short loc_14000CA7E
0x14000ca6a  lea     rcx, ModuleName; "ntdll.dll"
0x14000ca71  call    cs:__imp_GetModuleHandleW
0x14000ca77  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ca7e  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000ca85  mov     rcx, rax; hModule
0x14000ca88  call    cs:__imp_GetProcAddress
0x14000ca8e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000ca95  test    rax, rax
0x14000ca98  jnz     short loc_14000CAD9
0x14000ca9a  mov     r8d, 0C0000139h
0x14000caa0  xor     ebx, ebx
0x14000caa2  test    rdi, rdi
0x14000caa5  jz      short loc_14000CAB5
0x14000caa7  xor     ecx, ecx
0x14000caa9  cmp     r8d, 80000022h
0x14000cab0  setnz   cl
0x14000cab3  mov     [rdi], ecx
0x14000cab5  mov     eax, ebx
0x14000cab7  mov     rcx, [rsp+68h+var_20]
0x14000cabc  xor     rcx, rsp; StackCookie
0x14000cabf  call    __security_check_cookie
0x14000cac4  lea     r11, [rsp+68h+var_18]
0x14000cac9  mov     rbx, [r11+30h]
0x14000cacd  mov     rbp, [r11+38h]
0x14000cad1  mov     rsp, r11
0x14000cad4  pop     r14
0x14000cad6  pop     rdi
0x14000cad7  pop     rsi
0x14000cad8  retn
0x14000cad9  lea     r9, [rsp+68h+var_30]
0x14000cade  mov     edx, ebp
0x14000cae0  lea     r8, [rsp+68h+var_38]
0x14000cae5  mov     ecx, r14d
0x14000cae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000caed  mov     r8d, eax
0x14000caf0  test    eax, eax
0x14000caf2  jnz     short loc_14000CB36
0x14000caf4  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000caf8  mov     ecx, edx
0x14000cafa  mov     eax, [rsp+68h+var_28]
0x14000cafe  mov     [rsi+0Ch], eax
0x14000cb01  mov     eax, edx
0x14000cb03  shr     eax, 0Eh
0x14000cb06  shr     ecx, 4
0x14000cb09  and     eax, 3
0x14000cb0c  and     ecx, 3
0x14000cb0f  mov     [rsi+8], eax
0x14000cb12  mov     [rsi], ecx
0x14000cb14  mov     eax, edx
0x14000cb16  mov     ecx, edx
0x14000cb18  shr     eax, 6
0x14000cb1b  shr     ecx, 8
0x14000cb1e  and     eax, ebx
0x14000cb20  and     cl, 3Fh
0x14000cb23  shr     edx, 7
0x14000cb26  and     edx, ebx
0x14000cb28  mov     [rsi+4], cl
0x14000cb2b  mov     [rsi+10h], edx
0x14000cb2e  mov     [rsi+14h], eax
0x14000cb31  jmp     loc_14000CAA2
0x14000cb36  cmp     eax, 117h
0x14000cb3b  jnz     loc_14000CAA0
0x14000cb41  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000cb45  shr     eax, 7
0x14000cb48  and     eax, ebx
0x14000cb4a  mov     [rsi+10h], eax
0x14000cb4d  jmp     loc_14000CAA2
```
