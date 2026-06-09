# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x1400119f0`
- end: `0x140011a71`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140010c94`

## callees

- `0x140010e9c`
- `0x1400119f0`
- `0x140011a78`
- `0x140014d50`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        __int64 a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v4; // edi
  unsigned int v5; // eax
  __int64 v6; // r9
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v4 = a2 & 1;
  v5 = wil_details_MapReportingKind((unsigned int)a3, a2 & 1, a3, a2);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     v6,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v8 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v4, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400119f0  mov     [rsp+arg_0], rbx
0x1400119f5  mov     [rsp+arg_10], r8d
0x1400119fa  push    rdi
0x1400119fb  sub     rsp, 50h
0x1400119ff  mov     edi, edx
0x140011a01  mov     r9, rdx
0x140011a04  mov     rbx, rcx
0x140011a07  and     edi, 1
0x140011a0a  mov     edx, edi
0x140011a0c  mov     ecx, r8d
0x140011a0f  call    wil_details_MapReportingKind
0x140011a14  mov     r8d, eax
0x140011a17  mov     rdx, r9
0x140011a1a  mov     rcx, rbx
0x140011a1d  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140011a22  test    eax, eax
0x140011a24  jz      short loc_140011A65
0x140011a26  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140011a2d  test    rax, rax
0x140011a30  jz      short loc_140011A65
0x140011a32  mov     rdx, [rbx+10h]
0x140011a36  lea     rcx, [rsp+58h+arg_10]
0x140011a3b  mov     [rsp+58h+var_20], 1
0x140011a44  mov     r9d, edi
0x140011a47  mov     [rsp+58h+var_28], 0
0x140011a4c  xor     r8d, r8d
0x140011a4f  mov     [rsp+58h+var_30], 0
0x140011a58  mov     [rsp+58h+var_38], rcx
0x140011a5d  mov     ecx, [rbx+18h]
0x140011a60  call    _guard_dispatch_icall
0x140011a65  mov     rbx, [rsp+58h+arg_0]
0x140011a6a  add     rsp, 50h
0x140011a6e  pop     rdi
0x140011a6f  retn
```
