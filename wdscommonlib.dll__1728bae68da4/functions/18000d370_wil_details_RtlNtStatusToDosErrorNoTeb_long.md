# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000d370`
- end: `0x18000d3e9`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `121`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000d370`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d3ba`
- `KERNEL32!GetProcAddress` at `0x18000d3ba`
- `KERNEL32!GetModuleHandleW` at `0x18000d39d`
- `KERNEL32!GetModuleHandleW` at `0x18000d39d`

## string_xrefs

- `0x18000d396`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC ProcAddress; // rax
  unsigned int v2; // ebx
  unsigned int v3; // edi
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = 0;
  v3 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v3);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v3);
  return v2;
}

```

## disassembly

```asm
0x18000d370  mov     [rsp+arg_0], rbx
0x18000d375  push    rdi
0x18000d376  sub     rsp, 20h
0x18000d37a  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000d381  xor     ebx, ebx
0x18000d383  mov     edi, ecx
0x18000d385  test    rax, rax
0x18000d388  jnz     short loc_18000D3D2
0x18000d38a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d391  test    rax, rax
0x18000d394  jnz     short loc_18000D3B0
0x18000d396  lea     rcx, ModuleName; "ntdll.dll"
0x18000d39d  call    cs:__imp_GetModuleHandleW
0x18000d3a4  nop     dword ptr [rax+rax+00h]
0x18000d3a9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d3b0  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000d3b7  mov     rcx, rax; hModule
0x18000d3ba  call    cs:__imp_GetProcAddress
0x18000d3c1  nop     dword ptr [rax+rax+00h]
0x18000d3c6  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000d3cd  test    rax, rax
0x18000d3d0  jz      short loc_18000D3DB
0x18000d3d2  mov     ecx, edi
0x18000d3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d9  mov     ebx, eax
0x18000d3db  mov     eax, ebx
0x18000d3dd  mov     rbx, [rsp+28h+arg_0]
0x18000d3e2  add     rsp, 20h
0x18000d3e6  pop     rdi
0x18000d3e7  retn
```
