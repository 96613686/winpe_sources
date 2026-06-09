# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18001a4c0`
- end: `0x18001a530`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001a4c0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18001a51a`
- `KERNEL32!FormatMessageW` at `0x18001a51a`
- `KERNEL32!GetModuleHandleW` at `0x18001a4ea`
- `KERNEL32!GetModuleHandleW` at `0x18001a4ea`

## string_xrefs

- `0x18001a4e3`: `ntdll.dll`

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
0x18001a4c0  mov     [rsp+arg_0], rbx
0x18001a4c5  mov     [rsp+arg_8], rsi
0x18001a4ca  push    rdi
0x18001a4cb  sub     rsp, 40h
0x18001a4cf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001a4d6  mov     ebx, r8d
0x18001a4d9  mov     rdi, rdx
0x18001a4dc  mov     esi, ecx
0x18001a4de  test    rax, rax
0x18001a4e1  jnz     short loc_18001A4F7
0x18001a4e3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001a4ea  call    cs:__imp_GetModuleHandleW
0x18001a4f0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001a4f7  mov     [rsp+48h+Arguments], 0; Arguments
0x18001a500  mov     r9d, 400h; dwLanguageId
0x18001a506  mov     [rsp+48h+nSize], ebx; nSize
0x18001a50a  mov     r8d, esi; dwMessageId
0x18001a50d  mov     rdx, rax; lpSource
0x18001a510  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18001a515  mov     ecx, 1A00h; dwFlags
0x18001a51a  call    cs:__imp_FormatMessageW
0x18001a520  mov     rbx, [rsp+48h+arg_0]
0x18001a525  mov     rsi, [rsp+48h+arg_8]
0x18001a52a  add     rsp, 40h
0x18001a52e  pop     rdi
0x18001a52f  retn
```
