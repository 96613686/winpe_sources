# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000b600`
- end: `0x18000b66c`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `108`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000b600`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b62d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b62d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b644`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b644`

## string_xrefs

- `0x18000b626`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  unsigned int v1; // edi
  FARPROC ProcAddress; // rax
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rax

  v1 = (unsigned int)this;
  ProcAddress = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v3 = 0;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v1);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v1);
  return v3;
}

```

## disassembly

```asm
0x18000b600  mov     [rsp+arg_0], rbx
0x18000b605  push    rdi
0x18000b606  sub     rsp, 20h
0x18000b60a  mov     edi, ecx
0x18000b60c  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000b613  xor     ebx, ebx
0x18000b615  test    rax, rax
0x18000b618  jnz     short loc_18000B656
0x18000b61a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b621  test    rax, rax
0x18000b624  jnz     short loc_18000B63A
0x18000b626  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000b62d  call    cs:__imp_GetModuleHandleW
0x18000b633  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b63a  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000b641  mov     rcx, rax; hModule
0x18000b644  call    cs:__imp_GetProcAddress
0x18000b64a  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000b651  test    rax, rax
0x18000b654  jz      short loc_18000B65F
0x18000b656  mov     ecx, edi
0x18000b658  call    _guard_dispatch_icall
0x18000b65d  mov     ebx, eax
0x18000b65f  mov     eax, ebx
0x18000b661  mov     rbx, [rsp+28h+arg_0]
0x18000b666  add     rsp, 20h
0x18000b66a  pop     rdi
0x18000b66b  retn
```
