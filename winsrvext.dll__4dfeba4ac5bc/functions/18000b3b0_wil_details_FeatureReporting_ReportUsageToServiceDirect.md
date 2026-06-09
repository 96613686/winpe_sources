# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000b3b0`
- end: `0x18000b483`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000b280`

## callees

- `0x18000af94`
- `0x18000b3b0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b433`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b433`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b450`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b450`

## string_xrefs

- `0x18000b42c`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, int a3, int a4)
{
  __int16 v4; // bx
  int v7; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v11; // [rsp+30h] [rbp-48h] BYREF
  int v12; // [rsp+34h] [rbp-44h]
  char v13; // [rsp+38h] [rbp-40h] BYREF

  v4 = a2;
  v7 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     (unsigned int)&v13,
                     *(_QWORD *)(a1 + 8),
                     a3,
                     HIDWORD(a2),
                     a4)
                 + 16);
  if ( (v4 & 0x400) != 0 && a3 != 254 )
  {
    v11 = *(_DWORD *)(a1 + 24);
    v12 = (unsigned __int16)a3;
    if ( (v4 & 0x800) != 0 )
      HIWORD(v12) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_9;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_9:
      ((void (__fastcall *)(int *))ProcAddress)(&v11);
  }
  return v7 == 0;
}

```

## disassembly

```asm
0x18000b3b0  push    rbx
0x18000b3b2  push    rbp
0x18000b3b3  push    rsi
0x18000b3b4  push    rdi
0x18000b3b5  sub     rsp, 58h
0x18000b3b9  mov     rax, r9
0x18000b3bc  mov     rbx, rdx
0x18000b3bf  mov     r9, rdx
0x18000b3c2  mov     [rsp+78h+var_58], eax
0x18000b3c6  mov     rdx, [rcx+8]
0x18000b3ca  mov     rsi, rcx
0x18000b3cd  shr     r9, 20h
0x18000b3d1  lea     rcx, [rsp+78h+var_40]
0x18000b3d6  mov     edi, r8d
0x18000b3d9  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000b3de  mov     ebp, [rax+10h]
0x18000b3e1  bt      ebx, 0Ah
0x18000b3e5  jnb     loc_18000B472
0x18000b3eb  cmp     edi, 0FEh
0x18000b3f1  jz      short loc_18000B472
0x18000b3f3  mov     eax, [rsi+18h]
0x18000b3f6  mov     [rsp+78h+var_48], 0
0x18000b3ff  mov     dword ptr [rsp+78h+var_48], eax
0x18000b403  mov     word ptr [rsp+78h+var_48+4], di
0x18000b408  bt      ebx, 0Bh
0x18000b40c  jnb     short loc_18000B414
0x18000b40e  or      word ptr [rsp+78h+var_48+6], 1
0x18000b414  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b41b  test    rax, rax
0x18000b41e  jnz     short loc_18000B468
0x18000b420  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000b427  test    rax, rax
0x18000b42a  jnz     short loc_18000B446
0x18000b42c  lea     rcx, ModuleName; "ntdll.dll"
0x18000b433  call    cs:__imp_GetModuleHandleW
0x18000b43a  nop     dword ptr [rax+rax+00h]
0x18000b43f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000b446  lea     rdx, ProcName; "RtlNotifyFeatureUsage"
0x18000b44d  mov     rcx, rax; hModule
0x18000b450  call    cs:__imp_GetProcAddress
0x18000b457  nop     dword ptr [rax+rax+00h]
0x18000b45c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b463  test    rax, rax
0x18000b466  jz      short loc_18000B472
0x18000b468  lea     rcx, [rsp+78h+var_48]
0x18000b46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b472  xor     eax, eax
0x18000b474  test    ebp, ebp
0x18000b476  setz    al
0x18000b479  add     rsp, 58h
0x18000b47d  pop     rdi
0x18000b47e  pop     rsi
0x18000b47f  pop     rbp
0x18000b480  pop     rbx
0x18000b481  retn
```
