# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14001e82c`
- end: `0x14001e8ad`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140017148`

## callees

- `0x14001e82c`
- `0x14001e8b4`
- `0x14001ec50`
- `0x140040a70`

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
0x14001e82c  mov     [rsp+arg_0], rbx
0x14001e831  mov     [rsp+arg_10], r8d
0x14001e836  push    rdi
0x14001e837  sub     rsp, 50h
0x14001e83b  mov     edi, edx
0x14001e83d  mov     r9, rdx
0x14001e840  mov     rbx, rcx
0x14001e843  and     edi, 1
0x14001e846  mov     edx, edi
0x14001e848  mov     ecx, r8d
0x14001e84b  call    wil_details_MapReportingKind
0x14001e850  mov     r8d, eax
0x14001e853  mov     rdx, r9
0x14001e856  mov     rcx, rbx
0x14001e859  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14001e85e  test    eax, eax
0x14001e860  jz      short loc_14001E8A1
0x14001e862  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14001e869  test    rax, rax
0x14001e86c  jz      short loc_14001E8A1
0x14001e86e  mov     rdx, [rbx+10h]
0x14001e872  lea     rcx, [rsp+58h+arg_10]
0x14001e877  mov     [rsp+58h+var_20], 1
0x14001e880  mov     r9d, edi
0x14001e883  mov     [rsp+58h+var_28], 0
0x14001e888  xor     r8d, r8d
0x14001e88b  mov     [rsp+58h+var_30], 0
0x14001e894  mov     [rsp+58h+var_38], rcx
0x14001e899  mov     ecx, [rbx+18h]
0x14001e89c  call    _guard_dispatch_icall
0x14001e8a1  mov     rbx, [rsp+58h+arg_0]
0x14001e8a6  add     rsp, 50h
0x14001e8aa  pop     rdi
0x14001e8ab  retn
```
