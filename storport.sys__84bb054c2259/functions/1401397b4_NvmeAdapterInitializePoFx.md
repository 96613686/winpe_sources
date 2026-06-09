# NvmeAdapterInitializePoFx

- ea: `0x1401397b4`
- end: `0x140139bae`
- name: `NvmeAdapterInitializePoFx`
- size: `1018`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140113f70`

## callees

- `0x1400290b0`
- `0x140033410`
- `0x140080ca8`
- `0x1400849e0`
- `0x14009ebcc`
- `0x14009ec90`
- `0x1401397b4`
- `0x140139ca4`
- `0x14013e7ac`
- `0x14014b500`

## import_xrefs

- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401398ce`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401398ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401398aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401398aa`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140139882`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140139882`
- `ntoskrnl!PoFxSetComponentResidency` at `0x140139ab5`
- `ntoskrnl!PoFxSetComponentResidency` at `0x140139ab5`
- `ntoskrnl!PoFxUnregisterDevice` at `0x140139866`
- `ntoskrnl!PoFxUnregisterDevice` at `0x140139866`
- `ntoskrnl!PoFxStartDevicePowerManagement` at `0x140139b9d`
- `ntoskrnl!PoFxStartDevicePowerManagement` at `0x140139b9d`
- `ntoskrnl!PoFxSetComponentLatency` at `0x140139aa1`
- `ntoskrnl!PoFxSetComponentLatency` at `0x140139aa1`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140139afe`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140139afe`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401398f8`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401398f8`

## pseudocode

```c
__int64 __fastcall NvmeAdapterInitializePoFx(__int64 a1, const signed __int32 *a2, bool *a3)
{
  __int64 v6; // rax
  _QWORD *Pool; // rsi
  int v9; // ebx
  unsigned int TotalStorPoFxDeviceSize; // eax
  size_t v11; // r15
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v12; // rcx
  __int64 v13; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 StorPoFxComponent; // rax
  __int64 v18; // rbx
  int v19; // r8d
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // edx
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // r8d
  int v26; // edx
  __int64 v27; // rax
  __int64 v28; // [rsp+A8h] [rbp+20h] BYREF

  v28 = 0;
  if ( RuntimePowerDisabled )
    return 0;
  v6 = *(_QWORD *)(a1 + 168);
  if ( *(_BYTE *)v6 == 1 )
  {
    if ( a3 )
      *a3 = (*(_DWORD *)(v6 + 176) & 8) != 0;
    return 0;
  }
  Pool = 0;
  v9 = NvmeRegisterForRuntimePowerManagement(*(_QWORD *)(a1 + 8), a2, a1, &v28);
  if ( v9 >= 0 )
  {
    TotalStorPoFxDeviceSize = RaidGetTotalStorPoFxDeviceSize(a2);
    v11 = TotalStorPoFxDeviceSize;
    Pool = (_QWORD *)RaidAllocatePool(72, TotalStorPoFxDeviceSize + 192, 1330667858, *(_QWORD *)(a1 + 8));
    if ( Pool )
    {
      v13 = *(_QWORD *)(a1 + 168);
      *(_QWORD *)(v13 + 80) = ExAllocateCacheAwareRundownProtection(NonPagedPoolNx, 0x4F506152u);
      v14 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(*(_QWORD *)(a1 + 168) + 80LL);
      if ( v14 )
      {
        ExWaitForRundownProtectionReleaseCacheAware(v14);
        v15 = v28;
        *((_DWORD *)Pool + 5) |= 1u;
        v16 = *((unsigned int *)Pool + 5);
        *Pool = v15;
        *((_DWORD *)Pool + 32) = -1;
        *((_DWORD *)Pool + 33) = -1;
        *((_BYTE *)Pool + 64) = 1;
        *((_DWORD *)Pool + 17) = 0;
        if ( (a2[3] & 2) != 0 )
        {
          LODWORD(v16) = v16 | 0x200;
          *((_DWORD *)Pool + 5) = v16;
        }
        StorPoFxComponent = RaidGetStorPoFxComponent(a2, 0, v16);
        v18 = StorPoFxComponent;
        if ( StorPoFxComponent && (unsigned __int8)RaidAdapterValidateStorPoFxComponent(StorPoFxComponent) )
        {
          if ( *(_DWORD *)(v18 + 8) == 1 )
            *((_DWORD *)Pool + 5) = v19 | 0x80;
          Pool[1] = Pool + 24;
          memmove(Pool + 24, a2, v11);
          *(_DWORD *)(*(_QWORD *)(a1 + 168) + 176LL) &= ~8u;
          if ( (*(_BYTE *)(*(_QWORD *)(a1 + 168) + 176LL) & 0x10) != 0 && (a2[3] & 4) != 0 )
          {
            LOBYTE(v20) = 1;
            if ( (int)RaidSetD3Cold(*(_QWORD *)(a1 + 8), v20) >= 0 )
            {
              *(_DWORD *)(*(_QWORD *)(a1 + 168) + 176LL) |= 8u;
              if ( a3 )
                *a3 = 1;
            }
          }
          if ( (a2[3] & 8) != 0 )
            *(_DWORD *)(*(_QWORD *)(a1 + 168) + 176LL) |= 0x40u;
          if ( (a2[3] & 0x200) != 0 )
            *(_DWORD *)(*(_QWORD *)(a1 + 168) + 176LL) |= 0x80u;
          v21 = *(_QWORD *)(a1 + 168);
          v22 = *(_DWORD *)(v21 + 176) | 0x20;
          if ( ((*((_BYTE *)a2 + 12) >> 6) & ((*(_DWORD *)(v21 + 176) & 9) == 9)) == 0 )
            v22 = *(_DWORD *)(v21 + 176) & 0xFFFFFFDF;
          *(_DWORD *)(v21 + 176) = v22;
          if ( (a2[3] & 0x40) != 0 )
            *(_DWORD *)(*(_QWORD *)(a1 + 168) + 176LL) |= 0x100u;
          v23 = *(_QWORD *)(a1 + 168);
          if ( (*(_DWORD *)(v23 + 176) & 0x120) == 0x120 )
          {
            *(_DWORD *)(v23 + 176) &= ~0x100u;
            v23 = *(_QWORD *)(a1 + 168);
          }
          if ( _bittest(a2 + 3, 0xAu) )
            *(_DWORD *)(v23 + 176) |= 0x200u;
          PoFxSetComponentLatency(*Pool, 0, -1);
          PoFxSetComponentResidency(*Pool, 0, -1);
          if ( !_bittest((const signed __int32 *)(*(_QWORD *)(a1 + 168) + 176LL), 0xAu)
            && *a2 >= 2u
            && (a2[3] & 0x10) != 0 )
          {
            *((_DWORD *)Pool + 32) = a2[4];
          }
          *(_QWORD *)(*(_QWORD *)(a1 + 168) + 8LL) = Pool;
          ExReInitializeRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(a1 + 168) + 80LL));
          **(_BYTE **)(a1 + 168) = 1;
          NvmeAdapterPoFxSetDeviceIdleTimeout(
            a1,
            *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a1 + 168) + 8LL) + 128LL),
            v24,
            0);
          if ( StorEtwLoggingEnabled )
          {
            v26 = *(_DWORD *)(a1 + 56);
            if ( v26 != -1 && (byte_140177432 & 0x10) != 0 )
            {
              v27 = *(_QWORD *)(a1 + 168);
              McTemplateK0pqtqqt_EtwWriteTransfer(
                (*(_DWORD *)(v27 + 176) >> 3) & 1,
                v26,
                v25,
                **(_QWORD **)(v27 + 8),
                v26,
                (*(_DWORD *)(v27 + 176) & 8) != 0,
                *(_DWORD *)(*(_QWORD *)(v27 + 8) + 128LL),
                *(_DWORD *)(v18 + 8),
                (*(_DWORD *)(v27 + 176) & 0x20) != 0);
            }
          }
          PoFxStartDevicePowerManagement(**(_QWORD **)(*(_QWORD *)(a1 + 168) + 8LL));
          return 0;
        }
        v9 = -1073741811;
      }
      else
      {
        v9 = -1073741670;
      }
    }
    else
    {
      v9 = -1056964605;
    }
  }
  if ( v28 )
    PoFxUnregisterDevice();
  v12 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(*(_QWORD *)(a1 + 168) + 80LL);
  if ( v12 )
  {
    ExFreeCacheAwareRundownProtection(v12);
    *(_QWORD *)(*(_QWORD *)(a1 + 168) + 80LL) = 0;
  }
  if ( Pool )
    ExFreePoolWithTag(Pool, 0x4F506152u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1401397b4  mov     rax, rsp
0x1401397b7  push    rbx
0x1401397b8  push    rbp
0x1401397b9  push    rsi
0x1401397ba  push    rdi
0x1401397bb  push    r14
0x1401397bd  push    r15
0x1401397bf  sub     rsp, 58h
0x1401397c3  cmp     cs:RuntimePowerDisabled, 0
0x1401397ca  mov     r14, r8
0x1401397cd  mov     rbp, rdx
0x1401397d0  mov     qword ptr [rax+20h], 0
0x1401397d8  mov     rdi, rcx
0x1401397db  jnz     short loc_1401397FC
0x1401397dd  mov     rax, [rcx+0A8h]
0x1401397e4  cmp     byte ptr [rax], 1
0x1401397e7  jnz     short loc_14013980C
0x1401397e9  test    r8, r8
0x1401397ec  jz      short loc_1401397FC
0x1401397ee  mov     eax, [rax+0B0h]
0x1401397f4  shr     eax, 3
0x1401397f7  and     al, 1
0x1401397f9  mov     [r8], al
0x1401397fc  xor     eax, eax
0x1401397fe  add     rsp, 58h
0x140139802  pop     r15
0x140139804  pop     r14
0x140139806  pop     rdi
0x140139807  pop     rsi
0x140139808  pop     rbp
0x140139809  pop     rbx
0x14013980a  retn
0x14013980c  mov     rcx, [rcx+8]
0x140139810  lea     r9, [rsp+88h+arg_18]
0x140139818  mov     r8, rdi
0x14013981b  xor     esi, esi
0x14013981d  call    NvmeRegisterForRuntimePowerManagement
0x140139822  mov     ebx, eax
0x140139824  test    eax, eax
0x140139826  js      short loc_140139859
0x140139828  mov     rcx, rbp
0x14013982b  call    RaidGetTotalStorPoFxDeviceSize
0x140139830  mov     r9, [rdi+8]
0x140139834  lea     ecx, [rsi+48h]
0x140139837  mov     r15d, eax
0x14013983a  mov     r8d, 4F506152h
0x140139840  lea     edx, [r15+0C0h]
0x140139847  call    RaidAllocatePool
0x14013984c  mov     rsi, rax
0x14013984f  test    rax, rax
0x140139852  jnz     short loc_1401398BD
0x140139854  mov     ebx, 0C1000003h
0x140139859  mov     rcx, [rsp+88h+arg_18]
0x140139861  test    rcx, rcx
0x140139864  jz      short loc_140139872
0x140139866  call    cs:__imp_PoFxUnregisterDevice
0x14013986d  nop     dword ptr [rax+rax+00h]
0x140139872  mov     rax, [rdi+0A8h]
0x140139879  mov     rcx, [rax+50h]; RunRefCacheAware
0x14013987d  test    rcx, rcx
0x140139880  jz      short loc_14013989D
0x140139882  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140139889  nop     dword ptr [rax+rax+00h]
0x14013988e  mov     rax, [rdi+0A8h]
0x140139895  mov     qword ptr [rax+50h], 0
0x14013989d  test    rsi, rsi
0x1401398a0  jz      short loc_1401398B6
0x1401398a2  mov     edx, 4F506152h; Tag
0x1401398a7  mov     rcx, rsi; P
0x1401398aa  call    cs:__imp_ExFreePoolWithTag
0x1401398b1  nop     dword ptr [rax+rax+00h]
0x1401398b6  mov     eax, ebx
0x1401398b8  jmp     loc_1401397FE
0x1401398bd  mov     rbx, [rdi+0A8h]
0x1401398c4  mov     edx, 4F506152h; PoolTag
0x1401398c9  mov     ecx, 200h; PoolType
0x1401398ce  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1401398d5  nop     dword ptr [rax+rax+00h]
0x1401398da  mov     [rbx+50h], rax
0x1401398de  mov     rax, [rdi+0A8h]
0x1401398e5  mov     rcx, [rax+50h]; RunRef
0x1401398e9  test    rcx, rcx
0x1401398ec  jnz     short loc_1401398F8
0x1401398ee  mov     ebx, 0C000009Ah
0x1401398f3  jmp     loc_140139859
0x1401398f8  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1401398ff  nop     dword ptr [rax+rax+00h]
0x140139904  mov     rax, [rsp+88h+arg_18]
0x14013990c  or      dword ptr [rsi+14h], 1
0x140139910  mov     r8d, [rsi+14h]
0x140139914  mov     [rsi], rax
0x140139917  or      eax, 0FFFFFFFFh
0x14013991a  mov     [rsi+80h], eax
0x140139920  mov     [rsi+84h], eax
0x140139926  mov     byte ptr [rsi+40h], 1
0x14013992a  mov     dword ptr [rsi+44h], 0
0x140139931  mov     eax, [rbp+0Ch]
0x140139934  test    al, 2
0x140139936  jz      short loc_140139941
0x140139938  bts     r8d, 9
0x14013993d  mov     [rsi+14h], r8d
0x140139941  xor     edx, edx
0x140139943  mov     rcx, rbp
0x140139946  call    RaidGetStorPoFxComponent
0x14013994b  mov     rbx, rax
0x14013994e  test    rax, rax
0x140139951  jnz     short loc_14013995D
0x140139953  mov     ebx, 0C000000Dh
0x140139958  jmp     loc_140139859
0x14013995d  mov     rcx, rbx
0x140139960  call    RaidAdapterValidateStorPoFxComponent
0x140139965  test    al, al
0x140139967  jz      short loc_140139953
0x140139969  cmp     dword ptr [rbx+8], 1
0x14013996d  jnz     short loc_140139978
0x14013996f  bts     r8d, 7
0x140139974  mov     [rsi+14h], r8d
0x140139978  lea     rcx, [rsi+0C0h]; void *
0x14013997f  mov     r8, r15; Size
0x140139982  mov     rdx, rbp; Src
0x140139985  mov     [rsi+8], rcx
0x140139989  call    memmove
0x14013998e  mov     rax, [rdi+0A8h]
0x140139995  and     dword ptr [rax+0B0h], 0FFFFFFF7h
0x14013999c  mov     rax, [rdi+0A8h]
0x1401399a3  test    byte ptr [rax+0B0h], 10h
0x1401399aa  setnz   cl
0x1401399ad  test    byte ptr [rbp+0Ch], 4
0x1401399b1  setnz   al
0x1401399b4  test    al, cl
0x1401399b6  jz      short loc_1401399DE
0x1401399b8  mov     rcx, [rdi+8]
0x1401399bc  mov     dl, 1
0x1401399be  call    RaidSetD3Cold
0x1401399c3  test    eax, eax
0x1401399c5  js      short loc_1401399DE
0x1401399c7  mov     rax, [rdi+0A8h]
0x1401399ce  or      dword ptr [rax+0B0h], 8
0x1401399d5  test    r14, r14
0x1401399d8  jz      short loc_1401399DE
0x1401399da  mov     byte ptr [r14], 1
0x1401399de  mov     eax, [rbp+0Ch]
0x1401399e1  test    al, 8
0x1401399e3  jz      short loc_1401399F3
0x1401399e5  mov     rax, [rdi+0A8h]
0x1401399ec  or      dword ptr [rax+0B0h], 40h
0x1401399f3  mov     r9d, 200h
0x1401399f9  test    [rbp+0Ch], r9d
0x1401399fd  jz      short loc_140139A0E
0x1401399ff  mov     rax, [rdi+0A8h]
0x140139a06  bts     dword ptr [rax+0B0h], 7
0x140139a0e  mov     r8, [rdi+0A8h]
0x140139a15  mov     edx, [r8+0B0h]
0x140139a1c  mov     eax, edx
0x140139a1e  and     eax, 9
0x140139a21  cmp     al, 9
0x140139a23  mov     al, [rbp+0Ch]
0x140139a26  setz    cl
0x140139a29  shr     al, 6
0x140139a2c  and     cl, al
0x140139a2e  mov     eax, edx
0x140139a30  and     eax, 0FFFFFFDFh
0x140139a33  or      edx, 20h
0x140139a36  test    cl, 1
0x140139a39  cmovz   edx, eax
0x140139a3c  mov     [r8+0B0h], edx
0x140139a43  mov     eax, [rbp+0Ch]
0x140139a46  test    al, 40h
0x140139a48  jz      short loc_140139A59
0x140139a4a  mov     rax, [rdi+0A8h]
0x140139a51  bts     dword ptr [rax+0B0h], 8
0x140139a59  mov     rcx, [rdi+0A8h]
0x140139a60  mov     r8d, 120h
0x140139a66  mov     edx, [rcx+0B0h]
0x140139a6c  mov     eax, edx
0x140139a6e  and     eax, r8d
0x140139a71  cmp     eax, r8d
0x140139a74  jnz     short loc_140139A87
0x140139a76  btr     edx, 8
0x140139a7a  mov     [rcx+0B0h], edx
0x140139a80  mov     rcx, [rdi+0A8h]
0x140139a87  bt      dword ptr [rbp+0Ch], 0Ah
0x140139a8c  jnb     short loc_140139A95
0x140139a8e  or      [rcx+0B0h], r9d
0x140139a95  mov     rcx, [rsi]
0x140139a98  or      r14, 0FFFFFFFFFFFFFFFFh
0x140139a9c  mov     r8, r14
0x140139a9f  xor     edx, edx
0x140139aa1  call    cs:__imp_PoFxSetComponentLatency
0x140139aa8  nop     dword ptr [rax+rax+00h]
0x140139aad  mov     rcx, [rsi]
0x140139ab0  mov     r8, r14
0x140139ab3  xor     edx, edx
0x140139ab5  call    cs:__imp_PoFxSetComponentResidency
0x140139abc  nop     dword ptr [rax+rax+00h]
0x140139ac1  mov     rax, [rdi+0A8h]
0x140139ac8  bt      dword ptr [rax+0B0h], 0Ah
0x140139ad0  jb      short loc_140139AE8
0x140139ad2  cmp     dword ptr [rbp+0], 2
0x140139ad6  jb      short loc_140139AE8
0x140139ad8  mov     eax, [rbp+0Ch]
0x140139adb  test    al, 10h
0x140139add  jz      short loc_140139AE8
0x140139adf  mov     eax, [rbp+10h]
0x140139ae2  mov     [rsi+80h], eax
0x140139ae8  mov     rax, [rdi+0A8h]
0x140139aef  mov     [rax+8], rsi
0x140139af3  mov     rcx, [rdi+0A8h]
0x140139afa  mov     rcx, [rcx+50h]; RunRefCacheAware
0x140139afe  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140139b05  nop     dword ptr [rax+rax+00h]
0x140139b0a  mov     rax, [rdi+0A8h]
0x140139b11  xor     r9d, r9d
0x140139b14  mov     rcx, rdi
0x140139b17  mov     byte ptr [rax], 1
0x140139b1a  mov     rax, [rdi+0A8h]
0x140139b21  mov     rdx, [rax+8]
0x140139b25  mov     edx, [rdx+80h]
0x140139b2b  call    NvmeAdapterPoFxSetDeviceIdleTimeout
0x140139b30  cmp     cs:StorEtwLoggingEnabled, 0
0x140139b37  jz      short loc_140139B8F
0x140139b39  mov     edx, [rdi+38h]
0x140139b3c  cmp     edx, 0FFFFFFFFh
0x140139b3f  jz      short loc_140139B8F
0x140139b41  test    cs:byte_140177432, 10h
0x140139b48  jz      short loc_140139B8F
0x140139b4a  mov     rax, [rdi+0A8h]
0x140139b51  mov     ecx, [rax+0B0h]
0x140139b57  mov     r9, [rax+8]
0x140139b5b  mov     eax, ecx
0x140139b5d  shr     eax, 5
0x140139b60  and     eax, 1
0x140139b63  shr     ecx, 3
0x140139b66  mov     [rsp+88h+var_48], eax
0x140139b6a  and     ecx, 1
0x140139b6d  mov     eax, [rbx+8]
0x140139b70  mov     [rsp+88h+var_50], eax
0x140139b74  mov     eax, [r9+80h]
0x140139b7b  mov     r9, [r9]
0x140139b7e  mov     [rsp+88h+var_58], eax
0x140139b82  mov     [rsp+88h+var_60], ecx
0x140139b86  mov     [rsp+88h+var_68], edx
0x140139b8a  call    McTemplateK0pqtqqt_EtwWriteTransfer
0x140139b8f  mov     rax, [rdi+0A8h]
0x140139b96  mov     rcx, [rax+8]
0x140139b9a  mov     rcx, [rcx]
0x140139b9d  call    cs:__imp_PoFxStartDevicePowerManagement
0x140139ba4  nop     dword ptr [rax+rax+00h]
0x140139ba9  jmp     loc_1401397FC
```
