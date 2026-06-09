# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000a070`
- end: `0x18000a0ce`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a070`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a0ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a097`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a097`

## string_xrefs

- `0x18000a090`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  unsigned int v1; // ebx
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  v1 = (unsigned int)this;
  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  return result;
}

```

## disassembly

```asm
0x18000a070  push    rbx
0x18000a072  sub     rsp, 20h
0x18000a076  mov     ebx, ecx
0x18000a078  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000a07f  test    rax, rax
0x18000a082  jnz     short loc_18000A0C0
0x18000a084  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a08b  test    rax, rax
0x18000a08e  jnz     short loc_18000A0A4
0x18000a090  lea     rcx, ModuleName; "ntdll.dll"
0x18000a097  call    cs:__imp_GetModuleHandleW
0x18000a09d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a0a4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000a0ab  mov     rcx, rax; hModule
0x18000a0ae  call    cs:__imp_GetProcAddress
0x18000a0b4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000a0bb  test    rax, rax
0x18000a0be  jz      short loc_18000A0C8
0x18000a0c0  mov     ecx, ebx
0x18000a0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c7  nop
0x18000a0c8  add     rsp, 20h
0x18000a0cc  pop     rbx
0x18000a0cd  retn
```
