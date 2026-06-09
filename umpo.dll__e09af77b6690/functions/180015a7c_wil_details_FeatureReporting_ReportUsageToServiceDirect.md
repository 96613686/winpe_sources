# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180015a7c`
- end: `0x180015b1d`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `161`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180015950`

## callees

- `0x1800157cc`
- `0x180015a7c`
- `0x180015da4`
- `0x180019010`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  int v5; // edi
  int v6; // ebp
  void (__fastcall *NtDllProcedureAddress)(int *); // rax
  int v9; // [rsp+30h] [rbp-38h] BYREF
  int v10; // [rsp+34h] [rbp-34h]
  _BYTE v11[48]; // [rsp+38h] [rbp-30h] BYREF

  v3 = a2;
  v5 = a3;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v11,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && v5 != 254 )
  {
    v9 = *(_DWORD *)(a1 + 24);
    v10 = (unsigned __int16)v5;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v10) |= 1u;
    NtDllProcedureAddress = (void (__fastcall *)(int *))g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage
      || (NtDllProcedureAddress = (void (__fastcall *)(int *))wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage"),
          (g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress) != 0) )
    {
      NtDllProcedureAddress(&v9);
    }
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x180015a7c  mov     [rsp+arg_18], rbx
0x180015a81  push    rbp
0x180015a82  push    rsi
0x180015a83  push    rdi
0x180015a84  sub     rsp, 50h
0x180015a88  mov     r9, rdx
0x180015a8b  mov     rbx, rdx
0x180015a8e  mov     rdx, [rcx+8]
0x180015a92  mov     rsi, rcx
0x180015a95  shr     r9, 20h
0x180015a99  lea     rcx, [rsp+68h+var_30]
0x180015a9e  mov     edi, r8d
0x180015aa1  call    wil_details_FeatureReporting_RecordUsageInCache
0x180015aa6  mov     ebp, [rax+10h]
0x180015aa9  bt      ebx, 0Ah
0x180015aad  jnb     short loc_180015B06
0x180015aaf  cmp     edi, 0FEh
0x180015ab5  jz      short loc_180015B06
0x180015ab7  mov     eax, [rsi+18h]
0x180015aba  mov     [rsp+68h+var_38], 0
0x180015ac3  mov     dword ptr [rsp+68h+var_38], eax
0x180015ac7  mov     word ptr [rsp+68h+var_38+4], di
0x180015acc  bt      ebx, 0Bh
0x180015ad0  jnb     short loc_180015AD8
0x180015ad2  or      word ptr [rsp+68h+var_38+6], 1
0x180015ad8  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180015adf  test    rax, rax
0x180015ae2  jnz     short loc_180015AFC
0x180015ae4  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180015aeb  call    wil_details_GetNtDllProcedureAddress
0x180015af0  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180015af7  test    rax, rax
0x180015afa  jz      short loc_180015B06
0x180015afc  lea     rcx, [rsp+68h+var_38]
0x180015b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b06  mov     rbx, [rsp+68h+arg_18]
0x180015b0e  xor     eax, eax
0x180015b10  test    ebp, ebp
0x180015b12  setz    al
0x180015b15  add     rsp, 50h
0x180015b19  pop     rdi
0x180015b1a  pop     rsi
0x180015b1b  pop     rbp
0x180015b1c  retn
```
