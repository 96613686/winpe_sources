# NvmeNamespaceRegisterForIdleDetection

- ea: `0x1400807f8`
- end: `0x140080c9f`
- name: `NvmeNamespaceRegisterForIdleDetection`
- size: `1191`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14011ebcc`

## callees

- `0x1400290b0`
- `0x140033454`
- `0x14003348c`
- `0x1400807f8`
- `0x140080ca8`
- `0x140080d2c`
- `0x14013e7ac`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400809c7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400809c7`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14008096f`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14008096f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080c50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080c50`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140080c14`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140080c14`
- `ntoskrnl!PoFxActivateComponent` at `0x140080bba`
- `ntoskrnl!PoFxActivateComponent` at `0x140080bba`
- `ntoskrnl!PoFxSetComponentResidency` at `0x140080ac2`
- `ntoskrnl!PoFxSetComponentResidency` at `0x140080ac2`
- `ntoskrnl!PoFxUnregisterDevice` at `0x140080c3c`
- `ntoskrnl!PoFxUnregisterDevice` at `0x140080c3c`
- `ntoskrnl!PoFxStartDevicePowerManagement` at `0x140080bd4`
- `ntoskrnl!PoFxStartDevicePowerManagement` at `0x140080bd4`
- `ntoskrnl!PoFxSetComponentLatency` at `0x140080aae`
- `ntoskrnl!PoFxSetComponentLatency` at `0x140080aae`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140080ae4`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140080ae4`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14008098f`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14008098f`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceRegisterForIdleDetection(__int64 a1, __int64 a2)
{
  __int64 v2; // rbp
  int v5; // ebx
  _QWORD *Pool; // rsi
  __int64 v7; // r15
  __int64 v8; // rax
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // r8
  int v14; // edx
  int v16; // edx
  char v17; // r12
  unsigned int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rax
  _DWORD *v25; // r15
  __int64 v26; // r8
  __int64 v27; // rdx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v28; // rcx
  _BYTE *v29; // rdx

  v2 = a1 + 16;
  if ( RuntimePowerDisabled )
  {
LABEL_2:
    v5 = 0;
LABEL_49:
    v29 = *(_BYTE **)(a1 + 128);
    if ( v29[1] == 1 || **(_BYTE **)(*(_QWORD *)(*(_QWORD *)v2 + 128LL) + 168LL) == 1 )
      *v29 = 0;
    return (unsigned int)v5;
  }
  Pool = 0;
  v7 = *(_QWORD *)(*(_QWORD *)v2 + 128LL);
  if ( (*(_DWORD *)(*(_QWORD *)(v7 + 408) + 184LL) & 0x40000000) == 0
    || (v8 = *(_QWORD *)(v7 + 168), *(_BYTE *)v8 == 1) && (*(_DWORD *)(v8 + 176) & 0x100) != 0 )
  {
    v5 = -1073741823;
    goto LABEL_42;
  }
  v9 = NvmeNamespaceCheckAndAcquirePoFx();
  v10 = *(_QWORD *)(a1 + 128);
  if ( !v9 )
  {
    if ( *(_BYTE *)(v10 + 1) == 1 )
      return 3221225558LL;
    v16 = *(_DWORD *)(v10 + 136);
    v17 = 0;
    if ( (v16 & 4) != 0 )
      v18 = v16 ^ (v16 ^ (*(_DWORD *)(a2 + 8) >> 1)) & 1;
    else
      v18 = v16 & 0xFFFFFFFE;
    *(_DWORD *)(v10 + 136) = v18;
    v19 = *(_QWORD *)(v7 + 168);
    if ( (*(_DWORD *)(v19 + 176) & 0x20) != 0
      && *(_BYTE *)v19 == 1
      && (*(_DWORD *)(*(_QWORD *)(v19 + 8) + 20LL) & 0x80u) == 0 )
    {
      v17 = 1;
      v20 = 304;
    }
    else
    {
      v20 = 272;
    }
    Pool = (_QWORD *)RaidAllocatePool(72, v20, 1330667858, *(_QWORD *)(a1 + 8));
    if ( Pool
      && (v21 = *(_QWORD *)(a1 + 128),
          *(_QWORD *)(v21 + 40) = ExAllocateCacheAwareRundownProtection(NonPagedPoolNx, 0x4F506152u),
          (v22 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(*(_QWORD *)(a1 + 128) + 40LL)) != 0) )
    {
      ExWaitForRundownProtectionReleaseCacheAware(v22);
      v23 = Pool[4] & 0xFFFFFFFD;
      *((_BYTE *)Pool + 64) = 1;
      *((_DWORD *)Pool + 4) = 0;
      *((_DWORD *)Pool + 8) = v23 | 4;
      *((_DWORD *)Pool + 5) = -1;
      Pool[11] = Pool + 10;
      Pool[10] = Pool + 10;
      KeInitializeSpinLock(Pool + 12);
      Pool[1] = Pool + 24;
      *((_DWORD *)Pool + 48) = 1;
      *((_DWORD *)Pool + 49) = 16;
      *((_DWORD *)Pool + 50) = 1;
      *((_DWORD *)Pool + 53) = 32;
      *((_DWORD *)Pool + 52) = 1;
      *((_DWORD *)Pool + 54) = 1;
      *((_OWORD *)Pool + 14) = xmmword_140156670;
      *((_DWORD *)Pool + 60) = 1;
      *((_DWORD *)Pool + 61) = 32;
      Pool[31] = 0;
      Pool[32] = 0;
      *((_DWORD *)Pool + 66) = -1;
      if ( (*(_DWORD *)(*(_QWORD *)(v7 + 408) + 184LL) & 0x40000000) != 0 )
      {
        v24 = *(_QWORD *)(v7 + 168);
        if ( *(_BYTE *)v24 == 1 && (*(_DWORD *)(*(_QWORD *)(v24 + 8) + 20LL) & 0x200) != 0 )
          *((_DWORD *)Pool + 51) |= 2u;
      }
      v25 = (_DWORD *)Pool + 51;
      if ( v17 )
      {
        *v25 |= 0x100u;
        *((_DWORD *)Pool + 54) = 2;
        *((_DWORD *)Pool + 68) = 1;
        *((_DWORD *)Pool + 69) = 32;
        Pool[35] = 0;
        Pool[36] = 0;
        *((_DWORD *)Pool + 74) = -1;
        *((_DWORD *)Pool + 8) |= 0x200u;
      }
      v5 = NvmeRegisterForRuntimePowerManagement(*(_QWORD *)(a1 + 8), Pool + 24, a1, Pool);
      if ( v5 >= 0 )
      {
        PoFxSetComponentLatency(*Pool, 0, -1);
        PoFxSetComponentResidency(*Pool, 0, -1);
        *(_QWORD *)(*(_QWORD *)(a1 + 128) + 8LL) = Pool;
        ExReInitializeRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(a1 + 128) + 40LL));
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 128) + 8LL) + 32LL) ^= (*(_DWORD *)(a2 + 8)
                                                                       ^ *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 128)
                                                                                               + 8LL)
                                                                                   + 32LL))
                                                                      & 1;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 128) + 8LL) + 24LL) = 0;
        if ( *((_DWORD *)Pool + 48) >= 2u )
        {
          v25 = (_DWORD *)Pool + 51;
          if ( (*((_DWORD *)Pool + 51) & 0x10) != 0 )
            *((_DWORD *)Pool + 6) = *((_DWORD *)Pool + 52);
        }
        if ( (*v25 & 2) != 0 )
          *((_DWORD *)Pool + 8) |= 0x400u;
        LOBYTE(v26) = 1;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 128) + 8LL) + 20LL) = *(_DWORD *)(a2 + 12);
        NvmeNamespacePoFxSetDeviceIdleTimeout(a1, *(unsigned int *)(a2 + 12), v26);
        *(_BYTE *)(*(_QWORD *)(a1 + 128) + 1LL) = 1;
        if ( **(_BYTE **)(*(_QWORD *)(*(_QWORD *)v2 + 128LL) + 168LL) == 1
          && !_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(a1 + 128) + 96LL), 1, 0) )
        {
          PoFxActivateComponent(**(_QWORD **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v2 + 128LL) + 168LL) + 8LL), 0, 0);
        }
        PoFxStartDevicePowerManagement(**(_QWORD **)(*(_QWORD *)(a1 + 128) + 8LL));
        v27 = *(unsigned int *)(*(_QWORD *)(a1 + 128) + 136LL);
        LOBYTE(v27) = v27 & 1;
        RaidSetD3Cold(*(_QWORD *)(a1 + 8), v27);
        goto LABEL_2;
      }
    }
    else
    {
      v5 = -1073741670;
    }
