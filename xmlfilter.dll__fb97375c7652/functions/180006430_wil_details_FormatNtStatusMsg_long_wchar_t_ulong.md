# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x180006430`
- end: `0x1800064a0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006430`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000645a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000645a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000648a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000648a`

## string_xrefs

- `0x180006453`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  FormatMessageW(0x1A00u, ModuleHandleW, dwMessageId, 0x400u, lpBuffer, nSize, 0);
}

```

## disassembly

```asm
0x180006430  mov     [rsp+arg_0], rbx
0x180006435  mov     [rsp+arg_8], rsi
0x18000643a  push    rdi
0x18000643b  sub     rsp, 40h
0x18000643f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006446  mov     ebx, r8d
0x180006449  mov     rdi, rdx
0x18000644c  mov     esi, ecx
0x18000644e  test    rax, rax
0x180006451  jnz     short loc_180006467
0x180006453  lea     rcx, ModuleName; "ntdll.dll"
0x18000645a  call    cs:__imp_GetModuleHandleW
0x180006460  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006467  mov     [rsp+48h+Arguments], 0; Arguments
0x180006470  mov     r9d, 400h; dwLanguageId
0x180006476  mov     [rsp+48h+nSize], ebx; nSize
0x18000647a  mov     r8d, esi; dwMessageId
0x18000647d  mov     rdx, rax; lpSource
0x180006480  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006485  mov     ecx, 1A00h; dwFlags
0x18000648a  call    cs:__imp_FormatMessageW
0x180006490  mov     rbx, [rsp+48h+arg_0]
0x180006495  mov     rsi, [rsp+48h+arg_8]
0x18000649a  add     rsp, 40h
0x18000649e  pop     rdi
0x18000649f  retn
```
