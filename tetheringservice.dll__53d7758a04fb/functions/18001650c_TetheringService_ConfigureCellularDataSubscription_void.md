# TetheringService::ConfigureCellularDataSubscription(void)

- ea: `0x18001650c`
- end: `0x180016706`
- name: `?ConfigureCellularDataSubscription@TetheringService@@AEAAJXZ`
- size: `506`
- prototype: `__int64 __fastcall(TetheringService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019ec0`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18001650c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016687`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016687`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016575`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001661a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016575`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001661a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001662c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001662c`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001667c`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001667c`
- `ntdll!NtQueryWnfStateData` at `0x1800165a3`
- `ntdll!NtQueryWnfStateData` at `0x1800165a3`

## pseudocode

```c
__int64 __fastcall TetheringService::ConfigureCellularDataSubscription(TetheringService *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v3; // ebx
  unsigned int v4; // ebx
  TetheringServiceTelemetry *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  int v9; // edi
  int v11; // [rsp+70h] [rbp+8h] BYREF
  int v12; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v13; // [rsp+80h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 331, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1408);
  v13 = 0;
  v12 = 0;
  v11 = 4;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1408));
  v3 = NtQueryWnfStateData(&WNF_CELL_DATA_ENABLED_BY_USER_MODEM0, 0, 0, &v13, &v12, &v11);
  if ( v3 < 0 )
  {
    v4 = v3 | 0x10000000;
    if ( (v4 & 0x80000000) != 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 332;
LABEL_9:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v4);
        goto LABEL_15;
      }
      goto LABEL_15;
    }
LABEL_14:
    *((_BYTE *)this + 1664) = BYTE1(v12);
    goto LABEL_15;
  }
  v4 = 0;
  if ( v11 == 4 )
    goto LABEL_14;
  v4 = -2147019873;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 333;
    goto LABEL_9;
  }
LABEL_15:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
  if ( *((_QWORD *)this + 209) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 209) = 0;
  }
  v7 = RtlSubscribeWnfStateChangeNotification(
         (char *)this + 1672,
         WNF_CELL_DATA_ENABLED_BY_USER_MODEM0,
         v13,
         TetheringService::CellularDataWnfCallback,
         0,
         0,
         0,
         0);
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1488);
  v9 = v7;
  LeaveCriticalSection(v8);
  if ( v9 )
  {
    v4 = v9 | 0x10000000;
    if ( v9 < 0
      && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 334, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v4);
    }
  }
  LeaveCriticalSection(v2);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 335, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18001650c  mov     [rsp+arg_18], rbx
