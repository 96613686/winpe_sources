# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180011660`
- end: `0x1800116d0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180011660`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001168a`
- `KERNEL32!GetModuleHandleW` at `0x18001168a`
- `KERNEL32!FormatMessageW` at `0x1800116ba`
- `KERNEL32!FormatMessageW` at `0x1800116ba`

## string_xrefs

- `0x180011683`: `ntdll.dll`

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
0x180011660  mov     [rsp+arg_0], rbx
0x180011665  mov     [rsp+arg_8], rsi
0x18001166a  push    rdi
0x18001166b  sub     rsp, 40h
0x18001166f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011676  mov     ebx, r8d
0x180011679  mov     rdi, rdx
0x18001167c  mov     esi, ecx
0x18001167e  test    rax, rax
0x180011681  jnz     short loc_180011697
0x180011683  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001168a  call    cs:__imp_GetModuleHandleW
0x180011690  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011697  mov     [rsp+48h+Arguments], 0; Arguments
0x1800116a0  mov     r9d, 400h; dwLanguageId
0x1800116a6  mov     [rsp+48h+nSize], ebx; nSize
0x1800116aa  mov     r8d, esi; dwMessageId
0x1800116ad  mov     rdx, rax; lpSource
0x1800116b0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800116b5  mov     ecx, 1A00h; dwFlags
0x1800116ba  call    cs:__imp_FormatMessageW
0x1800116c0  mov     rbx, [rsp+48h+arg_0]
0x1800116c5  mov     rsi, [rsp+48h+arg_8]
0x1800116ca  add     rsp, 40h
0x1800116ce  pop     rdi
0x1800116cf  retn
```
