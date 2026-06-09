# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140010ef8`
- end: `0x140010f6e`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14003a528`

## callees

- `0x140010ef8`
- `0x140010f74`
- `0x14001108c`
- `0x140011640`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(44406110, Feature_ReFS_WOF_Support_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140010ef8  mov     [rsp+arg_10], r8d
0x140010efd  push    rbx
0x140010efe  sub     rsp, 50h
0x140010f02  mov     ebx, edx
0x140010f04  mov     r9, rdx
0x140010f07  and     ebx, 1
0x140010f0a  mov     ecx, r8d
0x140010f0d  mov     edx, ebx
0x140010f0f  call    wil_details_MapReportingKind
0x140010f14  mov     r8d, eax
0x140010f17  mov     rdx, r9
0x140010f1a  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140010f1f  test    eax, eax
0x140010f21  jz      short loc_140010F67
0x140010f23  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140010f2a  test    rax, rax
0x140010f2d  jz      short loc_140010F67
0x140010f2f  mov     rdx, cs:off_140017BC0
0x140010f36  lea     rcx, [rsp+58h+arg_10]
0x140010f3b  mov     [rsp+58h+var_20], 1
0x140010f44  mov     r9d, ebx
0x140010f47  mov     [rsp+58h+var_28], 0
0x140010f4c  xor     r8d, r8d
0x140010f4f  mov     [rsp+58h+var_30], 0
0x140010f58  mov     [rsp+58h+var_38], rcx
0x140010f5d  mov     ecx, 2A5955Eh
0x140010f62  call    _guard_dispatch_icall
0x140010f67  add     rsp, 50h
0x140010f6b  pop     rbx
0x140010f6c  retn
```
