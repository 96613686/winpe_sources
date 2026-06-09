# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140011640`
- end: `0x1400116b6`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140011a20`

## callees

- `0x140011640`
- `0x1400116bc`
- `0x140011ab4`
- `0x14001bd10`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(56791059, &Feature_Udfs_Bitmap_Dismount_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011640  mov     [rsp+arg_10], r8d
0x140011645  push    rbx
0x140011646  sub     rsp, 50h
0x14001164a  mov     ebx, edx
0x14001164c  mov     r9, rdx
0x14001164f  and     ebx, 1
0x140011652  mov     ecx, r8d
0x140011655  mov     edx, ebx
0x140011657  call    wil_details_MapReportingKind
0x14001165c  mov     r8d, eax
0x14001165f  mov     rdx, r9
0x140011662  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140011667  test    eax, eax
0x140011669  jz      short loc_1400116AF
0x14001166b  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140011672  test    rax, rax
0x140011675  jz      short loc_1400116AF
0x140011677  mov     rdx, cs:off_140024CD0
0x14001167e  lea     rcx, [rsp+58h+arg_10]
0x140011683  mov     [rsp+58h+var_20], 1
0x14001168c  mov     r9d, ebx
0x14001168f  mov     [rsp+58h+var_28], 0
0x140011694  xor     r8d, r8d
0x140011697  mov     [rsp+58h+var_30], 0
0x1400116a0  mov     [rsp+58h+var_38], rcx
0x1400116a5  mov     ecx, 3629013h
0x1400116aa  call    _guard_dispatch_icall
0x1400116af  add     rsp, 50h
0x1400116b3  pop     rbx
0x1400116b4  retn
```
