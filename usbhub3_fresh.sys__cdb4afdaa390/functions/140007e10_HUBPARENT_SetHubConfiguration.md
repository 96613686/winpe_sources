# HUBPARENT_SetHubConfiguration

- ea: `0x140007e10`
- end: `0x14000823d`
- name: `HUBPARENT_SetHubConfiguration`
- size: `1069`
- prototype: `_UNKNOWN **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009c60`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x140007e10`
- `0x14000a53c`
- `0x14003bd60`
- `0x140045530`
- `0x140045570`
- `0x140045940`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008203`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008203`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x140007fd9`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x140007fd9`

## pseudocode

```c
_UNKNOWN **__fastcall HUBPARENT_SetHubConfiguration(__int64 a1)
{
  int v2; // edx
  int v3; // ecx
  PURB v4; // r14
  struct _USB_CONFIGURATION_DESCRIPTOR *v5; // rdi
  int v6; // ecx
  int v7; // ecx
  __int64 *v8; // rbx
  struct _USB_INTERFACE_DESCRIPTOR *v9; // rax
  int v10; // edx
  _UNKNOWN **result; // rax
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int64 v14; // rdi
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // edi
  __int64 v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v22; // [rsp+68h] [rbp-98h]
  __int128 v23; // [rsp+78h] [rbp-88h]
  __int64 v24; // [rsp+88h] [rbp-78h]
  _USBD_INTERFACE_LIST_ENTRY InterfaceList; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-60h]
  _QWORD v27[9]; // [rsp+B0h] [rbp-50h] BYREF

  LODWORD(v24) = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  memset(v27, 0, sizeof(v27));
  v3 = *(_DWORD *)(a1 + 256);
  v4 = 0;
  v5 = *(struct _USB_CONFIGURATION_DESCRIPTOR **)(a1 + 1272);
  v20 = 0;
  v6 = v3 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 != 1 )
        goto LABEL_9;
    }
    else
    {
      v8 = (__int64 *)(a1 + 2536);
      v9 = (struct _USB_INTERFACE_DESCRIPTOR *)HUBDESC_ParseConfigurationDescriptor(
                                                 (__int64)v5,
                                                 &v5->bLength,
                                                 -1,
                                                 -1,
                                                 9,
                                                 -1,
                                                 2,
                                                 0,
                                                 *(_QWORD *)(a1 + 2536));
      if ( v9 )
        goto LABEL_11;
    }
  }
  v8 = (__int64 *)(a1 + 2536);
  v9 = (struct _USB_INTERFACE_DESCRIPTOR *)HUBDESC_ParseConfigurationDescriptor(
                                             (__int64)v5,
                                             &v5->bLength,
                                             -1,
                                             -1,
                                             9,
                                             -1,
                                             1,
                                             0,
                                             *(_QWORD *)(a1 + 2536));
  if ( !v9 )
  {
    v9 = (struct _USB_INTERFACE_DESCRIPTOR *)HUBDESC_ParseConfigurationDescriptor(
                                               (__int64)v5,
                                               &v5->bLength,
                                               -1,
                                               -1,
                                               9,
                                               -1,
                                               0,
                                               0,
                                               *v8);
    if ( !v9 )
    {
      v9 = (struct _USB_INTERFACE_DESCRIPTOR *)HUBDESC_ParseConfigurationDescriptor(
                                                 (__int64)v5,
                                                 &v5->bLength,
                                                 -1,
                                                 -1,
                                                 9,
                                                 -1,
                                                 -1,
                                                 0,
                                                 *v8);
      if ( !v9 )
      {
LABEL_9:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v2) = 2;
          WPP_RECORDER_SF_(*(_QWORD *)(a1 + 2536), v2, 3, 12, (__int64)WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids);
        }
        goto LABEL_23;
      }
    }
  }
