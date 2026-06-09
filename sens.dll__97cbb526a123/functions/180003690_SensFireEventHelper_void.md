# SensFireEventHelper(void *)

- ea: `0x180003690`
- end: `0x180003a8c`
- name: `?SensFireEventHelper@@YAKPEAX@Z`
- size: `1020`
- prototype: `__int64 __fastcall(unsigned int *Parameter)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180002e60`

## callees

- `0x180003690`
- `0x180003aa0`
- `0x180003bd0`
- `0x1800041fc`
- `0x18000478c`
- `0x180007644`
- `0x180008300`
- `0x1800093b0`
- `0x18000a0e0`
- `0x18000a4f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800036bf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800036bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003766`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003766`

## pseudocode

```c
__int64 __fastcall SensFireEventHelper(unsigned int *Parameter)
{
  unsigned int v2; // edi
  unsigned int v3; // esi
  unsigned int v4; // r8d
  unsigned int v5; // eax
  unsigned int v7; // edi
  unsigned int v8; // r8d
  char *v9; // r9
  char *v10; // rdx
  char *v11; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids);
  }
  v2 = *Parameter;
  v3 = CoInitializeEx(0, 0);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147417850 )
    return v3;
  if ( v2 )
  {
    switch ( v2 )
    {
      case 5u:
        v5 = FireWinlogonEvent(Parameter, L"STARTSHELL", 5);
        break;
      case 0xBu:
        v5 = FireWinlogonEvent(Parameter, L"DISPLAY UNLOCK", 11);
        break;
      case 6u:
        v5 = FireWinlogonEvent(Parameter, L"POSTSHELL", 6);
        break;
      default:
        switch ( v2 )
        {
          case 2u:
            v5 = FireWinlogonEvent(Parameter, L"LOGON", v2);
            goto LABEL_15;
          case 3u:
            v5 = FireWinlogonEvent(Parameter, L"LOGOFF", v2);
            goto LABEL_15;
          case 7u:
            v5 = FireWinlogonEvent(Parameter, L"SESSION DISCONNECT", v2);
            goto LABEL_15;
          case 8u:
            v5 = FireWinlogonEvent(Parameter, L"SESSION RECONNECT", v2);
            goto LABEL_15;
          case 0xAu:
            v5 = FireWinlogonEvent(Parameter, L"DISPLAY LOCK", v2);
            goto LABEL_15;
          case 0xCu:
            v5 = FireWinlogonEvent(Parameter, L"STARTSCREENSAVER", v2);
            goto LABEL_15;
          case 0xDu:
            v5 = FireWinlogonEvent(Parameter, L"STOPSCREENSAVER", v2);
            goto LABEL_15;
          case 0xEu:
            v5 = FirePowerEvent(Parameter, L"ON AC POWER", v2);
            goto LABEL_15;
          case 0xFu:
            FirePowerEvent(Parameter, L"ON BATTERY POWER", v2);
            goto LABEL_26;
          case 0x10u:
LABEL_26:
            v5 = FirePowerEvent(Parameter, L"BATTERY IS LOW", v2);
            goto LABEL_15;
          case 0x11u:
            v5 = FirePowerEvent(Parameter, L"POWER STATUS CHANGED", v2);
            goto LABEL_15;
          case 0x12u:
          case 0x13u:
            v7 = 0;
            goto LABEL_16;
          case 0x14u:
            v5 = FireRasEvent(Parameter, L"RAS STARTED");
            goto LABEL_15;
          case 0x15u:
            v5 = FireRasEvent(Parameter, L"RAS STOPPED");
            goto LABEL_15;
          case 0x16u:
            v5 = FireRasEvent(Parameter, L"RAS CONNECT");
            goto LABEL_15;
          case 0x17u:
            v5 = FireRasEvent(Parameter, L"RAS DISCONNECT");
            goto LABEL_15;
          case 0x18u:
            v5 = FireRasEvent(Parameter, L"RAS DISCONNECT PENDING");
            goto LABEL_15;
          case 0x19u:
            v5 = FireLanEvent(Parameter, L"LAN CONNECT", v4);
            goto LABEL_15;
          case 0x1Au:
            v5 = FireLanEvent(Parameter, L"LAN DISCONNECT", v4);
            goto LABEL_15;
          default:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids, v2);
            }
            v7 = -2147024809;
            goto LABEL_16;
        }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v8 = Parameter[3];
      v9 = "WAN ";
      v10 = byte_18000DCD0;
      if ( !Parameter[1] )
        v10 = "NOT ";
      v11 = "LAN ";
      if ( (v8 & 1) == 0 )
        v11 = byte_18000DCD0;
      if ( (v8 & 2) == 0 )
        v9 = byte_18000DCD0;
      WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v10, v8, (_DWORD)v9, (__int64)v11, (__int64)v10);
    }
    v5 = SensFireNetEventHelper((struct _SENSEVENT_NETALIVE *)Parameter);
  }
