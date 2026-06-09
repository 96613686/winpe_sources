# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1400134d0`
- end: `0x14001352e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400134d0`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001350e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001350e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400134f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400134f7`

## string_xrefs

- `0x1400134f0`: `ntdll.dll`

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
0x1400134d0  push    rbx
0x1400134d2  sub     rsp, 20h
0x1400134d6  mov     ebx, ecx
0x1400134d8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1400134df  test    rax, rax
0x1400134e2  jnz     short loc_140013520
0x1400134e4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400134eb  test    rax, rax
0x1400134ee  jnz     short loc_140013504
0x1400134f0  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1400134f7  call    cs:__imp_GetModuleHandleW
0x1400134fd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140013504  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x14001350b  mov     rcx, rax; hModule
0x14001350e  call    cs:__imp_GetProcAddress
0x140013514  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x14001351b  test    rax, rax
0x14001351e  jz      short loc_140013528
0x140013520  mov     ecx, ebx
0x140013522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013527  nop
0x140013528  add     rsp, 20h
0x14001352c  pop     rbx
0x14001352d  retn
```
