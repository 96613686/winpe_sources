# wil_QueryFeatureState

- ea: `0x18001cfa4`
- end: `0x18001d10a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001af30`

## callees

- `0x18001cfa4`
- `0x18001d370`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d040`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d040`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d029`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d029`

## string_xrefs

- `0x18001d022`: `ntdll.dll`
- `0x18001d036`: `RtlQueryFeatureConfiguration`

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
0x18001cfa4  mov     [rsp+arg_10], rbx
0x18001cfa9  mov     [rsp+arg_18], rbp
0x18001cfae  push    rsi
0x18001cfaf  push    rdi
0x18001cfb0  push    r14
0x18001cfb2  sub     rsp, 50h
0x18001cfb6  mov     rax, cs:__security_cookie
0x18001cfbd  xor     rax, rsp
0x18001cfc0  mov     [rsp+68h+var_20], rax
0x18001cfc5  mov     rdi, [rsp+68h+arg_20]
0x18001cfcd  mov     r14d, edx
0x18001cfd0  mov     rax, [rsp+68h+arg_28]
0x18001cfd8  mov     rsi, rcx
0x18001cfdb  test    rdi, rdi
0x18001cfde  jz      short loc_18001CFE6
0x18001cfe0  mov     dword ptr [rdi], 0
0x18001cfe6  xor     ebp, ebp
0x18001cfe8  mov     [rsp+68h+var_38], 0
0x18001cff1  test    r8d, r8d
0x18001cff4  mov     ebx, 1
0x18001cff9  mov     [rax], ebx
0x18001cffb  setz    bpl
0x18001cfff  xor     eax, eax
0x18001d001  mov     [rsp+68h+var_30], rax
0x18001d006  mov     [rsp+68h+var_28], eax
0x18001d00a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001d011  test    rax, rax
0x18001d014  jnz     short loc_18001D091
0x18001d016  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d01d  test    rax, rax
0x18001d020  jnz     short loc_18001D036
0x18001d022  lea     rcx, ModuleName; "ntdll.dll"
0x18001d029  call    cs:__imp_GetModuleHandleW
0x18001d02f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d036  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001d03d  mov     rcx, rax; hModule
0x18001d040  call    cs:__imp_GetProcAddress
0x18001d046  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001d04d  test    rax, rax
0x18001d050  jnz     short loc_18001D091
0x18001d052  mov     r8d, 0C0000139h
0x18001d058  xor     ebx, ebx
0x18001d05a  test    rdi, rdi
0x18001d05d  jz      short loc_18001D06D
0x18001d05f  xor     ecx, ecx
0x18001d061  cmp     r8d, 80000022h
0x18001d068  setnz   cl
0x18001d06b  mov     [rdi], ecx
0x18001d06d  mov     eax, ebx
0x18001d06f  mov     rcx, [rsp+68h+var_20]
0x18001d074  xor     rcx, rsp; StackCookie
0x18001d077  call    __security_check_cookie
0x18001d07c  lea     r11, [rsp+68h+var_18]
0x18001d081  mov     rbx, [r11+30h]
0x18001d085  mov     rbp, [r11+38h]
0x18001d089  mov     rsp, r11
0x18001d08c  pop     r14
0x18001d08e  pop     rdi
0x18001d08f  pop     rsi
0x18001d090  retn
0x18001d091  lea     r9, [rsp+68h+var_30]
0x18001d096  mov     edx, ebp
0x18001d098  lea     r8, [rsp+68h+var_38]
0x18001d09d  mov     ecx, r14d
0x18001d0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0a5  mov     r8d, eax
0x18001d0a8  test    eax, eax
0x18001d0aa  jnz     short loc_18001D0EE
0x18001d0ac  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001d0b0  mov     ecx, edx
0x18001d0b2  mov     eax, [rsp+68h+var_28]
0x18001d0b6  mov     [rsi+0Ch], eax
0x18001d0b9  mov     eax, edx
0x18001d0bb  shr     eax, 0Eh
0x18001d0be  shr     ecx, 4
0x18001d0c1  and     eax, 3
0x18001d0c4  and     ecx, 3
0x18001d0c7  mov     [rsi+8], eax
0x18001d0ca  mov     [rsi], ecx
0x18001d0cc  mov     eax, edx
0x18001d0ce  mov     ecx, edx
0x18001d0d0  shr     eax, 6
0x18001d0d3  shr     ecx, 8
0x18001d0d6  and     eax, ebx
0x18001d0d8  and     cl, 3Fh
0x18001d0db  shr     edx, 7
0x18001d0de  and     edx, ebx
0x18001d0e0  mov     [rsi+4], cl
0x18001d0e3  mov     [rsi+10h], edx
0x18001d0e6  mov     [rsi+14h], eax
0x18001d0e9  jmp     loc_18001D05A
0x18001d0ee  cmp     eax, 117h
0x18001d0f3  jnz     loc_18001D058
0x18001d0f9  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18001d0fd  shr     eax, 7
0x18001d100  and     eax, ebx
0x18001d102  mov     [rsi+10h], eax
0x18001d105  jmp     loc_18001D05A
```
