# wil_QueryFeatureState

- ea: `0x1800381b0`
- end: `0x180038316`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800307e4`

## callees

- `0x1800381b0`
- `0x180056e30`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003824c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003824c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038235`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038235`

## string_xrefs

- `0x18003822e`: `ntdll.dll`
- `0x180038242`: `RtlQueryFeatureConfiguration`

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
0x1800381b0  mov     [rsp+arg_10], rbx
0x1800381b5  mov     [rsp+arg_18], rbp
0x1800381ba  push    rsi
0x1800381bb  push    rdi
0x1800381bc  push    r14
0x1800381be  sub     rsp, 50h
0x1800381c2  mov     rax, cs:__security_cookie
0x1800381c9  xor     rax, rsp
0x1800381cc  mov     [rsp+68h+var_20], rax
0x1800381d1  mov     rdi, [rsp+68h+arg_20]
0x1800381d9  mov     r14d, edx
0x1800381dc  mov     rax, [rsp+68h+arg_28]
0x1800381e4  mov     rsi, rcx
0x1800381e7  test    rdi, rdi
0x1800381ea  jz      short loc_1800381F2
0x1800381ec  mov     dword ptr [rdi], 0
0x1800381f2  xor     ebp, ebp
0x1800381f4  mov     [rsp+68h+var_38], 0
0x1800381fd  test    r8d, r8d
0x180038200  mov     ebx, 1
0x180038205  mov     [rax], ebx
0x180038207  setz    bpl
0x18003820b  xor     eax, eax
0x18003820d  mov     [rsp+68h+var_30], rax
0x180038212  mov     [rsp+68h+var_28], eax
0x180038216  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18003821d  test    rax, rax
0x180038220  jnz     short loc_18003829D
0x180038222  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180038229  test    rax, rax
0x18003822c  jnz     short loc_180038242
0x18003822e  lea     rcx, ModuleName; "ntdll.dll"
0x180038235  call    cs:__imp_GetModuleHandleW
0x18003823b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180038242  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180038249  mov     rcx, rax; hModule
0x18003824c  call    cs:__imp_GetProcAddress
0x180038252  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180038259  test    rax, rax
0x18003825c  jnz     short loc_18003829D
0x18003825e  mov     r8d, 0C0000139h
0x180038264  xor     ebx, ebx
0x180038266  test    rdi, rdi
0x180038269  jz      short loc_180038279
0x18003826b  xor     ecx, ecx
0x18003826d  cmp     r8d, 80000022h
0x180038274  setnz   cl
0x180038277  mov     [rdi], ecx
0x180038279  mov     eax, ebx
0x18003827b  mov     rcx, [rsp+68h+var_20]
0x180038280  xor     rcx, rsp; StackCookie
0x180038283  call    __security_check_cookie
0x180038288  lea     r11, [rsp+68h+var_18]
0x18003828d  mov     rbx, [r11+30h]
0x180038291  mov     rbp, [r11+38h]
0x180038295  mov     rsp, r11
0x180038298  pop     r14
0x18003829a  pop     rdi
0x18003829b  pop     rsi
0x18003829c  retn
0x18003829d  lea     r9, [rsp+68h+var_30]
0x1800382a2  mov     edx, ebp
0x1800382a4  lea     r8, [rsp+68h+var_38]
0x1800382a9  mov     ecx, r14d
0x1800382ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382b1  mov     r8d, eax
0x1800382b4  test    eax, eax
0x1800382b6  jnz     short loc_1800382FA
0x1800382b8  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800382bc  mov     ecx, edx
0x1800382be  mov     eax, [rsp+68h+var_28]
0x1800382c2  mov     [rsi+0Ch], eax
0x1800382c5  mov     eax, edx
0x1800382c7  shr     eax, 0Eh
0x1800382ca  shr     ecx, 4
0x1800382cd  and     eax, 3
0x1800382d0  and     ecx, 3
0x1800382d3  mov     [rsi+8], eax
0x1800382d6  mov     [rsi], ecx
0x1800382d8  mov     eax, edx
0x1800382da  mov     ecx, edx
0x1800382dc  shr     eax, 6
0x1800382df  shr     ecx, 8
0x1800382e2  and     eax, ebx
0x1800382e4  and     cl, 3Fh
0x1800382e7  shr     edx, 7
0x1800382ea  and     edx, ebx
0x1800382ec  mov     [rsi+4], cl
0x1800382ef  mov     [rsi+10h], edx
0x1800382f2  mov     [rsi+14h], eax
0x1800382f5  jmp     loc_180038266
0x1800382fa  cmp     eax, 117h
0x1800382ff  jnz     loc_180038264
0x180038305  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180038309  shr     eax, 7
0x18003830c  and     eax, ebx
0x18003830e  mov     [rsi+10h], eax
0x180038311  jmp     loc_180038266
```
