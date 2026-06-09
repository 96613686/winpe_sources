# wil_details_NtQueryWnfStateData

- ea: `0x18000eb9c`
- end: `0x18000ec3d`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000cb4c`
- `0x18000e8e0`

## callees

- `0x18000eb9c`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ebe8`
- `KERNEL32!GetProcAddress` at `0x18000ebe8`
- `KERNEL32!GetModuleHandleW` at `0x18000ebcb`
- `KERNEL32!GetModuleHandleW` at `0x18000ebcb`

## string_xrefs

- `0x18000ebc4`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_NtQueryWnfStateData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, __int64, __int64, __int64); // r10
  HMODULE ModuleHandleW; // rax

  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000eb9c  mov     [rsp+arg_0], rbx
0x18000eba1  push    rdi
0x18000eba2  sub     rsp, 40h
0x18000eba6  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000ebad  mov     rbx, r9
0x18000ebb0  mov     rdi, rcx
0x18000ebb3  test    r10, r10
0x18000ebb6  jnz     short loc_18000EC0A
0x18000ebb8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebbf  test    rax, rax
0x18000ebc2  jnz     short loc_18000EBDE
0x18000ebc4  lea     rcx, ModuleName; "ntdll.dll"
0x18000ebcb  call    cs:__imp_GetModuleHandleW
0x18000ebd2  nop     dword ptr [rax+rax+00h]
0x18000ebd7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebde  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000ebe5  mov     rcx, rax; hModule
0x18000ebe8  call    cs:__imp_GetProcAddress
0x18000ebef  nop     dword ptr [rax+rax+00h]
0x18000ebf4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000ebfb  mov     r10, rax
0x18000ebfe  test    rax, rax
0x18000ec01  jnz     short loc_18000EC0A
0x18000ec03  mov     eax, 0C0000139h
0x18000ec08  jmp     short loc_18000EC31
0x18000ec0a  mov     rax, [rsp+48h+arg_28]
0x18000ec0f  mov     r9, rbx
0x18000ec12  mov     [rsp+48h+var_20], rax
0x18000ec17  xor     r8d, r8d
0x18000ec1a  mov     rax, [rsp+48h+arg_20]
0x18000ec1f  xor     edx, edx
0x18000ec21  mov     [rsp+48h+var_28], rax
0x18000ec26  mov     rcx, rdi
0x18000ec29  mov     rax, r10
0x18000ec2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec31  mov     rbx, [rsp+48h+arg_0]
0x18000ec36  add     rsp, 40h
0x18000ec3a  pop     rdi
0x18000ec3b  retn
```
