# KmclpClientOpenChannel

- ea: `0x14000b3d8`
- end: `0x14000bb67`
- name: `KmclpClientOpenChannel`
- size: `1935`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14000abe0`
- `0x14000afe8`
- `0x14000e4e0`

## callees

- `0x140007d58`
- `0x140009028`
- `0x14000ab90`
- `0x14000af84`
- `0x14000b3d8`
- `0x14000cbc8`
- `0x14000cf30`
- `0x14000e310`
- `0x14000e414`
- `0x14000f5c4`
- `0x14000f780`
- `0x140011a4c`
- `0x140011e90`
- `0x140011ed0`
- `0x140012280`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000b947`
- `ntoskrnl!KeInitializeEvent` at `0x14000b947`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b991`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b991`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14000b600`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14000b600`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14000b772`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14000b772`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14000b5c4`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14000b5c4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b8d5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b8d5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b8ed`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b8ed`

## pseudocode

```c
__int64 __fastcall KmclpClientOpenChannel(ULONG_PTR BugCheckParameter2)
{
  __int64 v2; // r8
  int v3; // eax
  __int64 v4; // r8
  int BounceBlock; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  ULONG v10; // esi
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int64 v17; // r8
  __int64 v18; // rdx
  int v19; // r12d
  int v20; // eax
  unsigned int v21; // r14d
  __int64 *v22; // r15
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v26; // r8
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  bool v29; // zf
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  _PROCESSOR_NUMBER ProcNumber; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v35; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Event[32]; // [rsp+50h] [rbp-B0h] BYREF
  _GROUP_AFFINITY Affinity; // [rsp+70h] [rbp-90h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v40[11]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v41[32]; // [rsp+140h] [rbp+40h] BYREF

  memset(v41, 0, sizeof(v41));
  memset(v40, 0, sizeof(v40));
  v36 = 0;
  v35 = 0;
  Affinity = 0;
  ProcNumber = 0;
  PreviousAffinity = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qLd(
      WPP_GLOBAL_Control->AttachedDevice,
      53,
      v2,
      BugCheckParameter2,
      *(_DWORD *)(BugCheckParameter2 + 2200),
      *(unsigned __int8 *)(BugCheckParameter2 + 2824));
  }
  PreviousAffinity = 0;
  if ( *(_BYTE *)(BugCheckParameter2 + 2824) )
    v3 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(BugCheckParameter2 + 2872))(
           *(_QWORD *)(BugCheckParameter2 + 2840),
           v40);
  else
    v3 = KmclpSynchronousIoControl(BugCheckParameter2, 4112420, 0, 0, v40, 176);
  BounceBlock = v3;
  if ( v3 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_40;
    }
    v7 = 54;
    goto LABEL_33;
  }
  v8 = v40[0];
  *(_QWORD *)(BugCheckParameter2 + 3080) = *((_QWORD *)&v40[2] + 1);
  v9 = v40[1];
  *(_QWORD *)(BugCheckParameter2 + 3088) = *(_QWORD *)&v40[3];
  *(_OWORD *)(BugCheckParameter2 + 2736) = v8;
  *(_OWORD *)(BugCheckParameter2 + 2752) = v9;
  if ( *(_BYTE *)(BugCheckParameter2 + 2896) )
    *(_BYTE *)(BugCheckParameter2 + 2897) = BYTE6(v40[2]);
  v10 = *(_DWORD *)(BugCheckParameter2 + 1968);
  v11 = *(_OWORD *)((char *)&v40[4] + 8);
  *(_OWORD *)(BugCheckParameter2 + 1824) = *(_OWORD *)((char *)&v40[3] + 8);
  v12 = *(_OWORD *)((char *)&v40[5] + 8);
  *(_OWORD *)(BugCheckParameter2 + 1840) = v11;
  v13 = *(_OWORD *)((char *)&v40[6] + 8);
  *(_OWORD *)(BugCheckParameter2 + 1856) = v12;
  v14 = *(_OWORD *)((char *)&v40[7] + 8);
  *(_OWORD *)(BugCheckParameter2 + 1872) = v13;
  v15 = *(_OWORD *)((char *)&v40[8] + 8);
  *(_OWORD *)(BugCheckParameter2 + 1888) = v14;
  v16 = *(_OWORD *)((char *)&v40[9] + 8);
  *(_OWORD *)(BugCheckParameter2 + 1904) = v15;
  *(_QWORD *)&v15 = *((_QWORD *)&v40[10] + 1);
  *(_OWORD *)(BugCheckParameter2 + 1920) = v16;
  *(_QWORD *)(BugCheckParameter2 + 1936) = v15;
  if ( v10 == -1 )
  {
    v10 = v40[2];
    *(_DWORD *)(BugCheckParameter2 + 1968) = v40[2];
  }
  if ( KeGetProcessorNumberFromIndex(v10, &ProcNumber) >= 0 )
  {
    *(_QWORD *)&Affinity.Group = ProcNumber.Group;
    Affinity.Mask = 1LL << ProcNumber.Number;
    KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
  }
  if ( *(_BYTE *)(BugCheckParameter2 + 2897) )
  {
    v18 = *(unsigned int *)(BugCheckParameter2 + 1972);
    if ( (_DWORD)v18 )
    {
      LOBYTE(v17) = 1;
      BounceBlock = KmclpAllocateBounceBlock(BugCheckParameter2, v18, v17);
      if ( BounceBlock < 0 )
        goto LABEL_40;
    }
  }
  if ( !*(_BYTE *)(BugCheckParameter2 + 1729) )
  {
    BounceBlock = InOpenChannel(BugCheckParameter2);
    if ( BounceBlock < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_40;
      }
      v7 = 55;
      goto LABEL_33;
    }
  }
  BounceBlock = KmclpInitializeVmbusConnection(BugCheckParameter2);
  if ( BounceBlock < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_40;
    }
    v7 = 56;
