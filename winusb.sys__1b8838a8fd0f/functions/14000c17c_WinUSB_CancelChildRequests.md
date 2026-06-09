# WinUSB_CancelChildRequests

- ea: `0x14000c17c`
- end: `0x14000c4f8`
- name: `WinUSB_CancelChildRequests`
- size: `892`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000e080`
- `0x14000eff0`

## callees

- `0x140001020`
- `0x1400013d0`
- `0x14000c17c`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c250`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c250`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c26d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c3bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c26d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c3bb`

## pseudocode

```c
char __fastcall WinUSB_CancelChildRequests(__int64 a1)
{
  char v2; // di
  __int64 v3; // rbx
  __int64 v4; // r14
  KSPIN_LOCK *v5; // r15
  KIRQL v6; // al
  KIRQL v7; // r12
  _QWORD **v9; // rsi
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  _QWORD *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int128 v21; // [rsp+30h] [rbp-10h] BYREF

  v21 = 0;
  v2 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        5u,
        1u,
        0x37u,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        4u,
        3u,
        0x38u,
        (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
        a1,
        v21);
  }
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400150C0);
  v4 = *(_QWORD *)v3;
  *((_QWORD *)&v21 + 1) = &v21;
  *(_QWORD *)&v21 = &v21;
  v5 = (KSPIN_LOCK *)(v4 + 232);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 232));
  v7 = v6;
  if ( *(_BYTE *)(v3 + 137) == 1 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 232), v6);
  }
  else
  {
    v2 = 1;
    *(_BYTE *)(v3 + 136) = 1;
    if ( *(_QWORD *)(v4 + 224) == a1 )
      *(_QWORD *)(v4 + 224) = 0;
    v9 = (_QWORD **)(v3 + 120);
    while ( 1 )
    {
      v10 = *v9;
      if ( *v9 == v9 )
        break;
      if ( (_QWORD **)v10[1] != v9 )
        goto LABEL_29;
      v11 = (_QWORD *)*v10;
      if ( *(_QWORD **)(*v10 + 8LL) != v10 )
        goto LABEL_29;
      *v9 = v11;
      v12 = v10 - 6;
      v11[1] = v9;
      ++*(_DWORD *)(v3 + 140);
      *((_BYTE *)v10 + 76) = 1;
      v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *))(WdfFunctions_01015 + 1632))(
              WdfDriverGlobals,
              v10 - 6);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1640))(
        WdfDriverGlobals,
        v13,
        0,
        1168,
        "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\isoch.c");
      v14 = v21;
      if ( *(__int128 **)(v21 + 8) != &v21 )
LABEL_29:
        __fastfail(3u);
      v2 = 0;
      v12[8] = v21;
      v12[9] = &v21;
      *(_QWORD *)(v14 + 8) = v12 + 8;
      *(_QWORD *)&v21 = v12 + 8;
    }
    if ( v2 == 1 )
      *(_BYTE *)(v3 + 137) = 1;
    KeReleaseSpinLock(v5, v7);
    while ( 1 )
    {
      v15 = v21;
      if ( (__int128 *)v21 == &v21 )
        break;
      if ( *(__int128 **)(v21 + 8) != &v21 )
        goto LABEL_29;
      v16 = *(_QWORD *)v21;
      if ( *(_QWORD *)(*(_QWORD *)v21 + 8LL) != (_QWORD)v21 )
        goto LABEL_29;
      *(_QWORD *)&v21 = *(_QWORD *)v21;
      *(_QWORD *)(v16 + 8) = &v21;
      v17 = v15 - 64;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(
                WdfDriverGlobals,
                v15 - 64);
        WPP_RECORDER_SF_q(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          4u,
          3u,
          0x39u,
          (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
          v18);
      }
      v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v17);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2064))(WdfDriverGlobals, v19);
      v20 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v17);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, const char *))(WdfFunctions_01015 + 1648))(
        WdfDriverGlobals,
        v20,
        0,
        1209,
        "onecore\\drivers\\wdm\\usb\\driver\\winusb\\sys\\isoch.c");
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x3Au,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x14000c17c  push    rbp
0x14000c17e  push    rbx
0x14000c17f  push    rsi
0x14000c180  push    rdi
0x14000c181  push    r12
0x14000c183  push    r14
0x14000c185  push    r15
0x14000c187  mov     rbp, rsp
0x14000c18a  sub     rsp, 40h
0x14000c18e  xorps   xmm0, xmm0
0x14000c191  mov     rsi, rcx
0x14000c194  movups  [rbp+var_10], xmm0
0x14000c198  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000c19f  xor     edi, edi
0x14000c1a1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000c1a8  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c1af  jz      short loc_14000C20C
0x14000c1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c1b8  cmp     [rcx+48h], di
0x14000c1bc  jz      short loc_14000C1DD
0x14000c1be  mov     rcx, [rcx+40h]
0x14000c1c2  lea     r9d, [rdi+37h]
0x14000c1c6  lea     r8d, [rdi+1]
0x14000c1ca  mov     [rsp+40h+var_20], rax
0x14000c1cf  mov     dl, 5
0x14000c1d1  call    WPP_RECORDER_SF_
0x14000c1d6  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c1dd  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14000c1e4  jz      short loc_14000C20C
0x14000c1e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c1ed  mov     r9d, 38h ; '8'
0x14000c1f3  mov     [rsp+40h+var_18], rsi
0x14000c1f8  mov     dl, 4
0x14000c1fa  mov     [rsp+40h+var_20], rax
0x14000c1ff  mov     rcx, [rcx+40h]
0x14000c203  lea     r8d, [r9-35h]
0x14000c207  call    WPP_RECORDER_SF_q
0x14000c20c  mov     rax, cs:WdfFunctions_01015
0x14000c213  mov     rdx, rsi
0x14000c216  mov     r8, cs:off_1400150C0
0x14000c21d  mov     rcx, cs:WdfDriverGlobals
0x14000c224  mov     rax, [rax+650h]
0x14000c22b  call    _guard_dispatch_icall
0x14000c230  mov     rbx, rax
0x14000c233  mov     r14, [rax]
0x14000c236  lea     rax, [rbp+var_10]
0x14000c23a  mov     qword ptr [rbp+var_10+8], rax
0x14000c23e  lea     rax, [rbp+var_10]
0x14000c242  mov     qword ptr [rbp+var_10], rax
0x14000c246  lea     r15, [r14+0E8h]
0x14000c24d  mov     rcx, r15; SpinLock
0x14000c250  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c257  nop     dword ptr [rax+rax+00h]
0x14000c25c  cmp     byte ptr [rbx+89h], 1
0x14000c263  mov     r12b, al
0x14000c266  jnz     short loc_14000C2CA
0x14000c268  mov     dl, al; NewIrql
0x14000c26a  mov     rcx, r15; SpinLock
0x14000c26d  call    cs:__imp_KeReleaseSpinLock
0x14000c274  nop     dword ptr [rax+rax+00h]
0x14000c279  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000c280  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c287  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14000c28e  jz      short loc_14000C2B7
0x14000c290  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c297  xor     eax, eax
0x14000c299  cmp     [rcx+48h], ax
0x14000c29d  jz      short loc_14000C2B7
0x14000c29f  mov     rcx, [rcx+40h]
0x14000c2a3  lea     r9d, [rax+3Ah]
0x14000c2a7  lea     r8d, [rax+1]
0x14000c2ab  mov     [rsp+40h+var_20], r14
0x14000c2b0  mov     dl, 5
0x14000c2b2  call    WPP_RECORDER_SF_
0x14000c2b7  mov     al, dil
0x14000c2ba  add     rsp, 40h
0x14000c2be  pop     r15
0x14000c2c0  pop     r14
0x14000c2c2  pop     r12
0x14000c2c4  pop     rdi
0x14000c2c5  pop     rsi
0x14000c2c6  pop     rbx
0x14000c2c7  pop     rbp
0x14000c2c8  retn
0x14000c2ca  mov     dil, 1
0x14000c2cd  mov     [rbx+88h], dil
0x14000c2d4  cmp     [r14+0E0h], rsi
0x14000c2db  jnz     short loc_14000C2E8
0x14000c2dd  mov     qword ptr [r14+0E0h], 0
0x14000c2e8  lea     rsi, [rbx+78h]
0x14000c2ec  mov     rax, [rsi]
0x14000c2ef  cmp     rax, rsi
0x14000c2f2  jz      loc_14000C3A8
0x14000c2f8  cmp     [rax+8], rsi
0x14000c2fc  jnz     loc_14000C4F1
0x14000c302  mov     rcx, [rax]
0x14000c305  cmp     [rcx+8], rax
0x14000c309  jnz     loc_14000C4F1
0x14000c30f  mov     [rsi], rcx
0x14000c312  lea     r14, [rax-30h]
0x14000c316  mov     [rcx+8], rsi
0x14000c31a  mov     rdx, r14
0x14000c31d  inc     dword ptr [rbx+8Ch]
0x14000c323  mov     byte ptr [r14+7Ch], 1
0x14000c328  mov     rax, cs:WdfFunctions_01015
0x14000c32f  mov     rcx, cs:WdfDriverGlobals
0x14000c336  mov     rax, [rax+660h]
0x14000c33d  call    _guard_dispatch_icall
0x14000c342  mov     rcx, cs:WdfFunctions_01015
0x14000c349  mov     rdx, rax
0x14000c34c  mov     r9d, 490h
0x14000c352  xor     r8d, r8d
0x14000c355  mov     r10, [rcx+668h]
0x14000c35c  lea     rcx, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\driver\\win"...
0x14000c363  mov     [rsp+40h+var_20], rcx
0x14000c368  mov     rax, r10
0x14000c36b  mov     rcx, cs:WdfDriverGlobals
0x14000c372  call    _guard_dispatch_icall
0x14000c377  mov     rcx, qword ptr [rbp+var_10]
0x14000c37b  lea     rax, [rbp+var_10]
0x14000c37f  cmp     [rcx+8], rax
0x14000c383  jnz     loc_14000C4F1
0x14000c389  lea     rax, [r14+40h]
0x14000c38d  xor     dil, dil
0x14000c390  mov     [rax], rcx
0x14000c393  lea     rdx, [rbp+var_10]
0x14000c397  mov     [rax+8], rdx
0x14000c39b  mov     [rcx+8], rax
0x14000c39f  mov     qword ptr [rbp+var_10], rax
0x14000c3a3  jmp     loc_14000C2EC
0x14000c3a8  cmp     dil, 1
0x14000c3ac  jnz     short loc_14000C3B5
0x14000c3ae  mov     [rbx+89h], dil
0x14000c3b5  mov     dl, r12b; NewIrql
0x14000c3b8  mov     rcx, r15; SpinLock
0x14000c3bb  call    cs:__imp_KeReleaseSpinLock
0x14000c3c2  nop     dword ptr [rax+rax+00h]
0x14000c3c7  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000c3ce  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000c3d5  mov     rax, qword ptr [rbp+var_10]
0x14000c3d9  lea     rcx, [rbp+var_10]
0x14000c3dd  cmp     rax, rcx
0x14000c3e0  jz      loc_14000C287
0x14000c3e6  lea     rcx, [rbp+var_10]
0x14000c3ea  cmp     [rax+8], rcx
0x14000c3ee  jnz     loc_14000C4F1
0x14000c3f4  mov     rcx, [rax]
0x14000c3f7  cmp     [rcx+8], rax
0x14000c3fb  jnz     loc_14000C4F1
0x14000c401  lea     rdx, [rbp+var_10]
0x14000c405  mov     qword ptr [rbp+var_10], rcx
0x14000c409  mov     [rcx+8], rdx
0x14000c40d  lea     rbx, [rax-40h]
0x14000c411  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14000c418  jz      short loc_14000C45D
0x14000c41a  mov     rax, cs:WdfFunctions_01015
0x14000c421  mov     rdx, rbx
0x14000c424  mov     rcx, cs:WdfDriverGlobals
0x14000c42b  mov     rax, [rax+660h]
0x14000c432  call    _guard_dispatch_icall
0x14000c437  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c43e  mov     r9d, 39h ; '9'
0x14000c444  mov     [rsp+40h+var_18], rax
0x14000c449  mov     dl, 4
0x14000c44b  mov     [rsp+40h+var_20], r14
0x14000c450  mov     rcx, [rcx+40h]
0x14000c454  lea     r8d, [r9-36h]
0x14000c458  call    WPP_RECORDER_SF_q
0x14000c45d  mov     rax, cs:WdfFunctions_01015
0x14000c464  mov     rdx, rbx
0x14000c467  mov     rcx, cs:WdfDriverGlobals
0x14000c46e  mov     rax, [rax+660h]
0x14000c475  call    _guard_dispatch_icall
0x14000c47a  mov     rcx, cs:WdfFunctions_01015
0x14000c481  mov     rdx, rax
0x14000c484  mov     r8, [rcx+810h]
0x14000c48b  mov     rcx, cs:WdfDriverGlobals
0x14000c492  mov     rax, r8
0x14000c495  call    _guard_dispatch_icall
0x14000c49a  mov     rax, cs:WdfFunctions_01015
0x14000c4a1  mov     rdx, rbx
0x14000c4a4  mov     rcx, cs:WdfDriverGlobals
0x14000c4ab  mov     rax, [rax+660h]
0x14000c4b2  call    _guard_dispatch_icall
0x14000c4b7  mov     rcx, cs:WdfFunctions_01015
0x14000c4be  mov     rdx, rax
0x14000c4c1  mov     r9d, 4B9h
0x14000c4c7  xor     r8d, r8d
0x14000c4ca  mov     r10, [rcx+670h]
0x14000c4d1  lea     rcx, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\driver\\win"...
0x14000c4d8  mov     [rsp+40h+var_20], rcx
0x14000c4dd  mov     rax, r10
0x14000c4e0  mov     rcx, cs:WdfDriverGlobals
0x14000c4e7  call    _guard_dispatch_icall
0x14000c4ec  jmp     loc_14000C3D5
0x14000c4f1  mov     ecx, 3
0x14000c4f6  int     29h; Win8: RtlFailFast(ecx)
```
