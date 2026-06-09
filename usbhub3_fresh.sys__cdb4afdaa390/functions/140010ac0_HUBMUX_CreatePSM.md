# HUBMUX_CreatePSM

- ea: `0x140010ac0`
- end: `0x140011059`
- name: `HUBMUX_CreatePSM`
- size: `1433`
- prototype: `unsigned __int64 __fastcall(__int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140010598`

## callees

- `0x140002430`
- `0x1400024b8`
- `0x1400067ac`
- `0x140010ac0`
- `0x140011d90`
- `0x140045530`
- `0x140045570`
- `0x140045940`

## import_xrefs

- `ntoskrnl!ExAllocateTimer` at `0x140010e3b`
- `ntoskrnl!ExAllocateTimer` at `0x140010e3b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010de6`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010de6`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140010cec`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140010cec`

## pseudocode

```c
unsigned __int64 __fastcall HUBMUX_CreatePSM(__int64 a1, unsigned __int16 *a2)
{
  int v4; // eax
  int v5; // edx
  __int64 v6; // rax
  __int64 v7; // rsi
  int v8; // r9d
  _QWORD *v9; // r12
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  int v14; // edx
  int v15; // r9d
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 Timer; // rax
  int v19; // edx
  int v20; // edx
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // [rsp+20h] [rbp-A9h]
  unsigned __int64 v26; // [rsp+40h] [rbp-89h] BYREF
  __int128 v27; // [rsp+48h] [rbp-81h] BYREF
  __int64 (__fastcall *v28)(__int64); // [rsp+58h] [rbp-71h]
  __int64 v29; // [rsp+60h] [rbp-69h]
  __int128 v30; // [rsp+68h] [rbp-61h]
  __int64 *v31; // [rsp+78h] [rbp-51h]
  __int128 v32; // [rsp+80h] [rbp-49h] BYREF
  __int128 v33; // [rsp+90h] [rbp-39h]
  __int64 v34; // [rsp+A0h] [rbp-29h]
  __int128 v35; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-11h]
  char pszDest[16]; // [rsp+C8h] [rbp-1h] BYREF
  __int64 v38; // [rsp+D8h] [rbp+Fh]

  *(_QWORD *)&v27 = 56;
  LODWORD(v34) = 0;
  v38 = 0;
  v31 = off_14006B158;
  v30 = *(unsigned __int64 *)(a1 + 16);
  v26 = 0;
  *((_QWORD *)&v27 + 1) = HUBMISC_EvtPsmCleanup;
  v28 = HUBMISC_EvtPsmDestroy;
  v32 = 0;
  v33 = 0;
  v29 = 0x100000002LL;
  v35 = 0;
  v36 = 0;
  *(_OWORD *)pszDest = 0;
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, unsigned __int64 *))(WdfFunctions_01015 + 1656))(
         WdfDriverGlobals,
         &v27,
         &v26);
  if ( v4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 2536), v5, 4, 10, (__int64)WPP_f6bc06825974302b29b4735b6d0d1d51_Traceguids, v4);
    }
    v26 = 0;
    goto LABEL_24;
  }
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
    WdfDriverGlobals,
    v6,
    "PSM Tag",
    141,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hsmmux.c");
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v26,
         off_14006B158);
  memset((void *)(v7 + 8), 0, 0x5D0u);
  *(_QWORD *)v7 = a1;
  *(_OWORD *)(v7 + 200) = *(_OWORD *)a2;
  *(_OWORD *)(v7 + 216) = *((_OWORD *)a2 + 1);
  *(_QWORD *)(v7 + 232) = *((_QWORD *)a2 + 4);
  v8 = *(_DWORD *)(a1 + 96);
  v25 = *a2;
  *(_QWORD *)&v35 = 56;
  pszDest[0] = 0;
  HIDWORD(v36) = 16;
  v38 = 0x200000002LL;
  *(_QWORD *)&v36 = v7;
  BYTE8(v36) = 1;
  *((_QWORD *)&v35 + 1) = 0x20000000400LL;
  RtlStringCchPrintfA(pszDest, 0x10u, "hub%d port%d", v8, v25);
  v9 = (_QWORD *)(v7 + 1432);
  v10 = (_QWORD *)(a1 + 2536);
  if ( (int)imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v35, v7 + 1432) < 0 )
    *v9 = *v10;
  v11 = *(_QWORD *)(a1 + 16);
  v31 = 0;
  v28 = 0;
  v29 = 0x100000001LL;
  v30 = v26;
  v27 = 0;
  LODWORD(v27) = 56;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 336))(WdfDriverGlobals, v11);
  v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64))(WdfFunctions_01015 + 1976))(
          WdfDriverGlobals,
          &v27,
          v12,
          v7 + 16);
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_24;
    v15 = 11;
    goto LABEL_10;
  }
  *(_QWORD *)(v7 + 32) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2280))(
                           WdfDriverGlobals,
                           *(_QWORD *)(v7 + 16));
  KeInitializeSpinLock((PKSPIN_LOCK)(v7 + 1112));
  v16 = *(_QWORD *)v7;
  *(_DWORD *)(v7 + 1152) = 0;
  *(_DWORD *)(v7 + 1224) = 0;
  *(_QWORD *)(v7 + 1232) = v7;
  *(_QWORD *)(v7 + 1240) = HUBSM_AddPsm20Event;
  v17 = *(_QWORD *)(v16 + 248);
  *(_QWORD *)(v7 + 1272) = v16;
  *(_QWORD *)(v7 + 1304) = v17;
  Timer = ExAllocateTimer(HUBMISC_PsmEventTimer, v7, 4);
  *(_QWORD *)(v7 + 1312) = Timer;
  if ( Timer )
  {
    if ( (*(_DWORD *)(a1 + 40) & 0x80000) != 0 )
    {
      v31 = 0;
      v33 = 0;
      LODWORD(v33) = 0;
      DWORD2(v33) = 0;
      BYTE4(v33) = 1;
      v28 = 0;
      v29 = 0x100000001LL;
      v30 = v26;
      v34 = 0;
      *((_QWORD *)&v32 + 1) = HUBMISC_PsmResetCompletePollingTimer;
      v27 = 0;
      LODWORD(v27) = 56;
      *(_QWORD *)&v32 = 40;
      v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01015 + 2544))(
              WdfDriverGlobals,
              &v32,
              &v27,
              v7 + 240);
      if ( v13 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_24:
          if ( v26 )
          {
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
            return 0;
          }
          return v26;
        }
        v15 = 13;