LABEL_33:
    WPP_SF_qd(v6->AttachedDevice, v7, v4, BugCheckParameter2, BounceBlock);
LABEL_40:
    KmclpTeardownOpenChannelState(BugCheckParameter2);
    KmclpDisableClosedChannel(BugCheckParameter2);
    goto LABEL_41;
  }
  v19 = *(_DWORD *)(BugCheckParameter2 + 1964);
  v20 = *(_DWORD *)(BugCheckParameter2 + 1960) + 1;
  v21 = v19 + 1;
  *(_DWORD *)(BugCheckParameter2 + 2712) = v20;
  *(_DWORD *)(BugCheckParameter2 + 2716) = v19 + 1;
  if ( *(_BYTE *)(BugCheckParameter2 + 2824) )
  {
    v22 = (__int64 *)(BugCheckParameter2 + 2704);
    BounceBlock = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, ULONG_PTR))(BugCheckParameter2 + 2880))(
                    *(_QWORD *)(BugCheckParameter2 + 2840),
                    (unsigned int)(v19 + 1 + v20),
                    v21,
                    BugCheckParameter2 + 2704);
    if ( BounceBlock < 0 )
    {
LABEL_36:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 57, v23, BugCheckParameter2, BounceBlock);
      }
      goto LABEL_40;
    }
  }
  else
  {
    LODWORD(v36) = v21 + v20;
    v35 = 0;
    HIDWORD(v36) = v19 + 1;
    BounceBlock = KmclpSynchronousIoControl(BugCheckParameter2, 4112430, &v36, 8, &v35, 4);
    if ( BounceBlock < 0 )
      goto LABEL_36;
    v22 = (__int64 *)(BugCheckParameter2 + 2704);
    (*(void (__fastcall **)(_QWORD, _QWORD, ULONG_PTR))(BugCheckParameter2 + 2448))(
      *(_QWORD *)(BugCheckParameter2 + 2368),
      v35,
      BugCheckParameter2 + 2704);
  }
  if ( !*(_BYTE *)(BugCheckParameter2 + 1729) )
  {
    BounceBlock = PkInitializeRingBuffer((void *)(BugCheckParameter2 + 64), *v22, *v22 + 4096, v19);
    if ( BounceBlock < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_79;
      }
      v28 = 58;
LABEL_78:
      WPP_SF_qd(v27->AttachedDevice, v28, v26, BugCheckParameter2, BounceBlock);
LABEL_79:
      KmclpClientCloseChannel(BugCheckParameter2);
      goto LABEL_40;
    }
    *(_QWORD *)(BugCheckParameter2 + 216) = BugCheckParameter2 + 488;
  }
  ExAcquirePushLockExclusiveEx(BugCheckParameter2 + 2808, 0);
  *(_BYTE *)(BugCheckParameter2 + 2806) = 1;
  ExReleasePushLockExclusiveEx(BugCheckParameter2 + 2808, 0);
  memset(v41, 0, 0x78u);
  v29 = *(_BYTE *)(BugCheckParameter2 + 1986) == 0;
  v30 = 1;
  v41[30] = v10;
  if ( !v29 )
    v30 = 3;
  v41[31] = v30;
  if ( *(_BYTE *)(BugCheckParameter2 + 2824) )
  {
    memset(Event, 0, sizeof(Event));
    KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
    BounceBlock = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64 (__fastcall *)(), _BYTE *))(BugCheckParameter2
                                                                                                 + 2888))(
                    *(_QWORD *)(BugCheckParameter2 + 2840),
                    v41,
                    KmclpOpenChannelCompletionCallback,
                    Event);
    if ( BounceBlock == 259 )
    {
      KeWaitForSingleObject(Event, Executive, 0, 0, 0);
      BounceBlock = *(_DWORD *)&Event[24];
    }
  }
  else
  {
    BounceBlock = KmclpSynchronousIoControl(BugCheckParameter2, 4112436, v41, 128, 0, 0);
  }
  if ( BounceBlock < 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_79;
    }
    v28 = 59;
    goto LABEL_78;
  }
  *(_DWORD *)(BugCheckParameter2 + 3276) = v10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      60,
      WPP_fa014546bb113ca58de70d4b381949e7_Traceguids,
      BugCheckParameter2);
  }
  if ( *(_BYTE *)(BugCheckParameter2 + 2024) )
    v31 = (*(__int64 (__fastcall **)(ULONG_PTR, _QWORD))(BugCheckParameter2 + 2048))(
            BugCheckParameter2,
            *(_QWORD *)(BugCheckParameter2 + 2040));
  else
    v31 = (*(__int64 (__fastcall **)(ULONG_PTR))(BugCheckParameter2 + 2040))(BugCheckParameter2);
  BounceBlock = v31;
  if ( v31 < 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_79;
    }
    v28 = 61;
    goto LABEL_78;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 62, v26, BugCheckParameter2, v31);
  }
  *(_DWORD *)(BugCheckParameter2 + 2200) = 4;
  BounceBlock = 0;
  v32 = _InterlockedIncrement((volatile signed __int32 *)(BugCheckParameter2 + 3296)) % 24;
  v33 = v32 + 207;
  v32 *= 2;
  *(_QWORD *)(BugCheckParameter2 + 8 * v32 + 3304) = MEMORY[0xFFFFF78000000008];
  *(_BYTE *)(BugCheckParameter2 + 16 * v33) = *(_BYTE *)(BugCheckParameter2 + 2200);
  *(_BYTE *)(BugCheckParameter2 + 8 * v32 + 3313) = *(_BYTE *)(BugCheckParameter2 + 2204);
  *(_WORD *)(BugCheckParameter2 + 8 * v32 + 3314) = *(_DWORD *)(BugCheckParameter2 + 2216);
  *(_WORD *)(BugCheckParameter2 + 8 * v32 + 3316) = 2329;
