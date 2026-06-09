# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14000792c`
- end: `0x1400079a2`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140007d4c`

## callees

- `0x14000792c`
- `0x1400079a8`
- `0x140007de0`
- `0x140009010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        __int64 a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v3 = a2 & 1;
  v4 = wil_details_MapReportingKind((unsigned int)a3, a2 & 1, a3, a2);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     v5,
                                                                                                     v6,
                                                                                                     v4);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v8 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(31261443, &Feature_ResourceManagerLimits_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000792c  mov     [rsp+arg_10], r8d
0x140007931  push    rbx
0x140007932  sub     rsp, 50h
0x140007936  mov     ebx, edx
0x140007938  mov     r9, rdx
0x14000793b  and     ebx, 1
0x14000793e  mov     ecx, r8d
0x140007941  mov     edx, ebx
0x140007943  call    wil_details_MapReportingKind
0x140007948  mov     r8d, eax
0x14000794b  mov     rdx, r9
0x14000794e  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140007953  test    eax, eax
0x140007955  jz      short loc_14000799B
0x140007957  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000795e  test    rax, rax
0x140007961  jz      short loc_14000799B
0x140007963  mov     rdx, cs:off_14000CB08
0x14000796a  lea     rcx, [rsp+58h+arg_10]
0x14000796f  mov     [rsp+58h+var_20], 1
0x140007978  mov     r9d, ebx
0x14000797b  mov     [rsp+58h+var_28], 0
0x140007980  xor     r8d, r8d
0x140007983  mov     [rsp+58h+var_30], 0
0x14000798c  mov     [rsp+58h+var_38], rcx
0x140007991  mov     ecx, 1DD0303h
0x140007996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000799b  add     rsp, 50h
0x14000799f  pop     rbx
0x1400079a0  retn
```