LABEL_11:
  if ( v9->bInterfaceClass != 9 || !v9->bNumEndpoints )
  {
LABEL_23:
    if ( v20 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    return (_UNKNOWN **)HUBSM_AddEvent(a1 + 1280, 2006);
  }
  InterfaceList.InterfaceDescriptor = v9;
  v26 = 0;
  v4 = USBD_CreateConfigurationRequestEx(v5, &InterfaceList);
  if ( v4 )
  {
    v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 336))(
            WdfDriverGlobals,
            *(_QWORD *)(a1 + 16));
    v13 = *(_QWORD *)(a1 + 16);
    v14 = v12;
    *(_QWORD *)&v22 = 0;
    v24 = 0;
    v23 = v13;
    v21 = 0;
    LODWORD(v21) = 56;
    *((_QWORD *)&v22 + 1) = 0x100000001LL;
    v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64 *))(WdfFunctions_01015 + 1976))(
            WdfDriverGlobals,
            &v21,
            v12,
            &v20);
    if ( v16 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v19) = v16;
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_d(*v8, v15, 3, 14, (__int64)WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids, v19);
      }
      goto LABEL_23;
    }
    memset(v27, 0, sizeof(v27));
    LOBYTE(v27[0]) = 15;
    LODWORD(v27[3]) = 2228227;
    v27[1] = v4;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 2016))(
      WdfDriverGlobals,
      v20,
      v27);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, __int64, __int64, __int64), PURB))(WdfFunctions_01015 + 2080))(
      WdfDriverGlobals,
      v20,
      HUBPARENT_SetHubConfigurationComplete,
      v4);
    result = (_UNKNOWN **)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _QWORD))(WdfFunctions_01015 + 2024))(
                            WdfDriverGlobals,
                            v20,
                            v14,
                            0);
    if ( !(_BYTE)result )
    {
      v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, v20);
      result = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v19) = v18;
        LOBYTE(v17) = 2;
        result = (_UNKNOWN **)WPP_RECORDER_SF_d(
                                *v8,
                                v17,
                                3,
                                15,
                                (__int64)WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids,
                                v19);
      }
      if ( v18 < 0 )
        goto LABEL_23;
    }
  }
  else
  {
    result = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      return (_UNKNOWN **)WPP_RECORDER_SF_(*v8, v10, 3, 13, (__int64)WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140007e10  push    rbp
0x140007e12  push    rbx
0x140007e13  push    rsi
0x140007e14  push    rdi
0x140007e15  push    r12
0x140007e17  push    r14
0x140007e19  lea     rbp, [rsp-8]
0x140007e1e  sub     rsp, 108h
0x140007e25  mov     rax, cs:__security_cookie
0x140007e2c  xor     rax, rsp
0x140007e2f  mov     [rbp+30h+var_38], rax
0x140007e33  xorps   xmm0, xmm0
0x140007e36  xor     eax, eax
0x140007e38  mov     rsi, rcx
0x140007e3b  mov     dword ptr [rbp+30h+var_A8], eax
0x140007e3e  xor     edx, edx; Val
0x140007e40  lea     rcx, [rbp+30h+var_80]; void *
0x140007e44  movups  [rsp+130h+var_D8], xmm0
0x140007e49  lea     r8d, [rax+48h]; Size
0x140007e4d  movups  [rsp+130h+var_C8], xmm0
0x140007e52  movups  [rsp+130h+var_B8], xmm0
0x140007e57  call    memset
0x140007e5c  mov     ecx, [rsi+100h]
0x140007e62  xor     r14d, r14d
0x140007e65  mov     rdi, [rsi+4F8h]
0x140007e6c  or      r12d, 0FFFFFFFFh
0x140007e70  mov     [rsp+130h+var_E0], r14
0x140007e75  sub     ecx, 1
0x140007e78  jz      short loc_140007ECC
0x140007e7a  sub     ecx, 1
0x140007e7d  jz      short loc_140007E89
0x140007e7f  cmp     ecx, 1
0x140007e82  jz      short loc_140007ECC
0x140007e84  jmp     loc_140007F79
0x140007e89  lea     rbx, [rsi+9E8h]
0x140007e90  mov     r9d, r12d
0x140007e93  mov     rax, [rbx]
0x140007e96  mov     r8d, r12d
0x140007e99  mov     [rsp+130h+var_F0], rax
0x140007e9e  mov     rdx, rdi
0x140007ea1  mov     [rsp+130h+var_F8], r14
0x140007ea6  mov     rcx, rdi
0x140007ea9  mov     [rsp+130h+var_100], 2
0x140007eb1  mov     dword ptr [rsp+130h+var_108], r12d
0x140007eb6  mov     dword ptr [rsp+130h+var_110], 9
0x140007ebe  call    HUBDESC_ParseConfigurationDescriptor
0x140007ec3  test    rax, rax
0x140007ec6  jnz     loc_140007FB6
0x140007ecc  lea     rbx, [rsi+9E8h]
0x140007ed3  mov     r9d, r12d
0x140007ed6  mov     rax, [rbx]
0x140007ed9  mov     r8d, r12d
0x140007edc  mov     [rsp+130h+var_F0], rax
0x140007ee1  mov     rdx, rdi
0x140007ee4  mov     [rsp+130h+var_F8], r14
0x140007ee9  mov     rcx, rdi
0x140007eec  mov     [rsp+130h+var_100], 1
0x140007ef4  mov     dword ptr [rsp+130h+var_108], r12d
0x140007ef9  mov     dword ptr [rsp+130h+var_110], 9
0x140007f01  call    HUBDESC_ParseConfigurationDescriptor
0x140007f06  test    rax, rax
0x140007f09  jnz     loc_140007FB6
0x140007f0f  mov     rax, [rbx]
0x140007f12  mov     r9d, r12d
0x140007f15  mov     [rsp+130h+var_F0], rax
0x140007f1a  mov     r8d, r12d
0x140007f1d  mov     [rsp+130h+var_F8], r14
0x140007f22  mov     rdx, rdi
0x140007f25  mov     [rsp+130h+var_100], r14d
0x140007f2a  mov     rcx, rdi
0x140007f2d  mov     dword ptr [rsp+130h+var_108], r12d
0x140007f32  mov     dword ptr [rsp+130h+var_110], 9
0x140007f3a  call    HUBDESC_ParseConfigurationDescriptor
0x140007f3f  test    rax, rax
0x140007f42  jnz     short loc_140007FB6
0x140007f44  mov     rax, [rbx]
0x140007f47  mov     r9d, r12d
0x140007f4a  mov     [rsp+130h+var_F0], rax
0x140007f4f  mov     r8d, r12d
0x140007f52  mov     [rsp+130h+var_F8], r14
0x140007f57  mov     rdx, rdi
0x140007f5a  mov     [rsp+130h+var_100], r12d
0x140007f5f  mov     rcx, rdi
0x140007f62  mov     dword ptr [rsp+130h+var_108], r12d
0x140007f67  mov     dword ptr [rsp+130h+var_110], 9
0x140007f6f  call    HUBDESC_ParseConfigurationDescriptor
0x140007f74  test    rax, rax
0x140007f77  jnz     short loc_140007FB6
0x140007f79  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007f80  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007f87  jz      loc_1400081D5
0x140007f8d  mov     rcx, [rsi+9E8h]
0x140007f94  lea     rax, WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids
0x140007f9b  mov     r9d, 0Ch
0x140007fa1  mov     [rsp+130h+var_110], rax
0x140007fa6  mov     dl, 2
0x140007fa8  lea     r8d, [r9-9]
0x140007fac  call    WPP_RECORDER_SF_
0x140007fb1  jmp     loc_1400081D5
0x140007fb6  cmp     byte ptr [rax+5], 9
0x140007fba  jnz     loc_1400081D5
0x140007fc0  cmp     [rax+4], r14b
0x140007fc4  jz      loc_1400081D5
0x140007fca  lea     rdx, [rbp+30h+InterfaceList]; InterfaceList
0x140007fce  mov     [rbp+30h+InterfaceList.InterfaceDescriptor], rax
0x140007fd2  mov     rcx, rdi; ConfigurationDescriptor
0x140007fd5  mov     [rbp+30h+var_90], r14
0x140007fd9  call    cs:__imp_USBD_CreateConfigurationRequestEx
0x140007fe0  nop     dword ptr [rax+rax+00h]
0x140007fe5  mov     r14, rax
0x140007fe8  test    rax, rax
0x140007feb  jnz     short loc_140008024
0x140007fed  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007ff4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007ffb  jz      loc_140008220
0x140008001  mov     rcx, [rbx]
0x140008004  lea     rax, WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids
0x14000800b  lea     r9d, [r14+0Dh]
0x14000800f  mov     [rsp+130h+var_110], rax
0x140008014  lea     r8d, [r14+3]
0x140008018  mov     dl, 2
0x14000801a  call    WPP_RECORDER_SF_
0x14000801f  jmp     loc_140008220
0x140008024  mov     rax, cs:WdfFunctions_01015
0x14000802b  mov     rdx, [rsi+10h]
0x14000802f  mov     rcx, cs:WdfDriverGlobals
0x140008036  mov     rax, [rax+150h]
0x14000803d  call    _guard_dispatch_icall
0x140008042  mov     rcx, [rsi+10h]
0x140008046  lea     r9, [rsp+130h+var_E0]
0x14000804b  mov     rdi, rax
0x14000804e  lea     rdx, [rsp+130h+var_D8]
0x140008053  xorps   xmm0, xmm0
0x140008056  xor     eax, eax
0x140008058  movups  [rsp+130h+var_C8], xmm0
0x14000805d  mov     [rbp+30h+var_A8], rax
0x140008061  mov     eax, 1
0x140008066  movups  [rsp+130h+var_B8], xmm0
0x14000806b  mov     qword ptr [rsp+130h+var_B8], rcx
0x140008070  mov     r8, rdi
0x140008073  mov     rcx, cs:WdfFunctions_01015
0x14000807a  movups  [rsp+130h+var_D8], xmm0
0x14000807f  mov     dword ptr [rsp+130h+var_D8], 38h ; '8'
0x140008087  mov     dword ptr [rsp+130h+var_C8+8], eax
0x14000808b  mov     dword ptr [rsp+130h+var_C8+0Ch], eax
0x14000808f  mov     rax, [rcx+7B8h]
0x140008096  mov     rcx, cs:WdfDriverGlobals
0x14000809d  call    _guard_dispatch_icall
0x1400080a2  mov     ecx, eax
0x1400080a4  test    eax, eax
0x1400080a6  jns     short loc_1400080E5
0x1400080a8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400080af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400080b6  jz      loc_1400081D5
0x1400080bc  mov     dword ptr [rsp+130h+var_108], ecx
0x1400080c0  lea     rax, WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids
0x1400080c7  mov     rcx, [rbx]
0x1400080ca  mov     r9d, 0Eh
0x1400080d0  mov     dl, 2
0x1400080d2  mov     [rsp+130h+var_110], rax
0x1400080d7  lea     r8d, [r9-0Bh]
0x1400080db  call    WPP_RECORDER_SF_d
0x1400080e0  jmp     loc_1400081D5
0x1400080e5  xor     edx, edx; Val
0x1400080e7  lea     rcx, [rbp+30h+var_80]; void *
0x1400080eb  lea     r8d, [rdx+48h]; Size
0x1400080ef  call    memset
0x1400080f4  mov     rax, cs:WdfFunctions_01015
0x1400080fb  lea     r8, [rbp+30h+var_80]
0x1400080ff  mov     rdx, [rsp+130h+var_E0]
0x140008104  mov     rcx, cs:WdfDriverGlobals
0x14000810b  mov     [rbp+30h+var_80], 0Fh
0x14000810f  mov     [rbp+30h+var_68], 220003h
0x140008116  mov     [rbp+30h+var_78], r14
0x14000811a  mov     rax, [rax+7E0h]
0x140008121  call    _guard_dispatch_icall
0x140008126  mov     rax, cs:WdfFunctions_01015
0x14000812d  lea     r8, HUBPARENT_SetHubConfigurationComplete
0x140008134  mov     rdx, [rsp+130h+var_E0]
0x140008139  mov     r9, r14
0x14000813c  mov     rcx, cs:WdfDriverGlobals
0x140008143  mov     rax, [rax+820h]
0x14000814a  call    _guard_dispatch_icall
0x14000814f  mov     rax, cs:WdfFunctions_01015
0x140008156  xor     r9d, r9d
0x140008159  mov     rdx, [rsp+130h+var_E0]
0x14000815e  mov     r8, rdi
0x140008161  mov     rcx, cs:WdfDriverGlobals
0x140008168  mov     rax, [rax+7E8h]
0x14000816f  call    _guard_dispatch_icall
0x140008174  test    al, al
0x140008176  jnz     loc_140008220
0x14000817c  mov     rax, cs:WdfFunctions_01015
0x140008183  mov     rdx, [rsp+130h+var_E0]
0x140008188  mov     rcx, cs:WdfDriverGlobals
0x14000818f  mov     rax, [rax+7F0h]
0x140008196  call    _guard_dispatch_icall
0x14000819b  mov     edi, eax
0x14000819d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400081a4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400081ab  jz      short loc_1400081D1
0x1400081ad  mov     rcx, [rbx]
0x1400081b0  lea     rax, WPP_7215ce29f44d3be25ae6d82bbfc5240b_Traceguids
0x1400081b7  mov     r9d, 0Fh
0x1400081bd  mov     dword ptr [rsp+130h+var_108], edi
0x1400081c1  mov     dl, 2
0x1400081c3  mov     [rsp+130h+var_110], rax
0x1400081c8  lea     r8d, [r9-0Ch]
0x1400081cc  call    WPP_RECORDER_SF_d
0x1400081d1  test    edi, edi
0x1400081d3  jns     short loc_140008220
0x1400081d5  mov     rdx, [rsp+130h+var_E0]
0x1400081da  test    rdx, rdx
0x1400081dd  jz      short loc_1400081F9
0x1400081df  mov     rax, cs:WdfFunctions_01015
0x1400081e6  mov     rcx, cs:WdfDriverGlobals
0x1400081ed  mov     rax, [rax+680h]
0x1400081f4  call    _guard_dispatch_icall
0x1400081f9  test    r14, r14
0x1400081fc  jz      short loc_14000820F
0x1400081fe  xor     edx, edx; Tag
0x140008200  mov     rcx, r14; P
0x140008203  call    cs:__imp_ExFreePoolWithTag
0x14000820a  nop     dword ptr [rax+rax+00h]
0x14000820f  lea     rcx, [rsi+500h]
0x140008216  mov     edx, 7D6h
0x14000821b  call    HUBSM_AddEvent
0x140008220  mov     rcx, [rbp+30h+var_38]
0x140008224  xor     rcx, rsp; StackCookie
0x140008227  call    __security_check_cookie
0x14000822c  add     rsp, 108h
0x140008233  pop     r14
0x140008235  pop     r12
0x140008237  pop     rdi
0x140008238  pop     rsi
0x140008239  pop     rbx
0x14000823a  pop     rbp
0x14000823b  retn
```
