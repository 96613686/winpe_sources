# HUBFDO_LowPowerEpochCallback

- ea: `0x14000e6d0`
- end: `0x14000e901`
- name: `HUBFDO_LowPowerEpochCallback`
- size: `561`
- prototype: `POWER_SETTING_CALLBACK`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000e6d0`
- `0x140045570`
- `0x140086ad4`

## import_xrefs

- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000e8e5`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000e8e5`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000e83d`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000e83d`

## pseudocode

```c
__int64 __fastcall HUBFDO_LowPowerEpochCallback(LPCGUID SettingGuid, int *Value, __int64 ValueLength, _DWORD *Context)
{
  int v5; // eax
  int v6; // eax
  int v7; // edx
  int v9; // [rsp+58h] [rbp+10h] BYREF

  if ( Context )
  {
    v5 = *Value;
    if ( Context[698] != *Value )
    {
      Context[698] = v5;
      if ( v5 == 1 )
      {
        if ( (Context[10] & 0x8000000) != 0
          && ((Context[11] & 0x100) != 0 || *((_DWORD **)Context + 300) == Context + 600) )
        {
          v9 = 0;
          v6 = HUBREG_OpenQueryAttemptRecoveryFromUsbPowerDrainValue(&v9, Value, ValueLength);
          if ( v6 >= 0 )
          {
            if ( v9 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v7) = 4;
                WPP_RECORDER_SF_(
                  *((_QWORD *)Context + 317),
                  v7,
                  3,
                  119,
                  (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
              }
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, POWER_SETTING_CALLBACK *, __int64, const char *))(WdfFunctions_01015 + 3512))(
                WdfDriverGlobals,
                *((_QWORD *)Context + 2),
                HUBFDO_LowPowerEpochCallback,
                7427,
                "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubfdo.c");
              if ( *((_QWORD *)Context + 331) )
                SleepstudyHelper_ComponentInactive();
              *((_BYTE *)Context + 2796) = 1;
            }
            else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v7) = 3;
              WPP_RECORDER_SF_(
                *((_QWORD *)Context + 317),
                v7,
                3,
                118,
                (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v7) = 3;
            WPP_RECORDER_SF_d(
              *((_QWORD *)Context + 317),
              v7,
              3,
              117,
              (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
              v6);
          }
        }
      }
      else if ( !v5 && *((_BYTE *)Context + 2796) == 1 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(Value) = 4;
          WPP_RECORDER_SF_(
            *((_QWORD *)Context + 317),
            (_DWORD)Value,
            3,
            120,
            (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
        }
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, POWER_SETTING_CALLBACK *, int, const char *))(WdfFunctions_01015 + 3504))(
          WdfDriverGlobals,
          *((_QWORD *)Context + 2),
          0,
          HUBFDO_LowPowerEpochCallback,
          7444,
          "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubfdo.c");
        if ( *((_QWORD *)Context + 331) )
          SleepstudyHelper_ComponentActive();
        *((_BYTE *)Context + 2796) = 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000e6d0  push    rbx
