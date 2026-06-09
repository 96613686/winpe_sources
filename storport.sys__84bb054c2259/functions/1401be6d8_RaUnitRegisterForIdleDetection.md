# RaUnitRegisterForIdleDetection

- ea: `0x1401be6d8`
- end: `0x1401be8c3`
- name: `RaUnitRegisterForIdleDetection`
- size: `491`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140047ab4`

## callees

- `0x140004cb4`
- `0x140005c50`
- `0x140012174`
- `0x1400290b0`
- `0x1400324bc`
- `0x14003c3e0`
- `0x140080ca8`
- `0x14009d424`
- `0x1400a2a44`
- `0x1400a4c30`
- `0x14014b400`
- `0x1401be6d8`

## import_xrefs

- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x1401c51b7`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x1401c51b7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401c4fbe`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401c4fbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c50b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c50b5`
- `ntoskrnl!PoRegisterCoalescingCallback` at `0x1401c5186`
- `ntoskrnl!PoRegisterCoalescingCallback` at `0x1401c5186`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401be7ad`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401be80b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401be7ad`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401be80b`
- `ntoskrnl!PoFxSetComponentResidency` at `0x1401c5079`
- `ntoskrnl!PoFxSetComponentResidency` at `0x1401c5079`
- `ntoskrnl!ExAllocateTimer` at `0x1401c51d7`
- `ntoskrnl!ExAllocateTimer` at `0x1401c51fb`
- `ntoskrnl!ExAllocateTimer` at `0x1401c51d7`
- `ntoskrnl!ExAllocateTimer` at `0x1401c51fb`
- `ntoskrnl!PoFxStartDevicePowerManagement` at `0x1401c5158`
- `ntoskrnl!PoFxStartDevicePowerManagement` at `0x1401c5158`
- `ntoskrnl!PoFxSetComponentLatency` at `0x1401c5064`
- `ntoskrnl!PoFxSetComponentLatency` at `0x1401c5064`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1401c5093`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1401c5093`

## pseudocode

```c
__int64 __fastcall RaUnitRegisterForIdleDetection(PVOID Context, __int64 a2)
{
  int v2; // esi
  __int64 v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // r8
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // r14
  int v12; // r15d
  int v13; // ebx
  int v14; // r12d
  int v15; // r8d
  __int64 *v16; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  char v20; // si
  unsigned __int8 v21; // al
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 Pool; // rax
  _QWORD *v26; // rbx
  unsigned int v27; // ecx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  unsigned int *v31; // rdx
  unsigned int v32; // eax
  __int64 v33; // r8
  __int64 v34; // rbx
  __int64 v35; // rbx
  int v36; // [rsp+80h] [rbp-19h]
  int v37; // [rsp+84h] [rbp-15h]
  __int128 v38; // [rsp+88h] [rbp-11h] BYREF
  __int64 v39; // [rsp+98h] [rbp-1h]
  __int128 v40; // [rsp+A0h] [rbp+7h] BYREF

  v2 = 0;
  LOBYTE(v36) = -1;
  v37 = 0;
  if ( RuntimePowerDisabled )
  {
    *((_BYTE *)Context + 507) |= 0x20u;
    goto LABEL_12;
  }
  v5 = *((_QWORD *)Context + 3);
  if ( !v5 || (*(_BYTE *)(v5 + 108) & 8) != 0 || *((_DWORD *)Context + 486) == 1 )
    goto LABEL_24;
  if ( !(unsigned __int8)RaidUnitCheckAndAcquirePoFx(Context) )
  {
    if ( (unsigned __int8)RaidUnitIsRegisteredForIdleDetection(Context) )
    {
      v2 = -1073741738;
      goto LABEL_12;
    }
    v21 = _interlockedbittestandset((volatile signed __int32 *)Context + 128, 0);
    v37 = v21;
    if ( !v21 )
    {
      *((_BYTE *)Context + 505) ^= (*((_BYTE *)Context + 505) ^ (4 * (*(_DWORD *)(a2 + 8) >> 1))) & 4;
      if ( (unsigned __int8)RaidIsUnitControlSupported(Context, 4) )
      {
        v24 = *((_QWORD *)Context + 3);
        v40 = 0;
        v39 = 0;
        v38 = 0;
        LOWORD(v40) = 1;
        DWORD1(v40) = 4;
        WORD1(v40) = *(_WORD *)(v24 + 56);
        WORD4(v40) = *((_WORD *)Context + 52);
        BYTE10(v40) = *((_BYTE *)Context + 106);
        *((_QWORD *)&v38 + 1) = &v40;
        *(_QWORD *)&v38 = 0x1800000001LL;
        LOBYTE(v39) = 1;
        v2 = RaCallMiniportUnitControl(v24 + 360, 4, &v38);
      }
      if ( *((_QWORD *)Context + 234) )
      {
LABEL_51:
        if ( v2 >= 0 )
          goto LABEL_52;
LABEL_38:
        *((_BYTE *)Context + 505) &= ~4u;
LABEL_39:
        LOBYTE(v22) = (*((_BYTE *)Context + 505) & 4) != 0;
        RaidSetD3Cold(*((_QWORD *)Context + 1), v22);
        goto LABEL_12;
      }
      if ( (*(_BYTE *)(v5 + 104) & 0x20) != 0 )
      {
        v20 = 0;
        if ( (*(_BYTE *)(v5 + 110) & 0x40) == 0 )
          goto LABEL_26;
      }
      else
      {
        if ( (*(_BYTE *)(v5 + 110) & 0x40) == 0 )
        {
          v2 = -1073741637;
          goto LABEL_38;
        }
        v20 = 0;
      }
      v18 = *(_QWORD *)(v5 + 5024);
      if ( v18 && (*(_DWORD *)(v18 + 20) & 0x100) == 0 )
      {
        v20 = 1;
        v19 = 296;
LABEL_42:
        Pool = RaidAllocatePool(64, v19, 1330667858, *((_QWORD *)Context + 1));
        v26 = (_QWORD *)Pool;
        if ( Pool )
        {
          v27 = *(_DWORD *)(Pool + 32) & 0xFFFFFFFB;
          *(_DWORD *)(Pool + 16) = 0;
          *(_DWORD *)(Pool + 32) = v27 | 0xA;
          *(_QWORD *)(Pool + 88) = Pool + 80;
          *(_QWORD *)(Pool + 80) = Pool + 80;
          KeInitializeSpinLock((PKSPIN_LOCK)(Pool + 96));
          v26[1] = v26 + 23;
          *((_DWORD *)v26 + 47) = 16;
          *((_DWORD *)v26 + 46) = 1;
          *((_DWORD *)v26 + 48) = 1;
          *((_DWORD *)v26 + 52) = 1;
          *((_DWORD *)v26 + 50) = 1;
          *((_DWORD *)v26 + 51) = 32;
          *(_OWORD *)(v26 + 27) = xmmword_14015A8D8;
          *((_DWORD *)v26 + 58) = 1;
          *((_DWORD *)v26 + 59) = 32;
          v26[30] = 0;
          v26[31] = 0;
          *((_DWORD *)v26 + 64) = -1;
          if ( v20 )
          {
            *((_DWORD *)v26 + 49) |= 0x100u;
            *((_DWORD *)v26 + 52) = 2;
            *((_DWORD *)v26 + 66) = 1;
            *((_DWORD *)v26 + 67) = 32;
            v26[34] = 0;
            v26[35] = 0;
            *((_DWORD *)v26 + 72) = -1;
            *((_DWORD *)v26 + 8) |= 0x1000u;
          }
          v2 = RaidRegisterForRuntimePowerManagement(*((_QWORD *)Context + 1), v26 + 23, Context, v26);
          if ( v2 >= 0 )
          {
            if ( *v26 )
            {
              PoFxSetComponentLatency(*v26, 0, -1);
              PoFxSetComponentResidency(*v26, 0, -1);
              v28 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)Context + 233);
              *((_QWORD *)Context + 234) = v26;
              ExReInitializeRundownProtectionCacheAware(v28);
              *((_BYTE *)Context + 505) |= 0x80u;
LABEL_52:
              *(_DWORD *)(*((_QWORD *)Context + 234) + 32LL) ^= (*(_DWORD *)(a2 + 8)
                                                               ^ *(_DWORD *)(*((_QWORD *)Context + 234) + 32LL))
                                                              & 1;
              v29 = *((_DWORD *)Context + 487);
              v30 = *((_QWORD *)Context + 234);
              if ( v29 != -1 )
                goto LABEL_60;
              v31 = *(unsigned int **)(v30 + 8);
              v23 = *v31;
              if ( (unsigned int)v23 < 2 )
                goto LABEL_59;
              v32 = v31[3];
              if ( (v32 & 0x10) != 0 )
              {
                v29 = v31[4];
                goto LABEL_60;
              }
              if ( (unsigned int)v23 >= 3 && (v32 & 0x20) != 0 )
                v29 = 0;
              else
LABEL_59:
                v29 = 300000;
LABEL_60:
              *(_DWORD *)(v30 + 24) = v29;
              LOBYTE(v23) = 1;
              *(_DWORD *)(*((_QWORD *)Context + 234) + 20LL) = *(_DWORD *)(a2 + 12);
              RaidUnitPoFxSetDeviceIdleTimeout(Context, *(unsigned int *)(a2 + 12), v23);
              PoFxStartDevicePowerManagement(**((_QWORD **)Context + 234));
              v33 = *((_QWORD *)Context + 234);
              if ( (*(_DWORD *)(v33 + 32) & 0x100) != 0 )
              {
                LOBYTE(v22) = 1;
                PoRegisterCoalescingCallback(RaidUnitIoCoalescingCallback, v22, v33 + 104, Context);
                PoRegisterPowerSettingCallback(
                  *((PDEVICE_OBJECT *)Context + 1),
                  &GUID_ACDC_POWER_SOURCE,
                  RaidUnitPowerSettingCallback,
                  Context,
                  (PVOID *)(*((_QWORD *)Context + 234) + 112LL));
                v34 = *((_QWORD *)Context + 234);
                *(_QWORD *)(v34 + 120) = ExAllocateTimer(RaidUnitPowerCycleCheck, Context, 0);
                v35 = *((_QWORD *)Context + 234);
                *(_QWORD *)(v35 + 128) = ExAllocateTimer(RaidUnitEndMaintenanceTime, Context, 0);
              }
              goto LABEL_39;
            }
            v2 = -1073741823;
          }
          ExFreePoolWithTag(v26, 0x4F506152u);
        }
        else
        {
          v2 = -1073741670;
        }
        goto LABEL_51;
      }
LABEL_26:
      v19 = 264;
      goto LABEL_42;
    }
