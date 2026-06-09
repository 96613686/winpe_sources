# NvmeAdapterFabricsGetSubsystemPortsIoctl

- ea: `0x1401a5a20`
- end: `0x1401a6041`
- name: `NvmeAdapterFabricsGetSubsystemPortsIoctl`
- size: `1569`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400fa14c`
- `0x1400fa1d0`
- `0x140100b40`
- `0x14014b400`
- `0x14014b800`
- `0x1401a5a20`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a5b09`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a5b09`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a5d5f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a5d5f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a5d02`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a5d02`
- `ntoskrnl!IofCompleteRequest` at `0x1401a600a`
- `ntoskrnl!IofCompleteRequest` at `0x1401a600a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a5c90`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a5d1e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a5c90`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a5d1e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a5d0e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a5d0e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a5b1f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a5b1f`

## pseudocode

```c
__int64 __fastcall NvmeAdapterFabricsGetSubsystemPortsIoctl(__int64 a1, _QWORD *a2)
{
  char v2; // si
  _QWORD *v3; // rbx
  __int64 v5; // rax
  __int64 v6; // rbp
  int v7; // edi
  __int64 HostGateway; // rax
  __int64 v9; // r13
  _WORD *v10; // r15
  unsigned int v11; // ecx
  __int64 *v12; // rbp
  _WORD *v13; // r14
  _DWORD *v14; // rcx
  __int64 v15; // rdx
  _OWORD *v16; // rcx
  _OWORD *v17; // rax
  __int128 v18; // xmm1
  _OWORD *v19; // rax
  __int64 v20; // rdx
  _OWORD *v21; // rcx
  __int128 v22; // xmm1
  __int64 v23; // rax
  bool v24; // zf
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  int *v27; // rax
  int v28; // ecx
  __int64 *v29; // rdx
  __int64 v30; // rdx
  unsigned int v31; // r12d
  unsigned __int8 v32; // r10
  char *v33; // r11
  char v34; // r14
  _BYTE *v35; // r9
  __int64 v36; // r15
  char v37; // r13
  unsigned __int64 v38; // rbp
  __int64 v39; // r8
  int v40; // ecx
  char v41; // cl
  char v42; // bp
  char v43; // r11
  char v44; // r8
  _BYTE *v45; // rax
  char *v46; // r8
  unsigned int v47; // eax
  __int128 v49; // [rsp+60h] [rbp-58h] BYREF

  v2 = 1;
  a2[7] = 0;
  v3 = a2;
  *(_QWORD *)&v49 = a2;
  if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && *(_QWORD *)(a1 + 616) )
  {
    v5 = a2[3];
    if ( v5 && (v6 = a2[23], *(_DWORD *)(v6 + 16) >= 0x10u) && *(_WORD *)v5 == 1 && *(_WORD *)(v5 + 2) >= 0x10u )
    {
      if ( *(_DWORD *)(v6 + 8) >= 8u )
      {
        HostGateway = NvmeAdapterGetHostGateway(a1, *(_QWORD *)(v5 + 8) ^ a1);
        v9 = HostGateway;
        if ( HostGateway )
        {
          v7 = NvmeAdapterHostGatewayAcquireRundown(HostGateway);
          if ( v7 >= 0 )
          {
            v10 = (_WORD *)v3[3];
            memset_0(v10, 0, *(unsigned int *)(v6 + 8));
            *v10 = 1;
            KeEnterCriticalRegion();
            ExAcquireResourceSharedLite((PERESOURCE)(v9 + 384), 1u);
            v11 = (unsigned __int16)(568 * *(_WORD *)(v9 + 376) + 8);
            v10[1] = v11;
            if ( *(_DWORD *)(v6 + 8) < v11 )
            {
              v23 = 8;
            }
            else
            {
              v12 = *(__int64 **)(v9 + 360);
              v13 = v10 + 4;
              if ( v12 != (__int64 *)(v9 + 360) )
              {
                do
                {
                  if ( (int)NvmeAdapterSubsystemPortAcquireRundown(v12 - 1) >= 0 )
                  {
                    *(_DWORD *)v13 = 37224449;
                    v14 = v13 + 2;
                    if ( (v12[3] & 1) != 0 )
                      *v14 |= 2u;
                    if ( (v12[3] & 2) != 0 )
                      *v14 |= 1u;
                    if ( (v12[3] & 4) != 0 )
                      *v14 |= 4u;
                    v15 = 2;
                    v16 = (_OWORD *)((char *)v12 + 52);
                    *((_QWORD *)v13 + 1) = a1 ^ (unsigned __int64)(v12 - 1);
                    v13[8] = *((_WORD *)v12 - 2);
                    v17 = v13 + 10;
                    do
                    {
                      *v17 = *v16;
                      v17[1] = v16[1];
                      v17[2] = v16[2];
                      v17[3] = v16[3];
                      v17[4] = v16[4];
                      v17[5] = v16[5];
                      v17[6] = v16[6];
                      v18 = v16[7];
                      v16 += 8;
                      v17[7] = v18;
                      v17 += 8;
                      --v15;
                    }
                    while ( v15 );
                    v19 = v13 + 138;
                    v20 = 2;
                    v21 = (_OWORD *)((char *)v12 + 308);
                    do
                    {
                      *v19 = *v21;
                      v19[1] = v21[1];
                      v19[2] = v21[2];
                      v19[3] = v21[3];
                      v19[4] = v21[4];
                      v19[5] = v21[5];
                      v19[6] = v21[6];
                      v22 = v21[7];
                      v21 += 8;
                      v19[7] = v22;
                      v19 += 8;
                      --v20;
                    }
                    while ( v20 );
                    *(_OWORD *)(v13 + 266) = *(_OWORD *)((char *)v12 + 564);
                    *(_OWORD *)(v13 + 274) = *(_OWORD *)((char *)v12 + 580);
                    ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v12[4]);
                    ++*((_DWORD *)v10 + 1);
                    v13 += 284;
                  }
                  v12 = (__int64 *)*v12;
                  v7 = 0;
                }
                while ( v12 != (__int64 *)(v9 + 360) );
                LOWORD(v11) = v10[1];
                v3 = (_QWORD *)v49;
              }
              if ( *((_DWORD *)v10 + 1) < *(_DWORD *)(v9 + 376) )
              {
                LOWORD(v11) = 568 * v10[2] + 8;
                v10[1] = v11;
              }
              v23 = (unsigned __int16)v11;
            }
            v3[7] = v23;
            ExReleaseResourceLite((PERESOURCE)(v9 + 384));
            KeLeaveCriticalRegion();
            ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v9 + 56));
          }
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
  v24 = StorEtwLoggingEnabled == 0;
  *((_BYTE *)v3 + 141) = -84;
  *((_DWORD *)v3 + 12) = v7;
  if ( v24 )
    goto LABEL_99;
  v49 = 0;
  IoGetActivityIdIrp(v3, &v49);
  v26 = v3[23];
  if ( *(_BYTE *)v26 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_99;
    v29 = EventNonReadWriteRequestComplete;
    goto LABEL_98;
  }
  if ( *(_BYTE *)v26 != 15 )
  {
    if ( *(_BYTE *)v26 != 27 )
      goto LABEL_99;
    if ( *(_BYTE *)(v26 + 1) == 7 && !*(_DWORD *)(v26 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v27 = (int *)v3[7];
        if ( v27 )
          v28 = *v27;
        else
          v28 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v28, v26, (unsigned int)&v49, (_DWORD)v3, v28, *((_DWORD *)v3 + 12));
      }
      goto LABEL_99;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_99;
    v29 = EventPnpRequestComplete;
LABEL_98:
    McTemplateK0pd_EtwWriteTransfer(v25, v29, &v49, v3, *((_DWORD *)v3 + 12));
    goto LABEL_99;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_99;
  v30 = *(_QWORD *)(v26 + 8);
  if ( *(_BYTE *)(v30 + 2) != 40 )
  {
    v41 = *(_BYTE *)(v30 + 72);
    v35 = *(_BYTE **)(v30 + 32);
    v32 = *(_BYTE *)(v30 + 11);
    v34 = *(_BYTE *)(v30 + 4);
    if ( *(_BYTE *)(v30 + 2) )
      goto LABEL_99;
LABEL_77:
    LOBYTE(v25) = v41 - 8;
    if ( (v25 & 0x5D) != 0 )
      goto LABEL_99;
    v42 = *(_BYTE *)(v30 + 3);
    if ( v42 == 1 || !v35 || !v32 )
      goto LABEL_94;
    LOBYTE(v30) = 0;
    v43 = 0;
    v44 = 0;
    v25 = (unsigned __int64)&v35[v32];
    v45 = v35 + 8;
    if ( (unsigned __int8)((*v35 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v45 <= v25 )
      {
        v43 = v35[2];
        LOBYTE(v30) = v35[1] & 0xF;
        v44 = v35[3];
        goto LABEL_93;
      }
    }
    else if ( (unsigned __int64)v45 <= v25 )
    {
      v46 = v35 + 13;
      LOBYTE(v30) = v35[2] & 0xF;
      v47 = v32;
      if ( (unsigned int)(unsigned __int8)v35[7] + 8 <= v32 )
        v47 = (unsigned __int8)v35[7] + 8;
      v25 = (unsigned __int64)&v35[v47];
      if ( (unsigned __int64)v46 <= v25 )
        v43 = v35[12];
      if ( (unsigned __int64)(v35 + 14) > v25 )
        v44 = 0;
      else
        v44 = *v46;
LABEL_93:
      if ( v2 )
      {
LABEL_95:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v25,
          v30,
          (unsigned int)&v49,
          (_DWORD)v3,
          *((_DWORD *)v3 + 12),
          v42,
          v34,
          v30,
          v43,
          v44,
          (char)v3);
        goto LABEL_99;
      }
LABEL_94:
      LOBYTE(v30) = 0;
      v43 = 0;
      v44 = 0;
      goto LABEL_95;
    }
    v2 = 0;
    goto LABEL_93;
  }
  if ( *(_DWORD *)(v30 + 20) )
    goto LABEL_99;
  v31 = *(_DWORD *)(v30 + 56);
  if ( !v31 )
    goto LABEL_99;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  while ( 1 )
  {
    v25 = *(unsigned int *)(v30 + 4 * v36 + 120);
    if ( (unsigned int)v25 >= 0x80 )
    {
      v38 = *(unsigned int *)(v30 + 16);
      if ( (unsigned int)v25 < (unsigned int)v38 )
        break;
    }
LABEL_68:
    v36 = (unsigned int)(v36 + 1);
    if ( (unsigned int)v36 >= v31 )
      goto LABEL_74;
  }
  v39 = (unsigned int)v25;
  v40 = *(_DWORD *)(v25 + v30) - 64;
  if ( v40 )
  {
    LODWORD(v25) = v40 - 1;
    if ( (_DWORD)v25 )
    {
      if ( (_DWORD)v25 == 1 )
      {
        LODWORD(v25) = v39 + 40;
        if ( v39 + 40 <= v38 )
        {
          if ( *(_DWORD *)(v39 + v30 + 12) )
            v33 = (char *)(v39 + v30 + 32);
          v35 = *(_BYTE **)(v39 + v30 + 24);
          goto LABEL_73;
        }
      }
    }
    else
    {
      LODWORD(v25) = v39 + 56;
      if ( v39 + 56 <= v38 )
      {
        v37 = 1;
        if ( *(_BYTE *)(v39 + v30 + 10) )
          v33 = (char *)(v39 + v30 + 24);
        v34 = *(_BYTE *)(v39 + v30 + 8);
        v35 = *(_BYTE **)(v39 + v30 + 16);
        v32 = *(_BYTE *)(v39 + v30 + 9);
      }
    }
    goto LABEL_67;
  }
  LODWORD(v25) = v39 + 40;
  if ( v39 + 40 > v38 )
  {
LABEL_67:
    if ( v37 )
      goto LABEL_74;
    goto LABEL_68;
  }
  if ( *(_BYTE *)(v39 + v30 + 10) )
    v33 = (char *)(v39 + v30 + 24);
  v35 = *(_BYTE **)(v39 + v30 + 16);
LABEL_73:
  v32 = *(_BYTE *)(v39 + v30 + 9);
  v34 = *(_BYTE *)(v39 + v30 + 8);
LABEL_74:
  if ( v33 )
  {
    v41 = *v33;
    goto LABEL_77;
  }
LABEL_99:
  IofCompleteRequest((PIRP)v3, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1401a5a20  mov     [rsp+arg_10], rbx
0x1401a5a25  push    rbp
0x1401a5a26  push    rsi
0x1401a5a27  push    rdi
0x1401a5a28  push    r12
0x1401a5a2a  push    r13
0x1401a5a2c  push    r14
0x1401a5a2e  push    r15
0x1401a5a30  sub     rsp, 80h
0x1401a5a37  mov     rax, cs:__security_cookie
0x1401a5a3e  xor     rax, rsp
0x1401a5a41  mov     [rsp+0B8h+var_48], rax
0x1401a5a46  mov     esi, 1
0x1401a5a4b  mov     qword ptr [rdx+38h], 0
0x1401a5a53  mov     rbx, rdx
0x1401a5a56  mov     qword ptr [rsp+0B8h+var_58], rdx
0x1401a5a5b  mov     r12, rcx
0x1401a5a5e  lea     r14d, [rsi+7]
0x1401a5a62  test    [rcx+98h], sil
0x1401a5a69  jz      loc_1401A5D33
0x1401a5a6f  cmp     qword ptr [rcx+268h], 0
0x1401a5a77  jz      loc_1401A5D33
0x1401a5a7d  mov     rax, [rdx+18h]
0x1401a5a81  test    rax, rax
0x1401a5a84  jz      loc_1401A5D2C
0x1401a5a8a  mov     rbp, [rdx+0B8h]
0x1401a5a91  lea     ecx, [rsi+0Fh]
0x1401a5a94  cmp     [rbp+10h], ecx
0x1401a5a97  jb      loc_1401A5D2C
0x1401a5a9d  cmp     [rax], si
0x1401a5aa0  jnz     loc_1401A5D2C
0x1401a5aa6  cmp     [rax+2], cx
0x1401a5aaa  jb      loc_1401A5D2C
0x1401a5ab0  cmp     [rbp+8], r14d
0x1401a5ab4  jnb     short loc_1401A5AC0
0x1401a5ab6  mov     edi, 0C0000023h
0x1401a5abb  jmp     loc_1401A5D38
0x1401a5ac0  mov     rdx, r12
0x1401a5ac3  mov     rcx, r12
0x1401a5ac6  xor     rdx, [rax+8]
0x1401a5aca  call    NvmeAdapterGetHostGateway
0x1401a5acf  mov     r13, rax
0x1401a5ad2  test    rax, rax
0x1401a5ad5  jnz     short loc_1401A5AE1
0x1401a5ad7  mov     edi, 0C0000225h
0x1401a5adc  jmp     loc_1401A5D38
0x1401a5ae1  mov     rcx, r13
0x1401a5ae4  call    NvmeAdapterHostGatewayAcquireRundown
0x1401a5ae9  mov     edi, eax
0x1401a5aeb  test    eax, eax
0x1401a5aed  js      loc_1401A5D38
0x1401a5af3  mov     r15, [rbx+18h]
0x1401a5af7  xor     edx, edx; Val
0x1401a5af9  mov     r8d, [rbp+8]; Size
0x1401a5afd  mov     rcx, r15; void *
0x1401a5b00  call    memset_0
0x1401a5b05  mov     [r15], si
0x1401a5b09  call    cs:__imp_KeEnterCriticalRegion
0x1401a5b10  nop     dword ptr [rax+rax+00h]
0x1401a5b15  lea     rcx, [r13+180h]; Resource
0x1401a5b1c  mov     dl, sil; Wait
0x1401a5b1f  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a5b26  nop     dword ptr [rax+rax+00h]
0x1401a5b2b  movzx   ecx, word ptr [r13+178h]
0x1401a5b33  mov     edx, 238h
0x1401a5b38  imul    ecx, edx
0x1401a5b3b  add     cx, r14w
0x1401a5b3f  movzx   ecx, cx
0x1401a5b42  mov     [r15+2], cx
0x1401a5b47  cmp     [rbp+8], ecx
0x1401a5b4a  jb      loc_1401A5CF4
0x1401a5b50  lea     rax, [r13+168h]
0x1401a5b57  mov     rbp, [rax]
0x1401a5b5a  lea     r14, [r15+8]
0x1401a5b5e  cmp     rbp, rax
0x1401a5b61  jz      loc_1401A5CC8
0x1401a5b67  lea     rbx, [r13+168h]
0x1401a5b6e  lea     rcx, [rbp-8]
0x1401a5b72  call    NvmeAdapterSubsystemPortAcquireRundown
0x1401a5b77  test    eax, eax
0x1401a5b79  js      loc_1401A5CAA
0x1401a5b7f  mov     dword ptr [r14], 2380001h
0x1401a5b86  lea     rcx, [r14+4]
0x1401a5b8a  test    [rbp+18h], sil
0x1401a5b8e  jz      short loc_1401A5B93
0x1401a5b90  or      dword ptr [rcx], 2
0x1401a5b93  test    byte ptr [rbp+18h], 2
0x1401a5b97  jz      short loc_1401A5B9B
0x1401a5b99  or      [rcx], esi
0x1401a5b9b  test    byte ptr [rbp+18h], 4
0x1401a5b9f  jz      short loc_1401A5BA4
0x1401a5ba1  or      dword ptr [rcx], 4
0x1401a5ba4  lea     rax, [rbp-8]
0x1401a5ba8  mov     edx, 2
0x1401a5bad  xor     rax, r12
0x1401a5bb0  lea     rcx, [rbp+34h]
0x1401a5bb4  mov     [r14+8], rax
0x1401a5bb8  movzx   eax, word ptr [rbp-4]
0x1401a5bbc  mov     [r14+10h], ax
0x1401a5bc1  lea     r8d, [rdx+7Eh]
0x1401a5bc5  lea     rax, [r14+14h]
0x1401a5bc9  movups  xmm0, xmmword ptr [rcx]
0x1401a5bcc  movups  xmmword ptr [rax], xmm0
0x1401a5bcf  movups  xmm1, xmmword ptr [rcx+10h]
0x1401a5bd3  movups  xmmword ptr [rax+10h], xmm1
0x1401a5bd7  movups  xmm0, xmmword ptr [rcx+20h]
0x1401a5bdb  movups  xmmword ptr [rax+20h], xmm0
0x1401a5bdf  movups  xmm1, xmmword ptr [rcx+30h]
0x1401a5be3  movups  xmmword ptr [rax+30h], xmm1
0x1401a5be7  movups  xmm0, xmmword ptr [rcx+40h]
0x1401a5beb  movups  xmmword ptr [rax+40h], xmm0
0x1401a5bef  movups  xmm1, xmmword ptr [rcx+50h]
0x1401a5bf3  movups  xmmword ptr [rax+50h], xmm1
0x1401a5bf7  movups  xmm0, xmmword ptr [rcx+60h]
0x1401a5bfb  movups  xmmword ptr [rax+60h], xmm0
0x1401a5bff  movups  xmm1, xmmword ptr [rcx+70h]
0x1401a5c03  add     rcx, r8
0x1401a5c06  movups  xmmword ptr [rax+70h], xmm1
0x1401a5c0a  add     rax, r8
0x1401a5c0d  sub     rdx, rsi
0x1401a5c10  jnz     short loc_1401A5BC9
0x1401a5c12  lea     rax, [r14+114h]
0x1401a5c19  mov     edx, 2
0x1401a5c1e  lea     rcx, [rbp+134h]
0x1401a5c25  movups  xmm0, xmmword ptr [rcx]
0x1401a5c28  movups  xmmword ptr [rax], xmm0
0x1401a5c2b  movups  xmm1, xmmword ptr [rcx+10h]
0x1401a5c2f  movups  xmmword ptr [rax+10h], xmm1
0x1401a5c33  movups  xmm0, xmmword ptr [rcx+20h]
0x1401a5c37  movups  xmmword ptr [rax+20h], xmm0
0x1401a5c3b  movups  xmm1, xmmword ptr [rcx+30h]
0x1401a5c3f  movups  xmmword ptr [rax+30h], xmm1
0x1401a5c43  movups  xmm0, xmmword ptr [rcx+40h]
0x1401a5c47  movups  xmmword ptr [rax+40h], xmm0
0x1401a5c4b  movups  xmm1, xmmword ptr [rcx+50h]
0x1401a5c4f  movups  xmmword ptr [rax+50h], xmm1
0x1401a5c53  movups  xmm0, xmmword ptr [rcx+60h]
0x1401a5c57  movups  xmmword ptr [rax+60h], xmm0
0x1401a5c5b  movups  xmm1, xmmword ptr [rcx+70h]
0x1401a5c5f  add     rcx, r8
0x1401a5c62  movups  xmmword ptr [rax+70h], xmm1
0x1401a5c66  add     rax, r8
0x1401a5c69  sub     rdx, rsi
0x1401a5c6c  jnz     short loc_1401A5C25
0x1401a5c6e  movups  xmm0, xmmword ptr [rbp+234h]
0x1401a5c75  movups  xmmword ptr [r14+214h], xmm0
0x1401a5c7d  movups  xmm1, xmmword ptr [rbp+244h]
0x1401a5c84  movups  xmmword ptr [r14+224h], xmm1
0x1401a5c8c  mov     rcx, [rbp+20h]; RunRefCacheAware
0x1401a5c90  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a5c97  nop     dword ptr [rax+rax+00h]
0x1401a5c9c  add     [r15+4], esi
0x1401a5ca0  mov     edx, 238h
0x1401a5ca5  add     r14, rdx
0x1401a5ca8  jmp     short loc_1401A5CAF
0x1401a5caa  mov     edx, 238h
0x1401a5caf  mov     rbp, [rbp+0]
0x1401a5cb3  xor     edi, edi
0x1401a5cb5  cmp     rbp, rbx
0x1401a5cb8  jnz     loc_1401A5B6E
0x1401a5cbe  movzx   ecx, word ptr [r15+2]
0x1401a5cc3  mov     rbx, qword ptr [rsp+0B8h+var_58]
0x1401a5cc8  mov     eax, [r13+178h]
0x1401a5ccf  mov     r14d, 8
0x1401a5cd5  cmp     [r15+4], eax
0x1401a5cd9  jnb     short loc_1401A5CEF
0x1401a5cdb  movzx   ecx, word ptr [r15+4]
0x1401a5ce0  movzx   eax, dx
0x1401a5ce3  imul    ecx, eax
0x1401a5ce6  add     cx, r14w
0x1401a5cea  mov     [r15+2], cx
0x1401a5cef  movzx   eax, cx
0x1401a5cf2  jmp     short loc_1401A5CF7
0x1401a5cf4  mov     rax, r14
0x1401a5cf7  lea     rcx, [r13+180h]; Resource
0x1401a5cfe  mov     [rbx+38h], rax
0x1401a5d02  call    cs:__imp_ExReleaseResourceLite
0x1401a5d09  nop     dword ptr [rax+rax+00h]
0x1401a5d0e  call    cs:__imp_KeLeaveCriticalRegion
0x1401a5d15  nop     dword ptr [rax+rax+00h]
0x1401a5d1a  mov     rcx, [r13+38h]; RunRefCacheAware
0x1401a5d1e  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a5d25  nop     dword ptr [rax+rax+00h]
0x1401a5d2a  jmp     short loc_1401A5D38
0x1401a5d2c  mov     edi, 0C000000Dh
0x1401a5d31  jmp     short loc_1401A5D38
0x1401a5d33  mov     edi, 0C00000BBh
0x1401a5d38  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a5d3f  mov     byte ptr [rbx+8Dh], 0ACh
0x1401a5d46  mov     [rbx+30h], edi
0x1401a5d49  jz      loc_1401A6005
0x1401a5d4f  xorps   xmm0, xmm0
0x1401a5d52  lea     rdx, [rsp+0B8h+var_58]
0x1401a5d57  mov     rcx, rbx
0x1401a5d5a  movups  [rsp+0B8h+var_58], xmm0
0x1401a5d5f  call    cs:__imp_IoGetActivityIdIrp
0x1401a5d66  nop     dword ptr [rax+rax+00h]
0x1401a5d6b  mov     rdx, [rbx+0B8h]
0x1401a5d72  movzx   eax, byte ptr [rdx]
0x1401a5d75  sub     eax, 0Eh
0x1401a5d78  jz      loc_1401A5FE1
0x1401a5d7e  sub     eax, esi
0x1401a5d80  jz      short loc_1401A5DE9
0x1401a5d82  cmp     eax, 0Ch
0x1401a5d85  jnz     loc_1401A6005
0x1401a5d8b  cmp     byte ptr [rdx+1], 7
0x1401a5d8f  jnz     short loc_1401A5DD0
0x1401a5d91  cmp     dword ptr [rdx+8], 0
0x1401a5d95  jnz     short loc_1401A5DD0
0x1401a5d97  test    cs:byte_140177432, 40h
0x1401a5d9e  jz      loc_1401A6005
0x1401a5da4  mov     rax, [rbx+38h]
0x1401a5da8  test    rax, rax
0x1401a5dab  jz      short loc_1401A5DB1
0x1401a5dad  mov     ecx, [rax]
0x1401a5daf  jmp     short loc_1401A5DB3
0x1401a5db1  xor     ecx, ecx
0x1401a5db3  mov     eax, [rbx+30h]
0x1401a5db6  lea     r8, [rsp+0B8h+var_58]
0x1401a5dbb  mov     [rsp+0B8h+var_90], eax
0x1401a5dbf  mov     r9, rbx
0x1401a5dc2  mov     [rsp+0B8h+var_98], ecx
0x1401a5dc6  call    McTemplateK0pqd_EtwWriteTransfer
0x1401a5dcb  jmp     loc_1401A6005
0x1401a5dd0  test    cs:byte_140177432, 20h
0x1401a5dd7  jz      loc_1401A6005
0x1401a5ddd  lea     rdx, EventPnpRequestComplete
0x1401a5de4  jmp     loc_1401A5FF1
0x1401a5de9  cmp     cs:byte_140177431, 0
0x1401a5df0  jge     loc_1401A6005
0x1401a5df6  mov     rdx, [rdx+8]
0x1401a5dfa  movzx   eax, byte ptr [rdx+2]
0x1401a5dfe  cmp     al, 28h ; '('
0x1401a5e00  jnz     loc_1401A5EE9
0x1401a5e06  cmp     dword ptr [rdx+14h], 0
0x1401a5e0a  jnz     loc_1401A6005
0x1401a5e10  mov     r12d, [rdx+38h]
0x1401a5e14  test    r12d, r12d
0x1401a5e17  jz      loc_1401A6005
0x1401a5e1d  xor     r10b, r10b
0x1401a5e20  xor     r11d, r11d
0x1401a5e23  xor     r14b, r14b
0x1401a5e26  xor     r9d, r9d
0x1401a5e29  xor     r15d, r15d
0x1401a5e2c  xor     r13b, r13b
0x1401a5e2f  mov     ecx, [rdx+r15*4+78h]
0x1401a5e34  cmp     ecx, 80h
0x1401a5e3a  jb      short loc_1401A5EAF
0x1401a5e3c  mov     ebp, [rdx+10h]
0x1401a5e3f  cmp     ecx, ebp
0x1401a5e41  jnb     short loc_1401A5EAF
0x1401a5e43  mov     r8d, ecx
0x1401a5e46  mov     ecx, [rcx+rdx]
0x1401a5e49  sub     ecx, 40h ; '@'
0x1401a5e4c  jz      short loc_1401A5EA1
0x1401a5e4e  sub     ecx, esi
0x1401a5e50  jz      short loc_1401A5E75
0x1401a5e52  cmp     ecx, esi
0x1401a5e54  jnz     short loc_1401A5EAA
0x1401a5e56  lea     rcx, [r8+28h]
0x1401a5e5a  cmp     rcx, rbp
0x1401a5e5d  ja      short loc_1401A5EAA
0x1401a5e5f  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401a5e65  jbe     short loc_1401A5E6E
0x1401a5e67  lea     r11, [rdx+20h]
0x1401a5e6b  add     r11, r8
0x1401a5e6e  mov     r9, [r8+rdx+18h]
0x1401a5e73  jmp     short loc_1401A5ED1
0x1401a5e75  lea     rcx, [r8+38h]
0x1401a5e79  cmp     rcx, rbp
0x1401a5e7c  ja      short loc_1401A5EAA
0x1401a5e7e  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a5e84  mov     r13b, sil
0x1401a5e87  jbe     short loc_1401A5E90
0x1401a5e89  lea     r11, [rdx+18h]
0x1401a5e8d  add     r11, r8
0x1401a5e90  mov     r14b, [r8+rdx+8]
0x1401a5e95  mov     r9, [r8+rdx+10h]
0x1401a5e9a  mov     r10b, [r8+rdx+9]
0x1401a5e9f  jmp     short loc_1401A5EAA
0x1401a5ea1  lea     rcx, [r8+28h]
0x1401a5ea5  cmp     rcx, rbp
0x1401a5ea8  jbe     short loc_1401A5EBD
0x1401a5eaa  test    r13b, r13b
0x1401a5ead  jnz     short loc_1401A5EDB
0x1401a5eaf  add     r15d, esi
0x1401a5eb2  cmp     r15d, r12d
0x1401a5eb5  jb      loc_1401A5E2F
0x1401a5ebb  jmp     short loc_1401A5EDB
0x1401a5ebd  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a5ec3  jbe     short loc_1401A5ECC
0x1401a5ec5  lea     r11, [rdx+18h]
0x1401a5ec9  add     r11, r8
0x1401a5ecc  mov     r9, [r8+rdx+10h]
0x1401a5ed1  mov     r10b, [r8+rdx+9]
0x1401a5ed6  mov     r14b, [r8+rdx+8]
0x1401a5edb  test    r11, r11
0x1401a5ede  jz      loc_1401A6005
0x1401a5ee4  mov     cl, [r11]
0x1401a5ee7  jmp     short loc_1401A5F00
  ... truncated ...
```
