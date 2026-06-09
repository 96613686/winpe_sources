# wil_details_NtQueryWnfStateData

- ea: `0x18000be68`
- end: `0x18000bf09`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800091fc`
- `0x18000bb68`

## callees

- `0x18000be68`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000beb4`
- `KERNEL32!GetProcAddress` at `0x18000beb4`
- `KERNEL32!GetModuleHandleW` at `0x18000be97`
- `KERNEL32!GetModuleHandleW` at `0x18000be97`

## string_xrefs

- `0x18000be90`: `ntdll.dll`

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
0x18000be68  mov     [rsp+arg_0], rbx
0x18000be6d  push    rdi
0x18000be6e  sub     rsp, 40h
0x18000be72  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000be79  mov     rbx, r9
0x18000be7c  mov     rdi, rcx
0x18000be7f  test    r10, r10
0x18000be82  jnz     short loc_18000BED6
0x18000be84  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000be8b  test    rax, rax
0x18000be8e  jnz     short loc_18000BEAA
0x18000be90  lea     rcx, ModuleName; "ntdll.dll"
0x18000be97  call    cs:__imp_GetModuleHandleW
0x18000be9e  nop     dword ptr [rax+rax+00h]
0x18000bea3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000beaa  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000beb1  mov     rcx, rax; hModule
0x18000beb4  call    cs:__imp_GetProcAddress
0x18000bebb  nop     dword ptr [rax+rax+00h]
0x18000bec0  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000bec7  mov     r10, rax
0x18000beca  test    rax, rax
0x18000becd  jnz     short loc_18000BED6
0x18000becf  mov     eax, 0C0000139h
0x18000bed4  jmp     short loc_18000BEFD
0x18000bed6  mov     rax, [rsp+48h+arg_28]
0x18000bedb  mov     r9, rbx
0x18000bede  mov     [rsp+48h+var_20], rax
0x18000bee3  xor     r8d, r8d
0x18000bee6  mov     rax, [rsp+48h+arg_20]
0x18000beeb  xor     edx, edx
0x18000beed  mov     [rsp+48h+var_28], rax
0x18000bef2  mov     rcx, rdi
0x18000bef5  mov     rax, r10
0x18000bef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000befd  mov     rbx, [rsp+48h+arg_0]
0x18000bf02  add     rsp, 40h
0x18000bf06  pop     rdi
0x18000bf07  retn
```
