# ServiceControl(ulong,ulong,void *,void *)

- ea: `0x180002c10`
- end: `0x180002e51`
- name: `?ServiceControl@@YAKKKPEAX0@Z`
- size: `577`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callees

- `0x180002c10`
- `0x1800030a0`
- `0x180008300`
- `0x18000a7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002d30`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002d30`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180002c6c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180002c6c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002d23`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002d62`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002d23`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002d62`

## pseudocode

```c
__int64 __fastcall ServiceControl(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  char BatteryFlag; // dl
  unsigned int v7; // ebx
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+30h] [rbp-28h] BYREF
  BYTE ACLineStatus; // [rsp+34h] [rbp-24h]
  char v12; // [rsp+35h] [rbp-23h]
  __int64 v13; // [rsp+36h] [rbp-22h]
  __int16 BatteryFullLifeTime_high; // [rsp+3Eh] [rbp-1Ah]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids, dwControl);
  }
  if ( dwControl == 1 )
  {
    gServiceStatus.dwControlsAccepted = 65;
    gServiceStatus.dwWin32ExitCode = 0;
    gServiceStatus.dwCurrentState = 3;
    gServiceStatus.dwWaitHint = 3000;
    gServiceStatus.dwCheckPoint = 1;
    SetServiceStatus(ghStatusHandle, &gServiceStatus);
    SetEvent(g_svchostShutdownEvent);
    return 0;
  }
  if ( dwControl != 13 )
  {
    if ( dwControl != 4 )
      return 120;
    v7 = 0;
    gServiceStatus.dwWaitHint = 0;
    if ( gServiceStatus.dwCurrentState == 2 )
    {
      *(_QWORD *)&gServiceStatus.dwControlsAccepted = 0;
    }
    else
    {
      *(_QWORD *)&gServiceStatus.dwControlsAccepted = 65;
      if ( gServiceStatus.dwCurrentState == 4 || gServiceStatus.dwCurrentState == 1 )
      {
        gServiceStatus.dwCheckPoint = 0;
LABEL_14:
        SetServiceStatus(ghStatusHandle, &gServiceStatus);
        return v7;
      }
    }
    gServiceStatus.dwCheckPoint = 1;
    goto LABEL_14;
  }
  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  GetSystemPowerStatus(&SystemPowerStatus);
  if ( dwEventType == 10 )
  {
    if ( SystemPowerStatus.ACLineStatus == 1 )
    {
      if ( gSystemPowerState.ACLineStatus != 1 )
      {
        BatteryFlag = SystemPowerStatus.BatteryFlag;
        v10 = 14;
LABEL_9:
        gSystemPowerState = SystemPowerStatus;
        ACLineStatus = SystemPowerStatus.ACLineStatus;
        v13 = *(_QWORD *)&SystemPowerStatus.BatteryLifePercent;
        v12 = BatteryFlag;
        BatteryFullLifeTime_high = HIWORD(SystemPowerStatus.BatteryFullLifeTime);
        SensFireEvent(&v10);
        return 0;
      }
    }
    else if ( !SystemPowerStatus.ACLineStatus && gSystemPowerState.ACLineStatus == 1 )
    {
      BatteryFlag = SystemPowerStatus.BatteryFlag;
      if ( (SystemPowerStatus.BatteryFlag & 0x80u) == 0 )
      {
        BatteryFlag = SystemPowerStatus.BatteryFlag & 0xFD;
        v10 = 15;
        SystemPowerStatus.BatteryFlag &= ~2u;
        goto LABEL_9;
      }
LABEL_23:
      if ( (BatteryFlag & 2) == 0 || (BatteryFlag & 8) != 0 || (gSystemPowerState.BatteryFlag & 2) != 0 )
        return 0;
      v10 = 16;
      goto LABEL_9;
    }
    BatteryFlag = SystemPowerStatus.BatteryFlag;
    goto LABEL_23;
  }
  return 0;
}

