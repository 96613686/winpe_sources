# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140009b30`
- end: `0x140009ba0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140009b30`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140009b8a`
- `KERNEL32!FormatMessageW` at `0x140009b8a`
- `KERNEL32!GetModuleHandleW` at `0x140009b5a`
- `KERNEL32!GetModuleHandleW` at `0x140009b5a`

## string_xrefs

- `0x140009b53`: `ntdll.dll`

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
0x140009b30  mov     [rsp+arg_0], rbx
0x140009b35  mov     [rsp+arg_8], rsi
0x140009b3a  push    rdi
0x140009b3b  sub     rsp, 40h
0x140009b3f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009b46  mov     ebx, r8d
0x140009b49  mov     rdi, rdx
0x140009b4c  mov     esi, ecx
0x140009b4e  test    rax, rax
0x140009b51  jnz     short loc_140009B67
0x140009b53  lea     rcx, ModuleName; "ntdll.dll"
0x140009b5a  call    cs:__imp_GetModuleHandleW
0x140009b60  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009b67  mov     [rsp+48h+Arguments], 0; Arguments
0x140009b70  mov     r9d, 400h; dwLanguageId
0x140009b76  mov     [rsp+48h+nSize], ebx; nSize
0x140009b7a  mov     r8d, esi; dwMessageId
0x140009b7d  mov     rdx, rax; lpSource
0x140009b80  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140009b85  mov     ecx, 1A00h; dwFlags
0x140009b8a  call    cs:__imp_FormatMessageW
0x140009b90  mov     rbx, [rsp+48h+arg_0]
0x140009b95  mov     rsi, [rsp+48h+arg_8]
0x140009b9a  add     rsp, 40h
0x140009b9e  pop     rdi
0x140009b9f  retn
```
