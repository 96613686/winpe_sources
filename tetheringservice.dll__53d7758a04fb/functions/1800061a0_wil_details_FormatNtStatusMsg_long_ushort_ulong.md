# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x1800061a0`
- end: `0x180006210`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800061a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800061fa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800061fa`

## string_xrefs

- `0x1800061c3`: `ntdll.dll`

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
0x1800061a0  mov     [rsp+arg_0], rbx
0x1800061a5  mov     [rsp+arg_8], rsi
0x1800061aa  push    rdi
0x1800061ab  sub     rsp, 40h
0x1800061af  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800061b6  mov     ebx, r8d
0x1800061b9  mov     rdi, rdx
0x1800061bc  mov     esi, ecx
0x1800061be  test    rax, rax
0x1800061c1  jnz     short loc_1800061D7
0x1800061c3  lea     rcx, ModuleName; "ntdll.dll"
0x1800061ca  call    cs:__imp_GetModuleHandleW
0x1800061d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800061d7  mov     [rsp+48h+Arguments], 0; Arguments
0x1800061e0  mov     r9d, 400h; dwLanguageId
0x1800061e6  mov     [rsp+48h+nSize], ebx; nSize
0x1800061ea  mov     r8d, esi; dwMessageId
0x1800061ed  mov     rdx, rax; lpSource
0x1800061f0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x1800061f5  mov     ecx, 1A00h; dwFlags
0x1800061fa  call    cs:__imp_FormatMessageW
0x180006200  mov     rbx, [rsp+48h+arg_0]
0x180006205  mov     rsi, [rsp+48h+arg_8]
0x18000620a  add     rsp, 40h
0x18000620e  pop     rdi
0x18000620f  retn
```