LABEL_24:
    v2 = -1073741823;
    goto LABEL_12;
  }
  v6 = *((_QWORD *)Context + 234);
  v7 = *(_DWORD *)(a2 + 12);
  if ( v7 != *(_DWORD *)(v6 + 20) )
  {
    *(_DWORD *)(v6 + 20) = v7;
    if ( _bittest((const signed __int32 *)(*((_QWORD *)Context + 234) + 32LL), 8u) )
      RaidUnitAdaptiveIdleTimeout(Context);
    else
      RaidUnitPoFxSetDeviceIdleTimeout(Context, *(unsigned int *)(a2 + 12), 0);
  }
  v8 = *((_QWORD *)Context + 234);
  v9 = *(_DWORD *)(v8 + 32);
  if ( (((unsigned __int8)v9 ^ *(_BYTE *)(a2 + 8)) & 1) != 0 )
    *(_DWORD *)(v8 + 32) = v9 ^ (v9 ^ *(_DWORD *)(a2 + 8)) & 1;
  ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 233));
LABEL_12:
  if ( StorEtwLoggingEnabled )
  {
    v10 = *((_QWORD *)Context + 3);
    LODWORD(v11) = 0;
    LOBYTE(v12) = 0;
    LOBYTE(v13) = 0;
    LOBYTE(v14) = 0;
    if ( v10 )
      v36 = *(_DWORD *)(v10 + 56);
    if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(Context) )
    {
      v16 = (__int64 *)*((_QWORD *)Context + 234);
      v11 = *v16;
      v13 = v16[4] & 1;
      v14 = *((_DWORD *)v16 + 5);
      v12 = *(_DWORD *)(v16[1] + 24);
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 233));
    }
    if ( (byte_140177432 & 0x10) != 0 )
      McTemplateK0pquuudttqqttq_EtwWriteTransfer(
        *(_DWORD *)(a2 + 8) & 1,
        (*(_DWORD *)(a2 + 8) >> 1) & 1,
        v15,
        v11,
        v36,
        *((_BYTE *)Context + 104),
        *((_BYTE *)Context + 105),
        *((_BYTE *)Context + 106),
        v2,
        (*(_DWORD *)(a2 + 8) & 2) != 0,
        *(_BYTE *)(a2 + 8) & 1,
        *(_DWORD *)(a2 + 12),
        v12,
        (*((_BYTE *)Context + 505) & 4) != 0,
        v13,
        v14);
  }
  if ( !v37 )
    *((_DWORD *)Context + 128) &= ~1u;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1401be6d8  mov     [rsp-8+arg_10], rbx
