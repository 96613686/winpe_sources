# NotificationServiceImpl::InitializeFastKADetectionOnWifi(void)

- ea: `0x18006e8dc`
- end: `0x18006eb0b`
- name: `?InitializeFastKADetectionOnWifi@NotificationServiceImpl@@AEAAJXZ`
- size: `559`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180070300`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18006e8dc`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x18006eac9`
- `wlanapi!WlanCloseHandle` at `0x18006eac9`
- `wlanapi!WlanOpenHandle` at `0x18006e955`
- `wlanapi!WlanOpenHandle` at `0x18006e955`
- `wlanapi!WlanRegisterNotification` at `0x18006ea15`
- `wlanapi!WlanRegisterNotification` at `0x18006ea15`

## string_xrefs

- `0x18006e9b3`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006ea7d`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NotificationServiceImpl::InitializeFastKADetectionOnWifi(void **this)
{
  PVOID *v2; // rcx
  signed int v3; // ebx
  HANDLE *v4; // rsi
  signed int v5; // eax
  __int64 v6; // r9
  bool v7; // sf
  __int64 v8; // rdx
  signed int v9; // eax
  __int64 v10; // r9
  bool v11; // sf
  int pCallbackContext; // [rsp+20h] [rbp-58h]
  int pCallbackContexta; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD pdwNegotiatedVersion; // [rsp+80h] [rbp+8h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 263, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  v4 = this + 40;
  if ( this[40] == (void *)-1LL )
  {
    pdwNegotiatedVersion = 0;
    v5 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, this + 40);
    v3 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v5 > 0 )
          v6 = (unsigned __int16)v5 | 0x80070000;
        else
          v6 = (unsigned int)v5;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v6);
      }
      v7 = v3 < 0;
      if ( v3 <= 0 )
      {
LABEL_17:
        if ( v7 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xAF3,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
            (const char *)(unsigned int)v3,
            pCallbackContext);
          v2 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          {
LABEL_38:
            if ( *v4 != (HANDLE)-1LL )
            {
              WlanCloseHandle(*v4, 0);
              v2 = (PVOID *)WPP_GLOBAL_Control;
            }
            goto LABEL_40;
          }
          v8 = 265;
LABEL_37:
          WPP_SF_d(v2[2], v8, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, (unsigned int)v3);
          v2 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_38;
        }
        v9 = WlanRegisterNotification(
               *v4,
               0x18u,
               1,
               (WLAN_NOTIFICATION_CALLBACK)NotificationServiceImpl::WlanCallbackThunk,
               this,
               0,
               0);
        v3 = v9;
        if ( v9 )
        {
          v2 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v10 = (unsigned __int16)v9 | 0x80070000;
            else
              v10 = (unsigned int)v9;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 266, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v10);
            v2 = (PVOID *)WPP_GLOBAL_Control;
          }
          v11 = v3 < 0;
          if ( v3 <= 0 )
            goto LABEL_33;
          v3 = (unsigned __int16)v3 | 0x80070000;
        }
        else
        {
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        v11 = v3 < 0;
LABEL_33:
        if ( !v11 )
          goto LABEL_40;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB03,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)(unsigned int)v3,
          pCallbackContexta);
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_38;
        v8 = 267;
        goto LABEL_37;
      }
      v3 = (unsigned __int16)v3 | 0x80070000;
    }
    v7 = v3 < 0;
    goto LABEL_17;
  }
