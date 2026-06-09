# PgmCreateAddress

- ea: `0x140001a50`
- end: `0x140002042`
- name: `PgmCreateAddress`
- size: `1522`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400078e0`

## callees

- `0x140001030`
- `0x140001a50`
- `0x1400023b8`
- `0x140002550`
- `0x140005038`
- `0x140005068`
- `0x1400051c8`
- `0x140005280`
- `0x1400055f0`
- `0x1400386b4`
- `0x140038afc`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x140001dcd`
- `ntoskrnl!RtlEqualSid` at `0x140001dcd`
- `ntoskrnl!PsGetCurrentProcess` at `0x140001c5a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140001c5a`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001c44`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001c44`
- `ntoskrnl!ExAllocatePool2` at `0x140001bbe`
- `ntoskrnl!ExAllocatePool2` at `0x140001bbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001d8e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001da0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e95`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002031`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001d8e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001da0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e95`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002031`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d1b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001dec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001f9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d1b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001dec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001f9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001c0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001cdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001c0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001cdc`

## pseudocode

```c
__int64 __fastcall PgmCreateAddress(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r15
  int UserInfo; // eax
  int v7; // ebx
  char v8; // r14
  unsigned __int32 v9; // esi
  unsigned __int16 v10; // r13
  _QWORD *Pool2; // rax
  _QWORD *v12; // rdi
  PVOID v13; // rcx
  KSPIN_LOCK *v15; // rcx
  _QWORD *v16; // rax
  int v17; // r8d
  int v18; // r9d
  int v19; // r8d
  int v20; // r9d
  struct _LIST_ENTRY *v21; // r15
  KIRQL v22; // cl
  struct _LIST_ENTRY *Flink; // r14
  unsigned int v24; // ebx
  KIRQL v25; // al
  BOOLEAN v26; // al
  unsigned int v27; // ecx
  __int64 v28; // rdx
  __int64 v29; // r8
  struct _LIST_ENTRY *Blink; // rax
  int v31; // r8d
  const char *v32; // r9
  KIRQL v33; // al
  _QWORD *v34; // rcx
  PVOID P[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v36; // [rsp+A0h] [rbp+48h] BYREF
  __int64 NewIrql; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v38; // [rsp+B0h] [rbp+58h]
  unsigned int v39; // [rsp+B8h] [rbp+60h] BYREF

  v38 = a3;
  NewIrql = a2;
  v36 = a1;
  v4 = a3;
  v39 = 0;
  LOWORD(v36) = 0;
  P[0] = 0;
  LOBYTE(NewIrql) = 0;
  UserInfo = PgmGetUserInfo(a1, a3, P, &NewIrql);
  if ( UserInfo < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids,
      (unsigned int)UserInfo);
  }
  if ( !GetIpAddress((_DWORD *)(a4 + *(unsigned __int8 *)(a4 + 5) + 9LL), *(unsigned __int16 *)(a4 + 6), &v39, &v36) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids);
    v7 = -1073741305;
LABEL_26:
    v13 = P[0];
LABEL_27:
    ExFreePoolWithTag(v13, 0);
    return (unsigned int)v7;
  }
  v8 = NewIrql;
  v9 = _byteswap_ulong(v39);
  v10 = __ROR2__(v36, 8);
  if ( v9 )
  {
    if ( HIBYTE(v9) < 0xE0u )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids, v9);
      v7 = -1073741823;
      goto LABEL_26;
    }
  }
  else if ( !(_BYTE)NewIrql )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids);
    v7 = -1073741790;
    goto LABEL_26;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(64, 480, 812476240);
  v12 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids);
    v7 = -1073741670;
    goto LABEL_26;
  }
  Pool2[1] = Pool2;
  v15 = Pool2 + 53;
  *Pool2 = Pool2;
  v16 = Pool2 + 3;
  v16[1] = v16;
  *v16 = v16;
  v12[40] = v12 + 39;
  v12[39] = v12 + 39;
  KeInitializeSpinLock(v15);
  ++*((_DWORD *)v12 + 5);
  *((_DWORD *)v12 + 4) = 1380205633;
  v12[5] = PsGetCurrentProcess();
  v12[28] = P[0];
  v7 = TdiOpenAddressHandle(
         (int)v12 + 72,
         (_DWORD)v12,
         v17,
         v18,
         (__int64)(v12 + 8),
         (__int64)(v12 + 9),
         (__int64)(v12 + 10));
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids,
        (unsigned int)v7,
        v12);
    ExFreePoolWithTag(P[0], 0);
    v13 = v12;
    goto LABEL_27;
  }
  if ( v9 )
  {
    *((_DWORD *)v12 + 82) = v9;
    *((_WORD *)v12 + 166) = v10;
    v12[28] = P[0];
    v21 = 0;
    LOBYTE(NewIrql) = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v22 = NewIrql;
    if ( !v8 )
    {
      Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
      v24 = 0;
      LODWORD(v36) = 0;
      if ( (union _DEVICE_OBJECT::$3ABEFC84562B0417329DFE2AD83813CB *)WPP_MAIN_CB.Queue.ListEntry.Flink != &WPP_MAIN_CB.Queue )
      {
        do
        {
          if ( v9 == LODWORD(Flink[20].Blink) && v10 == WORD2(Flink[20].Blink) )
          {
            v25 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&Flink[26].Blink);
            ++HIDWORD(Flink[1].Flink);
            KeReleaseSpinLock((PKSPIN_LOCK)&Flink[26].Blink, v25);
            KeReleaseSpinLock(&SpinLock, NewIrql);
            if ( v21 )
              PgmDereferenceAddress(v21);
            v21 = Flink;
            v26 = RtlEqualSid(*(PSID *)P[0], Flink[14].Flink->Flink);
            v27 = v36 + 1;
            if ( !v26 )
              v27 = v36;
            v24 = v27;
            LODWORD(v36) = v27;
            v22 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
            LOBYTE(NewIrql) = v22;
          }
          Flink = Flink->Flink;
        }
        while ( Flink != (struct _LIST_ENTRY *)&WPP_MAIN_CB.Queue );
        if ( v24 >= 2 )
        {
          KeReleaseSpinLock(&SpinLock, v22);
          if ( v21 )
            PgmDereferenceAddress(v21);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_dDD(WPP_GLOBAL_Control->AttachedDevice, v28, v29, v24, v9, v10);
          }
          v7 = -1073741790;
LABEL_66:
          PgmDestroyAddress(v12);
          return (unsigned int)v7;
        }
      }
    }
    Blink = WPP_MAIN_CB.Queue.ListEntry.Blink;
    if ( WPP_MAIN_CB.Queue.ListEntry.Blink->Flink == (struct _LIST_ENTRY *)&WPP_MAIN_CB.Queue )
    {
      *v12 = &WPP_MAIN_CB.Queue;
      v12[1] = Blink;
      Blink->Flink = (struct _LIST_ENTRY *)v12;
      WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)v12;
      KeReleaseSpinLock(&SpinLock, v22);
      if ( v21 )
        PgmDereferenceAddress(v21);
      v4 = v38;
      goto LABEL_56;
    }
LABEL_68:
    __fastfail(3u);
  }
  v7 = TdiOpenAddressHandle((int)v12 + 96, 0, v19, v20, (__int64)(v12 + 11), (__int64)(v12 + 12), (__int64)(v12 + 13));
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids,
        (unsigned int)v7,
        v12);
    goto LABEL_66;
  }
  v33 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v12[34] = 56;
  v12[33] = 0x2BBFFFFFA88LL;
  v12[35] = 10000000;
  v12[36] = 1428571;
  *((_DWORD *)v12 + 74) = 15;
  *((_DWORD *)v12 + 63) = 0;
  *((_BYTE *)v12 + 304) = 1;
  *((_DWORD *)v12 + 64) = 255;
  v34 = *(_QWORD **)&WPP_MAIN_CB.DeviceType;
  if ( **(struct _DEVICE_OBJECT ***)&WPP_MAIN_CB.DeviceType != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceExtension )
    goto LABEL_68;
  *v12 = &WPP_MAIN_CB.DeviceExtension;
  v12[1] = v34;
  *v34 = v12;
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = v12;
  KeReleaseSpinLock(&SpinLock, v33);
LABEL_56:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    v32 = "Receiver";
    if ( !v9 )
      v32 = "Sender";
    WPP_SF_sqDD(WPP_GLOBAL_Control->AttachedDevice, (unsigned int)"Sender", v31, (_DWORD)v32, (char)v12, v9, v10);
  }
  *(_QWORD *)(*(_QWORD *)(v4 + 48) + 24LL) = v12;
  *(_QWORD *)(*(_QWORD *)(v4 + 48) + 32LL) = 1;
  return 0;
}

```

