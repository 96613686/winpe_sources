# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140001e68`
- end: `0x140001f7f`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `279`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, unsigned int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x140002354`

## callees

- `0x140001e68`
- `0x140001f88`
- `0x140002790`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        unsigned int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  unsigned int v7; // [rsp+70h] [rbp+18h] BYREF

  v7 = a3;
  v3 = a2 & 1;
  v4 = a3;
  if ( a3 )
  {
    v4 = a3 - 1;
    if ( a3 == 1 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1);
      goto LABEL_17;
    }
    v4 = a3 - 2;
    if ( a3 == 2 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 1;
      goto LABEL_17;
    }
    v4 = a3 - 3;
    if ( a3 == 3 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 2;
      goto LABEL_17;
    }
    v4 = a3 - 4;
    if ( a3 == 4 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 3;
      goto LABEL_17;
    }
    v4 = a3 - 5;
    if ( a3 == 5 )
    {
      v5 = 2 * (unsigned int)!(a2 & 1) + 8;
      goto LABEL_17;
    }
    if ( a3 == 6 )
    {
      v5 = 2 * (unsigned int)!(a2 & 1) + 9;
      goto LABEL_17;
    }
    if ( (unsigned __int8)(a3 - 100) <= 0x31u )
    {
      v5 = (unsigned __int8)(a3 - 100) + (v3 != 0 ? 100 : 150);
      goto LABEL_17;
    }
  }
  v5 = 255;
LABEL_17:
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     v4,
                                                                                                     a2,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(59383985, &Feature_Servicing_WerReportBootLKD_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x140001e68  mov     [rsp+arg_10], r8d
0x140001e6d  push    rbx
0x140001e6e  sub     rsp, 50h
0x140001e72  mov     ebx, edx
0x140001e74  mov     r9d, r8d
0x140001e77  and     ebx, 1
0x140001e7a  mov     ecx, r8d
0x140001e7d  test    r8d, r8d
0x140001e80  jz      loc_140001F25
0x140001e86  sub     ecx, 1
0x140001e89  jz      loc_140001F18
0x140001e8f  sub     ecx, 1
0x140001e92  jz      short loc_140001F09
0x140001e94  sub     ecx, 1
0x140001e97  jz      short loc_140001EFA
0x140001e99  sub     ecx, 1
0x140001e9c  jz      short loc_140001EEB
0x140001e9e  sub     ecx, 1
0x140001ea1  jz      short loc_140001EDC
0x140001ea3  cmp     ecx, 1
0x140001ea6  jz      short loc_140001ECD
0x140001ea8  sub     r9b, 64h ; 'd'
0x140001eac  cmp     r9b, 31h ; '1'
0x140001eb0  ja      short loc_140001F25
0x140001eb2  mov     eax, ebx
0x140001eb4  neg     eax
0x140001eb6  movzx   eax, r9b
0x140001eba  sbb     r8d, r8d
0x140001ebd  and     r8d, 0FFFFFFCEh
0x140001ec1  add     r8d, 96h
0x140001ec8  add     r8d, eax
0x140001ecb  jmp     short loc_140001F2B
0x140001ecd  mov     eax, ebx
0x140001ecf  xor     eax, 1
0x140001ed2  lea     r8d, ds:9[rax*2]
0x140001eda  jmp     short loc_140001F2B
0x140001edc  mov     eax, ebx
0x140001ede  xor     eax, 1
0x140001ee1  lea     r8d, ds:8[rax*2]
0x140001ee9  jmp     short loc_140001F2B
0x140001eeb  mov     eax, ebx
0x140001eed  xor     eax, 1
0x140001ef0  lea     r8d, ds:3[rax*4]
0x140001ef8  jmp     short loc_140001F2B
0x140001efa  mov     eax, ebx
0x140001efc  xor     eax, 1
0x140001eff  lea     r8d, ds:2[rax*4]
0x140001f07  jmp     short loc_140001F2B
0x140001f09  mov     eax, ebx
0x140001f0b  xor     eax, 1
0x140001f0e  lea     r8d, ds:1[rax*4]
0x140001f16  jmp     short loc_140001F2B
0x140001f18  mov     r8d, ebx
0x140001f1b  xor     r8d, 1
0x140001f1f  shl     r8d, 2
0x140001f23  jmp     short loc_140001F2B
0x140001f25  mov     r8d, 0FFh
0x140001f2b  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140001f30  test    eax, eax
0x140001f32  jz      short loc_140001F78
0x140001f34  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140001f3b  test    rax, rax
0x140001f3e  jz      short loc_140001F78
0x140001f40  mov     rdx, cs:off_140008B48
0x140001f47  lea     rcx, [rsp+58h+arg_10]
0x140001f4c  mov     [rsp+58h+var_20], 1
0x140001f55  mov     r9d, ebx
0x140001f58  mov     [rsp+58h+var_28], 0
0x140001f5d  xor     r8d, r8d
0x140001f60  mov     [rsp+58h+var_30], 0
0x140001f69  mov     [rsp+58h+var_38], rcx
0x140001f6e  mov     ecx, 38A20B1h
0x140001f73  call    _guard_dispatch_icall
0x140001f78  add     rsp, 50h
0x140001f7c  pop     rbx
0x140001f7d  retn
```
