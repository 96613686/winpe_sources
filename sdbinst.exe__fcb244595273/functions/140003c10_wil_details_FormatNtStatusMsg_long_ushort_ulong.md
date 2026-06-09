# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140003c10`
- end: `0x140003c80`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003c10`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140003c6a`
- `KERNEL32!FormatMessageW` at `0x140003c6a`
- `KERNEL32!GetModuleHandleW` at `0x140003c3a`
- `KERNEL32!GetModuleHandleW` at `0x140003c3a`

## string_xrefs

- `0x140003c33`: `ntdll.dll`

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
0x140003c10  mov     [rsp+arg_0], rbx
0x140003c15  mov     [rsp+arg_8], rsi
0x140003c1a  push    rdi
0x140003c1b  sub     rsp, 40h
0x140003c1f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003c26  mov     ebx, r8d
0x140003c29  mov     rdi, rdx
0x140003c2c  mov     esi, ecx
0x140003c2e  test    rax, rax
0x140003c31  jnz     short loc_140003C47
0x140003c33  lea     rcx, LibFileName; "ntdll.dll"
0x140003c3a  call    cs:__imp_GetModuleHandleW
0x140003c40  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140003c47  mov     [rsp+48h+Arguments], 0; Arguments
0x140003c50  mov     r9d, 400h; dwLanguageId
0x140003c56  mov     [rsp+48h+nSize], ebx; nSize
0x140003c5a  mov     r8d, esi; dwMessageId
0x140003c5d  mov     rdx, rax; lpSource
0x140003c60  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140003c65  mov     ecx, 1A00h; dwFlags
0x140003c6a  call    cs:__imp_FormatMessageW
0x140003c70  mov     rbx, [rsp+48h+arg_0]
0x140003c75  mov     rsi, [rsp+48h+arg_8]
0x140003c7a  add     rsp, 40h
0x140003c7e  pop     rdi
0x140003c7f  retn
```
