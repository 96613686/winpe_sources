# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180009018`
- end: `0x18000908d`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800093f0`

## callees

- `0x180009018`
- `0x180009094`
- `0x180009480`
- `0x180016010`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(59083637, &Feature_RailV2ServerBuildSupported_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009018  mov     [rsp+arg_10], r8d
0x18000901d  push    rbx
0x18000901e  sub     rsp, 50h
0x180009022  mov     ebx, edx
0x180009024  mov     r9, rdx
0x180009027  and     ebx, 1
0x18000902a  mov     ecx, r8d
0x18000902d  mov     edx, ebx
0x18000902f  call    wil_details_MapReportingKind
0x180009034  mov     r8d, eax
0x180009037  mov     rdx, r9
0x18000903a  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000903f  test    eax, eax
0x180009041  jz      short loc_180009087
0x180009043  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000904a  test    rax, rax
0x18000904d  jz      short loc_180009087
0x18000904f  mov     rdx, cs:off_18001C338
0x180009056  lea     rcx, [rsp+58h+arg_10]
0x18000905b  mov     [rsp+58h+var_20], 1
0x180009064  mov     r9d, ebx
0x180009067  mov     [rsp+58h+var_28], 0
0x18000906c  xor     r8d, r8d
0x18000906f  mov     [rsp+58h+var_30], 0
0x180009078  mov     [rsp+58h+var_38], rcx
0x18000907d  mov     ecx, 3858B75h
0x180009082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009087  add     rsp, 50h
0x18000908b  pop     rbx
0x18000908c  retn
```
