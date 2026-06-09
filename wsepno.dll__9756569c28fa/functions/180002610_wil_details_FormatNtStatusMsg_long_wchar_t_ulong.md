# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x180002610`
- end: `0x180002680`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002610`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000263a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000263a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000266a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000266a`

## string_xrefs

- `0x180002633`: `ntdll.dll`

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
0x180002610  mov     [rsp+arg_0], rbx
0x180002615  mov     [rsp+arg_8], rsi
0x18000261a  push    rdi
0x18000261b  sub     rsp, 40h
0x18000261f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002626  mov     ebx, r8d
0x180002629  mov     rdi, rdx
0x18000262c  mov     esi, ecx
0x18000262e  test    rax, rax
0x180002631  jnz     short loc_180002647
0x180002633  lea     rcx, ModuleName; "ntdll.dll"
0x18000263a  call    cs:__imp_GetModuleHandleW
0x180002640  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002647  mov     [rsp+48h+Arguments], 0; Arguments
0x180002650  mov     r9d, 400h; dwLanguageId
0x180002656  mov     [rsp+48h+nSize], ebx; nSize
0x18000265a  mov     r8d, esi; dwMessageId
0x18000265d  mov     rdx, rax; lpSource
0x180002660  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180002665  mov     ecx, 1A00h; dwFlags
0x18000266a  call    cs:__imp_FormatMessageW
0x180002670  mov     rbx, [rsp+48h+arg_0]
0x180002675  mov     rsi, [rsp+48h+arg_8]
0x18000267a  add     rsp, 40h
0x18000267e  pop     rdi
0x18000267f  retn
```
