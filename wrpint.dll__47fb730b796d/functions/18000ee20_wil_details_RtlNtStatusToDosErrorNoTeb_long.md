# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000ee20`
- end: `0x18000ee82`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ee20`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000ee5e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000ee5e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000ee47`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000ee47`

## string_xrefs

- `0x18000ee40`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC result; // rax
  unsigned int v2; // ebx
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  return result;
}

```

## disassembly

```asm
0x18000ee20  push    rbx
0x18000ee22  sub     rsp, 20h
0x18000ee26  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000ee2d  mov     ebx, ecx
0x18000ee2f  test    rax, rax
0x18000ee32  jnz     short loc_18000EE76
0x18000ee34  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ee3b  test    rax, rax
0x18000ee3e  jnz     short loc_18000EE54
0x18000ee40  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ee47  call    cs:__imp_GetModuleHandleW
0x18000ee4d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ee54  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000ee5b  mov     rcx, rax; hModule
0x18000ee5e  call    cs:__imp_GetProcAddress
0x18000ee64  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000ee6b  test    rax, rax
0x18000ee6e  jnz     short loc_18000EE76
0x18000ee70  add     rsp, 20h
0x18000ee74  pop     rbx
0x18000ee75  retn
0x18000ee76  mov     ecx, ebx
0x18000ee78  add     rsp, 20h
0x18000ee7c  pop     rbx
0x18000ee7d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
