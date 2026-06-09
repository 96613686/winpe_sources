# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x140011760`
- end: `0x1400117d0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140011760`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001178a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001178a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400117ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400117ba`

## string_xrefs

- `0x140011783`: `ntdll.dll`

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
0x140011760  mov     [rsp+arg_0], rbx
0x140011765  mov     [rsp+arg_8], rsi
0x14001176a  push    rdi
0x14001176b  sub     rsp, 40h
0x14001176f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011776  mov     ebx, r8d
0x140011779  mov     rdi, rdx
0x14001177c  mov     esi, ecx
0x14001177e  test    rax, rax
0x140011781  jnz     short loc_140011797
0x140011783  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14001178a  call    cs:__imp_GetModuleHandleW
0x140011790  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011797  mov     [rsp+48h+Arguments], 0; Arguments
0x1400117a0  mov     r9d, 400h; dwLanguageId
0x1400117a6  mov     [rsp+48h+nSize], ebx; nSize
0x1400117aa  mov     r8d, esi; dwMessageId
0x1400117ad  mov     rdx, rax; lpSource
0x1400117b0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400117b5  mov     ecx, 1A00h; dwFlags
0x1400117ba  call    cs:__imp_FormatMessageW
0x1400117c0  mov     rbx, [rsp+48h+arg_0]
0x1400117c5  mov     rsi, [rsp+48h+arg_8]
0x1400117ca  add     rsp, 40h
0x1400117ce  pop     rdi
0x1400117cf  retn
```
