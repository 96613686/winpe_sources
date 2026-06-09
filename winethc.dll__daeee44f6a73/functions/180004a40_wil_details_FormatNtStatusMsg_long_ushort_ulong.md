# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180004a40`
- end: `0x180004abd`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `125`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004a40`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180004a6a`
- `KERNEL32!GetModuleHandleW` at `0x180004a6a`
- `KERNEL32!FormatMessageW` at `0x180004aa0`
- `KERNEL32!FormatMessageW` at `0x180004aa0`

## string_xrefs

- `0x180004a63`: `ntdll.dll`

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
0x180004a40  mov     [rsp+arg_0], rbx
0x180004a45  mov     [rsp+arg_8], rsi
0x180004a4a  push    rdi
0x180004a4b  sub     rsp, 40h
0x180004a4f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004a56  mov     ebx, r8d
0x180004a59  mov     rdi, rdx
0x180004a5c  mov     esi, ecx
0x180004a5e  test    rax, rax
0x180004a61  jnz     short loc_180004A7D
0x180004a63  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180004a6a  call    cs:__imp_GetModuleHandleW
0x180004a71  nop     dword ptr [rax+rax+00h]
0x180004a76  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004a7d  mov     [rsp+48h+Arguments], 0; Arguments
0x180004a86  mov     r9d, 400h; dwLanguageId
0x180004a8c  mov     [rsp+48h+nSize], ebx; nSize
0x180004a90  mov     r8d, esi; dwMessageId
0x180004a93  mov     rdx, rax; lpSource
0x180004a96  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180004a9b  mov     ecx, 1A00h; dwFlags
0x180004aa0  call    cs:__imp_FormatMessageW
0x180004aa7  nop     dword ptr [rax+rax+00h]
0x180004aac  mov     rbx, [rsp+48h+arg_0]
0x180004ab1  mov     rsi, [rsp+48h+arg_8]
0x180004ab6  add     rsp, 40h
0x180004aba  pop     rdi
0x180004abb  retn
```
