# TetheringService::SetConfiguration(_TETHERING_CONNECTION_SETTINGS * const,_TETHERING_CONNECTION_SETTINGS * const)

- ea: `0x18001c75c`
- end: `0x18001cfa8`
- name: `?SetConfiguration@TetheringService@@QEAAJQEAU_TETHERING_CONNECTION_SETTINGS@@0@Z`
- size: `2124`
- prototype: `__int64 __fastcall(TetheringService *__hidden this, struct _TETHERING_CONNECTION_SETTINGS *const, struct _TETHERING_CONNECTION_SETTINGS *const)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x18000ccc0`
- `0x180014c8c`
- `0x180015cdc`
- `0x18001d2b0`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d8e4`
- `0x180012a90`
- `0x18001c0dc`
- `0x18001c184`
- `0x18001c75c`
- `0x18001e4a4`
- `0x18001f740`
- `0x180020150`
- `0x1800213fc`
- `0x18002a640`
- `0x18002b1f0`
- `0x18002c034`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c838`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cf79`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c838`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001cf79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cf40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cf40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c800`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c800`

## pseudocode

```c
__int64 __fastcall TetheringService::SetConfiguration(
        TetheringService *this,
        struct _TETHERING_CONNECTION_SETTINGS *const a2,
        struct _TETHERING_CONNECTION_SETTINGS *const a3)
{
  int v6; // r12d
  unsigned int v7; // r13d
  void *SettingValueGlobalInternal; // rdi
  int *v9; // rbx
  int v10; // edi
  unsigned int v11; // r10d
  int v12; // edi
  __int128 v13; // xmm0
  int v14; // ecx
  unsigned int v15; // r8d
  int DefaultPrivateConnectionSettingsInternal; // eax
  TetheringServiceTelemetry *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  TetheringServiceTelemetry *v20; // rcx
  unsigned int v21; // edx
  int v22; // eax
  unsigned int v23; // edi
  TetheringServiceTelemetry *v24; // rcx
  int v25; // ecx
  struct _TETHERING_CONNECTION_SETTINGS *v26; // rdx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int DefaultInterface; // eax
  TetheringServiceTelemetry *v31; // rcx
  __int64 v32; // rdx
  char v34; // [rsp+30h] [rbp-D0h]
  int v35; // [rsp+34h] [rbp-CCh]
  int v36; // [rsp+38h] [rbp-C8h]
  struct _GUID v37; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v38; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[212]; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+150h] [rbp+50h] BYREF
  __int128 v41; // [rsp+154h] [rbp+54h]
  int v42; // [rsp+164h] [rbp+64h]

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v6 = 0;
  v35 = 0;
  v36 = 0;
  v34 = 0;
  v7 = 2;
  v38 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  TetheringService::ResetInactivityTimerIfNotSharing(this);
  SettingValueGlobalInternal = (void *)TetheringSettingsGetSettingValueGlobalInternal(6);
  v9 = (int *)TetheringSettingsGetSettingValueGlobalInternal(7);
  if ( SettingValueGlobalInternal )
    free(SettingValueGlobalInternal);
  if ( v9 )
  {
    v6 = *v9;
    if ( *v9 == 1 || v6 == 4 )
    {
      v35 = v9[50];
      v36 = v9[51];
    }
  }
  if ( a2 || a3 )
  {
    v10 = 0;
    if ( *((_DWORD *)this + 56) != 2 || !a3 || (v11 = *(_DWORD *)a3) == 0 )
    {
      v20 = WPP_GLOBAL_Control;
      goto LABEL_39;
    }
    v38 = (struct _GUID)*((_OWORD *)this + 26);
    v12 = *((_DWORD *)this + 119);
    if ( v11 == 4 )
    {
      if ( v12 == 10 )
      {
LABEL_28:
        v13 = *((_OWORD *)this + 27);
        v14 = *((_DWORD *)this + 112);
        v15 = *((_DWORD *)this + 56);
        v40 = 25;
        v41 = v13;
        v42 = v14;
        v37 = v38;
        NetworkingTriageScenario::MobileHotspot::TetheringConfigurationChange(
          (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)&v40,
          &v37,
          v15,
          ((v12 - 1) & 0xFFFFFFF7) == 0 ? 1 : 4,
          v11);
        DefaultPrivateConnectionSettingsInternal = TetheringService::StopSharing(this, v7, 1);
        v10 = DefaultPrivateConnectionSettingsInternal;
        if ( DefaultPrivateConnectionSettingsInternal < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v18 = 181;
LABEL_32:
            v19 = (unsigned int)DefaultPrivateConnectionSettingsInternal;
LABEL_33:
            WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v19);
            goto LABEL_87;
          }
          goto LABEL_87;
        }
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
          v20 = WPP_GLOBAL_Control;
        }
        v34 = 1;
LABEL_39:
        if ( a2 && *(_DWORD *)a2 )
        {
          if ( (int)ValidateConnectionSettings(a2) < 0 )
          {
            v10 = -2095972345;
            if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                183,
                &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
                2198994951LL);
            }
            goto LABEL_88;
          }
          DefaultPrivateConnectionSettingsInternal = TetheringSettingsSaveSettingGlobalInternal(6, a2, 208);
          v10 = DefaultPrivateConnectionSettingsInternal;
          if ( DefaultPrivateConnectionSettingsInternal < 0 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v18 = 184;
              goto LABEL_32;
            }
LABEL_87:
            if ( v10 >= 0 )
              goto LABEL_89;
            goto LABEL_88;
          }
          memset_0(&v39[4], 0, 0xD0u);
          *(_DWORD *)v39 = 6;
          *(_OWORD *)&v39[4] = *(_OWORD *)a2;
          *(_OWORD *)&v39[20] = *((_OWORD *)a2 + 1);
          *(_OWORD *)&v39[36] = *((_OWORD *)a2 + 2);
          *(_OWORD *)&v39[52] = *((_OWORD *)a2 + 3);
          *(_OWORD *)&v39[68] = *((_OWORD *)a2 + 4);
          *(_OWORD *)&v39[84] = *((_OWORD *)a2 + 5);
          *(_OWORD *)&v39[100] = *((_OWORD *)a2 + 6);
          *(_OWORD *)&v39[116] = *((_OWORD *)a2 + 7);
          *(_OWORD *)&v39[132] = *((_OWORD *)a2 + 8);
          *(_OWORD *)&v39[148] = *((_OWORD *)a2 + 9);
          *(_OWORD *)&v39[164] = *((_OWORD *)a2 + 10);
          *(_OWORD *)&v39[180] = *((_OWORD *)a2 + 11);
          *(_OWORD *)&v39[196] = *((_OWORD *)a2 + 12);
          TetheringService::SendNotification(this, (struct _TETHERING_WNF_NOTIFICATION_MSG *)v39);
          v20 = WPP_GLOBAL_Control;
        }
        if ( !a3 )
          goto LABEL_87;
        v21 = *(_DWORD *)a3;
        if ( !*(_DWORD *)a3 )
          goto LABEL_87;
        if ( ((v21 - 1) & 0xFFFFFFFC) != 0 || v21 == 2 )
        {
          if ( v20 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)v20 + 2), 185, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, *(unsigned int *)a2);
          v10 = -2095972344;
          goto LABEL_88;
        }
        v22 = ValidateConnectionSettings(a3);
        v23 = v22;
        if ( v22 >= 0 )
        {
          if ( (*(_DWORD *)a3 == 1 || *(_DWORD *)a3 == 4)
            && ((v25 = *((_DWORD *)a3 + 50)) == 0 || !*((_DWORD *)a3 + 51)) )
          {
            *(_OWORD *)v39 = *(_OWORD *)a3;
            *(_OWORD *)&v39[16] = *((_OWORD *)a3 + 1);
            *(_OWORD *)&v39[32] = *((_OWORD *)a3 + 2);
            *(_OWORD *)&v39[48] = *((_OWORD *)a3 + 3);
            *(_OWORD *)&v39[64] = *((_OWORD *)a3 + 4);
            *(_OWORD *)&v39[80] = *((_OWORD *)a3 + 5);
            *(_OWORD *)&v39[96] = *((_OWORD *)a3 + 6);
            *(_OWORD *)&v39[112] = *((_OWORD *)a3 + 7);
            *(_OWORD *)&v39[128] = *((_OWORD *)a3 + 8);
            *(_OWORD *)&v39[144] = *((_OWORD *)a3 + 9);
            *(_OWORD *)&v39[160] = *((_OWORD *)a3 + 10);
            *(_OWORD *)&v39[176] = *((_OWORD *)a3 + 11);
            *(_OWORD *)&v39[192] = *((_OWORD *)a3 + 12);
            v27 = v25;
            if ( !v25 )
              v27 = v35;
            *(_DWORD *)&v39[200] = v27;
            v28 = *(_DWORD *)&v39[204];
            if ( !*((_DWORD *)a3 + 51) )
              v28 = v36;
            *(_DWORD *)&v39[204] = v28;
            v26 = (struct _TETHERING_CONNECTION_SETTINGS *)v39;
          }
          else
          {
            v26 = a3;
          }
          v29 = TetheringSettingsSaveSettingGlobalInternal(7, v26, 208);
          v10 = v29;
          if ( v29 < 0 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v18 = 189;
              v19 = (unsigned int)v29;
              goto LABEL_33;
            }
            goto LABEL_87;
          }
        }
        else
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              186,
              &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
              (unsigned int)v22);
            v24 = WPP_GLOBAL_Control;
          }
          if ( v6 != 4 || *(_DWORD *)a3 != 1 )
          {
            if ( v24 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)v24 + 2), 188, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v23);
            v10 = -2095972344;
            goto LABEL_88;
          }
          DefaultPrivateConnectionSettingsInternal = TetheringSettingsGenerateDefaultPrivateConnectionSettingsInternal();
          v10 = DefaultPrivateConnectionSettingsInternal;
          if ( DefaultPrivateConnectionSettingsInternal < 0 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v18 = 187;
              goto LABEL_32;
            }
            goto LABEL_87;
          }
        }
        memset_0(&v39[4], 0, 0xD0u);
        *(_DWORD *)v39 = 7;
        *(_OWORD *)&v39[4] = *(_OWORD *)a3;
        *(_OWORD *)&v39[20] = *((_OWORD *)a3 + 1);
        *(_OWORD *)&v39[36] = *((_OWORD *)a3 + 2);
        *(_OWORD *)&v39[52] = *((_OWORD *)a3 + 3);
        *(_OWORD *)&v39[68] = *((_OWORD *)a3 + 4);
        *(_OWORD *)&v39[84] = *((_OWORD *)a3 + 5);
        *(_OWORD *)&v39[100] = *((_OWORD *)a3 + 6);
        *(_OWORD *)&v39[116] = *((_OWORD *)a3 + 7);
        *(_OWORD *)&v39[132] = *((_OWORD *)a3 + 8);
        *(_OWORD *)&v39[148] = *((_OWORD *)a3 + 9);
        *(_OWORD *)&v39[164] = *((_OWORD *)a3 + 10);
        *(_OWORD *)&v39[180] = *((_OWORD *)a3 + 11);
        *(_OWORD *)&v39[196] = *((_OWORD *)a3 + 12);
        TetheringService::SendNotification(this, (struct _TETHERING_WNF_NOTIFICATION_MSG *)v39);
        goto LABEL_87;
      }
    }
    else if ( v11 != 1 || ((v12 - 1) & 0xFFFFFFF7) == 0 )
    {
      goto LABEL_28;
    }
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      v11 = *(_DWORD *)a3;
    }
    v7 = 4;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v10 = -2147024809;
LABEL_88:
  *((_DWORD *)this + 412) = v10;
  memset_0(&v39[8], 0, 0xCCu);
  *(_DWORD *)v39 = 10;
  *(_DWORD *)&v39[4] = v10;
  TetheringService::SendNotification(this, (struct _TETHERING_WNF_NOTIFICATION_MSG *)v39);
LABEL_89:
  if ( v34 )
  {
    v37 = 0;
    DefaultInterface = InterfaceMgr::GetDefaultInterface(2, *(unsigned int *)a3, &v37);
    v10 = DefaultInterface;
    if ( DefaultInterface < 0 )
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v32 = 191;
        goto LABEL_98;
      }
    }
    else
    {
      DefaultInterface = TetheringService::StartSharingInternal(this, &v38, &v37, 0, v7 | 1, 0);
      v10 = DefaultInterface;
      if ( DefaultInterface < 0 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v32 = 190;
LABEL_98:
          WPP_SF_d(
            *((_QWORD *)v31 + 2),
            v32,
            &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
            (unsigned int)DefaultInterface);
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      192,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)v10);
  }
  if ( v9 )
    free(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001c75c  mov     [rsp-8+arg_18], rbx
0x18001c761  push    rbp
0x18001c762  push    rsi
0x18001c763  push    rdi
0x18001c764  push    r12
0x18001c766  push    r13
0x18001c768  push    r14
0x18001c76a  push    r15
0x18001c76c  lea     rbp, [rsp-70h]
0x18001c771  sub     rsp, 170h
0x18001c778  mov     rax, cs:__security_cookie
0x18001c77f  xor     rax, rsp
0x18001c782  mov     [rbp+0A0h+var_38], rax
0x18001c786  mov     rsi, r8
0x18001c789  mov     r14, rdx
0x18001c78c  mov     r15, rcx
0x18001c78f  lea     rax, WPP_GLOBAL_Control
0x18001c796  xor     ebx, ebx
0x18001c798  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c79f  cmp     rcx, rax
0x18001c7a2  jz      short loc_18001C7DC
0x18001c7a4  test    byte ptr [rcx+1Ch], 8
0x18001c7a8  jz      short loc_18001C7DC
0x18001c7aa  test    r8, r8
0x18001c7ad  jz      short loc_18001C7B4
0x18001c7af  mov     eax, [r8]
0x18001c7b2  jmp     short loc_18001C7B6
0x18001c7b4  mov     eax, ebx
0x18001c7b6  test    r14, r14
0x18001c7b9  jz      short loc_18001C7C0
0x18001c7bb  mov     r9d, [rdx]
0x18001c7be  jmp     short loc_18001C7C3
0x18001c7c0  mov     r9d, ebx
0x18001c7c3  mov     edx, 0B1h
0x18001c7c8  mov     [rsp+1A0h+var_180], eax
0x18001c7cc  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c7d3  mov     rcx, [rcx+10h]
0x18001c7d7  call    WPP_SF_dd
0x18001c7dc  mov     r12d, ebx
0x18001c7df  mov     [rsp+1A0h+var_16C], ebx
0x18001c7e3  mov     [rsp+1A0h+var_168], ebx
0x18001c7e7  mov     [rsp+1A0h+var_170], bl
0x18001c7eb  mov     r13d, 2
0x18001c7f1  xorps   xmm0, xmm0
0x18001c7f4  movups  xmmword ptr [rsp+1A0h+var_140.Data1], xmm0
0x18001c7f9  lea     rcx, [r15+110h]; lpCriticalSection
0x18001c800  call    cs:__imp_EnterCriticalSection
0x18001c806  mov     rcx, r15; this
0x18001c809  call    ?ResetInactivityTimerIfNotSharing@TetheringService@@AEAAXXZ; TetheringService::ResetInactivityTimerIfNotSharing(void)
0x18001c80e  lea     ecx, [r13+4]
0x18001c812  call    ?TetheringSettingsGetSettingValueGlobalInternal@@YAPEAXW4TetheringSettingGlobal@@@Z; TetheringSettingsGetSettingValueGlobalInternal(TetheringSettingGlobal)
0x18001c817  mov     rdi, rax
0x18001c81a  mov     [rsp+1A0h+var_160], rax
0x18001c81f  lea     ecx, [r13+5]
0x18001c823  call    ?TetheringSettingsGetSettingValueGlobalInternal@@YAPEAXW4TetheringSettingGlobal@@@Z; TetheringSettingsGetSettingValueGlobalInternal(TetheringSettingGlobal)
0x18001c828  mov     rbx, rax
0x18001c82b  mov     [rsp+1A0h+var_160], rax
0x18001c830  test    rdi, rdi
0x18001c833  jz      short loc_18001C83E
0x18001c835  mov     rcx, rdi; Block
0x18001c838  call    cs:__imp_free
0x18001c83e  test    rbx, rbx
0x18001c841  jz      short loc_18001C866
0x18001c843  mov     r12d, [rbx]
0x18001c846  cmp     r12d, 1
0x18001c84a  jz      short loc_18001C852
0x18001c84c  cmp     r12d, 4
0x18001c850  jnz     short loc_18001C866
0x18001c852  mov     eax, [rbx+0C8h]
0x18001c858  mov     [rsp+1A0h+var_16C], eax
0x18001c85c  mov     eax, [rbx+0CCh]
0x18001c862  mov     [rsp+1A0h+var_168], eax
0x18001c866  test    r14, r14
0x18001c869  jnz     short loc_18001C8A8
0x18001c86b  test    rsi, rsi
0x18001c86e  jnz     short loc_18001C8A8
0x18001c870  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c877  lea     r14, WPP_GLOBAL_Control
0x18001c87e  cmp     rcx, r14
0x18001c881  jz      short loc_18001C89E
0x18001c883  test    byte ptr [rcx+1Ch], 1
0x18001c887  jz      short loc_18001C89E
0x18001c889  mov     edx, 0B2h
0x18001c88e  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c895  mov     rcx, [rcx+10h]
0x18001c899  call    WPP_SF_
0x18001c89e  mov     edi, 80070057h
0x18001c8a3  jmp     loc_18001CE6D
0x18001c8a8  xor     edi, edi
0x18001c8aa  mov     eax, [r15+0E0h]
0x18001c8b1  cmp     eax, 2
0x18001c8b4  jnz     loc_18001CA42
0x18001c8ba  test    rsi, rsi
0x18001c8bd  jz      loc_18001CA42
0x18001c8c3  mov     r10d, [rsi]
0x18001c8c6  test    r10d, r10d
0x18001c8c9  jz      loc_18001CA42
0x18001c8cf  movups  xmm0, xmmword ptr [r15+1A0h]
0x18001c8d7  movdqu  xmmword ptr [rsp+1A0h+var_140.Data1], xmm0
0x18001c8dd  mov     edi, [r15+1DCh]
0x18001c8e4  mov     edx, 0FFFFFFF7h
0x18001c8e9  cmp     r10d, 4
0x18001c8ed  jnz     short loc_18001C8F6
0x18001c8ef  cmp     edi, 0Ah
0x18001c8f2  jnz     short loc_18001C903
0x18001c8f4  jmp     short loc_18001C959
0x18001c8f6  cmp     r10d, 1
0x18001c8fa  jnz     short loc_18001C959
0x18001c8fc  lea     eax, [rdi-1]
0x18001c8ff  test    edx, eax
0x18001c901  jz      short loc_18001C959
0x18001c903  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c90a  lea     rax, WPP_GLOBAL_Control
0x18001c911  cmp     rcx, rax
0x18001c914  jz      short loc_18001C953
0x18001c916  test    byte ptr [rcx+1Ch], 8
0x18001c91a  jz      short loc_18001C953
0x18001c91c  lea     eax, [rdi-1]
0x18001c91f  test    edx, eax
0x18001c921  setz    al
0x18001c924  neg     al
0x18001c926  sbb     r9d, r9d
0x18001c929  and     r9d, 0FFFFFFFDh
0x18001c92d  add     r9d, 4
0x18001c931  mov     edx, 0B4h
0x18001c936  mov     [rsp+1A0h+var_180], r10d
0x18001c93b  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c942  mov     rcx, [rcx+10h]
0x18001c946  call    WPP_SF_dd
0x18001c94b  mov     r10d, [rsi]
0x18001c94e  mov     edx, 0FFFFFFF7h
0x18001c953  mov     r13d, 4
0x18001c959  movups  xmm0, xmmword ptr [r15+1B0h]
0x18001c961  mov     ecx, [r15+1C0h]
0x18001c968  lea     eax, [rdi-1]
0x18001c96b  test    edx, eax
0x18001c96d  setz    al
0x18001c970  mov     r8d, [r15+0E0h]; unsigned int
0x18001c977  mov     [rbp+0A0h+var_50], 19h
0x18001c97e  movdqu  [rbp+0A0h+var_4C], xmm0
0x18001c983  mov     [rbp+0A0h+var_3C], ecx
0x18001c986  movaps  xmm0, xmmword ptr [rsp+1A0h+var_140.Data1]
0x18001c98b  movdqa  xmmword ptr [rsp+1A0h+var_150.Data1], xmm0
0x18001c991  neg     al
0x18001c993  sbb     r9d, r9d
0x18001c996  and     r9d, 0FFFFFFFDh
0x18001c99a  add     r9d, 4; unsigned int
0x18001c99e  mov     [rsp+1A0h+var_180], r10d; unsigned int
0x18001c9a3  lea     rdx, [rsp+1A0h+var_150]; struct _GUID *
0x18001c9a8  lea     rcx, [rbp+0A0h+var_50]; struct NetworkingTriageScenario::MobileHotspot::RequiredFields *
0x18001c9ac  call    ?TetheringConfigurationChange@MobileHotspot@NetworkingTriageScenario@@SAXAEBURequiredFields@12@U_GUID@@KKK@Z; NetworkingTriageScenario::MobileHotspot::TetheringConfigurationChange(NetworkingTriageScenario::MobileHotspot::RequiredFields const &,_GUID,ulong,ulong,ulong)
0x18001c9b1  mov     r8d, 1
0x18001c9b7  mov     edx, r13d
0x18001c9ba  mov     rcx, r15
0x18001c9bd  call    ?StopSharing@TetheringService@@AEAAJKW4StopReason@1@@Z; TetheringService::StopSharing(ulong,TetheringService::StopReason)
0x18001c9c2  mov     edi, eax
0x18001c9c4  test    eax, eax
0x18001c9c6  jns     short loc_18001CA06
0x18001c9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9cf  lea     r14, WPP_GLOBAL_Control
0x18001c9d6  cmp     rcx, r14
0x18001c9d9  jz      loc_18001CE69
0x18001c9df  test    byte ptr [rcx+1Ch], 1
0x18001c9e3  jz      loc_18001CE69
0x18001c9e9  mov     edx, 0B5h
0x18001c9ee  mov     r9d, eax
0x18001c9f1  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c9f8  mov     rcx, [rcx+10h]
0x18001c9fc  call    WPP_SF_d
0x18001ca01  jmp     loc_18001CE69
0x18001ca06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca0d  lea     rax, WPP_GLOBAL_Control
0x18001ca14  cmp     rcx, rax
0x18001ca17  jz      short loc_18001CA3B
0x18001ca19  test    byte ptr [rcx+1Ch], 8
0x18001ca1d  jz      short loc_18001CA3B
0x18001ca1f  mov     edx, 0B6h
0x18001ca24  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001ca2b  mov     rcx, [rcx+10h]
0x18001ca2f  call    WPP_SF_
0x18001ca34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca3b  mov     [rsp+1A0h+var_170], 1
0x18001ca40  jmp     short loc_18001CA49
0x18001ca42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca49  test    r14, r14
0x18001ca4c  jz      loc_18001CBA1
0x18001ca52  cmp     dword ptr [r14], 0
0x18001ca56  jz      loc_18001CBA1
0x18001ca5c  mov     rcx, r14; struct _TETHERING_CONNECTION_SETTINGS *
0x18001ca5f  call    ?ValidateConnectionSettings@@YAJPEAU_TETHERING_CONNECTION_SETTINGS@@@Z; ValidateConnectionSettings(_TETHERING_CONNECTION_SETTINGS *)
0x18001ca64  test    eax, eax
0x18001ca66  jns     short loc_18001CAAB
0x18001ca68  mov     edi, 83120007h
0x18001ca6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca74  lea     r14, WPP_GLOBAL_Control
0x18001ca7b  cmp     rcx, r14
0x18001ca7e  jz      loc_18001CE6D
0x18001ca84  test    byte ptr [rcx+1Ch], 1
0x18001ca88  jz      loc_18001CE6D
0x18001ca8e  mov     edx, 0B7h
0x18001ca93  mov     r9d, edi
0x18001ca96  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001ca9d  mov     rcx, [rcx+10h]
0x18001caa1  call    WPP_SF_d
0x18001caa6  jmp     loc_18001CE6D
0x18001caab  mov     r8d, 0D0h
0x18001cab1  mov     rdx, r14
0x18001cab4  mov     ecx, 6
0x18001cab9  call    ?TetheringSettingsSaveSettingGlobalInternal@@YAJW4TetheringSettingGlobal@@PEAXK@Z; TetheringSettingsSaveSettingGlobalInternal(TetheringSettingGlobal,void *,ulong)
0x18001cabe  mov     edi, eax
0x18001cac0  test    eax, eax
0x18001cac2  jns     short loc_18001CAEF
0x18001cac4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cacb  lea     r14, WPP_GLOBAL_Control
0x18001cad2  cmp     rcx, r14
0x18001cad5  jz      loc_18001CE69
0x18001cadb  test    byte ptr [rcx+1Ch], 1
0x18001cadf  jz      loc_18001CE69
0x18001cae5  mov     edx, 0B8h
0x18001caea  jmp     loc_18001C9EE
0x18001caef  xor     edx, edx; Val
0x18001caf1  mov     r8d, 0D0h; Size
0x18001caf7  lea     rcx, [rsp+1A0h+var_130+4]; void *
0x18001cafc  call    memset_0
0x18001cb01  mov     dword ptr [rsp+1A0h+var_130], 6
0x18001cb09  movups  xmm0, xmmword ptr [r14]
0x18001cb0d  movups  [rsp+1A0h+var_130+4], xmm0
0x18001cb12  movups  xmm1, xmmword ptr [r14+10h]
0x18001cb17  movups  [rbp+0A0h+var_11C], xmm1
0x18001cb1b  movups  xmm0, xmmword ptr [r14+20h]
0x18001cb20  movups  [rbp+0A0h+var_10C], xmm0
0x18001cb24  movups  xmm1, xmmword ptr [r14+30h]
0x18001cb29  movups  [rbp+0A0h+var_FC], xmm1
0x18001cb2d  movups  xmm0, xmmword ptr [r14+40h]
0x18001cb32  movups  [rbp+0A0h+var_EC], xmm0
0x18001cb36  movups  xmm1, xmmword ptr [r14+50h]
0x18001cb3b  movups  [rbp+0A0h+var_DC], xmm1
0x18001cb3f  movups  xmm0, xmmword ptr [r14+60h]
0x18001cb44  movups  [rbp+0A0h+var_CC], xmm0
0x18001cb48  movups  xmm1, xmmword ptr [r14+70h]
0x18001cb4d  movups  [rbp+0A0h+var_BC], xmm1
0x18001cb51  movups  xmm0, xmmword ptr [r14+80h]
0x18001cb59  movups  [rbp+0A0h+var_AC], xmm0
0x18001cb5d  movups  xmm1, xmmword ptr [r14+90h]
0x18001cb65  movups  [rbp+0A0h+var_9C], xmm1
0x18001cb69  movups  xmm0, xmmword ptr [r14+0A0h]
0x18001cb71  movups  [rbp+0A0h+var_8C], xmm0
0x18001cb75  movups  xmm1, xmmword ptr [r14+0B0h]
0x18001cb7d  movups  [rbp+0A0h+var_7C], xmm1
0x18001cb81  movups  xmm0, xmmword ptr [r14+0C0h]
0x18001cb89  movups  [rbp+0A0h+var_6C], xmm0
0x18001cb8d  lea     rdx, [rsp+1A0h+var_130]; struct _TETHERING_WNF_NOTIFICATION_MSG *
0x18001cb92  mov     rcx, r15; this
0x18001cb95  call    ?SendNotification@TetheringService@@AEAAXPEAU_TETHERING_WNF_NOTIFICATION_MSG@@@Z; TetheringService::SendNotification(_TETHERING_WNF_NOTIFICATION_MSG *)
0x18001cb9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cba1  test    rsi, rsi
0x18001cba4  jz      loc_18001CE62
0x18001cbaa  mov     edx, [rsi]
0x18001cbac  test    edx, edx
0x18001cbae  jz      loc_18001CE62
0x18001cbb4  lea     eax, [rdx-1]
0x18001cbb7  test    eax, 0FFFFFFFCh
0x18001cbbc  jnz     loc_18001CE2A
0x18001cbc2  cmp     edx, 2
0x18001cbc5  jz      loc_18001CE2A
0x18001cbcb  mov     rcx, rsi; struct _TETHERING_CONNECTION_SETTINGS *
0x18001cbce  call    ?ValidateConnectionSettings@@YAJPEAU_TETHERING_CONNECTION_SETTINGS@@@Z; ValidateConnectionSettings(_TETHERING_CONNECTION_SETTINGS *)
0x18001cbd3  mov     edi, eax
0x18001cbd5  test    eax, eax
0x18001cbd7  jns     loc_18001CC80
0x18001cbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbe4  lea     r14, WPP_GLOBAL_Control
0x18001cbeb  cmp     rcx, r14
0x18001cbee  jz      short loc_18001CC15
0x18001cbf0  test    byte ptr [rcx+1Ch], 1
0x18001cbf4  jz      short loc_18001CC15
0x18001cbf6  mov     edx, 0BAh
0x18001cbfb  mov     r9d, eax
0x18001cbfe  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001cc05  mov     rcx, [rcx+10h]
0x18001cc09  call    WPP_SF_d
0x18001cc0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc15  cmp     r12d, 4
0x18001cc19  jnz     short loc_18001CC53
0x18001cc1b  cmp     dword ptr [rsi], 1
0x18001cc1e  jnz     short loc_18001CC53
0x18001cc20  call    ?TetheringSettingsGenerateDefaultPrivateConnectionSettingsInternal@@YAJXZ; TetheringSettingsGenerateDefaultPrivateConnectionSettingsInternal(void)
0x18001cc25  mov     edi, eax
0x18001cc27  test    eax, eax
0x18001cc29  jns     loc_18001CD8A
0x18001cc2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc36  cmp     rcx, r14
0x18001cc39  jz      loc_18001CE69
0x18001cc3f  test    byte ptr [rcx+1Ch], 1
0x18001cc43  jz      loc_18001CE69
0x18001cc49  mov     edx, 0BBh
0x18001cc4e  jmp     loc_18001C9EE
0x18001cc53  cmp     rcx, r14
0x18001cc56  jz      short loc_18001CC76
0x18001cc58  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
