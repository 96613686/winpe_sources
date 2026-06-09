# NvmeAdapterFabricsGetControllersIoctl

- ea: `0x1401a3fc8`
- end: `0x1401a4585`
- name: `NvmeAdapterFabricsGetControllersIoctl`
- size: `1469`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400e7d6c`
- `0x1400f8d6c`
- `0x14014b400`
- `0x14014b800`
- `0x1401a3fc8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a40b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a40b0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a429c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a429c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a423a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a423a`
- `ntoskrnl!IofCompleteRequest` at `0x1401a454e`
- `ntoskrnl!IofCompleteRequest` at `0x1401a454e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a41df`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a4256`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a41df`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a4256`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a4246`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a4246`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a40c6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a40c6`

## pseudocode

```c
__int64 __fastcall NvmeAdapterFabricsGetControllersIoctl(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  char v4; // di
  __int64 v5; // rax
  __int64 v6; // rsi
  unsigned int v7; // esi
  int v8; // ebp
  __int64 SubsystemPort; // r13
  _WORD *v10; // r14
  unsigned __int16 v11; // cx
  char v12; // bp
  __int64 *v13; // r12
  _WORD *v14; // rsi
  int *v15; // rax
  int v16; // ecx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  bool v20; // zf
  unsigned __int64 v21; // rcx
  __int64 v22; // rdx
  int *v23; // rax
  int v24; // ecx
  __int64 v25; // rdx
  unsigned int v26; // r12d
  unsigned __int8 v27; // r10
  char *v28; // r11
  char v29; // r14
  _BYTE *v30; // r9
  __int64 v31; // r15
  char v32; // r13
  unsigned __int64 v33; // rbp
  __int64 v34; // r8
  int v35; // ecx
  char v36; // cl
  char v37; // bp
  char v38; // r11
  char v39; // r8
  _BYTE *v40; // rax
  char *v41; // r8
  unsigned int v42; // eax
  __int128 v44; // [rsp+68h] [rbp-50h] BYREF

  a2[7] = 0;
  v2 = a2;
  *(_QWORD *)&v44 = a2;
  v4 = 1;
  if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && *(_QWORD *)(a1 + 616) )
  {
    v5 = a2[3];
    if ( v5 && (v6 = a2[23], *(_DWORD *)(v6 + 16) >= 0x10u) && *(_WORD *)v5 == 1 && *(_WORD *)(v5 + 2) >= 0x10u )
    {
      if ( *(_DWORD *)(v6 + 8) >= 8u )
      {
        v8 = *(_DWORD *)(v5 + 4);
        SubsystemPort = NvmeAdapterFindSubsystemPort(a1, *(_QWORD *)(v5 + 8) ^ a1, 0, 0);
        if ( SubsystemPort )
        {
          v10 = (_WORD *)v2[3];
          memset_0(v10, 0, *(unsigned int *)(v6 + 8));
          *v10 = 1;
          KeEnterCriticalRegion();
          ExAcquireResourceSharedLite((PERESOURCE)(SubsystemPort + 632), 1u);
          v11 = 32 * *(_WORD *)(SubsystemPort + 624) + 8;
          v10[1] = v11;
          if ( *(_DWORD *)(v6 + 8) < (unsigned int)v11 )
          {
            v19 = 8;
          }
          else
          {
            v12 = v8 & 1;
            v13 = *(__int64 **)(SubsystemPort + 608);
            v14 = v10 + 4;
            if ( v13 != (__int64 *)(SubsystemPort + 608) )
            {
              do
              {
                if ( (int)NvmeControllerAcquireRundown(v13 - 8) >= 0 )
                {
                  v15 = (int *)(v13 + 63);
                  if ( !v12 || *v15 == 2 )
                  {
                    *(_DWORD *)v14 = 2097153;
                    v16 = *v15;
                    if ( *v15 == 2 )
                    {
                      *((_DWORD *)v14 + 1) |= 1u;
                    }
                    else if ( v16 == 3 )
                    {
                      *((_DWORD *)v14 + 1) |= 2u;
                    }
                    else if ( v16 == 4 )
                    {
                      v17 = *((_DWORD *)v14 + 1);
                      if ( *(_DWORD *)v13[156] == 1 )
                        v18 = v17 | 0x10;
                      else
                        v18 = v17 | 4;
                      *((_DWORD *)v14 + 1) = v18;
                    }
                    if ( (v13[9] & 4) != 0 )
                      *((_DWORD *)v14 + 1) |= 8u;
                    *((_QWORD *)v14 + 1) = a1 ^ (unsigned __int64)(v13 - 8);
                    v14[8] = *((_WORD *)v13 - 30);
                    *((_DWORD *)v14 + 5) = *((_DWORD *)v13 + 127);
                    if ( *((_DWORD *)v13 + 127) == 1 )
                    {
                      v14[12] = *((_WORD *)v13 - 22);
                      v14[13] = *((_WORD *)v13 - 28);
                    }
                    ++*((_DWORD *)v10 + 1);
                    v14 += 16;
                  }
                  ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v13[61]);
                }
                v13 = (__int64 *)*v13;
              }
              while ( v13 != (__int64 *)(SubsystemPort + 608) );
              v11 = v10[1];
              v2 = (_QWORD *)v44;
            }
            if ( *((_DWORD *)v10 + 1) < *(_DWORD *)(SubsystemPort + 624) )
            {
              v11 = 32 * v10[2] + 8;
              v10[1] = v11;
            }
            v19 = v11;
          }
          v2[7] = v19;
          ExReleaseResourceLite((PERESOURCE)(SubsystemPort + 632));
          KeLeaveCriticalRegion();
          ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(SubsystemPort + 40));
          v7 = 0;
        }
        else
        {
          v7 = -1073741275;
        }
      }
      else
      {
        v7 = -1073741789;
      }
    }
    else
    {
      v7 = -1073741811;
    }
  }
  else
  {
    v7 = -1073741637;
  }
  v20 = StorEtwLoggingEnabled == 0;
  *((_BYTE *)v2 + 141) = -84;
  *((_DWORD *)v2 + 12) = v7;
  if ( v20 )
    goto LABEL_103;
  v44 = 0;
  IoGetActivityIdIrp(v2, &v44);
  v22 = v2[23];
  if ( *(_BYTE *)v22 == 14 )
  {
    if ( (byte_140177432 & 8) != 0 )
      McTemplateK0pd_EtwWriteTransfer(v21, EventNonReadWriteRequestComplete, &v44, v2, *((_DWORD *)v2 + 12));
    goto LABEL_103;
  }
  if ( *(_BYTE *)v22 != 15 )
  {
    if ( *(_BYTE *)v22 == 27 )
    {
      if ( *(_BYTE *)(v22 + 1) != 7 || *(_DWORD *)(v22 + 8) )
      {
        if ( (byte_140177432 & 0x20) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v21, EventPnpRequestComplete, &v44, v2, *((_DWORD *)v2 + 12));
      }
      else if ( (byte_140177432 & 0x40) != 0 )
      {
        v23 = (int *)v2[7];
        if ( v23 )
          v24 = *v23;
        else
          v24 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v24, v22, (unsigned int)&v44, (_DWORD)v2, v24, *((_DWORD *)v2 + 12));
      }
    }
    goto LABEL_103;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_103;
  v25 = *(_QWORD *)(v22 + 8);
  if ( *(_BYTE *)(v25 + 2) != 40 )
  {
    v36 = *(_BYTE *)(v25 + 72);
    v30 = *(_BYTE **)(v25 + 32);
    v27 = *(_BYTE *)(v25 + 11);
    v29 = *(_BYTE *)(v25 + 4);
    if ( *(_BYTE *)(v25 + 2) )
      goto LABEL_103;
LABEL_82:
    LOBYTE(v21) = v36 - 8;
    if ( (v21 & 0x5D) != 0 )
      goto LABEL_103;
    v37 = *(_BYTE *)(v25 + 3);
    if ( v37 == 1 || !v30 || !v27 )
      goto LABEL_99;
    LOBYTE(v25) = 0;
    v38 = 0;
    v39 = 0;
    v21 = (unsigned __int64)&v30[v27];
    v40 = v30 + 8;
    if ( (unsigned __int8)((*v30 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v40 <= v21 )
      {
        v38 = v30[2];
        LOBYTE(v25) = v30[1] & 0xF;
        v39 = v30[3];
        goto LABEL_98;
      }
    }
    else if ( (unsigned __int64)v40 <= v21 )
    {
      v41 = v30 + 13;
      LOBYTE(v25) = v30[2] & 0xF;
      v42 = v27;
      if ( (unsigned int)(unsigned __int8)v30[7] + 8 <= v27 )
        v42 = (unsigned __int8)v30[7] + 8;
      v21 = (unsigned __int64)&v30[v42];
      if ( (unsigned __int64)v41 <= v21 )
        v38 = v30[12];
      if ( (unsigned __int64)(v30 + 14) > v21 )
        v39 = 0;
      else
        v39 = *v41;
LABEL_98:
      if ( v4 )
      {
LABEL_100:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v21,
          v25,
          (unsigned int)&v44,
          (_DWORD)v2,
          *((_DWORD *)v2 + 12),
          v37,
          v29,
          v25,
          v38,
          v39,
          (char)v2);
        goto LABEL_103;
      }
LABEL_99:
      LOBYTE(v25) = 0;
      v38 = 0;
      v39 = 0;
      goto LABEL_100;
    }
    v4 = 0;
    goto LABEL_98;
  }
  if ( *(_DWORD *)(v25 + 20) )
    goto LABEL_103;
  v26 = *(_DWORD *)(v25 + 56);
  if ( !v26 )
    goto LABEL_103;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  while ( 1 )
  {
    v21 = *(unsigned int *)(v25 + 4 * v31 + 120);
    if ( (unsigned int)v21 >= 0x80 )
    {
      v33 = *(unsigned int *)(v25 + 16);
      if ( (unsigned int)v21 < (unsigned int)v33 )
        break;
    }
LABEL_73:
    v31 = (unsigned int)(v31 + 1);
    if ( (unsigned int)v31 >= v26 )
      goto LABEL_79;
  }
  v34 = (unsigned int)v21;
  v35 = *(_DWORD *)(v21 + v25) - 64;
  if ( v35 )
  {
    LODWORD(v21) = v35 - 1;
    if ( (_DWORD)v21 )
    {
      if ( (_DWORD)v21 == 1 )
      {
        LODWORD(v21) = v34 + 40;
        if ( v34 + 40 <= v33 )
        {
          if ( *(_DWORD *)(v34 + v25 + 12) )
            v28 = (char *)(v34 + v25 + 32);
          v30 = *(_BYTE **)(v34 + v25 + 24);
          goto LABEL_78;
        }
      }
    }
    else
    {
      LODWORD(v21) = v34 + 56;
      if ( v34 + 56 <= v33 )
      {
        v32 = 1;
        if ( *(_BYTE *)(v34 + v25 + 10) )
          v28 = (char *)(v34 + v25 + 24);
        v29 = *(_BYTE *)(v34 + v25 + 8);
        v30 = *(_BYTE **)(v34 + v25 + 16);
        v27 = *(_BYTE *)(v34 + v25 + 9);
      }
    }
    goto LABEL_72;
  }
  LODWORD(v21) = v34 + 40;
  if ( v34 + 40 > v33 )
  {
LABEL_72:
    if ( v32 )
      goto LABEL_79;
    goto LABEL_73;
  }
  if ( *(_BYTE *)(v34 + v25 + 10) )
    v28 = (char *)(v34 + v25 + 24);
  v30 = *(_BYTE **)(v34 + v25 + 16);
