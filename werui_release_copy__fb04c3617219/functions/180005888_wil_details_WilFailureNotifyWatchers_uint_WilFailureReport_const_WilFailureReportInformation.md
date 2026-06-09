# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180005888`
- end: `0x18000590e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005350`

## callees

- `0x180005888`
- `0x180018010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800058bc`
- `KERNEL32!GetModuleHandleW` at `0x1800058bc`
- `KERNEL32!GetProcAddress` at `0x1800058d8`
- `KERNEL32!GetProcAddress` at `0x1800058d8`

## string_xrefs

- `0x1800058b5`: `kernelbase.dll`

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
0x180005888  mov     [rsp+arg_0], rbx
0x18000588d  mov     [rsp+arg_8], rsi
0x180005892  push    rdi
0x180005893  sub     rsp, 20h
0x180005897  mov     rdi, r8
0x18000589a  mov     rsi, rdx
0x18000589d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800058a4  test    rbx, rbx
0x1800058a7  jnz     short loc_1800058ED
0x1800058a9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800058b0  test    rax, rax
0x1800058b3  jnz     short loc_1800058CE
0x1800058b5  lea     rcx, ModuleName; "kernelbase.dll"
0x1800058bc  call    cs:__imp_GetModuleHandleW
0x1800058c2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800058c9  test    rax, rax
0x1800058cc  jz      short loc_1800058E1
0x1800058ce  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800058d5  mov     rcx, rax; hModule
0x1800058d8  call    cs:__imp_GetProcAddress
0x1800058de  mov     rbx, rax
0x1800058e1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x1800058e8  test    rbx, rbx
0x1800058eb  jz      short loc_1800058FE
0x1800058ed  mov     r8, rdi
0x1800058f0  mov     rdx, rsi
0x1800058f3  xor     ecx, ecx
0x1800058f5  mov     rax, rbx
0x1800058f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058fd  nop
0x1800058fe  mov     rbx, [rsp+28h+arg_0]
0x180005903  mov     rsi, [rsp+28h+arg_8]
0x180005908  add     rsp, 20h
0x18000590c  pop     rdi
0x18000590d  retn
```
