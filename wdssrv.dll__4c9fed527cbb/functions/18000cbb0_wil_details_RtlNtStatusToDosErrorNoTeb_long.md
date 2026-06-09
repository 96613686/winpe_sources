# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000cbb0`
- end: `0x18000cc29`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `121`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000cbb0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000cbdd`
- `KERNEL32!GetModuleHandleW` at `0x18000cbdd`
- `KERNEL32!GetProcAddress` at `0x18000cbfa`
- `KERNEL32!GetProcAddress` at `0x18000cbfa`

## string_xrefs

- `0x18000cbd6`: `ntdll.dll`

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
0x18000cbb0  mov     [rsp+arg_0], rbx
0x18000cbb5  push    rdi
0x18000cbb6  sub     rsp, 20h
0x18000cbba  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000cbc1  xor     ebx, ebx
0x18000cbc3  mov     edi, ecx
0x18000cbc5  test    rax, rax
0x18000cbc8  jnz     short loc_18000CC12
0x18000cbca  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cbd1  test    rax, rax
0x18000cbd4  jnz     short loc_18000CBF0
0x18000cbd6  lea     rcx, ModuleName; "ntdll.dll"
0x18000cbdd  call    cs:__imp_GetModuleHandleW
0x18000cbe4  nop     dword ptr [rax+rax+00h]
0x18000cbe9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cbf0  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000cbf7  mov     rcx, rax; hModule
0x18000cbfa  call    cs:__imp_GetProcAddress
0x18000cc01  nop     dword ptr [rax+rax+00h]
0x18000cc06  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000cc0d  test    rax, rax
0x18000cc10  jz      short loc_18000CC1B
0x18000cc12  mov     ecx, edi
0x18000cc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc19  mov     ebx, eax
0x18000cc1b  mov     eax, ebx
0x18000cc1d  mov     rbx, [rsp+28h+arg_0]
0x18000cc22  add     rsp, 20h
0x18000cc26  pop     rdi
0x18000cc27  retn
```
