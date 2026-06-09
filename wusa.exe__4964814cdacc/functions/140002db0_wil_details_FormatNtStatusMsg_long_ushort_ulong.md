# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x140002db0`
- end: `0x140002e20`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002db0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140002dda`
- `KERNEL32!GetModuleHandleW` at `0x140002dda`
- `KERNEL32!FormatMessageW` at `0x140002e0a`
- `KERNEL32!FormatMessageW` at `0x140002e0a`

## string_xrefs

- `0x140002dd3`: `ntdll.dll`

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
0x140002db0  mov     [rsp+arg_0], rbx
0x140002db5  mov     [rsp+arg_8], rsi
0x140002dba  push    rdi
0x140002dbb  sub     rsp, 40h
0x140002dbf  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140002dc6  mov     ebx, r8d
0x140002dc9  mov     rdi, rdx
0x140002dcc  mov     esi, ecx
0x140002dce  test    rax, rax
0x140002dd1  jnz     short loc_140002DE7
0x140002dd3  lea     rcx, ModuleName; "ntdll.dll"
0x140002dda  call    cs:__imp_GetModuleHandleW
0x140002de0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140002de7  mov     [rsp+48h+Arguments], 0; Arguments
0x140002df0  mov     r9d, 400h; dwLanguageId
0x140002df6  mov     [rsp+48h+nSize], ebx; nSize
0x140002dfa  mov     r8d, esi; dwMessageId
0x140002dfd  mov     rdx, rax; lpSource
0x140002e00  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x140002e05  mov     ecx, 1A00h; dwFlags
0x140002e0a  call    cs:__imp_FormatMessageW
0x140002e10  mov     rbx, [rsp+48h+arg_0]
0x140002e15  mov     rsi, [rsp+48h+arg_8]
0x140002e1a  add     rsp, 40h
0x140002e1e  pop     rdi
0x140002e1f  retn
```
