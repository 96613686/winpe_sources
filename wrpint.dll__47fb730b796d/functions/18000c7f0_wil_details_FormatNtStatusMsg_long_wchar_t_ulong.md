# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x18000c7f0`
- end: `0x18000c860`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c7f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000c81a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000c81a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c84a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c84a`

## string_xrefs

- `0x18000c813`: `ntdll.dll`

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
0x18000c7f0  mov     [rsp+arg_0], rbx
0x18000c7f5  mov     [rsp+arg_8], rsi
0x18000c7fa  push    rdi
0x18000c7fb  sub     rsp, 40h
0x18000c7ff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c806  mov     ebx, r8d
0x18000c809  mov     rdi, rdx
0x18000c80c  mov     esi, ecx
0x18000c80e  test    rax, rax
0x18000c811  jnz     short loc_18000C827
0x18000c813  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000c81a  call    cs:__imp_GetModuleHandleW
0x18000c820  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c827  mov     [rsp+48h+Arguments], 0; Arguments
0x18000c830  mov     r9d, 400h; dwLanguageId
0x18000c836  mov     [rsp+48h+nSize], ebx; nSize
0x18000c83a  mov     r8d, esi; dwMessageId
0x18000c83d  mov     rdx, rax; lpSource
0x18000c840  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000c845  mov     ecx, 1A00h; dwFlags
0x18000c84a  call    cs:__imp_FormatMessageW
0x18000c850  mov     rbx, [rsp+48h+arg_0]
0x18000c855  mov     rsi, [rsp+48h+arg_8]
0x18000c85a  add     rsp, 40h
0x18000c85e  pop     rdi
0x18000c85f  retn
```
