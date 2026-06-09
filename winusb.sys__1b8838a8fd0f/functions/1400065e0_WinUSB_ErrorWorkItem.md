# WinUSB_ErrorWorkItem

- ea: `0x1400065e0`
- end: `0x140006ac3`
- name: `WinUSB_ErrorWorkItem`
- size: `1251`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x1400012b4`
- `0x1400062f4`
- `0x140006408`
- `0x1400065e0`
- `0x140010700`
- `0x14001d4b8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000679e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000679e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006817`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006817`

## string_xrefs

- `0x14000697c`: `onecore\drivers\wdm\usb\driver\winusb\sys\usbcom.c`

## pseudocode

```c
__int128 *__fastcall WinUSB_ErrorWorkItem(__int64 a1)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rdi
  int v4; // edx
  int v5; // eax
  int v6; // r8d
  char v7; // r15
  int v8; // eax
  int v9; // r8d
  KIRQL v10; // r9
  __int64 v11; // r8
  _QWORD *v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // rax
  __int32 v16; // esi
  int v17; // edx
  __int64 v18; // rdi
  __int128 *result; // rax
  __int64 v20; // rax
  __int64 v21; // r14
  __int64 v22; // rax
  unsigned int v23; // r14d
  int v24; // r8d
  __int64 v25; // r12
  int v26; // edx
  int v27; // r8d
  int v28; // [rsp+20h] [rbp-49h]
  __int128 v29; // [rsp+50h] [rbp-19h] BYREF
  _OWORD v30[6]; // [rsp+60h] [rbp-9h] BYREF

  v29 = 0;
  memset(v30, 0, 24);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      48,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids);
  v2 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                   WdfDriverGlobals,
                   a1,
                   off_140015090);
  v3 = v2 + 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v4 = *(unsigned __int8 *)(*v3 + 8LL);
    LOBYTE(v4) = 3;
    WPP_RECORDER_SF_dq(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      4,
      49,
      (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      *(_BYTE *)(*v3 + 8LL),
      *(_QWORD *)(*v3 + 160LL));
  }
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, _QWORD))(WdfFunctions_01015 + 2824))(
         WdfDriverGlobals,
         *(_QWORD *)(*v3 + 160LL),
         0,
         0);
  v7 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dqq(
        WPP_GLOBAL_Control->DeviceExtension,
        *(unsigned __int8 *)(*v3 + 8LL),
        v6,
        50,
        v28,
        *(_BYTE *)(*v3 + 8LL),
        *(_QWORD *)(*v3 + 160LL),
        *(_QWORD *)(*v2 + 8LL));
    v8 = WinUSB_ResetDevice(*v2);
    v7 = v8;
    if ( v8 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dqq(
        WPP_GLOBAL_Control->DeviceExtension,
        *(unsigned __int8 *)(*v3 + 8LL),
        v9,
        51,
        v28,
        *(_BYTE *)(*v3 + 8LL),
        *(_QWORD *)(*v3 + 160LL),
        *(_QWORD *)(*v2 + 8LL));
  }
  *((_QWORD *)&v29 + 1) = &v29;
  *(_QWORD *)&v29 = &v29;
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*v3 + 120LL));
  *(_DWORD *)(*v3 + 128LL) = 0;
  while ( 1 )
  {
    v11 = v2[1];
    v12 = (_QWORD *)(v11 + 136);
    v13 = *(_QWORD **)(v11 + 136);
    if ( v13 == (_QWORD *)(v11 + 136) )
      break;
    if ( (_QWORD *)v13[1] != v12
      || (v14 = *v13, *(_QWORD **)(*v13 + 8LL) != v13)
      || (*v12 = v14,
          *(_QWORD *)(v14 + 8) = v12,
          v15 = (_QWORD *)*((_QWORD *)&v29 + 1),
          **((__int128 ***)&v29 + 1) != &v29) )
    {
LABEL_33:
      __fastfail(3u);
    }
    v13[1] = *((_QWORD *)&v29 + 1);
    *v13 = &v29;
    *v15 = v13;
    *((_QWORD *)&v29 + 1) = v13;
  }
  v16 = 1;
  KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 120), v10);
  while ( 1 )
  {
    v18 = v29;
    result = &v29;
    if ( (__int128 *)v29 == &v29 )
      break;
    if ( *(__int128 **)(v29 + 8) != &v29 )
      goto LABEL_33;
    v20 = *(_QWORD *)v29;
    if ( *(_QWORD *)(*(_QWORD *)v29 + 8LL) != (_QWORD)v29 )
      goto LABEL_33;
    *(_QWORD *)&v29 = *(_QWORD *)v29;
    *(_QWORD *)(v20 + 8) = &v29;
    v21 = *(_QWORD *)(v2[1] + 80LL);
    if ( v21 )
    {
      if ( (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2048))(
             WdfDriverGlobals,
             *(_QWORD *)(v2[1] + 80LL)) == -1073741536 )
        v16 = _InterlockedExchange((volatile __int32 *)(v2[1] + 92LL), 1);
      else
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
          WdfDriverGlobals,
          v21,
          0,
          1451,
          "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\usbcom.c");
      if ( v16 == 1 )
      {
        *(_QWORD *)((char *)v30 + 12) = 0;
        DWORD1(v30[1]) = 0;
        *(_QWORD *)&v30[0] = 24;
        DWORD2(v30[0]) = 0;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _OWORD *))(WdfFunctions_01015 + 1992))(
          WdfDriverGlobals,
          *(_QWORD *)(v2[1] + 104LL),
          v30);
        *(_QWORD *)(v2[1] + 80LL) = 0;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v26,
            v27,
            53,
            (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
            *(_BYTE *)(v2[1] + 8LL),
            *(_DWORD *)(v18 - 4),
            *(_DWORD *)(v18 - 28),
            *(_DWORD *)(v18 - 32));
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
          WdfDriverGlobals,
          v21,
          *(unsigned int *)(v2[1] + 96LL),
          *(unsigned int *)(v18 - 32));
      }
    }
    else
    {
      v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(
              WdfDriverGlobals,
              v18 - 32);
      v23 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, v22);
      v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(
              WdfDriverGlobals,
              v18 - 32);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          *(unsigned __int8 *)(v2[1] + 8LL),
          v24,
          52,
          (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
          *(_BYTE *)(v2[1] + 8LL),
          *(_DWORD *)(v18 - 4),
          *(_DWORD *)(v18 - 28),
          *(_DWORD *)(v18 - 32));
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
        WdfDriverGlobals,
        v25,
        v23,
        *(unsigned int *)(v18 - 32));
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v17) = 5;
    return (__int128 *)WPP_RECORDER_SF_d(
                         WPP_GLOBAL_Control->DeviceExtension,
                         v17,
                         1,
                         54,
                         (__int64)WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
                         v7);
  }
  return result;
}

```

