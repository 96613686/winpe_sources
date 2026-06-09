# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x18000c390`
- end: `0x18000c435`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c390`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c3fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c3fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c413`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c413`

## string_xrefs

- `0x18000c3f5`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilInternalTelAssertUM(wil::details *this, const char *a2, const void *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  _QWORD v5[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v6; // [rsp+30h] [rbp-30h]
  __int64 v7; // [rsp+40h] [rbp-20h]
  __int64 v8; // [rsp+48h] [rbp-18h]
  __int64 v9; // [rsp+50h] [rbp-10h]

  v9 = 1;
  v5[0] = 11;
  v5[1] = &_ImageBase;
  v6 = (unsigned __int64)a2;
  v7 = 0;
  v8 = -1;
  ProcAddress = (FARPROC)`wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert;
  if ( `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert )
    goto LABEL_5;
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "MicrosoftTelemetryAssertTriggeredUM");
  `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_5:
    ((void (__fastcall *)(_QWORD *, const char *, const void *))ProcAddress)(v5, a2, a3);
}

```

## disassembly

```asm
0x18000c390  push    rbp
0x18000c392  mov     rbp, rsp
0x18000c395  sub     rsp, 60h
0x18000c399  xorps   xmm0, xmm0
0x18000c39c  xor     eax, eax
0x18000c39e  movups  [rbp+var_40], xmm0
0x18000c3a2  movups  [rbp+var_30], xmm0
0x18000c3a6  movups  [rbp+var_20], xmm0
0x18000c3aa  mov     [rbp+var_10], rax
0x18000c3ae  mov     dword ptr [rbp+var_40], 0Bh
0x18000c3b5  lea     rax, __ImageBase
0x18000c3bc  mov     qword ptr [rbp+var_40+8], rax
0x18000c3c0  mov     qword ptr [rbp+var_30], rdx
0x18000c3c4  mov     byte ptr [rbp+var_30+8], 0
0x18000c3c8  mov     qword ptr [rbp+var_20], 0
0x18000c3d0  or      eax, 0FFFFFFFFh
0x18000c3d3  mov     dword ptr [rbp+var_20+8], eax
0x18000c3d6  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000c3d9  mov     byte ptr [rbp+var_10], 1
0x18000c3dd  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000c3e4  test    rax, rax
0x18000c3e7  jnz     short loc_18000C425
0x18000c3e9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c3f0  test    rax, rax
0x18000c3f3  jnz     short loc_18000C409
0x18000c3f5  lea     rcx, ModuleName; "ntdll.dll"
0x18000c3fc  call    cs:__imp_GetModuleHandleW
0x18000c402  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c409  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000c410  mov     rcx, rax; hModule
0x18000c413  call    cs:__imp_GetProcAddress
0x18000c419  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000c420  test    rax, rax
0x18000c423  jz      short loc_18000C42F
0x18000c425  lea     rcx, [rbp+var_40]
0x18000c429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c42e  nop
0x18000c42f  add     rsp, 60h
0x18000c433  pop     rbp
0x18000c434  retn
```