0x180016511  push    rbp
0x180016512  push    rsi
0x180016513  push    rdi
0x180016514  push    r12
0x180016516  push    r15
0x180016518  sub     rsp, 40h
0x18001651c  mov     rdi, rcx
0x18001651f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016526  lea     r15, WPP_GLOBAL_Control
0x18001652d  lea     r12, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180016534  cmp     rcx, r15
0x180016537  jz      short loc_180016550
0x180016539  test    byte ptr [rcx+1Ch], 8
0x18001653d  jz      short loc_180016550
0x18001653f  mov     rcx, [rcx+10h]
0x180016543  mov     edx, 14Bh
0x180016548  mov     r8, r12
0x18001654b  call    WPP_SF_
0x180016550  lea     rbp, [rdi+580h]
0x180016557  mov     [rsp+68h+arg_10], 0
0x180016562  mov     rcx, rbp; lpCriticalSection
0x180016565  mov     [rsp+68h+arg_8], 0
0x18001656d  mov     [rsp+68h+arg_0], 4
0x180016575  call    cs:__imp_EnterCriticalSection
0x18001657b  lea     rax, [rsp+68h+arg_0]
0x180016580  xor     r8d, r8d
0x180016583  mov     [rsp+68h+var_40], rax
0x180016588  lea     r9, [rsp+68h+arg_10]
0x180016590  lea     rax, [rsp+68h+arg_8]
0x180016595  xor     edx, edx
0x180016597  lea     rcx, WNF_CELL_DATA_ENABLED_BY_USER_MODEM0
0x18001659e  mov     [rsp+68h+var_48], rax
0x1800165a3  call    cs:__imp_NtQueryWnfStateData
0x1800165a9  mov     ebx, eax
0x1800165ab  test    eax, eax
0x1800165ad  jns     short loc_1800165DF
0x1800165af  or      ebx, 10000000h
0x1800165b5  jge     short loc_180016606
0x1800165b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165be  cmp     rcx, r15
0x1800165c1  jz      short loc_180016610
0x1800165c3  test    byte ptr [rcx+1Ch], 1
0x1800165c7  jz      short loc_180016610
0x1800165c9  mov     edx, 14Ch
0x1800165ce  mov     rcx, [rcx+10h]
0x1800165d2  mov     r9d, ebx
0x1800165d5  mov     r8, r12
0x1800165d8  call    WPP_SF_d
0x1800165dd  jmp     short loc_180016610
0x1800165df  xor     ebx, ebx
0x1800165e1  cmp     [rsp+68h+arg_0], 4
0x1800165e6  jz      short loc_180016606
0x1800165e8  mov     ebx, 8007139Fh
0x1800165ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165f4  cmp     rcx, r15
0x1800165f7  jz      short loc_180016610
0x1800165f9  test    byte ptr [rcx+1Ch], 1
0x1800165fd  jz      short loc_180016610
0x1800165ff  mov     edx, 14Dh
0x180016604  jmp     short loc_1800165CE
0x180016606  mov     al, byte ptr [rsp+68h+arg_8+1]
0x18001660a  mov     [rdi+680h], al
0x180016610  lea     rsi, [rdi+5D0h]
0x180016617  mov     rcx, rsi; lpCriticalSection
0x18001661a  call    cs:__imp_EnterCriticalSection
0x180016620  mov     rcx, [rdi+688h]
0x180016627  test    rcx, rcx
0x18001662a  jz      short loc_18001663D
0x18001662c  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180016632  mov     qword ptr [rdi+688h], 0
0x18001663d  mov     r8d, [rsp+68h+arg_10]
0x180016645  lea     r9, ?CellularDataWnfCallback@TetheringService@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; TetheringService::CellularDataWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18001664c  mov     rdx, cs:WNF_CELL_DATA_ENABLED_BY_USER_MODEM0
0x180016653  lea     rcx, [rdi+688h]
0x18001665a  mov     [rsp+68h+var_30], 0
0x180016662  mov     [rsp+68h+var_38], 0
0x18001666a  mov     [rsp+68h+var_40], 0
0x180016673  mov     [rsp+68h+var_48], 0
0x18001667c  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180016682  mov     rcx, rsi; lpCriticalSection
0x180016685  mov     edi, eax
0x180016687  call    cs:__imp_LeaveCriticalSection
0x18001668d  test    edi, edi
0x18001668f  jz      short loc_1800166C1
0x180016691  mov     ebx, edi
0x180016693  or      ebx, 10000000h
0x180016699  jge     short loc_1800166C1
0x18001669b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166a2  cmp     rcx, r15
0x1800166a5  jz      short loc_1800166C1
0x1800166a7  test    byte ptr [rcx+1Ch], 1
0x1800166ab  jz      short loc_1800166C1
0x1800166ad  mov     rcx, [rcx+10h]
0x1800166b1  mov     edx, 14Eh
0x1800166b6  mov     r9d, ebx
0x1800166b9  mov     r8, r12
0x1800166bc  call    WPP_SF_d
0x1800166c1  mov     rcx, rbp; lpCriticalSection
0x1800166c4  call    cs:__imp_LeaveCriticalSection
0x1800166ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166d1  cmp     rcx, r15
0x1800166d4  jz      short loc_1800166F0
0x1800166d6  test    byte ptr [rcx+1Ch], 8
0x1800166da  jz      short loc_1800166F0
0x1800166dc  mov     rcx, [rcx+10h]
0x1800166e0  mov     edx, 14Fh
0x1800166e5  mov     r9d, ebx
0x1800166e8  mov     r8, r12
0x1800166eb  call    WPP_SF_d
0x1800166f0  mov     eax, ebx
0x1800166f2  mov     rbx, [rsp+68h+arg_18]
0x1800166fa  add     rsp, 40h
0x1800166fe  pop     r15
0x180016700  pop     r12
0x180016702  pop     rdi
0x180016703  pop     rsi
0x180016704  pop     rbp
0x180016705  retn
```