## disassembly

```asm
0x1400065e0  push    rbp
0x1400065e2  push    rbx
0x1400065e3  push    rsi
0x1400065e4  push    rdi
0x1400065e5  push    r12
0x1400065e7  push    r13
0x1400065e9  push    r14
0x1400065eb  push    r15
0x1400065ed  lea     rbp, [rsp-1Fh]
0x1400065f2  sub     rsp, 88h
0x1400065f9  xorps   xmm0, xmm0
0x1400065fc  xorps   xmm1, xmm1
0x1400065ff  xor     eax, eax
0x140006601  mov     rbx, rcx
0x140006604  movups  [rbp+57h+var_70], xmm0
0x140006608  mov     [rbp+57h+var_50], rax
0x14000660c  movups  [rbp+57h+var_60], xmm1
0x140006610  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006617  xor     r13d, r13d
0x14000661a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140006621  lea     rsi, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140006628  lea     r14d, [rax+1]
0x14000662c  jz      short loc_140006653
0x14000662e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006635  cmp     [rcx+48h], r13w
0x14000663a  jz      short loc_140006653
0x14000663c  mov     rcx, [rcx+40h]
0x140006640  lea     r9d, [rax+30h]
0x140006644  mov     r8d, r14d
0x140006647  mov     [rsp+0C0h+var_A0], rsi
0x14000664c  mov     dl, 5
0x14000664e  call    WPP_RECORDER_SF_
0x140006653  mov     rax, cs:WdfFunctions_01015
0x14000665a  mov     rdx, rbx
0x14000665d  mov     r8, cs:off_140015090
0x140006664  mov     rcx, cs:WdfDriverGlobals
0x14000666b  mov     rax, [rax+650h]
0x140006672  call    _guard_dispatch_icall
0x140006677  mov     rbx, rax
0x14000667a  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140006681  lea     rdi, [rax+8]
0x140006685  jz      short loc_1400066BF
0x140006687  mov     rcx, [rdi]
0x14000668a  mov     r9d, 31h ; '1'
0x140006690  movzx   edx, byte ptr [rcx+8]
0x140006694  lea     r8d, [r9-2Dh]
0x140006698  mov     rcx, [rcx+0A0h]
0x14000669f  mov     [rsp+0C0h+var_90], rcx
0x1400066a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066ab  mov     [rsp+0C0h+var_98], edx
0x1400066af  mov     dl, 3
0x1400066b1  mov     [rsp+0C0h+var_A0], rsi
0x1400066b6  mov     rcx, [rcx+40h]
0x1400066ba  call    WPP_RECORDER_SF_dq
0x1400066bf  mov     rdx, [rdi]
0x1400066c2  xor     r9d, r9d
0x1400066c5  mov     rax, cs:WdfFunctions_01015
0x1400066cc  xor     r8d, r8d
0x1400066cf  mov     rcx, cs:WdfDriverGlobals
0x1400066d6  mov     rdx, [rdx+0A0h]
0x1400066dd  mov     rax, [rax+0B08h]
0x1400066e4  call    _guard_dispatch_icall
0x1400066e9  mov     r15d, eax
0x1400066ec  test    eax, eax
0x1400066ee  jns     loc_140006787
0x1400066f4  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400066fb  jz      short loc_140006736
0x1400066fd  mov     rcx, [rdi]
0x140006700  mov     r9d, 32h ; '2'
0x140006706  mov     rax, [rbx]
0x140006709  movzx   edx, byte ptr [rcx+8]
0x14000670d  mov     rax, [rax+8]
0x140006711  mov     [rsp+0C0h+var_88], rax
0x140006716  mov     rax, [rcx+0A0h]
0x14000671d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006724  mov     [rsp+0C0h+var_90], rax
0x140006729  mov     [rsp+0C0h+var_98], edx
0x14000672d  mov     rcx, [rcx+40h]
0x140006731  call    WPP_RECORDER_SF_dqq
0x140006736  mov     rcx, [rbx]
0x140006739  call    WinUSB_ResetDevice
0x14000673e  mov     r15d, eax
0x140006741  test    eax, eax
0x140006743  jns     short loc_140006787
0x140006745  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000674c  jz      short loc_140006787
0x14000674e  mov     rcx, [rdi]
0x140006751  mov     r9d, 33h ; '3'
0x140006757  mov     rax, [rbx]
0x14000675a  movzx   edx, byte ptr [rcx+8]
0x14000675e  mov     rax, [rax+8]
0x140006762  mov     [rsp+0C0h+var_88], rax
0x140006767  mov     rax, [rcx+0A0h]
0x14000676e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006775  mov     [rsp+0C0h+var_90], rax
0x14000677a  mov     [rsp+0C0h+var_98], edx
0x14000677e  mov     rcx, [rcx+40h]
0x140006782  call    WPP_RECORDER_SF_dqq
0x140006787  lea     rax, [rbp+57h+var_70]
0x14000678b  mov     qword ptr [rbp+57h+var_70+8], rax
0x14000678f  lea     rax, [rbp+57h+var_70]
0x140006793  mov     qword ptr [rbp+57h+var_70], rax
0x140006797  mov     rcx, [rdi]
0x14000679a  add     rcx, 78h ; 'x'; SpinLock
0x14000679e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400067a5  nop     dword ptr [rax+rax+00h]
0x1400067aa  mov     rcx, [rdi]
0x1400067ad  mov     r9b, al
0x1400067b0  mov     [rcx+80h], r13d
0x1400067b7  mov     r8, [rbx+8]
0x1400067bb  lea     rdx, [r8+88h]
0x1400067c2  mov     rcx, [rdx]
0x1400067c5  cmp     rcx, rdx
0x1400067c8  jz      short loc_14000680D
0x1400067ca  cmp     [rcx+8], rdx
0x1400067ce  jnz     loc_140006A6A
0x1400067d4  mov     rax, [rcx]
0x1400067d7  cmp     [rax+8], rcx
0x1400067db  jnz     loc_140006A6A
0x1400067e1  mov     [rdx], rax
0x1400067e4  mov     [rax+8], rdx
0x1400067e8  lea     rdx, [rbp+57h+var_70]
0x1400067ec  mov     rax, qword ptr [rbp+57h+var_70+8]
0x1400067f0  cmp     [rax], rdx
0x1400067f3  jnz     loc_140006A6A
0x1400067f9  mov     [rcx+8], rax
0x1400067fd  lea     rdx, [rbp+57h+var_70]
0x140006801  mov     [rcx], rdx
0x140006804  mov     [rax], rcx
0x140006807  mov     qword ptr [rbp+57h+var_70+8], rcx
0x14000680b  jmp     short loc_1400067B7
0x14000680d  lea     rcx, [r8+78h]; SpinLock
0x140006811  mov     dl, r9b; NewIrql
0x140006814  mov     esi, r14d
0x140006817  call    cs:__imp_KeReleaseSpinLock
0x14000681e  nop     dword ptr [rax+rax+00h]
0x140006823  mov     rdi, qword ptr [rbp+57h+var_70]
0x140006827  lea     rax, [rbp+57h+var_70]
0x14000682b  cmp     rdi, rax
0x14000682e  jz      loc_140006A71
0x140006834  lea     rax, [rbp+57h+var_70]
0x140006838  cmp     [rdi+8], rax
0x14000683c  jnz     loc_140006A6A
0x140006842  mov     rax, [rdi]
0x140006845  cmp     [rax+8], rdi
0x140006849  jnz     loc_140006A6A
0x14000684f  mov     qword ptr [rbp+57h+var_70], rax
0x140006853  lea     rcx, [rbp+57h+var_70]
0x140006857  mov     [rax+8], rcx
0x14000685b  mov     rax, [rbx+8]
0x14000685f  mov     rcx, cs:WdfDriverGlobals
0x140006866  mov     r14, [rax+50h]
0x14000686a  mov     rax, cs:WdfFunctions_01015
0x140006871  test    r14, r14
0x140006874  jnz     loc_140006951
0x14000687a  mov     rax, [rax+660h]
0x140006881  lea     rdx, [rdi-20h]
0x140006885  call    _guard_dispatch_icall
0x14000688a  mov     rcx, cs:WdfFunctions_01015
0x140006891  mov     rdx, rax
0x140006894  mov     r8, [rcx+7F0h]
0x14000689b  mov     rcx, cs:WdfDriverGlobals
0x1400068a2  mov     rax, r8
0x1400068a5  call    _guard_dispatch_icall
0x1400068aa  mov     rcx, cs:WdfFunctions_01015
0x1400068b1  lea     rdx, [rdi-20h]
0x1400068b5  mov     r14d, eax
0x1400068b8  mov     rax, [rcx+660h]
0x1400068bf  mov     rcx, cs:WdfDriverGlobals
0x1400068c6  call    _guard_dispatch_icall
0x1400068cb  mov     r12, rax
0x1400068ce  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400068d5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400068dc  jz      short loc_140006921
0x1400068de  mov     rcx, [rbx+8]
0x1400068e2  lea     rax, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x1400068e9  mov     r9d, 34h ; '4'
0x1400068ef  movzx   edx, byte ptr [rcx+8]
0x1400068f3  mov     ecx, [rdi-20h]
0x1400068f6  mov     [rsp+0C0h+var_80], ecx
0x1400068fa  mov     ecx, [rdi-1Ch]
0x1400068fd  mov     dword ptr [rsp+0C0h+var_88], ecx
0x140006901  mov     ecx, [rdi-4]
0x140006904  mov     dword ptr [rsp+0C0h+var_90], ecx
0x140006908  mov     rcx, cs:WPP_GLOBAL_Control
0x14000690f  mov     [rsp+0C0h+var_98], edx
0x140006913  mov     [rsp+0C0h+var_A0], rax
0x140006918  mov     rcx, [rcx+40h]
0x14000691c  call    WPP_RECORDER_SF_dDdd
0x140006921  mov     rax, cs:WdfFunctions_01015
0x140006928  mov     r8d, r14d
0x14000692b  mov     r9d, [rdi-20h]
0x14000692f  mov     rdx, r12
0x140006932  mov     rcx, cs:WdfDriverGlobals
0x140006939  mov     rax, [rax+848h]
0x140006940  call    _guard_dispatch_icall
0x140006945  lea     r12, WPP_RECORDER_INITIALIZED
0x14000694c  jmp     loc_140006823
0x140006951  mov     rax, [rax+800h]
0x140006958  mov     rdx, r14
0x14000695b  call    _guard_dispatch_icall
0x140006960  cmp     eax, 0C0000120h
0x140006965  jnz     short loc_140006975
0x140006967  mov     rax, [rbx+8]
0x14000696b  mov     esi, 1
0x140006970  xchg    esi, [rax+5Ch]
0x140006973  jmp     short loc_1400069A7
0x140006975  mov     rax, cs:WdfFunctions_01015
0x14000697c  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\driver\\win"...
0x140006983  mov     [rsp+0C0h+var_A0], rcx
0x140006988  mov     r9d, 5ABh
0x14000698e  mov     rcx, cs:WdfDriverGlobals
0x140006995  xor     r8d, r8d
0x140006998  mov     rdx, r14
0x14000699b  mov     rax, [rax+670h]
0x1400069a2  call    _guard_dispatch_icall
0x1400069a7  cmp     esi, 1
0x1400069aa  jnz     loc_140006823
0x1400069b0  mov     rax, cs:WdfFunctions_01015
0x1400069b7  lea     r8, [rbp+57h+var_60]
0x1400069bb  mov     rcx, cs:WdfDriverGlobals
0x1400069c2  mov     qword ptr [rbp+57h+var_60+0Ch], r13
0x1400069c6  mov     dword ptr [rbp+57h+var_50+4], r13d
0x1400069ca  mov     qword ptr [rbp+57h+var_60], 18h
0x1400069d2  mov     dword ptr [rbp+57h+var_60+8], r13d
0x1400069d6  mov     rdx, [rbx+8]
0x1400069da  mov     rax, [rax+7C8h]
0x1400069e1  mov     rdx, [rdx+68h]
0x1400069e5  call    _guard_dispatch_icall
0x1400069ea  mov     rax, [rbx+8]
0x1400069ee  mov     [rax+50h], r13
0x1400069f2  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400069f9  jz      short loc_140006A3C
0x1400069fb  mov     rax, [rbx+8]
0x1400069ff  lea     r9d, [rsi+34h]
0x140006a03  movzx   ecx, byte ptr [rax+8]
0x140006a07  mov     eax, [rdi-20h]
0x140006a0a  mov     [rsp+0C0h+var_80], eax
0x140006a0e  mov     eax, [rdi-1Ch]
0x140006a11  mov     dword ptr [rsp+0C0h+var_88], eax
0x140006a15  mov     eax, [rdi-4]
0x140006a18  mov     dword ptr [rsp+0C0h+var_90], eax
0x140006a1c  lea     rax, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140006a23  mov     [rsp+0C0h+var_98], ecx
0x140006a27  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a2e  mov     [rsp+0C0h+var_A0], rax
0x140006a33  mov     rcx, [rcx+40h]
0x140006a37  call    WPP_RECORDER_SF_dDdd
0x140006a3c  mov     r8, [rbx+8]
0x140006a40  mov     rdx, r14
0x140006a43  mov     rax, cs:WdfFunctions_01015
0x140006a4a  mov     r9d, [rdi-20h]
0x140006a4e  mov     rcx, cs:WdfDriverGlobals
0x140006a55  mov     r8d, [r8+60h]
0x140006a59  mov     rax, [rax+848h]
0x140006a60  call    _guard_dispatch_icall
0x140006a65  jmp     loc_140006823
0x140006a6a  mov     ecx, 3
0x140006a6f  int     29h; Win8: RtlFailFast(ecx)
0x140006a71  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140006a78  jz      short loc_140006AAE
0x140006a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a81  cmp     [rcx+48h], r13w
0x140006a86  jz      short loc_140006AAE
0x140006a88  mov     rcx, [rcx+40h]
0x140006a8c  lea     rax, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x140006a93  mov     r9d, 36h ; '6'
0x140006a99  mov     [rsp+0C0h+var_98], r15d
0x140006a9e  mov     dl, 5
0x140006aa0  mov     [rsp+0C0h+var_A0], rax
0x140006aa5  lea     r8d, [r9-35h]
0x140006aa9  call    WPP_RECORDER_SF_d
0x140006aae  add     rsp, 88h
0x140006ab5  pop     r15
0x140006ab7  pop     r14
0x140006ab9  pop     r13
0x140006abb  pop     r12
0x140006abd  pop     rdi
0x140006abe  pop     rsi
0x140006abf  pop     rbx
0x140006ac0  pop     rbp
0x140006ac1  retn
```
