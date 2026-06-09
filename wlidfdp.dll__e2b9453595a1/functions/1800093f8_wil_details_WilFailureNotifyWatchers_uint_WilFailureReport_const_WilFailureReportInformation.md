# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x1800093f8`
- end: `0x18000947e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007930`

## callees

- `0x1800093f8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000942c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000942c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009448`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009448`

## string_xrefs

- `0x180009425`: `kernelbase.dll`

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
0x1800093f8  mov     [rsp+arg_0], rbx
0x1800093fd  mov     [rsp+arg_8], rsi
0x180009402  push    rdi
0x180009403  sub     rsp, 20h
0x180009407  mov     rdi, r8
0x18000940a  mov     rsi, rdx
0x18000940d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180009414  test    rbx, rbx
0x180009417  jnz     short loc_18000945D
0x180009419  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009420  test    rax, rax
0x180009423  jnz     short loc_18000943E
0x180009425  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000942c  call    cs:__imp_GetModuleHandleW
0x180009432  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009439  test    rax, rax
0x18000943c  jz      short loc_180009451
0x18000943e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180009445  mov     rcx, rax; hModule
0x180009448  call    cs:__imp_GetProcAddress
0x18000944e  mov     rbx, rax
0x180009451  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180009458  test    rbx, rbx
0x18000945b  jz      short loc_18000946E
0x18000945d  mov     r8, rdi
0x180009460  mov     rdx, rsi
0x180009463  xor     ecx, ecx
0x180009465  mov     rax, rbx
0x180009468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000946d  nop
0x18000946e  mov     rbx, [rsp+28h+arg_0]
0x180009473  mov     rsi, [rsp+28h+arg_8]
0x180009478  add     rsp, 20h
0x18000947c  pop     rdi
0x18000947d  retn
```
