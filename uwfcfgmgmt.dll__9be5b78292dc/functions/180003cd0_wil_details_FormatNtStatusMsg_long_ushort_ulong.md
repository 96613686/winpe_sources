# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003cd0`
- end: `0x180003d40`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003cd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003cfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003cfa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d2a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003d2a`

## string_xrefs

- `0x180003cf3`: `ntdll.dll`

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
0x180003cd0  mov     [rsp+arg_0], rbx
0x180003cd5  mov     [rsp+arg_8], rsi
0x180003cda  push    rdi
0x180003cdb  sub     rsp, 40h
0x180003cdf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003ce6  mov     ebx, r8d
0x180003ce9  mov     rdi, rdx
0x180003cec  mov     esi, ecx
0x180003cee  test    rax, rax
0x180003cf1  jnz     short loc_180003D07
0x180003cf3  lea     rcx, ModuleName; "ntdll.dll"
0x180003cfa  call    cs:__imp_GetModuleHandleW
0x180003d00  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003d07  mov     [rsp+48h+Arguments], 0; Arguments
0x180003d10  mov     r9d, 400h; dwLanguageId
0x180003d16  mov     [rsp+48h+nSize], ebx; nSize
0x180003d1a  mov     r8d, esi; dwMessageId
0x180003d1d  mov     rdx, rax; lpSource
0x180003d20  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003d25  mov     ecx, 1A00h; dwFlags
0x180003d2a  call    cs:__imp_FormatMessageW
0x180003d30  mov     rbx, [rsp+48h+arg_0]
0x180003d35  mov     rsi, [rsp+48h+arg_8]
0x180003d3a  add     rsp, 40h
0x180003d3e  pop     rdi
0x180003d3f  retn
```
