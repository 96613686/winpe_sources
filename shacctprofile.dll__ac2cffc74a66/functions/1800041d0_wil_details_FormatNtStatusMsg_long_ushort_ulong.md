# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800041d0`
- end: `0x180004240`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800041d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800041fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800041fa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000422a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000422a`

## string_xrefs

- `0x1800041f3`: `ntdll.dll`

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
0x1800041d0  mov     [rsp+arg_0], rbx
0x1800041d5  mov     [rsp+arg_8], rsi
0x1800041da  push    rdi
0x1800041db  sub     rsp, 40h
0x1800041df  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800041e6  mov     ebx, r8d
0x1800041e9  mov     rdi, rdx
0x1800041ec  mov     esi, ecx
0x1800041ee  test    rax, rax
0x1800041f1  jnz     short loc_180004207
0x1800041f3  lea     rcx, ModuleName; "ntdll.dll"
0x1800041fa  call    cs:__imp_GetModuleHandleW
0x180004200  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004207  mov     [rsp+48h+Arguments], 0; Arguments
0x180004210  mov     r9d, 400h; dwLanguageId
0x180004216  mov     [rsp+48h+nSize], ebx; nSize
0x18000421a  mov     r8d, esi; dwMessageId
0x18000421d  mov     rdx, rax; lpSource
0x180004220  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004225  mov     ecx, 1A00h; dwFlags
0x18000422a  call    cs:__imp_FormatMessageW
0x180004230  mov     rbx, [rsp+48h+arg_0]
0x180004235  mov     rsi, [rsp+48h+arg_8]
0x18000423a  add     rsp, 40h
0x18000423e  pop     rdi
0x18000423f  retn
```
