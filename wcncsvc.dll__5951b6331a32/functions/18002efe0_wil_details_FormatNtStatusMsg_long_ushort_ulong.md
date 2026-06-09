# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x18002efe0`
- end: `0x18002f050`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002efe0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f00a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f00a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002f03a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002f03a`

## string_xrefs

- `0x18002f003`: `ntdll.dll`

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
0x18002efe0  mov     [rsp+arg_0], rbx
0x18002efe5  mov     [rsp+arg_8], rsi
0x18002efea  push    rdi
0x18002efeb  sub     rsp, 40h
0x18002efef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002eff6  mov     ebx, r8d
0x18002eff9  mov     rdi, rdx
0x18002effc  mov     esi, ecx
0x18002effe  test    rax, rax
0x18002f001  jnz     short loc_18002F017
0x18002f003  lea     rcx, ModuleName; "ntdll.dll"
0x18002f00a  call    cs:__imp_GetModuleHandleW
0x18002f010  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002f017  mov     [rsp+48h+Arguments], 0; Arguments
0x18002f020  mov     r9d, 400h; dwLanguageId
0x18002f026  mov     [rsp+48h+nSize], ebx; nSize
0x18002f02a  mov     r8d, esi; dwMessageId
0x18002f02d  mov     rdx, rax; lpSource
0x18002f030  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18002f035  mov     ecx, 1A00h; dwFlags
0x18002f03a  call    cs:__imp_FormatMessageW
0x18002f040  mov     rbx, [rsp+48h+arg_0]
0x18002f045  mov     rsi, [rsp+48h+arg_8]
0x18002f04a  add     rsp, 40h
0x18002f04e  pop     rdi
0x18002f04f  retn
```
