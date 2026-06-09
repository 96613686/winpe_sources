# WinUSB_ResetDefaults

- ea: `0x140004130`
- end: `0x1400043c3`
- name: `WinUSB_ResetDefaults`
- size: `659`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400026d0`
- `0x1400190b0`
- `0x14001b370`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x140004130`
- `0x140007694`
- `0x140010700`

## pseudocode

```c
__int64 __fastcall WinUSB_ResetDefaults(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rbp
  unsigned __int8 v4; // si
  int v5; // eax
  char v6; // cl
  int v7; // esi
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  char v10; // al
  int v11; // eax
  int v12; // eax
  unsigned __int16 v14; // r9
  unsigned int v15; // eax
  __int64 v16; // [rsp+28h] [rbp-50h]
  int v17; // [rsp+30h] [rbp-48h]

  v2 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0xC2u,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids);
  v4 = 0;
  if ( !*(_BYTE *)(a1 + 128) )
  {
LABEL_7:
    if ( !*(_BYTE *)(a1 + 160) )
    {
LABEL_18:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LODWORD(v16) = v2;
        WPP_RECORDER_SF_d(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          5u,
          1u,
          0xC6u,
          (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
          v16);
      }
      return v2;
    }
    v6 = *(_BYTE *)(a1 + 164);
    v7 = *(_DWORD *)(a1 + 168);
    v8 = *(_OWORD *)(a1 + 240);
    *(_OWORD *)(a1 + 164) = *(_OWORD *)(a1 + 224);
    v9 = *(_OWORD *)(a1 + 256);
    *(_OWORD *)(a1 + 180) = v8;
    *(_QWORD *)&v8 = *(_QWORD *)(a1 + 272);
    *(_OWORD *)(a1 + 196) = v9;
    *(_QWORD *)(a1 + 212) = v8;
    if ( *(_BYTE *)(a1 + 220) )
    {
      v10 = *(_BYTE *)(a1 + 164);
      if ( v6 != v10 )
      {
        if ( v10 )
        {
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 3512))(
            WdfDriverGlobals,
            v3,
            0,
            4202,
            "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\ioctl.c");
        }
        else
        {
          v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD, int, const char *))(WdfFunctions_01015 + 3504))(
                  WdfDriverGlobals,
                  v3,
                  0,
                  0,
                  4207,
                  "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\ioctl.c");
          v2 = 0;
          if ( v15 != 259 )
            v2 = v15;
          if ( (v2 & 0x80000000) != 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return v2;
            v14 = 196;
            LODWORD(v16) = v2;
            goto LABEL_24;
          }
        }
      }
    }
    if ( *(_BYTE *)(a1 + 232) )
    {
      v11 = *(_DWORD *)(a1 + 168);
      if ( v7 != v11 )
      {
        *(_DWORD *)(a1 + 192) = v11;
        v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 368))(WdfDriverGlobals, v3);
        v2 = v12;
        if ( v12 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v17 = v12;
            LODWORD(v16) = v7;
            WPP_RECORDER_SF_dD(
              (__int64)WPP_GLOBAL_Control->DeviceExtension,
              2u,
              3u,
              0xC5u,
              (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
              v16,
              v17);
          }
          *(_DWORD *)(a1 + 168) = v7;
        }
      }
    }
    goto LABEL_18;
  }
  while ( 1 )
  {
    v5 = WinUSB_SetInterface(a1, v4, *(_BYTE *)(a1 + 296));
    v2 = v5;
    if ( v5 < 0 )
      break;
    if ( ++v4 >= *(_BYTE *)(a1 + 128) )
      goto LABEL_7;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = 195;
    LODWORD(v16) = v5;
LABEL_24:
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      2u,
      3u,
      v14,
      (__int64)WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids,
      v16);
    goto LABEL_18;
  }
  return v2;
}

```

## disassembly