LABEL_78:
  v27 = *(_BYTE *)(v34 + v25 + 9);
  v29 = *(_BYTE *)(v34 + v25 + 8);
LABEL_79:
  if ( v28 )
  {
    v36 = *v28;
    goto LABEL_82;
  }
LABEL_103:
  IofCompleteRequest((PIRP)v2, 0);
  return v7;
}

```

## disassembly

```asm
0x1401a3fc8  mov     [rsp+arg_10], rbx
0x1401a3fcd  push    rbp
0x1401a3fce  push    rsi
0x1401a3fcf  push    rdi
0x1401a3fd0  push    r12
0x1401a3fd2  push    r13
0x1401a3fd4  push    r14
0x1401a3fd6  push    r15
0x1401a3fd8  sub     rsp, 80h
0x1401a3fdf  mov     rax, cs:__security_cookie
0x1401a3fe6  xor     rax, rsp
0x1401a3fe9  mov     [rsp+0B8h+var_40], rax
0x1401a3fee  mov     ebp, 20h ; ' '
0x1401a3ff3  mov     qword ptr [rdx+38h], 0
0x1401a3ffb  mov     rbx, rdx
0x1401a3ffe  mov     qword ptr [rsp+0B8h+var_50], rdx
0x1401a4003  mov     r15, rcx
0x1401a4006  lea     edi, [rbp-1Fh]
0x1401a4009  lea     r12d, [rbp-18h]
0x1401a400d  test    [rcx+98h], dil
0x1401a4014  jz      loc_1401A4270
0x1401a401a  cmp     qword ptr [rcx+268h], 0
0x1401a4022  jz      loc_1401A4270
0x1401a4028  mov     rax, [rdx+18h]
0x1401a402c  test    rax, rax
0x1401a402f  jz      loc_1401A4269
0x1401a4035  mov     rsi, [rdx+0B8h]
0x1401a403c  lea     ecx, [rbp-10h]
0x1401a403f  cmp     [rsi+10h], ecx
0x1401a4042  jb      loc_1401A4269
0x1401a4048  cmp     [rax], di
0x1401a404b  jnz     loc_1401A4269
0x1401a4051  cmp     [rax+2], cx
0x1401a4055  jb      loc_1401A4269
0x1401a405b  cmp     [rsi+8], r12d
0x1401a405f  jnb     short loc_1401A406B
0x1401a4061  mov     esi, 0C0000023h
0x1401a4066  jmp     loc_1401A4275
0x1401a406b  mov     ebp, [rax+4]
0x1401a406e  mov     rdx, r15
0x1401a4071  xor     rdx, [rax+8]
0x1401a4075  xor     r9d, r9d
0x1401a4078  xor     r8d, r8d
0x1401a407b  mov     rcx, r15
0x1401a407e  call    NvmeAdapterFindSubsystemPort
0x1401a4083  mov     r13, rax
0x1401a4086  test    rax, rax
0x1401a4089  jnz     short loc_1401A409A
0x1401a408b  mov     esi, 0C0000225h
0x1401a4090  mov     ebp, 20h ; ' '
0x1401a4095  jmp     loc_1401A4275
0x1401a409a  mov     r14, [rbx+18h]
0x1401a409e  xor     edx, edx; Val
0x1401a40a0  mov     r8d, [rsi+8]; Size
0x1401a40a4  mov     rcx, r14; void *
0x1401a40a7  call    memset_0
0x1401a40ac  mov     [r14], di
0x1401a40b0  call    cs:__imp_KeEnterCriticalRegion
0x1401a40b7  nop     dword ptr [rax+rax+00h]
0x1401a40bc  lea     rcx, [r13+278h]; Resource
0x1401a40c3  mov     dl, dil; Wait
0x1401a40c6  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a40cd  nop     dword ptr [rax+rax+00h]
0x1401a40d2  movzx   eax, word ptr [r13+270h]
0x1401a40da  shl     ax, 5
0x1401a40de  add     ax, r12w
0x1401a40e2  movzx   ecx, ax
0x1401a40e5  mov     [r14+2], cx
0x1401a40ea  cmp     [rsi+8], ecx
0x1401a40ed  jb      loc_1401A422C
0x1401a40f3  lea     rax, [r13+260h]
0x1401a40fa  and     bpl, dil
0x1401a40fd  mov     r12, [rax]
0x1401a4100  lea     rsi, [r14+8]
0x1401a4104  mov     [rsp+0B8h+var_58], ebp
0x1401a4108  cmp     r12, rax
0x1401a410b  jz      loc_1401A4202
0x1401a4111  lea     rbx, [r13+260h]
0x1401a4118  lea     rcx, [r12-40h]
0x1401a411d  call    NvmeControllerAcquireRundown
0x1401a4122  test    eax, eax
0x1401a4124  js      loc_1401A41EB
0x1401a412a  cmp     byte ptr [rsp+0B8h+var_58], 0
0x1401a412f  lea     rax, [r12+1F8h]
0x1401a4137  jz      short loc_1401A4142
0x1401a4139  cmp     dword ptr [rax], 2
0x1401a413c  jnz     loc_1401A41D7
0x1401a4142  mov     dword ptr [rsi], 200001h
0x1401a4148  mov     edx, 20h ; ' '
0x1401a414d  mov     ecx, [rax]
0x1401a414f  cmp     ecx, 2
0x1401a4152  jnz     short loc_1401A4159
0x1401a4154  or      [rsi+4], edi
0x1401a4157  jmp     short loc_1401A4185
0x1401a4159  cmp     ecx, 3
0x1401a415c  jnz     short loc_1401A4164
0x1401a415e  or      dword ptr [rsi+4], 2
0x1401a4162  jmp     short loc_1401A4185
0x1401a4164  cmp     ecx, 4
0x1401a4167  jnz     short loc_1401A4185
0x1401a4169  mov     rax, [r12+4E0h]
0x1401a4171  mov     ecx, [rax]
0x1401a4173  mov     eax, [rsi+4]
0x1401a4176  cmp     ecx, edi
0x1401a4178  jnz     short loc_1401A417F
0x1401a417a  or      eax, 10h
0x1401a417d  jmp     short loc_1401A4182
0x1401a417f  or      eax, 4
0x1401a4182  mov     [rsi+4], eax
0x1401a4185  test    byte ptr [r12+48h], 4
0x1401a418b  jz      short loc_1401A4191
0x1401a418d  or      dword ptr [rsi+4], 8
0x1401a4191  lea     rax, [r12-40h]
0x1401a4196  xor     rax, r15
0x1401a4199  mov     [rsi+8], rax
0x1401a419d  movzx   eax, word ptr [r12-3Ch]
0x1401a41a3  mov     [rsi+10h], ax
0x1401a41a7  mov     eax, [r12+1FCh]
0x1401a41af  mov     [rsi+14h], eax
0x1401a41b2  cmp     [r12+1FCh], edi
0x1401a41ba  jnz     short loc_1401A41D0
0x1401a41bc  movzx   eax, word ptr [r12-2Ch]
0x1401a41c2  mov     [rsi+18h], ax
0x1401a41c6  movzx   eax, word ptr [r12-38h]
0x1401a41cc  mov     [rsi+1Ah], ax
0x1401a41d0  add     [r14+4], edi
0x1401a41d4  add     rsi, rdx
0x1401a41d7  mov     rcx, [r12+1E8h]; RunRefCacheAware
0x1401a41df  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a41e6  nop     dword ptr [rax+rax+00h]
0x1401a41eb  mov     r12, [r12]
0x1401a41ef  cmp     r12, rbx
0x1401a41f2  jnz     loc_1401A4118
0x1401a41f8  movzx   ecx, word ptr [r14+2]
0x1401a41fd  mov     rbx, qword ptr [rsp+0B8h+var_50]
0x1401a4202  mov     eax, [r13+270h]
0x1401a4209  mov     r12d, 8
0x1401a420f  cmp     [r14+4], eax
0x1401a4213  jnb     short loc_1401A4227
0x1401a4215  movzx   ecx, word ptr [r14+4]
0x1401a421a  shl     cx, 5
0x1401a421e  add     cx, r12w
0x1401a4222  mov     [r14+2], cx
0x1401a4227  movzx   eax, cx
0x1401a422a  jmp     short loc_1401A422F
0x1401a422c  mov     rax, r12
0x1401a422f  lea     rcx, [r13+278h]; Resource
0x1401a4236  mov     [rbx+38h], rax
0x1401a423a  call    cs:__imp_ExReleaseResourceLite
0x1401a4241  nop     dword ptr [rax+rax+00h]
0x1401a4246  call    cs:__imp_KeLeaveCriticalRegion
0x1401a424d  nop     dword ptr [rax+rax+00h]
0x1401a4252  mov     rcx, [r13+28h]; RunRefCacheAware
0x1401a4256  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a425d  nop     dword ptr [rax+rax+00h]
0x1401a4262  xor     esi, esi
0x1401a4264  jmp     loc_1401A4090
0x1401a4269  mov     esi, 0C000000Dh
0x1401a426e  jmp     short loc_1401A4275
0x1401a4270  mov     esi, 0C00000BBh
0x1401a4275  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a427c  mov     byte ptr [rbx+8Dh], 0ACh
0x1401a4283  mov     [rbx+30h], esi
0x1401a4286  jz      loc_1401A4549
0x1401a428c  xorps   xmm0, xmm0
0x1401a428f  lea     rdx, [rsp+0B8h+var_50]
0x1401a4294  mov     rcx, rbx
0x1401a4297  movups  [rsp+0B8h+var_50], xmm0
0x1401a429c  call    cs:__imp_IoGetActivityIdIrp
0x1401a42a3  nop     dword ptr [rax+rax+00h]
0x1401a42a8  mov     rdx, [rbx+0B8h]
0x1401a42af  movzx   eax, byte ptr [rdx]
0x1401a42b2  sub     eax, 0Eh
0x1401a42b5  jz      loc_1401A4525
0x1401a42bb  sub     eax, edi
0x1401a42bd  jz      short loc_1401A432D
0x1401a42bf  cmp     eax, 0Ch
0x1401a42c2  jnz     loc_1401A4549
0x1401a42c8  cmp     byte ptr [rdx+1], 7
0x1401a42cc  jnz     short loc_1401A430D
0x1401a42ce  cmp     dword ptr [rdx+8], 0
0x1401a42d2  jnz     short loc_1401A430D
0x1401a42d4  test    cs:byte_140177432, 40h
0x1401a42db  jz      loc_1401A4549
0x1401a42e1  mov     rax, [rbx+38h]
0x1401a42e5  test    rax, rax
0x1401a42e8  jz      short loc_1401A42EE
0x1401a42ea  mov     ecx, [rax]
0x1401a42ec  jmp     short loc_1401A42F0
0x1401a42ee  xor     ecx, ecx
0x1401a42f0  mov     eax, [rbx+30h]
0x1401a42f3  lea     r8, [rsp+0B8h+var_50]
0x1401a42f8  mov     [rsp+0B8h+var_90], eax
0x1401a42fc  mov     r9, rbx
0x1401a42ff  mov     [rsp+0B8h+var_98], ecx
0x1401a4303  call    McTemplateK0pqd_EtwWriteTransfer
0x1401a4308  jmp     loc_1401A4549
0x1401a430d  test    cs:byte_140177432, bpl
0x1401a4314  jz      loc_1401A4549
0x1401a431a  mov     eax, [rbx+30h]
0x1401a431d  lea     rdx, EventPnpRequestComplete
0x1401a4324  mov     [rsp+0B8h+var_98], eax
0x1401a4328  jmp     loc_1401A453C
0x1401a432d  cmp     cs:byte_140177431, 0
0x1401a4334  jge     loc_1401A4549
0x1401a433a  mov     rdx, [rdx+8]
0x1401a433e  movzx   eax, byte ptr [rdx+2]
0x1401a4342  cmp     al, 28h ; '('
0x1401a4344  jnz     loc_1401A442D
0x1401a434a  cmp     dword ptr [rdx+14h], 0
0x1401a434e  jnz     loc_1401A4549
0x1401a4354  mov     r12d, [rdx+38h]
0x1401a4358  test    r12d, r12d
0x1401a435b  jz      loc_1401A4549
0x1401a4361  xor     r10b, r10b
0x1401a4364  xor     r11d, r11d
0x1401a4367  xor     r14b, r14b
0x1401a436a  xor     r9d, r9d
0x1401a436d  xor     r15d, r15d
0x1401a4370  xor     r13b, r13b
0x1401a4373  mov     ecx, [rdx+r15*4+78h]
0x1401a4378  cmp     ecx, 80h
0x1401a437e  jb      short loc_1401A43F3
0x1401a4380  mov     ebp, [rdx+10h]
0x1401a4383  cmp     ecx, ebp
0x1401a4385  jnb     short loc_1401A43F3
0x1401a4387  mov     r8d, ecx
0x1401a438a  mov     ecx, [rcx+rdx]
0x1401a438d  sub     ecx, 40h ; '@'
0x1401a4390  jz      short loc_1401A43E5
0x1401a4392  sub     ecx, edi
0x1401a4394  jz      short loc_1401A43B9
0x1401a4396  cmp     ecx, edi
0x1401a4398  jnz     short loc_1401A43EE
0x1401a439a  lea     rcx, [r8+28h]
0x1401a439e  cmp     rcx, rbp
0x1401a43a1  ja      short loc_1401A43EE
0x1401a43a3  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401a43a9  jbe     short loc_1401A43B2
0x1401a43ab  lea     r11, [rdx+20h]
0x1401a43af  add     r11, r8
0x1401a43b2  mov     r9, [r8+rdx+18h]
0x1401a43b7  jmp     short loc_1401A4415
0x1401a43b9  lea     rcx, [r8+38h]
0x1401a43bd  cmp     rcx, rbp
0x1401a43c0  ja      short loc_1401A43EE
0x1401a43c2  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a43c8  mov     r13b, dil
0x1401a43cb  jbe     short loc_1401A43D4
0x1401a43cd  lea     r11, [rdx+18h]
0x1401a43d1  add     r11, r8
0x1401a43d4  mov     r14b, [r8+rdx+8]
0x1401a43d9  mov     r9, [r8+rdx+10h]
0x1401a43de  mov     r10b, [r8+rdx+9]
0x1401a43e3  jmp     short loc_1401A43EE
0x1401a43e5  lea     rcx, [r8+28h]
0x1401a43e9  cmp     rcx, rbp
0x1401a43ec  jbe     short loc_1401A4401
0x1401a43ee  test    r13b, r13b
0x1401a43f1  jnz     short loc_1401A441F
0x1401a43f3  add     r15d, edi
0x1401a43f6  cmp     r15d, r12d
0x1401a43f9  jb      loc_1401A4373
0x1401a43ff  jmp     short loc_1401A441F
0x1401a4401  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a4407  jbe     short loc_1401A4410
0x1401a4409  lea     r11, [rdx+18h]
0x1401a440d  add     r11, r8
0x1401a4410  mov     r9, [r8+rdx+10h]
0x1401a4415  mov     r10b, [r8+rdx+9]
0x1401a441a  mov     r14b, [r8+rdx+8]
0x1401a441f  test    r11, r11
0x1401a4422  jz      loc_1401A4549
0x1401a4428  mov     cl, [r11]
0x1401a442b  jmp     short loc_1401A4444
0x1401a442d  mov     cl, [rdx+48h]
0x1401a4430  mov     r9, [rdx+20h]
0x1401a4434  mov     r10b, [rdx+0Bh]
0x1401a4438  mov     r14b, [rdx+4]
0x1401a443c  test    eax, eax
0x1401a443e  jnz     loc_1401A4549
0x1401a4444  sub     cl, 8
0x1401a4447  test    cl, 5Dh
0x1401a444a  jnz     loc_1401A4549
0x1401a4450  mov     bpl, [rdx+3]
0x1401a4454  cmp     bpl, dil
0x1401a4457  jz      loc_1401A44EA
0x1401a445d  test    r9, r9
0x1401a4460  jz      loc_1401A44EA
0x1401a4466  test    r10b, r10b
0x1401a4469  jz      short loc_1401A44EA
0x1401a446b  mov     al, [r9]
0x1401a446e  xor     dl, dl
0x1401a4470  and     al, 7Fh
0x1401a4472  movzx   ecx, r10b
0x1401a4476  sub     al, 72h ; 'r'
0x1401a4478  xor     r11b, r11b
0x1401a447b  xor     r8b, r8b
0x1401a447e  add     rcx, r9
0x1401a4481  cmp     al, dil
  ... truncated ...
```
