# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800090f0`
- end: `0x18000914e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800090f0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009117`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009117`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000912e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000912e`

## string_xrefs

- `0x180009110`: `ntdll.dll`

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
0x1800090f0  push    rbx
0x1800090f2  sub     rsp, 20h
0x1800090f6  mov     ebx, ecx
0x1800090f8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800090ff  test    rax, rax
0x180009102  jnz     short loc_180009140
0x180009104  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000910b  test    rax, rax
0x18000910e  jnz     short loc_180009124
0x180009110  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009117  call    cs:__imp_GetModuleHandleW
0x18000911d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009124  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000912b  mov     rcx, rax; hModule
0x18000912e  call    cs:__imp_GetProcAddress
0x180009134  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000913b  test    rax, rax
0x18000913e  jz      short loc_180009148
0x180009140  mov     ecx, ebx
0x180009142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009147  nop
0x180009148  add     rsp, 20h
0x18000914c  pop     rbx
0x18000914d  retn
```