LABEL_42:
    v28 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(*(_QWORD *)(a1 + 128) + 40LL);
    if ( v28 )
    {
      ExFreeCacheAwareRundownProtection(v28);
      *(_QWORD *)(*(_QWORD *)(a1 + 128) + 40LL) = 0;
    }
    if ( Pool )
    {
      if ( *Pool )
        PoFxUnregisterDevice();
      ExFreePoolWithTag(Pool, 0x4F506152u);
    }
    if ( v5 == -1073741738 )
      return (unsigned int)v5;
    goto LABEL_49;
  }
  v11 = *(_QWORD *)(v10 + 8);
  v12 = *(_DWORD *)(a2 + 12);
  if ( v12 != *(_DWORD *)(v11 + 20) )
  {
    *(_DWORD *)(v11 + 20) = v12;
    NvmeNamespacePoFxSetDeviceIdleTimeout(a1, *(unsigned int *)(a2 + 12), 0);
  }
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 128) + 8LL);
  v14 = *(_DWORD *)(v13 + 32);
  if ( (((unsigned __int8)v14 ^ *(_BYTE *)(a2 + 8)) & 1) != 0 )
    *(_DWORD *)(v13 + 32) = v14 ^ (v14 ^ *(_DWORD *)(a2 + 8)) & 1;
  NvmeNamespaceReleasePoFx(a1);
  return 0;
}

