# HUBFDO_IoctlGetDescriptorFromNodeConnection

- ea: `0x14007afe0`
- end: `0x14007b5a2`
- name: `HUBFDO_IoctlGetDescriptorFromNodeConnection`
- size: `1474`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14007a810`

## callees

- `0x140001f94`
- `0x1400024b8`
- `0x14000a520`
- `0x14000ca70`
- `0x14002f910`
- `0x140045530`
- `0x140045570`
- `0x140045640`
- `0x140045940`
- `0x14007afe0`
- `0x14007dd5c`

## pseudocode

```c
__int64 __fastcall HUBFDO_IoctlGetDescriptorFromNodeConnection(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v8; // r13d
  unsigned __int64 v9; // rbx
  __int64 v10; // rax
  _QWORD *v11; // rdi
  int v12; // edx
  int v13; // r12d
  __int64 v14; // rax
  int ActivityIdIrp; // eax
  __int64 v16; // rcx
  __int64 v17; // rsi
  __int64 v18; // r8
  unsigned __int16 *v19; // r9
  __int64 v20; // rsi
  unsigned __int16 *v21; // r14
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  unsigned __int16 *v25; // rdx
  unsigned __int64 v26; // rax
  char v27; // al
  unsigned __int16 v28; // dx
  size_t v29; // r8
  void *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rbx
  __int64 v33; // rax
  unsigned __int16 *v34; // rax
  __int64 v35; // rbx
  unsigned __int16 *v37; // [rsp+30h] [rbp-69h] BYREF
  __int64 v38; // [rsp+38h] [rbp-61h]
  __int64 v39; // [rsp+40h] [rbp-59h]
  __int64 v40; // [rsp+48h] [rbp-51h]
  _QWORD v41[9]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v42; // [rsp+98h] [rbp-1h] BYREF

  v38 = a2;
  v39 = a1;
  v37 = 0;
  memset(v41, 0, sizeof(v41));
  v42 = 0;
  v8 = 0;
  LODWORD(v9) = 0;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(WdfDriverGlobals, a1);
  v11 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                    WdfDriverGlobals,
                    v10,
                    off_14006B270);
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, unsigned __int16 **, _QWORD))(WdfFunctions_01015 + 2160))(
          WdfDriverGlobals,
          a2,
          a3,
          &v37,
          0);
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(v11[317], v12, 3, 70, (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids, v13);
    }
    return HUBFDO_CompleteGetDescriptorRequest((_DWORD)v11, v8, v38, v13, v9);
  }
  v13 = HUBFDO_IoctlValidateParameters((_DWORD)v11, 4, a4, (_DWORD)v37, 13, a3);
  if ( v13 >= 0 )
  {
    v8 = *v37;
    if ( a3 != 12 )
      memset(v37 + 6, 0, a3 - 12);
    if ( (byte_14006ED41 & 4) != 0 )
    {
      v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2280))(WdfDriverGlobals, v38);
      ActivityIdIrp = HUBMISC_GetActivityIdIrp(v14, &v42);
      if ( (byte_14006ED41 & 4) != 0 )
        McTemplateK0pq_EtwWriteTransfer(
          v16,
          USBHUB3_ETW_EVENT_HUB_IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION_START,
          (unsigned __int64)&v42 & -(__int64)(ActivityIdIrp >= 0),
          v11[31],
          v8);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1072))(WdfDriverGlobals, v11[2]);
    v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64))(WdfFunctions_01015 + 1080))(
            WdfDriverGlobals,
            v11[2],
            0,
            1);
    if ( !v17 )
      goto LABEL_47;
    do
    {
      if ( v17 != v11[334]
        && *(unsigned __int16 *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                                   WdfDriverGlobals,
                                   v17,
                                   off_14006B1D0)
                               + 48) == v8 )
      {
        break;
      }
      v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64))(WdfFunctions_01015 + 1080))(
              WdfDriverGlobals,
              v11[2],
              v17,
              1);
    }
    while ( v17 );
    if ( !v17
      || (v40 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                  WdfDriverGlobals,
                  v17,
                  off_14006B1D0),
          (v20 = *(_QWORD *)(v40 + 24)) == 0)
      || (*(_DWORD *)(v20 + 1644) & 2) == 0 )
    {
LABEL_47:
      v13 = -1073741810;
      goto LABEL_48;
    }
    v21 = v37;
    v18 = *((unsigned __int8 *)v37 + 7);
    v22 = *((unsigned __int8 *)v37 + 7);
    v37[2] = 1664;
    v23 = v22 - 1;
    if ( !v23 )
    {
      v25 = (unsigned __int16 *)(v20 + 1996);
      v9 = (unsigned int)a3 - 12LL;
      if ( v9 > 0x12 )
        LODWORD(v9) = 18;
      goto LABEL_46;
    }
    v24 = v23 - 1;
    if ( v24 )
    {
      if ( v24 == 13 )
      {
        v25 = *(unsigned __int16 **)(v20 + 2064);
        if ( v25 )
        {
          v9 = v25[1];
          v26 = (unsigned int)a3 - 12LL;
          if ( v9 < v26 )
          {
LABEL_46:
            v30 = v37 + 6;
            v29 = (unsigned int)v9;
            goto LABEL_41;
          }
LABEL_22:
          LODWORD(v9) = v26;
          goto LABEL_46;
        }
      }
    }
    else
    {
      v25 = *(unsigned __int16 **)(v20 + 2024);
      if ( v25 && !*((_BYTE *)v21 + 6) )
      {
        v26 = v25[1];
        v9 = (unsigned int)a3 - 12LL;
        if ( v26 >= v9 )
          goto LABEL_46;
        goto LABEL_22;
      }
    }
    if ( (_BYTE)v18 != 3 )
      goto LABEL_43;
    v27 = *((_BYTE *)v21 + 6);
    if ( !v27 || v27 != *(_BYTE *)(v20 + 2012) || v21[4] != 1033 )
      goto LABEL_43;
    if ( (*(_DWORD *)(v20 + 1640) & 0x40) == 0 )
    {
      v13 = -1073741823;
      goto LABEL_48;
    }
    v28 = (*(_DWORD *)(v20 + 1644) & 0x800) != 0 ? 0xC : 0;
    v9 = (unsigned __int16)(*(_WORD *)(v20 + 2156) - v28);
    if ( v9 >= (unsigned __int64)(unsigned int)a3 - 12 )
      LODWORD(v9) = a3 - 12;
    if ( (unsigned int)v9 > v21[5] )
    {
LABEL_43:
      v31 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
              WdfDriverGlobals,
              v39,
              off_14006B0A8);
      *(_QWORD *)(v31 + 152) = *(_QWORD *)(v21 + 2);
      v32 = v31 + 24;
      *(_QWORD *)(v31 + 32) = *(_QWORD *)(*(_QWORD *)(v40 + 24) + 24LL);
      v33 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v20);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015
                                                                                                + 1640))(
        WdfDriverGlobals,
        v33,
        "User Mode FDO Request",
        4744,
        "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubfdo.c");
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1088))(WdfDriverGlobals, v11[2]);
      *(_DWORD *)v32 = 3276936;
      *(_DWORD *)(v32 + 36) = a3 - 12;
      *(_DWORD *)(v32 + 32) = 11;
      v34 = v37 + 6;
      *(_QWORD *)(v32 + 48) = 0;
      *(_QWORD *)(v32 + 40) = v34;
      *(_DWORD *)(v32 + 56) = 5000;
      memset(v41, 0, sizeof(v41));
      v41[1] = v32;
      v35 = v38;
      LOBYTE(v41[0]) = 15;
      LODWORD(v41[3]) = 2228227;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 2016))(
        WdfDriverGlobals,
        v38,
        v41);
      *(_QWORD *)(v20 + 504) = v35;
      return HUBSM_AddDsmEvent(v20, 4051);
    }
    v19 = v37;
    if ( (_BYTE)v9 )
      *((_BYTE *)v37 + 12) = v9;
    if ( (unsigned __int8)v9 > 1u )
      *((_BYTE *)v19 + 13) = 3;
    if ( (unsigned __int8)v9 <= 2u )
      goto LABEL_48;
    v29 = (unsigned int)(unsigned __int8)v9 - 2;
    v25 = (unsigned __int16 *)(*(_QWORD *)(v20 + 2160) + 2 * ((unsigned __int64)v28 >> 1));
    v30 = v19 + 7;