## disassembly

```asm
0x140001a50  mov     [rsp-40h+arg_10], r8
0x140001a55  mov     [rsp-40h+NewIrql], rdx
0x140001a5a  mov     [rsp-40h+arg_0], rcx
0x140001a5f  push    rbp
0x140001a60  push    rbx
0x140001a61  push    rsi
0x140001a62  push    rdi
0x140001a63  push    r12
0x140001a65  push    r13
0x140001a67  push    r14
0x140001a69  push    r15
0x140001a6b  mov     rbp, rsp
0x140001a6e  sub     rsp, 58h
0x140001a72  xor     r12d, r12d
0x140001a75  mov     r15, r8
0x140001a78  mov     rbx, r9
0x140001a7b  mov     [rbp+arg_18], r12d
0x140001a7f  mov     rdx, r15
0x140001a82  mov     word ptr [rbp+arg_0], r12w
0x140001a87  lea     r9, [rbp+NewIrql]
0x140001a8b  mov     [rbp+P], r12
0x140001a8f  lea     r8, [rbp+P]
0x140001a93  mov     byte ptr [rbp+NewIrql], r12b
0x140001a97  call    PgmGetUserInfo
0x140001a9c  lea     rdi, WPP_GLOBAL_Control
0x140001aa3  test    eax, eax
0x140001aa5  jns     short loc_140001AD3
0x140001aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x140001aae  cmp     rcx, rdi
0x140001ab1  jz      short loc_140001AD3
0x140001ab3  mov     edx, [rcx+2Ch]
0x140001ab6  test    dl, 2
0x140001ab9  jz      short loc_140001AD3
0x140001abb  mov     rcx, [rcx+18h]
0x140001abf  lea     edx, [r12+12h]
0x140001ac4  mov     r9d, eax
0x140001ac7  lea     r8, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids
0x140001ace  call    WPP_SF_d
0x140001ad3  movzx   ecx, byte ptr [rbx+5]
0x140001ad7  lea     r9, [rbp+arg_0]
0x140001adb  movzx   edx, word ptr [rbx+6]
0x140001adf  lea     r8, [rbp+arg_18]
0x140001ae3  add     rcx, 9
0x140001ae7  add     rcx, rbx
0x140001aea  call    GetIpAddress
0x140001aef  test    al, al
0x140001af1  jnz     short loc_140001B25
0x140001af3  mov     rcx, cs:WPP_GLOBAL_Control
0x140001afa  cmp     rcx, rdi
0x140001afd  jz      short loc_140001B1B
0x140001aff  mov     eax, [rcx+2Ch]
0x140001b02  test    al, 2
0x140001b04  jz      short loc_140001B1B
0x140001b06  mov     rcx, [rcx+18h]
0x140001b0a  lea     r8, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids
0x140001b11  mov     edx, 13h
0x140001b16  call    WPP_SF_
0x140001b1b  mov     ebx, 0C0000207h
0x140001b20  jmp     loc_140001C04
0x140001b25  mov     esi, [rbp+arg_18]
0x140001b28  movzx   r13d, word ptr [rbp+arg_0]
0x140001b2d  mov     r14b, byte ptr [rbp+NewIrql]
0x140001b31  bswap   esi
0x140001b33  ror     r13w, 8
0x140001b38  test    esi, esi
0x140001b3a  jz      short loc_140001B7A
0x140001b3c  mov     eax, esi
0x140001b3e  shr     eax, 18h
0x140001b41  cmp     al, 0E0h
0x140001b43  jnb     short loc_140001BAE
0x140001b45  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b4c  cmp     rcx, rdi
0x140001b4f  jz      short loc_140001B70
0x140001b51  mov     eax, [rcx+2Ch]
0x140001b54  test    al, 2
0x140001b56  jz      short loc_140001B70
0x140001b58  mov     rcx, [rcx+18h]
0x140001b5c  lea     r8, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids
0x140001b63  mov     edx, 14h
0x140001b68  mov     r9d, esi
0x140001b6b  call    WPP_SF_d
0x140001b70  mov     ebx, 0C0000001h
0x140001b75  jmp     loc_140001C04
0x140001b7a  test    r14b, r14b
0x140001b7d  jnz     short loc_140001BAE
0x140001b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b86  cmp     rcx, rdi
0x140001b89  jz      short loc_140001BA7
0x140001b8b  mov     eax, [rcx+2Ch]
0x140001b8e  test    al, 2
0x140001b90  jz      short loc_140001BA7
0x140001b92  mov     rcx, [rcx+18h]
0x140001b96  lea     r8, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids
0x140001b9d  mov     edx, 15h
0x140001ba2  call    WPP_SF_
0x140001ba7  mov     ebx, 0C0000022h
0x140001bac  jmp     short loc_140001C04
0x140001bae  mov     edx, 1E0h
0x140001bb3  mov     ecx, 40h ; '@'
0x140001bb8  mov     r8d, 306D6750h
0x140001bbe  call    cs:__imp_ExAllocatePool2
0x140001bc5  nop     dword ptr [rax+rax+00h]
0x140001bca  mov     rdi, rax
0x140001bcd  test    rax, rax
0x140001bd0  jnz     short loc_140001C1D
0x140001bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bd9  lea     rax, WPP_GLOBAL_Control
0x140001be0  cmp     rcx, rax
0x140001be3  jz      short loc_140001BFF
0x140001be5  mov     eax, [rcx+2Ch]
0x140001be8  test    al, 2
0x140001bea  jz      short loc_140001BFF
0x140001bec  mov     rcx, [rcx+18h]
0x140001bf0  lea     edx, [rdi+16h]
0x140001bf3  lea     r8, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids
0x140001bfa  call    WPP_SF_
0x140001bff  mov     ebx, 0C000009Ah
0x140001c04  mov     rcx, [rbp+P]; P
0x140001c08  xor     edx, edx; Tag
0x140001c0a  call    cs:__imp_ExFreePoolWithTag
0x140001c11  nop     dword ptr [rax+rax+00h]
0x140001c16  mov     eax, ebx
0x140001c18  jmp     loc_140001F10
0x140001c1d  mov     [rax+8], rdi
0x140001c21  lea     rcx, [rdi+1A8h]; SpinLock
0x140001c28  mov     [rax], rdi
0x140001c2b  add     rax, 18h
0x140001c2f  mov     [rax+8], rax
0x140001c33  mov     [rax], rax
0x140001c36  lea     rax, [rdi+138h]
0x140001c3d  mov     [rax+8], rax
0x140001c41  mov     [rax], rax
0x140001c44  call    cs:__imp_KeInitializeSpinLock
0x140001c4b  nop     dword ptr [rax+rax+00h]
0x140001c50  inc     dword ptr [rdi+14h]
0x140001c53  mov     dword ptr [rdi+10h], 52444441h
0x140001c5a  call    cs:__imp_PsGetCurrentProcess
0x140001c61  nop     dword ptr [rax+rax+00h]
0x140001c66  mov     [rdi+28h], rax
0x140001c6a  lea     rcx, [rdi+48h]
0x140001c6e  mov     rax, [rbp+P]
0x140001c72  lea     rdx, [rdi+40h]
0x140001c76  mov     [rdi+0E0h], rax
0x140001c7d  lea     rax, [rdi+50h]
0x140001c81  mov     [rsp+58h+var_28], rax
0x140001c86  mov     [rsp+58h+var_30], rcx
0x140001c8b  mov     [rsp+58h+var_38], rdx
0x140001c90  mov     rdx, rdi
0x140001c93  call    TdiOpenAddressHandle
0x140001c98  mov     ebx, eax
0x140001c9a  test    eax, eax
0x140001c9c  jns     short loc_140001CF0
0x140001c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ca5  lea     rax, WPP_GLOBAL_Control
0x140001cac  cmp     rcx, rax
0x140001caf  jz      short loc_140001CD6
0x140001cb1  mov     edx, [rcx+2Ch]
0x140001cb4  test    dl, 2
0x140001cb7  jz      short loc_140001CD6
0x140001cb9  mov     rcx, [rcx+18h]
0x140001cbd  lea     r8, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids
0x140001cc4  mov     edx, 17h
0x140001cc9  mov     [rsp+58h+var_38], rdi
0x140001cce  mov     r9d, ebx
0x140001cd1  call    WPP_SF_dq
0x140001cd6  mov     rcx, [rbp+P]; P
0x140001cda  xor     edx, edx; Tag
0x140001cdc  call    cs:__imp_ExFreePoolWithTag
0x140001ce3  nop     dword ptr [rax+rax+00h]
0x140001ce8  mov     rcx, rdi
0x140001ceb  jmp     loc_140001C08
0x140001cf0  test    esi, esi
0x140001cf2  jz      loc_140001F22
0x140001cf8  mov     [rdi+148h], esi
0x140001cfe  lea     r12, SpinLock
0x140001d05  mov     [rdi+14Ch], r13w
0x140001d0d  mov     rcx, r12; SpinLock
0x140001d10  mov     rax, [rbp+P]
0x140001d14  mov     [rdi+0E0h], rax
0x140001d1b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001d22  nop     dword ptr [rax+rax+00h]
0x140001d27  xor     r15d, r15d
0x140001d2a  mov     byte ptr [rbp+NewIrql], al
0x140001d2d  lea     rdx, WPP_MAIN_CB.Queue
0x140001d34  mov     cl, al
0x140001d36  test    r14b, r14b
0x140001d39  jnz     loc_140001E6F
0x140001d3f  mov     r14, qword ptr cs:WPP_MAIN_CB.Queue
0x140001d46  xor     ebx, ebx
0x140001d48  mov     dword ptr [rbp+arg_0], ebx
0x140001d4b  cmp     r14, rdx
0x140001d4e  jz      loc_140001E6F
0x140001d54  cmp     esi, [r14+148h]
0x140001d5b  jnz     loc_140001E04
0x140001d61  cmp     r13w, [r14+14Ch]
0x140001d69  jnz     loc_140001E04
0x140001d6f  lea     rbx, [r14+1A8h]
0x140001d76  mov     rcx, rbx; SpinLock
0x140001d79  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001d80  nop     dword ptr [rax+rax+00h]
0x140001d85  inc     dword ptr [r14+14h]
0x140001d89  mov     rcx, rbx; SpinLock
0x140001d8c  mov     dl, al; NewIrql
0x140001d8e  call    cs:__imp_KeReleaseSpinLock
0x140001d95  nop     dword ptr [rax+rax+00h]
0x140001d9a  mov     dl, byte ptr [rbp+NewIrql]; NewIrql
0x140001d9d  mov     rcx, r12; SpinLock
0x140001da0  call    cs:__imp_KeReleaseSpinLock
0x140001da7  nop     dword ptr [rax+rax+00h]
0x140001dac  test    r15, r15
0x140001daf  jz      short loc_140001DB9
0x140001db1  mov     rcx, r15; P
0x140001db4  call    PgmDereferenceAddress
0x140001db9  mov     rdx, [r14+0E0h]
0x140001dc0  mov     r15, r14
0x140001dc3  mov     rcx, [rbp+P]
0x140001dc7  mov     rdx, [rdx]; Sid2
0x140001dca  mov     rcx, [rcx]; Sid1
0x140001dcd  call    cs:__imp_RtlEqualSid
0x140001dd4  nop     dword ptr [rax+rax+00h]
0x140001dd9  mov     ebx, dword ptr [rbp+arg_0]
0x140001ddc  test    al, al
0x140001dde  lea     ecx, [rbx+1]
0x140001de1  cmovz   ecx, ebx
0x140001de4  mov     ebx, ecx
0x140001de6  mov     dword ptr [rbp+arg_0], ecx
0x140001de9  mov     rcx, r12; SpinLock
0x140001dec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001df3  nop     dword ptr [rax+rax+00h]
0x140001df8  mov     cl, al
0x140001dfa  mov     byte ptr [rbp+NewIrql], al
0x140001dfd  lea     rdx, WPP_MAIN_CB.Queue
0x140001e04  mov     r14, [r14]
0x140001e07  cmp     r14, rdx
0x140001e0a  jnz     loc_140001D54
0x140001e10  cmp     ebx, 2
0x140001e13  jb      short loc_140001E6F
0x140001e15  mov     dl, cl; NewIrql
0x140001e17  mov     rcx, r12; SpinLock
0x140001e1a  call    cs:__imp_KeReleaseSpinLock
0x140001e21  nop     dword ptr [rax+rax+00h]
0x140001e26  test    r15, r15
0x140001e29  jz      short loc_140001E33
0x140001e2b  mov     rcx, r15; P
0x140001e2e  call    PgmDereferenceAddress
0x140001e33  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e3a  lea     rax, WPP_GLOBAL_Control
0x140001e41  cmp     rcx, rax
0x140001e44  jz      short loc_140001E65
0x140001e46  mov     eax, [rcx+2Ch]
0x140001e49  test    al, 2
0x140001e4b  jz      short loc_140001E65
0x140001e4d  mov     rcx, [rcx+18h]
0x140001e51  mov     r9d, ebx
0x140001e54  movzx   eax, r13w
0x140001e58  mov     dword ptr [rsp+58h+var_30], eax
0x140001e5c  mov     dword ptr [rsp+58h+var_38], esi
0x140001e60  call    WPP_SF_dDD
0x140001e65  mov     ebx, 0C0000022h
0x140001e6a  jmp     loc_140001F82
0x140001e6f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001e76  cmp     [rax], rdx
0x140001e79  jnz     loc_140002014
0x140001e7f  mov     [rdi], rdx
0x140001e82  mov     dl, cl; NewIrql
0x140001e84  mov     [rdi+8], rax
0x140001e88  mov     rcx, r12; SpinLock
0x140001e8b  mov     [rax], rdi
0x140001e8e  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rdi
0x140001e95  call    cs:__imp_KeReleaseSpinLock
0x140001e9c  nop     dword ptr [rax+rax+00h]
0x140001ea1  test    r15, r15
0x140001ea4  jz      short loc_140001EAE
0x140001ea6  mov     rcx, r15; P
0x140001ea9  call    PgmDereferenceAddress
0x140001eae  mov     r15, [rbp+arg_10]
0x140001eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140001eb9  lea     rax, WPP_GLOBAL_Control
0x140001ec0  cmp     rcx, rax
0x140001ec3  jz      short loc_140001EFA
0x140001ec5  mov     eax, [rcx+2Ch]
0x140001ec8  test    al, 4
0x140001eca  jz      short loc_140001EFA
0x140001ecc  mov     rcx, [rcx+18h]
0x140001ed0  lea     rdx, aSender; "Sender"
0x140001ed7  movzx   eax, r13w
0x140001edb  lea     r9, aReceiver; "Receiver"
0x140001ee2  mov     dword ptr [rsp+58h+var_28], eax
0x140001ee6  test    esi, esi
0x140001ee8  mov     dword ptr [rsp+58h+var_30], esi
0x140001eec  cmovz   r9, rdx
0x140001ef0  mov     [rsp+58h+var_38], rdi
0x140001ef5  call    WPP_SF_sqDD
0x140001efa  mov     rax, [r15+30h]
0x140001efe  mov     [rax+18h], rdi
0x140001f02  mov     rax, [r15+30h]
0x140001f06  mov     qword ptr [rax+20h], 1
0x140001f0e  xor     eax, eax
0x140001f10  add     rsp, 58h
0x140001f14  pop     r15
  ... truncated ...
```
