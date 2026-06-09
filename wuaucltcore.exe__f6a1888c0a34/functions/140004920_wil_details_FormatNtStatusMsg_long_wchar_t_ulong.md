# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x140004920`
- end: `0x140004990`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004920`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000494a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000494a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000497a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000497a`

## string_xrefs

- `0x140004943`: `ntdll.dll`

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
0x140004920  mov     [rsp+arg_0], rbx
0x140004925  mov     [rsp+arg_8], rsi
0x14000492a  push    rdi
0x14000492b  sub     rsp, 40h
0x14000492f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004936  mov     ebx, r8d
0x140004939  mov     rdi, rdx
0x14000493c  mov     esi, ecx
0x14000493e  test    rax, rax
0x140004941  jnz     short loc_140004957
0x140004943  lea     rcx, ModuleName; "ntdll.dll"
0x14000494a  call    cs:__imp_GetModuleHandleW
0x140004950  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004957  mov     [rsp+48h+Arguments], 0; Arguments
0x140004960  mov     r9d, 400h; dwLanguageId
0x140004966  mov     [rsp+48h+nSize], ebx; nSize
0x14000496a  mov     r8d, esi; dwMessageId
0x14000496d  mov     rdx, rax; lpSource
0x140004970  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140004975  mov     ecx, 1A00h; dwFlags
0x14000497a  call    cs:__imp_FormatMessageW
0x140004980  mov     rbx, [rsp+48h+arg_0]
0x140004985  mov     rsi, [rsp+48h+arg_8]
0x14000498a  add     rsp, 40h
0x14000498e  pop     rdi
0x14000498f  retn
```
