# HUBFDO_PowerSettingCallback

- ea: `0x14000e910`
- end: `0x14000ec93`
- name: `HUBFDO_PowerSettingCallback`
- size: `899`
- prototype: `POWER_SETTING_CALLBACK`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000e910`
- `0x14000f864`
- `0x140045530`
- `0x140045570`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000e96a`
- `ntoskrnl!RtlCompareMemory` at `0x14000eb21`
- `ntoskrnl!RtlCompareMemory` at `0x14000e96a`
- `ntoskrnl!RtlCompareMemory` at `0x14000eb21`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000ead0`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000ead0`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000ea30`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000ea30`

## pseudocode

```c
__int64 __fastcall HUBFDO_PowerSettingCallback(LPCGUID SettingGuid, int *Value, ULONG ValueLength, PVOID Context)
{
  bool v4; // zf
  int v9; // ebx
  int v10; // edx
  int v11; // eax
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // edx
  __int128 v22; // [rsp+40h] [rbp-30h] BYREF
  __int128 v23; // [rsp+50h] [rbp-20h]
  int v24; // [rsp+60h] [rbp-10h]

  v4 = (*((_DWORD *)Context + 10) & 0x4000000) == 0;
  v24 = 0;
  v22 = 0;
  v23 = 0;
  if ( v4 )
    return (unsigned int)-1073741811;
  v9 = 0;
  if ( RtlCompareMemory(SettingGuid, &GUID_USB_SETTING_SELECTIVE_SUSPEND, 0x10u) == 16 )
  {
    if ( ValueLength >= 4 && (unsigned int)*Value <= 1 )
    {
      v11 = *((_DWORD *)Context + 10) & 0x8000000;
      if ( *Value == 1 )
      {
        if ( v11 )
        {
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64, const char *))(WdfFunctions_01015 + 3512))(
            WdfDriverGlobals,
            *((_QWORD *)Context + 2),
            0,
            6297,
            "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubfdo.c");
          _InterlockedAnd((volatile signed __int32 *)Context + 10, 0xF7FFFFFF);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 4;
            WPP_RECORDER_SF_(
              *((_QWORD *)Context + 317),
              v12,
              3,
              90,
              (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
          }
          if ( *((_QWORD *)Context + 331) )
            SleepstudyHelper_ComponentInactive();
        }
      }
      else if ( !v11 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 4;
          WPP_RECORDER_SF_(
            *((_QWORD *)Context + 317),
            v10,
            3,
            91,
            (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids);
        }
        v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, _QWORD, int, const char *))(WdfFunctions_01015 + 3504))(
               WdfDriverGlobals,
               *((_QWORD *)Context + 2),
               0,
               0,
               6314,
               "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubfdo.c");
        if ( v9 < 0 )
        {
          v9 = 0;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v13) = 3;
            WPP_RECORDER_SF_d(
              *((_QWORD *)Context + 317),
              v13,
              3,
              92,
              (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
              0);
          }
        }
        else
        {
          _InterlockedOr((volatile signed __int32 *)Context + 10, 0x8000000u);
          if ( *((_QWORD *)Context + 331) )
            SleepstudyHelper_ComponentActive();
        }
      }
      return (unsigned int)v9;
    }
    return (unsigned int)-1073741811;
  }
  if ( RtlCompareMemory(SettingGuid, &GUID_POWER_HUB_SELECTIVE_SUSPEND_TIMEOUT, 0x10u) != 16 )
    return (unsigned int)-1073741811;
  if ( *Value != *((_DWORD *)Context + 648) )
  {
    if ( (unsigned int)*Value >= *((_DWORD *)Context + 649) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = 4;
        WPP_RECORDER_SF_d(
          *((_QWORD *)Context + 317),
          v14,
          3,
          94,
          (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
          *Value);
      }
      v17 = *Value;
      *((_QWORD *)&v23 + 1) = 2;
      v24 = 2;
      *(_QWORD *)&v23 = 0x200000002LL;
      *(_QWORD *)&v22 = 0x200000024LL;
      HIDWORD(v22) = v17;
      DWORD2(v22) = 3;
      if ( !*((_BYTE *)Context + 240) || (*((_DWORD *)Context + 11) & 0x20) != 0 )
        HIDWORD(v23) = 2;
      v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, PVOID))(WdfFunctions_01015 + 1632))(
              WdfDriverGlobals,
              Context);
      v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 368))(
              WdfDriverGlobals,
              v18,
              &v22);
      v9 = v19;
      if ( v19 >= 0 )
      {
        *((_DWORD *)Context + 648) = *Value;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v20) = 3;
          WPP_RECORDER_SF_d(
            *((_QWORD *)Context + 317),
            v20,
            3,
            95,
            (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
            v19);
        }
        return 0;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_LL(*((_QWORD *)Context + 317), v14, v15, v16);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000e910  push    rbp
0x14000e912  push    rbx
0x14000e913  push    rsi
0x14000e914  push    rdi
0x14000e915  push    r12
0x14000e917  push    r14
0x14000e919  push    r15
0x14000e91b  mov     rbp, rsp
0x14000e91e  sub     rsp, 70h
0x14000e922  mov     rax, cs:__security_cookie
0x14000e929  xor     rax, rsp
0x14000e92c  mov     [rbp+var_8], rax
0x14000e930  xor     eax, eax
0x14000e932  xorps   xmm0, xmm0
0x14000e935  test    dword ptr [r9+28h], 4000000h
0x14000e93d  mov     rdi, r9
0x14000e940  mov     r14d, r8d
0x14000e943  mov     [rbp+var_10], eax
0x14000e946  mov     r12, rdx
0x14000e949  mov     rsi, rcx
0x14000e94c  movups  [rbp+var_30], xmm0
0x14000e950  movups  [rbp+var_20], xmm0
0x14000e954  jz      loc_14000EC70
0x14000e95a  lea     r15d, [rax+10h]
0x14000e95e  xor     ebx, ebx
0x14000e960  mov     r8d, r15d; Length
0x14000e963  lea     rdx, GUID_USB_SETTING_SELECTIVE_SUSPEND; Source2
0x14000e96a  call    cs:__imp_RtlCompareMemory
0x14000e971  nop     dword ptr [rax+rax+00h]
0x14000e976  cmp     rax, r15
0x14000e979  jnz     loc_14000EB14
0x14000e97f  cmp     r14d, 4
0x14000e983  jb      loc_14000EC70
0x14000e989  mov     ecx, [r12]
0x14000e98d  cmp     ecx, 1
0x14000e990  ja      loc_14000EC70
0x14000e996  mov     eax, [rdi+28h]
0x14000e999  mov     r12d, 8000000h
0x14000e99f  and     eax, r12d
0x14000e9a2  cmp     ecx, 1
0x14000e9a5  jnz     loc_14000EA41
0x14000e9ab  test    eax, eax
0x14000e9ad  jz      loc_14000EC75
0x14000e9b3  mov     rax, cs:WdfFunctions_01015
0x14000e9ba  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14000e9c1  mov     rdx, [rdi+10h]
0x14000e9c5  mov     r9d, 1899h
0x14000e9cb  mov     [rsp+70h+var_50], rcx
0x14000e9d0  xor     r8d, r8d
0x14000e9d3  mov     rcx, cs:WdfDriverGlobals
0x14000e9da  mov     rax, [rax+0DB8h]
0x14000e9e1  call    _guard_dispatch_icall
0x14000e9e6  lock and dword ptr [rdi+28h], 0F7FFFFFFh
0x14000e9ee  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e9f5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000e9fc  jz      short loc_14000EA20
0x14000e9fe  mov     rcx, [rdi+9E8h]
0x14000ea05  lea     r15, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000ea0c  lea     r9d, [rbx+5Ah]
0x14000ea10  mov     [rsp+70h+var_50], r15
0x14000ea15  lea     r8d, [rbx+3]
0x14000ea19  mov     dl, 4
0x14000ea1b  call    WPP_RECORDER_SF_
0x14000ea20  mov     rcx, [rdi+0A58h]
0x14000ea27  test    rcx, rcx
0x14000ea2a  jz      loc_14000EC75
0x14000ea30  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x14000ea37  nop     dword ptr [rax+rax+00h]
0x14000ea3c  jmp     loc_14000EC75
0x14000ea41  test    eax, eax
0x14000ea43  jnz     loc_14000EC75
0x14000ea49  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ea50  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000ea57  lea     r15, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000ea5e  lea     esi, [rax+3]
0x14000ea61  jz      short loc_14000EA7D
0x14000ea63  mov     rcx, [rdi+9E8h]
0x14000ea6a  lea     r9d, [rax+5Bh]
0x14000ea6e  mov     r8d, esi
0x14000ea71  mov     [rsp+70h+var_50], r15
0x14000ea76  mov     dl, 4
0x14000ea78  call    WPP_RECORDER_SF_
0x14000ea7d  mov     rax, cs:WdfFunctions_01015
0x14000ea84  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14000ea8b  mov     rdx, [rdi+10h]
0x14000ea8f  xor     r9d, r9d
0x14000ea92  mov     [rsp+70h+var_48], rcx
0x14000ea97  xor     r8d, r8d
0x14000ea9a  mov     rcx, cs:WdfDriverGlobals
0x14000eaa1  mov     rax, [rax+0DB0h]
0x14000eaa8  mov     dword ptr [rsp+70h+var_50], 18AAh
0x14000eab0  call    _guard_dispatch_icall
0x14000eab5  mov     ebx, eax
0x14000eab7  test    eax, eax
0x14000eab9  js      short loc_14000EAE1
0x14000eabb  lock or [rdi+28h], r12d
0x14000eac0  mov     rcx, [rdi+0A58h]
0x14000eac7  test    rcx, rcx
0x14000eaca  jz      loc_14000EC75
0x14000ead0  call    cs:__imp_SleepstudyHelper_ComponentActive
0x14000ead7  nop     dword ptr [rax+rax+00h]
0x14000eadc  jmp     loc_14000EC75
0x14000eae1  xor     ebx, ebx
0x14000eae3  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000eaea  jz      loc_14000EC75
0x14000eaf0  mov     rcx, [rdi+9E8h]
0x14000eaf7  lea     r9d, [rbx+5Ch]
0x14000eafb  mov     dword ptr [rsp+70h+var_48], ebx
0x14000eaff  mov     r8d, esi
0x14000eb02  mov     dl, sil
0x14000eb05  mov     [rsp+70h+var_50], r15
0x14000eb0a  call    WPP_RECORDER_SF_d
0x14000eb0f  jmp     loc_14000EC75
0x14000eb14  mov     r8, r15; Length
0x14000eb17  lea     rdx, GUID_POWER_HUB_SELECTIVE_SUSPEND_TIMEOUT; Source2
0x14000eb1e  mov     rcx, rsi; Source1
0x14000eb21  call    cs:__imp_RtlCompareMemory
0x14000eb28  nop     dword ptr [rax+rax+00h]
0x14000eb2d  cmp     rax, r15
0x14000eb30  jnz     loc_14000EC70
0x14000eb36  mov     eax, [r12]
0x14000eb3a  cmp     eax, [rdi+0A20h]
0x14000eb40  jz      loc_14000EC75
0x14000eb46  mov     ecx, [rdi+0A24h]
0x14000eb4c  cmp     eax, ecx
0x14000eb4e  jnb     short loc_14000EB7D
0x14000eb50  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000eb57  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000eb5e  jz      loc_14000EC75
0x14000eb64  mov     [rsp+70h+var_40], ecx
0x14000eb68  mov     rcx, [rdi+9E8h]
0x14000eb6f  mov     dword ptr [rsp+70h+var_48], eax
0x14000eb73  call    WPP_RECORDER_SF_LL
0x14000eb78  jmp     loc_14000EC75
0x14000eb7d  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000eb84  mov     esi, 3
0x14000eb89  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000eb90  lea     r15, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14000eb97  jz      short loc_14000EBB7
0x14000eb99  mov     rcx, [rdi+9E8h]
0x14000eba0  lea     r9d, [rsi+5Bh]
0x14000eba4  mov     dword ptr [rsp+70h+var_48], eax
0x14000eba8  mov     r8d, esi
0x14000ebab  mov     dl, 4
0x14000ebad  mov     [rsp+70h+var_50], r15
0x14000ebb2  call    WPP_RECORDER_SF_d
0x14000ebb7  mov     ecx, 2
0x14000ebbc  mov     eax, [r12]
0x14000ebc0  mov     qword ptr [rbp+var_20+8], rcx
0x14000ebc4  mov     [rbp+var_10], ecx
0x14000ebc7  mov     dword ptr [rbp+var_30+4], ecx
0x14000ebca  mov     dword ptr [rbp+var_20], ecx
0x14000ebcd  mov     dword ptr [rbp+var_20+4], ecx
0x14000ebd0  mov     dword ptr [rbp+var_30], 24h ; '$'
0x14000ebd7  mov     dword ptr [rbp+var_30+0Ch], eax
0x14000ebda  mov     dword ptr [rbp+var_30+8], esi
0x14000ebdd  cmp     [rdi+0F0h], bl
0x14000ebe3  jz      short loc_14000EBEC
0x14000ebe5  mov     eax, [rdi+2Ch]
0x14000ebe8  test    al, 20h
0x14000ebea  jz      short loc_14000EBEF
0x14000ebec  mov     dword ptr [rbp+var_20+0Ch], ecx
0x14000ebef  mov     rax, cs:WdfFunctions_01015
0x14000ebf6  mov     rdx, rdi
0x14000ebf9  mov     rcx, cs:WdfDriverGlobals
0x14000ec00  mov     rax, [rax+660h]
0x14000ec07  call    _guard_dispatch_icall
0x14000ec0c  mov     rcx, cs:WdfFunctions_01015
0x14000ec13  lea     r8, [rbp+var_30]
0x14000ec17  mov     rdx, rax
0x14000ec1a  mov     r9, [rcx+170h]
0x14000ec21  mov     rcx, cs:WdfDriverGlobals
0x14000ec28  mov     rax, r9
0x14000ec2b  call    _guard_dispatch_icall
0x14000ec30  mov     ebx, eax
0x14000ec32  test    eax, eax
0x14000ec34  jns     short loc_14000EC64
0x14000ec36  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000ec3d  jz      short loc_14000EC60
0x14000ec3f  mov     rcx, [rdi+9E8h]
0x14000ec46  mov     r9d, 5Fh ; '_'
0x14000ec4c  mov     dword ptr [rsp+70h+var_48], eax
0x14000ec50  mov     r8d, esi
0x14000ec53  mov     dl, sil
0x14000ec56  mov     [rsp+70h+var_50], r15
0x14000ec5b  call    WPP_RECORDER_SF_d
0x14000ec60  xor     ebx, ebx
0x14000ec62  jmp     short loc_14000EC75
0x14000ec64  mov     eax, [r12]
0x14000ec68  mov     [rdi+0A20h], eax
0x14000ec6e  jmp     short loc_14000EC75
0x14000ec70  mov     ebx, 0C000000Dh
0x14000ec75  mov     eax, ebx
0x14000ec77  mov     rcx, [rbp+var_8]
0x14000ec7b  xor     rcx, rsp; StackCookie
0x14000ec7e  call    __security_check_cookie
0x14000ec83  add     rsp, 70h
0x14000ec87  pop     r15
0x14000ec89  pop     r14
0x14000ec8b  pop     r12
0x14000ec8d  pop     rdi
0x14000ec8e  pop     rsi
0x14000ec8f  pop     rbx
0x14000ec90  pop     rbp
0x14000ec91  retn
```