LABEL_41:
  KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 63, v24, BugCheckParameter2, BounceBlock);
  }
  return (unsigned int)BounceBlock;
}

```

## disassembly

```asm
0x14000b3d8  push    rbp
0x14000b3da  push    rbx
0x14000b3db  push    rsi
0x14000b3dc  push    rdi
0x14000b3dd  push    r12
0x14000b3df  push    r13
0x14000b3e1  push    r14
0x14000b3e3  push    r15
0x14000b3e5  lea     rbp, [rsp-0D8h]
0x14000b3ed  sub     rsp, 1D8h
0x14000b3f4  mov     rax, cs:__security_cookie
0x14000b3fb  xor     rax, rsp
0x14000b3fe  mov     [rbp+110h+var_50], rax
0x14000b405  mov     rdi, rcx
0x14000b408  xor     edx, edx; Val
0x14000b40a  lea     rcx, [rbp+110h+var_D0]; void *
0x14000b40e  mov     r8d, 80h; Size
0x14000b414  call    memset
0x14000b419  mov     ebx, 0B0h
0x14000b41e  lea     rcx, [rbp+110h+var_180]; void *
0x14000b422  mov     r8d, ebx; Size
0x14000b425  xor     edx, edx; Val
0x14000b427  call    memset
0x14000b42c  xor     r15d, r15d
0x14000b42f  xorps   xmm0, xmm0
0x14000b432  xorps   xmm1, xmm1
0x14000b435  mov     [rsp+210h+var_1C8], r15
0x14000b43a  mov     [rsp+210h+var_1CC], r15d
0x14000b43f  movups  xmmword ptr [rsp+210h+Affinity.Mask], xmm0
0x14000b444  mov     dword ptr [rsp+210h+ProcNumber.Group], r15d
0x14000b449  movups  xmmword ptr [rbp+110h+PreviousAffinity.Mask], xmm1
0x14000b44d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b454  lea     r12, WPP_GLOBAL_Control
0x14000b45b  cmp     rcx, r12
0x14000b45e  jz      short loc_14000B491
0x14000b460  mov     eax, [rcx+2Ch]
0x14000b463  test    al, 1
0x14000b465  jz      short loc_14000B491
0x14000b467  cmp     byte ptr [rcx+29h], 4
0x14000b46b  jb      short loc_14000B491
0x14000b46d  movzx   eax, byte ptr [rdi+0B08h]
0x14000b474  lea     edx, [rbx-7Bh]
0x14000b477  mov     rcx, [rcx+18h]
0x14000b47b  mov     r9, rdi
0x14000b47e  mov     dword ptr [rsp+210h+var_1E8], eax
0x14000b482  mov     eax, [rdi+898h]
0x14000b488  mov     dword ptr [rsp+210h+Timeout], eax
0x14000b48c  call    WPP_SF_qLd
0x14000b491  xorps   xmm0, xmm0
0x14000b494  movups  xmmword ptr [rbp+110h+PreviousAffinity.Mask], xmm0
0x14000b498  cmp     [rdi+0B08h], r15b
0x14000b49f  jz      short loc_14000B4BA
0x14000b4a1  mov     rax, [rdi+0B38h]
0x14000b4a8  lea     rdx, [rbp+110h+var_180]
0x14000b4ac  mov     rcx, [rdi+0B18h]
0x14000b4b3  call    _guard_dispatch_icall
0x14000b4b8  jmp     short loc_14000B4DA
0x14000b4ba  lea     rax, [rbp+110h+var_180]
0x14000b4be  mov     dword ptr [rsp+210h+var_1E8], ebx
0x14000b4c2  xor     r9d, r9d
0x14000b4c5  mov     [rsp+210h+Timeout], rax
0x14000b4ca  xor     r8d, r8d
0x14000b4cd  mov     edx, 3EC024h
0x14000b4d2  mov     rcx, rdi
0x14000b4d5  call    KmclpSynchronousIoControl
0x14000b4da  mov     ebx, eax
0x14000b4dc  test    eax, eax
0x14000b4de  jns     short loc_14000B50F
0x14000b4e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4e7  cmp     rcx, r12
0x14000b4ea  jz      loc_14000B75E
0x14000b4f0  mov     eax, [rcx+2Ch]
0x14000b4f3  test    al, 1
0x14000b4f5  jz      loc_14000B75E
0x14000b4fb  cmp     byte ptr [rcx+29h], 2
0x14000b4ff  jb      loc_14000B75E
0x14000b505  mov     edx, 36h ; '6'
0x14000b50a  jmp     loc_14000B6AF
0x14000b50f  mov     rax, [rbp+110h+var_158]
0x14000b513  movups  xmm0, [rbp+110h+var_180]
0x14000b517  mov     [rdi+0C08h], rax
0x14000b51e  movups  xmm1, [rbp+110h+var_170]
0x14000b522  mov     rax, [rbp+110h+var_150]
0x14000b526  mov     [rdi+0C10h], rax
0x14000b52d  movdqu  xmmword ptr [rdi+0AB0h], xmm0
0x14000b535  movdqu  xmmword ptr [rdi+0AC0h], xmm1
0x14000b53d  cmp     [rdi+0B50h], r15b
0x14000b544  jz      short loc_14000B54F
0x14000b546  mov     al, [rbp+110h+var_15A]
0x14000b549  mov     [rdi+0B51h], al
0x14000b54f  movups  xmm0, [rbp+110h+var_148]
0x14000b553  mov     esi, [rdi+7B0h]
0x14000b559  movups  xmm1, [rbp+110h+var_138]
0x14000b55d  movups  xmmword ptr [rdi+720h], xmm0
0x14000b564  movups  xmm0, [rbp+110h+var_128]
0x14000b568  movups  xmmword ptr [rdi+730h], xmm1
0x14000b56f  movups  xmm1, [rbp+110h+var_118]
0x14000b573  movups  xmmword ptr [rdi+740h], xmm0
0x14000b57a  movups  xmm0, [rbp+110h+var_108]
0x14000b57e  movups  xmmword ptr [rdi+750h], xmm1
0x14000b585  movups  xmm1, [rbp+110h+var_F8]
0x14000b589  movups  xmmword ptr [rdi+760h], xmm0
0x14000b590  movups  xmm0, [rbp+110h+var_E8]
0x14000b594  movups  xmmword ptr [rdi+770h], xmm1
0x14000b59b  movsd   xmm1, [rbp+110h+var_D8]
0x14000b5a0  movups  xmmword ptr [rdi+780h], xmm0
0x14000b5a7  movsd   qword ptr [rdi+790h], xmm1
0x14000b5af  cmp     esi, 0FFFFFFFFh
0x14000b5b2  jnz     short loc_14000B5BD
0x14000b5b4  mov     esi, [rbp+110h+var_160]
0x14000b5b7  mov     [rdi+7B0h], esi
0x14000b5bd  lea     rdx, [rsp+210h+ProcNumber]; ProcNumber
0x14000b5c2  mov     ecx, esi; ProcIndex
0x14000b5c4  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14000b5cb  nop     dword ptr [rax+rax+00h]
0x14000b5d0  test    eax, eax
0x14000b5d2  js      short loc_14000B60C
0x14000b5d4  movzx   eax, [rsp+210h+ProcNumber.Group]
0x14000b5d9  lea     rdx, [rbp+110h+PreviousAffinity]; PreviousAffinity
0x14000b5dd  mov     cl, [rsp+210h+ProcNumber.Number]
0x14000b5e1  xorps   xmm0, xmm0
0x14000b5e4  movups  xmmword ptr [rsp+210h+Affinity.Mask], xmm0
0x14000b5e9  mov     [rsp+210h+Affinity.Group], ax
0x14000b5ee  mov     eax, 1
0x14000b5f3  shl     rax, cl
0x14000b5f6  lea     rcx, [rsp+210h+Affinity]; Affinity
0x14000b5fb  mov     [rsp+210h+Affinity.Mask], rax
0x14000b600  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14000b607  nop     dword ptr [rax+rax+00h]
0x14000b60c  cmp     [rdi+0B51h], r15b
0x14000b613  jz      short loc_14000B634
0x14000b615  mov     edx, [rdi+7B4h]
0x14000b61b  test    edx, edx
0x14000b61d  jz      short loc_14000B634
0x14000b61f  mov     r8b, 1
0x14000b622  mov     rcx, rdi
0x14000b625  call    KmclpAllocateBounceBlock
0x14000b62a  mov     ebx, eax
0x14000b62c  test    eax, eax
0x14000b62e  js      loc_14000B75E
0x14000b634  cmp     [rdi+6C1h], r15b
0x14000b63b  jnz     short loc_14000B677
0x14000b63d  mov     rcx, rdi
0x14000b640  call    InOpenChannel
0x14000b645  mov     ebx, eax
0x14000b647  test    eax, eax
0x14000b649  jns     short loc_14000B677
0x14000b64b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b652  cmp     rcx, r12
0x14000b655  jz      loc_14000B75E
0x14000b65b  mov     eax, [rcx+2Ch]
0x14000b65e  test    al, 1
0x14000b660  jz      loc_14000B75E
0x14000b666  cmp     byte ptr [rcx+29h], 2
0x14000b66a  jb      loc_14000B75E
0x14000b670  mov     edx, 37h ; '7'
0x14000b675  jmp     short loc_14000B6AF
0x14000b677  mov     rcx, rdi
0x14000b67a  call    KmclpInitializeVmbusConnection
0x14000b67f  mov     ebx, eax
0x14000b681  test    eax, eax
0x14000b683  jns     short loc_14000B6C4
0x14000b685  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b68c  cmp     rcx, r12
0x14000b68f  jz      loc_14000B75E
0x14000b695  mov     eax, [rcx+2Ch]
0x14000b698  test    al, 1
0x14000b69a  jz      loc_14000B75E
0x14000b6a0  cmp     byte ptr [rcx+29h], 2
0x14000b6a4  jb      loc_14000B75E
0x14000b6aa  mov     edx, 38h ; '8'
0x14000b6af  mov     rcx, [rcx+18h]
0x14000b6b3  mov     r9, rdi
0x14000b6b6  mov     dword ptr [rsp+210h+Timeout], ebx
0x14000b6ba  call    WPP_SF_qd
0x14000b6bf  jmp     loc_14000B75E
0x14000b6c4  mov     r13d, [rdi+7A8h]
0x14000b6cb  mov     r12d, [rdi+7ACh]
0x14000b6d2  lea     eax, [r13+1]
0x14000b6d6  lea     r14d, [r12+1]
0x14000b6db  mov     [rdi+0A98h], eax
0x14000b6e1  lea     ecx, [r14+rax]
0x14000b6e5  mov     [rdi+0A9Ch], r14d
0x14000b6ec  cmp     [rdi+0B08h], r15b
0x14000b6f3  jz      loc_14000B7D2
0x14000b6f9  mov     rax, [rdi+0B40h]
0x14000b700  lea     r15, [rdi+0A90h]
0x14000b707  mov     edx, ecx
0x14000b709  mov     r9, r15
0x14000b70c  mov     rcx, [rdi+0B18h]
0x14000b713  mov     r8d, r14d
0x14000b716  call    _guard_dispatch_icall
0x14000b71b  mov     ebx, eax
0x14000b71d  test    eax, eax
0x14000b71f  jns     loc_14000B835
0x14000b725  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b72c  lea     r12, WPP_GLOBAL_Control
0x14000b733  cmp     rcx, r12
0x14000b736  jz      short loc_14000B75A
0x14000b738  mov     eax, [rcx+2Ch]
0x14000b73b  test    al, 1
0x14000b73d  jz      short loc_14000B75A
0x14000b73f  cmp     byte ptr [rcx+29h], 2
0x14000b743  jb      short loc_14000B75A
0x14000b745  mov     rcx, [rcx+18h]
0x14000b749  mov     edx, 39h ; '9'
0x14000b74e  mov     r9, rdi
0x14000b751  mov     dword ptr [rsp+210h+Timeout], ebx
0x14000b755  call    WPP_SF_qd
0x14000b75a  test    ebx, ebx
0x14000b75c  jns     short loc_14000B76E
0x14000b75e  mov     rcx, rdi
0x14000b761  call    KmclpTeardownOpenChannelState
0x14000b766  mov     rcx, rdi; BugCheckParameter2
0x14000b769  call    KmclpDisableClosedChannel
0x14000b76e  lea     rcx, [rbp+110h+PreviousAffinity]; PreviousAffinity
0x14000b772  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14000b779  nop     dword ptr [rax+rax+00h]
0x14000b77e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b785  cmp     rcx, r12
0x14000b788  jz      short loc_14000B7AC
0x14000b78a  mov     eax, [rcx+2Ch]
0x14000b78d  test    al, 1
0x14000b78f  jz      short loc_14000B7AC
0x14000b791  cmp     byte ptr [rcx+29h], 4
0x14000b795  jb      short loc_14000B7AC
0x14000b797  mov     rcx, [rcx+18h]
0x14000b79b  mov     edx, 3Fh ; '?'
0x14000b7a0  mov     r9, rdi
0x14000b7a3  mov     dword ptr [rsp+210h+Timeout], ebx
0x14000b7a7  call    WPP_SF_qd
0x14000b7ac  mov     eax, ebx
0x14000b7ae  mov     rcx, [rbp+110h+var_50]
0x14000b7b5  xor     rcx, rsp; StackCookie
0x14000b7b8  call    __security_check_cookie
0x14000b7bd  add     rsp, 1D8h
0x14000b7c4  pop     r15
0x14000b7c6  pop     r14
0x14000b7c8  pop     r13
0x14000b7ca  pop     r12
0x14000b7cc  pop     rdi
0x14000b7cd  pop     rsi
0x14000b7ce  pop     rbx
0x14000b7cf  pop     rbp
0x14000b7d0  retn
0x14000b7d2  mov     dword ptr [rsp+210h+var_1C8], ecx
0x14000b7d6  lea     rax, [rsp+210h+var_1CC]
0x14000b7db  mov     rcx, rdi
0x14000b7de  mov     dword ptr [rsp+210h+var_1E8], 4
0x14000b7e6  mov     r9d, 8
0x14000b7ec  mov     [rsp+210h+Timeout], rax
0x14000b7f1  lea     r8, [rsp+210h+var_1C8]
0x14000b7f6  mov     [rsp+210h+var_1CC], r15d
0x14000b7fb  mov     edx, 3EC02Eh
0x14000b800  mov     dword ptr [rsp+210h+var_1C8+4], r14d
0x14000b805  call    KmclpSynchronousIoControl
0x14000b80a  mov     ebx, eax
0x14000b80c  test    eax, eax
0x14000b80e  js      loc_14000B725
0x14000b814  mov     rax, [rdi+990h]
0x14000b81b  lea     r15, [rdi+0A90h]
0x14000b822  mov     edx, [rsp+210h+var_1CC]
0x14000b826  mov     r8, r15
0x14000b829  mov     rcx, [rdi+940h]
0x14000b830  call    _guard_dispatch_icall
0x14000b835  cmp     byte ptr [rdi+6C1h], 0
0x14000b83c  jnz     loc_14000B8C6
0x14000b842  mov     r9, [r15]
0x14000b845  lea     rcx, [rdi+40h]; void *
0x14000b849  mov     [rsp+210h+var_1E0], r12d; int
0x14000b84e  shl     r14d, 0Ch
0x14000b852  mov     edx, r14d
0x14000b855  add     rdx, r9
0x14000b858  lea     rax, [r9+1000h]
0x14000b85f  mov     [rsp+210h+var_1E8], rax; __int64
0x14000b864  mov     [rsp+210h+Timeout], r9; __int64
0x14000b869  mov     r9d, r13d
0x14000b86c  lea     r8, [rdx+1000h]
0x14000b873  call    PkInitializeRingBuffer
0x14000b878  xor     r14d, r14d
0x14000b87b  mov     ebx, eax
0x14000b87d  test    eax, eax
0x14000b87f  jns     short loc_14000B8B6
0x14000b881  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b888  lea     r12, WPP_GLOBAL_Control
0x14000b88f  cmp     rcx, r12
0x14000b892  jz      loc_14000BA9F
0x14000b898  mov     eax, [rcx+2Ch]
0x14000b89b  test    al, 1
0x14000b89d  jz      loc_14000BA9F
0x14000b8a3  cmp     byte ptr [rcx+29h], 2
0x14000b8a7  jb      loc_14000BA9F
0x14000b8ad  lea     edx, [r14+3Ah]
0x14000b8b1  jmp     loc_14000BA8F
0x14000b8b6  lea     rax, [rdi+1E8h]
0x14000b8bd  mov     [rdi+0D8h], rax
0x14000b8c4  jmp     short loc_14000B8C9
0x14000b8c6  xor     r14d, r14d
0x14000b8c9  lea     rbx, [rdi+0AF8h]
0x14000b8d0  xor     edx, edx
  ... truncated ...
```
