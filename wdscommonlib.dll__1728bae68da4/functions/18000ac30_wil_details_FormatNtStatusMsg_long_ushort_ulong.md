# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18000ac30`
- end: `0x18000acaa`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `122`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ac30`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000ac8d`
- `KERNEL32!FormatMessageW` at `0x18000ac8d`
- `KERNEL32!GetModuleHandleW` at `0x18000ac5a`
- `KERNEL32!GetModuleHandleW` at `0x18000ac5a`

## string_xrefs

- `0x18000ac53`: `ntdll.dll`

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
0x18000ac30  mov     [rsp+arg_0], rbx
0x18000ac35  mov     [rsp+arg_8], rsi
0x18000ac3a  push    rdi
0x18000ac3b  sub     rsp, 40h
0x18000ac3f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ac46  mov     ebx, r8d
0x18000ac49  mov     rdi, rdx
0x18000ac4c  mov     esi, ecx
0x18000ac4e  test    rax, rax
0x18000ac51  jnz     short loc_18000AC6D
0x18000ac53  lea     rcx, ModuleName; "ntdll.dll"
0x18000ac5a  call    cs:__imp_GetModuleHandleW
0x18000ac61  nop     dword ptr [rax+rax+00h]
0x18000ac66  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ac6d  and     [rsp+48h+var_18], 0
0x18000ac73  mov     r9d, 400h; dwLanguageId
0x18000ac79  mov     [rsp+48h+nSize], ebx; nSize
0x18000ac7d  mov     r8d, esi; dwMessageId
0x18000ac80  mov     rdx, rax; lpSource
0x18000ac83  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000ac88  mov     ecx, 1A00h; dwFlags
0x18000ac8d  call    cs:__imp_FormatMessageW
0x18000ac94  nop     dword ptr [rax+rax+00h]
0x18000ac99  mov     rbx, [rsp+48h+arg_0]
0x18000ac9e  mov     rsi, [rsp+48h+arg_8]
0x18000aca3  add     rsp, 40h
0x18000aca7  pop     rdi
0x18000aca8  retn
```
