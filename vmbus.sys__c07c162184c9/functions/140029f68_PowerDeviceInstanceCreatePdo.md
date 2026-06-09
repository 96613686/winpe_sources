# PowerDeviceInstanceCreatePdo

- ea: `0x140029f68`
- end: `0x14002a571`
- name: `PowerDeviceInstanceCreatePdo`
- size: `1545`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002b2b0`

## callees

- `0x1400038cc`
- `0x140017000`
- `0x140017190`
- `0x140017540`
- `0x140029f68`

## pseudocode

```c
__int64 __fastcall PowerDeviceInstanceCreatePdo(__int64 a1, __int64 a2)
{
  int v4; // ebx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v11[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v12[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v13; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v14; // [rsp+70h] [rbp-90h]
  __int128 v15; // [rsp+80h] [rbp-80h]
  __int64 *v16; // [rsp+90h] [rbp-70h]
  _QWORD v17[18]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v18[2]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v19; // [rsp+150h] [rbp+50h]
  _OWORD v20[2]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v21; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v22[22]; // [rsp+190h] [rbp+90h]

  v9 = a1;
  memset(v17, 0, 0x8Cu);
  LODWORD(v16) = 0;
  memset(v18, 0, sizeof(v18));
  v10 = 0;
  v11[0] = 2490404;
  v12[0] = 1703960;
  v19 = 0;
  v11[1] = &v21;
  v13 = 0;
  v12[1] = v20;
  v14 = 0;
  v15 = 0;
  *(_OWORD *)v22 = *(_OWORD *)L"werDevice";
  v21 = *(_OWORD *)L"VMBUS\\PowerDevice";
  *(_QWORD *)&v22[14] = *(_QWORD *)L"ce";
  v20[0] = *(_OWORD *)L"PowerDevice0";
  *(_OWORD *)((char *)v20 + 10) = *(_OWORD *)L"Device0";
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 528))(WdfDriverGlobals, a1, 42);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 488))(WdfDriverGlobals, v9, 3);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const UNICODE_STRING *))(WdfFunctions_01033 + 544))(
         WdfDriverGlobals,
         v9,
         &SDDL_DEVOBJ_KERNEL_ONLY);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, GUID *))(WdfFunctions_01033 + 1744))(
           WdfDriverGlobals,
           v9,
           &GUID_BUS_VMBUS);
    if ( v4 >= 0 )
    {
      LOBYTE(v7) = 1;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 496))(
        WdfDriverGlobals,
        v9,
        v7);
      v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 1696))(
             WdfDriverGlobals,
             v9,
             v11);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 1712))(
               WdfDriverGlobals,
               v9,
               v11);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 1720))(
                 WdfDriverGlobals,
                 v9,
                 v11);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 1704))(
                   WdfDriverGlobals,
                   v9,
                   v12);
            if ( v4 >= 0 )
            {
              memset(v17, 0, sizeof(v17));
              if ( WdfClientVersionHigherThanFramework )
              {
                if ( (unsigned int)WdfStructureCount <= 0x29 )
                  LODWORD(v17[0]) = -1;
                else
                  LODWORD(v17[0]) = *(_DWORD *)(WdfStructures + 328);
              }
              else
              {
                LODWORD(v17[0]) = 144;
              }
              v17[9] = PowerDeviceSelfManagedIoInit;
              v17[11] = PowerDeviceSelfManagedIoRestart;
              v17[10] = PowerDeviceSelfManagedIoSuspend;
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 440))(
                WdfDriverGlobals,
                v9,
                v17);
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 512))(WdfDriverGlobals, v9);
              v13 = 0;
              v16 = 0;
              v14 = 0;
              v15 = 0;
              if ( WdfClientVersionHigherThanFramework )
              {
                if ( (unsigned int)WdfStructureCount <= 0x26 )
                  LODWORD(v13) = -1;
                else
                  LODWORD(v13) = *(_DWORD *)(WdfStructures + 304);
              }
              else
              {
                LODWORD(v13) = 56;
              }
              v16 = off_14001C0A0;
              *((_QWORD *)&v14 + 1) = 0x100000001LL;
              *((_QWORD *)&v13 + 1) = PowerDeviceCleanup;
              v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, __int128 *, __int64 *))(WdfFunctions_01033 + 600))(
                     WdfDriverGlobals,
                     &v9,
                     &v13,
                     &v10);
              if ( v4 >= 0 )
              {
                *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                             WdfDriverGlobals,
                             v10,
                             off_14001C0A0) = a2;
                memset(v18, 0, sizeof(v18));
                v19 = 0;
                if ( WdfClientVersionHigherThanFramework )
                {
                  if ( (unsigned int)WdfStructureCount <= 0xC )
                    LODWORD(v18[0]) = -1;
                  else
                    LODWORD(v18[0]) = *(_DWORD *)(WdfStructures + 96);
                }
                else
                {
                  LODWORD(v18[0]) = 48;
                }
                *(__m128i *)((char *)v18 + 4) = _mm_load_si128((const __m128i *)&_xmm);
                HIDWORD(v18[1]) = 2;
                *(_QWORD *)&v19 = 0x100000002LL;
                *((_QWORD *)&v19 + 1) = -1;
                *(_QWORD *)((char *)&v18[1] + 4) = 0x200000001LL;
                (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 664))(
                  WdfDriverGlobals,
                  v10,
                  v18);
              }
              else
              {
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v6 = 19;
                  goto LABEL_6;
                }
              }
            }
            else
            {
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v6 = 18;
                goto LABEL_6;
              }
            }
          }
          else
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v6 = 17;
              goto LABEL_6;
            }
          }
        }
        else
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v6 = 16;
            goto LABEL_6;
          }
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v6 = 15;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v6 = 14;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v6 = 13;
LABEL_6:
      WPP_SF_d(v5->AttachedDevice, v6, WPP_2ff8b0bb8e893dc1ecd1a3d57a9e5fd9_Traceguids, (unsigned int)v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140029f68  mov     [rsp-8+arg_8], rbx
0x140029f6d  mov     [rsp-8+arg_10], rsi
0x140029f72  push    rbp
0x140029f73  push    r12
0x140029f75  push    r15
0x140029f77  lea     rbp, [rsp-0B0h]
0x140029f7f  sub     rsp, 1B0h
0x140029f86  mov     rax, cs:__security_cookie
0x140029f8d  xor     rax, rsp
0x140029f90  mov     [rbp+0C0h+var_18], rax
0x140029f97  mov     rsi, rdx
0x140029f9a  mov     [rsp+1C0h+var_190], rcx
0x140029f9f  mov     rbx, rcx
0x140029fa2  xor     eax, eax
0x140029fa4  xor     edx, edx; Val
0x140029fa6  mov     [rbp+0C0h+var_11C], eax
0x140029fa9  lea     rcx, [rbp+0C0h+var_120]; void *
0x140029fad  mov     r8d, 8Ch; Size
0x140029fb3  call    memset
0x140029fb8  movups  xmm1, xmmword ptr cs:aVmbusPowerdevi+10h; "werDevice"
0x140029fbf  mov     rcx, cs:WdfDriverGlobals
0x140029fc6  xor     eax, eax
0x140029fc8  xorps   xmm0, xmm0
0x140029fcb  mov     dword ptr [rbp+0C0h+var_130], eax
0x140029fce  movups  [rbp+0C0h+var_90], xmm0
0x140029fd2  mov     [rsp+1C0h+var_188], rax
0x140029fd7  mov     rdx, rbx
0x140029fda  lea     r12d, [rax+26h]
0x140029fde  mov     [rsp+1C0h+var_180], 260024h
0x140029fe7  movups  [rbp+0C0h+var_80], xmm0
0x140029feb  lea     rax, [rbp+0C0h+var_40]
0x140029ff2  mov     [rsp+1C0h+var_170], 1A0018h
0x140029ffb  movups  [rbp+0C0h+var_70], xmm0
0x140029fff  mov     [rsp+1C0h+var_178], rax
0x14002a004  lea     rax, [rbp+0C0h+var_60]
0x14002a008  movups  [rsp+1C0h+var_160], xmm0
0x14002a00d  mov     [rsp+1C0h+var_168], rax
0x14002a012  lea     r8d, [r12+4]
0x14002a017  mov     rax, cs:WdfFunctions_01033
0x14002a01e  movups  [rsp+1C0h+var_150], xmm0
0x14002a023  movups  [rbp+0C0h+var_140], xmm0
0x14002a027  movups  xmm0, xmmword ptr cs:aVmbusPowerdevi; "VMBUS\\PowerDevice"
0x14002a02e  movups  xmmword ptr [rbp+0C0h+var_30], xmm1
0x14002a035  movups  xmm1, xmmword ptr cs:aPowerdevice0+0Ah; "Device0"
0x14002a03c  movups  [rbp+0C0h+var_40], xmm0
0x14002a043  movsd   xmm0, qword ptr cs:aVmbusPowerdevi+1Eh; "ce"
0x14002a04b  movsd   qword ptr [rbp+0C0h+var_30+0Eh], xmm0
0x14002a053  movups  xmm0, xmmword ptr cs:aPowerdevice0; "PowerDevice0"
0x14002a05a  movups  xmmword ptr [rbp+0C0h+var_60], xmm0
0x14002a05e  movups  xmmword ptr [rbp+0C0h+var_60+0Ah], xmm1
0x14002a062  mov     rax, [rax+210h]
0x14002a069  call    _guard_dispatch_icall
0x14002a06e  mov     rax, cs:WdfFunctions_01033
0x14002a075  lea     r8d, [r12-23h]
0x14002a07a  mov     rdx, [rsp+1C0h+var_190]
0x14002a07f  mov     rcx, cs:WdfDriverGlobals
0x14002a086  mov     rax, [rax+1E8h]
0x14002a08d  call    _guard_dispatch_icall
0x14002a092  mov     rax, cs:WdfFunctions_01033
0x14002a099  lea     r8, SDDL_DEVOBJ_KERNEL_ONLY
0x14002a0a0  mov     rdx, [rsp+1C0h+var_190]
0x14002a0a5  mov     rcx, cs:WdfDriverGlobals
0x14002a0ac  mov     rax, [rax+220h]
0x14002a0b3  call    _guard_dispatch_icall
0x14002a0b8  mov     ebx, eax
0x14002a0ba  test    eax, eax
0x14002a0bc  jns     short loc_14002A108
0x14002a0be  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a0c5  lea     rax, WPP_GLOBAL_Control
0x14002a0cc  cmp     rcx, rax
0x14002a0cf  jz      loc_14002A546
0x14002a0d5  mov     edx, [rcx+2Ch]
0x14002a0d8  test    dl, 1
0x14002a0db  jz      loc_14002A546
0x14002a0e1  cmp     byte ptr [rcx+29h], 2
0x14002a0e5  jb      loc_14002A546
0x14002a0eb  lea     edx, [r12-19h]
0x14002a0f0  mov     rcx, [rcx+18h]
0x14002a0f4  lea     r8, WPP_2ff8b0bb8e893dc1ecd1a3d57a9e5fd9_Traceguids
0x14002a0fb  mov     r9d, ebx
0x14002a0fe  call    WPP_SF_d
0x14002a103  jmp     loc_14002A546
0x14002a108  mov     rax, cs:WdfFunctions_01033
0x14002a10f  lea     r8, GUID_BUS_VMBUS
0x14002a116  mov     rdx, [rsp+1C0h+var_190]
0x14002a11b  mov     rcx, cs:WdfDriverGlobals
0x14002a122  mov     rax, [rax+6D0h]
0x14002a129  call    _guard_dispatch_icall
0x14002a12e  mov     ebx, eax
0x14002a130  test    eax, eax
0x14002a132  jns     short loc_14002A167
0x14002a134  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a13b  lea     rax, WPP_GLOBAL_Control
0x14002a142  cmp     rcx, rax
0x14002a145  jz      loc_14002A546
0x14002a14b  mov     eax, [rcx+2Ch]
0x14002a14e  test    al, 1
0x14002a150  jz      loc_14002A546
0x14002a156  cmp     byte ptr [rcx+29h], 2
0x14002a15a  jb      loc_14002A546
0x14002a160  mov     edx, 0Eh
0x14002a165  jmp     short loc_14002A0F0
0x14002a167  mov     rax, cs:WdfFunctions_01033
0x14002a16e  mov     r8b, 1
0x14002a171  mov     rdx, [rsp+1C0h+var_190]
0x14002a176  mov     rcx, cs:WdfDriverGlobals
0x14002a17d  mov     rax, [rax+1F0h]
0x14002a184  call    _guard_dispatch_icall
0x14002a189  mov     rax, cs:WdfFunctions_01033
0x14002a190  lea     r8, [rsp+1C0h+var_180]
0x14002a195  mov     rdx, [rsp+1C0h+var_190]
0x14002a19a  mov     rcx, cs:WdfDriverGlobals
0x14002a1a1  mov     rax, [rax+6A0h]
0x14002a1a8  call    _guard_dispatch_icall
0x14002a1ad  mov     ebx, eax
0x14002a1af  test    eax, eax
0x14002a1b1  jns     short loc_14002A1E9
0x14002a1b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a1ba  lea     rax, WPP_GLOBAL_Control
0x14002a1c1  cmp     rcx, rax
0x14002a1c4  jz      loc_14002A546
0x14002a1ca  mov     eax, [rcx+2Ch]
0x14002a1cd  test    al, 1
0x14002a1cf  jz      loc_14002A546
0x14002a1d5  cmp     byte ptr [rcx+29h], 2
0x14002a1d9  jb      loc_14002A546
0x14002a1df  mov     edx, 0Fh
0x14002a1e4  jmp     loc_14002A0F0
0x14002a1e9  mov     rax, cs:WdfFunctions_01033
0x14002a1f0  lea     r8, [rsp+1C0h+var_180]
0x14002a1f5  mov     rdx, [rsp+1C0h+var_190]
0x14002a1fa  mov     rcx, cs:WdfDriverGlobals
0x14002a201  mov     rax, [rax+6B0h]
0x14002a208  call    _guard_dispatch_icall
0x14002a20d  mov     ebx, eax
0x14002a20f  test    eax, eax
0x14002a211  jns     short loc_14002A249
0x14002a213  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a21a  lea     rax, WPP_GLOBAL_Control
0x14002a221  cmp     rcx, rax
0x14002a224  jz      loc_14002A546
0x14002a22a  mov     eax, [rcx+2Ch]
0x14002a22d  test    al, 1
0x14002a22f  jz      loc_14002A546
0x14002a235  cmp     byte ptr [rcx+29h], 2
0x14002a239  jb      loc_14002A546
0x14002a23f  mov     edx, 10h
0x14002a244  jmp     loc_14002A0F0
0x14002a249  mov     rax, cs:WdfFunctions_01033
0x14002a250  lea     r8, [rsp+1C0h+var_180]
0x14002a255  mov     rdx, [rsp+1C0h+var_190]
0x14002a25a  mov     rcx, cs:WdfDriverGlobals
0x14002a261  mov     rax, [rax+6B8h]
0x14002a268  call    _guard_dispatch_icall
0x14002a26d  mov     ebx, eax
0x14002a26f  test    eax, eax
0x14002a271  jns     short loc_14002A2A9
0x14002a273  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a27a  lea     rax, WPP_GLOBAL_Control
0x14002a281  cmp     rcx, rax
0x14002a284  jz      loc_14002A546
0x14002a28a  mov     eax, [rcx+2Ch]
0x14002a28d  test    al, 1
0x14002a28f  jz      loc_14002A546
0x14002a295  cmp     byte ptr [rcx+29h], 2
0x14002a299  jb      loc_14002A546
0x14002a29f  mov     edx, 11h
0x14002a2a4  jmp     loc_14002A0F0
0x14002a2a9  mov     rax, cs:WdfFunctions_01033
0x14002a2b0  lea     r8, [rsp+1C0h+var_170]
0x14002a2b5  mov     rdx, [rsp+1C0h+var_190]
0x14002a2ba  mov     rcx, cs:WdfDriverGlobals
0x14002a2c1  mov     rax, [rax+6A8h]
0x14002a2c8  call    _guard_dispatch_icall
0x14002a2cd  mov     ebx, eax
0x14002a2cf  test    eax, eax
0x14002a2d1  jns     short loc_14002A309
0x14002a2d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a2da  lea     rax, WPP_GLOBAL_Control
0x14002a2e1  cmp     rcx, rax
0x14002a2e4  jz      loc_14002A546
0x14002a2ea  mov     eax, [rcx+2Ch]
0x14002a2ed  test    al, 1
0x14002a2ef  jz      loc_14002A546
0x14002a2f5  cmp     byte ptr [rcx+29h], 2
0x14002a2f9  jb      loc_14002A546
0x14002a2ff  mov     edx, 12h
0x14002a304  jmp     loc_14002A0F0
0x14002a309  mov     ebx, 90h
0x14002a30e  lea     rcx, [rbp+0C0h+var_120]; void *
0x14002a312  mov     r8d, ebx; Size
0x14002a315  xor     edx, edx; Val
0x14002a317  call    memset
0x14002a31c  or      r15d, 0FFFFFFFFh
0x14002a320  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002a327  jz      short loc_14002A34A
0x14002a329  cmp     cs:WdfStructureCount, 29h ; ')'
0x14002a330  jbe     short loc_14002A344
0x14002a332  mov     rax, cs:WdfStructures
0x14002a339  mov     ecx, [rax+148h]
0x14002a33f  mov     [rbp+0C0h+var_120], ecx
0x14002a342  jmp     short loc_14002A34D
0x14002a344  mov     [rbp+0C0h+var_120], r15d
0x14002a348  jmp     short loc_14002A34D
0x14002a34a  mov     [rbp+0C0h+var_120], ebx
0x14002a34d  mov     rdx, [rsp+1C0h+var_190]
0x14002a352  lea     rax, PowerDeviceSelfManagedIoInit
0x14002a359  mov     rcx, cs:WdfDriverGlobals
0x14002a360  lea     r8, [rbp+0C0h+var_120]
0x14002a364  mov     [rbp+0C0h+var_D8], rax
0x14002a368  lea     rax, PowerDeviceSelfManagedIoRestart
0x14002a36f  mov     [rbp+0C0h+var_C8], rax
0x14002a373  lea     rax, PowerDeviceSelfManagedIoSuspend
0x14002a37a  mov     [rbp+0C0h+var_D0], rax
0x14002a37e  mov     rax, cs:WdfFunctions_01033
0x14002a385  mov     rax, [rax+1B8h]
0x14002a38c  call    _guard_dispatch_icall
0x14002a391  mov     rax, cs:WdfFunctions_01033
0x14002a398  mov     rdx, [rsp+1C0h+var_190]
0x14002a39d  mov     rcx, cs:WdfDriverGlobals
0x14002a3a4  mov     rax, [rax+200h]
0x14002a3ab  call    _guard_dispatch_icall
0x14002a3b0  xorps   xmm0, xmm0
0x14002a3b3  xor     eax, eax
0x14002a3b5  cmp     cs:WdfClientVersionHigherThanFramework, al
0x14002a3bb  movups  [rsp+1C0h+var_160], xmm0
0x14002a3c0  mov     [rbp+0C0h+var_130], rax
0x14002a3c4  movups  [rsp+1C0h+var_150], xmm0
0x14002a3c9  movups  [rbp+0C0h+var_140], xmm0
0x14002a3cd  jz      short loc_14002A3F2
0x14002a3cf  cmp     cs:WdfStructureCount, r12d
0x14002a3d6  jbe     short loc_14002A3EB
0x14002a3d8  mov     rax, cs:WdfStructures
0x14002a3df  mov     ecx, [rax+130h]
0x14002a3e5  mov     dword ptr [rsp+1C0h+var_160], ecx
0x14002a3e9  jmp     short loc_14002A3FA
0x14002a3eb  mov     dword ptr [rsp+1C0h+var_160], r15d
0x14002a3f0  jmp     short loc_14002A3FA
0x14002a3f2  mov     dword ptr [rsp+1C0h+var_160], 38h ; '8'
0x14002a3fa  mov     rax, cs:off_14001C0A0
0x14002a401  lea     r9, [rsp+1C0h+var_188]
0x14002a406  mov     rcx, cs:WdfDriverGlobals
0x14002a40d  lea     r8, [rsp+1C0h+var_160]
0x14002a412  mov     [rbp+0C0h+var_130], rax
0x14002a416  lea     rdx, [rsp+1C0h+var_190]
0x14002a41b  lea     rax, PowerDeviceCleanup
0x14002a422  mov     dword ptr [rsp+1C0h+var_150+8], 1
0x14002a42a  mov     qword ptr [rsp+1C0h+var_160+8], rax
0x14002a42f  mov     rax, cs:WdfFunctions_01033
0x14002a436  mov     dword ptr [rsp+1C0h+var_150+0Ch], 1
0x14002a43e  mov     rax, [rax+258h]
0x14002a445  call    _guard_dispatch_icall
0x14002a44a  mov     ebx, eax
0x14002a44c  test    eax, eax
0x14002a44e  jns     short loc_14002A486
0x14002a450  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a457  lea     rax, WPP_GLOBAL_Control
0x14002a45e  cmp     rcx, rax
0x14002a461  jz      loc_14002A546
0x14002a467  mov     eax, [rcx+2Ch]
0x14002a46a  test    al, 1
0x14002a46c  jz      loc_14002A546
0x14002a472  cmp     byte ptr [rcx+29h], 2
0x14002a476  jb      loc_14002A546
0x14002a47c  mov     edx, 13h
0x14002a481  jmp     loc_14002A0F0
0x14002a486  mov     rax, cs:WdfFunctions_01033
0x14002a48d  mov     r8, cs:off_14001C0A0
0x14002a494  mov     rdx, [rsp+1C0h+var_188]
0x14002a499  mov     rcx, cs:WdfDriverGlobals
0x14002a4a0  mov     rax, [rax+650h]
0x14002a4a7  call    _guard_dispatch_icall
0x14002a4ac  xorps   xmm0, xmm0
0x14002a4af  mov     [rax], rsi
0x14002a4b2  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002a4b9  movups  [rbp+0C0h+var_90], xmm0
0x14002a4bd  movups  [rbp+0C0h+var_80], xmm0
0x14002a4c1  movups  [rbp+0C0h+var_70], xmm0
0x14002a4c5  jz      short loc_14002A4E5
0x14002a4c7  cmp     cs:WdfStructureCount, 0Ch
0x14002a4ce  jbe     short loc_14002A4DF
0x14002a4d0  mov     rax, cs:WdfStructures
0x14002a4d7  mov     ecx, [rax+60h]
0x14002a4da  mov     dword ptr [rbp+0C0h+var_90], ecx
0x14002a4dd  jmp     short loc_14002A4EC
0x14002a4df  mov     dword ptr [rbp+0C0h+var_90], r15d
0x14002a4e3  jmp     short loc_14002A4EC
0x14002a4e5  mov     dword ptr [rbp+0C0h+var_90], 30h ; '0'
0x14002a4ec  mov     rax, cs:WdfFunctions_01033
0x14002a4f3  lea     r8, [rbp+0C0h+var_90]
0x14002a4f7  movdqa  xmm0, cs:__xmm@00000002000000020000000200000002
0x14002a4ff  mov     rdx, [rsp+1C0h+var_188]
0x14002a504  mov     rcx, cs:WdfDriverGlobals
0x14002a50b  movups  [rbp+0C0h+var_90+4], xmm0
0x14002a50f  mov     dword ptr [rbp+0C0h+var_80+8], 2
0x14002a516  mov     dword ptr [rbp+0C0h+var_80+0Ch], 2
0x14002a51d  mov     dword ptr [rbp+0C0h+var_70], 2
0x14002a524  mov     dword ptr [rbp+0C0h+var_70+8], r15d
0x14002a528  mov     dword ptr [rbp+0C0h+var_70+0Ch], r15d
0x14002a52c  mov     dword ptr [rbp+0C0h+var_80+4], 1
  ... truncated ...
```