```

## disassembly

```asm
0x1400807f8  push    rbx
0x1400807fa  push    rbp
0x1400807fb  push    rsi
0x1400807fc  push    rdi
0x1400807fd  push    r12
0x1400807ff  push    r13
0x140080801  push    r14
0x140080803  push    r15
0x140080805  sub     rsp, 28h
0x140080809  cmp     cs:RuntimePowerDisabled, 0
0x140080810  lea     rbp, [rcx+10h]
0x140080814  mov     r13, rdx
0x140080817  mov     rdi, rcx
0x14008081a  mov     r14d, 1
0x140080820  jz      short loc_140080829
0x140080822  xor     ebx, ebx
0x140080824  jmp     loc_140080C64
0x140080829  mov     rax, [rbp+0]
0x14008082d  xor     esi, esi
0x14008082f  mov     r15, [rax+80h]
0x140080836  mov     rax, [r15+198h]
0x14008083d  test    dword ptr [rax+0B8h], 40000000h
0x140080847  jnz     short loc_140080853
0x140080849  mov     ebx, 0C0000001h
0x14008084e  jmp     loc_140080C04
0x140080853  mov     rax, [r15+0A8h]
0x14008085a  cmp     [rax], r14b
0x14008085d  jnz     short loc_14008086B
0x14008085f  test    dword ptr [rax+0B0h], 100h
0x140080869  jnz     short loc_140080849
0x14008086b  call    NvmeNamespaceCheckAndAcquirePoFx
0x140080870  mov     rcx, [rdi+80h]
0x140080877  test    al, al
0x140080879  jz      short loc_1400808D0
0x14008087b  mov     rdx, [rcx+8]
0x14008087f  mov     eax, [r13+0Ch]
0x140080883  cmp     eax, [rdx+14h]
0x140080886  jz      short loc_14008089A
0x140080888  mov     [rdx+14h], eax
0x14008088b  xor     r8d, r8d
0x14008088e  mov     edx, [r13+0Ch]
0x140080892  mov     rcx, rdi
0x140080895  call    NvmeNamespacePoFxSetDeviceIdleTimeout
0x14008089a  mov     rax, [rdi+80h]
0x1400808a1  mov     ecx, [r13+8]
0x1400808a5  mov     r8, [rax+8]
0x1400808a9  mov     eax, ecx
0x1400808ab  mov     edx, [r8+20h]
0x1400808af  xor     eax, edx
0x1400808b1  test    r14b, al
0x1400808b4  jz      short loc_1400808C1
0x1400808b6  xor     ecx, edx
0x1400808b8  and     ecx, r14d
0x1400808bb  xor     ecx, edx
0x1400808bd  mov     [r8+20h], ecx
0x1400808c1  mov     rcx, rdi
0x1400808c4  call    NvmeNamespaceReleasePoFx
0x1400808c9  xor     eax, eax
0x1400808cb  jmp     loc_140080C8D
0x1400808d0  cmp     [rcx+1], r14b
0x1400808d4  jnz     short loc_1400808E0
0x1400808d6  mov     eax, 0C0000056h
0x1400808db  jmp     loc_140080C8D
0x1400808e0  mov     edx, [rcx+88h]
0x1400808e6  xor     r12b, r12b
0x1400808e9  test    dl, 4
0x1400808ec  jz      short loc_1400808FD
0x1400808ee  mov     eax, [r13+8]
0x1400808f2  shr     eax, 1
0x1400808f4  xor     eax, edx
0x1400808f6  and     eax, r14d
0x1400808f9  xor     eax, edx
0x1400808fb  jmp     short loc_140080902
0x1400808fd  mov     eax, edx
0x1400808ff  and     eax, 0FFFFFFFEh
0x140080902  mov     [rcx+88h], eax
0x140080908  mov     rcx, [r15+0A8h]
0x14008090f  mov     eax, [rcx+0B0h]
0x140080915  test    al, 20h
0x140080917  jz      short loc_140080933
0x140080919  cmp     [rcx], r14b
0x14008091c  jnz     short loc_140080933
0x14008091e  mov     rax, [rcx+8]
0x140080922  mov     ecx, [rax+14h]
0x140080925  test    cl, cl
0x140080927  js      short loc_140080933
0x140080929  mov     r12b, r14b
0x14008092c  mov     edx, 130h
0x140080931  jmp     short loc_140080938
0x140080933  mov     edx, 110h
0x140080938  mov     r9, [rdi+8]
0x14008093c  mov     ecx, 48h ; 'H'
0x140080941  mov     r8d, 4F506152h
0x140080947  call    RaidAllocatePool
0x14008094c  mov     rsi, rax
0x14008094f  test    rax, rax
0x140080952  jnz     short loc_14008095E
0x140080954  mov     ebx, 0C000009Ah
0x140080959  jmp     loc_140080C04
0x14008095e  mov     rbx, [rdi+80h]
0x140080965  mov     edx, 4F506152h; PoolTag
0x14008096a  mov     ecx, 200h; PoolType
0x14008096f  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140080976  nop     dword ptr [rax+rax+00h]
0x14008097b  mov     [rbx+28h], rax
0x14008097f  mov     rax, [rdi+80h]
0x140080986  mov     rcx, [rax+28h]; RunRef
0x14008098a  test    rcx, rcx
0x14008098d  jz      short loc_140080954
0x14008098f  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140080996  nop     dword ptr [rax+rax+00h]
0x14008099b  mov     eax, [rsi+20h]
0x14008099e  lea     rcx, [rsi+60h]; SpinLock
0x1400809a2  and     eax, 0FFFFFFFDh
0x1400809a5  mov     [rsi+40h], r14b
0x1400809a9  or      eax, 4
0x1400809ac  mov     dword ptr [rsi+10h], 0
0x1400809b3  mov     [rsi+20h], eax
0x1400809b6  or      ebx, 0FFFFFFFFh
0x1400809b9  lea     rax, [rsi+50h]
0x1400809bd  mov     [rsi+14h], ebx
0x1400809c0  mov     [rax+8], rax
0x1400809c4  mov     [rax], rax
0x1400809c7  call    cs:__imp_KeInitializeSpinLock
0x1400809ce  nop     dword ptr [rax+rax+00h]
0x1400809d3  lea     r14, [rsi+0C0h]
0x1400809da  mov     r8d, 1
0x1400809e0  mov     [rsi+8], r14
0x1400809e4  xor     edx, edx
0x1400809e6  mov     [r14], r8d
0x1400809e9  mov     dword ptr [r14+4], 10h
0x1400809f1  mov     [r14+8], r8d
0x1400809f5  lea     r9d, [r8+1Fh]
0x1400809f9  mov     [r14+14h], r9d
0x1400809fd  mov     [r14+10h], r8d
0x140080a01  mov     [r14+18h], r8d
0x140080a05  movups  xmm0, cs:xmmword_140156670
0x140080a0c  movdqu  xmmword ptr [r14+20h], xmm0
0x140080a12  mov     [r14+30h], r8d
0x140080a16  mov     [r14+34h], r9d
0x140080a1a  mov     [r14+38h], rdx
0x140080a1e  mov     [r14+40h], rdx
0x140080a22  mov     [r14+48h], ebx
0x140080a26  mov     rax, [r15+198h]
0x140080a2d  test    dword ptr [rax+0B8h], 40000000h
0x140080a37  jz      short loc_140080A57
0x140080a39  mov     rax, [r15+0A8h]
0x140080a40  cmp     [rax], r8b
0x140080a43  jnz     short loc_140080A57
0x140080a45  mov     rax, [rax+8]
0x140080a49  test    dword ptr [rax+14h], 200h
0x140080a50  jz      short loc_140080A57
0x140080a52  or      dword ptr [r14+0Ch], 2
0x140080a57  lea     r15, [r14+0Ch]
0x140080a5b  test    r12b, r12b
0x140080a5e  jz      short loc_140080A86
0x140080a60  bts     dword ptr [r15], 8
0x140080a65  mov     dword ptr [r14+18h], 2
0x140080a6d  mov     [r14+50h], r8d
0x140080a71  mov     [r14+54h], r9d
0x140080a75  mov     [r14+58h], rdx
0x140080a79  mov     [r14+60h], rdx
0x140080a7d  mov     [r14+68h], ebx
0x140080a81  bts     dword ptr [rsi+20h], 9
0x140080a86  mov     rcx, [rdi+8]
0x140080a8a  mov     r9, rsi
0x140080a8d  mov     r8, rdi
0x140080a90  mov     rdx, r14
0x140080a93  call    NvmeRegisterForRuntimePowerManagement
0x140080a98  mov     ebx, eax
0x140080a9a  test    eax, eax
0x140080a9c  js      loc_140080BFE
0x140080aa2  mov     rcx, [rsi]
0x140080aa5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140080aa9  mov     r8, rbx
0x140080aac  xor     edx, edx
0x140080aae  call    cs:__imp_PoFxSetComponentLatency
0x140080ab5  nop     dword ptr [rax+rax+00h]
0x140080aba  mov     rcx, [rsi]
0x140080abd  mov     r8, rbx
0x140080ac0  xor     edx, edx
0x140080ac2  call    cs:__imp_PoFxSetComponentResidency
0x140080ac9  nop     dword ptr [rax+rax+00h]
0x140080ace  mov     rax, [rdi+80h]
0x140080ad5  mov     [rax+8], rsi
0x140080ad9  mov     rcx, [rdi+80h]
0x140080ae0  mov     rcx, [rcx+28h]; RunRefCacheAware
0x140080ae4  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140080aeb  nop     dword ptr [rax+rax+00h]
0x140080af0  mov     rax, [rdi+80h]
0x140080af7  mov     rdx, [rax+8]
0x140080afb  mov     eax, [rdx+20h]
0x140080afe  mov     ecx, eax
0x140080b00  xor     ecx, [r13+8]
0x140080b04  and     ecx, 1
0x140080b07  xor     ecx, eax
0x140080b09  mov     [rdx+20h], ecx
0x140080b0c  mov     rax, [rdi+80h]
0x140080b13  mov     rcx, [rax+8]
0x140080b17  mov     dword ptr [rcx+18h], 0
0x140080b1e  cmp     dword ptr [r14], 2
0x140080b22  jb      short loc_140080B36
0x140080b24  lea     r15, [r14+0Ch]
0x140080b28  mov     eax, [r15]
0x140080b2b  test    al, 10h
0x140080b2d  jz      short loc_140080B36
0x140080b2f  mov     eax, [r14+10h]
0x140080b33  mov     [rsi+18h], eax
0x140080b36  mov     eax, [r15]
0x140080b39  test    al, 2
0x140080b3b  jz      short loc_140080B42
0x140080b3d  bts     dword ptr [rsi+20h], 0Ah
0x140080b42  mov     rax, [rdi+80h]
0x140080b49  mov     r14d, 1
0x140080b4f  mov     r8b, r14b
0x140080b52  mov     rcx, [rax+8]
0x140080b56  mov     eax, [r13+0Ch]
0x140080b5a  mov     [rcx+14h], eax
0x140080b5d  mov     rcx, rdi
0x140080b60  mov     edx, [r13+0Ch]
0x140080b64  call    NvmeNamespacePoFxSetDeviceIdleTimeout
0x140080b69  mov     rax, [rdi+80h]
0x140080b70  mov     [rax+1], r14b
0x140080b74  mov     rax, [rbp+0]
0x140080b78  mov     rcx, [rax+80h]
0x140080b7f  mov     rax, [rcx+0A8h]
0x140080b86  cmp     [rax], r14b
0x140080b89  jnz     short loc_140080BC6
0x140080b8b  mov     rcx, [rdi+80h]
0x140080b92  xor     eax, eax
0x140080b94  lock cmpxchg [rcx+60h], r14d
0x140080b9a  jnz     short loc_140080BC6
0x140080b9c  mov     rax, [rbp+0]
0x140080ba0  xor     r8d, r8d
0x140080ba3  xor     edx, edx
0x140080ba5  mov     rcx, [rax+80h]
0x140080bac  mov     rax, [rcx+0A8h]
0x140080bb3  mov     rcx, [rax+8]
0x140080bb7  mov     rcx, [rcx]
0x140080bba  call    cs:__imp_PoFxActivateComponent
0x140080bc1  nop     dword ptr [rax+rax+00h]
0x140080bc6  mov     rax, [rdi+80h]
0x140080bcd  mov     rcx, [rax+8]
0x140080bd1  mov     rcx, [rcx]
0x140080bd4  call    cs:__imp_PoFxStartDevicePowerManagement
0x140080bdb  nop     dword ptr [rax+rax+00h]
0x140080be0  mov     rax, [rdi+80h]
0x140080be7  mov     rcx, [rdi+8]
0x140080beb  mov     edx, [rax+88h]
0x140080bf1  and     dl, r14b
0x140080bf4  call    RaidSetD3Cold
0x140080bf9  jmp     loc_140080822
0x140080bfe  mov     r14d, 1
0x140080c04  mov     rax, [rdi+80h]
0x140080c0b  mov     rcx, [rax+28h]; RunRefCacheAware
0x140080c0f  test    rcx, rcx
0x140080c12  jz      short loc_140080C2F
0x140080c14  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140080c1b  nop     dword ptr [rax+rax+00h]
0x140080c20  mov     rax, [rdi+80h]
0x140080c27  mov     qword ptr [rax+28h], 0
0x140080c2f  test    rsi, rsi
0x140080c32  jz      short loc_140080C5C
0x140080c34  mov     rcx, [rsi]
0x140080c37  test    rcx, rcx
0x140080c3a  jz      short loc_140080C48
0x140080c3c  call    cs:__imp_PoFxUnregisterDevice
0x140080c43  nop     dword ptr [rax+rax+00h]
0x140080c48  mov     edx, 4F506152h; Tag
0x140080c4d  mov     rcx, rsi; P
0x140080c50  call    cs:__imp_ExFreePoolWithTag
0x140080c57  nop     dword ptr [rax+rax+00h]
0x140080c5c  cmp     ebx, 0C0000056h
0x140080c62  jz      short loc_140080C8B
0x140080c64  mov     rdx, [rdi+80h]
0x140080c6b  cmp     [rdx+1], r14b
0x140080c6f  jz      short loc_140080C88
0x140080c71  mov     rax, [rbp+0]
0x140080c75  mov     rcx, [rax+80h]
0x140080c7c  mov     rax, [rcx+0A8h]
0x140080c83  cmp     [rax], r14b
0x140080c86  jnz     short loc_140080C8B
0x140080c88  mov     byte ptr [rdx], 0
0x140080c8b  mov     eax, ebx
0x140080c8d  add     rsp, 28h
0x140080c91  pop     r15
0x140080c93  pop     r14
0x140080c95  pop     r13
0x140080c97  pop     r12
0x140080c99  pop     rdi
0x140080c9a  pop     rsi
0x140080c9b  pop     rbp
0x140080c9c  pop     rbx
0x140080c9d  retn
```
