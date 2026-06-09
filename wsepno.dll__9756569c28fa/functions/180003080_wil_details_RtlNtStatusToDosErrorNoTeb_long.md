# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180003080`
- end: `0x1800030de`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003080`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800030be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800030be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800030a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800030a7`

## string_xrefs

- `0x1800030a0`: `ntdll.dll`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180003080  push    rbx
0x180003082  sub     rsp, 20h
0x180003086  mov     ebx, ecx
0x180003088  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000308f  test    rax, rax
0x180003092  jnz     short loc_1800030D0
0x180003094  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000309b  test    rax, rax
0x18000309e  jnz     short loc_1800030B4
0x1800030a0  lea     rcx, ModuleName; "ntdll.dll"
0x1800030a7  call    cs:__imp_GetModuleHandleW
0x1800030ad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800030b4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800030bb  mov     rcx, rax; hModule
0x1800030be  call    cs:__imp_GetProcAddress
0x1800030c4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800030cb  test    rax, rax
0x1800030ce  jz      short loc_1800030D8
0x1800030d0  mov     ecx, ebx
0x1800030d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d7  nop
0x1800030d8  add     rsp, 20h
0x1800030dc  pop     rbx
0x1800030dd  retn
```