LABEL_40:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 268, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006e8dc  push    rbx
0x18006e8de  push    rsi
0x18006e8df  push    rdi
0x18006e8e0  push    r12
0x18006e8e2  push    r13
0x18006e8e4  push    r14
0x18006e8e6  sub     rsp, 48h
0x18006e8ea  mov     rdi, rcx
0x18006e8ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e8f4  lea     r14, WPP_GLOBAL_Control
0x18006e8fb  lea     r12, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006e902  cmp     rcx, r14
0x18006e905  jz      short loc_18006E92B
0x18006e907  test    byte ptr [rcx+1Ch], 2
0x18006e90b  jz      short loc_18006E92B
0x18006e90d  cmp     byte ptr [rcx+19h], 6
0x18006e911  jb      short loc_18006E92B
0x18006e913  mov     rcx, [rcx+10h]
0x18006e917  mov     edx, 107h
0x18006e91c  mov     r8, r12
0x18006e91f  call    WPP_SF_
0x18006e924  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e92b  xor     ebx, ebx
0x18006e92d  lea     rsi, [rdi+140h]
0x18006e934  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18006e938  jnz     loc_18006EAD6
0x18006e93e  mov     r9, rsi; phClientHandle
0x18006e941  mov     [rsp+78h+pdwNegotiatedVersion], ebx
0x18006e948  lea     r8, [rsp+78h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18006e950  xor     edx, edx; pReserved
0x18006e952  lea     ecx, [rbx+2]; dwClientVersion
0x18006e955  call    cs:__imp_WlanOpenHandle
0x18006e95b  mov     ebx, eax
0x18006e95d  mov     r13d, 80070000h
0x18006e963  test    eax, eax
0x18006e965  jz      short loc_18006E9AA
0x18006e967  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e96e  cmp     rcx, r14
0x18006e971  jz      short loc_18006E9A0
0x18006e973  test    byte ptr [rcx+1Ch], 4
0x18006e977  jz      short loc_18006E9A0
0x18006e979  cmp     byte ptr [rcx+19h], 2
0x18006e97d  jb      short loc_18006E9A0
0x18006e97f  test    eax, eax
0x18006e981  jg      short loc_18006E988
0x18006e983  mov     r9d, eax
0x18006e986  jmp     short loc_18006E98F
0x18006e988  movzx   r9d, bx
0x18006e98c  or      r9d, r13d
0x18006e98f  mov     rcx, [rcx+10h]
0x18006e993  mov     edx, 108h
0x18006e998  mov     r8, r12
0x18006e99b  call    WPP_SF_d
0x18006e9a0  test    ebx, ebx
0x18006e9a2  jle     short loc_18006E9AC
0x18006e9a4  movzx   ebx, bx
0x18006e9a7  or      ebx, r13d
0x18006e9aa  test    ebx, ebx
0x18006e9ac  jns     short loc_18006E9EB
0x18006e9ae  mov     rcx, [rsp+78h]; this
0x18006e9b3  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006e9ba  mov     r9d, ebx; char *
0x18006e9bd  mov     edx, 0AF3h; void *
0x18006e9c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006e9c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e9ce  cmp     rcx, r14
0x18006e9d1  jz      loc_18006EABE
0x18006e9d7  test    byte ptr [rcx+1Ch], 80h
0x18006e9db  jz      loc_18006EABE
0x18006e9e1  mov     edx, 109h
0x18006e9e6  jmp     loc_18006EAA8
0x18006e9eb  mov     rcx, [rsi]; hClientHandle
0x18006e9ee  lea     r9, ?WlanCallbackThunk@NotificationServiceImpl@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x18006e9f5  mov     edx, 18h; dwNotifSource
0x18006e9fa  mov     [rsp+78h+pdwPrevNotifSource], 0; pdwPrevNotifSource
0x18006ea03  mov     [rsp+78h+pReserved], 0; pReserved
0x18006ea0c  mov     [rsp+78h+pCallbackContext], rdi; int
0x18006ea11  lea     r8d, [rdx-17h]; bIgnoreDuplicate
0x18006ea15  call    cs:__imp_WlanRegisterNotification
0x18006ea1b  mov     ebx, eax
0x18006ea1d  test    eax, eax
0x18006ea1f  jz      short loc_18006EA6D
0x18006ea21  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ea28  cmp     rcx, r14
0x18006ea2b  jz      short loc_18006EA61
0x18006ea2d  test    byte ptr [rcx+1Ch], 4
0x18006ea31  jz      short loc_18006EA61
0x18006ea33  cmp     byte ptr [rcx+19h], 2
0x18006ea37  jb      short loc_18006EA61
0x18006ea39  test    eax, eax
0x18006ea3b  jg      short loc_18006EA42
0x18006ea3d  mov     r9d, eax
0x18006ea40  jmp     short loc_18006EA49
0x18006ea42  movzx   r9d, bx
0x18006ea46  or      r9d, r13d
0x18006ea49  mov     rcx, [rcx+10h]
0x18006ea4d  mov     edx, 10Ah
0x18006ea52  mov     r8, r12
0x18006ea55  call    WPP_SF_d
0x18006ea5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ea61  test    ebx, ebx
0x18006ea63  jle     short loc_18006EA76
0x18006ea65  movzx   ebx, bx
0x18006ea68  or      ebx, r13d
0x18006ea6b  jmp     short loc_18006EA74
0x18006ea6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ea74  test    ebx, ebx
0x18006ea76  jns     short loc_18006EAD6
0x18006ea78  mov     rcx, [rsp+78h]; this
0x18006ea7d  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006ea84  mov     r9d, ebx; char *
0x18006ea87  mov     edx, 0B03h; void *
0x18006ea8c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006ea91  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ea98  cmp     rcx, r14
0x18006ea9b  jz      short loc_18006EABE
0x18006ea9d  test    byte ptr [rcx+1Ch], 80h
0x18006eaa1  jz      short loc_18006EABE
0x18006eaa3  mov     edx, 10Bh
0x18006eaa8  mov     rcx, [rcx+10h]
0x18006eaac  mov     r9d, ebx
0x18006eaaf  mov     r8, r12
0x18006eab2  call    WPP_SF_d
0x18006eab7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eabe  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18006eac2  jz      short loc_18006EAD6
0x18006eac4  mov     rcx, [rsi]; hClientHandle
0x18006eac7  xor     edx, edx; pReserved
0x18006eac9  call    cs:__imp_WlanCloseHandle
0x18006eacf  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ead6  cmp     rcx, r14
0x18006ead9  jz      short loc_18006EAFB
0x18006eadb  test    byte ptr [rcx+1Ch], 2
0x18006eadf  jz      short loc_18006EAFB
0x18006eae1  cmp     byte ptr [rcx+19h], 6
0x18006eae5  jb      short loc_18006EAFB
0x18006eae7  mov     rcx, [rcx+10h]
0x18006eaeb  mov     edx, 10Ch
0x18006eaf0  mov     r9d, ebx
0x18006eaf3  mov     r8, r12
0x18006eaf6  call    WPP_SF_d
0x18006eafb  mov     eax, ebx
0x18006eafd  add     rsp, 48h
0x18006eb01  pop     r14
0x18006eb03  pop     r13
0x18006eb05  pop     r12
0x18006eb07  pop     rdi
0x18006eb08  pop     rsi
0x18006eb09  pop     rbx
0x18006eb0a  retn
```
