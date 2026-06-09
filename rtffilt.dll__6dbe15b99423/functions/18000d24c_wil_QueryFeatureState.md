# wil_QueryFeatureState

- ea: `0x18000d24c`
- end: `0x18000d3b2`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007684`

## callees

- `0x180001e40`
- `0x18000d24c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d2d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d2d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2e8`

## string_xrefs

- `0x18000d2ca`: `ntdll.dll`
- `0x18000d2de`: `RtlQueryFeatureConfiguration`

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
0x18000d24c  mov     [rsp+arg_10], rbx
0x18000d251  mov     [rsp+arg_18], rbp
0x18000d256  push    rsi
0x18000d257  push    rdi
0x18000d258  push    r14
0x18000d25a  sub     rsp, 50h
0x18000d25e  mov     rax, cs:__security_cookie
0x18000d265  xor     rax, rsp
0x18000d268  mov     [rsp+68h+var_20], rax
0x18000d26d  mov     rdi, [rsp+68h+arg_20]
0x18000d275  mov     r14d, edx
0x18000d278  mov     rax, [rsp+68h+arg_28]
0x18000d280  mov     rsi, rcx
0x18000d283  test    rdi, rdi
0x18000d286  jz      short loc_18000D28E
0x18000d288  mov     dword ptr [rdi], 0
0x18000d28e  xor     ebp, ebp
0x18000d290  mov     [rsp+68h+var_38], 0
0x18000d299  test    r8d, r8d
0x18000d29c  mov     ebx, 1
0x18000d2a1  mov     [rax], ebx
0x18000d2a3  setz    bpl
0x18000d2a7  xor     eax, eax
0x18000d2a9  mov     [rsp+68h+var_30], rax
0x18000d2ae  mov     [rsp+68h+var_28], eax
0x18000d2b2  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000d2b9  test    rax, rax
0x18000d2bc  jnz     short loc_18000D339
0x18000d2be  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d2c5  test    rax, rax
0x18000d2c8  jnz     short loc_18000D2DE
0x18000d2ca  lea     rcx, ModuleName; "ntdll.dll"
0x18000d2d1  call    cs:__imp_GetModuleHandleW
0x18000d2d7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d2de  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000d2e5  mov     rcx, rax; hModule
0x18000d2e8  call    cs:__imp_GetProcAddress
0x18000d2ee  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000d2f5  test    rax, rax
0x18000d2f8  jnz     short loc_18000D339
0x18000d2fa  mov     r8d, 0C0000139h
0x18000d300  xor     ebx, ebx
0x18000d302  test    rdi, rdi
0x18000d305  jz      short loc_18000D315
0x18000d307  xor     ecx, ecx
0x18000d309  cmp     r8d, 80000022h
0x18000d310  setnz   cl
0x18000d313  mov     [rdi], ecx
0x18000d315  mov     eax, ebx
0x18000d317  mov     rcx, [rsp+68h+var_20]
0x18000d31c  xor     rcx, rsp; StackCookie
0x18000d31f  call    __security_check_cookie
0x18000d324  lea     r11, [rsp+68h+var_18]
0x18000d329  mov     rbx, [r11+30h]
0x18000d32d  mov     rbp, [r11+38h]
0x18000d331  mov     rsp, r11
0x18000d334  pop     r14
0x18000d336  pop     rdi
0x18000d337  pop     rsi
0x18000d338  retn
0x18000d339  lea     r9, [rsp+68h+var_30]
0x18000d33e  mov     edx, ebp
0x18000d340  lea     r8, [rsp+68h+var_38]
0x18000d345  mov     ecx, r14d
0x18000d348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d34d  mov     r8d, eax
0x18000d350  test    eax, eax
0x18000d352  jnz     short loc_18000D396
0x18000d354  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000d358  mov     ecx, edx
0x18000d35a  mov     eax, [rsp+68h+var_28]
0x18000d35e  mov     [rsi+0Ch], eax
0x18000d361  mov     eax, edx
0x18000d363  shr     eax, 0Eh
0x18000d366  shr     ecx, 4
0x18000d369  and     eax, 3
0x18000d36c  and     ecx, 3
0x18000d36f  mov     [rsi+8], eax
0x18000d372  mov     [rsi], ecx
0x18000d374  mov     eax, edx
0x18000d376  mov     ecx, edx
0x18000d378  shr     eax, 6
0x18000d37b  shr     ecx, 8
0x18000d37e  and     eax, ebx
0x18000d380  and     cl, 3Fh
0x18000d383  shr     edx, 7
0x18000d386  and     edx, ebx
0x18000d388  mov     [rsi+4], cl
0x18000d38b  mov     [rsi+10h], edx
0x18000d38e  mov     [rsi+14h], eax
0x18000d391  jmp     loc_18000D302
0x18000d396  cmp     eax, 117h
0x18000d39b  jnz     loc_18000D300
0x18000d3a1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000d3a5  shr     eax, 7
0x18000d3a8  and     eax, ebx
0x18000d3aa  mov     [rsi+10h], eax
0x18000d3ad  jmp     loc_18000D302
```
