# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14001e9b4`
- end: `0x14001ea35`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140019420`

## callees

- `0x14001e9b4`
- `0x14001ea3c`
- `0x14001eda4`
- `0x140039780`

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
0x14001e9b4  mov     [rsp+arg_0], rbx
0x14001e9b9  mov     [rsp+arg_10], r8d
0x14001e9be  push    rdi
0x14001e9bf  sub     rsp, 50h
0x14001e9c3  mov     edi, edx
0x14001e9c5  mov     r9, rdx
0x14001e9c8  mov     rbx, rcx
0x14001e9cb  and     edi, 1
0x14001e9ce  mov     edx, edi
0x14001e9d0  mov     ecx, r8d
0x14001e9d3  call    wil_details_MapReportingKind
0x14001e9d8  mov     r8d, eax
0x14001e9db  mov     rdx, r9
0x14001e9de  mov     rcx, rbx
0x14001e9e1  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14001e9e6  test    eax, eax
0x14001e9e8  jz      short loc_14001EA29
0x14001e9ea  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14001e9f1  test    rax, rax
0x14001e9f4  jz      short loc_14001EA29
0x14001e9f6  mov     rdx, [rbx+10h]
0x14001e9fa  lea     rcx, [rsp+58h+arg_10]
0x14001e9ff  mov     [rsp+58h+var_20], 1
0x14001ea08  mov     r9d, edi
0x14001ea0b  mov     [rsp+58h+var_28], 0
0x14001ea10  xor     r8d, r8d
0x14001ea13  mov     [rsp+58h+var_30], 0
0x14001ea1c  mov     [rsp+58h+var_38], rcx
0x14001ea21  mov     ecx, [rbx+18h]
0x14001ea24  call    _guard_dispatch_icall
0x14001ea29  mov     rbx, [rsp+58h+arg_0]
0x14001ea2e  add     rsp, 50h
0x14001ea32  pop     rdi
0x14001ea33  retn
```
