# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1400126dc`
- end: `0x14001279f`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1400125b0`

## callees

- `0x140001686`
- `0x14000169e`
- `0x1400122d8`
- `0x1400126dc`
- `0x14002f010`

## string_xrefs

- `0x140012750`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  int v5; // edi
  int v6; // ebp
  FARPROC RtlNotifyFeatureUsage; // rax
  HMODULE ModuleHandleW_0; // rax
  int v10; // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+34h] [rbp-34h]
  _BYTE v12[48]; // [rsp+38h] [rbp-30h] BYREF

  v3 = a2;
  v5 = a3;
  v6 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(v12, *(_QWORD *)(a1 + 8), a3, HIDWORD(a2)) + 16);
  if ( (v3 & 0x400) != 0 && v5 != 254 )
  {
    v10 = *(_DWORD *)(a1 + 24);
    v11 = (unsigned __int16)v5;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v11) |= 1u;
    RtlNotifyFeatureUsage = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_9;
    ModuleHandleW_0 = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW_0 = GetModuleHandleW_0(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW_0;
    }
    RtlNotifyFeatureUsage = GetProcAddress_0(ModuleHandleW_0, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)RtlNotifyFeatureUsage;
    if ( RtlNotifyFeatureUsage )
LABEL_9:
      ((void (__fastcall *)(int *))RtlNotifyFeatureUsage)(&v10);
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x1400126dc  mov     [rsp+arg_18], rbx
0x1400126e1  push    rbp
0x1400126e2  push    rsi
0x1400126e3  push    rdi
0x1400126e4  sub     rsp, 50h
0x1400126e8  mov     r9, rdx
0x1400126eb  mov     rbx, rdx
0x1400126ee  mov     rdx, [rcx+8]
0x1400126f2  mov     rsi, rcx
0x1400126f5  shr     r9, 20h
0x1400126f9  lea     rcx, [rsp+68h+var_30]
0x1400126fe  mov     edi, r8d
0x140012701  call    wil_details_FeatureReporting_RecordUsageInCache
0x140012706  mov     ebp, [rax+10h]
0x140012709  bt      ebx, 0Ah
0x14001270d  jnb     short loc_140012788
0x14001270f  cmp     edi, 0FEh
0x140012715  jz      short loc_140012788
0x140012717  mov     eax, [rsi+18h]
0x14001271a  mov     [rsp+68h+var_38], 0
0x140012723  mov     dword ptr [rsp+68h+var_38], eax
0x140012727  mov     word ptr [rsp+68h+var_38+4], di
0x14001272c  bt      ebx, 0Bh
0x140012730  jnb     short loc_140012738
0x140012732  or      word ptr [rsp+68h+var_38+6], 1
0x140012738  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14001273f  test    rax, rax
0x140012742  jnz     short loc_14001277E
0x140012744  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14001274b  test    rax, rax
0x14001274e  jnz     short loc_140012763
0x140012750  lea     rcx, LibFileName; "ntdll.dll"
0x140012757  call    GetModuleHandleW_0
0x14001275c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x140012763  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14001276a  mov     rcx, rax; hModule
0x14001276d  call    GetProcAddress_0
0x140012772  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140012779  test    rax, rax
0x14001277c  jz      short loc_140012788
0x14001277e  lea     rcx, [rsp+68h+var_38]
0x140012783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012788  mov     rbx, [rsp+68h+arg_18]
0x140012790  xor     eax, eax
0x140012792  test    ebp, ebp
0x140012794  setz    al
0x140012797  add     rsp, 50h
0x14001279b  pop     rdi
0x14001279c  pop     rsi
0x14001279d  pop     rbp
0x14001279e  retn
```
