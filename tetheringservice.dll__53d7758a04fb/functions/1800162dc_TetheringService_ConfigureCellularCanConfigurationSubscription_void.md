# TetheringService::ConfigureCellularCanConfigurationSubscription(void)

- ea: `0x1800162dc`
- end: `0x180016505`
- name: `?ConfigureCellularCanConfigurationSubscription@TetheringService@@AEAAJXZ`
- size: `553`
- prototype: `__int64 __fastcall(TetheringService *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019034`
- `0x180019ec0`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x1800162dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800164aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800164b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800164aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800164b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001630b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001631b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001630b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001631b`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180016415`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180016415`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016469`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016469`
- `ntdll!NtQueryWnfStateData` at `0x18001637f`
- `ntdll!NtQueryWnfStateData` at `0x18001637f`

## pseudocode

```c
__int64 __fastcall TetheringService::ConfigureCellularCanConfigurationSubscription(TetheringService *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  __int64 v3; // rax
  int v4; // ebx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  int v9; // [rsp+40h] [rbp-D8h] BYREF
  unsigned int v10; // [rsp+44h] [rbp-D4h] BYREF
  __int64 v11; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE v12[4]; // [rsp+50h] [rbp-C8h] BYREF
  int v13; // [rsp+54h] [rbp-C4h]

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1488);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1448));
  v10 = 0;
  memset_0(v12, 0, 0x74u);
  v3 = WNF_CELL_CONFIGURED_LINES_CAN1;
  if ( !*((_BYTE *)this + 1664) )
    v3 = WNF_CELL_CONFIGURED_LINES_CAN0;
  v11 = v3;
  v9 = 116;
  v4 = NtQueryWnfStateData(&v11, 0, 0, &v10, v12, &v9);
  if ( v4 < 0 )
  {
    v5 = v4 | 0x10000000;
    if ( (v5 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 336, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v5);
      }
      goto LABEL_13;
    }
LABEL_12:
    *((_DWORD *)this + 417) = v13;
    goto LABEL_13;
  }
  v5 = 0;
  if ( v9 == 116 )
    goto LABEL_12;
  v5 = -2147019873;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 337, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
LABEL_13:
  if ( *((_QWORD *)this + 211) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 211) = 0;
  }
  v6 = WNF_CELL_CONFIGURED_LINES_CAN1;
  if ( !*((_BYTE *)this + 1664) )
    v6 = WNF_CELL_CONFIGURED_LINES_CAN0;
  v7 = RtlSubscribeWnfStateChangeNotification(
         (char *)this + 1688,
         v6,
         v10,
         TetheringService::CellularCanConfigCallback,
         0,
         0,
         0,
         0);
  if ( v7 )
  {
    v5 = v7 | 0x10000000;
    if ( v7 < 0
      && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 338, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v5);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1448));
  LeaveCriticalSection(v1);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 339, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1800162dc  push    rbx
