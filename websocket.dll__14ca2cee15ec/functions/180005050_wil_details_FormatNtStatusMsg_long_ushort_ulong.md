# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005050`
- end: `0x1800050c0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005050`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000507a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000507a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800050aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800050aa`

## string_xrefs

- `0x180005073`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180005050  mov     [rsp+arg_0], rbx
0x180005055  mov     [rsp+arg_8], rsi
0x18000505a  push    rdi
0x18000505b  sub     rsp, 40h
0x18000505f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005066  mov     ebx, r8d
0x180005069  mov     rdi, rdx
0x18000506c  mov     esi, ecx
0x18000506e  test    rax, rax
0x180005071  jnz     short loc_180005087
0x180005073  lea     rcx, ModuleName; "ntdll.dll"
0x18000507a  call    cs:__imp_GetModuleHandleW
0x180005080  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005087  mov     [rsp+48h+Arguments], 0; Arguments
0x180005090  mov     r9d, 400h; dwLanguageId
0x180005096  mov     [rsp+48h+nSize], ebx; nSize
0x18000509a  mov     r8d, esi; dwMessageId
0x18000509d  mov     rdx, rax; lpSource
0x1800050a0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800050a5  mov     ecx, 1A00h; dwFlags
0x1800050aa  call    cs:__imp_FormatMessageW
0x1800050b0  mov     rbx, [rsp+48h+arg_0]
0x1800050b5  mov     rsi, [rsp+48h+arg_8]
0x1800050ba  add     rsp, 40h
0x1800050be  pop     rdi
0x1800050bf  retn
```
