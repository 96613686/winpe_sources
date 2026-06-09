# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180007c20`
- end: `0x180007c82`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007c20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c5e`

## string_xrefs

- `0x180007c40`: `ntdll.dll`

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
0x180007c20  push    rbx
0x180007c22  sub     rsp, 20h
0x180007c26  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180007c2d  mov     ebx, ecx
0x180007c2f  test    rax, rax
0x180007c32  jnz     short loc_180007C76
0x180007c34  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007c3b  test    rax, rax
0x180007c3e  jnz     short loc_180007C54
0x180007c40  lea     rcx, ModuleName; "ntdll.dll"
0x180007c47  call    cs:__imp_GetModuleHandleW
0x180007c4d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007c54  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180007c5b  mov     rcx, rax; hModule
0x180007c5e  call    cs:__imp_GetProcAddress
0x180007c64  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180007c6b  test    rax, rax
0x180007c6e  jnz     short loc_180007C76
0x180007c70  add     rsp, 20h
0x180007c74  pop     rbx
0x180007c75  retn
0x180007c76  mov     ecx, ebx
0x180007c78  add     rsp, 20h
0x180007c7c  pop     rbx
0x180007c7d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
