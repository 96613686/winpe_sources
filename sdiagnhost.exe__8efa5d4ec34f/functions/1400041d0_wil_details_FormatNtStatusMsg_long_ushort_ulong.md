# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1400041d0`
- end: `0x140004240`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400041d0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14000422a`
- `KERNEL32!FormatMessageW` at `0x14000422a`
- `KERNEL32!GetModuleHandleW` at `0x1400041fa`
- `KERNEL32!GetModuleHandleW` at `0x1400041fa`

## string_xrefs

- `0x1400041f3`: `ntdll.dll`

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
0x1400041d0  mov     [rsp+arg_0], rbx
0x1400041d5  mov     [rsp+arg_8], rsi
0x1400041da  push    rdi
0x1400041db  sub     rsp, 40h
0x1400041df  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400041e6  mov     ebx, r8d
0x1400041e9  mov     rdi, rdx
0x1400041ec  mov     esi, ecx
0x1400041ee  test    rax, rax
0x1400041f1  jnz     short loc_140004207
0x1400041f3  lea     rcx, ModuleName; "ntdll.dll"
0x1400041fa  call    cs:__imp_GetModuleHandleW
0x140004200  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004207  mov     [rsp+48h+Arguments], 0; Arguments
0x140004210  mov     r9d, 400h; dwLanguageId
0x140004216  mov     [rsp+48h+nSize], ebx; nSize
0x14000421a  mov     r8d, esi; dwMessageId
0x14000421d  mov     rdx, rax; lpSource
0x140004220  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140004225  mov     ecx, 1A00h; dwFlags
0x14000422a  call    cs:__imp_FormatMessageW
0x140004230  mov     rbx, [rsp+48h+arg_0]
0x140004235  mov     rsi, [rsp+48h+arg_8]
0x14000423a  add     rsp, 40h
0x14000423e  pop     rdi
0x14000423f  retn
```
