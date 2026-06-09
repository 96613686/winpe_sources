# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180008bb0`
- end: `0x180008c2a`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `122`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008bb0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180008c0d`
- `KERNEL32!FormatMessageW` at `0x180008c0d`
- `KERNEL32!GetModuleHandleW` at `0x180008bda`
- `KERNEL32!GetModuleHandleW` at `0x180008bda`

## string_xrefs

- `0x180008bd3`: `ntdll.dll`

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
0x180008bb0  mov     [rsp+arg_0], rbx
0x180008bb5  mov     [rsp+arg_8], rsi
0x180008bba  push    rdi
0x180008bbb  sub     rsp, 40h
0x180008bbf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008bc6  mov     ebx, r8d
0x180008bc9  mov     rdi, rdx
0x180008bcc  mov     esi, ecx
0x180008bce  test    rax, rax
0x180008bd1  jnz     short loc_180008BED
0x180008bd3  lea     rcx, ModuleName; "ntdll.dll"
0x180008bda  call    cs:__imp_GetModuleHandleW
0x180008be1  nop     dword ptr [rax+rax+00h]
0x180008be6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008bed  and     [rsp+48h+var_18], 0
0x180008bf3  mov     r9d, 400h; dwLanguageId
0x180008bf9  mov     [rsp+48h+nSize], ebx; nSize
0x180008bfd  mov     r8d, esi; dwMessageId
0x180008c00  mov     rdx, rax; lpSource
0x180008c03  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180008c08  mov     ecx, 1A00h; dwFlags
0x180008c0d  call    cs:__imp_FormatMessageW
0x180008c14  nop     dword ptr [rax+rax+00h]
0x180008c19  mov     rbx, [rsp+48h+arg_0]
0x180008c1e  mov     rsi, [rsp+48h+arg_8]
0x180008c23  add     rsp, 40h
0x180008c27  pop     rdi
0x180008c28  retn
```
