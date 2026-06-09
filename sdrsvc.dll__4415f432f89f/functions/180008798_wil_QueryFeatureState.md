# wil_QueryFeatureState

- ea: `0x180008798`
- end: `0x1800088fe`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005640`

## callees

- `0x180008798`
- `0x180021740`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000881d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000881d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008834`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008834`

## string_xrefs

- `0x180008816`: `ntdll.dll`
- `0x18000882a`: `RtlQueryFeatureConfiguration`

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
0x180008798  mov     [rsp+arg_10], rbx
0x18000879d  mov     [rsp+arg_18], rbp
0x1800087a2  push    rsi
0x1800087a3  push    rdi
0x1800087a4  push    r14
0x1800087a6  sub     rsp, 50h
0x1800087aa  mov     rax, cs:__security_cookie
0x1800087b1  xor     rax, rsp
0x1800087b4  mov     [rsp+68h+var_20], rax
0x1800087b9  mov     rdi, [rsp+68h+arg_20]
0x1800087c1  mov     r14d, edx
0x1800087c4  mov     rax, [rsp+68h+arg_28]
0x1800087cc  mov     rsi, rcx
0x1800087cf  test    rdi, rdi
0x1800087d2  jz      short loc_1800087DA
0x1800087d4  mov     dword ptr [rdi], 0
0x1800087da  xor     ebp, ebp
0x1800087dc  mov     [rsp+68h+var_38], 0
0x1800087e5  test    r8d, r8d
0x1800087e8  mov     ebx, 1
0x1800087ed  mov     [rax], ebx
0x1800087ef  setz    bpl
0x1800087f3  xor     eax, eax
0x1800087f5  mov     [rsp+68h+var_30], rax
0x1800087fa  mov     [rsp+68h+var_28], eax
0x1800087fe  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180008805  test    rax, rax
0x180008808  jnz     short loc_180008885
0x18000880a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008811  test    rax, rax
0x180008814  jnz     short loc_18000882A
0x180008816  lea     rcx, ModuleName; "ntdll.dll"
0x18000881d  call    cs:__imp_GetModuleHandleW
0x180008823  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000882a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180008831  mov     rcx, rax; hModule
0x180008834  call    cs:__imp_GetProcAddress
0x18000883a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180008841  test    rax, rax
0x180008844  jnz     short loc_180008885
0x180008846  mov     r8d, 0C0000139h
0x18000884c  xor     ebx, ebx
0x18000884e  test    rdi, rdi
0x180008851  jz      short loc_180008861
0x180008853  xor     ecx, ecx
0x180008855  cmp     r8d, 80000022h
0x18000885c  setnz   cl
0x18000885f  mov     [rdi], ecx
0x180008861  mov     eax, ebx
0x180008863  mov     rcx, [rsp+68h+var_20]
0x180008868  xor     rcx, rsp; StackCookie
0x18000886b  call    __security_check_cookie
0x180008870  lea     r11, [rsp+68h+var_18]
0x180008875  mov     rbx, [r11+30h]
0x180008879  mov     rbp, [r11+38h]
0x18000887d  mov     rsp, r11
0x180008880  pop     r14
0x180008882  pop     rdi
0x180008883  pop     rsi
0x180008884  retn
0x180008885  lea     r9, [rsp+68h+var_30]
0x18000888a  mov     edx, ebp
0x18000888c  lea     r8, [rsp+68h+var_38]
0x180008891  mov     ecx, r14d
0x180008894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008899  mov     r8d, eax
0x18000889c  test    eax, eax
0x18000889e  jnz     short loc_1800088E2
0x1800088a0  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800088a4  mov     ecx, edx
0x1800088a6  mov     eax, [rsp+68h+var_28]
0x1800088aa  mov     [rsi+0Ch], eax
0x1800088ad  mov     eax, edx
0x1800088af  shr     eax, 0Eh
0x1800088b2  shr     ecx, 4
0x1800088b5  and     eax, 3
0x1800088b8  and     ecx, 3
0x1800088bb  mov     [rsi+8], eax
0x1800088be  mov     [rsi], ecx
0x1800088c0  mov     eax, edx
0x1800088c2  mov     ecx, edx
0x1800088c4  shr     eax, 6
0x1800088c7  shr     ecx, 8
0x1800088ca  and     eax, ebx
0x1800088cc  and     cl, 3Fh
0x1800088cf  shr     edx, 7
0x1800088d2  and     edx, ebx
0x1800088d4  mov     [rsi+4], cl
0x1800088d7  mov     [rsi+10h], edx
0x1800088da  mov     [rsi+14h], eax
0x1800088dd  jmp     loc_18000884E
0x1800088e2  cmp     eax, 117h
0x1800088e7  jnz     loc_18000884C
0x1800088ed  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800088f1  shr     eax, 7
0x1800088f4  and     eax, ebx
0x1800088f6  mov     [rsi+10h], eax
0x1800088f9  jmp     loc_18000884E
```
