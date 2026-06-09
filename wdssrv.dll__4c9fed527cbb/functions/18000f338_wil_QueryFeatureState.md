# wil_QueryFeatureState

- ea: `0x18000f338`
- end: `0x18000f49e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a338`

## callees

- `0x18000f338`
- `0x18001c150`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000f3b7`
- `KERNEL32!GetModuleHandleW` at `0x18000f3b7`
- `KERNEL32!GetProcAddress` at `0x18000f3d4`
- `KERNEL32!GetProcAddress` at `0x18000f3d4`

## string_xrefs

- `0x18000f3b0`: `ntdll.dll`
- `0x18000f3ca`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  int v6; // ebx
  BOOL v9; // r14d
  unsigned int v10; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ecx
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+38h] [rbp-40h] BYREF
  int v18; // [rsp+40h] [rbp-38h]

  v6 = 0;
  if ( a5 )
    *a5 = 0;
  *a6 = 1;
  v16 = 0;
  v9 = a3 == 0;
  v10 = 0;
  v17 = 0;
  v18 = 0;
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
      v13 = -1073741511;
      goto LABEL_13;
    }
  }
  v13 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v16, &v17);
  if ( v13 )
  {
    if ( v13 != 279 )
      goto LABEL_13;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v17) >> 7) & 1;
  }
  else
  {
    v14 = HIDWORD(v17);
    *(_DWORD *)a1 = (HIDWORD(v17) >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v14) & 0x3F;
    *(_DWORD *)(a1 + 12) = v18;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v14 >> 14;
    *(_DWORD *)(a1 + 20) = (v14 >> 6) & 1;
    *(_DWORD *)(a1 + 16) = (v14 >> 7) & 1;
  }
  v10 = 1;
LABEL_13:
  if ( a5 )
  {
    LOBYTE(v6) = v13 != -2147483614;
    *a5 = v6;
  }
  return v10;
}

```

## disassembly

```asm
0x18000f338  mov     [rsp+arg_10], rbx
0x18000f33d  push    rbp
0x18000f33e  push    rsi
0x18000f33f  push    rdi
0x18000f340  push    r14
0x18000f342  push    r15
0x18000f344  sub     rsp, 50h
0x18000f348  mov     rax, cs:__security_cookie
0x18000f34f  xor     rax, rsp
0x18000f352  mov     [rsp+78h+var_30], rax
0x18000f357  mov     rdi, [rsp+78h+arg_20]
0x18000f35f  xor     ebx, ebx
0x18000f361  mov     rax, [rsp+78h+arg_28]
0x18000f369  mov     r15d, edx
0x18000f36c  mov     rsi, rcx
0x18000f36f  test    rdi, rdi
0x18000f372  jz      short loc_18000F376
0x18000f374  mov     [rdi], ebx
0x18000f376  test    r8d, r8d
0x18000f379  mov     dword ptr [rax], 1
0x18000f37f  mov     r14d, ebx
0x18000f382  mov     [rsp+78h+var_48], rbx
0x18000f387  setz    r14b
0x18000f38b  mov     ebp, ebx
0x18000f38d  xor     eax, eax
0x18000f38f  mov     [rsp+78h+var_40], rax
0x18000f394  mov     [rsp+78h+var_38], eax
0x18000f398  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000f39f  test    rax, rax
0x18000f3a2  jnz     short loc_18000F3F3
0x18000f3a4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f3ab  test    rax, rax
0x18000f3ae  jnz     short loc_18000F3CA
0x18000f3b0  lea     rcx, ModuleName; "ntdll.dll"
0x18000f3b7  call    cs:__imp_GetModuleHandleW
0x18000f3be  nop     dword ptr [rax+rax+00h]
0x18000f3c3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f3ca  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000f3d1  mov     rcx, rax; hModule
0x18000f3d4  call    cs:__imp_GetProcAddress
0x18000f3db  nop     dword ptr [rax+rax+00h]
0x18000f3e0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000f3e7  test    rax, rax
0x18000f3ea  jnz     short loc_18000F3F3
0x18000f3ec  mov     edx, 0C0000139h
0x18000f3f1  jmp     short loc_18000F46A
0x18000f3f3  lea     r9, [rsp+78h+var_40]
0x18000f3f8  mov     edx, r14d
0x18000f3fb  lea     r8, [rsp+78h+var_48]
0x18000f400  mov     ecx, r15d
0x18000f403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f408  mov     edx, eax
0x18000f40a  mov     ecx, eax
0x18000f40c  test    eax, eax
0x18000f40e  jnz     short loc_18000F450
0x18000f410  mov     ecx, dword ptr [rsp+78h+var_40+4]
0x18000f414  mov     eax, ecx
0x18000f416  shr     eax, 4
0x18000f419  and     eax, 3
0x18000f41c  mov     [rsi], eax
0x18000f41e  mov     eax, ecx
0x18000f420  shr     eax, 8
0x18000f423  and     al, 3Fh
0x18000f425  mov     [rsi+4], al
0x18000f428  mov     eax, [rsp+78h+var_38]
0x18000f42c  mov     [rsi+0Ch], eax
0x18000f42f  mov     eax, ecx
0x18000f431  shr     eax, 0Eh
0x18000f434  and     eax, 3
0x18000f437  mov     [rsi+8], eax
0x18000f43a  mov     eax, ecx
0x18000f43c  shr     eax, 6
0x18000f43f  and     eax, 1
0x18000f442  shr     ecx, 7
0x18000f445  and     ecx, 1
0x18000f448  mov     [rsi+14h], eax
0x18000f44b  mov     [rsi+10h], ecx
0x18000f44e  jmp     short loc_18000F465
0x18000f450  cmp     ecx, 117h
0x18000f456  jnz     short loc_18000F46A
0x18000f458  mov     eax, dword ptr [rsp+78h+var_40+4]
0x18000f45c  shr     eax, 7
0x18000f45f  and     eax, 1
0x18000f462  mov     [rsi+10h], eax
0x18000f465  mov     ebp, 1
0x18000f46a  test    rdi, rdi
0x18000f46d  jz      short loc_18000F47A
0x18000f46f  cmp     edx, 80000022h
0x18000f475  setnz   bl
0x18000f478  mov     [rdi], ebx
0x18000f47a  mov     eax, ebp
0x18000f47c  mov     rcx, [rsp+78h+var_30]
0x18000f481  xor     rcx, rsp; StackCookie
0x18000f484  call    __security_check_cookie
0x18000f489  mov     rbx, [rsp+78h+arg_10]
0x18000f491  add     rsp, 50h
0x18000f495  pop     r15
0x18000f497  pop     r14
0x18000f499  pop     rdi
0x18000f49a  pop     rsi
0x18000f49b  pop     rbp
0x18000f49c  retn
```