0x14000e6d2  sub     rsp, 40h
0x14000e6d6  mov     rbx, r9
0x14000e6d9  test    r9, r9
0x14000e6dc  jz      loc_14000E8F8
0x14000e6e2  mov     eax, [rdx]
0x14000e6e4  cmp     [r9+0AE8h], eax
0x14000e6eb  jz      loc_14000E8F8
0x14000e6f1  mov     [r9+0AE8h], eax
0x14000e6f8  cmp     eax, 1
0x14000e6fb  jnz     loc_14000E855
0x14000e701  test    dword ptr [r9+28h], 8000000h
0x14000e709  jz      loc_14000E8F8
0x14000e70f  test    dword ptr [r9+2Ch], 100h
0x14000e717  jnz     short loc_14000E729
0x14000e719  lea     rax, [r9+960h]
0x14000e720  cmp     [rax], rax
0x14000e723  jnz     loc_14000E8F8
0x14000e729  lea     rcx, [rsp+48h+arg_8]
0x14000e72e  mov     [rsp+48h+arg_8], 0
0x14000e736  call    HUBREG_OpenQueryAttemptRecoveryFromUsbPowerDrainValue
0x14000e73b  test    eax, eax
0x14000e73d  jns     short loc_14000E781
0x14000e73f  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e746  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000e74d  jz      loc_14000E8F8
0x14000e753  mov     rcx, [rbx+9E8h]
0x14000e75a  mov     r9d, 75h ; 'u'
0x14000e760  mov     dword ptr [rsp+48h+var_20], eax
0x14000e764  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000e76b  mov     [rsp+48h+var_28], rax
0x14000e770  lea     r8d, [r9-72h]
0x14000e774  mov     dl, r8b
0x14000e777  call    WPP_RECORDER_SF_d
0x14000e77c  jmp     loc_14000E8F8
0x14000e781  cmp     [rsp+48h+arg_8], 0
0x14000e786  jnz     short loc_14000E7C6
0x14000e788  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e78f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000e796  jz      loc_14000E8F8
0x14000e79c  mov     rcx, [rbx+9E8h]
0x14000e7a3  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000e7aa  mov     r9d, 76h ; 'v'
0x14000e7b0  mov     [rsp+48h+var_28], rax
0x14000e7b5  lea     r8d, [r9-73h]
0x14000e7b9  mov     dl, r8b
0x14000e7bc  call    WPP_RECORDER_SF_
0x14000e7c1  jmp     loc_14000E8F8
0x14000e7c6  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e7cd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000e7d4  jz      short loc_14000E7FA
0x14000e7d6  mov     rcx, [rbx+9E8h]
0x14000e7dd  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000e7e4  mov     r9d, 77h ; 'w'
0x14000e7ea  mov     [rsp+48h+var_28], rax
0x14000e7ef  mov     dl, 4
0x14000e7f1  lea     r8d, [r9-74h]
0x14000e7f5  call    WPP_RECORDER_SF_
0x14000e7fa  mov     rax, cs:WdfFunctions_01015
0x14000e801  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14000e808  mov     rdx, [rbx+10h]
0x14000e80c  lea     r8, HUBFDO_LowPowerEpochCallback
0x14000e813  mov     [rsp+48h+var_28], rcx
0x14000e818  mov     r9d, 1D03h
0x14000e81e  mov     rcx, cs:WdfDriverGlobals
0x14000e825  mov     rax, [rax+0DB8h]
0x14000e82c  call    _guard_dispatch_icall
0x14000e831  mov     rcx, [rbx+0A58h]
0x14000e838  test    rcx, rcx
0x14000e83b  jz      short loc_14000E849
0x14000e83d  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x14000e844  nop     dword ptr [rax+rax+00h]
0x14000e849  mov     byte ptr [rbx+0AECh], 1
0x14000e850  jmp     loc_14000E8F8
0x14000e855  test    eax, eax
0x14000e857  jnz     loc_14000E8F8
0x14000e85d  cmp     byte ptr [r9+0AECh], 1
0x14000e865  jnz     loc_14000E8F8
0x14000e86b  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e872  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000e879  jz      short loc_14000E89D
0x14000e87b  mov     rcx, [rbx+9E8h]
0x14000e882  lea     r9d, [rax+78h]
0x14000e886  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000e88d  mov     dl, 4
0x14000e88f  lea     r8d, [r9-75h]
0x14000e893  mov     [rsp+48h+var_28], rax
0x14000e898  call    WPP_RECORDER_SF_
0x14000e89d  mov     rax, cs:WdfFunctions_01015
0x14000e8a4  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14000e8ab  mov     rdx, [rbx+10h]
0x14000e8af  lea     r9, HUBFDO_LowPowerEpochCallback
0x14000e8b6  mov     [rsp+48h+var_20], rcx
0x14000e8bb  xor     r8d, r8d
0x14000e8be  mov     rcx, cs:WdfDriverGlobals
0x14000e8c5  mov     rax, [rax+0DB0h]
0x14000e8cc  mov     dword ptr [rsp+48h+var_28], 1D14h
0x14000e8d4  call    _guard_dispatch_icall
0x14000e8d9  mov     rcx, [rbx+0A58h]
0x14000e8e0  test    rcx, rcx
0x14000e8e3  jz      short loc_14000E8F1
0x14000e8e5  call    cs:__imp_SleepstudyHelper_ComponentActive
0x14000e8ec  nop     dword ptr [rax+rax+00h]
0x14000e8f1  mov     byte ptr [rbx+0AECh], 0
0x14000e8f8  xor     eax, eax
0x14000e8fa  add     rsp, 40h
0x14000e8fe  pop     rbx
0x14000e8ff  retn
```
