# Radio::CRadioSwitchManager::Startup(void)

- ea: `0x18002ac70`
- end: `0x18002adca`
- name: `?Startup@CRadioSwitchManager@Radio@@QEAAXXZ`
- size: `346`
- prototype: `void __fastcall(Radio::CRadioSwitchManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002ab40`

## callees

- `0x18002a9e0`
- `0x18002aa14`
- `0x18002ac70`
- `0x18002af7c`
- `0x18002b4e8`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002aca5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002aca5`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18002ad1e`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18002ad1e`
- `Rmapi!__imp_SearchHidDevicesForRadioFeature` at `0x18002acc8`
- `Rmapi!__imp_SearchHidDevicesForRadioFeature` at `0x18002ad95`
- `Rmapi!__imp_SearchHidDevicesForRadioFeature` at `0x18002acc8`
- `Rmapi!__imp_SearchHidDevicesForRadioFeature` at `0x18002ad95`

## pseudocode

```c
void __fastcall Radio::CRadioSwitchManager::Startup(Radio::CRadioSwitchManager *this)
{
  Radio::CRadioSwitchManager *v1; // rcx
  _QWORD v2[2]; // [rsp+20h] [rbp-1B8h] BYREF
  GUID v3; // [rsp+30h] [rbp-1A8h]

  memset_0(v2, 0, 0x1A0u);
  hObject = CreateEventW(0, 0, 0, 0);
  if ( hObject )
  {
    if ( (unsigned __int8)SearchHidDevicesForRadioFeature((unsigned int)dword_18003F248, qword_18003EFF0) )
    {
      LOBYTE(word_18003EFE8) = 1;
      Radio::CRadioSwitchManager::_StartHidReaderThread((DWORD *)&stru_18003EFC0);
    }
    v2[0] = 416;
    v2[1] = 0;
    v3 = GUID_DEVINTERFACE_HID;
    if ( (unsigned int)CM_Register_Notification(
                         v2,
                         &stru_18003EFC0,
                         &Radio::CRadioSwitchManager::s_HidEventCallback,
                         &qword_18003F518) )
    {
      v1 = (Radio::CRadioSwitchManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
      }
    }
    Radio::CRadioSwitchManager::EnsureSliderSwitchAndStoredStateMatch(v1);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
  }
  if ( (unsigned __int8)SearchHidDevicesForRadioFeature(3, qword_18003F250) )
  {
    HIBYTE(word_18003EFE8) = 1;
    Radio::CRadioSwitchManager::EnsureLEDState((Radio::CRadioSwitchManager *)&stru_18003EFC0);
  }
}

```

## disassembly

```asm
0x18002ac70  sub     rsp, 1D8h
0x18002ac77  mov     rax, cs:__security_cookie
0x18002ac7e  xor     rax, rsp
0x18002ac81  mov     [rsp+1D8h+var_18], rax
0x18002ac89  xor     edx, edx; Val
0x18002ac8b  lea     rcx, [rsp+1D8h+var_1B8]; void *
0x18002ac90  mov     r8d, 1A0h; Size
0x18002ac96  call    memset_0
0x18002ac9b  xor     r9d, r9d; lpName
0x18002ac9e  xor     r8d, r8d; bInitialState
0x18002aca1  xor     edx, edx; bManualReset
0x18002aca3  xor     ecx, ecx; lpEventAttributes
0x18002aca5  call    cs:__imp_CreateEventW
0x18002acab  mov     cs:hObject, rax
0x18002acb2  test    rax, rax
0x18002acb5  jz      loc_18002AD5C
0x18002acbb  mov     ecx, cs:dword_18003F248
0x18002acc1  lea     rdx, qword_18003EFF0
0x18002acc8  call    cs:__imp_SearchHidDevicesForRadioFeature
0x18002acce  test    al, al
0x18002acd0  jz      short loc_18002ACE5
0x18002acd2  lea     rcx, stru_18003EFC0; this
0x18002acd9  mov     byte ptr cs:word_18003EFE8, 1
0x18002ace0  call    ?_StartHidReaderThread@CRadioSwitchManager@Radio@@AEAAXXZ; Radio::CRadioSwitchManager::_StartHidReaderThread(void)
0x18002ace5  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_HID.Data1
0x18002acec  lea     r9, qword_18003F518
0x18002acf3  mov     [rsp+1D8h+var_1B8], 1A0h
0x18002acfc  lea     r8, ?s_HidEventCallback@CRadioSwitchManager@Radio@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; Radio::CRadioSwitchManager::s_HidEventCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18002ad03  mov     [rsp+1D8h+var_1B0], 0
0x18002ad0c  lea     rdx, stru_18003EFC0
0x18002ad13  lea     rcx, [rsp+1D8h+var_1B8]
0x18002ad18  movdqu  [rsp+1D8h+var_1A8], xmm0
0x18002ad1e  call    cs:__imp_CM_Register_Notification
0x18002ad24  test    eax, eax
0x18002ad26  jz      short loc_18002AD55
0x18002ad28  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad2f  lea     rax, WPP_GLOBAL_Control
0x18002ad36  cmp     rcx, rax
0x18002ad39  jz      short loc_18002AD55
0x18002ad3b  test    byte ptr [rcx+1Ch], 4
0x18002ad3f  jz      short loc_18002AD55
0x18002ad41  cmp     byte ptr [rcx+19h], 2
0x18002ad45  jb      short loc_18002AD55
0x18002ad47  mov     rcx, [rcx+10h]
0x18002ad4b  mov     edx, 0Ah
0x18002ad50  call    WPP_SF_
0x18002ad55  call    ?EnsureSliderSwitchAndStoredStateMatch@CRadioSwitchManager@Radio@@QEAAXXZ; Radio::CRadioSwitchManager::EnsureSliderSwitchAndStoredStateMatch(void)
0x18002ad5a  jmp     short loc_18002AD89
0x18002ad5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad63  lea     rax, WPP_GLOBAL_Control
0x18002ad6a  cmp     rcx, rax
0x18002ad6d  jz      short loc_18002AD89
0x18002ad6f  test    byte ptr [rcx+1Ch], 4
0x18002ad73  jz      short loc_18002AD89
0x18002ad75  cmp     byte ptr [rcx+19h], 2
0x18002ad79  jb      short loc_18002AD89
0x18002ad7b  mov     rcx, [rcx+10h]
0x18002ad7f  mov     edx, 0Bh
0x18002ad84  call    WPP_SF_
0x18002ad89  lea     rdx, qword_18003F250
0x18002ad90  mov     ecx, 3
0x18002ad95  call    cs:__imp_SearchHidDevicesForRadioFeature
0x18002ad9b  test    al, al
0x18002ad9d  jz      short loc_18002ADB2
0x18002ad9f  lea     rcx, stru_18003EFC0; this
0x18002ada6  mov     byte ptr cs:word_18003EFE8+1, 1
0x18002adad  call    ?EnsureLEDState@CRadioSwitchManager@Radio@@QEAAXXZ; Radio::CRadioSwitchManager::EnsureLEDState(void)
0x18002adb2  mov     rcx, [rsp+1D8h+var_18]
0x18002adba  xor     rcx, rsp; StackCookie
0x18002adbd  call    __security_check_cookie
0x18002adc2  add     rsp, 1D8h
0x18002adc9  retn
```
