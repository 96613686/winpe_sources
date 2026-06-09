# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180005b28`
- end: `0x180005bae`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004cf0`

## callees

- `0x180005b28`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005b78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005b78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b5c`

## string_xrefs

- `0x180005b55`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilFailureNotifyWatchers(
        wil::details *this,
        __int64 a2,
        const struct WilFailureReport *a3,
        struct WilFailureReportInformation *a4)
{
  FARPROC ProcAddress; // rbx
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (ModuleHandleW = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW) != 0) )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  }
  `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_6:
    ((void (__fastcall *)(_QWORD, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *))ProcAddress)(
      0,
      a2,
      a3,
      a4);
}

```

## disassembly

```asm
0x180005b28  mov     [rsp+arg_0], rbx
0x180005b2d  mov     [rsp+arg_8], rsi
0x180005b32  push    rdi
0x180005b33  sub     rsp, 20h
0x180005b37  mov     rdi, r8
0x180005b3a  mov     rsi, rdx
0x180005b3d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180005b44  test    rbx, rbx
0x180005b47  jnz     short loc_180005B8D
0x180005b49  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005b50  test    rax, rax
0x180005b53  jnz     short loc_180005B6E
0x180005b55  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005b5c  call    cs:__imp_GetModuleHandleW
0x180005b62  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005b69  test    rax, rax
0x180005b6c  jz      short loc_180005B81
0x180005b6e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180005b75  mov     rcx, rax; hModule
0x180005b78  call    cs:__imp_GetProcAddress
0x180005b7e  mov     rbx, rax
0x180005b81  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180005b88  test    rbx, rbx
0x180005b8b  jz      short loc_180005B9E
0x180005b8d  mov     r8, rdi
0x180005b90  mov     rdx, rsi
0x180005b93  xor     ecx, ecx
0x180005b95  mov     rax, rbx
0x180005b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b9d  nop
0x180005b9e  mov     rbx, [rsp+28h+arg_0]
0x180005ba3  mov     rsi, [rsp+28h+arg_8]
0x180005ba8  add     rsp, 20h
0x180005bac  pop     rdi
0x180005bad  retn
```
