# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x180006940`
- end: `0x1800069b0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006940`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000696a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000696a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000699a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000699a`

## string_xrefs

- `0x180006963`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180006940  mov     [rsp+arg_0], rbx
0x180006945  mov     [rsp+arg_8], rsi
0x18000694a  push    rdi
0x18000694b  sub     rsp, 40h
0x18000694f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006956  mov     ebx, r8d
0x180006959  mov     rdi, rdx
0x18000695c  mov     esi, ecx
0x18000695e  test    rax, rax
0x180006961  jnz     short loc_180006977
0x180006963  lea     rcx, ModuleName; "ntdll.dll"
0x18000696a  call    cs:__imp_GetModuleHandleW
0x180006970  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006977  mov     [rsp+48h+Arguments], 0; Arguments
0x180006980  mov     r9d, 400h; dwLanguageId
0x180006986  mov     [rsp+48h+nSize], ebx; nSize
0x18000698a  mov     r8d, esi; dwMessageId
0x18000698d  mov     rdx, rax; lpSource
0x180006990  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006995  mov     ecx, 1A00h; dwFlags
0x18000699a  call    cs:__imp_FormatMessageW
0x1800069a0  mov     rbx, [rsp+48h+arg_0]
0x1800069a5  mov     rsi, [rsp+48h+arg_8]
0x1800069aa  add     rsp, 40h
0x1800069ae  pop     rdi
0x1800069af  retn
```
