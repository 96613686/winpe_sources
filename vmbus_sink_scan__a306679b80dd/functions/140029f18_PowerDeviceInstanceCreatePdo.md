# PowerDeviceInstanceCreatePdo

- ea: `0x140029f18`
- end: `0x14002a521`
- name: `PowerDeviceInstanceCreatePdo`
- size: `1545`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002b260`

## callees

- `0x1400038cc`
- `0x140017000`
- `0x140017190`
- `0x140017540`
- `0x140029f18`

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
      WPP_SF_d(v5->AttachedDevice, v6, WPP_9bc149055a283eb2988b2e39efb7d62e_Traceguids, (unsigned int)v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140029f18  mov     [rsp-8+arg_8], rbx
0x140029f1d  mov     [rsp-8+arg_10], rsi
0x140029f22  push    rbp
0x140029f23  push    r12
0x140029f25  push    r15
0x140029f27  lea     rbp, [rsp-0B0h]
0x140029f2f  sub     rsp, 1B0h
0x140029f36  mov     rax, cs:__security_cookie
0x140029f3d  xor     rax, rsp
0x140029f40  mov     [rbp+0C0h+var_18], rax
0x140029f47  mov     rsi, rdx
0x140029f4a  mov     [rsp+1C0h+var_190], rcx
0x140029f4f  mov     rbx, rcx
0x140029f52  xor     eax, eax
0x140029f54  xor     edx, edx; Val
0x140029f56  mov     [rbp+0C0h+var_11C], eax
0x140029f59  lea     rcx, [rbp+0C0h+var_120]; void *
0x140029f5d  mov     r8d, 8Ch; Size
0x140029f63  call    memset
0x140029f68  movups  xmm1, xmmword ptr cs:aVmbusPowerdevi+10h; "werDevice"
0x140029f6f  mov     rcx, cs:WdfDriverGlobals
0x140029f76  xor     eax, eax
0x140029f78  xorps   xmm0, xmm0
0x140029f7b  mov     dword ptr [rbp+0C0h+var_130], eax
0x140029f7e  movups  [rbp+0C0h+var_90], xmm0
0x140029f82  mov     [rsp+1C0h+var_188], rax
0x140029f87  mov     rdx, rbx
0x140029f8a  lea     r12d, [rax+26h]
0x140029f8e  mov     [rsp+1C0h+var_180], 260024h
0x140029f97  movups  [rbp+0C0h+var_80], xmm0
0x140029f9b  lea     rax, [rbp+0C0h+var_40]
0x140029fa2  mov     [rsp+1C0h+var_170], 1A0018h
0x140029fab  movups  [rbp+0C0h+var_70], xmm0
0x140029faf  mov     [rsp+1C0h+var_178], rax
0x140029fb4  lea     rax, [rbp+0C0h+var_60]
0x140029fb8  movups  [rsp+1C0h+var_160], xmm0
0x140029fbd  mov     [rsp+1C0h+var_168], rax
0x140029fc2  lea     r8d, [r12+4]
0x140029fc7  mov     rax, cs:WdfFunctions_01033
0x140029fce  movups  [rsp+1C0h+var_150], xmm0
0x140029fd3  movups  [rbp+0C0h+var_140], xmm0
0x140029fd7  movups  xmm0, xmmword ptr cs:aVmbusPowerdevi; "VMBUS\\PowerDevice"
0x140029fde  movups  xmmword ptr [rbp+0C0h+var_30], xmm1
0x140029fe5  movups  xmm1, xmmword ptr cs:aPowerdevice0+0Ah; "Device0"
0x140029fec  movups  [rbp+0C0h+var_40], xmm0
0x140029ff3  movsd   xmm0, qword ptr cs:aVmbusPowerdevi+1Eh; "ce"
0x140029ffb  movsd   qword ptr [rbp+0C0h+var_30+0Eh], xmm0
0x14002a003  movups  xmm0, xmmword ptr cs:aPowerdevice0; "PowerDevice0"
0x14002a00a  movups  xmmword ptr [rbp+0C0h+var_60], xmm0
0x14002a00e  movups  xmmword ptr [rbp+0C0h+var_60+0Ah], xmm1
0x14002a012  mov     rax, [rax+210h]
0x14002a019  call    _guard_dispatch_icall
0x14002a01e  mov     rax, cs:WdfFunctions_01033
0x14002a025  lea     r8d, [r12-23h]
0x14002a02a  mov     rdx, [rsp+1C0h+var_190]
0x14002a02f  mov     rcx, cs:WdfDriverGlobals
0x14002a036  mov     rax, [rax+1E8h]
0x14002a03d  call    _guard_dispatch_icall
0x14002a042  mov     rax, cs:WdfFunctions_01033
0x14002a049  lea     r8, SDDL_DEVOBJ_KERNEL_ONLY
0x14002a050  mov     rdx, [rsp+1C0h+var_190]
0x14002a055  mov     rcx, cs:WdfDriverGlobals
0x14002a05c  mov     rax, [rax+220h]
0x14002a063  call    _guard_dispatch_icall
0x14002a068  mov     ebx, eax
0x14002a06a  test    eax, eax
0x14002a06c  jns     short loc_14002A0B8
0x14002a06e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a075  lea     rax, WPP_GLOBAL_Control
0x14002a07c  cmp     rcx, rax
0x14002a07f  jz      loc_14002A4F6
0x14002a085  mov     edx, [rcx+2Ch]
0x14002a088  test    dl, 1
0x14002a08b  jz      loc_14002A4F6
0x14002a091  cmp     byte ptr [rcx+29h], 2
0x14002a095  jb      loc_14002A4F6
0x14002a09b  lea     edx, [r12-19h]
0x14002a0a0  mov     rcx, [rcx+18h]
0x14002a0a4  lea     r8, WPP_9bc149055a283eb2988b2e39efb7d62e_Traceguids
0x14002a0ab  mov     r9d, ebx
0x14002a0ae  call    WPP_SF_d
0x14002a0b3  jmp     loc_14002A4F6
0x14002a0b8  mov     rax, cs:WdfFunctions_01033
0x14002a0bf  lea     r8, GUID_BUS_VMBUS
0x14002a0c6  mov     rdx, [rsp+1C0h+var_190]
0x14002a0cb  mov     rcx, cs:WdfDriverGlobals
0x14002a0d2  mov     rax, [rax+6D0h]
0x14002a0d9  call    _guard_dispatch_icall
0x14002a0de  mov     ebx, eax
0x14002a0e0  test    eax, eax
0x14002a0e2  jns     short loc_14002A117
0x14002a0e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a0eb  lea     rax, WPP_GLOBAL_Control
0x14002a0f2  cmp     rcx, rax
0x14002a0f5  jz      loc_14002A4F6
0x14002a0fb  mov     eax, [rcx+2Ch]
0x14002a0fe  test    al, 1
0x14002a100  jz      loc_14002A4F6
0x14002a106  cmp     byte ptr [rcx+29h], 2
0x14002a10a  jb      loc_14002A4F6
0x14002a110  mov     edx, 0Eh
0x14002a115  jmp     short loc_14002A0A0
0x14002a117  mov     rax, cs:WdfFunctions_01033
0x14002a11e  mov     r8b, 1
0x14002a121  mov     rdx, [rsp+1C0h+var_190]
0x14002a126  mov     rcx, cs:WdfDriverGlobals
0x14002a12d  mov     rax, [rax+1F0h]
0x14002a134  call    _guard_dispatch_icall
0x14002a139  mov     rax, cs:WdfFunctions_01033
0x14002a140  lea     r8, [rsp+1C0h+var_180]
0x14002a145  mov     rdx, [rsp+1C0h+var_190]
0x14002a14a  mov     rcx, cs:WdfDriverGlobals
0x14002a151  mov     rax, [rax+6A0h]
0x14002a158  call    _guard_dispatch_icall
0x14002a15d  mov     ebx, eax
0x14002a15f  test    eax, eax
0x14002a161  jns     short loc_14002A199
0x14002a163  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a16a  lea     rax, WPP_GLOBAL_Control
0x14002a171  cmp     rcx, rax
0x14002a174  jz      loc_14002A4F6
0x14002a17a  mov     eax, [rcx+2Ch]
0x14002a17d  test    al, 1
0x14002a17f  jz      loc_14002A4F6
0x14002a185  cmp     byte ptr [rcx+29h], 2
0x14002a189  jb      loc_14002A4F6
0x14002a18f  mov     edx, 0Fh
0x14002a194  jmp     loc_14002A0A0
0x14002a199  mov     rax, cs:WdfFunctions_01033
0x14002a1a0  lea     r8, [rsp+1C0h+var_180]
0x14002a1a5  mov     rdx, [rsp+1C0h+var_190]
0x14002a1aa  mov     rcx, cs:WdfDriverGlobals
0x14002a1b1  mov     rax, [rax+6B0h]
0x14002a1b8  call    _guard_dispatch_icall
0x14002a1bd  mov     ebx, eax
0x14002a1bf  test    eax, eax
0x14002a1c1  jns     short loc_14002A1F9
0x14002a1c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a1ca  lea     rax, WPP_GLOBAL_Control
0x14002a1d1  cmp     rcx, rax
0x14002a1d4  jz      loc_14002A4F6
0x14002a1da  mov     eax, [rcx+2Ch]
0x14002a1dd  test    al, 1
0x14002a1df  jz      loc_14002A4F6
0x14002a1e5  cmp     byte ptr [rcx+29h], 2
0x14002a1e9  jb      loc_14002A4F6
0x14002a1ef  mov     edx, 10h
0x14002a1f4  jmp     loc_14002A0A0
0x14002a1f9  mov     rax, cs:WdfFunctions_01033
0x14002a200  lea     r8, [rsp+1C0h+var_180]
0x14002a205  mov     rdx, [rsp+1C0h+var_190]
0x14002a20a  mov     rcx, cs:WdfDriverGlobals
0x14002a211  mov     rax, [rax+6B8h]
0x14002a218  call    _guard_dispatch_icall
0x14002a21d  mov     ebx, eax
0x14002a21f  test    eax, eax
0x14002a221  jns     short loc_14002A259
0x14002a223  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a22a  lea     rax, WPP_GLOBAL_Control
0x14002a231  cmp     rcx, rax
0x14002a234  jz      loc_14002A4F6
0x14002a23a  mov     eax, [rcx+2Ch]
0x14002a23d  test    al, 1
0x14002a23f  jz      loc_14002A4F6
0x14002a245  cmp     byte ptr [rcx+29h], 2
0x14002a249  jb      loc_14002A4F6
0x14002a24f  mov     edx, 11h
0x14002a254  jmp     loc_14002A0A0
0x14002a259  mov     rax, cs:WdfFunctions_01033
0x14002a260  lea     r8, [rsp+1C0h+var_170]
0x14002a265  mov     rdx, [rsp+1C0h+var_190]
0x14002a26a  mov     rcx, cs:WdfDriverGlobals
0x14002a271  mov     rax, [rax+6A8h]
0x14002a278  call    _guard_dispatch_icall
0x14002a27d  mov     ebx, eax
0x14002a27f  test    eax, eax
0x14002a281  jns     short loc_14002A2B9
0x14002a283  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a28a  lea     rax, WPP_GLOBAL_Control
0x14002a291  cmp     rcx, rax
0x14002a294  jz      loc_14002A4F6
0x14002a29a  mov     eax, [rcx+2Ch]
0x14002a29d  test    al, 1
0x14002a29f  jz      loc_14002A4F6
0x14002a2a5  cmp     byte ptr [rcx+29h], 2
0x14002a2a9  jb      loc_14002A4F6
0x14002a2af  mov     edx, 12h
0x14002a2b4  jmp     loc_14002A0A0
0x14002a2b9  mov     ebx, 90h
0x14002a2be  lea     rcx, [rbp+0C0h+var_120]; void *
0x14002a2c2  mov     r8d, ebx; Size
0x14002a2c5  xor     edx, edx; Val
0x14002a2c7  call    memset
0x14002a2cc  or      r15d, 0FFFFFFFFh
0x14002a2d0  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002a2d7  jz      short loc_14002A2FA
0x14002a2d9  cmp     cs:WdfStructureCount, 29h ; ')'
0x14002a2e0  jbe     short loc_14002A2F4
0x14002a2e2  mov     rax, cs:WdfStructures
0x14002a2e9  mov     ecx, [rax+148h]
0x14002a2ef  mov     [rbp+0C0h+var_120], ecx
0x14002a2f2  jmp     short loc_14002A2FD
0x14002a2f4  mov     [rbp+0C0h+var_120], r15d
0x14002a2f8  jmp     short loc_14002A2FD
0x14002a2fa  mov     [rbp+0C0h+var_120], ebx
0x14002a2fd  mov     rdx, [rsp+1C0h+var_190]
0x14002a302  lea     rax, PowerDeviceSelfManagedIoInit
0x14002a309  mov     rcx, cs:WdfDriverGlobals
0x14002a310  lea     r8, [rbp+0C0h+var_120]
0x14002a314  mov     [rbp+0C0h+var_D8], rax
0x14002a318  lea     rax, PowerDeviceSelfManagedIoRestart
0x14002a31f  mov     [rbp+0C0h+var_C8], rax
0x14002a323  lea     rax, PowerDeviceSelfManagedIoSuspend
0x14002a32a  mov     [rbp+0C0h+var_D0], rax
0x14002a32e  mov     rax, cs:WdfFunctions_01033
0x14002a335  mov     rax, [rax+1B8h]
0x14002a33c  call    _guard_dispatch_icall
0x14002a341  mov     rax, cs:WdfFunctions_01033
0x14002a348  mov     rdx, [rsp+1C0h+var_190]
0x14002a34d  mov     rcx, cs:WdfDriverGlobals
0x14002a354  mov     rax, [rax+200h]
0x14002a35b  call    _guard_dispatch_icall
0x14002a360  xorps   xmm0, xmm0
0x14002a363  xor     eax, eax
0x14002a365  cmp     cs:WdfClientVersionHigherThanFramework, al
0x14002a36b  movups  [rsp+1C0h+var_160], xmm0
0x14002a370  mov     [rbp+0C0h+var_130], rax
0x14002a374  movups  [rsp+1C0h+var_150], xmm0
0x14002a379  movups  [rbp+0C0h+var_140], xmm0
0x14002a37d  jz      short loc_14002A3A2
0x14002a37f  cmp     cs:WdfStructureCount, r12d
0x14002a386  jbe     short loc_14002A39B
0x14002a388  mov     rax, cs:WdfStructures
0x14002a38f  mov     ecx, [rax+130h]
0x14002a395  mov     dword ptr [rsp+1C0h+var_160], ecx
0x14002a399  jmp     short loc_14002A3AA
0x14002a39b  mov     dword ptr [rsp+1C0h+var_160], r15d
0x14002a3a0  jmp     short loc_14002A3AA
0x14002a3a2  mov     dword ptr [rsp+1C0h+var_160], 38h ; '8'
0x14002a3aa  mov     rax, cs:off_14001C0A0
0x14002a3b1  lea     r9, [rsp+1C0h+var_188]
0x14002a3b6  mov     rcx, cs:WdfDriverGlobals
0x14002a3bd  lea     r8, [rsp+1C0h+var_160]
0x14002a3c2  mov     [rbp+0C0h+var_130], rax
0x14002a3c6  lea     rdx, [rsp+1C0h+var_190]
0x14002a3cb  lea     rax, PowerDeviceCleanup
0x14002a3d2  mov     dword ptr [rsp+1C0h+var_150+8], 1
0x14002a3da  mov     qword ptr [rsp+1C0h+var_160+8], rax
0x14002a3df  mov     rax, cs:WdfFunctions_01033
0x14002a3e6  mov     dword ptr [rsp+1C0h+var_150+0Ch], 1
0x14002a3ee  mov     rax, [rax+258h]
0x14002a3f5  call    _guard_dispatch_icall
0x14002a3fa  mov     ebx, eax
0x14002a3fc  test    eax, eax
0x14002a3fe  jns     short loc_14002A436
0x14002a400  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a407  lea     rax, WPP_GLOBAL_Control
0x14002a40e  cmp     rcx, rax
0x14002a411  jz      loc_14002A4F6
0x14002a417  mov     eax, [rcx+2Ch]
0x14002a41a  test    al, 1
0x14002a41c  jz      loc_14002A4F6
0x14002a422  cmp     byte ptr [rcx+29h], 2
0x14002a426  jb      loc_14002A4F6
0x14002a42c  mov     edx, 13h
0x14002a431  jmp     loc_14002A0A0
0x14002a436  mov     rax, cs:WdfFunctions_01033
0x14002a43d  mov     r8, cs:off_14001C0A0
0x14002a444  mov     rdx, [rsp+1C0h+var_188]
0x14002a449  mov     rcx, cs:WdfDriverGlobals
0x14002a450  mov     rax, [rax+650h]
0x14002a457  call    _guard_dispatch_icall
0x14002a45c  xorps   xmm0, xmm0
0x14002a45f  mov     [rax], rsi
0x14002a462  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002a469  movups  [rbp+0C0h+var_90], xmm0
0x14002a46d  movups  [rbp+0C0h+var_80], xmm0
0x14002a471  movups  [rbp+0C0h+var_70], xmm0
0x14002a475  jz      short loc_14002A495
0x14002a477  cmp     cs:WdfStructureCount, 0Ch
0x14002a47e  jbe     short loc_14002A48F
0x14002a480  mov     rax, cs:WdfStructures
0x14002a487  mov     ecx, [rax+60h]
0x14002a48a  mov     dword ptr [rbp+0C0h+var_90], ecx
0x14002a48d  jmp     short loc_14002A49C
0x14002a48f  mov     dword ptr [rbp+0C0h+var_90], r15d
0x14002a493  jmp     short loc_14002A49C
0x14002a495  mov     dword ptr [rbp+0C0h+var_90], 30h ; '0'
0x14002a49c  mov     rax, cs:WdfFunctions_01033
0x14002a4a3  lea     r8, [rbp+0C0h+var_90]
0x14002a4a7  movdqa  xmm0, cs:__xmm@00000002000000020000000200000002
0x14002a4af  mov     rdx, [rsp+1C0h+var_188]
0x14002a4b4  mov     rcx, cs:WdfDriverGlobals
0x14002a4bb  movups  [rbp+0C0h+var_90+4], xmm0
0x14002a4bf  mov     dword ptr [rbp+0C0h+var_80+8], 2
0x14002a4c6  mov     dword ptr [rbp+0C0h+var_80+0Ch], 2
0x14002a4cd  mov     dword ptr [rbp+0C0h+var_70], 2
0x14002a4d4  mov     dword ptr [rbp+0C0h+var_70+8], r15d
0x14002a4d8  mov     dword ptr [rbp+0C0h+var_70+0Ch], r15d
0x14002a4dc  mov     dword ptr [rbp+0C0h+var_80+4], 1
  ... truncated ...
```
