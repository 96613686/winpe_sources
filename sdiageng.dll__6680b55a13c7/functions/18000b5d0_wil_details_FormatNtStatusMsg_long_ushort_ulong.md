# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000b5d0`
- end: `0x18000b640`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b5d0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000b62a`
- `KERNEL32!FormatMessageW` at `0x18000b62a`
- `KERNEL32!GetModuleHandleW` at `0x18000b5fa`
- `KERNEL32!GetModuleHandleW` at `0x18000b5fa`

## string_xrefs

- `0x18000b5f3`: `ntdll.dll`

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
0x18000b5d0  mov     [rsp+arg_0], rbx
0x18000b5d5  mov     [rsp+arg_8], rsi
0x18000b5da  push    rdi
0x18000b5db  sub     rsp, 40h
0x18000b5df  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b5e6  mov     ebx, r8d
0x18000b5e9  mov     rdi, rdx
0x18000b5ec  mov     esi, ecx
0x18000b5ee  test    rax, rax
0x18000b5f1  jnz     short loc_18000B607
0x18000b5f3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000b5fa  call    cs:__imp_GetModuleHandleW
0x18000b600  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b607  mov     [rsp+48h+Arguments], 0; Arguments
0x18000b610  mov     r9d, 400h; dwLanguageId
0x18000b616  mov     [rsp+48h+nSize], ebx; nSize
0x18000b61a  mov     r8d, esi; dwMessageId
0x18000b61d  mov     rdx, rax; lpSource
0x18000b620  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000b625  mov     ecx, 1A00h; dwFlags
0x18000b62a  call    cs:__imp_FormatMessageW
0x18000b630  mov     rbx, [rsp+48h+arg_0]
0x18000b635  mov     rsi, [rsp+48h+arg_8]
0x18000b63a  add     rsp, 40h
0x18000b63e  pop     rdi
0x18000b63f  retn
```