0x1800162de  push    rbp
0x1800162df  push    rsi
0x1800162e0  push    rdi
0x1800162e1  push    r12
0x1800162e3  push    r14
0x1800162e5  sub     rsp, 0E8h
0x1800162ec  mov     rax, cs:__security_cookie
0x1800162f3  xor     rax, rsp
0x1800162f6  mov     [rsp+118h+var_48], rax
0x1800162fe  lea     rbp, [rcx+5D0h]
0x180016305  mov     rsi, rcx
0x180016308  mov     rcx, rbp; lpCriticalSection
0x18001630b  call    cs:__imp_EnterCriticalSection
0x180016311  lea     r14, [rsi+5A8h]
0x180016318  mov     rcx, r14; lpCriticalSection
0x18001631b  call    cs:__imp_EnterCriticalSection
0x180016321  mov     edi, 74h ; 't'
0x180016326  mov     [rsp+118h+var_D4], 0
0x18001632e  mov     r8d, edi; Size
0x180016331  lea     rcx, [rsp+118h+var_C8]; void *
0x180016336  xor     edx, edx; Val
0x180016338  call    memset_0
0x18001633d  cmp     byte ptr [rsi+680h], 0
0x180016344  lea     r9, [rsp+118h+var_D4]
0x180016349  mov     rax, cs:WNF_CELL_CONFIGURED_LINES_CAN1
0x180016350  lea     rcx, [rsp+118h+var_D0]
0x180016355  cmovz   rax, cs:WNF_CELL_CONFIGURED_LINES_CAN0
0x18001635d  xor     r8d, r8d
0x180016360  mov     [rsp+118h+var_D0], rax
0x180016365  xor     edx, edx
0x180016367  lea     rax, [rsp+118h+var_D8]
0x18001636c  mov     [rsp+118h+var_D8], edi
0x180016370  mov     [rsp+118h+var_F0], rax
0x180016375  lea     rax, [rsp+118h+var_C8]
0x18001637a  mov     [rsp+118h+var_F8], rax
0x18001637f  call    cs:__imp_NtQueryWnfStateData
0x180016385  lea     r12, WPP_GLOBAL_Control
0x18001638c  mov     ebx, eax
0x18001638e  test    eax, eax
0x180016390  jns     short loc_1800163C6
0x180016392  or      ebx, 10000000h
0x180016398  jge     short loc_1800163FC
0x18001639a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163a1  cmp     rcx, r12
0x1800163a4  jz      short loc_180016406
0x1800163a6  test    byte ptr [rcx+1Ch], 1
0x1800163aa  jz      short loc_180016406
0x1800163ac  mov     rcx, [rcx+10h]
0x1800163b0  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800163b7  mov     edx, 150h
0x1800163bc  mov     r9d, ebx
0x1800163bf  call    WPP_SF_d
0x1800163c4  jmp     short loc_180016406
0x1800163c6  xor     ebx, ebx
0x1800163c8  cmp     [rsp+118h+var_D8], edi
0x1800163cc  jz      short loc_1800163FC
0x1800163ce  mov     ebx, 8007139Fh
0x1800163d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163da  cmp     rcx, r12
0x1800163dd  jz      short loc_180016406
0x1800163df  test    byte ptr [rcx+1Ch], 1
0x1800163e3  jz      short loc_180016406
0x1800163e5  mov     rcx, [rcx+10h]
0x1800163e9  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800163f0  mov     edx, 151h
0x1800163f5  call    WPP_SF_
0x1800163fa  jmp     short loc_180016406
0x1800163fc  mov     eax, [rsp+118h+var_C4]
0x180016400  mov     [rsi+684h], eax
0x180016406  lea     rdi, [rsi+698h]
0x18001640d  mov     rcx, [rdi]
0x180016410  test    rcx, rcx
0x180016413  jz      short loc_180016422
0x180016415  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001641b  mov     qword ptr [rdi], 0
0x180016422  cmp     byte ptr [rsi+680h], 0
0x180016429  lea     r9, ?CellularCanConfigCallback@TetheringService@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; TetheringService::CellularCanConfigCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180016430  mov     rdx, cs:WNF_CELL_CONFIGURED_LINES_CAN1
0x180016437  mov     rcx, rdi
0x18001643a  cmovz   rdx, cs:WNF_CELL_CONFIGURED_LINES_CAN0
0x180016442  mov     r8d, [rsp+118h+var_D4]
0x180016447  mov     [rsp+118h+var_E0], 0
0x18001644f  mov     [rsp+118h+var_E8], 0
0x180016457  mov     [rsp+118h+var_F0], 0
0x180016460  mov     [rsp+118h+var_F8], 0
0x180016469  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18001646f  test    eax, eax
0x180016471  jz      short loc_1800164A7
0x180016473  mov     ebx, eax
0x180016475  or      ebx, 10000000h
0x18001647b  jge     short loc_1800164A7
0x18001647d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016484  cmp     rcx, r12
0x180016487  jz      short loc_1800164A7
0x180016489  test    byte ptr [rcx+1Ch], 1
0x18001648d  jz      short loc_1800164A7
0x18001648f  mov     rcx, [rcx+10h]
0x180016493  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001649a  mov     edx, 152h
0x18001649f  mov     r9d, ebx
0x1800164a2  call    WPP_SF_d
0x1800164a7  mov     rcx, r14; lpCriticalSection
0x1800164aa  call    cs:__imp_LeaveCriticalSection
0x1800164b0  mov     rcx, rbp; lpCriticalSection
0x1800164b3  call    cs:__imp_LeaveCriticalSection
0x1800164b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164c0  cmp     rcx, r12
0x1800164c3  jz      short loc_1800164E3
0x1800164c5  test    byte ptr [rcx+1Ch], 8
0x1800164c9  jz      short loc_1800164E3
0x1800164cb  mov     rcx, [rcx+10h]
0x1800164cf  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800164d6  mov     edx, 153h
0x1800164db  mov     r9d, ebx
0x1800164de  call    WPP_SF_d
0x1800164e3  mov     eax, ebx
0x1800164e5  mov     rcx, [rsp+118h+var_48]
0x1800164ed  xor     rcx, rsp; StackCookie
0x1800164f0  call    __security_check_cookie
0x1800164f5  add     rsp, 0E8h
0x1800164fc  pop     r14
0x1800164fe  pop     r12
0x180016500  pop     rdi
0x180016501  pop     rsi
0x180016502  pop     rbp
0x180016503  pop     rbx
0x180016504  retn
```
