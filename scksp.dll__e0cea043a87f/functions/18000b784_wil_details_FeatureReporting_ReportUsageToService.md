# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18000b784`
- end: `0x18000b7f9`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18000bb28`

## callees

- `0x18000b784`
- `0x18000b800`
- `0x18000bbb8`
- `0x18003d010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        char a2,
        unsigned int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  unsigned int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v3 = a2 & 1;
  v4 = wil_details_MapReportingKind(a3, a2 & 1);
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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(59873727, &Feature_Servicing_SmartCardKspPqcSupport_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b784  mov     [rsp+arg_10], r8d
0x18000b789  push    rbx
0x18000b78a  sub     rsp, 50h
0x18000b78e  mov     ebx, edx
0x18000b790  mov     r9, rdx
0x18000b793  and     ebx, 1
0x18000b796  mov     ecx, r8d
0x18000b799  mov     edx, ebx
0x18000b79b  call    wil_details_MapReportingKind
0x18000b7a0  mov     r8d, eax
0x18000b7a3  mov     rdx, r9
0x18000b7a6  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000b7ab  test    eax, eax
0x18000b7ad  jz      short loc_18000B7F3
0x18000b7af  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000b7b6  test    rax, rax
0x18000b7b9  jz      short loc_18000B7F3
0x18000b7bb  mov     rdx, cs:off_1800486D0
0x18000b7c2  lea     rcx, [rsp+58h+arg_10]
0x18000b7c7  mov     [rsp+58h+var_20], 1
0x18000b7d0  mov     r9d, ebx
0x18000b7d3  mov     [rsp+58h+var_28], 0
0x18000b7d8  xor     r8d, r8d
0x18000b7db  mov     [rsp+58h+var_30], 0
0x18000b7e4  mov     [rsp+58h+var_38], rcx
0x18000b7e9  mov     ecx, 39199BFh
0x18000b7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f3  add     rsp, 50h
0x18000b7f7  pop     rbx
0x18000b7f8  retn
```
