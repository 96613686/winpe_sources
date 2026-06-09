# TetheringService::HandleDataWnfChange(uchar)

- ea: `0x180019034`
- end: `0x180019169`
- name: `?HandleDataWnfChange@TetheringService@@AEAAXE@Z`
- size: `309`
- prototype: `void __fastcall(TetheringService *this, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180020da0`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x1800162dc`
- `0x18001670c`
- `0x180019034`
- `0x18001f740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019135`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019135`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019080`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019080`

## pseudocode

```c
void __fastcall TetheringService::HandleDataWnfChange(TetheringService *this, char a2)
{
  int CanConfigurationSubscription; // eax
  int v5; // eax

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 378, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1408));
  if ( a2 != *((_BYTE *)this + 1664) )
  {
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 379, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
    *((_BYTE *)this + 1664) = a2;
    CanConfigurationSubscription = TetheringService::ConfigureCellularCanConfigurationSubscription(this);
    if ( CanConfigurationSubscription < 0
      && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        380,
        &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
        (unsigned int)CanConfigurationSubscription);
    }
    v5 = TetheringService::ConfigureCellularImsiSubscription(this);
    if ( v5 < 0
      && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        381,
        &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
        (unsigned int)v5);
    }
  }
  TetheringService::StopSharing(this, 1, 8);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1408));
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 382, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
}

```

## disassembly

```asm
0x180019034  push    rbx
0x180019036  push    rbp
0x180019037  push    rsi
0x180019038  push    rdi
0x180019039  push    r14
0x18001903b  sub     rsp, 20h
0x18001903f  mov     dil, dl
0x180019042  mov     rbx, rcx
0x180019045  mov     rcx, cs:WPP_GLOBAL_Control
0x18001904c  lea     rbp, WPP_GLOBAL_Control
0x180019053  lea     r14, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001905a  cmp     rcx, rbp
0x18001905d  jz      short loc_180019076
0x18001905f  test    byte ptr [rcx+1Ch], 8
0x180019063  jz      short loc_180019076
0x180019065  mov     rcx, [rcx+10h]
0x180019069  mov     edx, 17Ah
0x18001906e  mov     r8, r14
0x180019071  call    WPP_SF_
0x180019076  lea     rsi, [rbx+580h]
0x18001907d  mov     rcx, rsi; lpCriticalSection
0x180019080  call    cs:__imp_EnterCriticalSection
0x180019086  cmp     dil, [rbx+680h]
0x18001908d  jz      loc_180019121
0x180019093  mov     rcx, cs:WPP_GLOBAL_Control
0x18001909a  cmp     rcx, rbp
0x18001909d  jz      short loc_1800190B6
0x18001909f  test    byte ptr [rcx+1Ch], 4
0x1800190a3  jz      short loc_1800190B6
0x1800190a5  mov     rcx, [rcx+10h]
0x1800190a9  mov     edx, 17Bh
0x1800190ae  mov     r8, r14
0x1800190b1  call    WPP_SF_
0x1800190b6  mov     rcx, rbx; this
0x1800190b9  mov     [rbx+680h], dil
0x1800190c0  call    ?ConfigureCellularCanConfigurationSubscription@TetheringService@@AEAAJXZ; TetheringService::ConfigureCellularCanConfigurationSubscription(void)
0x1800190c5  test    eax, eax
0x1800190c7  jns     short loc_1800190EF
0x1800190c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190d0  cmp     rcx, rbp
0x1800190d3  jz      short loc_1800190EF
0x1800190d5  test    byte ptr [rcx+1Ch], 2
0x1800190d9  jz      short loc_1800190EF
0x1800190db  mov     rcx, [rcx+10h]
0x1800190df  mov     edx, 17Ch
0x1800190e4  mov     r9d, eax
0x1800190e7  mov     r8, r14
0x1800190ea  call    WPP_SF_d
0x1800190ef  mov     rcx, rbx; this
0x1800190f2  call    ?ConfigureCellularImsiSubscription@TetheringService@@AEAAJXZ; TetheringService::ConfigureCellularImsiSubscription(void)
0x1800190f7  test    eax, eax
0x1800190f9  jns     short loc_180019121
0x1800190fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180019102  cmp     rcx, rbp
0x180019105  jz      short loc_180019121
0x180019107  test    byte ptr [rcx+1Ch], 2
0x18001910b  jz      short loc_180019121
0x18001910d  mov     rcx, [rcx+10h]
0x180019111  mov     edx, 17Dh
0x180019116  mov     r9d, eax
0x180019119  mov     r8, r14
0x18001911c  call    WPP_SF_d
0x180019121  mov     edx, 1
0x180019126  mov     rcx, rbx
0x180019129  lea     r8d, [rdx+7]
0x18001912d  call    ?StopSharing@TetheringService@@AEAAJKW4StopReason@1@@Z; TetheringService::StopSharing(ulong,TetheringService::StopReason)
0x180019132  mov     rcx, rsi; lpCriticalSection
0x180019135  call    cs:__imp_LeaveCriticalSection
0x18001913b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019142  cmp     rcx, rbp
0x180019145  jz      short loc_18001915E
0x180019147  test    byte ptr [rcx+1Ch], 8
0x18001914b  jz      short loc_18001915E
0x18001914d  mov     rcx, [rcx+10h]
0x180019151  mov     edx, 17Eh
0x180019156  mov     r8, r14
0x180019159  call    WPP_SF_
0x18001915e  add     rsp, 20h
0x180019162  pop     r14
0x180019164  pop     rdi
0x180019165  pop     rsi
0x180019166  pop     rbp
0x180019167  pop     rbx
0x180019168  retn
```
