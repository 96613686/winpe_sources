# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x1800328f0`
- end: `0x18003294e`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800328f0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003292e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003292e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032917`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032917`

## string_xrefs

- `0x180032910`: `ntdll.dll`

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
0x1800328f0  push    rbx
0x1800328f2  sub     rsp, 20h
0x1800328f6  mov     ebx, ecx
0x1800328f8  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x1800328ff  test    rax, rax
0x180032902  jnz     short loc_180032940
0x180032904  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003290b  test    rax, rax
0x18003290e  jnz     short loc_180032924
0x180032910  lea     rcx, ModuleName; "ntdll.dll"
0x180032917  call    cs:__imp_GetModuleHandleW
0x18003291d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180032924  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18003292b  mov     rcx, rax; hModule
0x18003292e  call    cs:__imp_GetProcAddress
0x180032934  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18003293b  test    rax, rax
0x18003293e  jz      short loc_180032948
0x180032940  mov     ecx, ebx
0x180032942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032947  nop
0x180032948  add     rsp, 20h
0x18003294c  pop     rbx
0x18003294d  retn
```
