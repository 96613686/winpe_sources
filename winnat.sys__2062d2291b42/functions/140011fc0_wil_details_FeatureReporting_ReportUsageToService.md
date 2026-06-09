# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140011fc0`
- end: `0x140012041`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400123b0`

## callees

- `0x140011fc0`
- `0x140012048`
- `0x140012430`
- `0x14001f4b0`

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
0x140011fc0  mov     [rsp+arg_0], rbx
0x140011fc5  mov     [rsp+arg_10], r8d
0x140011fca  push    rdi
0x140011fcb  sub     rsp, 50h
0x140011fcf  mov     edi, edx
0x140011fd1  mov     r9, rdx
0x140011fd4  mov     rbx, rcx
0x140011fd7  and     edi, 1
0x140011fda  mov     edx, edi
0x140011fdc  mov     ecx, r8d
0x140011fdf  call    wil_details_MapReportingKind
0x140011fe4  mov     r8d, eax
0x140011fe7  mov     rdx, r9
0x140011fea  mov     rcx, rbx
0x140011fed  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140011ff2  test    eax, eax
0x140011ff4  jz      short loc_140012035
0x140011ff6  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140011ffd  test    rax, rax
0x140012000  jz      short loc_140012035
0x140012002  mov     rdx, [rbx+10h]
0x140012006  lea     rcx, [rsp+58h+arg_10]
0x14001200b  mov     [rsp+58h+var_20], 1
0x140012014  mov     r9d, edi
0x140012017  mov     [rsp+58h+var_28], 0
0x14001201c  xor     r8d, r8d
0x14001201f  mov     [rsp+58h+var_30], 0
0x140012028  mov     [rsp+58h+var_38], rcx
0x14001202d  mov     ecx, [rbx+18h]
0x140012030  call    _guard_dispatch_icall
0x140012035  mov     rbx, [rsp+58h+arg_0]
0x14001203a  add     rsp, 50h
0x14001203e  pop     rdi
0x14001203f  retn
```
