# FWUPDATE_AddIdsForFirmwareUpdateDevice

- ea: `0x14008ece0`
- end: `0x14008f09d`
- name: `FWUPDATE_AddIdsForFirmwareUpdateDevice`
- size: `957`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008f0a4`

## callees

- `0x1400024b8`
- `0x14000f648`
- `0x140045530`
- `0x140045570`
- `0x14008ece0`

## string_xrefs

- `0x14008efea`: `USB\MS_COMP_WINUSB`
- `0x14008ef70`: `USB\MS_COMP_WINUSB&MS_SUBCOMP_GFU`

## pseudocode

```c
__int64 __fastcall FWUPDATE_AddIdsForFirmwareUpdateDevice(__int64 a1, __int64 a2)
{
  __int64 v2; // r9
  __int64 v3; // r8
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  _UNKNOWN **v8; // rdx
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+20h] [rbp-E0h]
  __int64 v13; // [rsp+28h] [rbp-D8h]
  int v14; // [rsp+28h] [rbp-D8h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  char v16; // [rsp+40h] [rbp-C0h] BYREF

  v2 = *(unsigned __int16 *)(a1 + 2738);
  v3 = *(unsigned __int16 *)(a1 + 2736);
  DestinationString.Buffer = (wchar_t *)&v16;
  *(_QWORD *)&DestinationString.Length = 11796480;
  v6 = RtlUnicodeStringPrintf(&DestinationString, L"USB\\VID_%04X&PID_%04X&GFU", v3, v2);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1696))(
           WdfDriverGlobals,
           a2,
           &DestinationString);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v14 = *(unsigned __int16 *)(a1 + 2742);
      v11 = *(unsigned __int16 *)(a1 + 2740);
      v6 = RtlUnicodeStringPrintf(
             &DestinationString,
             L"USB\\VID_%04X&PID_%04X&BCD_%04X&REV_%04X&GFU",
             *(unsigned __int16 *)(a1 + 2736),
             *(unsigned __int16 *)(a1 + 2738),
             v11,
             v14);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015
                                                                                               + 1712))(
               WdfDriverGlobals,
               a2,
               &DestinationString);
        v7 = v6;
        if ( v6 >= 0 )
        {
          LODWORD(v12) = *(unsigned __int16 *)(a1 + 2740);
          v6 = RtlUnicodeStringPrintf(
                 &DestinationString,
                 L"USB\\VID_%04X&PID_%04X&BCD_%04X&GFU",
                 *(unsigned __int16 *)(a1 + 2736),
                 *(unsigned __int16 *)(a1 + 2738),
                 v12);
          v7 = v6;
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1712))(
                   WdfDriverGlobals,
                   a2,
                   &DestinationString);
            v7 = v6;
            if ( v6 >= 0 )
            {
              v6 = RtlUnicodeStringPrintf(
                     &DestinationString,
                     L"USB\\VID_%04X&PID_%04X&GFU",
                     *(unsigned __int16 *)(a1 + 2736),
                     *(unsigned __int16 *)(a1 + 2738));
              v7 = v6;
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1712))(
                       WdfDriverGlobals,
                       a2,
                       &DestinationString);
                v7 = v6;
                if ( v6 >= 0 )
                {
                  v6 = RtlUnicodeStringPrintf(&DestinationString, L"USB\\MS_COMP_WINUSB&MS_SUBCOMP_GFU");
                  v7 = v6;
                  if ( v6 >= 0 )
                  {
                    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1720))(
                           WdfDriverGlobals,
                           a2,
                           &DestinationString);
                    v7 = v6;
                    if ( v6 >= 0 )
                    {
                      v6 = RtlUnicodeStringPrintf(&DestinationString, L"USB\\MS_COMP_WINUSB");
                      v7 = v6;
                      if ( v6 >= 0 )
                      {
                        v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1720))(
                               WdfDriverGlobals,
                               a2,
                               &DestinationString);
                        v7 = v6;
                        if ( v6 < 0 )
                        {
                          v8 = &WPP_RECORDER_INITIALIZED;
                          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                          {
                            v9 = 22;
                            goto LABEL_37;
                          }
                        }
                      }
                      else
                      {
                        v8 = &WPP_RECORDER_INITIALIZED;
                        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          v9 = 21;
                          goto LABEL_37;
                        }
                      }
                    }
                    else
                    {
                      v8 = &WPP_RECORDER_INITIALIZED;
                      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      {
                        v9 = 20;
                        goto LABEL_37;
                      }
                    }
                  }
                  else
                  {
                    v8 = &WPP_RECORDER_INITIALIZED;
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      v9 = 19;
                      goto LABEL_37;
                    }
                  }
                }
                else
                {
                  v8 = &WPP_RECORDER_INITIALIZED;
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    v9 = 18;
                    goto LABEL_37;
                  }
                }
              }
              else
              {
                v8 = &WPP_RECORDER_INITIALIZED;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  v9 = 17;
                  goto LABEL_37;
                }
              }
            }
            else
            {
              v8 = &WPP_RECORDER_INITIALIZED;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v9 = 16;
                goto LABEL_37;
              }
            }
          }
          else
          {
            v8 = &WPP_RECORDER_INITIALIZED;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v9 = 15;
              goto LABEL_37;
            }
          }
        }
        else
        {
          v8 = &WPP_RECORDER_INITIALIZED;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v9 = 14;
            goto LABEL_37;
          }
        }
      }
      else
      {
        v8 = &WPP_RECORDER_INITIALIZED;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v9 = 13;
          goto LABEL_37;
        }
      }
    }
    else
    {
      v8 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = 12;
        goto LABEL_37;
      }
    }
  }
  else
  {
    v8 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 11;
LABEL_37:
      LODWORD(v13) = v6;
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 2536),
        (_DWORD)v8,
        3,
        v9,
        (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
        v13);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14008ece0  mov     [rsp-8+arg_10], rbx
