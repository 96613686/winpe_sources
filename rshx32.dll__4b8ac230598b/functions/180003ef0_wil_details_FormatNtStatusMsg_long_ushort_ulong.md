# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180003ef0`
- end: `0x180003f60`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003ef0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f1a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003f4a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003f4a`

## string_xrefs

- `0x180003f13`: `ntdll.dll`

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
0x180003ef0  mov     [rsp+arg_0], rbx
0x180003ef5  mov     [rsp+arg_8], rsi
0x180003efa  push    rdi
0x180003efb  sub     rsp, 40h
0x180003eff  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003f06  mov     ebx, r8d
0x180003f09  mov     rdi, rdx
0x180003f0c  mov     esi, ecx
0x180003f0e  test    rax, rax
0x180003f11  jnz     short loc_180003F27
0x180003f13  lea     rcx, ModuleName; "ntdll.dll"
0x180003f1a  call    cs:__imp_GetModuleHandleW
0x180003f20  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003f27  mov     [rsp+48h+Arguments], 0; Arguments
0x180003f30  mov     r9d, 400h; dwLanguageId
0x180003f36  mov     [rsp+48h+nSize], ebx; nSize
0x180003f3a  mov     r8d, esi; dwMessageId
0x180003f3d  mov     rdx, rax; lpSource
0x180003f40  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x180003f45  mov     ecx, 1A00h; dwFlags
0x180003f4a  call    cs:__imp_FormatMessageW
0x180003f50  mov     rbx, [rsp+48h+arg_0]
0x180003f55  mov     rsi, [rsp+48h+arg_8]
0x180003f5a  add     rsp, 40h
0x180003f5e  pop     rdi
0x180003f5f  retn
```
