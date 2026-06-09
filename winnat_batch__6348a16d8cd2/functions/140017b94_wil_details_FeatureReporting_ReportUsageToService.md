# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140017b94`
- end: `0x140017c15`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140017fbc`

## callees

- `0x140017b94`
- `0x140017c1c`
- `0x14001803c`
- `0x14001ef70`

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
0x140017b94  mov     [rsp+arg_0], rbx
0x140017b99  mov     [rsp+arg_10], r8d
0x140017b9e  push    rdi
0x140017b9f  sub     rsp, 50h
0x140017ba3  mov     edi, edx
0x140017ba5  mov     r9, rdx
0x140017ba8  mov     rbx, rcx
0x140017bab  and     edi, 1
0x140017bae  mov     edx, edi
0x140017bb0  mov     ecx, r8d
0x140017bb3  call    wil_details_MapReportingKind
0x140017bb8  mov     r8d, eax
0x140017bbb  mov     rdx, r9
0x140017bbe  mov     rcx, rbx
0x140017bc1  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140017bc6  test    eax, eax
0x140017bc8  jz      short loc_140017C09
0x140017bca  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140017bd1  test    rax, rax
0x140017bd4  jz      short loc_140017C09
0x140017bd6  mov     rdx, [rbx+10h]
0x140017bda  lea     rcx, [rsp+58h+arg_10]
0x140017bdf  mov     [rsp+58h+var_20], 1
0x140017be8  mov     r9d, edi
0x140017beb  mov     [rsp+58h+var_28], 0
0x140017bf0  xor     r8d, r8d
0x140017bf3  mov     [rsp+58h+var_30], 0
0x140017bfc  mov     [rsp+58h+var_38], rcx
0x140017c01  mov     ecx, [rbx+18h]
0x140017c04  call    _guard_dispatch_icall
0x140017c09  mov     rbx, [rsp+58h+arg_0]
0x140017c0e  add     rsp, 50h
0x140017c12  pop     rdi
0x140017c13  retn
```
