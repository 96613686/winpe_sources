# CBthActiveConnector::CreateAndStart(CBthActiveConnector * *,SERVICE_STATUS_HANDLE__ *)

- ea: `0x180006360`
- end: `0x1800066dd`
- name: `?CreateAndStart@CBthActiveConnector@@SAJPEAPEAV1@PEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `893`
- prototype: `__int64 __fastcall(struct CBthActiveConnector **, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1800018c0`

## callees

- `0x180004c50`
- `0x180006360`
- `0x18000785c`
- `0x180007f28`
- `0x18000899c`
- `0x180009394`
- `0x18000e204`
- `0x18000ea58`
- `0x180011f78`
- `0x180012058`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000642c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800064a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000642c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800064a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000662a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000667c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000662a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000667c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800065f4`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800065f4`
- `SHLWAPI!__imp_SHCreateThread` at `0x180006672`
- `SHLWAPI!__imp_SHCreateThread` at `0x180006672`

## pseudocode

```c
__int64 __fastcall CBthActiveConnector::CreateAndStart(
        struct CBthActiveConnector **a1,
        struct SERVICE_STATUS_HANDLE__ *a2)
{
  HPOWERNOTIFY *v3; // rax
  unsigned int v4; // edx
  HPOWERNOTIFY *v5; // rdi
  CBthActiveConnector *v6; // rbx
  unsigned int v7; // esi
  HANDLE EventW; // rax
  signed int v9; // eax
  CPnPNotification *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  HANDLE v13; // rax
  signed int v14; // eax
  int refreshed; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  signed int LastError; // eax
  bool v20; // sf
  signed int v21; // eax
  signed int v22; // eax

  g_BthActiveConnector = 0;
  v3 = (HPOWERNOTIFY *)operator new(0x38u);
  v5 = v3;
  if ( v3 )
  {
    *v3 = 0;
    v3[1] = 0;
    v3[2] = (HPOWERNOTIFY)-1LL;
    v3[3] = (HPOWERNOTIFY)-1LL;
    v3[4] = (HPOWERNOTIFY)-1LL;
    *((_DWORD *)v3 + 10) = 0;
    v3[6] = 0;
  }
  else
  {
    v5 = 0;
  }
  v6 = (CBthActiveConnector *)v5;
  if ( !v5 )
  {
    v7 = -2147024882;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, "pThis");
    goto LABEL_56;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v5[3] = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v13 = CreateEventW(0, 1, 0, 0);
    v5[2] = v13;
    if ( (((unsigned __int64)v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      refreshed = CBthActiveConnector::_RefreshBatteryState((CBthActiveConnector *)v5, 0);
      if ( refreshed < 0
        && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
          (unsigned int)refreshed);
      }
      v16 = CBthActiveConnector::_RefreshWaitInterval((CBthActiveConnector *)v5);
      if ( v16 < 0
        && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
          (unsigned int)v16);
      }
      v17 = CBthActiveConnector::_RefreshLoggedInState((CBthActiveConnector *)v5);
      if ( v17 < 0
        && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
          (unsigned int)v17);
      }
      if ( *((_DWORD *)v5 + 1) == 1 )
        CBthActiveConnector::_ExitSuspend((CBthActiveConnector *)v5);
      v18 = CBthActiveConnector::_InitializeDeviceCount((CBthActiveConnector *)v5);
      v7 = v18;
      if ( v18 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          goto LABEL_56;
        }
        v11 = 18;
        v12 = (unsigned int)v18;
LABEL_15:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v12);
        goto LABEL_56;
      }
      if ( PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 1u, a2, v5 + 6) )
      {
        v5[6] = 0;
        LastError = GetLastError();
        v20 = LastError < 0;
        if ( LastError > 0 )
          v20 = 1;
        if ( v20
          && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v21 = GetLastError();
          if ( v21 > 0 )
            v21 = (unsigned __int16)v21 | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
            (unsigned int)v21);
        }
      }
      if ( SHCreateThread(
             (LPTHREAD_START_ROUTINE)CBthActiveConnector::_ThreadProc,
             v5,
             0x18u,
             (LPTHREAD_START_ROUTINE)CBthActiveConnector::_ThreadCreateCallback) )
      {
        v6 = 0;
        g_BthActiveConnector = (CBthActiveConnector *)v5;
        goto LABEL_56;
      }
      v22 = GetLastError();
      v7 = v22;
      if ( v22 > 0 )
        v7 = (unsigned __int16)v22 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = 20;
        goto LABEL_14;
      }
    }
    else
    {
      v14 = GetLastError();
      v7 = v14;
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v11 = 14;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 13;
LABEL_14:
      v12 = v7;
      goto LABEL_15;
    }
  }