0x14008ece5  push    rbp
0x14008ece6  push    rsi
0x14008ece7  push    rdi
0x14008ece8  lea     rbp, [rsp-10h]
0x14008eced  sub     rsp, 110h
0x14008ecf4  mov     rax, cs:__security_cookie
0x14008ecfb  xor     rax, rsp
0x14008ecfe  mov     [rbp+20h+var_20], rax
0x14008ed02  movzx   r9d, word ptr [rcx+0AB2h]
0x14008ed0a  lea     rax, [rsp+120h+var_E0]
0x14008ed0f  movzx   r8d, word ptr [rcx+0AB0h]
0x14008ed17  mov     rsi, rdx
0x14008ed1a  mov     rdi, rcx
0x14008ed1d  mov     [rsp+120h+DestinationString.Buffer], rax
0x14008ed22  lea     rdx, aUsbVid04xPid04_7; "USB\\VID_%04X&PID_%04X&GFU"
0x14008ed29  mov     qword ptr [rsp+120h+DestinationString.Length], 0B40000h
0x14008ed32  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14008ed37  call    RtlUnicodeStringPrintf
0x14008ed3c  mov     ebx, eax
0x14008ed3e  test    eax, eax
0x14008ed40  jns     short loc_14008ED61
0x14008ed42  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ed49  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008ed50  jz      loc_14008F07B
0x14008ed56  mov     r9d, 0Bh
0x14008ed5c  jmp     loc_14008F057
0x14008ed61  mov     rax, cs:WdfFunctions_01015
0x14008ed68  lea     r8, [rsp+120h+DestinationString]
0x14008ed6d  mov     rcx, cs:WdfDriverGlobals
0x14008ed74  mov     rdx, rsi
0x14008ed77  mov     rax, [rax+6A0h]
0x14008ed7e  call    _guard_dispatch_icall
0x14008ed83  mov     ebx, eax
0x14008ed85  test    eax, eax
0x14008ed87  jns     short loc_14008EDA8
0x14008ed89  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ed90  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008ed97  jz      loc_14008F07B
0x14008ed9d  mov     r9d, 0Ch
0x14008eda3  jmp     loc_14008F057
0x14008eda8  movzx   ecx, word ptr [rdi+0AB4h]
0x14008edaf  lea     rdx, aUsbVid04xPid04_3; "USB\\VID_%04X&PID_%04X&BCD_%04X&REV_%04"...
0x14008edb6  movzx   eax, word ptr [rdi+0AB6h]
0x14008edbd  movzx   r9d, word ptr [rdi+0AB2h]
0x14008edc5  movzx   r8d, word ptr [rdi+0AB0h]
0x14008edcd  mov     dword ptr [rsp+120h+var_F8], eax
0x14008edd1  mov     dword ptr [rsp+120h+var_100], ecx
0x14008edd5  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14008edda  call    RtlUnicodeStringPrintf
0x14008eddf  mov     ebx, eax
0x14008ede1  test    eax, eax
0x14008ede3  jns     short loc_14008EE04
0x14008ede5  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008edec  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008edf3  jz      loc_14008F07B
0x14008edf9  mov     r9d, 0Dh
0x14008edff  jmp     loc_14008F057
0x14008ee04  mov     rax, cs:WdfFunctions_01015
0x14008ee0b  lea     r8, [rsp+120h+DestinationString]
0x14008ee10  mov     rcx, cs:WdfDriverGlobals
0x14008ee17  mov     rdx, rsi
0x14008ee1a  mov     rax, [rax+6B0h]
0x14008ee21  call    _guard_dispatch_icall
0x14008ee26  mov     ebx, eax
0x14008ee28  test    eax, eax
0x14008ee2a  jns     short loc_14008EE4B
0x14008ee2c  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ee33  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008ee3a  jz      loc_14008F07B
0x14008ee40  mov     r9d, 0Eh
0x14008ee46  jmp     loc_14008F057
0x14008ee4b  movzx   eax, word ptr [rdi+0AB4h]
0x14008ee52  lea     rdx, aUsbVid04xPid04_2; "USB\\VID_%04X&PID_%04X&BCD_%04X&GFU"
0x14008ee59  movzx   r9d, word ptr [rdi+0AB2h]
0x14008ee61  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14008ee66  movzx   r8d, word ptr [rdi+0AB0h]
0x14008ee6e  mov     dword ptr [rsp+120h+var_100], eax
0x14008ee72  call    RtlUnicodeStringPrintf
0x14008ee77  mov     ebx, eax
0x14008ee79  test    eax, eax
0x14008ee7b  jns     short loc_14008EE9C
0x14008ee7d  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ee84  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008ee8b  jz      loc_14008F07B
0x14008ee91  mov     r9d, 0Fh
0x14008ee97  jmp     loc_14008F057
0x14008ee9c  mov     rax, cs:WdfFunctions_01015
0x14008eea3  lea     r8, [rsp+120h+DestinationString]
0x14008eea8  mov     rcx, cs:WdfDriverGlobals
0x14008eeaf  mov     rdx, rsi
0x14008eeb2  mov     rax, [rax+6B0h]
0x14008eeb9  call    _guard_dispatch_icall
0x14008eebe  mov     ebx, eax
0x14008eec0  test    eax, eax
0x14008eec2  jns     short loc_14008EEE3
0x14008eec4  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008eecb  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008eed2  jz      loc_14008F07B
0x14008eed8  mov     r9d, 10h
0x14008eede  jmp     loc_14008F057
0x14008eee3  movzx   r9d, word ptr [rdi+0AB2h]
0x14008eeeb  lea     rdx, aUsbVid04xPid04_7; "USB\\VID_%04X&PID_%04X&GFU"
0x14008eef2  movzx   r8d, word ptr [rdi+0AB0h]
0x14008eefa  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14008eeff  call    RtlUnicodeStringPrintf
0x14008ef04  mov     ebx, eax
0x14008ef06  test    eax, eax
0x14008ef08  jns     short loc_14008EF29
0x14008ef0a  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ef11  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008ef18  jz      loc_14008F07B
0x14008ef1e  mov     r9d, 11h
0x14008ef24  jmp     loc_14008F057
0x14008ef29  mov     rax, cs:WdfFunctions_01015
0x14008ef30  lea     r8, [rsp+120h+DestinationString]
0x14008ef35  mov     rcx, cs:WdfDriverGlobals
0x14008ef3c  mov     rdx, rsi
0x14008ef3f  mov     rax, [rax+6B0h]
0x14008ef46  call    _guard_dispatch_icall
0x14008ef4b  mov     ebx, eax
0x14008ef4d  test    eax, eax
0x14008ef4f  jns     short loc_14008EF70
0x14008ef51  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ef58  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008ef5f  jz      loc_14008F07B
0x14008ef65  mov     r9d, 12h
0x14008ef6b  jmp     loc_14008F057
0x14008ef70  lea     rdx, aUsbMsCompWinus_0; "USB\\MS_COMP_WINUSB&MS_SUBCOMP_GFU"
0x14008ef77  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14008ef7c  call    RtlUnicodeStringPrintf
0x14008ef81  mov     ebx, eax
0x14008ef83  test    eax, eax
0x14008ef85  jns     short loc_14008EFA6
0x14008ef87  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ef8e  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008ef95  jz      loc_14008F07B
0x14008ef9b  mov     r9d, 13h
0x14008efa1  jmp     loc_14008F057
0x14008efa6  mov     rax, cs:WdfFunctions_01015
0x14008efad  lea     r8, [rsp+120h+DestinationString]
0x14008efb2  mov     rcx, cs:WdfDriverGlobals
0x14008efb9  mov     rdx, rsi
0x14008efbc  mov     rax, [rax+6B8h]
0x14008efc3  call    _guard_dispatch_icall
0x14008efc8  mov     ebx, eax
0x14008efca  test    eax, eax
0x14008efcc  jns     short loc_14008EFEA
0x14008efce  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008efd5  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008efdc  jz      loc_14008F07B
0x14008efe2  mov     r9d, 14h
0x14008efe8  jmp     short loc_14008F057
0x14008efea  lea     rdx, aUsbMsCompWinus; "USB\\MS_COMP_WINUSB"
0x14008eff1  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14008eff6  call    RtlUnicodeStringPrintf
0x14008effb  mov     ebx, eax
0x14008effd  test    eax, eax
0x14008efff  jns     short loc_14008F019
0x14008f001  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008f008  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008f00f  jz      short loc_14008F07B
0x14008f011  mov     r9d, 15h
0x14008f017  jmp     short loc_14008F057
0x14008f019  mov     rax, cs:WdfFunctions_01015
0x14008f020  lea     r8, [rsp+120h+DestinationString]
0x14008f025  mov     rcx, cs:WdfDriverGlobals
0x14008f02c  mov     rdx, rsi
0x14008f02f  mov     rax, [rax+6B8h]
0x14008f036  call    _guard_dispatch_icall
0x14008f03b  mov     ebx, eax
0x14008f03d  test    eax, eax
0x14008f03f  jns     short loc_14008F07B
0x14008f041  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008f048  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008f04f  jz      short loc_14008F07B
0x14008f051  mov     r9d, 16h
0x14008f057  mov     rcx, [rdi+9E8h]
0x14008f05e  mov     r8d, 3
0x14008f064  mov     dword ptr [rsp+120h+var_F8], eax
0x14008f068  mov     dl, 2
0x14008f06a  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x14008f071  mov     [rsp+120h+var_100], rax
0x14008f076  call    WPP_RECORDER_SF_d
0x14008f07b  mov     eax, ebx
0x14008f07d  mov     rcx, [rbp+20h+var_20]
0x14008f081  xor     rcx, rsp; StackCookie
0x14008f084  call    __security_check_cookie
0x14008f089  mov     rbx, [rsp+120h+arg_10]
0x14008f091  add     rsp, 110h
0x14008f098  pop     rdi
0x14008f099  pop     rsi
0x14008f09a  pop     rbp
0x14008f09b  retn
```
