# UmpoUpdateEffectivePowerMode

- ea: `0x1800168dc`
- end: `0x180016a33`
- name: `UmpoUpdateEffectivePowerMode`
- size: `343`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180016400`
- `0x180016470`
- `0x1800165a8`

## callees

- `0x180015e68`
- `0x1800168dc`
- `0x1800188bc`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180016a22`
- `ntdll!RtlPublishWnfStateData` at `0x180016a22`

## pseudocode

```c
__int64 UmpoUpdateEffectivePowerMode()
{
  int v0; // ecx
  unsigned int v1; // edx
  unsigned int v2; // r8d
  __int64 result; // rax
  int v4; // [rsp+40h] [rbp+8h] BYREF

  if ( !UmpoMostRecentStateMixedReality )
  {
    if ( UmpoMostRecentStateGameMode )
    {
      v0 = 5;
      goto LABEL_16;
    }
    if ( UmpoMostRecentStateEnergySaver != 128 )
    {
      if ( UmpoMostRecentStateEnergySaver == 240 )
      {
        v0 = 0;
        goto LABEL_16;
      }
      if ( !memcmp_0(&UmpoMostRecentStateUserConfiguredPowerMode, &GUID_POWER_MODE_BEST_PERFORMANCE, 0x10u) )
      {
        v0 = 4;
        goto LABEL_16;
      }
      if ( memcmp_0(&UmpoMostRecentStateUserConfiguredPowerMode, &GUID_POWER_MODE_PERFORMANCE, 0x10u) )
      {
        if ( !memcmp_0(&UmpoMostRecentStateUserConfiguredPowerMode, &GUID_POWER_MODE_BEST_EFFICIENCY, 0x10u) )
          goto LABEL_12;
        if ( memcmp_0(&UmpoMostRecentStateSchemePersonality, &GUID_MIN_POWER_SAVINGS, 0x10u) )
        {
          v0 = (memcmp_0(&UmpoMostRecentStateSchemePersonality, &GUID_MAX_POWER_SAVINGS, 0x10u) != 0) + 1;
          goto LABEL_16;
        }
      }
      v0 = 3;
      goto LABEL_16;
    }
LABEL_12:
    v0 = 1;
    goto LABEL_16;
  }
  v0 = 6;
LABEL_16:
  v1 = 0;
  do
  {
    v2 = v1 + 1;
    result = v1;
    if ( v1 )
    {
      if ( v1 != 1 )
        goto LABEL_23;
      result = 1;
LABEL_20:
      *(&v4 + result) = v0;
      goto LABEL_23;
    }
    result = 0;
    if ( (unsigned int)(v0 - 5) > 1 )
      goto LABEL_20;
    v4 = 4;
LABEL_23:
    ++v1;
  }
  while ( v2 < 2 );
  if ( UmpoMostRecentEffectivePowerMode != v0 )
  {
    UmpoMostRecentEffectivePowerMode = v0;
    RtlPublishWnfStateData(WNF_PO_EFFECTIVE_POWER_MODE, 0, &v4, 8, 0);
    return UmpoEffectivePowerModeChanged();
  }
  return result;
}

```

## disassembly