LABEL_41:
    memmove(v30, v25, v29);
LABEL_48:
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, unsigned __int16 *))(WdfFunctions_01015 + 1088))(
      WdfDriverGlobals,
      v11[2],
      v18,
      v19);
  }
  return HUBFDO_CompleteGetDescriptorRequest((_DWORD)v11, v8, v38, v13, v9);
}

```

## disassembly

```asm
0x14007afe0  push    rbp
0x14007afe2  push    rbx
0x14007afe3  push    rsi
0x14007afe4  push    rdi
0x14007afe5  push    r12
0x14007afe7  push    r13
0x14007afe9  push    r14
0x14007afeb  push    r15
0x14007afed  lea     rbp, [rsp-1Fh]
0x14007aff2  sub     rsp, 0B8h
0x14007aff9  mov     rax, cs:__security_cookie
0x14007b000  xor     rax, rsp
0x14007b003  mov     [rbp+57h+var_48], rax
0x14007b007  mov     r12, rdx
0x14007b00a  mov     [rbp+57h+var_B8], rdx
0x14007b00e  xor     edx, edx; Val
0x14007b010  mov     [rbp+57h+var_B0], rcx
0x14007b014  mov     r15, r8
0x14007b017  mov     [rbp+57h+var_C0], 0
0x14007b01f  mov     rdi, rcx
0x14007b022  mov     rsi, r9
0x14007b025  lea     rcx, [rbp+57h+var_A0]; void *
0x14007b029  lea     r8d, [rdx+48h]; Size
0x14007b02d  call    memset
0x14007b032  mov     rax, cs:WdfFunctions_01015
0x14007b039  xorps   xmm0, xmm0
0x14007b03c  mov     rcx, cs:WdfDriverGlobals
0x14007b043  mov     rdx, rdi
0x14007b046  movups  [rbp+57h+var_58], xmm0
0x14007b04a  xor     r13d, r13d
0x14007b04d  xor     ebx, ebx
0x14007b04f  mov     rax, [rax+4E8h]
0x14007b056  call    _guard_dispatch_icall
0x14007b05b  mov     rcx, cs:WdfFunctions_01015
0x14007b062  mov     rdx, rax
0x14007b065  mov     r8, cs:off_14006B270
0x14007b06c  mov     rax, [rcx+650h]
0x14007b073  mov     rcx, cs:WdfDriverGlobals
0x14007b07a  call    _guard_dispatch_icall
0x14007b07f  mov     rcx, cs:WdfFunctions_01015
0x14007b086  lea     r9, [rbp+57h+var_C0]
0x14007b08a  mov     rdi, rax
0x14007b08d  mov     [rsp+0F0h+var_D0], rbx
0x14007b092  mov     r8, r15
0x14007b095  mov     rdx, r12
0x14007b098  mov     rax, [rcx+870h]
0x14007b09f  mov     rcx, cs:WdfDriverGlobals
0x14007b0a6  call    _guard_dispatch_icall
0x14007b0ab  mov     r12d, eax
0x14007b0ae  test    eax, eax
0x14007b0b0  jns     short loc_14007B0F2
0x14007b0b2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007b0b9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007b0c0  jz      loc_14007B56B
0x14007b0c6  mov     rcx, [rdi+9E8h]
0x14007b0cd  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14007b0d4  lea     r9d, [r13+46h]
0x14007b0d8  mov     dword ptr [rsp+0F0h+var_C8], r12d
0x14007b0dd  lea     r8d, [r13+3]
0x14007b0e1  mov     [rsp+0F0h+var_D0], rax
0x14007b0e6  mov     dl, 2
0x14007b0e8  call    WPP_RECORDER_SF_d
0x14007b0ed  jmp     loc_14007B56B
0x14007b0f2  mov     r9, [rbp+57h+var_C0]
0x14007b0f6  mov     r8, rsi
0x14007b0f9  mov     [rsp+0F0h+var_C8], r15
0x14007b0fe  mov     edx, 4
0x14007b103  mov     rcx, rdi
0x14007b106  mov     [rsp+0F0h+var_D0], 0Dh
0x14007b10f  call    HUBFDO_IoctlValidateParameters
0x14007b114  mov     r12d, eax
0x14007b117  test    eax, eax
0x14007b119  js      loc_14007B56B
0x14007b11f  mov     rcx, [rbp+57h+var_C0]
0x14007b123  lea     r8, [r15-0Ch]; Size
0x14007b127  movzx   r13d, word ptr [rcx]
0x14007b12b  test    r8, r8
0x14007b12e  jz      short loc_14007B13B
0x14007b130  add     rcx, 0Ch; void *
0x14007b134  xor     edx, edx; Val
0x14007b136  call    memset
0x14007b13b  test    cs:byte_14006ED41, 4
0x14007b142  mov     r14d, 1
0x14007b148  jz      short loc_14007B1A7
0x14007b14a  mov     rax, cs:WdfFunctions_01015
0x14007b151  mov     rdx, [rbp+57h+var_B8]
0x14007b155  mov     rcx, cs:WdfDriverGlobals
0x14007b15c  mov     rax, [rax+8E8h]
0x14007b163  call    _guard_dispatch_icall
0x14007b168  lea     rdx, [rbp+57h+var_58]
0x14007b16c  mov     rcx, rax
0x14007b16f  call    HUBMISC_GetActivityIdIrp
0x14007b174  test    cs:byte_14006ED41, 4
0x14007b17b  jz      short loc_14007B1A7
0x14007b17d  mov     r9, [rdi+0F8h]
0x14007b184  lea     rdx, USBHUB3_ETW_EVENT_HUB_IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION_START
0x14007b18b  shr     eax, 1Fh
0x14007b18e  xor     al, r14b
0x14007b191  mov     dword ptr [rsp+0F0h+var_D0], r13d
0x14007b196  neg     al
0x14007b198  lea     rax, [rbp+57h+var_58]
0x14007b19c  sbb     r8, r8
0x14007b19f  and     r8, rax
0x14007b1a2  call    McTemplateK0pq_EtwWriteTransfer
0x14007b1a7  mov     rax, cs:WdfFunctions_01015
0x14007b1ae  mov     rdx, [rdi+10h]
0x14007b1b2  mov     rcx, cs:WdfDriverGlobals
0x14007b1b9  mov     rax, [rax+430h]
0x14007b1c0  call    _guard_dispatch_icall
0x14007b1c5  mov     rax, cs:WdfFunctions_01015
0x14007b1cc  mov     r9d, r14d
0x14007b1cf  mov     rdx, [rdi+10h]
0x14007b1d3  xor     r8d, r8d
0x14007b1d6  mov     rcx, cs:WdfDriverGlobals
0x14007b1dd  mov     rax, [rax+438h]
0x14007b1e4  call    _guard_dispatch_icall
0x14007b1e9  mov     rsi, rax
0x14007b1ec  test    rax, rax
0x14007b1ef  jz      loc_14007B547
0x14007b1f5  cmp     rsi, [rdi+0A70h]
0x14007b1fc  jz      short loc_14007B22B
0x14007b1fe  mov     rcx, cs:WdfFunctions_01015
0x14007b205  mov     rdx, rsi
0x14007b208  mov     r8, cs:off_14006B1D0
0x14007b20f  mov     rax, [rcx+650h]
0x14007b216  mov     rcx, cs:WdfDriverGlobals
0x14007b21d  call    _guard_dispatch_icall
0x14007b222  movzx   ecx, word ptr [rax+30h]
0x14007b226  cmp     ecx, r13d
0x14007b229  jz      short loc_14007B257
0x14007b22b  mov     rax, cs:WdfFunctions_01015
0x14007b232  mov     r9d, r14d
0x14007b235  mov     rdx, [rdi+10h]
0x14007b239  mov     r8, rsi
0x14007b23c  mov     rcx, cs:WdfDriverGlobals
0x14007b243  mov     rax, [rax+438h]
0x14007b24a  call    _guard_dispatch_icall
0x14007b24f  mov     rsi, rax
0x14007b252  test    rax, rax
0x14007b255  jnz     short loc_14007B1F5
0x14007b257  test    rsi, rsi
0x14007b25a  jz      loc_14007B547
0x14007b260  mov     rax, cs:WdfFunctions_01015
0x14007b267  mov     rdx, rsi
0x14007b26a  mov     r8, cs:off_14006B1D0
0x14007b271  mov     rcx, cs:WdfDriverGlobals
0x14007b278  mov     rax, [rax+650h]
0x14007b27f  call    _guard_dispatch_icall
0x14007b284  mov     [rbp+57h+var_A8], rax
0x14007b288  mov     rsi, [rax+18h]
0x14007b28c  test    rsi, rsi
0x14007b28f  jz      loc_14007B547
0x14007b295  mov     ecx, [rsi+66Ch]
0x14007b29b  test    cl, 2
0x14007b29e  jz      loc_14007B547
0x14007b2a4  mov     r14, [rbp+57h+var_C0]
0x14007b2a8  movzx   r8d, byte ptr [r14+7]
0x14007b2ad  mov     ecx, r8d
0x14007b2b0  mov     word ptr [r14+4], 680h
0x14007b2b7  sub     ecx, 1
0x14007b2ba  jz      loc_14007B51E
0x14007b2c0  sub     ecx, 1
0x14007b2c3  jz      short loc_14007B2F1
0x14007b2c5  cmp     ecx, 0Dh
0x14007b2c8  jnz     short loc_14007B319
0x14007b2ca  mov     rdx, [rsi+810h]
0x14007b2d1  test    rdx, rdx
0x14007b2d4  jz      short loc_14007B319
0x14007b2d6  movzx   ebx, word ptr [rdx+2]
0x14007b2da  mov     eax, r15d
0x14007b2dd  add     rax, 0FFFFFFFFFFFFFFF4h
0x14007b2e1  cmp     rbx, rax
0x14007b2e4  jb      loc_14007B537
0x14007b2ea  mov     ebx, eax
0x14007b2ec  jmp     loc_14007B537
0x14007b2f1  mov     rdx, [rsi+7E8h]
0x14007b2f8  test    rdx, rdx
0x14007b2fb  jz      short loc_14007B319
0x14007b2fd  cmp     [r14+6], bl
0x14007b301  jnz     short loc_14007B319
0x14007b303  movzx   eax, word ptr [rdx+2]
0x14007b307  mov     ebx, r15d
0x14007b30a  add     rbx, 0FFFFFFFFFFFFFFF4h
0x14007b30e  cmp     rax, rbx
0x14007b311  jnb     loc_14007B537
0x14007b317  jmp     short loc_14007B2EA
0x14007b319  cmp     r8b, 3
0x14007b31d  jnz     loc_14007B3DE
0x14007b323  mov     al, [r14+6]
0x14007b327  test    al, al
0x14007b329  jz      loc_14007B3DE
0x14007b32f  cmp     al, [rsi+7DCh]
0x14007b335  jnz     loc_14007B3DE
0x14007b33b  mov     eax, 409h
0x14007b340  cmp     [r14+8], ax
0x14007b345  jnz     loc_14007B3DE
0x14007b34b  mov     eax, [rsi+668h]
0x14007b351  test    al, 40h
0x14007b353  jz      short loc_14007B3D3
0x14007b355  mov     eax, [rsi+66Ch]
0x14007b35b  and     eax, 800h
0x14007b360  mov     ecx, r15d
0x14007b363  neg     eax
0x14007b365  movzx   eax, word ptr [rsi+86Ch]
0x14007b36c  sbb     dx, dx
0x14007b36f  add     rcx, 0FFFFFFFFFFFFFFF4h
0x14007b373  and     dx, 0Ch
0x14007b377  sub     ax, dx
0x14007b37a  movzx   ebx, ax
0x14007b37d  movzx   eax, word ptr [r14+0Ah]
0x14007b382  cmp     rbx, rcx
0x14007b385  cmovnb  ebx, ecx
0x14007b388  cmp     ebx, eax
0x14007b38a  ja      short loc_14007B3DE
0x14007b38c  mov     r9, [rbp+57h+var_C0]
0x14007b390  movzx   eax, bl
0x14007b393  test    bl, bl
0x14007b395  jz      short loc_14007B39B
0x14007b397  mov     [r9+0Ch], bl
0x14007b39b  cmp     eax, 1
0x14007b39e  jbe     short loc_14007B3A5
0x14007b3a0  mov     byte ptr [r9+0Dh], 3
0x14007b3a5  cmp     eax, 2
0x14007b3a8  jbe     loc_14007B54D
0x14007b3ae  add     eax, 0FFFFFFFEh
0x14007b3b1  movzx   ecx, dx
0x14007b3b4  shr     rcx, 1
0x14007b3b7  mov     r8d, eax; Size
0x14007b3ba  mov     rax, [rsi+870h]
0x14007b3c1  lea     rdx, [rax+rcx*2]; Src
0x14007b3c5  lea     rcx, [r9+0Eh]; void *
0x14007b3c9  call    memmove
0x14007b3ce  jmp     loc_14007B54D
0x14007b3d3  mov     r12d, 0C0000001h
0x14007b3d9  jmp     loc_14007B54D
0x14007b3de  mov     rax, cs:WdfFunctions_01015
0x14007b3e5  mov     r8, cs:off_14006B0A8
0x14007b3ec  mov     rdx, [rbp+57h+var_B0]
0x14007b3f0  mov     rcx, cs:WdfDriverGlobals
0x14007b3f7  mov     rax, [rax+650h]
0x14007b3fe  call    _guard_dispatch_icall
0x14007b403  mov     rcx, [r14+4]
0x14007b407  mov     rdx, rsi
0x14007b40a  mov     [rax+98h], rcx
0x14007b411  lea     rbx, [rax+18h]
0x14007b415  mov     rax, [rbp+57h+var_A8]
0x14007b419  mov     rax, [rax+18h]
0x14007b41d  mov     rcx, [rax+18h]
0x14007b421  mov     [rbx+8], rcx
0x14007b425  mov     rax, cs:WdfFunctions_01015
0x14007b42c  mov     rcx, cs:WdfDriverGlobals
0x14007b433  mov     rax, [rax+660h]
0x14007b43a  call    _guard_dispatch_icall
0x14007b43f  mov     rcx, cs:WdfFunctions_01015
0x14007b446  lea     r8, UserModeFdoRequest; "User Mode FDO Request"
0x14007b44d  mov     rdx, rax
0x14007b450  mov     r9d, 1288h
0x14007b456  mov     r10, [rcx+668h]
0x14007b45d  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14007b464  mov     [rsp+0F0h+var_D0], rcx
0x14007b469  mov     rax, r10
0x14007b46c  mov     rcx, cs:WdfDriverGlobals
0x14007b473  call    _guard_dispatch_icall
0x14007b478  mov     rax, cs:WdfFunctions_01015
0x14007b47f  mov     rdx, [rdi+10h]
0x14007b483  mov     rcx, cs:WdfDriverGlobals
0x14007b48a  mov     rax, [rax+440h]
0x14007b491  call    _guard_dispatch_icall
0x14007b496  lea     eax, [r15-0Ch]
0x14007b49a  mov     dword ptr [rbx], 320088h
0x14007b4a0  mov     [rbx+24h], eax
0x14007b4a3  lea     rcx, [rbp+57h+var_A0]; void *
0x14007b4a7  xor     edx, edx; Val
0x14007b4a9  mov     dword ptr [rbx+20h], 0Bh
0x14007b4b0  mov     rax, [rbp+57h+var_C0]
0x14007b4b4  add     rax, 0Ch
0x14007b4b8  mov     qword ptr [rbx+30h], 0
0x14007b4c0  mov     [rbx+28h], rax
0x14007b4c4  lea     r8d, [rdx+48h]; Size
0x14007b4c8  mov     dword ptr [rbx+38h], 1388h
0x14007b4cf  call    memset
0x14007b4d4  mov     rax, cs:WdfFunctions_01015
0x14007b4db  lea     r8, [rbp+57h+var_A0]
0x14007b4df  mov     rcx, cs:WdfDriverGlobals
0x14007b4e6  mov     [rbp+57h+var_98], rbx
0x14007b4ea  mov     rbx, [rbp+57h+var_B8]
0x14007b4ee  mov     [rbp+57h+var_A0], 0Fh
0x14007b4f2  mov     rdx, rbx
0x14007b4f5  mov     [rbp+57h+var_88], 220003h
0x14007b4fc  mov     rax, [rax+7E0h]
0x14007b503  call    _guard_dispatch_icall
0x14007b508  mov     edx, 0FD3h
0x14007b50d  mov     [rsi+1F8h], rbx
0x14007b514  mov     rcx, rsi
0x14007b517  call    HUBSM_AddDsmEvent
0x14007b51c  jmp     short loc_14007B581
0x14007b51e  mov     ebx, r15d
0x14007b521  lea     rdx, [rsi+7CCh]
0x14007b528  add     rbx, 0FFFFFFFFFFFFFFF4h
0x14007b52c  cmp     rbx, 12h
  ... truncated ...
```
