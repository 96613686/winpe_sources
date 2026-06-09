# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140004060`
- end: `0x1400040d0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140004060`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1400040ba`
- `KERNEL32!FormatMessageW` at `0x1400040ba`
- `KERNEL32!GetModuleHandleW` at `0x14000408a`
- `KERNEL32!GetModuleHandleW` at `0x14000408a`

## string_xrefs

- `0x140004083`: `ntdll.dll`

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
0x140004060  mov     [rsp+arg_0], rbx
0x140004065  mov     [rsp+arg_8], rsi
0x14000406a  push    rdi
0x14000406b  sub     rsp, 40h
0x14000406f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004076  mov     ebx, r8d
0x140004079  mov     rdi, rdx
0x14000407c  mov     esi, ecx
0x14000407e  test    rax, rax
0x140004081  jnz     short loc_140004097
0x140004083  lea     rcx, ModuleName; "ntdll.dll"
0x14000408a  call    cs:__imp_GetModuleHandleW
0x140004090  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004097  mov     [rsp+48h+Arguments], 0; Arguments
0x1400040a0  mov     r9d, 400h; dwLanguageId
0x1400040a6  mov     [rsp+48h+nSize], ebx; nSize
0x1400040aa  mov     r8d, esi; dwMessageId
0x1400040ad  mov     rdx, rax; lpSource
0x1400040b0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1400040b5  mov     ecx, 1A00h; dwFlags
0x1400040ba  call    cs:__imp_FormatMessageW
0x1400040c0  mov     rbx, [rsp+48h+arg_0]
0x1400040c5  mov     rsi, [rsp+48h+arg_8]
0x1400040ca  add     rsp, 40h
0x1400040ce  pop     rdi
0x1400040cf  retn
```