```asm
0x1800168dc  push    rsi
0x1800168de  sub     rsp, 30h
0x1800168e2  cmp     cs:UmpoMostRecentStateMixedReality, 0
0x1800168e9  jz      short loc_1800168F5
0x1800168eb  mov     ecx, 6
0x1800168f0  jmp     loc_1800169C1
0x1800168f5  cmp     cs:UmpoMostRecentStateGameMode, 0
0x1800168fc  jz      short loc_180016908
0x1800168fe  mov     ecx, 5
0x180016903  jmp     loc_1800169C1
0x180016908  mov     eax, cs:UmpoMostRecentStateEnergySaver
0x18001690e  cmp     eax, 80h
0x180016913  jz      short loc_18001697B
0x180016915  cmp     eax, 0F0h
0x18001691a  jnz     short loc_180016923
0x18001691c  xor     ecx, ecx
0x18001691e  jmp     loc_1800169C1
0x180016923  mov     esi, 10h
0x180016928  lea     rdx, GUID_POWER_MODE_BEST_PERFORMANCE; Buf2
0x18001692f  mov     r8d, esi; Size
0x180016932  lea     rcx, UmpoMostRecentStateUserConfiguredPowerMode; Buf1
0x180016939  call    memcmp_0
0x18001693e  test    eax, eax
0x180016940  jnz     short loc_180016947
0x180016942  lea     ecx, [rsi-0Ch]
0x180016945  jmp     short loc_1800169C1
0x180016947  mov     r8, rsi; Size
0x18001694a  lea     rdx, GUID_POWER_MODE_PERFORMANCE; Buf2
0x180016951  lea     rcx, UmpoMostRecentStateUserConfiguredPowerMode; Buf1
0x180016958  call    memcmp_0
0x18001695d  test    eax, eax
0x18001695f  jz      short loc_18001699C
0x180016961  mov     r8, rsi; Size
0x180016964  lea     rdx, GUID_POWER_MODE_BEST_EFFICIENCY; Buf2
0x18001696b  lea     rcx, UmpoMostRecentStateUserConfiguredPowerMode; Buf1
0x180016972  call    memcmp_0
0x180016977  test    eax, eax
0x180016979  jnz     short loc_180016982
0x18001697b  mov     ecx, 1
0x180016980  jmp     short loc_1800169C1
0x180016982  mov     r8, rsi; Size
0x180016985  lea     rdx, GUID_MIN_POWER_SAVINGS; Buf2
0x18001698c  lea     rcx, UmpoMostRecentStateSchemePersonality; Buf1
0x180016993  call    memcmp_0
0x180016998  test    eax, eax
0x18001699a  jnz     short loc_1800169A3
0x18001699c  mov     ecx, 3
0x1800169a1  jmp     short loc_1800169C1
0x1800169a3  mov     r8, rsi; Size
0x1800169a6  lea     rdx, GUID_MAX_POWER_SAVINGS; Buf2
0x1800169ad  lea     rcx, UmpoMostRecentStateSchemePersonality; Buf1
0x1800169b4  call    memcmp_0
0x1800169b9  neg     eax
0x1800169bb  sbb     ecx, ecx
0x1800169bd  neg     ecx
0x1800169bf  inc     ecx
0x1800169c1  xor     edx, edx
0x1800169c3  lea     r8d, [rdx+1]
0x1800169c7  mov     eax, r8d
0x1800169ca  sub     eax, 1
0x1800169cd  jz      short loc_1800169DC
0x1800169cf  cmp     eax, 1
0x1800169d2  jnz     short loc_1800169EE
0x1800169d4  mov     eax, edx
0x1800169d6  mov     [rsp+rax*4+38h+arg_0], ecx
0x1800169da  jmp     short loc_1800169EE
0x1800169dc  lea     eax, [rcx-5]
0x1800169df  cmp     eax, 1
0x1800169e2  mov     eax, edx
0x1800169e4  ja      short loc_1800169D6
0x1800169e6  mov     [rsp+rax*4+38h+arg_0], 4
0x1800169ee  mov     edx, r8d
0x1800169f1  cmp     r8d, 2
0x1800169f5  jb      short loc_1800169C3
0x1800169f7  cmp     cs:UmpoMostRecentEffectivePowerMode, ecx
0x1800169fd  jz      short loc_180016A2D
0x1800169ff  mov     cs:UmpoMostRecentEffectivePowerMode, ecx
0x180016a05  lea     r8, [rsp+38h+arg_0]
0x180016a0a  mov     rcx, cs:WNF_PO_EFFECTIVE_POWER_MODE
0x180016a11  mov     r9d, 8
0x180016a17  xor     edx, edx
0x180016a19  mov     [rsp+38h+var_18], 0
0x180016a22  call    cs:__imp_RtlPublishWnfStateData
0x180016a28  call    UmpoEffectivePowerModeChanged
0x180016a2d  add     rsp, 30h
0x180016a31  pop     rsi
0x180016a32  retn
```
