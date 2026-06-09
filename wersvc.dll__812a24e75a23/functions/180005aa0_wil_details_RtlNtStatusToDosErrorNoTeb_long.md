# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180005aa0`
- end: `0x180005afe`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005aa0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ac7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ac7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ade`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ade`

## string_xrefs

- `0x180005ac0`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005aa0  push    rbx
0x180005aa2  sub     rsp, 20h
0x180005aa6  mov     ebx, ecx
0x180005aa8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180005aaf  test    rax, rax
0x180005ab2  jnz     short loc_180005AF0
0x180005ab4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005abb  test    rax, rax
0x180005abe  jnz     short loc_180005AD4
0x180005ac0  lea     rcx, Src; "ntdll.dll"
0x180005ac7  call    cs:__imp_GetModuleHandleW
0x180005acd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005ad4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180005adb  mov     rcx, rax; hModule
0x180005ade  call    cs:__imp_GetProcAddress
0x180005ae4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180005aeb  test    rax, rax
0x180005aee  jz      short loc_180005AF8
0x180005af0  mov     ecx, ebx
0x180005af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af7  nop
0x180005af8  add     rsp, 20h
0x180005afc  pop     rbx
0x180005afd  retn
```
