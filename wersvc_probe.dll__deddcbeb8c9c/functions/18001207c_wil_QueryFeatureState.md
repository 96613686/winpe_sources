# wil_QueryFeatureState

- ea: `0x18001207c`
- end: `0x1800121e2`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000abb8`

## callees

- `0x1800029d0`
- `0x18001207c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012101`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012101`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012118`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012118`

## string_xrefs

- `0x1800120fa`: `ntdll.dll`
- `0x18001210e`: `RtlQueryFeatureConfiguration`

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
0x18001207c  mov     [rsp+arg_10], rbx
0x180012081  mov     [rsp+arg_18], rbp
0x180012086  push    rsi
0x180012087  push    rdi
0x180012088  push    r14
0x18001208a  sub     rsp, 50h
0x18001208e  mov     rax, cs:__security_cookie
0x180012095  xor     rax, rsp
0x180012098  mov     [rsp+68h+var_20], rax
0x18001209d  mov     rdi, [rsp+68h+arg_20]
0x1800120a5  mov     r14d, edx
0x1800120a8  mov     rax, [rsp+68h+arg_28]
0x1800120b0  mov     rsi, rcx
0x1800120b3  test    rdi, rdi
0x1800120b6  jz      short loc_1800120BE
0x1800120b8  mov     dword ptr [rdi], 0
0x1800120be  xor     ebp, ebp
0x1800120c0  mov     [rsp+68h+var_38], 0
0x1800120c9  test    r8d, r8d
0x1800120cc  mov     ebx, 1
0x1800120d1  mov     [rax], ebx
0x1800120d3  setz    bpl
0x1800120d7  xor     eax, eax
0x1800120d9  mov     [rsp+68h+var_30], rax
0x1800120de  mov     [rsp+68h+var_28], eax
0x1800120e2  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800120e9  test    rax, rax
0x1800120ec  jnz     short loc_180012169
0x1800120ee  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800120f5  test    rax, rax
0x1800120f8  jnz     short loc_18001210E
0x1800120fa  lea     rcx, Src; "ntdll.dll"
0x180012101  call    cs:__imp_GetModuleHandleW
0x180012107  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001210e  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180012115  mov     rcx, rax; hModule
0x180012118  call    cs:__imp_GetProcAddress
0x18001211e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180012125  test    rax, rax
0x180012128  jnz     short loc_180012169
0x18001212a  mov     r8d, 0C0000139h
0x180012130  xor     ebx, ebx
0x180012132  test    rdi, rdi
0x180012135  jz      short loc_180012145
0x180012137  xor     ecx, ecx
0x180012139  cmp     r8d, 80000022h
0x180012140  setnz   cl
0x180012143  mov     [rdi], ecx
0x180012145  mov     eax, ebx
0x180012147  mov     rcx, [rsp+68h+var_20]
0x18001214c  xor     rcx, rsp; StackCookie
0x18001214f  call    __security_check_cookie
0x180012154  lea     r11, [rsp+68h+var_18]
0x180012159  mov     rbx, [r11+30h]
0x18001215d  mov     rbp, [r11+38h]
0x180012161  mov     rsp, r11
0x180012164  pop     r14
0x180012166  pop     rdi
0x180012167  pop     rsi
0x180012168  retn
0x180012169  lea     r9, [rsp+68h+var_30]
0x18001216e  mov     edx, ebp
0x180012170  lea     r8, [rsp+68h+var_38]
0x180012175  mov     ecx, r14d
0x180012178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001217d  mov     r8d, eax
0x180012180  test    eax, eax
0x180012182  jnz     short loc_1800121C6
0x180012184  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180012188  mov     ecx, edx
0x18001218a  mov     eax, [rsp+68h+var_28]
0x18001218e  mov     [rsi+0Ch], eax
0x180012191  mov     eax, edx
0x180012193  shr     eax, 0Eh
0x180012196  shr     ecx, 4
0x180012199  and     eax, 3
0x18001219c  and     ecx, 3
0x18001219f  mov     [rsi+8], eax
0x1800121a2  mov     [rsi], ecx
0x1800121a4  mov     eax, edx
0x1800121a6  mov     ecx, edx
0x1800121a8  shr     eax, 6
0x1800121ab  shr     ecx, 8
0x1800121ae  and     eax, ebx
0x1800121b0  and     cl, 3Fh
0x1800121b3  shr     edx, 7
0x1800121b6  and     edx, ebx
0x1800121b8  mov     [rsi+4], cl
0x1800121bb  mov     [rsi+10h], edx
0x1800121be  mov     [rsi+14h], eax
0x1800121c1  jmp     loc_180012132
0x1800121c6  cmp     eax, 117h
0x1800121cb  jnz     loc_180012130
0x1800121d1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800121d5  shr     eax, 7
0x1800121d8  and     eax, ebx
0x1800121da  mov     [rsi+10h], eax
0x1800121dd  jmp     loc_180012132
```
