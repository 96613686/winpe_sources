# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180006000`
- end: `0x18000607a`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `122`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006000`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000605d`
- `KERNEL32!FormatMessageW` at `0x18000605d`
- `KERNEL32!GetModuleHandleW` at `0x18000602a`
- `KERNEL32!GetModuleHandleW` at `0x18000602a`

## string_xrefs

- `0x180006023`: `ntdll.dll`

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
0x180006000  mov     [rsp+arg_0], rbx
0x180006005  mov     [rsp+arg_8], rsi
0x18000600a  push    rdi
0x18000600b  sub     rsp, 40h
0x18000600f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006016  mov     ebx, r8d
0x180006019  mov     rdi, rdx
0x18000601c  mov     esi, ecx
0x18000601e  test    rax, rax
0x180006021  jnz     short loc_18000603D
0x180006023  lea     rcx, ModuleName; "ntdll.dll"
0x18000602a  call    cs:__imp_GetModuleHandleW
0x180006031  nop     dword ptr [rax+rax+00h]
0x180006036  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000603d  and     [rsp+48h+var_18], 0
0x180006043  mov     r9d, 400h; dwLanguageId
0x180006049  mov     [rsp+48h+nSize], ebx; nSize
0x18000604d  mov     r8d, esi; dwMessageId
0x180006050  mov     rdx, rax; lpSource
0x180006053  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180006058  mov     ecx, 1A00h; dwFlags
0x18000605d  call    cs:__imp_FormatMessageW
0x180006064  nop     dword ptr [rax+rax+00h]
0x180006069  mov     rbx, [rsp+48h+arg_0]
0x18000606e  mov     rsi, [rsp+48h+arg_8]
0x180006073  add     rsp, 40h
0x180006077  pop     rdi
0x180006078  retn
```
