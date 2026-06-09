# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140007484`
- end: `0x14000759a`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140007900`

## callees

- `0x140007484`
- `0x1400075a0`
- `0x140009010`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(31261443, &Feature_ResourceManagerLimits_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x140007484  mov     [rsp+arg_10], r8d
0x140007489  push    rbx
0x14000748a  sub     rsp, 50h
0x14000748e  mov     ebx, edx
0x140007490  mov     r9d, r8d
0x140007493  and     ebx, 1
0x140007496  mov     ecx, r8d
0x140007499  test    r8d, r8d
0x14000749c  jz      loc_140007541
0x1400074a2  sub     ecx, 1
0x1400074a5  jz      loc_140007534
0x1400074ab  sub     ecx, 1
0x1400074ae  jz      short loc_140007525
0x1400074b0  sub     ecx, 1
0x1400074b3  jz      short loc_140007516
0x1400074b5  sub     ecx, 1
0x1400074b8  jz      short loc_140007507
0x1400074ba  sub     ecx, 1
0x1400074bd  jz      short loc_1400074F8
0x1400074bf  cmp     ecx, 1
0x1400074c2  jz      short loc_1400074E9
0x1400074c4  sub     r9b, 64h ; 'd'
0x1400074c8  cmp     r9b, 31h ; '1'
0x1400074cc  ja      short loc_140007541
0x1400074ce  mov     eax, ebx
0x1400074d0  neg     eax
0x1400074d2  movzx   eax, r9b
0x1400074d6  sbb     r8d, r8d
0x1400074d9  and     r8d, 0FFFFFFCEh
0x1400074dd  add     r8d, 96h
0x1400074e4  add     r8d, eax
0x1400074e7  jmp     short loc_140007547
0x1400074e9  mov     eax, ebx
0x1400074eb  xor     eax, 1
0x1400074ee  lea     r8d, ds:9[rax*2]
0x1400074f6  jmp     short loc_140007547
0x1400074f8  mov     eax, ebx
0x1400074fa  xor     eax, 1
0x1400074fd  lea     r8d, ds:8[rax*2]
0x140007505  jmp     short loc_140007547
0x140007507  mov     eax, ebx
0x140007509  xor     eax, 1
0x14000750c  lea     r8d, ds:3[rax*4]
0x140007514  jmp     short loc_140007547
0x140007516  mov     eax, ebx
0x140007518  xor     eax, 1
0x14000751b  lea     r8d, ds:2[rax*4]
0x140007523  jmp     short loc_140007547
0x140007525  mov     eax, ebx
0x140007527  xor     eax, 1
0x14000752a  lea     r8d, ds:1[rax*4]
0x140007532  jmp     short loc_140007547
0x140007534  mov     r8d, ebx
0x140007537  xor     r8d, 1
0x14000753b  shl     r8d, 2
0x14000753f  jmp     short loc_140007547
0x140007541  mov     r8d, 0FFh
0x140007547  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000754c  test    eax, eax
0x14000754e  jz      short loc_140007594
0x140007550  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140007557  test    rax, rax
0x14000755a  jz      short loc_140007594
0x14000755c  mov     rdx, cs:off_14000CAE8
0x140007563  lea     rcx, [rsp+58h+arg_10]
0x140007568  mov     [rsp+58h+var_20], 1
0x140007571  mov     r9d, ebx
0x140007574  mov     [rsp+58h+var_28], 0
0x140007579  xor     r8d, r8d
0x14000757c  mov     [rsp+58h+var_30], 0
0x140007585  mov     [rsp+58h+var_38], rcx
0x14000758a  mov     ecx, 1DD0303h
0x14000758f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007594  add     rsp, 50h
0x140007598  pop     rbx
0x140007599  retn
```