0x1401be6dd  push    rbp
0x1401be6de  push    rsi
0x1401be6df  push    rdi
0x1401be6e0  push    r12
0x1401be6e2  push    r13
0x1401be6e4  push    r14
0x1401be6e6  push    r15
0x1401be6e8  lea     rbp, [rsp-27h]
0x1401be6ed  sub     rsp, 0C0h
0x1401be6f4  mov     rax, cs:__security_cookie
0x1401be6fb  xor     rax, rsp
0x1401be6fe  mov     [rbp+57h+var_40], rax
0x1401be702  xor     esi, esi
0x1401be704  mov     [rbp+57h+var_70], 0FFFFFFFFh
0x1401be70b  cmp     cs:RuntimePowerDisabled, sil
0x1401be712  mov     r13, rdx
0x1401be715  mov     rdi, rcx
0x1401be718  mov     [rbp+57h+var_6C], esi
0x1401be71b  lea     r14d, [rsi+1]
0x1401be71f  jnz     loc_1401BE862
0x1401be725  mov     rbx, [rcx+18h]
0x1401be729  test    rbx, rbx
0x1401be72c  jz      loc_1401BE874
0x1401be732  test    byte ptr [rbx+6Ch], 8
0x1401be736  jnz     loc_1401BE874
0x1401be73c  cmp     [rcx+798h], r14d
0x1401be743  jz      loc_1401BE874
0x1401be749  call    RaidUnitCheckAndAcquirePoFx
0x1401be74e  test    al, al
0x1401be750  jz      loc_1401C4E4E
0x1401be756  mov     rcx, [rdi+750h]
0x1401be75d  mov     eax, [r13+0Ch]
0x1401be761  cmp     eax, [rcx+14h]
0x1401be764  jz      short loc_1401BE78A
0x1401be766  mov     [rcx+14h], eax
0x1401be769  mov     rcx, rdi
0x1401be76c  mov     rax, [rdi+750h]
0x1401be773  bt      dword ptr [rax+20h], 8
0x1401be778  jb      loc_1401BE858
0x1401be77e  mov     edx, [r13+0Ch]
0x1401be782  xor     r8d, r8d
0x1401be785  call    RaidUnitPoFxSetDeviceIdleTimeout
0x1401be78a  mov     r8, [rdi+750h]
0x1401be791  mov     ecx, [r13+8]
0x1401be795  mov     eax, ecx
0x1401be797  mov     edx, [r8+20h]
0x1401be79b  xor     eax, edx
0x1401be79d  test    r14b, al
0x1401be7a0  jnz     loc_1401BE894
0x1401be7a6  mov     rcx, [rdi+748h]; RunRefCacheAware
0x1401be7ad  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401be7b4  nop     dword ptr [rax+rax+00h]
0x1401be7b9  cmp     cs:StorEtwLoggingEnabled, 0
0x1401be7c0  jz      short loc_1401BE824
0x1401be7c2  mov     rax, [rdi+18h]
0x1401be7c6  xor     r14d, r14d
0x1401be7c9  xor     r15d, r15d
0x1401be7cc  xor     ebx, ebx
0x1401be7ce  xor     r12d, r12d
0x1401be7d1  test    rax, rax
0x1401be7d4  jz      short loc_1401BE7DC
0x1401be7d6  mov     eax, [rax+38h]
0x1401be7d9  mov     [rbp+57h+var_70], eax
0x1401be7dc  mov     rcx, rdi
0x1401be7df  call    RaidUnitCheckAndAcquirePoFx
0x1401be7e4  test    al, al
0x1401be7e6  jz      short loc_1401BE817
0x1401be7e8  mov     rcx, [rdi+750h]
0x1401be7ef  mov     rax, [rcx+8]
0x1401be7f3  mov     ebx, [rcx+20h]
0x1401be7f6  mov     r14, [rcx]
0x1401be7f9  and     ebx, 1
0x1401be7fc  mov     r12d, [rcx+14h]
0x1401be800  mov     rcx, [rdi+748h]; RunRefCacheAware
0x1401be807  mov     r15d, [rax+18h]
0x1401be80b  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401be812  nop     dword ptr [rax+rax+00h]
0x1401be817  test    cs:byte_140177432, 10h
0x1401be81e  jnz     loc_1401C521D
0x1401be824  cmp     [rbp+57h+var_6C], 0
0x1401be828  jz      loc_1401BE8B7
0x1401be82e  mov     eax, esi
0x1401be830  mov     rcx, [rbp+57h+var_40]
0x1401be834  xor     rcx, rsp; StackCookie
0x1401be837  call    __security_check_cookie
0x1401be83c  mov     rbx, [rsp+0F0h+arg_10]
0x1401be844  add     rsp, 0C0h
0x1401be84b  pop     r15
0x1401be84d  pop     r14
0x1401be84f  pop     r13
0x1401be851  pop     r12
0x1401be853  pop     rdi
0x1401be854  pop     rsi
0x1401be855  pop     rbp
0x1401be856  retn
0x1401be858  call    RaidUnitAdaptiveIdleTimeout
0x1401be85d  jmp     loc_1401BE78A
0x1401be862  mov     r14d, 20h ; ' '
0x1401be868  or      [rcx+1FBh], r14b
0x1401be86f  jmp     loc_1401BE7B9
0x1401be874  mov     esi, 0C0000001h
0x1401be879  jmp     loc_1401BE7B9
0x1401be87e  mov     rax, [rbx+13A0h]
0x1401be885  test    rax, rax
0x1401be888  jnz     short loc_1401BE8A4
0x1401be88a  mov     edx, 108h
0x1401be88f  jmp     loc_1401C4F7C
0x1401be894  xor     ecx, edx
0x1401be896  and     ecx, r14d
0x1401be899  xor     ecx, edx
0x1401be89b  mov     [r8+20h], ecx
0x1401be89f  jmp     loc_1401BE7A6
0x1401be8a4  test    [rax+14h], r12d
0x1401be8a8  jnz     short loc_1401BE88A
0x1401be8aa  mov     sil, 1
0x1401be8ad  mov     edx, 128h
0x1401be8b2  jmp     loc_1401C4F7C
0x1401be8b7  and     dword ptr [rdi+200h], 0FFFFFFFEh
0x1401be8be  jmp     loc_1401BE82E
0x1401c4e4e  mov     rcx, rdi
0x1401c4e51  call    RaidUnitIsRegisteredForIdleDetection
0x1401c4e56  test    al, al
0x1401c4e58  jnz     loc_1401C5213
0x1401c4e5e  lock bts dword ptr [rdi+200h], 0
0x1401c4e67  setb    al
0x1401c4e6a  movzx   ecx, al
0x1401c4e6d  mov     [rbp+57h+var_6C], ecx
0x1401c4e70  test    al, al
0x1401c4e72  jnz     loc_1401BE874
0x1401c4e78  mov     cl, [rdi+1F9h]
0x1401c4e7e  mov     r12d, 4
0x1401c4e84  mov     eax, [r13+8]
0x1401c4e88  mov     edx, r12d
0x1401c4e8b  shr     eax, 1
0x1401c4e8d  shl     al, 2
0x1401c4e90  xor     al, cl
0x1401c4e92  and     al, r12b
0x1401c4e95  xor     al, cl
0x1401c4e97  mov     rcx, rdi
0x1401c4e9a  mov     [rdi+1F9h], al
0x1401c4ea0  call    RaidIsUnitControlSupported
0x1401c4ea5  lea     r15d, [r12+14h]
0x1401c4eaa  test    al, al
0x1401c4eac  jz      short loc_1401C4F0F
0x1401c4eae  mov     rcx, [rdi+18h]
0x1401c4eb2  lea     r8, [rbp+57h+var_68]
0x1401c4eb6  xor     eax, eax
0x1401c4eb8  xorps   xmm0, xmm0
0x1401c4ebb  movups  [rbp+57h+var_50], xmm0
0x1401c4ebf  mov     [rbp+57h+var_58], rax
0x1401c4ec3  mov     edx, r12d
0x1401c4ec6  movups  [rbp+57h+var_68], xmm0
0x1401c4eca  mov     word ptr [rbp+57h+var_50], r14w
0x1401c4ecf  mov     dword ptr [rbp+57h+var_50+4], r12d
0x1401c4ed3  movzx   eax, word ptr [rcx+38h]
0x1401c4ed7  add     rcx, 168h
0x1401c4ede  mov     word ptr [rbp+57h+var_50+2], ax
0x1401c4ee2  mov     al, [rdi+68h]
0x1401c4ee5  mov     byte ptr [rbp+57h+var_50+8], al
0x1401c4ee8  mov     al, [rdi+69h]
0x1401c4eeb  mov     byte ptr [rbp+57h+var_50+9], al
0x1401c4eee  mov     al, [rdi+6Ah]
0x1401c4ef1  mov     byte ptr [rbp+57h+var_50+0Ah], al
0x1401c4ef4  lea     rax, [rbp+57h+var_50]
0x1401c4ef8  mov     qword ptr [rbp+57h+var_68+8], rax
0x1401c4efc  mov     dword ptr [rbp+57h+var_68], r14d
0x1401c4f00  mov     dword ptr [rbp+57h+var_68+4], r15d
0x1401c4f04  mov     byte ptr [rbp+57h+var_58], r14b
0x1401c4f08  call    RaCallMiniportUnitControl
0x1401c4f0d  mov     esi, eax
0x1401c4f0f  cmp     qword ptr [rdi+750h], 0
0x1401c4f17  mov     r14d, 20h ; ' '
0x1401c4f1d  mov     r12d, 100h
0x1401c4f23  jnz     loc_1401C50C8
0x1401c4f29  test    [rbx+68h], r14b
0x1401c4f2d  jnz     short loc_1401C4F6A
0x1401c4f2f  test    byte ptr [rbx+6Eh], 40h
0x1401c4f33  jz      short loc_1401C4F3D
0x1401c4f35  xor     sil, sil
0x1401c4f38  jmp     loc_1401BE87E
0x1401c4f3d  mov     esi, 0C00000BBh
0x1401c4f42  and     byte ptr [rdi+1F9h], 0FBh
0x1401c4f49  mov     r14d, 1
0x1401c4f4f  mov     dl, [rdi+1F9h]
0x1401c4f55  mov     rcx, [rdi+8]
0x1401c4f59  shr     dl, 2
0x1401c4f5c  and     dl, r14b
0x1401c4f5f  call    RaidSetD3Cold
0x1401c4f64  nop
0x1401c4f65  jmp     loc_1401BE7B9
0x1401c4f6a  xor     sil, sil
0x1401c4f6d  test    byte ptr [rbx+6Eh], 40h
0x1401c4f71  jz      loc_1401BE88A
0x1401c4f77  jmp     loc_1401BE87E
0x1401c4f7c  mov     r9, [rdi+8]
0x1401c4f80  mov     ecx, 40h ; '@'
0x1401c4f85  mov     r8d, 4F506152h
0x1401c4f8b  call    RaidAllocatePool
0x1401c4f90  mov     rbx, rax
0x1401c4f93  test    rax, rax
0x1401c4f96  jz      loc_1401C50C3
0x1401c4f9c  mov     ecx, [rax+20h]
0x1401c4f9f  and     ecx, 0FFFFFFFBh
0x1401c4fa2  mov     dword ptr [rax+10h], 0
0x1401c4fa9  or      ecx, 0Ah
0x1401c4fac  mov     [rax+20h], ecx
0x1401c4faf  lea     rcx, [rax+50h]
0x1401c4fb3  mov     [rcx+8], rcx
0x1401c4fb7  mov     [rcx], rcx
0x1401c4fba  lea     rcx, [rax+60h]; SpinLock
0x1401c4fbe  call    cs:__imp_KeInitializeSpinLock
0x1401c4fc5  nop     dword ptr [rax+rax+00h]
0x1401c4fca  lea     rdx, [rbx+0B8h]
0x1401c4fd1  mov     r8d, 1
0x1401c4fd7  mov     [rbx+8], rdx
0x1401c4fdb  xor     ecx, ecx
0x1401c4fdd  mov     dword ptr [rdx+4], 10h
0x1401c4fe4  or      eax, 0FFFFFFFFh
0x1401c4fe7  mov     [rdx], r8d
0x1401c4fea  mov     [rdx+8], r8d
0x1401c4fee  mov     [rdx+18h], r8d
0x1401c4ff2  mov     [rdx+10h], r8d
0x1401c4ff6  mov     [rdx+14h], r14d
0x1401c4ffa  movups  xmm0, cs:xmmword_14015A8D8
0x1401c5001  movdqu  xmmword ptr [rdx+20h], xmm0
0x1401c5006  mov     [rdx+30h], r8d
0x1401c500a  mov     [rdx+34h], r14d
0x1401c500e  mov     [rdx+38h], rcx
0x1401c5012  mov     [rdx+40h], rcx
0x1401c5016  mov     [rdx+48h], eax
0x1401c5019  test    sil, sil
0x1401c501c  jz      short loc_1401C5041
0x1401c501e  or      [rdx+0Ch], r12d
0x1401c5022  mov     dword ptr [rdx+18h], 2
0x1401c5029  mov     [rdx+50h], r8d
0x1401c502d  mov     [rdx+54h], r14d
0x1401c5031  mov     [rdx+58h], rcx
0x1401c5035  mov     [rdx+60h], rcx
0x1401c5039  mov     [rdx+68h], eax
0x1401c503c  bts     dword ptr [rbx+20h], 0Ch
0x1401c5041  mov     rcx, [rdi+8]
0x1401c5045  mov     r9, rbx
0x1401c5048  mov     r8, rdi
0x1401c504b  call    RaidRegisterForRuntimePowerManagement
0x1401c5050  mov     esi, eax
0x1401c5052  test    eax, eax
0x1401c5054  js      short loc_1401C50AD
0x1401c5056  mov     rcx, [rbx]
0x1401c5059  test    rcx, rcx
0x1401c505c  jz      short loc_1401C50A8
0x1401c505e  or      r8, 0FFFFFFFFFFFFFFFFh
0x1401c5062  xor     edx, edx
0x1401c5064  call    cs:__imp_PoFxSetComponentLatency
0x1401c506b  nop     dword ptr [rax+rax+00h]
0x1401c5070  mov     rcx, [rbx]
0x1401c5073  or      r8, 0FFFFFFFFFFFFFFFFh
0x1401c5077  xor     edx, edx
0x1401c5079  call    cs:__imp_PoFxSetComponentResidency
0x1401c5080  nop     dword ptr [rax+rax+00h]
0x1401c5085  mov     rcx, [rdi+748h]; RunRefCacheAware
0x1401c508c  mov     [rdi+750h], rbx
0x1401c5093  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x1401c509a  nop     dword ptr [rax+rax+00h]
0x1401c509f  or      byte ptr [rdi+1F9h], 80h
0x1401c50a6  jmp     short loc_1401C50D0
0x1401c50a8  mov     esi, 0C0000001h
0x1401c50ad  mov     edx, 4F506152h; Tag
0x1401c50b2  mov     rcx, rbx; P
0x1401c50b5  call    cs:__imp_ExFreePoolWithTag
0x1401c50bc  nop     dword ptr [rax+rax+00h]
0x1401c50c1  jmp     short loc_1401C50C8
0x1401c50c3  mov     esi, 0C000009Ah
0x1401c50c8  test    esi, esi
0x1401c50ca  js      loc_1401C4F42
0x1401c50d0  mov     rdx, [rdi+750h]
0x1401c50d7  mov     eax, [rdx+20h]
0x1401c50da  mov     ecx, eax
0x1401c50dc  xor     ecx, [r13+8]
0x1401c50e0  and     ecx, 1
0x1401c50e3  xor     ecx, eax
0x1401c50e5  mov     [rdx+20h], ecx
0x1401c50e8  mov     eax, [rdi+79Ch]
0x1401c50ee  mov     rcx, [rdi+750h]
0x1401c50f5  cmp     eax, 0FFFFFFFFh
0x1401c50f8  jnz     short loc_1401C5127
0x1401c50fa  mov     rdx, [rcx+8]
0x1401c50fe  mov     r8d, [rdx]
0x1401c5101  cmp     r8d, 2
0x1401c5105  jb      short loc_1401C5122
0x1401c5107  mov     eax, [rdx+0Ch]
0x1401c510a  test    al, 10h
0x1401c510c  jz      short loc_1401C5113
0x1401c510e  mov     eax, [rdx+10h]
0x1401c5111  jmp     short loc_1401C5127
0x1401c5113  cmp     r8d, 3
0x1401c5117  jb      short loc_1401C5122
0x1401c5119  test    r14b, al
0x1401c511c  jz      short loc_1401C5122
0x1401c511e  xor     eax, eax
  ... truncated ...
```
