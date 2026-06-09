# UmpoNotifyKernelNonDefaultPpmProfileSettings

- ea: `0x1800012a0`
- end: `0x180001570`
- name: `UmpoNotifyKernelNonDefaultPpmProfileSettings`
- size: `720`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002530`
- `0x18000a680`
- `0x18000d9f0`
- `0x18000e3f0`
- `0x18000f4f4`
- `0x18000f5f4`

## callees

- `0x1800011c4`
- `0x180001234`
- `0x1800012a0`
- `0x180002d8c`
- `0x1800034c0`
- `0x180004e0c`
- `0x1800061d0`
- `0x180008640`
- `0x18000c17c`
- `0x18000f3dc`
- `0x180010070`
- `0x1800132cc`
- `0x18001337c`
- `0x1800188bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001547`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800013f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800014fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800013f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800014fb`

## pseudocode

```c
__int64 __fastcall UmpoNotifyKernelNonDefaultPpmProfileSettings(__int64 a1, __int64 a2)
{
  __int64 v2; // rdx
  unsigned int ActiveScheme; // ebx
  __int64 v4; // r8
  __int64 v5; // rdx
  unsigned int SuspensionPowerMode; // eax
  unsigned int v7; // ebx
  __int64 v8; // r10
  __int64 v9; // r14
  __int64 v10; // r11
  __int64 v11; // rdi
  __int64 v12; // r8
  __int64 v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  __int128 *v16; // rcx
  __int64 ProfileClient; // rsi
  __int64 v18; // r8
  __int64 v19; // r9
  char v20; // di
  int v21; // edi
  _BYTE v23[4]; // [rsp+40h] [rbp-49h] BYREF
  int v24; // [rsp+44h] [rbp-45h] BYREF
  __int128 v25; // [rsp+48h] [rbp-41h] BYREF
  UUID v26; // [rsp+58h] [rbp-31h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-21h] BYREF
  __int128 Buf2; // [rsp+78h] [rbp-11h] BYREF
  __int128 v29; // [rsp+88h] [rbp-1h] BYREF
  __int128 v30; // [rsp+98h] [rbp+Fh] BYREF
  __int128 v31; // [rsp+A8h] [rbp+1Fh] BYREF

  v24 = 0;
  Uuid = 0;
  v26 = 0;
  v25 = 0;
  Buf2 = 0;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  ActiveScheme = UmpoGetActiveScheme(&v26, a2);
  if ( !ActiveScheme )
  {
    v23[0] = 0;
    if ( (_DWORD)UmpoOverlaySchemeSuspendMask )
    {
      ActiveScheme = UmpoInternalGetPowerModeSchema(v23, v2, v4);
      if ( ActiveScheme )
        return ActiveScheme;
      LOBYTE(v5) = v23[0];
      SuspensionPowerMode = UmpoInternalGetSuspensionPowerMode((int)UmpoOverlaySchemeSuspendMask, v5, &Uuid);
    }
    else
    {
      LOBYTE(v2) = UmpoOnAcPower;
      SuspensionPowerMode = UmpoGetActualOverlayScheme(&Uuid, v2);
    }
    ActiveScheme = SuspensionPowerMode;
    if ( !SuspensionPowerMode )
    {
      UmpoDisablePpmProfiles();
      v24 = 16;
      ActiveScheme = UmpoReadACValue(
                       0,
                       (unsigned int)&v26,
                       (unsigned int)&NO_SUBGROUP_GUID,
                       0,
                       (__int64)&GUID_POWERSCHEME_PERSONALITY,
                       0,
                       (__int64)&Buf2,
                       (__int64)&v24);
      if ( ActiveScheme )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else if ( !memcmp_0(&GUID_TYPICAL_POWER_SAVINGS, &Buf2, 0x10u) )
      {
        *(_QWORD *)&v25 = &v26;
        *((_QWORD *)&v25 + 1) = &Uuid;
        UmpoEnumeratePowerSettings(
          &GUID_PROCESSOR_SETTINGS_SUBGROUP,
          (__int64 (__fastcall *)(UUID *, UUID *, __int64))UmpoNotifyKernelNonDefaultPpmProfileSettingsCallback,
          (__int64)&v25);
        if ( byte_1800248C8 != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        EnterCriticalSection(&UmpoPowerSettingOverrideLock);
        v7 = 0;
        if ( UmpoPowerSettingOverrideCount )
        {
          v8 = *(_QWORD *)GUID_PROCESSOR_SETTINGS_SUBGROUP.Data4;
          v9 = *(_QWORD *)&GUID_PROCESSOR_SETTINGS_SUBGROUP.Data1;
          v10 = *(_QWORD *)GUID_POWER_POLICY_PROFILE_DEFAULT.Data4;
          v11 = *(_QWORD *)&GUID_POWER_POLICY_PROFILE_DEFAULT.Data1;
          do
          {
            v12 = 88LL * v7;
            v13 = *(_QWORD *)((char *)UmpoPowerSettingOverride + v12 + 16) - v9;
            if ( !v13 )
              v13 = *(_QWORD *)((char *)UmpoPowerSettingOverride + v12 + 24) - v8;
            if ( !v13 )
            {
              v14 = (char *)UmpoPowerSettingOverride + v12 + 32;
              v15 = *v14 - v11;
              if ( *v14 == v11 )
                v15 = v14[1] - v10;
              if ( v15 )
              {
                ProfileClient = UmpoPpmFindProfileClient();
                if ( ProfileClient )
                {
                  v31 = *(_OWORD *)(v18 + v19 + 16);
                  v30 = *v16;
                  v29 = *(_OWORD *)(v18 + v19 + 48);
                  v20 = *(_BYTE *)(v18 + v19 + 64) != 0;
                  if ( byte_1800248C8 != 1 )
                    MicrosoftTelemetryAssertTriggeredNoArgs();
                  LeaveCriticalSection(&UmpoPowerSettingOverrideLock);
                  v21 = UmpoSendKernelPowerPolicyNotification(
                          (unsigned int)&Uuid,
                          (unsigned int)&v26,
                          (unsigned int)&v31,
                          (unsigned int)&v30,
                          (__int64)&v29,
                          v20);
                  if ( byte_1800248C8 != 1 )
                    MicrosoftTelemetryAssertTriggeredNoArgs();
                  EnterCriticalSection(&UmpoPowerSettingOverrideLock);
                  if ( !v21 )
                    ++*(_DWORD *)(ProfileClient + 44);
                  v11 = *(_QWORD *)&GUID_POWER_POLICY_PROFILE_DEFAULT.Data1;
                  v10 = *(_QWORD *)GUID_POWER_POLICY_PROFILE_DEFAULT.Data4;
                  v9 = *(_QWORD *)&GUID_PROCESSOR_SETTINGS_SUBGROUP.Data1;
                  v8 = *(_QWORD *)GUID_PROCESSOR_SETTINGS_SUBGROUP.Data4;
                }
              }
            }
            ++v7;
          }
          while ( v7 < UmpoPowerSettingOverrideCount );
        }
        if ( byte_1800248C8 != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        LeaveCriticalSection(&UmpoPowerSettingOverrideLock);
        UmpoEnablePpmProfiles();
        return 0;
      }
    }
  }
  return ActiveScheme;
}

```

