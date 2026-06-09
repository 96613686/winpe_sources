# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140001c54`
- end: `0x140001d69`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400090e0`

## callees

- `0x140001978`
- `0x140001c54`
- `0x140002bb0`
- `0x140002c90`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140001d20`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140001d20`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  __int64 v5; // rax
  void (__fastcall *SystemRoutineAddress)(__int64 *); // rax
  __int64 v8; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v10[24]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v11; // [rsp+60h] [rbp-20h] BYREF
  __int64 v12; // [rsp+70h] [rbp-10h]

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v10,
         (volatile signed __int32 *)&Feature_ReFS_WIM_Mount_Support__private_reporting,
         a3,
         SHIDWORD(a2));
  v11 = *(_OWORD *)v5;
  v12 = *(_QWORD *)(v5 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(40581351, a3, 1, &Feature_ReFS_WIM_Mount_Support__private_reporting, &v11);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v8 = 40581351;
    WORD2(v8) = a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v8) |= 1u;
    SystemRoutineAddress = (void (__fastcall *)(__int64 *))g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage
      || (*(_QWORD *)&SystemRoutineName.Length = 2883626,
          SystemRoutineName.Buffer = L"RtlNotifyFeatureUsage",
          SystemRoutineAddress = (void (__fastcall *)(__int64 *))MmGetSystemRoutineAddress(&SystemRoutineName),
          (g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)SystemRoutineAddress) != 0) )
    {
      SystemRoutineAddress(&v8);
    }
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x140001c54  mov     [rsp-18h+arg_0], rbx
0x140001c59  push    rbp
0x140001c5a  push    rsi
0x140001c5b  push    rdi
0x140001c5c  mov     rbp, rsp
0x140001c5f  sub     rsp, 80h
0x140001c66  mov     rax, cs:__security_cookie
0x140001c6d  xor     rax, rsp
0x140001c70  mov     [rbp+var_8], rax
0x140001c74  mov     r9, rdx
0x140001c77  lea     rcx, [rbp+var_38]
0x140001c7b  mov     rbx, rdx
0x140001c7e  shr     r9, 20h
0x140001c82  mov     rdx, cs:off_140005EC0
0x140001c89  mov     edi, r8d
0x140001c8c  call    wil_details_FeatureReporting_RecordUsageInCache
0x140001c91  mov     esi, 1
0x140001c96  movups  xmm1, xmmword ptr [rax]
0x140001c99  movups  [rbp+var_20], xmm1
0x140001c9d  movsd   xmm0, qword ptr [rax+10h]
0x140001ca2  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140001ca9  movsd   [rbp+var_10], xmm0
0x140001cae  test    rax, rax
0x140001cb1  jz      short loc_140001CD2
0x140001cb3  mov     r9, cs:off_140005EC0
0x140001cba  lea     rcx, [rbp+var_20]
0x140001cbe  mov     [rsp+80h+var_60], rcx
0x140001cc3  mov     r8d, esi
0x140001cc6  mov     ecx, 26B38E7h
0x140001ccb  mov     edx, edi
0x140001ccd  call    _guard_dispatch_icall
0x140001cd2  bt      ebx, 0Ah
0x140001cd6  jnb     short loc_140001D41
0x140001cd8  cmp     edi, 0FEh
0x140001cde  jz      short loc_140001D41
0x140001ce0  mov     [rbp+var_50], 0
0x140001ce8  mov     dword ptr [rbp+var_50], 26B38E7h
0x140001cef  mov     word ptr [rbp+var_50+4], di
0x140001cf3  bt      ebx, 0Bh
0x140001cf7  jnb     short loc_140001CFD
0x140001cf9  or      word ptr [rbp+var_50+6], si
0x140001cfd  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140001d04  test    rax, rax
0x140001d07  jnz     short loc_140001D38
0x140001d09  lea     rax, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140001d10  mov     qword ptr [rbp+SystemRoutineName.Length], 2C002Ah
0x140001d18  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x140001d1c  mov     [rbp+SystemRoutineName.Buffer], rax
0x140001d20  call    cs:__imp_MmGetSystemRoutineAddress
0x140001d27  nop     dword ptr [rax+rax+00h]
0x140001d2c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140001d33  test    rax, rax
0x140001d36  jz      short loc_140001D41
0x140001d38  lea     rcx, [rbp+var_50]
0x140001d3c  call    _guard_dispatch_icall
0x140001d41  xor     eax, eax
0x140001d43  cmp     dword ptr [rbp+var_10], eax
0x140001d46  setz    al
0x140001d49  mov     rcx, [rbp+var_8]
0x140001d4d  xor     rcx, rsp; StackCookie
0x140001d50  call    __security_check_cookie
0x140001d55  mov     rbx, [rsp+80h+arg_0]
0x140001d5d  add     rsp, 80h
0x140001d64  pop     rdi
0x140001d65  pop     rsi
0x140001d66  pop     rbp
0x140001d67  retn
```
