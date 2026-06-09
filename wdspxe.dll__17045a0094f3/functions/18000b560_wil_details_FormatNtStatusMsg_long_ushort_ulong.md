# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000b560`
- end: `0x18000b5da`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `122`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b560`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000b5bd`
- `KERNEL32!FormatMessageW` at `0x18000b5bd`
- `KERNEL32!GetModuleHandleW` at `0x18000b58a`
- `KERNEL32!GetModuleHandleW` at `0x18000b58a`

## string_xrefs

- `0x18000b583`: `ntdll.dll`

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
0x18000b560  mov     [rsp+arg_0], rbx
0x18000b565  mov     [rsp+arg_8], rsi
0x18000b56a  push    rdi
0x18000b56b  sub     rsp, 40h
0x18000b56f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b576  mov     ebx, r8d
0x18000b579  mov     rdi, rdx
0x18000b57c  mov     esi, ecx
0x18000b57e  test    rax, rax
0x18000b581  jnz     short loc_18000B59D
0x18000b583  lea     rcx, ModuleName; "ntdll.dll"
0x18000b58a  call    cs:__imp_GetModuleHandleW
0x18000b591  nop     dword ptr [rax+rax+00h]
0x18000b596  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b59d  and     [rsp+48h+var_18], 0
0x18000b5a3  mov     r9d, 400h; dwLanguageId
0x18000b5a9  mov     [rsp+48h+nSize], ebx; nSize
0x18000b5ad  mov     r8d, esi; dwMessageId
0x18000b5b0  mov     rdx, rax; lpSource
0x18000b5b3  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000b5b8  mov     ecx, 1A00h; dwFlags
0x18000b5bd  call    cs:__imp_FormatMessageW
0x18000b5c4  nop     dword ptr [rax+rax+00h]
0x18000b5c9  mov     rbx, [rsp+48h+arg_0]
0x18000b5ce  mov     rsi, [rsp+48h+arg_8]
0x18000b5d3  add     rsp, 40h
0x18000b5d7  pop     rdi
0x18000b5d8  retn
```
