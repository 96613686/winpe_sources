# RaUnitScsiMiniportIoctl

- ea: `0x140004db0`
- end: `0x140005286`
- name: `RaUnitScsiMiniportIoctl`
- size: `1238`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140036290`

## callees

- `0x1400016cc`
- `0x140003df0`
- `0x140004db0`
- `0x140005c50`
- `0x140006f50`
- `0x140008058`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x140004f4f`
- `ntoskrnl!PoFxIdleComponent` at `0x140004f4f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140004f96`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140004f96`
- `ntoskrnl!IofCompleteRequest` at `0x140004fc7`
- `ntoskrnl!IofCompleteRequest` at `0x140004fc7`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004f00`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004f62`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004f00`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140004f62`
- `ntoskrnl!PoFxActivateComponent` at `0x140004eea`
- `ntoskrnl!PoFxActivateComponent` at `0x140004eea`

## pseudocode

```c
__int64 __fastcall RaUnitScsiMiniportIoctl(__int64 a1, __int64 a2)
{
  char v2; // r13
  char v5; // si
  int SrbIoctlFromIrp; // eax
  __int64 v7; // r15
  char v8; // bl
  unsigned int v9; // eax
  __int64 v10; // r9
  __int64 v11; // r14
  unsigned int v12; // r15d
  volatile signed __int32 *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rcx
  bool v17; // zf
  unsigned __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 *v20; // rdx
  int *v21; // rax
  int v22; // ecx
  char v23; // cl
  _BYTE *v24; // r9
  unsigned __int8 v25; // r10
  char v26; // r12
  char v27; // bl
  __int64 v28; // rdx
  char v29; // r11
  _BYTE *v30; // rax
  char v31; // r8
  char *v32; // r8
  unsigned int v33; // eax
  __int64 v34; // r8
  int v35; // ecx
  unsigned int v36; // edi
  char *v37; // r11
  unsigned int v38; // r15d
  unsigned __int64 v39; // rbx
  unsigned int v40; // [rsp+60h] [rbp-20h] BYREF
  int v41; // [rsp+64h] [rbp-1Ch] BYREF
  __int128 v42; // [rsp+68h] [rbp-18h] BYREF

  v2 = 0;
  *(_QWORD *)&v42 = 0;
  v40 = 0;
  v41 = 0;
  v5 = 1;
  SrbIoctlFromIrp = RaidGetSrbIoctlFromIrp(a2, (unsigned int)&v42, (unsigned int)&v40, (unsigned int)&v41, 1);
  v40 = SrbIoctlFromIrp;
  if ( SrbIoctlFromIrp >= 0 )
  {
    v7 = *(_QWORD *)(a1 + 24);
    if ( *(_QWORD *)(v7 + 5024) )
    {
      RaidAdapterPoFxActivateComponent(*(_QWORD *)(a1 + 24), 0, 1);
      v8 = 2;
    }
    else
    {
      v8 = 0;
    }
    if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(a1) )
    {
      if ( (*(_BYTE *)(v7 + 108) & 1) != 0 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(a1 + 2168), 1u);
        if ( (*(_BYTE *)(v7 + 108) & 2) != 0 )
          _InterlockedAdd64((volatile signed __int64 *)(a1 + 2176), 1u);
      }
      v14 = *(volatile signed __int32 **)(a1 + 1872);
      if ( (v14[37] & 1) != 0 )
      {
        _InterlockedAdd(v14 + 36, 1u);
        v14 = *(volatile signed __int32 **)(a1 + 1872);
      }
      v15 = 5;
      v16 = *(_QWORD *)v14;
      if ( !*(_DWORD *)(a1 + 1036) )
        v15 = 1;
      PoFxActivateComponent(v16, 0, v15);
      v8 |= 1u;
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
    }
    v9 = RaidAdapterScsiMiniportIoctlWithAddress(
           *(_QWORD *)(a1 + 24),
           a2,
           *(unsigned __int8 *)(a1 + 104),
           *(unsigned __int8 *)(a1 + 105),
           *(unsigned __int8 *)(a1 + 106),
           1);
    v11 = *(_QWORD *)(a1 + 24);
    v12 = v9;
    if ( (v8 & 1) != 0 && (unsigned __int8)RaidUnitCheckAndAcquirePoFx(a1) )
    {
      PoFxIdleComponent(**(_QWORD **)(a1 + 1872), 0, 0);
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
    }
    if ( (unsigned __int8)v8 >= 2u )
    {
      if ( *(_QWORD *)(v11 + 5024) )
        RaidAdapterPoFxIdleComponent(v11, 0, 0, v10);
    }
    return v12;
  }
  v17 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = SrbIoctlFromIrp;
  if ( v17 )
    goto LABEL_23;
  v42 = 0;
  IoGetActivityIdIrp(a2, &v42);
  v19 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v19 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_23;
    v20 = EventNonReadWriteRequestComplete;
    goto LABEL_33;
  }
  if ( *(_BYTE *)v19 != 15 )
  {
    if ( *(_BYTE *)v19 != 27 )
      goto LABEL_23;
    if ( *(_BYTE *)(v19 + 1) == 7 && !*(_DWORD *)(v19 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v21 = *(int **)(a2 + 56);
        if ( v21 )
          v22 = *v21;
        else
          v22 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v22, v19, (unsigned int)&v42, a2, v22, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_23;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_23;
    v20 = EventPnpRequestComplete;
LABEL_33:
    McTemplateK0pd_EtwWriteTransfer(v18, v20, &v42, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_23;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_23;
  v28 = *(_QWORD *)(v19 + 8);
  if ( *(_BYTE *)(v28 + 2) != 40 )
  {
    v23 = *(_BYTE *)(v28 + 72);
    v24 = *(_BYTE **)(v28 + 32);
    v25 = *(_BYTE *)(v28 + 11);
    v26 = *(_BYTE *)(v28 + 4);
    if ( !*(_BYTE *)(v28 + 2) )
      goto LABEL_38;
    goto LABEL_23;
  }
  if ( *(_DWORD *)(v28 + 20) )
    goto LABEL_23;
  v38 = *(_DWORD *)(v28 + 56);
  if ( !v38 )
    goto LABEL_23;
  v25 = 0;
  v37 = 0;
  v26 = 0;
  v24 = 0;
  v36 = 0;
  while ( 1 )
  {
    v18 = *(unsigned int *)(v28 + 4LL * v36 + 120);
    if ( (unsigned int)v18 >= 0x80 )
    {
      v39 = *(unsigned int *)(v28 + 16);
      if ( (unsigned int)v18 < (unsigned int)v39 )
        break;
    }
LABEL_55:
    if ( ++v36 >= v38 )
      goto LABEL_56;
  }
  v34 = *(unsigned int *)(v28 + 4LL * v36 + 120);
  v35 = *(_DWORD *)(v18 + v28) - 64;
  if ( v35 )
  {
    LODWORD(v18) = v35 - 1;
    if ( (_DWORD)v18 )
    {
      if ( (_DWORD)v18 == 1 )
      {
        LODWORD(v18) = v34 + 40;
        if ( v34 + 40 <= v39 )
        {
          if ( *(_DWORD *)(v34 + v28 + 12) )
            v37 = (char *)(v34 + v28 + 32);
          v24 = *(_BYTE **)(v34 + v28 + 24);
          goto LABEL_66;
        }
      }
    }
    else
    {
      LODWORD(v18) = v34 + 56;
      if ( v34 + 56 <= v39 )
      {
        v2 = 1;
        if ( *(_BYTE *)(v34 + v28 + 10) )
          v37 = (char *)(v34 + v28 + 24);
        v26 = *(_BYTE *)(v34 + v28 + 8);
        v24 = *(_BYTE **)(v34 + v28 + 16);
        v25 = *(_BYTE *)(v34 + v28 + 9);
      }
    }
    goto LABEL_54;
  }
  LODWORD(v18) = v34 + 40;
  if ( v34 + 40 > v39 )
  {
LABEL_54:
    if ( v2 )
      goto LABEL_56;
    goto LABEL_55;
  }
  if ( *(_BYTE *)(v34 + v28 + 10) )
    v37 = (char *)(v34 + v28 + 24);
  v24 = *(_BYTE **)(v34 + v28 + 16);
LABEL_66:
  v26 = *(_BYTE *)(v34 + v28 + 8);
  v25 = *(_BYTE *)(v34 + v28 + 9);
LABEL_56:
  if ( !v37 )
    goto LABEL_23;
  v23 = *v37;
LABEL_38:
  LOBYTE(v18) = v23 - 8;
  if ( (v18 & 0x5D) != 0 )
    goto LABEL_23;
  v27 = *(_BYTE *)(v28 + 3);
  if ( v27 == 1 || !v24 || !v25 )
    goto LABEL_76;
  LOBYTE(v28) = 0;
  v18 = (unsigned __int64)&v24[v25];
  v29 = 0;
  v30 = v24 + 8;
  v31 = 0;
  if ( (unsigned __int8)((*v24 & 0x7F) - 114) <= 1u )
  {
    if ( (unsigned __int64)v30 <= v18 )
    {
      v29 = v24[2];
      LOBYTE(v28) = v24[1] & 0xF;
      v31 = v24[3];
      goto LABEL_84;
    }
    goto LABEL_83;
  }
  if ( (unsigned __int64)v30 > v18 )
  {
LABEL_83:
    v5 = 0;
    goto LABEL_84;
  }
  v32 = v24 + 13;
  LOBYTE(v28) = v24[2] & 0xF;
  v33 = v25;
  if ( (unsigned int)(unsigned __int8)v24[7] + 8 <= v25 )
    v33 = (unsigned __int8)v24[7] + 8;
  v18 = (unsigned __int64)&v24[v33];
  if ( (unsigned __int64)v32 <= v18 )
    v29 = v24[12];
  if ( (unsigned __int64)(v24 + 14) > v18 )
    v31 = 0;
  else
    v31 = *v32;
LABEL_84:
  if ( !v5 )
  {
LABEL_76:
    LOBYTE(v28) = 0;
    v29 = 0;
    v31 = 0;
  }
  McTemplateK0pduuuuup_EtwWriteTransfer(
    v18,
    v28,
    (unsigned int)&v42,
    a2,
    *(_DWORD *)(a2 + 48),
    v27,
    v26,
    v28,
    v29,
    v31,
    a2);
LABEL_23:
  IofCompleteRequest((PIRP)a2, 0);
  return v40;
}

```

## disassembly

```asm
0x140004db0  mov     [rsp-38h+arg_10], rbx
0x140004db5  push    rbp
0x140004db6  push    rsi
0x140004db7  push    rdi
0x140004db8  push    r12
0x140004dba  push    r13
0x140004dbc  push    r14
0x140004dbe  push    r15
0x140004dc0  mov     rbp, rsp
0x140004dc3  sub     rsp, 80h
0x140004dca  mov     rax, cs:__security_cookie
0x140004dd1  xor     rax, rsp
0x140004dd4  mov     [rbp+var_8], rax
0x140004dd8  xor     r13d, r13d
0x140004ddb  lea     r9, [rbp+var_1C]
0x140004ddf  mov     r14, rdx
0x140004de2  mov     qword ptr [rbp+var_18], r13
0x140004de6  mov     rdi, rcx
0x140004de9  mov     [rbp+var_20], r13d
0x140004ded  lea     r8, [rbp+var_20]
0x140004df1  mov     [rbp+var_1C], r13d
0x140004df5  lea     esi, [r13+1]
0x140004df9  mov     rcx, r14
0x140004dfc  lea     rdx, [rbp+var_18]
0x140004e00  mov     [rsp+80h+var_60], esi
0x140004e04  call    RaidGetSrbIoctlFromIrp
0x140004e09  mov     [rbp+var_20], eax
0x140004e0c  test    eax, eax
0x140004e0e  js      loc_140004F73
0x140004e14  mov     r15, [rdi+18h]
0x140004e18  cmp     [r15+13A0h], r13
0x140004e1f  jnz     short loc_140004E96
0x140004e21  mov     bl, r13b
0x140004e24  mov     rcx, rdi
0x140004e27  call    RaidUnitCheckAndAcquirePoFx
0x140004e2c  test    al, al
0x140004e2e  jnz     short loc_140004EAA
0x140004e30  movzx   eax, byte ptr [rdi+6Ah]
0x140004e34  mov     rdx, r14
0x140004e37  movzx   r9d, byte ptr [rdi+69h]
0x140004e3c  movzx   r8d, byte ptr [rdi+68h]
0x140004e41  mov     rcx, [rdi+18h]
0x140004e45  mov     [rsp+80h+var_58], esi
0x140004e49  mov     [rsp+80h+var_60], eax
0x140004e4d  call    RaidAdapterScsiMiniportIoctlWithAddress
0x140004e52  mov     r14, [rdi+18h]
0x140004e56  mov     r15d, eax
0x140004e59  test    sil, bl
0x140004e5c  jnz     loc_140004F30
0x140004e62  cmp     bl, 2
0x140004e65  jnb     loc_140004F11
0x140004e6b  mov     eax, r15d
0x140004e6e  mov     rcx, [rbp+var_8]
0x140004e72  xor     rcx, rsp; StackCookie
0x140004e75  call    __security_check_cookie
0x140004e7a  mov     rbx, [rsp+80h+arg_10]
0x140004e82  add     rsp, 80h
0x140004e89  pop     r15
0x140004e8b  pop     r14
0x140004e8d  pop     r13
0x140004e8f  pop     r12
0x140004e91  pop     rdi
0x140004e92  pop     rsi
0x140004e93  pop     rbp
0x140004e94  retn
0x140004e96  mov     r8d, esi
0x140004e99  xor     edx, edx
0x140004e9b  mov     rcx, r15
0x140004e9e  call    RaidAdapterPoFxActivateComponent
0x140004ea3  mov     bl, 2
0x140004ea5  jmp     loc_140004E24
0x140004eaa  test    [r15+6Ch], sil
0x140004eae  jnz     loc_140004FDB
0x140004eb4  mov     rcx, [rdi+750h]
0x140004ebb  mov     eax, [rcx+94h]
0x140004ec1  test    sil, al
0x140004ec4  jz      short loc_140004ED4
0x140004ec6  lock add [rcx+90h], esi
0x140004ecd  mov     rcx, [rdi+750h]
0x140004ed4  cmp     [rdi+40Ch], r13d
0x140004edb  mov     r8d, 5
0x140004ee1  mov     rcx, [rcx]
0x140004ee4  cmovbe  r8d, esi
0x140004ee8  xor     edx, edx
0x140004eea  call    cs:__imp_PoFxActivateComponent
0x140004ef1  nop     dword ptr [rax+rax+00h]
0x140004ef6  mov     rcx, [rdi+748h]; RunRefCacheAware
0x140004efd  or      bl, sil
0x140004f00  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140004f07  nop     dword ptr [rax+rax+00h]
0x140004f0c  jmp     loc_140004E30
0x140004f11  cmp     [r14+13A0h], r13
0x140004f18  jz      loc_140004E6B
0x140004f1e  xor     r8d, r8d
0x140004f21  xor     edx, edx
0x140004f23  mov     rcx, r14
0x140004f26  call    RaidAdapterPoFxIdleComponent
0x140004f2b  jmp     loc_140004E6B
0x140004f30  mov     rcx, rdi
0x140004f33  call    RaidUnitCheckAndAcquirePoFx
0x140004f38  test    al, al
0x140004f3a  jz      loc_140004E62
0x140004f40  mov     rcx, [rdi+750h]
0x140004f47  xor     r8d, r8d
0x140004f4a  xor     edx, edx
0x140004f4c  mov     rcx, [rcx]
0x140004f4f  call    cs:__imp_PoFxIdleComponent
0x140004f56  nop     dword ptr [rax+rax+00h]
0x140004f5b  mov     rcx, [rdi+748h]; RunRefCacheAware
0x140004f62  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140004f69  nop     dword ptr [rax+rax+00h]
0x140004f6e  jmp     loc_140004E62
0x140004f73  cmp     cs:StorEtwLoggingEnabled, r13b
0x140004f7a  mov     byte ptr [r14+8Dh], 0ACh
0x140004f82  mov     [r14+30h], eax
0x140004f86  jz      short loc_140004FC2
0x140004f88  xorps   xmm0, xmm0
0x140004f8b  lea     rdx, [rbp+var_18]
0x140004f8f  mov     rcx, r14
0x140004f92  movups  [rbp+var_18], xmm0
0x140004f96  call    cs:__imp_IoGetActivityIdIrp
0x140004f9d  nop     dword ptr [rax+rax+00h]
0x140004fa2  mov     rdx, [r14+0B8h]
0x140004fa9  movzx   eax, byte ptr [rdx]
0x140004fac  sub     eax, 0Eh
0x140004faf  jz      short loc_14000501E
0x140004fb1  sub     eax, esi
0x140004fb3  jnz     short loc_140004FFB
0x140004fb5  cmp     cs:byte_140177431, r13b
0x140004fbc  jl      loc_14000524C
0x140004fc2  xor     edx, edx; PriorityBoost
0x140004fc4  mov     rcx, r14; Irp
0x140004fc7  call    cs:__imp_IofCompleteRequest
0x140004fce  nop     dword ptr [rax+rax+00h]
0x140004fd3  mov     eax, [rbp+var_20]
0x140004fd6  jmp     loc_140004E6E
0x140004fdb  lock add [rdi+878h], rsi
0x140004fe3  test    byte ptr [r15+6Ch], 2
0x140004fe8  jz      loc_140004EB4
0x140004fee  lock add [rdi+880h], rsi
0x140004ff6  jmp     loc_140004EB4
0x140004ffb  cmp     eax, 0Ch
0x140004ffe  jnz     short loc_140004FC2
0x140005000  cmp     byte ptr [rdx+1], 7
0x140005004  jnz     short loc_14000500C
0x140005006  cmp     [rdx+8], r13d
0x14000500a  jz      short loc_140005047
0x14000500c  test    cs:byte_140177432, 20h
0x140005013  jz      short loc_140004FC2
0x140005015  lea     rdx, EventPnpRequestComplete
0x14000501c  jmp     short loc_14000502E
0x14000501e  test    cs:byte_140177432, 8
0x140005025  jz      short loc_140004FC2
0x140005027  lea     rdx, EventNonReadWriteRequestComplete
0x14000502e  mov     eax, [r14+30h]
0x140005032  lea     r8, [rbp+var_18]
0x140005036  mov     r9, r14
0x140005039  mov     [rsp+80h+var_60], eax
0x14000503d  call    McTemplateK0pd_EtwWriteTransfer
0x140005042  jmp     loc_140004FC2
0x140005047  test    cs:byte_140177432, 40h
0x14000504e  jz      loc_140004FC2
0x140005054  mov     rax, [r14+38h]
0x140005058  test    rax, rax
0x14000505b  jz      loc_14014C19E
0x140005061  mov     ecx, [rax]
0x140005063  jmp     loc_14014C1A1
0x140005068  mov     cl, [rdx+48h]
0x14000506b  mov     r9, [rdx+20h]
0x14000506f  mov     r10b, [rdx+0Bh]
0x140005073  mov     r12b, [rdx+4]
0x140005077  test    eax, eax
0x140005079  jnz     loc_140004FC2
0x14000507f  sub     cl, 8
0x140005082  test    cl, 5Dh
0x140005085  jnz     loc_140004FC2
0x14000508b  mov     bl, [rdx+3]
0x14000508e  cmp     bl, sil
0x140005091  jz      loc_14000520E
0x140005097  test    r9, r9
0x14000509a  jz      loc_14000520E
0x1400050a0  test    r10b, r10b
0x1400050a3  jz      loc_14000520E
0x1400050a9  mov     al, [r9]
0x1400050ac  mov     dl, r13b
0x1400050af  and     al, 7Fh
0x1400050b1  movzx   ecx, r10b
0x1400050b5  sub     al, 72h ; 'r'
0x1400050b7  add     rcx, r9
0x1400050ba  cmp     al, sil
0x1400050bd  mov     r11b, r13b
0x1400050c0  lea     rax, [r9+8]
0x1400050c4  mov     r8b, r13b
0x1400050c7  jbe     loc_140005266
0x1400050cd  cmp     rax, rcx
0x1400050d0  ja      loc_14000527C
0x1400050d6  movzx   ecx, byte ptr [r9+7]
0x1400050db  lea     r8, [r9+0Dh]
0x1400050df  mov     dl, [r9+2]
0x1400050e3  add     ecx, 8
0x1400050e6  and     dl, 0Fh
0x1400050e9  movzx   eax, r10b
0x1400050ed  cmp     ecx, eax
0x1400050ef  cmovbe  eax, ecx
0x1400050f2  mov     ecx, eax
0x1400050f4  add     rcx, r9
0x1400050f7  cmp     r8, rcx
0x1400050fa  ja      short loc_140005100
0x1400050fc  mov     r11b, [r9+0Ch]
0x140005100  lea     rax, [r9+0Eh]
0x140005104  cmp     rax, rcx
0x140005107  ja      loc_140005261
0x14000510d  mov     r8b, [r8]
0x140005110  jmp     loc_14000527F
0x140005115  mov     r8, rcx
0x140005118  mov     ecx, [rcx+rdx]
0x14000511b  sub     ecx, 40h ; '@'
0x14000511e  jz      short loc_140005181
0x140005120  sub     ecx, esi
0x140005122  jz      short loc_140005155
0x140005124  cmp     ecx, esi
0x140005126  jnz     short loc_140005131
0x140005128  lea     rcx, [r8+28h]
0x14000512c  cmp     rcx, rbx
0x14000512f  jbe     short loc_1400051A5
0x140005131  test    r13b, r13b
0x140005134  jnz     short loc_140005141
0x140005136  add     edi, esi
0x140005138  cmp     edi, r15d
0x14000513b  jb      loc_1400051EC
0x140005141  xor     r13d, r13d
0x140005144  test    r11, r11
0x140005147  jz      loc_140004FC2
0x14000514d  mov     cl, [r11]
0x140005150  jmp     loc_14000507F
0x140005155  lea     rcx, [r8+38h]
0x140005159  cmp     rcx, rbx
0x14000515c  ja      short loc_140005131
0x14000515e  cmp     byte ptr [r8+rdx+0Ah], 0
0x140005164  mov     r13b, sil
0x140005167  jbe     short loc_140005170
0x140005169  lea     r11, [rdx+18h]
0x14000516d  add     r11, r8
0x140005170  mov     r12b, [r8+rdx+8]
0x140005175  mov     r9, [r8+rdx+10h]
0x14000517a  mov     r10b, [r8+rdx+9]
0x14000517f  jmp     short loc_140005131
0x140005181  lea     rcx, [r8+28h]
0x140005185  cmp     rcx, rbx
0x140005188  ja      short loc_140005131
0x14000518a  xor     r13d, r13d
0x14000518d  cmp     [r8+rdx+0Ah], r13b
0x140005192  ja      short loc_1400051BD
0x140005194  mov     r9, [r8+rdx+10h]
0x140005199  mov     r12b, [r8+rdx+8]
0x14000519e  mov     r10b, [r8+rdx+9]
0x1400051a3  jmp     short loc_140005144
0x1400051a5  xor     r13d, r13d
0x1400051a8  cmp     [r8+rdx+0Ch], r13d
0x1400051ad  jbe     short loc_1400051B6
0x1400051af  lea     r11, [rdx+20h]
0x1400051b3  add     r11, r8
0x1400051b6  mov     r9, [r8+rdx+18h]
0x1400051bb  jmp     short loc_140005199
0x1400051bd  lea     r11, [rdx+18h]
0x1400051c1  add     r11, r8
0x1400051c4  jmp     short loc_140005194
0x1400051c6  cmp     [rdx+14h], r13d
0x1400051ca  jnz     loc_140004FC2
0x1400051d0  mov     r15d, [rdx+38h]
0x1400051d4  test    r15d, r15d
0x1400051d7  jz      loc_140004FC2
0x1400051dd  mov     r10b, r13b
0x1400051e0  mov     r11, r13
0x1400051e3  mov     r12b, r13b
0x1400051e6  mov     r9, r13
0x1400051e9  mov     edi, r13d
0x1400051ec  mov     eax, edi
0x1400051ee  mov     ecx, [rdx+rax*4+78h]
0x1400051f2  cmp     ecx, 80h
0x1400051f8  jb      loc_140005136
0x1400051fe  mov     ebx, [rdx+10h]
0x140005201  cmp     ecx, ebx
0x140005203  jnb     loc_140005136
0x140005209  jmp     loc_140005115
0x14000520e  mov     dl, r13b
0x140005211  mov     r11b, r13b
0x140005214  mov     r8b, r13b
0x140005217  mov     eax, [r14+30h]
0x14000521b  mov     r9, r14
0x14000521e  mov     [rsp+80h+var_30], r14
0x140005223  mov     [rsp+80h+var_38], r8b
0x140005228  lea     r8, [rbp+var_18]
0x14000522c  mov     [rsp+80h+var_40], r11b
0x140005231  mov     [rsp+80h+var_48], dl
0x140005235  mov     [rsp+80h+var_50], r12b
0x14000523a  mov     byte ptr [rsp+80h+var_58], bl
0x14000523e  mov     [rsp+80h+var_60], eax
0x140005242  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x140005247  jmp     loc_140004FC2
  ... truncated ...
```