## disassembly

```asm
0x1800012a0  push    rbp
0x1800012a2  push    rbx
0x1800012a3  push    rsi
0x1800012a4  push    rdi
0x1800012a5  push    r14
0x1800012a7  lea     rbp, [rsp-37h]
0x1800012ac  sub     rsp, 0C0h
0x1800012b3  mov     rax, cs:__security_cookie
0x1800012ba  xor     rax, rsp
0x1800012bd  mov     [rbp+57h+var_28], rax
0x1800012c1  xorps   xmm0, xmm0
0x1800012c4  mov     [rbp+57h+var_9C], 0
0x1800012cb  xorps   xmm1, xmm1
0x1800012ce  lea     rcx, [rbp+57h+var_88]; Uuid
0x1800012d2  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800012d6  movups  xmmword ptr [rbp+57h+var_88.Data1], xmm1
0x1800012da  movups  [rbp+57h+var_98], xmm0
0x1800012de  movups  [rbp+57h+Buf2], xmm1
0x1800012e2  movups  [rbp+57h+var_48], xmm0
0x1800012e6  movups  [rbp+57h+var_58], xmm1
0x1800012ea  movups  [rbp+57h+var_38], xmm0
0x1800012ee  call    UmpoGetActiveScheme
0x1800012f3  mov     ebx, eax
0x1800012f5  test    eax, eax
0x1800012f7  jnz     loc_180001554
0x1800012fd  cmp     cs:UmpoOverlaySchemeSuspendMask, eax
0x180001303  mov     [rbp+57h+var_A0], al
0x180001306  jz      short loc_18000132F
0x180001308  lea     rcx, [rbp+57h+var_A0]
0x18000130c  call    UmpoInternalGetPowerModeSchema
0x180001311  mov     ebx, eax
0x180001313  test    eax, eax
0x180001315  jnz     loc_180001554
0x18000131b  mov     dl, [rbp+57h+var_A0]
0x18000131e  lea     r8, [rbp+57h+Uuid]
0x180001322  mov     ecx, cs:UmpoOverlaySchemeSuspendMask
0x180001328  call    UmpoInternalGetSuspensionPowerMode
0x18000132d  jmp     short loc_18000133E
0x18000132f  mov     dl, cs:UmpoOnAcPower
0x180001335  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180001339  call    UmpoGetActualOverlayScheme
0x18000133e  mov     ebx, eax
0x180001340  test    eax, eax
0x180001342  jnz     loc_180001554
0x180001348  call    UmpoDisablePpmProfiles
0x18000134d  lea     rax, [rbp+57h+var_9C]
0x180001351  xor     r9d, r9d
0x180001354  mov     [rsp+0E0h+var_A8], rax
0x180001359  lea     edi, [rbx+10h]
0x18000135c  lea     rax, [rbp+57h+Buf2]
0x180001360  mov     [rbp+57h+var_9C], edi
0x180001363  mov     [rsp+0E0h+var_B0], rax
0x180001368  lea     r8, NO_SUBGROUP_GUID
0x18000136f  lea     rax, GUID_POWERSCHEME_PERSONALITY
0x180001376  mov     [rsp+0E0h+var_B8], 0
0x18000137f  lea     rdx, [rbp+57h+var_88]
0x180001383  mov     [rsp+0E0h+var_C0], rax
0x180001388  xor     ecx, ecx
0x18000138a  call    UmpoReadACValue
0x18000138f  mov     ebx, eax
0x180001391  test    eax, eax
0x180001393  jz      short loc_18000139F
0x180001395  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000139a  jmp     loc_180001554
0x18000139f  mov     r8, rdi; Size
0x1800013a2  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1800013a6  lea     rcx, GUID_TYPICAL_POWER_SAVINGS; Buf1
0x1800013ad  call    memcmp_0
0x1800013b2  test    eax, eax
0x1800013b4  jnz     loc_180001554
0x1800013ba  lea     rax, [rbp+57h+var_88]
0x1800013be  mov     qword ptr [rbp+57h+var_98], rax
0x1800013c2  lea     r8, [rbp+57h+var_98]
0x1800013c6  lea     rax, [rbp+57h+Uuid]
0x1800013ca  lea     rdx, UmpoNotifyKernelNonDefaultPpmProfileSettingsCallback
0x1800013d1  mov     qword ptr [rbp+57h+var_98+8], rax
0x1800013d5  lea     rcx, GUID_PROCESSOR_SETTINGS_SUBGROUP
0x1800013dc  call    UmpoEnumeratePowerSettings
0x1800013e1  cmp     cs:byte_1800248C8, 1
0x1800013e8  jz      short loc_1800013EF
0x1800013ea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800013ef  lea     rcx, UmpoPowerSettingOverrideLock; lpCriticalSection
0x1800013f6  call    cs:__imp_EnterCriticalSection
0x1800013fc  xor     ebx, ebx
0x1800013fe  cmp     cs:UmpoPowerSettingOverrideCount, ebx
0x180001404  jbe     loc_180001532
0x18000140a  mov     r10, qword ptr cs:GUID_PROCESSOR_SETTINGS_SUBGROUP.Data4
0x180001411  mov     r14, qword ptr cs:GUID_PROCESSOR_SETTINGS_SUBGROUP.Data1
0x180001418  mov     r11, qword ptr cs:GUID_POWER_POLICY_PROFILE_DEFAULT.Data4
0x18000141f  mov     rdi, qword ptr cs:GUID_POWER_POLICY_PROFILE_DEFAULT.Data1
0x180001426  mov     r9, cs:UmpoPowerSettingOverride
0x18000142d  mov     eax, ebx
0x18000142f  imul    r8, rax, 58h ; 'X'
0x180001433  mov     rax, [r8+r9+10h]
0x180001438  sub     rax, r14
0x18000143b  jnz     short loc_180001445
0x18000143d  mov     rax, [r8+r9+18h]
0x180001442  sub     rax, r10
0x180001445  test    rax, rax
0x180001448  jnz     loc_180001524
0x18000144e  lea     rcx, [r9+20h]
0x180001452  add     rcx, r8
0x180001455  mov     rax, [rcx]
0x180001458  sub     rax, rdi
0x18000145b  jnz     short loc_180001464
0x18000145d  mov     rax, [rcx+8]
0x180001461  sub     rax, r11
0x180001464  test    rax, rax
0x180001467  jz      loc_180001524
0x18000146d  call    UmpoPpmFindProfileClient
0x180001472  mov     rsi, rax
0x180001475  test    rax, rax
0x180001478  jz      loc_180001524
0x18000147e  movups  xmm0, xmmword ptr [r8+r9+10h]
0x180001484  movdqu  [rbp+57h+var_38], xmm0
0x180001489  movups  xmm1, xmmword ptr [rcx]
0x18000148c  movdqu  [rbp+57h+var_48], xmm1
0x180001491  movups  xmm0, xmmword ptr [r8+r9+30h]
0x180001497  movdqu  [rbp+57h+var_58], xmm0
0x18000149c  cmp     byte ptr [r8+r9+40h], 0
0x1800014a2  setnz   dil
0x1800014a6  cmp     cs:byte_1800248C8, 1
0x1800014ad  jz      short loc_1800014B4
0x1800014af  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800014b4  lea     rcx, UmpoPowerSettingOverrideLock; lpCriticalSection
0x1800014bb  call    cs:__imp_LeaveCriticalSection
0x1800014c1  lea     rax, [rbp+57h+var_58]
0x1800014c5  mov     byte ptr [rsp+0E0h+var_B8], dil
0x1800014ca  lea     r9, [rbp+57h+var_48]
0x1800014ce  mov     [rsp+0E0h+var_C0], rax
0x1800014d3  lea     r8, [rbp+57h+var_38]
0x1800014d7  lea     rdx, [rbp+57h+var_88]
0x1800014db  lea     rcx, [rbp+57h+Uuid]
0x1800014df  call    UmpoSendKernelPowerPolicyNotification
0x1800014e4  cmp     cs:byte_1800248C8, 1
0x1800014eb  mov     edi, eax
0x1800014ed  jz      short loc_1800014F4
0x1800014ef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800014f4  lea     rcx, UmpoPowerSettingOverrideLock; lpCriticalSection
0x1800014fb  call    cs:__imp_EnterCriticalSection
0x180001501  test    edi, edi
0x180001503  jnz     short loc_180001508
0x180001505  inc     dword ptr [rsi+2Ch]
0x180001508  mov     rdi, qword ptr cs:GUID_POWER_POLICY_PROFILE_DEFAULT.Data1
0x18000150f  mov     r11, qword ptr cs:GUID_POWER_POLICY_PROFILE_DEFAULT.Data4
0x180001516  mov     r14, qword ptr cs:GUID_PROCESSOR_SETTINGS_SUBGROUP.Data1
0x18000151d  mov     r10, qword ptr cs:GUID_PROCESSOR_SETTINGS_SUBGROUP.Data4
0x180001524  inc     ebx
0x180001526  cmp     ebx, cs:UmpoPowerSettingOverrideCount
0x18000152c  jb      loc_180001426
0x180001532  cmp     cs:byte_1800248C8, 1
0x180001539  jz      short loc_180001540
0x18000153b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001540  lea     rcx, UmpoPowerSettingOverrideLock; lpCriticalSection
0x180001547  call    cs:__imp_LeaveCriticalSection
0x18000154d  call    UmpoEnablePpmProfiles
0x180001552  xor     ebx, ebx
0x180001554  mov     eax, ebx
0x180001556  mov     rcx, [rbp+57h+var_28]
0x18000155a  xor     rcx, rsp; StackCookie
0x18000155d  call    __security_check_cookie
0x180001562  add     rsp, 0C0h
0x180001569  pop     r14
0x18000156b  pop     rdi
0x18000156c  pop     rsi
0x18000156d  pop     rbx
0x18000156e  pop     rbp
0x18000156f  retn
```
