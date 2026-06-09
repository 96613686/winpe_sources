# wil_QueryFeatureState

- ea: `0x18000ba64`
- end: `0x18000bbca`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800078e8`

## callees

- `0x180001770`
- `0x18000ba64`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb00`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bae9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bae9`

## string_xrefs

- `0x18000bae2`: `ntdll.dll`
- `0x18000baf6`: `RtlQueryFeatureConfiguration`

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
0x18000ba64  mov     [rsp+arg_10], rbx
0x18000ba69  mov     [rsp+arg_18], rbp
0x18000ba6e  push    rsi
0x18000ba6f  push    rdi
0x18000ba70  push    r14
0x18000ba72  sub     rsp, 50h
0x18000ba76  mov     rax, cs:__security_cookie
0x18000ba7d  xor     rax, rsp
0x18000ba80  mov     [rsp+68h+var_20], rax
0x18000ba85  mov     rdi, [rsp+68h+arg_20]
0x18000ba8d  mov     r14d, edx
0x18000ba90  mov     rax, [rsp+68h+arg_28]
0x18000ba98  mov     rsi, rcx
0x18000ba9b  test    rdi, rdi
0x18000ba9e  jz      short loc_18000BAA6
0x18000baa0  mov     dword ptr [rdi], 0
0x18000baa6  xor     ebp, ebp
0x18000baa8  mov     [rsp+68h+var_38], 0
0x18000bab1  test    r8d, r8d
0x18000bab4  mov     ebx, 1
0x18000bab9  mov     [rax], ebx
0x18000babb  setz    bpl
0x18000babf  xor     eax, eax
0x18000bac1  mov     [rsp+68h+var_30], rax
0x18000bac6  mov     [rsp+68h+var_28], eax
0x18000baca  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000bad1  test    rax, rax
0x18000bad4  jnz     short loc_18000BB51
0x18000bad6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000badd  test    rax, rax
0x18000bae0  jnz     short loc_18000BAF6
0x18000bae2  lea     rcx, ModuleName; "ntdll.dll"
0x18000bae9  call    cs:__imp_GetModuleHandleW
0x18000baef  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000baf6  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000bafd  mov     rcx, rax; hModule
0x18000bb00  call    cs:__imp_GetProcAddress
0x18000bb06  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000bb0d  test    rax, rax
0x18000bb10  jnz     short loc_18000BB51
0x18000bb12  mov     r8d, 0C0000139h
0x18000bb18  xor     ebx, ebx
0x18000bb1a  test    rdi, rdi
0x18000bb1d  jz      short loc_18000BB2D
0x18000bb1f  xor     ecx, ecx
0x18000bb21  cmp     r8d, 80000022h
0x18000bb28  setnz   cl
0x18000bb2b  mov     [rdi], ecx
0x18000bb2d  mov     eax, ebx
0x18000bb2f  mov     rcx, [rsp+68h+var_20]
0x18000bb34  xor     rcx, rsp; StackCookie
0x18000bb37  call    __security_check_cookie
0x18000bb3c  lea     r11, [rsp+68h+var_18]
0x18000bb41  mov     rbx, [r11+30h]
0x18000bb45  mov     rbp, [r11+38h]
0x18000bb49  mov     rsp, r11
0x18000bb4c  pop     r14
0x18000bb4e  pop     rdi
0x18000bb4f  pop     rsi
0x18000bb50  retn
0x18000bb51  lea     r9, [rsp+68h+var_30]
0x18000bb56  mov     edx, ebp
0x18000bb58  lea     r8, [rsp+68h+var_38]
0x18000bb5d  mov     ecx, r14d
0x18000bb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb65  mov     r8d, eax
0x18000bb68  test    eax, eax
0x18000bb6a  jnz     short loc_18000BBAE
0x18000bb6c  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000bb70  mov     ecx, edx
0x18000bb72  mov     eax, [rsp+68h+var_28]
0x18000bb76  mov     [rsi+0Ch], eax
0x18000bb79  mov     eax, edx
0x18000bb7b  shr     eax, 0Eh
0x18000bb7e  shr     ecx, 4
0x18000bb81  and     eax, 3
0x18000bb84  and     ecx, 3
0x18000bb87  mov     [rsi+8], eax
0x18000bb8a  mov     [rsi], ecx
0x18000bb8c  mov     eax, edx
0x18000bb8e  mov     ecx, edx
0x18000bb90  shr     eax, 6
0x18000bb93  shr     ecx, 8
0x18000bb96  and     eax, ebx
0x18000bb98  and     cl, 3Fh
0x18000bb9b  shr     edx, 7
0x18000bb9e  and     edx, ebx
0x18000bba0  mov     [rsi+4], cl
0x18000bba3  mov     [rsi+10h], edx
0x18000bba6  mov     [rsi+14h], eax
0x18000bba9  jmp     loc_18000BB1A
0x18000bbae  cmp     eax, 117h
0x18000bbb3  jnz     loc_18000BB18
0x18000bbb9  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000bbbd  shr     eax, 7
0x18000bbc0  and     eax, ebx
0x18000bbc2  mov     [rsi+10h], eax
0x18000bbc5  jmp     loc_18000BB1A
```