```asm
0x140004130  push    rbx
0x140004132  push    rbp
0x140004133  push    rsi
0x140004134  push    rdi
0x140004135  push    r12
0x140004137  push    r14
0x140004139  push    r15
0x14000413b  sub     rsp, 40h
0x14000413f  mov     rax, cs:WdfFunctions_01015
0x140004146  mov     rbx, rcx
0x140004149  xor     r14d, r14d
0x14000414c  mov     rdx, rcx
0x14000414f  mov     rcx, cs:WdfDriverGlobals
0x140004156  mov     edi, r14d
0x140004159  mov     rax, [rax+660h]
0x140004160  call    _guard_dispatch_icall
0x140004165  mov     rbp, rax
0x140004168  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000416f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140004176  lea     r12, WPP_1ea4bda7f8b23cafb6f0c7d9f6a1b177_Traceguids
0x14000417d  jz      short loc_1400041A7
0x14000417f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004186  cmp     [rcx+48h], r14w
0x14000418b  jz      short loc_1400041A7
0x14000418d  mov     rcx, [rcx+40h]
0x140004191  lea     r8d, [r14+1]
0x140004195  mov     r9d, 0C2h
0x14000419b  mov     [rsp+78h+var_58], r12
0x1400041a0  mov     dl, 5
0x1400041a2  call    WPP_RECORDER_SF_
0x1400041a7  mov     sil, r14b
0x1400041aa  cmp     [rbx+80h], r14b
0x1400041b1  jbe     short loc_1400041DB
0x1400041b3  mov     r8b, [rbx+128h]
0x1400041ba  mov     dl, sil
0x1400041bd  mov     rcx, rbx
0x1400041c0  call    WinUSB_SetInterface
0x1400041c5  mov     edi, eax
0x1400041c7  test    eax, eax
0x1400041c9  js      loc_14000433F
0x1400041cf  inc     sil
0x1400041d2  cmp     sil, [rbx+80h]
0x1400041d9  jb      short loc_1400041B3
0x1400041db  cmp     [rbx+0A0h], r14b
0x1400041e2  jz      loc_1400042F6
0x1400041e8  mov     cl, [rbx+0A4h]
0x1400041ee  mov     esi, [rbx+0A8h]
0x1400041f4  movups  xmm0, xmmword ptr [rbx+0E0h]
0x1400041fb  movups  xmm1, xmmword ptr [rbx+0F0h]
0x140004202  movups  xmmword ptr [rbx+0A4h], xmm0
0x140004209  movups  xmm0, xmmword ptr [rbx+100h]
0x140004210  movups  xmmword ptr [rbx+0B4h], xmm1
0x140004217  movsd   xmm1, qword ptr [rbx+110h]
0x14000421f  movups  xmmword ptr [rbx+0C4h], xmm0
0x140004226  movsd   qword ptr [rbx+0D4h], xmm1
0x14000422e  cmp     [rbx+0DCh], r14b
0x140004235  jz      short loc_14000427B
0x140004237  mov     al, [rbx+0A4h]
0x14000423d  cmp     cl, al
0x14000423f  jz      short loc_14000427B
0x140004241  test    al, al
0x140004243  lea     rcx, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\usb\\driver\\win"...
0x14000424a  mov     rax, cs:WdfFunctions_01015
0x140004251  mov     rdx, rbp
0x140004254  jz      loc_140004371
0x14000425a  mov     rax, [rax+0DB8h]
0x140004261  mov     r9d, 106Ah
0x140004267  mov     [rsp+78h+var_58], rcx
0x14000426c  xor     r8d, r8d
0x14000426f  mov     rcx, cs:WdfDriverGlobals
0x140004276  call    _guard_dispatch_icall
0x14000427b  cmp     [rbx+0E8h], r14b
0x140004282  jz      short loc_1400042F6
0x140004284  mov     eax, [rbx+0A8h]
0x14000428a  cmp     esi, eax
0x14000428c  jz      short loc_1400042F6
0x14000428e  lea     r8, [rbx+0B4h]
0x140004295  mov     rdx, rbp
0x140004298  mov     [r8+0Ch], eax
0x14000429c  mov     rax, cs:WdfFunctions_01015
0x1400042a3  mov     rcx, cs:WdfDriverGlobals
0x1400042aa  mov     rax, [rax+170h]
0x1400042b1  call    _guard_dispatch_icall
0x1400042b6  mov     edi, eax
0x1400042b8  test    eax, eax
0x1400042ba  jns     short loc_1400042F6
0x1400042bc  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400042c3  jz      short loc_1400042F0
0x1400042c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042cc  mov     r9d, 0C5h
0x1400042d2  mov     [rsp+78h+var_48], eax
0x1400042d6  mov     r8d, 3
0x1400042dc  mov     dword ptr [rsp+78h+var_50], esi
0x1400042e0  mov     dl, 2
0x1400042e2  mov     [rsp+78h+var_58], r12
0x1400042e7  mov     rcx, [rcx+40h]
0x1400042eb  call    WPP_RECORDER_SF_dD
0x1400042f0  mov     [rbx+0A8h], esi
0x1400042f6  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400042fd  jz      short loc_14000432D
0x1400042ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140004306  cmp     [rcx+48h], r14w
0x14000430b  jz      short loc_14000432D
0x14000430d  mov     rcx, [rcx+40h]
0x140004311  mov     r9d, 0C6h
0x140004317  mov     dword ptr [rsp+78h+var_50], edi
0x14000431b  mov     r8d, 1
0x140004321  mov     dl, 5
0x140004323  mov     [rsp+78h+var_58], r12
0x140004328  call    WPP_RECORDER_SF_d
0x14000432d  mov     eax, edi
0x14000432f  add     rsp, 40h
0x140004333  pop     r15
0x140004335  pop     r14
0x140004337  pop     r12
0x140004339  pop     rdi
0x14000433a  pop     rsi
0x14000433b  pop     rbp
0x14000433c  pop     rbx
0x14000433d  retn
0x14000433f  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140004346  jz      short loc_14000432D
0x140004348  mov     r9d, 0C3h
0x14000434e  mov     dword ptr [rsp+78h+var_50], eax
0x140004352  mov     rcx, cs:WPP_GLOBAL_Control
0x140004359  mov     r8d, 3
0x14000435f  mov     dl, 2
0x140004361  mov     [rsp+78h+var_58], r12
0x140004366  mov     rcx, [rcx+40h]
0x14000436a  call    WPP_RECORDER_SF_d
0x14000436f  jmp     short loc_1400042F6
0x140004371  mov     rax, [rax+0DB0h]
0x140004378  xor     r9d, r9d
0x14000437b  mov     [rsp+78h+var_50], rcx
0x140004380  xor     r8d, r8d
0x140004383  mov     rcx, cs:WdfDriverGlobals
0x14000438a  mov     dword ptr [rsp+78h+var_58], 106Fh
0x140004392  call    _guard_dispatch_icall
0x140004397  cmp     eax, 103h
0x14000439c  mov     edi, r14d
0x14000439f  cmovnz  edi, eax
0x1400043a2  test    edi, edi
0x1400043a4  jns     loc_14000427B
0x1400043aa  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400043b1  jz      loc_14000432D
0x1400043b7  mov     r9d, 0C4h
0x1400043bd  mov     dword ptr [rsp+78h+var_50], edi
0x1400043c1  jmp     short loc_140004352
```
