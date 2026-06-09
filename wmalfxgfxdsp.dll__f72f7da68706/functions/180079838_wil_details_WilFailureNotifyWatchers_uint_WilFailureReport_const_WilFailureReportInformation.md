# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180079838`
- end: `0x1800798bd`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `133`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180078800`

## callees

- `0x180079838`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079888`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079888`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007986c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007986c`

## string_xrefs

- `0x180079865`: `kernelbase.dll`

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
0x180079838  mov     [rsp+arg_0], rbx
0x18007983d  mov     [rsp+arg_8], rsi
0x180079842  push    rdi
0x180079843  sub     rsp, 20h
0x180079847  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18007984e  mov     rdi, r8
0x180079851  mov     rsi, rdx
0x180079854  test    rbx, rbx
0x180079857  jnz     short loc_18007989D
0x180079859  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180079860  test    rax, rax
0x180079863  jnz     short loc_18007987E
0x180079865  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18007986c  call    cs:__imp_GetModuleHandleW
0x180079872  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180079879  test    rax, rax
0x18007987c  jz      short loc_180079891
0x18007987e  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180079885  mov     rcx, rax; hModule
0x180079888  call    cs:__imp_GetProcAddress
0x18007988e  mov     rbx, rax
0x180079891  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180079898  test    rbx, rbx
0x18007989b  jz      short loc_1800798AD
0x18007989d  mov     r8, rdi
0x1800798a0  mov     rdx, rsi
0x1800798a3  xor     ecx, ecx
0x1800798a5  mov     rax, rbx
0x1800798a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800798ad  mov     rbx, [rsp+28h+arg_0]
0x1800798b2  mov     rsi, [rsp+28h+arg_8]
0x1800798b7  add     rsp, 20h
0x1800798bb  pop     rdi
0x1800798bc  retn
```
