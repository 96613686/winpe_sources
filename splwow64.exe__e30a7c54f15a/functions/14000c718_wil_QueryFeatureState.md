# wil_QueryFeatureState

- ea: `0x14000c718`
- end: `0x14000c87e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140009eb4`

## callees

- `0x140001ee0`
- `0x14000c718`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000c7b4`
- `KERNEL32!GetProcAddress` at `0x14000c7b4`
- `KERNEL32!GetModuleHandleW` at `0x14000c79d`
- `KERNEL32!GetModuleHandleW` at `0x14000c79d`

## string_xrefs

- `0x14000c796`: `ntdll.dll`
- `0x14000c7aa`: `RtlQueryFeatureConfiguration`

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
0x14000c718  mov     [rsp+arg_10], rbx
0x14000c71d  mov     [rsp+arg_18], rbp
0x14000c722  push    rsi
0x14000c723  push    rdi
0x14000c724  push    r14
0x14000c726  sub     rsp, 50h
0x14000c72a  mov     rax, cs:__security_cookie
0x14000c731  xor     rax, rsp
0x14000c734  mov     [rsp+68h+var_20], rax
0x14000c739  mov     rdi, [rsp+68h+arg_20]
0x14000c741  mov     r14d, edx
0x14000c744  mov     rax, [rsp+68h+arg_28]
0x14000c74c  mov     rsi, rcx
0x14000c74f  test    rdi, rdi
0x14000c752  jz      short loc_14000C75A
0x14000c754  mov     dword ptr [rdi], 0
0x14000c75a  xor     ebp, ebp
0x14000c75c  mov     [rsp+68h+var_38], 0
0x14000c765  test    r8d, r8d
0x14000c768  mov     ebx, 1
0x14000c76d  mov     [rax], ebx
0x14000c76f  setz    bpl
0x14000c773  xor     eax, eax
0x14000c775  mov     [rsp+68h+var_30], rax
0x14000c77a  mov     [rsp+68h+var_28], eax
0x14000c77e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000c785  test    rax, rax
0x14000c788  jnz     short loc_14000C805
0x14000c78a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c791  test    rax, rax
0x14000c794  jnz     short loc_14000C7AA
0x14000c796  lea     rcx, ModuleName; "ntdll.dll"
0x14000c79d  call    cs:__imp_GetModuleHandleW
0x14000c7a3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c7aa  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000c7b1  mov     rcx, rax; hModule
0x14000c7b4  call    cs:__imp_GetProcAddress
0x14000c7ba  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000c7c1  test    rax, rax
0x14000c7c4  jnz     short loc_14000C805
0x14000c7c6  mov     r8d, 0C0000139h
0x14000c7cc  xor     ebx, ebx
0x14000c7ce  test    rdi, rdi
0x14000c7d1  jz      short loc_14000C7E1
0x14000c7d3  xor     ecx, ecx
0x14000c7d5  cmp     r8d, 80000022h
0x14000c7dc  setnz   cl
0x14000c7df  mov     [rdi], ecx
0x14000c7e1  mov     eax, ebx
0x14000c7e3  mov     rcx, [rsp+68h+var_20]
0x14000c7e8  xor     rcx, rsp; StackCookie
0x14000c7eb  call    __security_check_cookie
0x14000c7f0  lea     r11, [rsp+68h+var_18]
0x14000c7f5  mov     rbx, [r11+30h]
0x14000c7f9  mov     rbp, [r11+38h]
0x14000c7fd  mov     rsp, r11
0x14000c800  pop     r14
0x14000c802  pop     rdi
0x14000c803  pop     rsi
0x14000c804  retn
0x14000c805  lea     r9, [rsp+68h+var_30]
0x14000c80a  mov     edx, ebp
0x14000c80c  lea     r8, [rsp+68h+var_38]
0x14000c811  mov     ecx, r14d
0x14000c814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c819  mov     r8d, eax
0x14000c81c  test    eax, eax
0x14000c81e  jnz     short loc_14000C862
0x14000c820  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000c824  mov     ecx, edx
0x14000c826  mov     eax, [rsp+68h+var_28]
0x14000c82a  mov     [rsi+0Ch], eax
0x14000c82d  mov     eax, edx
0x14000c82f  shr     eax, 0Eh
0x14000c832  shr     ecx, 4
0x14000c835  and     eax, 3
0x14000c838  and     ecx, 3
0x14000c83b  mov     [rsi+8], eax
0x14000c83e  mov     [rsi], ecx
0x14000c840  mov     eax, edx
0x14000c842  mov     ecx, edx
0x14000c844  shr     eax, 6
0x14000c847  shr     ecx, 8
0x14000c84a  and     eax, ebx
0x14000c84c  and     cl, 3Fh
0x14000c84f  shr     edx, 7
0x14000c852  and     edx, ebx
0x14000c854  mov     [rsi+4], cl
0x14000c857  mov     [rsi+10h], edx
0x14000c85a  mov     [rsi+14h], eax
0x14000c85d  jmp     loc_14000C7CE
0x14000c862  cmp     eax, 117h
0x14000c867  jnz     loc_14000C7CC
0x14000c86d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000c871  shr     eax, 7
0x14000c874  and     eax, ebx
0x14000c876  mov     [rsi+10h], eax
0x14000c879  jmp     loc_14000C7CE
```
