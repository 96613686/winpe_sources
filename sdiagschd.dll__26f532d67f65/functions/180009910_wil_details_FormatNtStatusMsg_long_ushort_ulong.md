# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180009910`
- end: `0x18000998a`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `122`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009910`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000993a`
- `KERNEL32!GetModuleHandleW` at `0x18000993a`
- `KERNEL32!FormatMessageW` at `0x18000996d`
- `KERNEL32!FormatMessageW` at `0x18000996d`

## string_xrefs

- `0x180009933`: `ntdll.dll`

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
0x180009910  mov     [rsp+arg_0], rbx
0x180009915  mov     [rsp+arg_8], rsi
0x18000991a  push    rdi
0x18000991b  sub     rsp, 40h
0x18000991f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009926  mov     ebx, r8d
0x180009929  mov     rdi, rdx
0x18000992c  mov     esi, ecx
0x18000992e  test    rax, rax
0x180009931  jnz     short loc_18000994D
0x180009933  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000993a  call    cs:__imp_GetModuleHandleW
0x180009941  nop     dword ptr [rax+rax+00h]
0x180009946  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000994d  and     [rsp+48h+var_18], 0
0x180009953  mov     r9d, 400h; dwLanguageId
0x180009959  mov     [rsp+48h+nSize], ebx; nSize
0x18000995d  mov     r8d, esi; dwMessageId
0x180009960  mov     rdx, rax; lpSource
0x180009963  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180009968  mov     ecx, 1A00h; dwFlags
0x18000996d  call    cs:__imp_FormatMessageW
0x180009974  nop     dword ptr [rax+rax+00h]
0x180009979  mov     rbx, [rsp+48h+arg_0]
0x18000997e  mov     rsi, [rsp+48h+arg_8]
0x180009983  add     rsp, 40h
0x180009987  pop     rdi
0x180009988  retn
```