LABEL_56:
  if ( v6 )
    CBthActiveConnector::`scalar deleting destructor'(v6, v4);
  return v7;
}

```

## disassembly

```asm
0x180006360  mov     [rsp+arg_8], rbx
0x180006365  mov     [rsp+arg_10], rbp
0x18000636a  mov     [rsp+arg_0], rcx
0x18000636f  push    rsi
0x180006370  push    rdi
0x180006371  push    r12
0x180006373  push    r14
0x180006375  push    r15
0x180006377  sub     rsp, 20h
0x18000637b  mov     rbp, rdx
0x18000637e  xor     r12d, r12d
0x180006381  mov     cs:?g_BthActiveConnector@@3PEAVCBthActiveConnector@@EA, r12; CBthActiveConnector * g_BthActiveConnector
0x180006388  mov     ecx, 38h ; '8'; Size
0x18000638d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006392  mov     rdi, rax
0x180006395  mov     [rsp+48h+arg_0], rax
0x18000639a  test    rax, rax
0x18000639d  jz      short loc_1800063C8
0x18000639f  mov     [rax], r12
0x1800063a2  mov     [rax+8], r12
0x1800063a6  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1800063ae  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800063b6  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x1800063be  mov     [rax+28h], r12d
0x1800063c2  mov     [rax+30h], r12
0x1800063c6  jmp     short loc_1800063CB
0x1800063c8  mov     rdi, r12
0x1800063cb  mov     rbx, rdi
0x1800063ce  mov     [rsp+48h+arg_0], rbx
0x1800063d3  test    rdi, rdi
0x1800063d6  jnz     short loc_18000641F
0x1800063d8  mov     esi, 8007000Eh
0x1800063dd  lea     r14, WPP_GLOBAL_Control
0x1800063e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063eb  cmp     rcx, r14
0x1800063ee  jz      loc_1800066B7
0x1800063f4  test    byte ptr [rcx+1Ch], 2
0x1800063f8  jz      loc_1800066B7
0x1800063fe  mov     edx, 0Ch
0x180006403  lea     r9, aPthis; "pThis"
0x18000640a  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180006411  mov     rcx, [rcx+10h]
0x180006415  call    WPP_SF_s
0x18000641a  jmp     loc_1800066B7
0x18000641f  xor     r9d, r9d; lpName
0x180006422  xor     r8d, r8d; bInitialState
0x180006425  mov     edx, 1; bManualReset
0x18000642a  xor     ecx, ecx; lpEventAttributes
0x18000642c  call    cs:__imp_CreateEventW
0x180006432  mov     [rdi+18h], rax
0x180006436  inc     rax
0x180006439  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000643f  jnz     short loc_180006494
0x180006441  call    cs:__imp_GetLastError
0x180006447  mov     esi, eax
0x180006449  test    eax, eax
0x18000644b  jle     short loc_180006456
0x18000644d  movzx   esi, ax
0x180006450  or      esi, 80070000h
0x180006456  lea     r14, WPP_GLOBAL_Control
0x18000645d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006464  cmp     rcx, r14
0x180006467  jz      loc_1800066B7
0x18000646d  test    byte ptr [rcx+1Ch], 2
0x180006471  jz      loc_1800066B7
0x180006477  mov     edx, 0Dh
0x18000647c  mov     r9d, esi
0x18000647f  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180006486  mov     rcx, [rcx+10h]
0x18000648a  call    WPP_SF_d
0x18000648f  jmp     loc_1800066B7
0x180006494  xor     r9d, r9d; lpName
0x180006497  xor     r8d, r8d; bInitialState
0x18000649a  mov     edx, 1; bManualReset
0x18000649f  xor     ecx, ecx; lpEventAttributes
0x1800064a1  call    cs:__imp_CreateEventW
0x1800064a7  mov     [rdi+10h], rax
0x1800064ab  inc     rax
0x1800064ae  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800064b4  jnz     short loc_1800064F3
0x1800064b6  call    cs:__imp_GetLastError
0x1800064bc  mov     esi, eax
0x1800064be  test    eax, eax
0x1800064c0  jle     short loc_1800064CB
0x1800064c2  movzx   esi, ax
0x1800064c5  or      esi, 80070000h
0x1800064cb  lea     r14, WPP_GLOBAL_Control
0x1800064d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064d9  cmp     rcx, r14
0x1800064dc  jz      loc_1800066B7
0x1800064e2  test    byte ptr [rcx+1Ch], 2
0x1800064e6  jz      loc_1800066B7
0x1800064ec  mov     edx, 0Eh
0x1800064f1  jmp     short loc_18000647C
0x1800064f3  xor     edx, edx; int *
0x1800064f5  mov     rcx, rdi; this
0x1800064f8  call    ?_RefreshBatteryState@CBthActiveConnector@@AEAAJPEAH@Z; CBthActiveConnector::_RefreshBatteryState(int *)
0x1800064fd  lea     r14, WPP_GLOBAL_Control
0x180006504  test    eax, eax
0x180006506  jns     short loc_180006532
0x180006508  mov     rcx, cs:WPP_GLOBAL_Control
0x18000650f  cmp     rcx, r14
0x180006512  jz      short loc_180006532
0x180006514  test    byte ptr [rcx+1Ch], 4
0x180006518  jz      short loc_180006532
0x18000651a  mov     edx, 0Fh
0x18000651f  mov     r9d, eax
0x180006522  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180006529  mov     rcx, [rcx+10h]
0x18000652d  call    WPP_SF_d
0x180006532  mov     rcx, rdi; this
0x180006535  call    ?_RefreshWaitInterval@CBthActiveConnector@@AEAAJXZ; CBthActiveConnector::_RefreshWaitInterval(void)
0x18000653a  test    eax, eax
0x18000653c  jns     short loc_180006568
0x18000653e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006545  cmp     rcx, r14
0x180006548  jz      short loc_180006568
0x18000654a  test    byte ptr [rcx+1Ch], 4
0x18000654e  jz      short loc_180006568
0x180006550  mov     edx, 10h
0x180006555  mov     r9d, eax
0x180006558  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x18000655f  mov     rcx, [rcx+10h]
0x180006563  call    WPP_SF_d
0x180006568  mov     rcx, rdi; this
0x18000656b  call    ?_RefreshLoggedInState@CBthActiveConnector@@AEAAJXZ; CBthActiveConnector::_RefreshLoggedInState(void)
0x180006570  test    eax, eax
0x180006572  jns     short loc_18000659E
0x180006574  mov     rcx, cs:WPP_GLOBAL_Control
0x18000657b  cmp     rcx, r14
0x18000657e  jz      short loc_18000659E
0x180006580  test    byte ptr [rcx+1Ch], 4
0x180006584  jz      short loc_18000659E
0x180006586  mov     edx, 11h
0x18000658b  mov     r9d, eax
0x18000658e  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180006595  mov     rcx, [rcx+10h]
0x180006599  call    WPP_SF_d
0x18000659e  cmp     dword ptr [rdi+4], 1
0x1800065a2  jnz     short loc_1800065AC
0x1800065a4  mov     rcx, rdi; this
0x1800065a7  call    ?_ExitSuspend@CBthActiveConnector@@AEAAXXZ; CBthActiveConnector::_ExitSuspend(void)
0x1800065ac  mov     rcx, rdi; this
0x1800065af  call    ?_InitializeDeviceCount@CBthActiveConnector@@AEAAJXZ; CBthActiveConnector::_InitializeDeviceCount(void)
0x1800065b4  mov     esi, eax
0x1800065b6  test    eax, eax
0x1800065b8  jns     short loc_1800065E1
0x1800065ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065c1  cmp     rcx, r14
0x1800065c4  jz      loc_1800066B7
0x1800065ca  test    byte ptr [rcx+1Ch], 2
0x1800065ce  jz      loc_1800066B7
0x1800065d4  mov     edx, 12h
0x1800065d9  mov     r9d, eax
0x1800065dc  jmp     loc_18000647F
0x1800065e1  lea     r9, [rdi+30h]; RegistrationHandle
0x1800065e5  mov     r8, rbp; Recipient
0x1800065e8  mov     edx, 1; Flags
0x1800065ed  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x1800065f4  call    cs:__imp_PowerSettingRegisterNotification
0x1800065fa  test    eax, eax
0x1800065fc  jz      short loc_18000665B
0x1800065fe  mov     [rdi+30h], r12
0x180006602  call    cs:__imp_GetLastError
0x180006608  test    eax, eax
0x18000660a  jle     short loc_180006616
0x18000660c  movzx   eax, ax
0x18000660f  or      eax, 80070000h
0x180006614  test    eax, eax
0x180006616  jns     short loc_18000665B
0x180006618  mov     rax, cs:WPP_GLOBAL_Control
0x18000661f  cmp     rax, r14
0x180006622  jz      short loc_18000665B
0x180006624  test    byte ptr [rax+1Ch], 2
0x180006628  jz      short loc_18000665B
0x18000662a  call    cs:__imp_GetLastError
0x180006630  test    eax, eax
0x180006632  jle     short loc_18000663C
0x180006634  movzx   eax, ax
0x180006637  or      eax, 80070000h
0x18000663c  mov     edx, 13h
0x180006641  mov     r9d, eax
0x180006644  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x18000664b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006652  mov     rcx, [rcx+10h]
0x180006656  call    WPP_SF_d
0x18000665b  lea     r9, ?_ThreadCreateCallback@CBthActiveConnector@@CAKPEAX@Z; pfnCallback
0x180006662  mov     r8d, 18h; flags
0x180006668  mov     rdx, rdi; pData
0x18000666b  lea     rcx, ?_ThreadProc@CBthActiveConnector@@CAKPEAX@Z; pfnThreadProc
0x180006672  call    cs:__imp_SHCreateThread
0x180006678  test    eax, eax
0x18000667a  jnz     short loc_1800066AD
0x18000667c  call    cs:__imp_GetLastError
0x180006682  mov     esi, eax
0x180006684  test    eax, eax
0x180006686  jle     short loc_180006691
0x180006688  movzx   esi, ax
0x18000668b  or      esi, 80070000h
0x180006691  mov     rcx, cs:WPP_GLOBAL_Control
0x180006698  cmp     rcx, r14
0x18000669b  jz      short loc_1800066B7
0x18000669d  test    byte ptr [rcx+1Ch], 2
0x1800066a1  jz      short loc_1800066B7
0x1800066a3  mov     edx, 14h
0x1800066a8  jmp     loc_18000647C
0x1800066ad  mov     rbx, r12
0x1800066b0  mov     cs:?g_BthActiveConnector@@3PEAVCBthActiveConnector@@EA, rdi; CBthActiveConnector * g_BthActiveConnector
0x1800066b7  test    rbx, rbx
0x1800066ba  jz      short loc_1800066C4
0x1800066bc  mov     rcx, rbx; this
0x1800066bf  call    ??_GCBthActiveConnector@@QEAAPEAXI@Z; CBthActiveConnector::`scalar deleting destructor'(uint)
0x1800066c4  mov     eax, esi
0x1800066c6  mov     rbx, [rsp+48h+arg_8]
0x1800066cb  mov     rbp, [rsp+48h+arg_10]
0x1800066d0  add     rsp, 20h
0x1800066d4  pop     r15
0x1800066d6  pop     r14
0x1800066d8  pop     r12
0x1800066da  pop     rdi
0x1800066db  pop     rsi
0x1800066dc  retn
```
