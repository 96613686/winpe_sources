# TetheringService::HandlePowerStateChange(_WLAN_OPERATIONAL_STATE)

- ea: `0x180019170`
- end: `0x18001927e`
- name: `?HandlePowerStateChange@TetheringService@@QEAAJW4_WLAN_OPERATIONAL_STATE@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(TetheringService *__hidden this, enum _WLAN_OPERATIONAL_STATE)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180021830`

## callees

- `0x18000bf4c`
- `0x1800186c4`
- `0x180019170`
- `0x18001ff08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019206`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019206`

## pseudocode

```c
__int64 __fastcall TetheringService::HandlePowerStateChange(TetheringService *this, enum _WLAN_OPERATIONAL_STATE a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  HANDLE v6; // rcx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  if ( (unsigned int)TetheringService::GetPrivateInterfaceType() == 1 )
  {
    if ( *((_BYTE *)this + 1891) )
    {
      if ( (unsigned int)(a2 - 1) <= 1 )
      {
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
        }
        v6 = g_hWlanPowerSet;
        *((_BYTE *)this + 1891) = 0;
        SetEvent(v6);
      }
    }
    else if ( a2 == wlan_operational_state_off )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
      TetheringService::StopSharingAsync(this, 4, v4, v5);
    }
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180019170  mov     [rsp+arg_0], rbx
0x180019175  mov     [rsp+arg_8], rsi
0x18001917a  push    rdi
0x18001917b  sub     rsp, 20h
0x18001917f  mov     ebx, edx
0x180019181  mov     rdi, rcx
0x180019184  mov     rcx, cs:WPP_GLOBAL_Control
0x18001918b  lea     rsi, WPP_GLOBAL_Control
0x180019192  cmp     rcx, rsi
0x180019195  jz      short loc_1800191B2
0x180019197  test    byte ptr [rcx+1Ch], 8
0x18001919b  jz      short loc_1800191B2
0x18001919d  mov     rcx, [rcx+10h]
0x1800191a1  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800191a8  mov     edx, 5Eh ; '^'
0x1800191ad  call    WPP_SF_
0x1800191b2  call    ?GetPrivateInterfaceType@TetheringService@@AEAA?AW4_TETHERING_CONNECTION_TYPE@@XZ; TetheringService::GetPrivateInterfaceType(void)
0x1800191b7  cmp     eax, 1
0x1800191ba  jnz     loc_180019245
0x1800191c0  cmp     byte ptr [rdi+763h], 0
0x1800191c7  jz      short loc_18001920E
0x1800191c9  lea     eax, [rbx-1]
0x1800191cc  cmp     eax, 1
0x1800191cf  ja      short loc_180019245
0x1800191d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191d8  cmp     rcx, rsi
0x1800191db  jz      short loc_1800191F8
0x1800191dd  test    byte ptr [rcx+1Ch], 4
0x1800191e1  jz      short loc_1800191F8
0x1800191e3  mov     rcx, [rcx+10h]
0x1800191e7  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800191ee  mov     edx, 5Fh ; '_'
0x1800191f3  call    WPP_SF_
0x1800191f8  mov     rcx, cs:?g_hWlanPowerSet@@3PEAXEA; hEvent
0x1800191ff  mov     byte ptr [rdi+763h], 0
0x180019206  call    cs:__imp_SetEvent
0x18001920c  jmp     short loc_180019245
0x18001920e  cmp     ebx, 1
0x180019211  jnz     short loc_180019245
0x180019213  mov     rcx, cs:WPP_GLOBAL_Control
0x18001921a  cmp     rcx, rsi
0x18001921d  jz      short loc_180019238
0x18001921f  test    byte ptr [rcx+1Ch], 4
0x180019223  jz      short loc_180019238
0x180019225  mov     rcx, [rcx+10h]
0x180019229  lea     edx, [rbx+5Fh]
0x18001922c  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180019233  call    WPP_SF_
0x180019238  mov     edx, 4
0x18001923d  mov     rcx, rdi
0x180019240  call    ?StopSharingAsync@TetheringService@@AEAAJW4StopReason@1@@Z; TetheringService::StopSharingAsync(TetheringService::StopReason)
0x180019245  mov     rcx, cs:WPP_GLOBAL_Control
0x18001924c  cmp     rcx, rsi
0x18001924f  jz      short loc_18001926C
0x180019251  test    byte ptr [rcx+1Ch], 8
0x180019255  jz      short loc_18001926C
0x180019257  mov     rcx, [rcx+10h]
0x18001925b  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180019262  mov     edx, 61h ; 'a'
0x180019267  call    WPP_SF_
0x18001926c  mov     rbx, [rsp+28h+arg_0]
0x180019271  xor     eax, eax
0x180019273  mov     rsi, [rsp+28h+arg_8]
0x180019278  add     rsp, 20h
0x18001927c  pop     rdi
0x18001927d  retn
```
