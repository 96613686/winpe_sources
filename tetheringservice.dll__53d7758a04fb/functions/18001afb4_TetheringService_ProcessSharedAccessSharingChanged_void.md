# TetheringService::ProcessSharedAccessSharingChanged(void)

- ea: `0x18001afb4`
- end: `0x18001b303`
- name: `?ProcessSharedAccessSharingChanged@TetheringService@@QEAAXXZ`
- size: `847`
- prototype: `void __fastcall(TetheringService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18000b130`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000ee3c`
- `0x18000f76c`
- `0x180016b68`
- `0x18001877c`
- `0x18001afb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b03b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b03b`
- `IPHLPAPI!GetIfEntry2` at `0x18001b0f1`
- `IPHLPAPI!GetIfEntry2` at `0x18001b0f1`
- `HNetCfgClient!HNetCfgStopSharing` at `0x18001b1fd`
- `HNetCfgClient!HNetCfgStopSharing` at `0x18001b1fd`

## pseudocode

```c
void __fastcall TetheringService::ProcessSharedAccessSharingChanged(TetheringService *this)
{
  TetheringService *v2; // rcx
  TetheringServiceTelemetry *v3; // rcx
  __int64 v4; // rdx
  int SharedAccessSharingState; // eax
  TetheringServiceTelemetry *v6; // rcx
  __int64 v7; // rdx
  bool v8; // sf
  int v9; // eax
  TetheringServiceTelemetry *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  bool v14; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v15; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int v16; // [rsp+28h] [rbp-D8h] BYREF
  _MIB_IF_ROW2 Row; // [rsp+30h] [rbp-D0h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  Row.InterfaceLuid.Value = 0;
  memset_0(&Row.InterfaceIndex, 0, 0x540u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( *((_DWORD *)this + 56) != 3 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v4 = 110;
LABEL_54:
      WPP_SF_(*((_QWORD *)v3 + 2), v4, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  v14 = 0;
  v15 = -1;
  v16 = -1;
  SharedAccessSharingState = TetheringService::GetSharedAccessSharingState(v2, &v14, &v15, &v16);
  if ( SharedAccessSharingState < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_55;
    }
    v7 = 111;
    goto LABEL_12;
  }
  if ( !v14 || v15 == -1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v4 = 120;
      goto LABEL_54;
    }
    goto LABEL_55;
  }
  Row.InterfaceIndex = v15;
  SharedAccessSharingState = GetIfEntry2(&Row);
  v8 = SharedAccessSharingState < 0;
  if ( SharedAccessSharingState > 0 )
  {
    SharedAccessSharingState = (unsigned __int16)SharedAccessSharingState | 0x80070000;
    v8 = SharedAccessSharingState < 0;
  }
  if ( v8 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_55;
    }
    v7 = 112;
    goto LABEL_12;
  }
  if ( Row.PhysicalMediumType == NdisPhysicalMediumWirelessWan )
  {
    SharedAccessSharingState = EntitlementMgr::SetPublicInterface((TetheringService *)((char *)this + 568), &Row);
    if ( SharedAccessSharingState < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_55;
      }
      v7 = 114;
      goto LABEL_12;
    }
    if ( *((_BYTE *)this + 662) )
    {
      v9 = EntitlementMgr::CheckEntitlement((TetheringService *)((char *)this + 568), 0);
      if ( v9 >= 0 )
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v4 = 119;
          goto LABEL_54;
        }
        goto LABEL_55;
      }
      v12 = 2198994956LL;
      if ( v9 == -2095972340 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_35;
        }
        v11 = 115;
        goto LABEL_34;
      }
    }
    else
    {
      v9 = -2147024875;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_35;
    }
    v11 = 116;
    v12 = (unsigned int)v9;
