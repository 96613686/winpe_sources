# wil_details_NtUpdateWnfStateData

- ea: `0x18000e2dc`
- end: `0x18000e386`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000cf7c`
- `0x18000e09c`

## callees

- `0x18000e2dc`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e313`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e313`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e32a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e32a`

## string_xrefs

- `0x18000e30c`: `ntdll.dll`
- `0x18000e320`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10
  HMODULE ModuleHandleW; // rax

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000e2dc  mov     [rsp+arg_0], rbx
0x18000e2e1  mov     [rsp+arg_8], rsi
0x18000e2e6  push    rdi
0x18000e2e7  sub     rsp, 40h
0x18000e2eb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e2f2  mov     ebx, r8d
0x18000e2f5  mov     rdi, rdx
0x18000e2f8  mov     rsi, rcx
0x18000e2fb  test    r10, r10
0x18000e2fe  jnz     short loc_18000E346
0x18000e300  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e307  test    rax, rax
0x18000e30a  jnz     short loc_18000E320
0x18000e30c  lea     rcx, ModuleName; "ntdll.dll"
0x18000e313  call    cs:__imp_GetModuleHandleW
0x18000e319  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e320  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000e327  mov     rcx, rax; hModule
0x18000e32a  call    cs:__imp_GetProcAddress
0x18000e330  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000e337  mov     r10, rax
0x18000e33a  test    rax, rax
0x18000e33d  jnz     short loc_18000E346
0x18000e33f  mov     eax, 0C0000139h
0x18000e344  jmp     short loc_18000E376
0x18000e346  mov     eax, [rsp+48h+arg_30]
0x18000e34d  xor     r9d, r9d
0x18000e350  mov     [rsp+48h+var_18], eax
0x18000e354  mov     r8d, ebx
0x18000e357  mov     eax, [rsp+48h+arg_28]
0x18000e35b  mov     rdx, rdi
0x18000e35e  mov     [rsp+48h+var_20], eax
0x18000e362  mov     rcx, rsi
0x18000e365  mov     rax, r10
0x18000e368  mov     [rsp+48h+var_28], 0
0x18000e371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e376  mov     rbx, [rsp+48h+arg_0]
0x18000e37b  mov     rsi, [rsp+48h+arg_8]
0x18000e380  add     rsp, 40h
0x18000e384  pop     rdi
0x18000e385  retn
```
