# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180002280`
- end: `0x1800022f0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002280`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800022aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800022aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800022da`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800022da`

## string_xrefs

- `0x1800022a3`: `ntdll.dll`

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
0x180002280  mov     [rsp+arg_0], rbx
0x180002285  mov     [rsp+arg_8], rsi
0x18000228a  push    rdi
0x18000228b  sub     rsp, 40h
0x18000228f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002296  mov     ebx, r8d
0x180002299  mov     rdi, rdx
0x18000229c  mov     esi, ecx
0x18000229e  test    rax, rax
0x1800022a1  jnz     short loc_1800022B7
0x1800022a3  lea     rcx, ModuleName; "ntdll.dll"
0x1800022aa  call    cs:__imp_GetModuleHandleW
0x1800022b0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800022b7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800022c0  mov     r9d, 400h; dwLanguageId
0x1800022c6  mov     [rsp+48h+nSize], ebx; nSize
0x1800022ca  mov     r8d, esi; dwMessageId
0x1800022cd  mov     rdx, rax; lpSource
0x1800022d0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800022d5  mov     ecx, 1A00h; dwFlags
0x1800022da  call    cs:__imp_FormatMessageW
0x1800022e0  mov     rbx, [rsp+48h+arg_0]
0x1800022e5  mov     rsi, [rsp+48h+arg_8]
0x1800022ea  add     rsp, 40h
0x1800022ee  pop     rdi
0x1800022ef  retn
```
