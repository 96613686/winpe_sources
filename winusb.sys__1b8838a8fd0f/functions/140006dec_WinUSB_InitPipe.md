# WinUSB_InitPipe

- ea: `0x140006dec`
- end: `0x140007513`
- name: `WinUSB_InitPipe`
- size: `1831`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x140007694`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x14000193c`
- `0x140006dec`
- `0x14000751c`
- `0x1400075d8`
- `0x140007f08`
- `0x14000d3ac`
- `0x1400106c0`
- `0x140010700`
- `0x140010bc0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140006fb4`
- `ntoskrnl!KeInitializeSpinLock` at `0x140007323`
- `ntoskrnl!KeInitializeSpinLock` at `0x140006fb4`
- `ntoskrnl!KeInitializeSpinLock` at `0x140007323`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007464`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007464`
- `ntoskrnl!ExAllocatePool2` at `0x140006ee0`
- `ntoskrnl!ExAllocatePool2` at `0x140006ee0`

## pseudocode

```c
__int64 __fastcall WinUSB_InitPipe(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v6; // rdx
  unsigned __int8 v7; // di
  __int64 Pool2; // rax
  int v9; // edx
  __int64 v10; // rbx
  int inited; // esi
  int v12; // edx
  int MaxBytesPerInterval; // eax
  bool v14; // zf
  unsigned int v15; // r8d
  int v16; // ecx
  __int64 v17; // rdx
  int v18; // edx
  int v19; // r9d
  __int64 v20; // rax
  _QWORD *v21; // r15
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 *v24; // rax
  _OWORD v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+60h] [rbp-A0h]
  __int64 *v28; // [rsp+70h] [rbp-90h]
  __int128 v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h]
  _QWORD v31[12]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+F0h] [rbp-10h] BYREF
  int v33; // [rsp+100h] [rbp+0h]

  memset(v31, 0, sizeof(v31));
  LODWORD(v28) = 0;
  memset(v26, 0, sizeof(v26));
  LODWORD(v30) = 0;
  v33 = 0;
  v27 = 0;
  v29 = 0;
  v32 = 0;
  v6 = WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v6,
      1,
      29,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2728))(
    WdfDriverGlobals,
    a3,
    &v32);
  if ( (SBYTE8(v32) & 0x80u) == 0 )
    v7 = BYTE8(v32) & 0xF;
  else
    v7 = (BYTE8(v32) & 0xF) + 16;
  Pool2 = ExAllocatePool2(64, 240, 1112757591);
  v10 = Pool2;
  if ( Pool2 )
  {
    inited = 0;
    *(_OWORD *)Pool2 = v32;
    *(_DWORD *)(Pool2 + 16) = v33;
    *(_OWORD *)(Pool2 + 20) = *(_OWORD *)(a1 + 280);
    *(_DWORD *)(Pool2 + 112) = (*(_DWORD *)(a1 + 32) & 4) != 0 ? 0x200000 : 0x40000;
    MaxBytesPerInterval = WinUsb_GetMaxBytesPerInterval(a1, a2, Pool2);
    v14 = *(_DWORD *)(v10 + 12) == 2;
    *(_DWORD *)(v10 + 168) = MaxBytesPerInterval;
    if ( v14 )
    {
      inited = WinUSB_InitIsochPipe(a1, v10);
      if ( inited < 0 )
        goto LABEL_34;
    }
    *(_QWORD *)(v10 + 160) = a3;
    KeInitializeSpinLock((PKSPIN_LOCK)(v10 + 40));
    v15 = *(_DWORD *)(v10 + 4);
    if ( v15 )
      v16 = *(_DWORD *)(v10 + 112) - *(_DWORD *)(v10 + 112) % v15;
    else
      v16 = 0;
    *(_DWORD *)(v10 + 112) = v16;
    if ( WinUSB_IsInterruptOrBulkInPipe(v10) )
    {
      v17 = *(unsigned int *)(v10 + 4);
      *(_DWORD *)(v10 + 64) = 0;
      *(_WORD *)(v10 + 68) = 0;
      inited = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, __int64, __int64, _QWORD))(WdfFunctions_01015 + 1536))(
                 WdfDriverGlobals,
                 0,
                 512,
                 1112757591,
                 v17,
                 v10 + 72,
                 0);
      if ( inited < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_34:
          if ( *(_QWORD *)(v10 + 72) )
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
          if ( *(_QWORD *)(v10 + 48) )
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
          if ( *(_QWORD *)(v10 + 192) )
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
          ExFreePoolWithTag((PVOID)v10, 0);
          goto LABEL_43;
        }
        v19 = 31;
LABEL_19:
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_dD(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          3,
          v19,
          (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
          v7,
          inited);
        goto LABEL_34;
      }
      *(_QWORD *)(v10 + 80) = 0;
      memset(v31, 0, sizeof(v31));
      v31[5] = WinUSB_SubmitRead;
      LODWORD(v31[0]) = 96;
      *(_QWORD *)((char *)v31 + 4) = 1;
      v20 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
      v21 = (_QWORD *)(v10 + 48);
      inited = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, _QWORD, __int64))(WdfFunctions_01015
                                                                                                  + 1216))(
                 WdfDriverGlobals,
                 v20,
                 v31,
                 0,
                 v10 + 48);
      if ( inited < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_34;
        v19 = 32;
        goto LABEL_19;
      }
      memset(v31, 0, sizeof(v31));
      v31[5] = WinUSB_RawIoRead;
      LODWORD(v31[0]) = 96;
      v31[7] = WinUSB_EvtRawIoStop;
      *(_QWORD *)((char *)v31 + 4) = 0x200000002LL;
      LODWORD(v31[10]) = -1;
      v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
      inited = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, _QWORD, __int64))(WdfFunctions_01015
                                                                                                  + 1216))(
                 WdfDriverGlobals,
                 v22,
                 v31,
                 0,
                 v10 + 56);
      if ( inited < 0 )
        goto LABEL_34;
      *((_QWORD *)&v26[1] + 1) = 0x100000001LL;
      v28 = off_140015040;
      v27 = *(unsigned __int64 *)(a1 + 8);
      memset((char *)v26 + 4, 0, 20);
      LODWORD(v26[0]) = 56;
      inited = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _OWORD *, _QWORD, __int64))(WdfFunctions_01015 + 1976))(
                 WdfDriverGlobals,
                 v26,
                 *(_QWORD *)(v10 + 160),
                 v10 + 104);
      if ( inited < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_34;
        v19 = 33;
        goto LABEL_19;
      }
    }
    else
    {
      if ( !WinUSB_IsInterruptOrBulkOutPipe(v10) )
        goto LABEL_42;
      memset(v31, 0, sizeof(v31));
      v31[5] = WinUSB_SubmitWrite;
      LODWORD(v31[0]) = 96;
      v31[7] = WinUSB_EvtWriteIoStop;
      v31[8] = WinUSB_EvtWriteIoResume;
      *(_QWORD *)((char *)v31 + 4) = 0x200000001LL;
      v23 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
      v21 = (_QWORD *)(v10 + 48);
      inited = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, _QWORD, __int64))(WdfFunctions_01015
                                                                                                  + 1216))(
                 WdfDriverGlobals,
                 v23,
                 v31,
                 0,
                 v10 + 48);
      if ( inited < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_34;
        v19 = 34;
        goto LABEL_19;
      }
    }
    *(_QWORD *)(v10 + 144) = v10 + 136;
    *(_QWORD *)(v10 + 136) = v10 + 136;
    KeInitializeSpinLock((PKSPIN_LOCK)(v10 + 120));
    *(_DWORD *)(v10 + 128) = 0;
    v28 = off_140015090;
    memset(v26, 0, 24);
    *((_QWORD *)&v26[1] + 1) = 0x100000001LL;
    v27 = 0;
    LODWORD(v26[0]) = 56;
    *(_QWORD *)&v27 = *v21;
    v30 = 1;
    *((_QWORD *)&v29 + 1) = WinUSB_ErrorWorkItem;
    *(_QWORD *)&v29 = 24;
    inited = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, _OWORD *, __int64))(WdfFunctions_01015 + 3032))(
               WdfDriverGlobals,
               &v29,
               v26,
               v10 + 152);
    if ( inited < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_34;
      v19 = 35;
      goto LABEL_19;
    }
    v24 = (__int64 *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 1616))(
                       WdfDriverGlobals,
                       *(_QWORD *)(v10 + 152),
                       off_140015090);
    *v24 = a1;
    v24[1] = v10;
LABEL_42:
    *(_QWORD *)(a2 + 8LL * v7 + 24) = v10;
    goto LABEL_43;
  }
  inited = -1073741670;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return (unsigned int)inited;
  LOBYTE(v9) = 2;
  WPP_RECORDER_SF_dD(
    WPP_GLOBAL_Control->DeviceExtension,
    v9,
    3,
    30,
    (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
    v7,
    154);
LABEL_43:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      36,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      inited);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140006dec  mov     [rsp-8+arg_18], rbx
0x140006df1  push    rbp
0x140006df2  push    rsi
0x140006df3  push    rdi
0x140006df4  push    r12
0x140006df6  push    r13
0x140006df8  push    r14
0x140006dfa  push    r15
0x140006dfc  lea     rbp, [rsp-10h]
0x140006e01  sub     rsp, 110h
0x140006e08  mov     rax, cs:__security_cookie
0x140006e0f  xor     rax, rsp
0x140006e12  mov     [rbp+40h+var_38], rax
0x140006e16  mov     r12, rdx
0x140006e19  mov     r15, r8
0x140006e1c  xor     edx, edx; Val
0x140006e1e  mov     r14, rcx
0x140006e21  lea     rcx, [rbp+40h+var_B0]; void *
0x140006e25  lea     r8d, [rdx+60h]; Size
0x140006e29  call    memset
0x140006e2e  xorps   xmm0, xmm0
0x140006e31  xor     eax, eax
0x140006e33  xorps   xmm1, xmm1
0x140006e36  mov     dword ptr [rsp+140h+var_D0], eax
0x140006e3a  movups  [rsp+140h+var_100], xmm0
0x140006e3f  mov     dword ptr [rbp+40h+var_B8], eax
0x140006e42  movups  [rsp+140h+var_F0], xmm0
0x140006e47  mov     [rbp+40h+var_40], eax
0x140006e4a  movups  [rsp+140h+var_E0], xmm0
0x140006e4f  movups  [rsp+140h+var_C8], xmm0
0x140006e54  movups  [rbp+40h+var_50], xmm1
0x140006e58  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006e5f  xor     r13d, r13d
0x140006e62  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006e69  lea     rdx, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140006e70  jz      short loc_140006E98
0x140006e72  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e79  cmp     [rcx+48h], r13w
0x140006e7e  jz      short loc_140006E98
0x140006e80  mov     rcx, [rcx+40h]
0x140006e84  lea     r9d, [r13+1Dh]
0x140006e88  mov     [rsp+140h+var_120], rdx
0x140006e8d  lea     r8d, [r13+1]
0x140006e91  mov     dl, 5
0x140006e93  call    WPP_RECORDER_SF_
0x140006e98  mov     rax, cs:WdfFunctions_01015
0x140006e9f  lea     r8, [rbp+40h+var_50]
0x140006ea3  mov     rcx, cs:WdfDriverGlobals
0x140006eaa  mov     rdx, r15
0x140006ead  mov     rax, [rax+0AA8h]
0x140006eb4  call    _guard_dispatch_icall
0x140006eb9  mov     dil, byte ptr [rbp+40h+var_50+8]
0x140006ebd  test    dil, dil
0x140006ec0  jns     short loc_140006ECC
0x140006ec2  and     dil, 0Fh
0x140006ec6  add     dil, 10h
0x140006eca  jmp     short loc_140006ED0
0x140006ecc  and     dil, 0Fh
0x140006ed0  mov     edx, 0F0h
0x140006ed5  mov     ecx, 40h ; '@'
0x140006eda  mov     r8d, 42535557h
0x140006ee0  call    cs:__imp_ExAllocatePool2
0x140006ee7  nop     dword ptr [rax+rax+00h]
0x140006eec  mov     rbx, rax
0x140006eef  test    rax, rax
0x140006ef2  jnz     short loc_140006F44
0x140006ef4  mov     esi, 0C000009Ah
0x140006ef9  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006f00  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140006f07  jz      loc_1400074E9
0x140006f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f14  lea     r9d, [rbx+1Eh]
0x140006f18  movzx   eax, dil
0x140006f1c  lea     r8d, [rbx+3]
0x140006f20  mov     dword ptr [rsp+140h+var_110], esi
0x140006f24  lea     rdi, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140006f2b  mov     dword ptr [rsp+140h+var_118], eax
0x140006f2f  mov     dl, 2
0x140006f31  mov     rcx, [rcx+40h]
0x140006f35  mov     [rsp+140h+var_120], rdi
0x140006f3a  call    WPP_RECORDER_SF_dD
0x140006f3f  jmp     loc_1400074B4
0x140006f44  movups  xmm0, [rbp+40h+var_50]
0x140006f48  mov     r8, rbx
0x140006f4b  mov     rdx, r12
0x140006f4e  mov     esi, r13d
0x140006f51  movups  xmmword ptr [rax], xmm0
0x140006f54  mov     eax, [rbp+40h+var_40]
0x140006f57  mov     [rbx+10h], eax
0x140006f5a  movups  xmm0, xmmword ptr [r14+118h]
0x140006f62  movdqu  xmmword ptr [rbx+14h], xmm0
0x140006f67  mov     eax, [r14+20h]
0x140006f6b  and     al, 4
0x140006f6d  neg     al
0x140006f6f  sbb     ecx, ecx
0x140006f71  and     ecx, 1C0000h
0x140006f77  add     ecx, 40000h
0x140006f7d  mov     [rbx+70h], ecx
0x140006f80  mov     rcx, r14
0x140006f83  call    WinUsb_GetMaxBytesPerInterval
0x140006f88  cmp     dword ptr [rbx+0Ch], 2
0x140006f8c  mov     [rbx+0A8h], eax
0x140006f92  jnz     short loc_140006FA9
0x140006f94  mov     rdx, rbx
0x140006f97  mov     rcx, r14
0x140006f9a  call    WinUSB_InitIsochPipe
0x140006f9f  mov     esi, eax
0x140006fa1  test    eax, eax
0x140006fa3  js      loc_1400073E5
0x140006fa9  lea     rcx, [rbx+28h]; SpinLock
0x140006fad  mov     [rbx+0A0h], r15
0x140006fb4  call    cs:__imp_KeInitializeSpinLock
0x140006fbb  nop     dword ptr [rax+rax+00h]
0x140006fc0  mov     r8d, [rbx+4]
0x140006fc4  test    r8d, r8d
0x140006fc7  jz      short loc_140006FD7
0x140006fc9  mov     ecx, [rbx+70h]
0x140006fcc  xor     edx, edx
0x140006fce  mov     eax, ecx
0x140006fd0  div     r8d
0x140006fd3  sub     ecx, edx
0x140006fd5  jmp     short loc_140006FDA
0x140006fd7  mov     ecx, r13d
0x140006fda  mov     [rbx+70h], ecx
0x140006fdd  mov     rcx, rbx
0x140006fe0  call    WinUSB_IsInterruptOrBulkInPipe
0x140006fe5  test    al, al
0x140006fe7  jz      loc_14000724D
0x140006fed  mov     edx, [rbx+4]
0x140006ff0  lea     rcx, [rbx+48h]
0x140006ff4  mov     [rbx+40h], r13d
0x140006ff8  mov     r9d, 42535557h
0x140006ffe  mov     [rbx+44h], r13w
0x140007003  mov     r8d, 200h
0x140007009  mov     rax, cs:WdfFunctions_01015
0x140007010  mov     [rsp+140h+var_110], r13
0x140007015  mov     [rsp+140h+var_118], rcx
0x14000701a  mov     rcx, cs:WdfDriverGlobals
0x140007021  mov     rax, [rax+600h]
0x140007028  mov     [rsp+140h+var_120], rdx
0x14000702d  xor     edx, edx
0x14000702f  call    _guard_dispatch_icall
0x140007034  mov     esi, eax
0x140007036  test    eax, eax
0x140007038  jns     short loc_140007089
0x14000703a  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007041  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007048  jz      loc_1400073EC
0x14000704e  mov     r9d, 1Fh
0x140007054  mov     rcx, cs:WPP_GLOBAL_Control
0x14000705b  mov     r8d, 3
0x140007061  movzx   eax, dil
0x140007065  mov     dl, 2
0x140007067  mov     dword ptr [rsp+140h+var_110], esi
0x14000706b  lea     rdi, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140007072  mov     dword ptr [rsp+140h+var_118], eax
0x140007076  mov     rcx, [rcx+40h]
0x14000707a  mov     [rsp+140h+var_120], rdi
0x14000707f  call    WPP_RECORDER_SF_dD
0x140007084  jmp     loc_1400073F3
0x140007089  mov     esi, 60h ; '`'
0x14000708e  mov     [rbx+50h], r13
0x140007092  mov     r8d, esi; Size
0x140007095  lea     rcx, [rbp+40h+var_B0]; void *
0x140007099  xor     edx, edx; Val
0x14000709b  call    memset
0x1400070a0  mov     rcx, cs:WdfDriverGlobals
0x1400070a7  lea     rax, WinUSB_SubmitRead
0x1400070ae  mov     [rbp+40h+var_88], rax
0x1400070b2  mov     rdx, r14
0x1400070b5  mov     rax, cs:WdfFunctions_01015
0x1400070bc  mov     [rbp+40h+var_B0], esi
0x1400070bf  mov     [rbp+40h+var_AC], 1
0x1400070c7  mov     rax, [rax+660h]
0x1400070ce  call    _guard_dispatch_icall
0x1400070d3  mov     rcx, cs:WdfFunctions_01015
0x1400070da  lea     r15, [rbx+30h]
0x1400070de  mov     rdx, rax
0x1400070e1  mov     [rsp+140h+var_120], r15
0x1400070e6  xor     r9d, r9d
0x1400070e9  lea     r8, [rbp+40h+var_B0]
0x1400070ed  mov     rax, [rcx+4C0h]
0x1400070f4  mov     rcx, cs:WdfDriverGlobals
0x1400070fb  call    _guard_dispatch_icall
0x140007100  mov     esi, eax
0x140007102  test    eax, eax
0x140007104  jns     short loc_140007125
0x140007106  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000710d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007114  jz      loc_1400073EC
0x14000711a  mov     r9d, 20h ; ' '
0x140007120  jmp     loc_140007054
0x140007125  mov     esi, 60h ; '`'
0x14000712a  lea     rcx, [rbp+40h+var_B0]; void *
0x14000712e  mov     r8d, esi; Size
0x140007131  xor     edx, edx; Val
0x140007133  call    memset
0x140007138  mov     rcx, cs:WdfDriverGlobals
0x14000713f  lea     rax, WinUSB_RawIoRead
0x140007146  mov     [rbp+40h+var_88], rax
0x14000714a  mov     rdx, r14
0x14000714d  lea     rax, WinUSB_EvtRawIoStop
0x140007154  mov     [rbp+40h+var_B0], esi
0x140007157  mov     [rbp+40h+var_78], rax
0x14000715b  mov     rax, cs:WdfFunctions_01015
0x140007162  mov     dword ptr [rbp+40h+var_AC+4], 2
0x140007169  mov     dword ptr [rbp+40h+var_AC], 2
0x140007170  mov     [rbp+40h+var_60], 0FFFFFFFFh
0x140007177  mov     rax, [rax+660h]
0x14000717e  call    _guard_dispatch_icall
0x140007183  mov     rcx, cs:WdfFunctions_01015
0x14000718a  lea     rdx, [rbx+38h]
0x14000718e  mov     r10, rax
0x140007191  mov     [rsp+140h+var_120], rdx
0x140007196  xor     r9d, r9d
0x140007199  lea     r8, [rbp+40h+var_B0]
0x14000719d  mov     rdx, r10
0x1400071a0  mov     rax, [rcx+4C0h]
0x1400071a7  mov     rcx, cs:WdfDriverGlobals
0x1400071ae  call    _guard_dispatch_icall
0x1400071b3  mov     esi, eax
0x1400071b5  test    eax, eax
0x1400071b7  js      loc_1400073E5
0x1400071bd  mov     rcx, cs:WdfDriverGlobals
0x1400071c4  lea     r9, [rbx+68h]
0x1400071c8  mov     eax, 1
0x1400071cd  mov     dword ptr [rsp+140h+var_F0+4], r13d
0x1400071d2  mov     dword ptr [rsp+140h+var_F0+8], eax
0x1400071d6  lea     rdx, [rsp+140h+var_100]
0x1400071db  mov     dword ptr [rsp+140h+var_F0+0Ch], eax
0x1400071df  xorps   xmm0, xmm0
0x1400071e2  mov     rax, cs:off_140015040
0x1400071e9  mov     [rsp+140h+var_D0], rax
0x1400071ee  mov     rax, [r14+8]
0x1400071f2  mov     qword ptr [rsp+140h+var_E0], rax
0x1400071f7  mov     rax, cs:WdfFunctions_01015
0x1400071fe  movdqu  [rsp+140h+var_100+4], xmm0
0x140007204  mov     qword ptr [rsp+140h+var_E0+8], r13
0x140007209  mov     dword ptr [rsp+140h+var_100], 38h ; '8'
0x140007211  mov     rax, [rax+7B8h]
0x140007218  mov     r8, [rbx+0A0h]
0x14000721f  call    _guard_dispatch_icall
0x140007224  mov     esi, eax
0x140007226  test    eax, eax
0x140007228  jns     loc_140007311
0x14000722e  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007235  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000723c  jz      loc_1400073EC
0x140007242  mov     r9d, 21h ; '!'
0x140007248  jmp     loc_140007054
0x14000724d  mov     rcx, rbx
0x140007250  call    WinUSB_IsInterruptOrBulkOutPipe
0x140007255  test    al, al
0x140007257  jz      loc_14000749D
0x14000725d  mov     esi, 60h ; '`'
0x140007262  lea     rcx, [rbp+40h+var_B0]; void *
0x140007266  mov     r8d, esi; Size
0x140007269  xor     edx, edx; Val
0x14000726b  call    memset
0x140007270  mov     rcx, cs:WdfDriverGlobals
0x140007277  lea     rax, WinUSB_SubmitWrite
0x14000727e  mov     [rbp+40h+var_88], rax
0x140007282  mov     rdx, r14
0x140007285  lea     rax, WinUSB_EvtWriteIoStop
0x14000728c  mov     [rbp+40h+var_B0], esi
0x14000728f  mov     [rbp+40h+var_78], rax
0x140007293  lea     rax, WinUSB_EvtWriteIoResume
0x14000729a  mov     [rbp+40h+var_70], rax
0x14000729e  mov     rax, cs:WdfFunctions_01015
0x1400072a5  mov     dword ptr [rbp+40h+var_AC+4], 2
0x1400072ac  mov     dword ptr [rbp+40h+var_AC], 1
0x1400072b3  mov     rax, [rax+660h]
0x1400072ba  call    _guard_dispatch_icall
0x1400072bf  mov     rcx, cs:WdfFunctions_01015
0x1400072c6  lea     r15, [rbx+30h]
0x1400072ca  mov     rdx, rax
0x1400072cd  mov     [rsp+140h+var_120], r15
0x1400072d2  xor     r9d, r9d
0x1400072d5  lea     r8, [rbp+40h+var_B0]
0x1400072d9  mov     rax, [rcx+4C0h]
0x1400072e0  mov     rcx, cs:WdfDriverGlobals
0x1400072e7  call    _guard_dispatch_icall
0x1400072ec  mov     esi, eax
0x1400072ee  test    eax, eax
0x1400072f0  jns     short loc_140007311
0x1400072f2  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400072f9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007300  jz      loc_1400073EC
0x140007306  mov     r9d, 22h ; '"'
0x14000730c  jmp     loc_140007054
0x140007311  lea     rax, [rbx+88h]
0x140007318  lea     rcx, [rbx+78h]; SpinLock
0x14000731c  mov     [rax+8], rax
0x140007320  mov     [rax], rax
0x140007323  call    cs:__imp_KeInitializeSpinLock
0x14000732a  nop     dword ptr [rax+rax+00h]
0x14000732f  mov     [rbx+80h], r13d
0x140007336  lea     r8, [rsp+140h+var_100]
0x14000733b  mov     rax, cs:off_140015090
0x140007342  lea     rdx, [rsp+140h+var_C8]
  ... truncated ...
```