LABEL_15:
  v7 = v5;
LABEL_16:
  FreeEventData(Parameter);
  if ( !v3 )
    CoUninitialize();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x180003690  push    rbx
0x180003692  push    rbp
0x180003693  push    rsi
0x180003694  push    rdi
0x180003695  sub     rsp, 38h
0x180003699  mov     rbx, rcx
0x18000369c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036a3  lea     rbp, WPP_GLOBAL_Control
0x1800036aa  cmp     rcx, rbp
0x1800036ad  jz      short loc_1800036B9
0x1800036af  test    byte ptr [rcx+1Ch], 1
0x1800036b3  jnz     loc_180003857
0x1800036b9  mov     edi, [rbx]
0x1800036bb  xor     edx, edx; dwCoInit
0x1800036bd  xor     ecx, ecx; pvReserved
0x1800036bf  call    cs:__imp_CoInitializeEx
0x1800036c5  mov     esi, eax
0x1800036c7  mov     eax, 80000000h
0x1800036cc  lea     ecx, [rsi+rax]
0x1800036cf  test    eax, ecx
0x1800036d1  jz      short loc_180003727
0x1800036d3  test    edi, edi
0x1800036d5  jz      short loc_18000373A
0x1800036d7  cmp     edi, 5
0x1800036da  jz      loc_18000378D
0x1800036e0  cmp     edi, 0Bh
0x1800036e3  jz      loc_1800037A4
0x1800036e9  cmp     edi, 6
0x1800036ec  jz      loc_1800037BB
0x1800036f2  lea     eax, [rdi-2]; switch 25 cases
0x1800036f5  cmp     eax, 18h
0x1800036f8  ja      def_180003711; jumptable 0000000180003711 default case, cases 4-6,9,11
0x1800036fe  lea     rdx, __ImageBase
0x180003705  cdqe
0x180003707  mov     ecx, ds:(jpt_180003711 - 180000000h)[rdx+rax*4]
0x18000370e  add     rcx, rdx
0x180003711  jmp     rcx; switch jump
0x180003713  mov     r8d, edi; jumptable 0000000180003711 case 10
0x180003716  lea     rdx, aDisplayLock; "DISPLAY LOCK"
0x18000371d  mov     rcx, rbx
0x180003720  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x180003725  jmp     short loc_180003758
0x180003727  cmp     esi, 80010106h
0x18000372d  jz      short loc_1800036D3
0x18000372f  mov     eax, esi
0x180003731  add     rsp, 38h
0x180003735  pop     rdi
0x180003736  pop     rsi
0x180003737  pop     rbp
0x180003738  pop     rbx
0x180003739  retn
0x18000373a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003741  cmp     rcx, rbp
0x180003744  jz      short loc_180003750
0x180003746  test    byte ptr [rcx+1Ch], 1
0x18000374a  jnz     loc_1800039A4
0x180003750  mov     rcx, rbx; struct _SENSEVENT_NETALIVE *
0x180003753  call    ?SensFireNetEventHelper@@YAJPEAU_SENSEVENT_NETALIVE@@@Z; SensFireNetEventHelper(_SENSEVENT_NETALIVE *)
0x180003758  mov     edi, eax
0x18000375a  mov     rcx, rbx; lpMem
0x18000375d  call    ?FreeEventData@@YAXPEAX@Z; FreeEventData(void *)
0x180003762  test    esi, esi
0x180003764  jnz     short loc_18000376C
0x180003766  call    cs:__imp_CoUninitialize
0x18000376c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003773  cmp     rcx, rbp
0x180003776  jz      short loc_180003782
0x180003778  test    byte ptr [rcx+1Ch], 1
0x18000377c  jnz     loc_180003A01
0x180003782  mov     eax, edi
0x180003784  add     rsp, 38h
0x180003788  pop     rdi
0x180003789  pop     rsi
0x18000378a  pop     rbp
0x18000378b  pop     rbx
0x18000378c  retn
0x18000378d  mov     r8d, 5
0x180003793  lea     rdx, aStartshell; "STARTSHELL"
0x18000379a  mov     rcx, rbx
0x18000379d  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x1800037a2  jmp     short loc_180003758
0x1800037a4  mov     r8d, 0Bh
0x1800037aa  lea     rdx, aDisplayUnlock; "DISPLAY UNLOCK"
0x1800037b1  mov     rcx, rbx
0x1800037b4  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x1800037b9  jmp     short loc_180003758
0x1800037bb  mov     r8d, 6
0x1800037c1  lea     rdx, aPostshell; "POSTSHELL"
0x1800037c8  mov     rcx, rbx
0x1800037cb  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x1800037d0  jmp     short loc_180003758
0x1800037d2  mov     r8d, edi; jumptable 0000000180003711 case 2
0x1800037d5  lea     rdx, aLogon; "LOGON"
0x1800037dc  mov     rcx, rbx
0x1800037df  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x1800037e4  jmp     loc_180003758
0x1800037e9  mov     r8d, edi; jumptable 0000000180003711 case 15
0x1800037ec  lea     rdx, aOnBatteryPower; "ON BATTERY POWER"
0x1800037f3  mov     rcx, rbx
0x1800037f6  call    ?FirePowerEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FirePowerEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x1800037fb  mov     r8d, edi; jumptable 0000000180003711 case 16
0x1800037fe  lea     rdx, aBatteryIsLow; "BATTERY IS LOW"
0x180003805  mov     rcx, rbx
0x180003808  call    ?FirePowerEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FirePowerEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x18000380d  jmp     loc_180003758
0x180003812  mov     r8d, edi; jumptable 0000000180003711 case 3
0x180003815  lea     rdx, aLogoff; "LOGOFF"
0x18000381c  mov     rcx, rbx
0x18000381f  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x180003824  jmp     loc_180003758
0x180003829  mov     r8d, edi; jumptable 0000000180003711 case 14
0x18000382c  lea     rdx, aOnAcPower; "ON AC POWER"
0x180003833  mov     rcx, rbx
0x180003836  call    ?FirePowerEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FirePowerEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x18000383b  jmp     loc_180003758
0x180003840  mov     r8d, edi; jumptable 0000000180003711 case 13
0x180003843  lea     rdx, aStopscreensave; "STOPSCREENSAVER"
0x18000384a  mov     rcx, rbx
0x18000384d  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x180003852  jmp     loc_180003758
0x180003857  cmp     byte ptr [rcx+19h], 5
0x18000385b  jb      loc_1800036B9
0x180003861  mov     rcx, [rcx+10h]
0x180003865  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x18000386c  mov     edx, 12h
0x180003871  call    WPP_SF_
0x180003876  jmp     loc_1800036B9
0x18000387b  xor     edi, edi; jumptable 0000000180003711 cases 18,19
0x18000387d  jmp     loc_18000375A
0x180003882  mov     r8d, edi; jumptable 0000000180003711 case 17
0x180003885  lea     rdx, aPowerStatusCha; "POWER STATUS CHANGED"
0x18000388c  mov     rcx, rbx
0x18000388f  call    ?FirePowerEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FirePowerEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x180003894  jmp     loc_180003758
0x180003899  mov     r8d, edi; jumptable 0000000180003711 case 7
0x18000389c  lea     rdx, aSessionDisconn; "SESSION DISCONNECT"
0x1800038a3  mov     rcx, rbx
0x1800038a6  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x1800038ab  jmp     loc_180003758
0x1800038b0  mov     r8d, edi; jumptable 0000000180003711 case 8
0x1800038b3  lea     rdx, aSessionReconne; "SESSION RECONNECT"
0x1800038ba  mov     rcx, rbx
0x1800038bd  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x1800038c2  jmp     loc_180003758
0x1800038c7  mov     r8d, edi; jumptable 0000000180003711 case 12
0x1800038ca  lea     rdx, aStartscreensav; "STARTSCREENSAVER"
0x1800038d1  mov     rcx, rbx
0x1800038d4  call    ?FireWinlogonEvent@@YAJPEAXPEBGW4SENS_EVENT_TYPE@@@Z; FireWinlogonEvent(void *,ushort const *,SENS_EVENT_TYPE)
0x1800038d9  jmp     loc_180003758
0x1800038de  lea     rdx, aRasStarted; jumptable 0000000180003711 case 20
0x1800038e5  mov     rcx, rbx; void *
0x1800038e8  call    ?FireRasEvent@@YAJPEAXPEBG@Z; FireRasEvent(void *,ushort const *)
0x1800038ed  jmp     loc_180003758
0x1800038f2  lea     rdx, aRasStopped; jumptable 0000000180003711 case 21
0x1800038f9  mov     rcx, rbx; void *
0x1800038fc  call    ?FireRasEvent@@YAJPEAXPEBG@Z; FireRasEvent(void *,ushort const *)
0x180003901  jmp     loc_180003758
0x180003906  lea     rdx, aRasConnect; jumptable 0000000180003711 case 22
0x18000390d  mov     rcx, rbx; void *
0x180003910  call    ?FireRasEvent@@YAJPEAXPEBG@Z; FireRasEvent(void *,ushort const *)
0x180003915  jmp     loc_180003758
0x18000391a  lea     rdx, aRasDisconnect; jumptable 0000000180003711 case 23
0x180003921  mov     rcx, rbx; void *
0x180003924  call    ?FireRasEvent@@YAJPEAXPEBG@Z; FireRasEvent(void *,ushort const *)
0x180003929  jmp     loc_180003758
0x18000392e  lea     rdx, aRasDisconnectP; jumptable 0000000180003711 case 24
0x180003935  mov     rcx, rbx; void *
0x180003938  call    ?FireRasEvent@@YAJPEAXPEBG@Z; FireRasEvent(void *,ushort const *)
0x18000393d  jmp     loc_180003758
0x180003942  lea     rdx, aLanConnect; jumptable 0000000180003711 case 25
0x180003949  mov     rcx, rbx; void *
0x18000394c  call    ?FireLanEvent@@YAJPEAXPEBGK@Z; FireLanEvent(void *,ushort const *,ulong)
0x180003951  jmp     loc_180003758
0x180003956  lea     rdx, aLanDisconnect; jumptable 0000000180003711 case 26
0x18000395d  mov     rcx, rbx; void *
0x180003960  call    ?FireLanEvent@@YAJPEAXPEBGK@Z; FireLanEvent(void *,ushort const *,ulong)
0x180003965  jmp     loc_180003758
0x18000396a  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180003711 default case, cases 4-6,9,11
0x180003971  cmp     rcx, rbp
0x180003974  jz      short loc_18000399A
0x180003976  test    byte ptr [rcx+1Ch], 1
0x18000397a  jz      short loc_18000399A
0x18000397c  cmp     byte ptr [rcx+19h], 2
0x180003980  jb      short loc_18000399A
0x180003982  mov     rcx, [rcx+10h]
0x180003986  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x18000398d  mov     edx, 14h
0x180003992  mov     r9d, edi
0x180003995  call    WPP_SF_d
0x18000399a  mov     edi, 80070057h
0x18000399f  jmp     loc_18000375A
0x1800039a4  cmp     byte ptr [rcx+19h], 4
0x1800039a8  jb      loc_180003750
0x1800039ae  cmp     dword ptr [rbx+4], 0
0x1800039b2  lea     r10, byte_18000DCD0
0x1800039b9  mov     r8d, [rbx+0Ch]
0x1800039bd  lea     rax, aNot; "NOT "
0x1800039c4  mov     rcx, [rcx+10h]
0x1800039c8  lea     r9, aWan; "WAN "
0x1800039cf  mov     rdx, r10
0x1800039d2  cmovz   rdx, rax
0x1800039d6  test    r8b, 1
0x1800039da  mov     [rsp+58h+var_30], rdx
0x1800039df  lea     rax, aLan; "LAN "
0x1800039e6  cmovz   rax, r10
0x1800039ea  test    r8b, 2
0x1800039ee  mov     [rsp+58h+var_38], rax
0x1800039f3  cmovz   r9, r10
0x1800039f7  call    WPP_SF_sss
0x1800039fc  jmp     loc_180003750
0x180003a01  cmp     byte ptr [rcx+19h], 5
0x180003a05  jb      loc_180003782
0x180003a0b  mov     rcx, [rcx+10h]
0x180003a0f  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x180003a16  mov     edx, 15h
0x180003a1b  call    WPP_SF_
0x180003a20  jmp     loc_180003782
```
