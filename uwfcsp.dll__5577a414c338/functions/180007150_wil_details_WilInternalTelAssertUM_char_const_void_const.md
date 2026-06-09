# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x180007150`
- end: `0x1800071f4`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `164`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007150`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071bc`

## string_xrefs

- `0x1800071b5`: `ntdll.dll`

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
  v7 = 0;
  v5[1] = &_ImageBase;
  v8 = -1;
  ProcAddress = (FARPROC)`wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert;
  v5[0] = 11;
  v6 = (unsigned __int64)a2;
  if ( `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert )
    goto LABEL_5;
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180007150  push    rbp
0x180007152  mov     rbp, rsp
0x180007155  sub     rsp, 60h
0x180007159  xor     eax, eax
0x18000715b  xorps   xmm0, xmm0
0x18000715e  mov     [rbp+var_10], rax
0x180007162  lea     rax, __ImageBase
0x180007169  movups  [rbp+var_20], xmm0
0x18000716d  mov     qword ptr [rbp+var_20], 0
0x180007175  movups  [rbp+var_40], xmm0
0x180007179  mov     qword ptr [rbp+var_40+8], rax
0x18000717d  or      eax, 0FFFFFFFFh
0x180007180  movups  [rbp+var_30], xmm0
0x180007184  mov     dword ptr [rbp+var_20+8], eax
0x180007187  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000718a  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180007191  mov     dword ptr [rbp+var_40], 0Bh
0x180007198  mov     qword ptr [rbp+var_30], rdx
0x18000719c  mov     byte ptr [rbp+var_30+8], 0
0x1800071a0  mov     byte ptr [rbp+var_10], 1
0x1800071a4  test    rax, rax
0x1800071a7  jnz     short loc_1800071E5
0x1800071a9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800071b0  test    rax, rax
0x1800071b3  jnz     short loc_1800071C9
0x1800071b5  lea     rcx, ModuleName; "ntdll.dll"
0x1800071bc  call    cs:__imp_GetModuleHandleW
0x1800071c2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800071c9  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800071d0  mov     rcx, rax; hModule
0x1800071d3  call    cs:__imp_GetProcAddress
0x1800071d9  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x1800071e0  test    rax, rax
0x1800071e3  jz      short loc_1800071EE
0x1800071e5  lea     rcx, [rbp+var_40]
0x1800071e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ee  add     rsp, 60h
0x1800071f2  pop     rbp
0x1800071f3  retn
```