LABEL_34:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v12);
LABEL_35:
    v13 = TetheringService::DisableGlobalSharing(v10);
    if ( v13 < 0
      && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        117,
        &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
        (unsigned int)v13);
    }
    SharedAccessSharingState = HNetCfgStopSharing(v15, v16);
    if ( SharedAccessSharingState >= 0 )
      goto LABEL_55;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_55;
    }
    v7 = 118;
LABEL_12:
    WPP_SF_d(
      *((_QWORD *)v6 + 2),
      v7,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)SharedAccessSharingState);
    goto LABEL_55;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v4 = 113;
    goto LABEL_54;
  }
LABEL_55:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
}

```

## disassembly

```asm
0x18001afb4  mov     [rsp-8+arg_8], rbx
0x18001afb9  mov     [rsp-8+arg_10], rsi
0x18001afbe  push    rbp
0x18001afbf  push    rdi
0x18001afc0  push    r15
0x18001afc2  lea     rbp, [rsp-490h]
0x18001afca  sub     rsp, 590h
0x18001afd1  mov     rax, cs:__security_cookie
0x18001afd8  xor     rax, rsp
0x18001afdb  mov     [rbp+4A0h+var_20], rax
0x18001afe2  mov     rbx, rcx
0x18001afe5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afec  lea     rsi, WPP_GLOBAL_Control
0x18001aff3  lea     r15, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001affa  cmp     rcx, rsi
0x18001affd  jz      short loc_18001B016
0x18001afff  test    byte ptr [rcx+1Ch], 8
0x18001b003  jz      short loc_18001B016
0x18001b005  mov     rcx, [rcx+10h]
0x18001b009  mov     edx, 6Dh ; 'm'
0x18001b00e  mov     r8, r15
0x18001b011  call    WPP_SF_
0x18001b016  xor     edx, edx; Val
0x18001b018  mov     qword ptr [rsp+5A0h+Row.InterfaceLuid], 0
0x18001b021  mov     r8d, 540h; Size
0x18001b027  lea     rcx, [rsp+5A0h+Row.InterfaceIndex]; void *
0x18001b02c  call    memset_0
0x18001b031  lea     rdi, [rbx+0E8h]
0x18001b038  mov     rcx, rdi; lpCriticalSection
0x18001b03b  call    cs:__imp_EnterCriticalSection
0x18001b041  mov     eax, [rbx+0E0h]
0x18001b047  cmp     eax, 3
0x18001b04a  jz      short loc_18001B070
0x18001b04c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b053  cmp     rcx, rsi
0x18001b056  jz      loc_18001B2B0
0x18001b05c  test    byte ptr [rcx+1Ch], 4
0x18001b060  jz      loc_18001B2B0
0x18001b066  mov     edx, 6Eh ; 'n'
0x18001b06b  jmp     loc_18001B2A4
0x18001b070  lea     r9, [rsp+5A0h+var_578]; unsigned int *
0x18001b075  mov     [rsp+5A0h+var_580], 0
0x18001b07a  lea     r8, [rsp+5A0h+var_57C]; unsigned int *
0x18001b07f  mov     [rsp+5A0h+var_57C], 0FFFFFFFFh
0x18001b087  lea     rdx, [rsp+5A0h+var_580]; bool *
0x18001b08c  mov     [rsp+5A0h+var_578], 0FFFFFFFFh
0x18001b094  call    ?GetSharedAccessSharingState@TetheringService@@AEAAJPEA_NPEAK1@Z; TetheringService::GetSharedAccessSharingState(bool *,ulong *,ulong *)
0x18001b099  test    eax, eax
0x18001b09b  jns     short loc_18001B0D0
0x18001b09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0a4  cmp     rcx, rsi
0x18001b0a7  jz      loc_18001B2B0
0x18001b0ad  test    byte ptr [rcx+1Ch], 1
0x18001b0b1  jz      loc_18001B2B0
0x18001b0b7  mov     edx, 6Fh ; 'o'
0x18001b0bc  mov     rcx, [rcx+10h]
0x18001b0c0  mov     r9d, eax
0x18001b0c3  mov     r8, r15
0x18001b0c6  call    WPP_SF_d
0x18001b0cb  jmp     loc_18001B2B0
0x18001b0d0  cmp     [rsp+5A0h+var_580], 0
0x18001b0d5  jz      loc_18001B28D
0x18001b0db  mov     eax, [rsp+5A0h+var_57C]
0x18001b0df  cmp     eax, 0FFFFFFFFh
0x18001b0e2  jz      loc_18001B28D
0x18001b0e8  lea     rcx, [rsp+5A0h+Row]; Row
0x18001b0ed  mov     [rsp+5A0h+Row.InterfaceIndex], eax
0x18001b0f1  call    cs:__imp_GetIfEntry2
0x18001b0f7  test    eax, eax
0x18001b0f9  jle     short loc_18001B105
0x18001b0fb  movzx   eax, ax
0x18001b0fe  or      eax, 80070000h
0x18001b103  test    eax, eax
0x18001b105  jns     short loc_18001B128
0x18001b107  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b10e  cmp     rcx, rsi
0x18001b111  jz      loc_18001B2B0
0x18001b117  test    byte ptr [rcx+1Ch], 1
0x18001b11b  jz      loc_18001B2B0
0x18001b121  mov     edx, 70h ; 'p'
0x18001b126  jmp     short loc_18001B0BC
0x18001b128  cmp     [rbp+4A0h+Row.PhysicalMediumType], 8
0x18001b12f  jz      short loc_18001B155
0x18001b131  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b138  cmp     rcx, rsi
0x18001b13b  jz      loc_18001B2B0
0x18001b141  test    byte ptr [rcx+1Ch], 4
0x18001b145  jz      loc_18001B2B0
0x18001b14b  mov     edx, 71h ; 'q'
0x18001b150  jmp     loc_18001B2A4
0x18001b155  lea     rdx, [rsp+5A0h+Row]; struct _MIB_IF_ROW2 *
0x18001b15a  lea     rcx, [rbx+238h]; this
0x18001b161  call    ?SetPublicInterface@EntitlementMgr@@QEAAJPEAU_MIB_IF_ROW2@@@Z; EntitlementMgr::SetPublicInterface(_MIB_IF_ROW2 *)
0x18001b166  test    eax, eax
0x18001b168  jns     short loc_18001B18E
0x18001b16a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b171  cmp     rcx, rsi
0x18001b174  jz      loc_18001B2B0
0x18001b17a  test    byte ptr [rcx+1Ch], 1
0x18001b17e  jz      loc_18001B2B0
0x18001b184  mov     edx, 72h ; 'r'
0x18001b189  jmp     loc_18001B0BC
0x18001b18e  cmp     byte ptr [rbx+296h], 0
0x18001b195  jnz     loc_18001B22F
0x18001b19b  mov     eax, 80070015h
0x18001b1a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1a7  cmp     rcx, rsi
0x18001b1aa  jz      short loc_18001B1C6
0x18001b1ac  test    byte ptr [rcx+1Ch], 1
0x18001b1b0  jz      short loc_18001B1C6
0x18001b1b2  mov     edx, 74h ; 't'
0x18001b1b7  mov     r9d, eax
0x18001b1ba  mov     rcx, [rcx+10h]
0x18001b1be  mov     r8, r15
0x18001b1c1  call    WPP_SF_d
0x18001b1c6  call    ?DisableGlobalSharing@TetheringService@@AEAAJXZ; TetheringService::DisableGlobalSharing(void)
0x18001b1cb  test    eax, eax
0x18001b1cd  jns     short loc_18001B1F5
0x18001b1cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1d6  cmp     rcx, rsi
0x18001b1d9  jz      short loc_18001B1F5
0x18001b1db  test    byte ptr [rcx+1Ch], 2
0x18001b1df  jz      short loc_18001B1F5
0x18001b1e1  mov     rcx, [rcx+10h]
0x18001b1e5  mov     edx, 75h ; 'u'
0x18001b1ea  mov     r9d, eax
0x18001b1ed  mov     r8, r15
0x18001b1f0  call    WPP_SF_d
0x18001b1f5  mov     edx, [rsp+5A0h+var_578]
0x18001b1f9  mov     ecx, [rsp+5A0h+var_57C]
0x18001b1fd  call    cs:__imp_HNetCfgStopSharing
0x18001b203  test    eax, eax
0x18001b205  jns     loc_18001B2B0
0x18001b20b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b212  cmp     rcx, rsi
0x18001b215  jz      loc_18001B2B0
0x18001b21b  test    byte ptr [rcx+1Ch], 1
0x18001b21f  jz      loc_18001B2B0
0x18001b225  mov     edx, 76h ; 'v'
0x18001b22a  jmp     loc_18001B0BC
0x18001b22f  xor     edx, edx; unsigned __int16 *
0x18001b231  lea     rcx, [rbx+238h]; this
0x18001b238  call    ?CheckEntitlement@EntitlementMgr@@AEAAJPEBG@Z; EntitlementMgr::CheckEntitlement(ushort const *)
0x18001b23d  test    eax, eax
0x18001b23f  jns     short loc_18001B274
0x18001b241  mov     r9d, 8312000Ch
0x18001b247  cmp     eax, r9d
0x18001b24a  jnz     loc_18001B1A0
0x18001b250  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b257  cmp     rcx, rsi
0x18001b25a  jz      loc_18001B1C6
0x18001b260  test    byte ptr [rcx+1Ch], 1
0x18001b264  jz      loc_18001B1C6
0x18001b26a  mov     edx, 73h ; 's'
0x18001b26f  jmp     loc_18001B1BA
0x18001b274  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b27b  cmp     rcx, rsi
0x18001b27e  jz      short loc_18001B2B0
0x18001b280  test    byte ptr [rcx+1Ch], 4
0x18001b284  jz      short loc_18001B2B0
0x18001b286  mov     edx, 77h ; 'w'
0x18001b28b  jmp     short loc_18001B2A4
0x18001b28d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b294  cmp     rcx, rsi
0x18001b297  jz      short loc_18001B2B0
0x18001b299  test    byte ptr [rcx+1Ch], 4
0x18001b29d  jz      short loc_18001B2B0
0x18001b29f  mov     edx, 78h ; 'x'
0x18001b2a4  mov     rcx, [rcx+10h]
0x18001b2a8  mov     r8, r15
0x18001b2ab  call    WPP_SF_
0x18001b2b0  mov     rcx, rdi; lpCriticalSection
0x18001b2b3  call    cs:__imp_LeaveCriticalSection
0x18001b2b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2c0  cmp     rcx, rsi
0x18001b2c3  jz      short loc_18001B2DC
0x18001b2c5  test    byte ptr [rcx+1Ch], 8
0x18001b2c9  jz      short loc_18001B2DC
0x18001b2cb  mov     rcx, [rcx+10h]
0x18001b2cf  mov     edx, 79h ; 'y'
0x18001b2d4  mov     r8, r15
0x18001b2d7  call    WPP_SF_
0x18001b2dc  mov     rcx, [rbp+4A0h+var_20]
0x18001b2e3  xor     rcx, rsp; StackCookie
0x18001b2e6  call    __security_check_cookie
0x18001b2eb  lea     r11, [rsp+5A0h+var_10]
0x18001b2f3  mov     rbx, [r11+28h]
0x18001b2f7  mov     rsi, [r11+30h]
0x18001b2fb  mov     rsp, r11
0x18001b2fe  pop     r15
0x18001b300  pop     rdi
0x18001b301  pop     rbp
0x18001b302  retn
```