```

## disassembly

```asm
0x180002c10  mov     [rsp+arg_8], rbx
0x180002c15  push    rdi
0x180002c16  sub     rsp, 50h
0x180002c1a  mov     rax, cs:__security_cookie
0x180002c21  xor     rax, rsp
0x180002c24  mov     [rsp+58h+var_18], rax
0x180002c29  mov     edi, edx
0x180002c2b  mov     ebx, ecx
0x180002c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c34  lea     rax, WPP_GLOBAL_Control
0x180002c3b  cmp     rcx, rax
0x180002c3e  jz      short loc_180002C4A
0x180002c40  test    byte ptr [rcx+1Ch], 1
0x180002c44  jnz     loc_180002E12
0x180002c4a  cmp     ebx, 1
0x180002c4d  jz      loc_180002CE5
0x180002c53  cmp     ebx, 0Dh
0x180002c56  jnz     loc_180002D82
0x180002c5c  xor     eax, eax
0x180002c5e  lea     rcx, [rsp+58h+SystemPowerStatus]; lpSystemPowerStatus
0x180002c63  mov     qword ptr [rsp+58h+SystemPowerStatus.ACLineStatus], rax
0x180002c68  mov     [rsp+58h+SystemPowerStatus.BatteryFullLifeTime], eax
0x180002c6c  call    cs:__imp_GetSystemPowerStatus
0x180002c72  cmp     edi, 0Ah
0x180002c75  jnz     short loc_180002CDE
0x180002c77  movzx   ecx, [rsp+58h+SystemPowerStatus.ACLineStatus]
0x180002c7c  cmp     cl, 1
0x180002c7f  jnz     loc_180002DB7
0x180002c85  cmp     cs:?gSystemPowerState@@3U_SYSTEM_POWER_STATUS@@A.ACLineStatus, cl; _SYSTEM_POWER_STATUS gSystemPowerState ...
0x180002c8b  jz      loc_180002DC4
0x180002c91  movzx   edx, [rsp+58h+SystemPowerStatus.BatteryFlag]
0x180002c96  mov     [rsp+58h+var_28], 0Eh
0x180002c9e  movsd   xmm0, qword ptr [rsp+58h+SystemPowerStatus.ACLineStatus]
0x180002ca4  mov     eax, [rsp+58h+SystemPowerStatus.BatteryFullLifeTime]
0x180002ca8  movsd   qword ptr cs:?gSystemPowerState@@3U_SYSTEM_POWER_STATUS@@A.ACLineStatus, xmm0; _SYSTEM_POWER_STATUS gSystemPowerState ...
0x180002cb0  movsd   xmm0, qword ptr [rsp+58h+SystemPowerStatus.BatteryLifePercent]
0x180002cb6  mov     cs:?gSystemPowerState@@3U_SYSTEM_POWER_STATUS@@A.BatteryFullLifeTime, eax; _SYSTEM_POWER_STATUS gSystemPowerState ...
0x180002cbc  movzx   eax, word ptr [rsp+58h+SystemPowerStatus.BatteryFullLifeTime+2]
0x180002cc1  mov     [rsp+58h+var_24], cl
0x180002cc5  lea     rcx, [rsp+58h+var_28]; void *
0x180002cca  movsd   [rsp+58h+var_22], xmm0
0x180002cd0  mov     [rsp+58h+var_23], dl
0x180002cd4  mov     [rsp+58h+var_1A], ax
0x180002cd9  call    ?SensFireEvent@@YAXPEAX@Z; SensFireEvent(void *)
0x180002cde  xor     ebx, ebx
0x180002ce0  jmp     loc_180002D68
0x180002ce5  mov     rcx, cs:?ghStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180002cec  lea     rdx, ?gServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180002cf3  xor     ebx, ebx
0x180002cf5  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 41h ; 'A'; _SERVICE_STATUS gServiceStatus ...
0x180002cff  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS gServiceStatus ...
0x180002d05  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS gServiceStatus ...
0x180002d0f  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0BB8h; _SERVICE_STATUS gServiceStatus ...
0x180002d19  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS gServiceStatus ...
0x180002d23  call    cs:__imp_SetServiceStatus
0x180002d29  mov     rcx, cs:?g_svchostShutdownEvent@@3PEAXEA; hEvent
0x180002d30  call    cs:__imp_SetEvent
0x180002d36  xor     eax, eax
0x180002d38  jmp     short loc_180002D6A
0x180002d3a  mov     qword ptr cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 41h ; 'A'; _SERVICE_STATUS gServiceStatus ...
0x180002d45  cmp     eax, 4
0x180002d48  jnz     loc_180002E43
0x180002d4e  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, ebx; _SERVICE_STATUS gServiceStatus ...
0x180002d54  mov     rcx, cs:?ghStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180002d5b  lea     rdx, ?gServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180002d62  call    cs:__imp_SetServiceStatus
0x180002d68  mov     eax, ebx
0x180002d6a  mov     rcx, [rsp+58h+var_18]
0x180002d6f  xor     rcx, rsp; StackCookie
0x180002d72  call    __security_check_cookie
0x180002d77  mov     rbx, [rsp+58h+arg_8]
0x180002d7c  add     rsp, 50h
0x180002d80  pop     rdi
0x180002d81  retn
0x180002d82  cmp     ebx, 4
0x180002d85  jnz     loc_180002E39
0x180002d8b  mov     eax, cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS gServiceStatus ...
0x180002d91  xor     ebx, ebx
0x180002d93  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, eax; _SERVICE_STATUS gServiceStatus ...
0x180002d99  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, ebx; _SERVICE_STATUS gServiceStatus ...
0x180002d9f  cmp     eax, 2
0x180002da2  jnz     short loc_180002D3A
0x180002da4  mov     qword ptr cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, rbx; _SERVICE_STATUS gServiceStatus ...
0x180002dab  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS gServiceStatus ...
0x180002db5  jmp     short loc_180002D54
0x180002db7  test    cl, cl
0x180002db9  jnz     short loc_180002DC4
0x180002dbb  cmp     cs:?gSystemPowerState@@3U_SYSTEM_POWER_STATUS@@A.ACLineStatus, 1; _SYSTEM_POWER_STATUS gSystemPowerState ...
0x180002dc2  jz      short loc_180002DF5
0x180002dc4  movzx   edx, [rsp+58h+SystemPowerStatus.BatteryFlag]
0x180002dc9  test    dl, 2
0x180002dcc  jz      loc_180002CDE
0x180002dd2  test    dl, 8
0x180002dd5  jnz     loc_180002CDE
0x180002ddb  test    cs:?gSystemPowerState@@3U_SYSTEM_POWER_STATUS@@A.BatteryFlag, 2; _SYSTEM_POWER_STATUS gSystemPowerState ...
0x180002de2  jnz     loc_180002CDE
0x180002de8  mov     [rsp+58h+var_28], 10h
0x180002df0  jmp     loc_180002C9E
0x180002df5  movzx   edx, [rsp+58h+SystemPowerStatus.BatteryFlag]
0x180002dfa  test    dl, dl
0x180002dfc  js      short loc_180002DC9
0x180002dfe  and     dl, 0FDh
0x180002e01  mov     [rsp+58h+var_28], 0Fh
0x180002e09  mov     [rsp+58h+SystemPowerStatus.BatteryFlag], dl
0x180002e0d  jmp     loc_180002C9E
0x180002e12  cmp     byte ptr [rcx+19h], 5
0x180002e16  jb      loc_180002C4A
0x180002e1c  mov     rcx, [rcx+10h]
0x180002e20  lea     r8, WPP_0a2071a0e0b23ae9b876091e2aeecbba_Traceguids
0x180002e27  mov     edx, 14h
0x180002e2c  mov     r9d, ebx
0x180002e2f  call    WPP_SF_d
0x180002e34  jmp     loc_180002C4A
0x180002e39  mov     ebx, 78h ; 'x'
0x180002e3e  jmp     loc_180002D68
0x180002e43  cmp     eax, 1
0x180002e46  jz      loc_180002D4E
0x180002e4c  jmp     loc_180002DAB
```