LABEL_10:
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_d(*v9, v14, 4, v15, (__int64)WPP_f6bc06825974302b29b4735b6d0d1d51_Traceguids, v13);
        goto LABEL_24;
      }
    }
    v22 = *(_QWORD *)v7;
    v23 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 248))(
            WdfDriverGlobals,
            *(_QWORD *)(*(_QWORD *)v7 + 16LL));
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(v22 + 504))(*(_QWORD *)(v22 + 248), v23, 1);
    *(_QWORD *)(v7 + 1264) = v24;
    if ( !v24 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = 2;
        WPP_RECORDER_SF_(*v9, v20, 4, 14, (__int64)WPP_f6bc06825974302b29b4735b6d0d1d51_Traceguids);
      }
      goto LABEL_24;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v26;
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_(*v10, v19, 3, 12, (__int64)WPP_f6bc06825974302b29b4735b6d0d1d51_Traceguids);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v20) = 4;
    WPP_RECORDER_SF_qqd(
      *(_QWORD *)(a1 + 2536),
      v20,
      3,
      15,
      (__int64)WPP_f6bc06825974302b29b4735b6d0d1d51_Traceguids,
      a1,
      v7,
      *a2);
  }
  return v26;
}

```

## disassembly

```asm
0x140010ac0  mov     [rsp-8+arg_10], rbx
0x140010ac5  push    rbp
0x140010ac6  push    rsi
0x140010ac7  push    rdi
0x140010ac8  push    r12
0x140010aca  push    r13
0x140010acc  push    r14
0x140010ace  push    r15
0x140010ad0  lea     rbp, [rsp-27h]
0x140010ad5  sub     rsp, 0F0h
0x140010adc  mov     rax, cs:__security_cookie
0x140010ae3  xor     rax, rsp
0x140010ae6  mov     [rbp+57h+var_40], rax
0x140010aea  xor     eax, eax
0x140010aec  mov     qword ptr [rsp+120h+var_D8], 38h ; '8'
0x140010af5  mov     dword ptr [rbp+57h+var_80], eax
0x140010af8  lea     r8, [rsp+120h+var_E0]
0x140010afd  mov     [rbp+57h+var_48], rax
0x140010b01  xor     edi, edi
0x140010b03  mov     rax, cs:off_14006B158
0x140010b0a  xorps   xmm1, xmm1
0x140010b0d  mov     [rbp+57h+var_A8], rax
0x140010b11  xorps   xmm0, xmm0
0x140010b14  mov     rax, [rcx+10h]
0x140010b18  mov     r13, rdx
0x140010b1b  mov     qword ptr [rbp+57h+var_B8], rax
0x140010b1f  lea     r14d, [rdi+1]
0x140010b23  lea     rax, HUBMISC_EvtPsmCleanup
0x140010b2a  mov     [rsp+120h+var_E0], rdi
0x140010b2f  mov     qword ptr [rbp+57h+var_D8+8], rax
0x140010b33  lea     ebx, [rdi+2]
0x140010b36  lea     rax, HUBMISC_EvtPsmDestroy
0x140010b3d  mov     qword ptr [rbp+57h+var_B8+8], rdi
0x140010b41  mov     qword ptr [rbp+57h+var_C8], rax
0x140010b45  lea     rdx, [rsp+120h+var_D8]
0x140010b4a  mov     rax, cs:WdfFunctions_01015
0x140010b51  mov     r15, rcx
0x140010b54  mov     rcx, cs:WdfDriverGlobals
0x140010b5b  movups  [rbp+57h+var_A0], xmm0
0x140010b5f  mov     dword ptr [rbp+57h+var_C8+0Ch], r14d
0x140010b63  movups  [rbp+57h+var_90], xmm0
0x140010b67  mov     dword ptr [rbp+57h+var_C8+8], ebx
0x140010b6a  movups  [rbp+57h+var_78], xmm1
0x140010b6e  movups  [rbp+57h+var_68], xmm1
0x140010b72  movups  xmmword ptr [rbp+57h+pszDest], xmm1
0x140010b76  mov     rax, [rax+678h]
0x140010b7d  call    _guard_dispatch_icall
0x140010b82  test    eax, eax
0x140010b84  jns     short loc_140010BCA
0x140010b86  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140010b8d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140010b94  jz      short loc_140010BBC
0x140010b96  mov     rcx, [r15+9E8h]
0x140010b9d  lea     r9d, [r14+9]
0x140010ba1  mov     dword ptr [rsp+120h+var_F8], eax
0x140010ba5  lea     r14, WPP_f6bc06825974302b29b4735b6d0d1d51_Traceguids
0x140010bac  lea     r8d, [rbx+2]
0x140010bb0  mov     [rsp+120h+var_100], r14
0x140010bb5  mov     dl, bl
0x140010bb7  call    WPP_RECORDER_SF_d
0x140010bbc  mov     [rsp+120h+var_E0], 0
0x140010bc5  jmp     loc_140011023
0x140010bca  mov     rax, cs:WdfFunctions_01015
0x140010bd1  mov     rdx, r15
0x140010bd4  mov     rcx, cs:WdfDriverGlobals
0x140010bdb  mov     rax, [rax+660h]
0x140010be2  call    _guard_dispatch_icall
0x140010be7  mov     rcx, cs:WdfFunctions_01015
0x140010bee  lea     r8, PsmTag; "PSM Tag"
0x140010bf5  mov     rdx, rax
0x140010bf8  mov     r9d, 8Dh
0x140010bfe  mov     r10, [rcx+668h]
0x140010c05  lea     rcx, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x140010c0c  mov     [rsp+120h+var_100], rcx
0x140010c11  mov     rax, r10
0x140010c14  mov     rcx, cs:WdfDriverGlobals
0x140010c1b  call    _guard_dispatch_icall
0x140010c20  mov     rax, cs:WdfFunctions_01015
0x140010c27  mov     r8, cs:off_14006B158
0x140010c2e  mov     rdx, [rsp+120h+var_E0]
0x140010c33  mov     rcx, cs:WdfDriverGlobals
0x140010c3a  mov     rax, [rax+650h]
0x140010c41  call    _guard_dispatch_icall
0x140010c46  xor     edx, edx; Val
0x140010c48  mov     r8d, 5D0h; Size
0x140010c4e  mov     rsi, rax
0x140010c51  lea     rcx, [rax+8]; void *
0x140010c55  call    memset
0x140010c5a  mov     [rsi], r15
0x140010c5d  lea     r8, pszFormat; "hub%d port%d"
0x140010c64  movups  xmm0, xmmword ptr [r13+0]
0x140010c69  mov     edx, 10h; cchDest
0x140010c6e  lea     rcx, [rbp+57h+pszDest]; pszDest
0x140010c72  movups  xmmword ptr [rsi+0C8h], xmm0
0x140010c79  movups  xmm1, xmmword ptr [r13+10h]
0x140010c7e  movups  xmmword ptr [rsi+0D8h], xmm1
0x140010c85  movsd   xmm0, qword ptr [r13+20h]
0x140010c8b  movsd   qword ptr [rsi+0E8h], xmm0
0x140010c93  movzx   eax, word ptr [r13+0]
0x140010c98  mov     r9d, [r15+60h]
0x140010c9c  mov     dword ptr [rsp+120h+var_100], eax
0x140010ca0  mov     qword ptr [rbp+57h+var_78], 38h ; '8'
0x140010ca8  mov     [rbp+57h+pszDest], dil
0x140010cac  mov     dword ptr [rbp+57h+var_68+0Ch], edx
0x140010caf  mov     dword ptr [rbp+57h+var_48], ebx
0x140010cb2  mov     dword ptr [rbp+57h+var_48+4], ebx
0x140010cb5  mov     qword ptr [rbp+57h+var_68], rsi
0x140010cb9  mov     byte ptr [rbp+57h+var_68+8], r14b
0x140010cbd  mov     dword ptr [rbp+57h+var_78+8], 400h
0x140010cc4  mov     dword ptr [rbp+57h+var_78+0Ch], 200h
0x140010ccb  call    RtlStringCchPrintfA
0x140010cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x140010cd7  lea     r12, [rsi+598h]
0x140010cde  mov     r8, r12
0x140010ce1  lea     rdx, [rbp+57h+var_78]
0x140010ce5  lea     rbx, [r15+9E8h]
0x140010cec  call    cs:__imp_imp_WppRecorderLogCreate
0x140010cf3  nop     dword ptr [rax+rax+00h]
0x140010cf8  test    eax, eax
0x140010cfa  jns     short loc_140010D03
0x140010cfc  mov     rax, [rbx]
0x140010cff  mov     [r12], rax
0x140010d03  mov     rdx, [r15+10h]
0x140010d07  xor     eax, eax
0x140010d09  mov     rcx, cs:WdfDriverGlobals
0x140010d10  xorps   xmm0, xmm0
0x140010d13  mov     [rbp+57h+var_A8], rax
0x140010d17  mov     rax, [rsp+120h+var_E0]
0x140010d1c  movups  [rbp+57h+var_C8], xmm0
0x140010d20  mov     dword ptr [rbp+57h+var_C8+8], r14d
0x140010d24  movups  [rbp+57h+var_B8], xmm0
0x140010d28  mov     qword ptr [rbp+57h+var_B8], rax
0x140010d2c  mov     rax, cs:WdfFunctions_01015
0x140010d33  movups  [rsp+120h+var_D8], xmm0
0x140010d38  mov     dword ptr [rsp+120h+var_D8], 38h ; '8'
0x140010d40  mov     dword ptr [rbp+57h+var_C8+0Ch], r14d
0x140010d44  mov     rax, [rax+150h]
0x140010d4b  call    _guard_dispatch_icall
0x140010d50  mov     rcx, cs:WdfFunctions_01015
0x140010d57  lea     r9, [rsi+10h]
0x140010d5b  mov     r8, rax
0x140010d5e  lea     rdx, [rsp+120h+var_D8]
0x140010d63  mov     r10, [rcx+7B8h]
0x140010d6a  mov     rcx, cs:WdfDriverGlobals
0x140010d71  mov     rax, r10
0x140010d74  call    _guard_dispatch_icall
0x140010d79  test    eax, eax
0x140010d7b  jns     short loc_140010DBD
0x140010d7d  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140010d84  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140010d8b  jz      loc_140011023
0x140010d91  mov     r9d, 0Bh
0x140010d97  mov     rcx, [r12]
0x140010d9b  lea     r14, WPP_f6bc06825974302b29b4735b6d0d1d51_Traceguids
0x140010da2  mov     dword ptr [rsp+120h+var_F8], eax
0x140010da6  mov     r8d, 4
0x140010dac  mov     dl, 2
0x140010dae  mov     [rsp+120h+var_100], r14
0x140010db3  call    WPP_RECORDER_SF_d
0x140010db8  jmp     loc_140011023
0x140010dbd  mov     rax, cs:WdfFunctions_01015
0x140010dc4  mov     rdx, [rsi+10h]
0x140010dc8  mov     rcx, cs:WdfDriverGlobals
0x140010dcf  mov     rax, [rax+8E8h]
0x140010dd6  call    _guard_dispatch_icall
0x140010ddb  lea     rcx, [rsi+458h]; SpinLock
0x140010de2  mov     [rsi+20h], rax
0x140010de6  call    cs:__imp_KeInitializeSpinLock
0x140010ded  nop     dword ptr [rax+rax+00h]
0x140010df2  mov     rcx, [rsi]
0x140010df5  lea     rax, HUBSM_AddPsm20Event
0x140010dfc  mov     [rsi+480h], edi
0x140010e02  mov     r8d, 4
0x140010e08  mov     [rsi+4C8h], edi
0x140010e0e  mov     rdx, rsi
0x140010e11  mov     [rsi+4D0h], rsi
0x140010e18  mov     [rsi+4D8h], rax
0x140010e1f  mov     rax, [rcx+0F8h]
0x140010e26  mov     [rsi+4F8h], rcx
0x140010e2d  lea     rcx, HUBMISC_PsmEventTimer
0x140010e34  mov     [rsi+518h], rax
0x140010e3b  call    cs:__imp_ExAllocateTimer
0x140010e42  nop     dword ptr [rax+rax+00h]
0x140010e47  mov     [rsi+520h], rax
0x140010e4e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140010e55  lea     r14, WPP_f6bc06825974302b29b4735b6d0d1d51_Traceguids
0x140010e5c  test    rax, rax
0x140010e5f  jnz     loc_140010EEB
0x140010e65  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140010e6c  jz      short loc_140010EBE
0x140010e6e  mov     rcx, [rbx]
0x140010e71  lea     r9d, [rax+0Ch]
0x140010e75  lea     r8d, [rax+3]
0x140010e79  mov     [rsp+120h+var_100], r14
0x140010e7e  mov     dl, 2
0x140010e80  call    WPP_RECORDER_SF_
0x140010e85  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140010e8c  jz      short loc_140010EBE
0x140010e8e  movzx   eax, word ptr [r13+0]
0x140010e93  mov     r9d, 0Fh
0x140010e99  mov     rcx, [r15+9E8h]
0x140010ea0  mov     dl, 4
0x140010ea2  mov     [rsp+120h+var_E8], eax
0x140010ea6  mov     [rsp+120h+var_F0], rsi
0x140010eab  lea     r8d, [r9-0Ch]
0x140010eaf  mov     [rsp+120h+var_F8], r15
0x140010eb4  mov     [rsp+120h+var_100], r14
0x140010eb9  call    WPP_RECORDER_SF_qqd
0x140010ebe  mov     rax, [rsp+120h+var_E0]
0x140010ec3  mov     rcx, [rbp+57h+var_40]
0x140010ec7  xor     rcx, rsp; StackCookie
0x140010eca  call    __security_check_cookie
0x140010ecf  mov     rbx, [rsp+120h+arg_10]
0x140010ed7  add     rsp, 0F0h
0x140010ede  pop     r15
0x140010ee0  pop     r14
0x140010ee2  pop     r13
0x140010ee4  pop     r12
0x140010ee6  pop     rdi
0x140010ee7  pop     rsi
0x140010ee8  pop     rbp
0x140010ee9  retn
0x140010eeb  test    dword ptr [r15+28h], 80000h
0x140010ef3  jz      loc_140010FA7
0x140010ef9  xor     eax, eax
0x140010efb  lea     r9, [rsi+0F0h]
0x140010f02  xorps   xmm0, xmm0
0x140010f05  mov     [rbp+57h+var_A8], rax
0x140010f09  movups  [rbp+57h+var_90], xmm0
0x140010f0d  mov     dword ptr [rbp+57h+var_90], 0
0x140010f14  lea     r8, [rsp+120h+var_D8]
0x140010f19  lea     ecx, [rax+1]
0x140010f1c  mov     dword ptr [rbp+57h+var_90+8], 0
0x140010f23  mov     rax, [rsp+120h+var_E0]
0x140010f28  lea     rdx, [rbp+57h+var_A0]
0x140010f2c  movups  [rbp+57h+var_A0], xmm0
0x140010f30  mov     byte ptr [rbp+57h+var_90+4], cl
0x140010f33  movups  [rbp+57h+var_C8], xmm0
0x140010f37  mov     dword ptr [rbp+57h+var_C8+8], ecx
0x140010f3a  movups  [rbp+57h+var_B8], xmm0
0x140010f3e  mov     qword ptr [rbp+57h+var_B8], rax
0x140010f42  xor     eax, eax
0x140010f44  mov     [rbp+57h+var_80], rax
0x140010f48  lea     rax, HUBMISC_PsmResetCompletePollingTimer
0x140010f4f  mov     qword ptr [rbp+57h+var_A0+8], rax
0x140010f53  mov     rax, cs:WdfFunctions_01015
0x140010f5a  movups  [rsp+120h+var_D8], xmm0
0x140010f5f  mov     dword ptr [rbp+57h+var_C8+0Ch], ecx
0x140010f62  mov     rcx, cs:WdfDriverGlobals
0x140010f69  mov     dword ptr [rsp+120h+var_D8], 38h ; '8'
0x140010f71  mov     dword ptr [rbp+57h+var_A0], 28h ; '('
0x140010f78  mov     rax, [rax+9F0h]
0x140010f7f  call    _guard_dispatch_icall
0x140010f84  test    eax, eax
0x140010f86  jns     short loc_140010FA7
0x140010f88  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140010f8f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140010f96  jz      loc_140011023
0x140010f9c  mov     r9d, 0Dh
0x140010fa2  jmp     loc_140010D97
0x140010fa7  mov     rbx, [rsi]
0x140010faa  mov     rax, cs:WdfFunctions_01015
0x140010fb1  mov     rcx, cs:WdfDriverGlobals
0x140010fb8  mov     rdx, [rbx+10h]
0x140010fbc  mov     rax, [rax+0F8h]
0x140010fc3  call    _guard_dispatch_icall
0x140010fc8  mov     rcx, [rbx+0F8h]
0x140010fcf  mov     rdx, rax
0x140010fd2  mov     rax, [rbx+1F8h]
0x140010fd9  mov     r8d, 1
0x140010fdf  call    _guard_dispatch_icall
0x140010fe4  mov     [rsi+4F0h], rax
0x140010feb  test    rax, rax
0x140010fee  jnz     loc_140010E85
0x140010ff4  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140010ffb  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140011002  jz      short loc_140011023
0x140011004  mov     rcx, [r12]
0x140011008  lea     r14, WPP_f6bc06825974302b29b4735b6d0d1d51_Traceguids
0x14001100f  lea     r9d, [rax+0Eh]
0x140011013  mov     [rsp+120h+var_100], r14
0x140011018  lea     r8d, [rax+4]
0x14001101c  mov     dl, 2
0x14001101e  call    WPP_RECORDER_SF_
0x140011023  mov     rdx, [rsp+120h+var_E0]
0x140011028  test    rdx, rdx
0x14001102b  jz      loc_140010EBE
0x140011031  mov     rax, cs:WdfFunctions_01015
0x140011038  mov     rcx, cs:WdfDriverGlobals
0x14001103f  mov     rax, [rax+680h]
0x140011046  call    _guard_dispatch_icall
0x14001104b  mov     [rsp+120h+var_E0], 0
0x140011054  jmp     loc_140010EBE
```
