# WinUSB_SubmitChildIsochTransfer

- ea: `0x14000ea0c`
- end: `0x14000efea`
- name: `WinUSB_SubmitChildIsochTransfer`
- size: `1502`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000eff0`

## callees

- `0x140001020`
- `0x1400013d0`
- `0x1400014bc`
- `0x1400015d8`
- `0x14000ced8`
- `0x14000d26c`
- `0x14000ea0c`
- `0x14000fbe8`
- `0x1400106c0`
- `0x140010700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000eaba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ed97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000edf3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000eaba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ed97`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000edf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eadb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eb46`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ed18`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ede4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ee3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eec4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ef6c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eadb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eb46`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ed18`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ede4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ee3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eec4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ef6c`

## pseudocode

```c
_UNKNOWN **__fastcall WinUSB_SubmitChildIsochTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rbx
  KIRQL v6; // al
  KIRQL v7; // r15
  _UNKNOWN **result; // rax
  PLIST_ENTRY FreeChildIsochRequest; // rax
  PLIST_ENTRY v10; // r12
  __int64 v11; // r14
  int v12; // ebp
  __int64 v13; // rdx
  unsigned int v14; // r11d
  int v15; // ebp
  int v16; // r15d
  int v17; // r10d
  unsigned int v18; // r8d
  unsigned int v19; // edx
  int v20; // eax
  int v21; // eax
  _QWORD *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r15
  int v25; // edx
  __int64 v26; // rdx
  _QWORD *v27; // rcx
  KIRQL v28; // al
  int v29; // edx
  KIRQL v30; // r15
  int v32; // edx
  int v33; // eax
  int v34; // edx
  KIRQL NewIrql; // [rsp+40h] [rbp-78h]
  KIRQL NewIrqla; // [rsp+40h] [rbp-78h]
  int v38; // [rsp+48h] [rbp-70h]
  int v39; // [rsp+50h] [rbp-68h]
  _BYTE v40[20]; // [rsp+58h] [rbp-60h] BYREF

  memset(v40, 0, sizeof(v40));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x70u,
      (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400150C0);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 232));
  v7 = v6;
  NewIrql = v6;
  if ( *(_BYTE *)(v5 + 136) != 1 )
  {
    FreeChildIsochRequest = WinUSB_GetFreeChildIsochRequest(a1);
    v10 = FreeChildIsochRequest;
    if ( !FreeChildIsochRequest )
    {
      v11 = 0;
      v12 = -1073741670;
      KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 232), v7);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          3,
          114,
          (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
          a1);
LABEL_41:
      v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 232));
      *(_QWORD *)(a3 + 224) = 0;
      v30 = v28;
      if ( v11 && *(_BYTE *)(v11 + 124) == 1 )
      {
        if ( (*(_DWORD *)(v5 + 140))-- == 1 )
        {
          *(_WORD *)(v5 + 136) = 257;
          KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 232), v28);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v32) = 4;
            WPP_RECORDER_SF_qq(
              WPP_GLOBAL_Control->DeviceExtension,
              v32,
              3,
              116,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              a1,
              (char)v10);
          }
LABEL_46:
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
            WdfDriverGlobals,
            a1,
            (unsigned int)v12);
          goto LABEL_53;
        }
      }
      else
      {
        v33 = *(_DWORD *)(v5 + 56);
        if ( v33 == *(_DWORD *)(v5 + 60) )
        {
          *(_BYTE *)(v5 + 137) = 1;
          KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 232), v30);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v34) = 4;
            WPP_RECORDER_SF_qd(
              WPP_GLOBAL_Control->DeviceExtension,
              v34,
              3,
              117,
              (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
              a1,
              v12);
          }
          goto LABEL_46;
        }
        *(_DWORD *)(v5 + 52) = v33;
        *(_DWORD *)(v5 + 40) = v12;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v29) = 4;
          WPP_RECORDER_SF_qd(
            WPP_GLOBAL_Control->DeviceExtension,
            v29,
            3,
            118,
            (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
            a1,
            v12);
        }
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 232), v30);
      goto LABEL_53;
    }
    v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, PLIST_ENTRY, __int64 *))(WdfFunctions_01015 + 1616))(
            WdfDriverGlobals,
            FreeChildIsochRequest,
            off_140015068);
    *(_QWORD *)(v11 + 96) = a1;
    *(_QWORD *)(v11 + 24) = *(_QWORD *)(v5 + 8);
    v13 = *(_QWORD *)(a3 + 160);
    *(_OWORD *)&v40[4] = 0;
    *(_DWORD *)v40 = 20;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _BYTE *))(WdfFunctions_01015 + 2728))(
      WdfDriverGlobals,
      v13,
      v40);
    v14 = *(_DWORD *)(v5 + 68);
    v15 = *(_DWORD *)(v5 + 64);
    v16 = *(_DWORD *)(v5 + 44) + v14 * *(_DWORD *)(v5 + 56);
    switch ( v40[9] )
    {
      case 1:
        v17 = 1;
        break;
      case 2:
        v17 = 2;
        break;
      case 3:
        v17 = 4;
        break;
      default:
        v17 = 8;
        break;
    }
    if ( (*(_DWORD *)(a2 + 32) & 4) != 0 )
    {
      v18 = ((unsigned int)(v17 * v15) >> 3) + 1;
      if ( (((_BYTE)v17 * (_BYTE)v15) & 7) == 0 )
        v18 = (unsigned int)(v17 * v15) >> 3;
    }
    else
    {
      v18 = *(_DWORD *)(v5 + 64);
    }
    if ( *(_DWORD *)(v5 + 56) == *(_DWORD *)(v5 + 52) - 1 )
    {
      v19 = *(_DWORD *)(v5 + 48) % v14;
      if ( v19 )
      {
        v14 = *(_DWORD *)(v5 + 48) % v14;
        v15 = v19 / *(_DWORD *)(a3 + 168) + 1;
        if ( !(v19 % *(_DWORD *)(a3 + 168)) )
          v15 = v19 / *(_DWORD *)(a3 + 168);
        if ( (*(_DWORD *)(a2 + 32) & 4) != 0 )
        {
          v18 = ((unsigned int)(v17 * v15) >> 3) + 1;
          if ( (((_BYTE)v17 * (_BYTE)v15) & 7) == 0 )
            v18 = (unsigned int)(v17 * v15) >> 3;
        }
        else
        {
          v18 = v15;
        }
      }
      *(_QWORD *)(a3 + 224) = 0;
    }
    v20 = *(_DWORD *)(v5 + 56);
    *(_DWORD *)(v11 + 104) = v20;
    v39 = v20;
    v21 = *(_DWORD *)(v5 + 72);
    *(_DWORD *)(v11 + 108) = v16;
    *(_DWORD *)(v11 + 120) = v14;
    *(_QWORD *)v11 = a3;
    *(_DWORD *)(v11 + 40) = v18;
    v38 = v21;
    v22 = (_QWORD *)(v5 + 120);
    v23 = *(_QWORD *)(v5 + 120);
    if ( *(_QWORD *)(v23 + 8) == v5 + 120 )
    {
      v24 = v11 + 48;
      *(_QWORD *)(v11 + 48) = v23;
      *(_QWORD *)(v11 + 56) = v22;
      *(_QWORD *)(v23 + 8) = v11 + 48;
      *v22 = v11 + 48;
      ++*(_DWORD *)(v5 + 56);
      KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 232), NewIrql);
      v12 = WinUSB_SubmitIsochTransfer(
              (_DWORD)v10,
              v15,
              v38 + 50 * v39,
              *(_QWORD *)(v11 + 8),
              (__int64)WinUSB_ChildIsochTransferComplete);
      if ( v12 >= 0 )
        goto LABEL_53;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v25) = 4;
        WPP_RECORDER_SF_qd(
          WPP_GLOBAL_Control->DeviceExtension,
          v25,
          3,
          115,
          (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
          (char)v10,
          v12);
      }
      NewIrqla = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 232));
      if ( *(_BYTE *)(v11 + 124) )
        goto LABEL_40;
      v26 = *(_QWORD *)v24;
      if ( *(_QWORD *)(*(_QWORD *)v24 + 8LL) == v24 )
      {
        v27 = *(_QWORD **)(v11 + 56);
        if ( *v27 == v24 )
        {
          *v27 = v26;
          *(_QWORD *)(v26 + 8) = v27;
LABEL_40:
          --*(_DWORD *)(v5 + 56);
          WinUSB_FreeChildIsochRequest(a1, v10);
          KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 232), NewIrqla);
          goto LABEL_41;
        }
      }
    }
    __fastfail(3u);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 232), v6);
  result = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return result;
  WPP_RECORDER_SF_q(
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    3,
    113,
    (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids,
    a1);
LABEL_53:
  result = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      return (_UNKNOWN **)WPP_RECORDER_SF_(
                            (__int64)WPP_GLOBAL_Control->DeviceExtension,
                            5u,
                            1u,
                            0x77u,
                            (__int64)WPP_0eec754a616436344c523d073d150c9e_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000ea0c  mov     [rsp+arg_8], rbx
0x14000ea11  push    rbp
0x14000ea12  push    rsi
0x14000ea13  push    rdi
0x14000ea14  push    r12
0x14000ea16  push    r13
0x14000ea18  push    r14
0x14000ea1a  push    r15
0x14000ea1c  sub     rsp, 80h
0x14000ea23  mov     rax, cs:__security_cookie
0x14000ea2a  xor     rax, rsp
0x14000ea2d  mov     [rsp+0B8h+var_48], rax
0x14000ea32  xorps   xmm0, xmm0
0x14000ea35  mov     [rsp+0B8h+var_70], rdx
0x14000ea3a  xor     eax, eax
0x14000ea3c  mov     r13, r8
0x14000ea3f  movups  [rsp+0B8h+var_60], xmm0
0x14000ea44  mov     [rsp+0B8h+var_50], eax
0x14000ea48  mov     rdi, rcx
0x14000ea4b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ea52  xor     ebp, ebp
0x14000ea54  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ea5b  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000ea62  jz      short loc_14000EA89
0x14000ea64  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea6b  cmp     [rcx+48h], bp
0x14000ea6f  jz      short loc_14000EA89
0x14000ea71  mov     rcx, [rcx+40h]
0x14000ea75  lea     r9d, [rbp+70h]
0x14000ea79  lea     r8d, [rbp+1]
0x14000ea7d  mov     [rsp+0B8h+var_98], r14
0x14000ea82  mov     dl, 5
0x14000ea84  call    WPP_RECORDER_SF_
0x14000ea89  mov     rax, cs:WdfFunctions_01015
0x14000ea90  mov     rdx, rdi
0x14000ea93  mov     r8, cs:off_1400150C0
0x14000ea9a  mov     rcx, cs:WdfDriverGlobals
0x14000eaa1  mov     rax, [rax+650h]
0x14000eaa8  call    _guard_dispatch_icall
0x14000eaad  lea     rsi, [r13+0E8h]
0x14000eab4  mov     rbx, rax
0x14000eab7  mov     rcx, rsi; SpinLock
0x14000eaba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000eac1  nop     dword ptr [rax+rax+00h]
0x14000eac6  cmp     byte ptr [rbx+88h], 1
0x14000eacd  mov     r15b, al
0x14000ead0  mov     [rsp+0B8h+NewIrql], al
0x14000ead4  jnz     short loc_14000EB28
0x14000ead6  mov     dl, al; NewIrql
0x14000ead8  mov     rcx, rsi; SpinLock
0x14000eadb  call    cs:__imp_KeReleaseSpinLock
0x14000eae2  nop     dword ptr [rax+rax+00h]
0x14000eae7  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000eaee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000eaf5  jz      loc_14000EFBA
0x14000eafb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb02  mov     r9d, 71h ; 'q'
0x14000eb08  mov     [rsp+0B8h+var_90], rdi
0x14000eb0d  mov     [rsp+0B8h+var_98], r14
0x14000eb12  mov     rcx, [rcx+40h]
0x14000eb16  lea     edx, [r9-6Fh]
0x14000eb1a  lea     r8d, [r9-6Eh]
0x14000eb1e  call    WPP_RECORDER_SF_q
0x14000eb23  jmp     loc_14000EF83
0x14000eb28  mov     rcx, rdi
0x14000eb2b  call    WinUSB_GetFreeChildIsochRequest
0x14000eb30  mov     r12, rax
0x14000eb33  test    rax, rax
0x14000eb36  jnz     short loc_14000EB9B
0x14000eb38  mov     r14, rbp
0x14000eb3b  mov     dl, r15b; NewIrql
0x14000eb3e  mov     rcx, rsi; SpinLock
0x14000eb41  mov     ebp, 0C000009Ah
0x14000eb46  call    cs:__imp_KeReleaseSpinLock
0x14000eb4d  nop     dword ptr [rax+rax+00h]
0x14000eb52  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000eb59  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000eb60  jz      loc_14000EDF0
0x14000eb66  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb6d  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000eb74  lea     r9d, [r12+72h]
0x14000eb79  mov     [rsp+0B8h+var_90], rdi
0x14000eb7e  lea     edx, [r12+2]
0x14000eb83  mov     [rsp+0B8h+var_98], rax
0x14000eb88  lea     r8d, [r12+3]
0x14000eb8d  mov     rcx, [rcx+40h]
0x14000eb91  call    WPP_RECORDER_SF_q
0x14000eb96  jmp     loc_14000EDF0
0x14000eb9b  mov     rax, cs:WdfFunctions_01015
0x14000eba2  mov     rdx, r12
0x14000eba5  mov     r8, cs:off_140015068
0x14000ebac  mov     rcx, cs:WdfDriverGlobals
0x14000ebb3  mov     rax, [rax+650h]
0x14000ebba  call    _guard_dispatch_icall
0x14000ebbf  xorps   xmm0, xmm0
0x14000ebc2  lea     r8, [rsp+0B8h+var_60]
0x14000ebc7  mov     r14, rax
0x14000ebca  mov     [rax+60h], rdi
0x14000ebce  mov     rcx, [rbx+8]
0x14000ebd2  mov     [rax+18h], rcx
0x14000ebd6  mov     rcx, cs:WdfFunctions_01015
0x14000ebdd  mov     rdx, [r13+0A0h]
0x14000ebe4  movdqu  [rsp+0B8h+var_60+4], xmm0
0x14000ebea  mov     dword ptr [rsp+0B8h+var_60], 14h
0x14000ebf2  mov     rax, [rcx+0AA8h]
0x14000ebf9  mov     rcx, cs:WdfDriverGlobals
0x14000ec00  call    _guard_dispatch_icall
0x14000ec05  mov     edx, [rbx+38h]
0x14000ec08  mov     r15d, edx
0x14000ec0b  mov     r11d, [rbx+44h]
0x14000ec0f  movzx   ecx, byte ptr [rsp+0B8h+var_60+9]
0x14000ec14  mov     ebp, [rbx+40h]
0x14000ec17  imul    r15d, r11d
0x14000ec1b  add     r15d, [rbx+2Ch]
0x14000ec1f  sub     ecx, 1
0x14000ec22  jz      short loc_14000EC46
0x14000ec24  sub     ecx, 1
0x14000ec27  jz      short loc_14000EC3E
0x14000ec29  sub     ecx, 1
0x14000ec2c  jz      short loc_14000EC36
0x14000ec2e  mov     r10d, 8
0x14000ec34  jmp     short loc_14000EC4C
0x14000ec36  mov     r10d, 4
0x14000ec3c  jmp     short loc_14000EC4C
0x14000ec3e  mov     r10d, 2
0x14000ec44  jmp     short loc_14000EC4C
0x14000ec46  mov     r10d, 1
0x14000ec4c  mov     r9, [rsp+0B8h+var_70]
0x14000ec51  mov     r9d, [r9+20h]
0x14000ec55  and     r9d, 4
0x14000ec59  jz      short loc_14000EC72
0x14000ec5b  mov     eax, ebp
0x14000ec5d  imul    eax, r10d
0x14000ec61  mov     ecx, eax
0x14000ec63  shr     ecx, 3
0x14000ec66  test    al, 7
0x14000ec68  lea     r8d, [rcx+1]
0x14000ec6c  cmovz   r8d, ecx
0x14000ec70  jmp     short loc_14000EC75
0x14000ec72  mov     r8d, ebp
0x14000ec75  mov     eax, [rbx+34h]
0x14000ec78  dec     eax
0x14000ec7a  cmp     edx, eax
0x14000ec7c  jnz     short loc_14000ECCA
0x14000ec7e  mov     eax, [rbx+30h]
0x14000ec81  xor     edx, edx
0x14000ec83  div     r11d
0x14000ec86  mov     eax, edx
0x14000ec88  test    edx, edx
0x14000ec8a  jz      short loc_14000ECBF
0x14000ec8c  mov     r11d, edx
0x14000ec8f  xor     edx, edx
0x14000ec91  div     dword ptr [r13+0A8h]
0x14000ec98  test    edx, edx
0x14000ec9a  lea     ebp, [rax+1]
0x14000ec9d  cmovz   ebp, eax
0x14000eca0  test    r9d, r9d
0x14000eca3  jz      short loc_14000ECBC
0x14000eca5  mov     eax, ebp
0x14000eca7  imul    eax, r10d
0x14000ecab  mov     ecx, eax
0x14000ecad  shr     ecx, 3
0x14000ecb0  test    al, 7
0x14000ecb2  lea     r8d, [rcx+1]
0x14000ecb6  cmovz   r8d, ecx
0x14000ecba  jmp     short loc_14000ECBF
0x14000ecbc  mov     r8d, ebp
0x14000ecbf  mov     qword ptr [r13+0E0h], 0
0x14000ecca  mov     eax, [rbx+38h]
0x14000eccd  mov     [r14+68h], eax
0x14000ecd1  mov     [rsp+0B8h+var_68], eax
0x14000ecd5  mov     eax, [rbx+48h]
0x14000ecd8  mov     [r14+6Ch], r15d
0x14000ecdc  mov     [r14+78h], r11d
0x14000ece0  mov     [r14], r13
0x14000ece3  mov     [r14+28h], r8d
0x14000ece7  mov     dword ptr [rsp+0B8h+var_70], eax
0x14000eceb  lea     rax, [rbx+78h]
0x14000ecef  mov     rcx, [rax]
0x14000ecf2  cmp     [rcx+8], rax
0x14000ecf6  jnz     loc_14000EFE3
0x14000ecfc  mov     dl, [rsp+0B8h+NewIrql]; NewIrql
0x14000ed00  lea     r15, [r14+30h]
0x14000ed04  mov     [r15], rcx
0x14000ed07  mov     [r15+8], rax
0x14000ed0b  mov     [rcx+8], r15
0x14000ed0f  mov     rcx, rsi; SpinLock
0x14000ed12  mov     [rax], r15
0x14000ed15  inc     dword ptr [rbx+38h]
0x14000ed18  call    cs:__imp_KeReleaseSpinLock
0x14000ed1f  nop     dword ptr [rax+rax+00h]
0x14000ed24  imul    r8d, [rsp+0B8h+var_68], 32h ; '2'
0x14000ed2a  lea     rax, WinUSB_ChildIsochTransferComplete
0x14000ed31  mov     r9, [r14+8]
0x14000ed35  mov     edx, ebp
0x14000ed37  mov     rcx, r12
0x14000ed3a  mov     [rsp+0B8h+var_98], rax
0x14000ed3f  add     r8d, dword ptr [rsp+0B8h+var_70]
0x14000ed44  call    WinUSB_SubmitIsochTransfer
0x14000ed49  mov     ebp, eax
0x14000ed4b  test    eax, eax
0x14000ed4d  jns     loc_14000EF7A
0x14000ed53  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ed5a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ed61  jz      short loc_14000ED94
0x14000ed63  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed6a  lea     rax, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000ed71  mov     r9d, 73h ; 's'
0x14000ed77  mov     dword ptr [rsp+0B8h+var_88], ebp
0x14000ed7b  mov     [rsp+0B8h+var_90], r12
0x14000ed80  mov     dl, 4
0x14000ed82  mov     [rsp+0B8h+var_98], rax
0x14000ed87  mov     rcx, [rcx+40h]
0x14000ed8b  lea     r8d, [r9-70h]
0x14000ed8f  call    WPP_RECORDER_SF_qd
0x14000ed94  mov     rcx, rsi; SpinLock
0x14000ed97  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ed9e  nop     dword ptr [rax+rax+00h]
0x14000eda3  cmp     byte ptr [r14+7Ch], 0
0x14000eda8  mov     [rsp+0B8h+NewIrql], al
0x14000edac  jnz     short loc_14000EDCF
0x14000edae  mov     rdx, [r15]
0x14000edb1  cmp     [rdx+8], r15
0x14000edb5  jnz     loc_14000EFE3
0x14000edbb  mov     rcx, [r15+8]
0x14000edbf  cmp     [rcx], r15
0x14000edc2  jnz     loc_14000EFE3
0x14000edc8  mov     [rcx], rdx
0x14000edcb  mov     [rdx+8], rcx
0x14000edcf  dec     dword ptr [rbx+38h]
0x14000edd2  mov     rdx, r12
0x14000edd5  mov     rcx, rdi
0x14000edd8  call    WinUSB_FreeChildIsochRequest
0x14000eddd  mov     dl, [rsp+0B8h+NewIrql]; NewIrql
0x14000ede1  mov     rcx, rsi; SpinLock
0x14000ede4  call    cs:__imp_KeReleaseSpinLock
0x14000edeb  nop     dword ptr [rax+rax+00h]
0x14000edf0  mov     rcx, rsi; SpinLock
0x14000edf3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000edfa  nop     dword ptr [rax+rax+00h]
0x14000edff  mov     qword ptr [r13+0E0h], 0
0x14000ee0a  mov     r15b, al
0x14000ee0d  test    r14, r14
0x14000ee10  jz      loc_14000EEAF
0x14000ee16  cmp     byte ptr [r14+7Ch], 1
0x14000ee1b  jnz     loc_14000EEAF
0x14000ee21  sub     dword ptr [rbx+8Ch], 1
0x14000ee28  jnz     loc_14000EF5F
0x14000ee2e  mov     dl, al; NewIrql
0x14000ee30  mov     word ptr [rbx+88h], 101h
0x14000ee39  mov     rcx, rsi; SpinLock
0x14000ee3c  call    cs:__imp_KeReleaseSpinLock
0x14000ee43  nop     dword ptr [rax+rax+00h]
0x14000ee48  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ee4f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ee56  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000ee5d  jz      short loc_14000EE8A
0x14000ee5f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee66  mov     r9d, 74h ; 't'
0x14000ee6c  mov     [rsp+0B8h+var_88], r12
0x14000ee71  mov     dl, 4
0x14000ee73  mov     [rsp+0B8h+var_90], rdi
0x14000ee78  mov     [rsp+0B8h+var_98], r14
0x14000ee7d  mov     rcx, [rcx+40h]
0x14000ee81  lea     r8d, [r9-71h]
0x14000ee85  call    WPP_RECORDER_SF_qq
0x14000ee8a  mov     rax, cs:WdfFunctions_01015
0x14000ee91  mov     r8d, ebp
0x14000ee94  mov     rcx, cs:WdfDriverGlobals
0x14000ee9b  mov     rdx, rdi
0x14000ee9e  mov     rax, [rax+838h]
0x14000eea5  call    _guard_dispatch_icall
0x14000eeaa  jmp     loc_14000EF81
0x14000eeaf  mov     eax, [rbx+38h]
0x14000eeb2  cmp     eax, [rbx+3Ch]
0x14000eeb5  jnz     short loc_14000EF16
0x14000eeb7  mov     dl, r15b; NewIrql
0x14000eeba  mov     byte ptr [rbx+89h], 1
0x14000eec1  mov     rcx, rsi; SpinLock
0x14000eec4  call    cs:__imp_KeReleaseSpinLock
0x14000eecb  nop     dword ptr [rax+rax+00h]
0x14000eed0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000eed7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000eede  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000eee5  jz      short loc_14000EE8A
0x14000eee7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eeee  mov     r9d, 75h ; 'u'
0x14000eef4  mov     dword ptr [rsp+0B8h+var_88], ebp
0x14000eef8  mov     dl, 4
0x14000eefa  mov     [rsp+0B8h+var_90], rdi
0x14000eeff  mov     [rsp+0B8h+var_98], r14
0x14000ef04  mov     rcx, [rcx+40h]
0x14000ef08  lea     r8d, [r9-72h]
0x14000ef0c  call    WPP_RECORDER_SF_qd
0x14000ef11  jmp     loc_14000EE8A
0x14000ef16  mov     [rbx+34h], eax
0x14000ef19  mov     [rbx+28h], ebp
0x14000ef1c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000ef23  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ef2a  lea     r14, WPP_0eec754a616436344c523d073d150c9e_Traceguids
  ... truncated ...
```
