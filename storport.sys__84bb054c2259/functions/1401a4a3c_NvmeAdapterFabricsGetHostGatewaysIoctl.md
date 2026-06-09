# NvmeAdapterFabricsGetHostGatewaysIoctl

- ea: `0x1401a4a3c`
- end: `0x1401a4f94`
- name: `NvmeAdapterFabricsGetHostGatewaysIoctl`
- size: `1368`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400fa1d0`
- `0x14014b400`
- `0x14014b800`
- `0x1401a4a3c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a4ad4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a4ad4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a4cb0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a4cb0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a4c5e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a4c5e`
- `ntoskrnl!IofCompleteRequest` at `0x1401a4f5c`
- `ntoskrnl!IofCompleteRequest` at `0x1401a4f5c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a4bec`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a4bec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a4c6a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a4c6a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a4ae7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a4ae7`

## pseudocode

```c
__int64 __fastcall NvmeAdapterFabricsGetHostGatewaysIoctl(__int64 a1, _QWORD *a2)
{
  char v2; // si
  _QWORD *v3; // rdi
  _QWORD *v5; // r13
  __int64 v6; // r14
  unsigned int v7; // r15d
  _WORD *v8; // r15
  __int64 v9; // rbx
  unsigned __int16 v10; // cx
  __int64 **v11; // rax
  _WORD *v12; // rbx
  __int64 **v13; // r12
  _OWORD *v14; // rcx
  __int64 v15; // rdx
  _OWORD *v16; // rax
  __int128 v17; // xmm1
  __int64 v18; // rax
  bool v19; // zf
  unsigned __int64 v20; // rcx
  _BYTE *v21; // rdx
  int *v22; // rax
  int v23; // ecx
  __int64 v24; // rdx
  unsigned int v25; // r12d
  unsigned __int8 v26; // r10
  char *v27; // r11
  char v28; // bl
  _BYTE *v29; // r9
  __int64 v30; // r14
  char v31; // r13
  unsigned __int64 v32; // rbp
  __int64 v33; // r8
  int v34; // ecx
  char v35; // cl
  char v36; // bp
  char v37; // r11
  char v38; // r8
  _BYTE *v39; // rax
  char *v40; // r8
  unsigned int v41; // eax
  __int128 v43; // [rsp+60h] [rbp-58h] BYREF

  v2 = 1;
  a2[7] = 0;
  v3 = a2;
  *(_QWORD *)&v43 = a2;
  if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && *(_QWORD *)(a1 + 616) )
  {
    v5 = a2 + 23;
    v6 = a2[23];
    if ( *(_DWORD *)(v6 + 8) >= 8u )
    {
      v8 = (_WORD *)a2[3];
      memset_0(v8, 0, *(unsigned int *)(v6 + 8));
      *v8 = 1;
      v9 = *(_QWORD *)(a1 + 616);
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite((PERESOURCE)(v9 + 24), 1u);
      v10 = 320 * *(_WORD *)(*(_QWORD *)(a1 + 616) + 16LL) + 8;
      v8[1] = v10;
      if ( *(_DWORD *)(v6 + 8) < (unsigned int)v10 )
      {
        v18 = 8;
      }
      else
      {
        v11 = *(__int64 ***)(a1 + 616);
        v12 = v8 + 4;
        v13 = (__int64 **)*v11;
        if ( *v11 != (__int64 *)v11 )
        {
          do
          {
            if ( (int)NvmeAdapterHostGatewayAcquireRundown(v13 - 3) >= 0 )
            {
              *(_DWORD *)v12 = 20971521;
              v14 = v13 + 6;
              *((_QWORD *)v12 + 1) = a1 ^ (unsigned __int64)(v13 - 3);
              v15 = 2;
              *((_DWORD *)v12 + 5) = *((_DWORD *)v13 - 5);
              *((_DWORD *)v12 + 6) = *((_DWORD *)v13 - 4);
              v16 = v12 + 14;
              do
              {
                *v16 = *v14;
                v16[1] = v14[1];
                v16[2] = v14[2];
                v16[3] = v14[3];
                v16[4] = v14[4];
                v16[5] = v14[5];
                v16[6] = v14[6];
                v17 = v14[7];
                v14 += 8;
                v16[7] = v17;
                v16 += 8;
                --v15;
              }
              while ( v15 );
              *(_OWORD *)(v12 + 142) = *((_OWORD *)v13 + 19);
              *(_OWORD *)(v12 + 150) = *((_OWORD *)v13 + 20);
              ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v13[4]);
              ++*((_DWORD *)v8 + 1);
              v12 += 160;
            }
            v13 = (__int64 **)*v13;
            v11 = *(__int64 ***)(a1 + 616);
          }
          while ( v13 != v11 );
          v10 = v8[1];
          v3 = (_QWORD *)v43;
        }
        if ( *((_DWORD *)v8 + 1) < *((_DWORD *)v11 + 4) )
        {
          v10 = 320 * v8[2] + 8;
          v8[1] = v10;
        }
        v18 = v10;
      }
      v3[7] = v18;
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 616) + 24LL));
      KeLeaveCriticalRegion();
      v7 = 0;
    }
    else
    {
      v7 = -1073741789;
    }
  }
  else
  {
    v7 = -1073741637;
    v5 = a2 + 23;
  }
  v19 = StorEtwLoggingEnabled == 0;
  *((_BYTE *)v3 + 141) = -84;
  *((_DWORD *)v3 + 12) = v7;
  if ( v19 )
    goto LABEL_82;
  v43 = 0;
  IoGetActivityIdIrp(v3, &v43);
  v21 = (_BYTE *)*v5;
  if ( *(_BYTE *)*v5 == 14 )
  {
    if ( (byte_140177432 & 8) != 0 )
      McTemplateK0pd_EtwWriteTransfer(v20, EventNonReadWriteRequestComplete, &v43, v3, *((_DWORD *)v3 + 12));
    goto LABEL_82;
  }
  if ( *(_BYTE *)*v5 != 15 )
  {
    if ( *(_BYTE *)*v5 == 27 )
    {
      if ( v21[1] != 7 || *((_DWORD *)v21 + 2) )
      {
        if ( (byte_140177432 & 0x20) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v20, EventPnpRequestComplete, &v43, v3, *((_DWORD *)v3 + 12));
      }
      else if ( (byte_140177432 & 0x40) != 0 )
      {
        v22 = (int *)v3[7];
        if ( v22 )
          v23 = *v22;
        else
          v23 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v23, (_DWORD)v21, (unsigned int)&v43, (_DWORD)v3, v23, *((_DWORD *)v3 + 12));
      }
    }
    goto LABEL_82;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_82;
  v24 = *((_QWORD *)v21 + 1);
  if ( *(_BYTE *)(v24 + 2) != 40 )
  {
    v35 = *(_BYTE *)(v24 + 72);
    v29 = *(_BYTE **)(v24 + 32);
    v26 = *(_BYTE *)(v24 + 11);
    v28 = *(_BYTE *)(v24 + 4);
    if ( *(_BYTE *)(v24 + 2) )
      goto LABEL_82;
LABEL_61:
    LOBYTE(v20) = v35 - 8;
    if ( (v20 & 0x5D) != 0 )
      goto LABEL_82;
    v36 = *(_BYTE *)(v24 + 3);
    if ( v36 == 1 || !v29 || !v26 )
      goto LABEL_78;
    LOBYTE(v24) = 0;
    v37 = 0;
    v38 = 0;
    v20 = (unsigned __int64)&v29[v26];
    v39 = v29 + 8;
    if ( (unsigned __int8)((*v29 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v39 <= v20 )
      {
        v37 = v29[2];
        LOBYTE(v24) = v29[1] & 0xF;
        v38 = v29[3];
        goto LABEL_77;
      }
    }
    else if ( (unsigned __int64)v39 <= v20 )
    {
      v40 = v29 + 13;
      LOBYTE(v24) = v29[2] & 0xF;
      v41 = v26;
      if ( (unsigned int)(unsigned __int8)v29[7] + 8 <= v26 )
        v41 = (unsigned __int8)v29[7] + 8;
      v20 = (unsigned __int64)&v29[v41];
      if ( (unsigned __int64)v40 <= v20 )
        v37 = v29[12];
      if ( (unsigned __int64)(v29 + 14) > v20 )
        v38 = 0;
      else
        v38 = *v40;
LABEL_77:
      if ( v2 )
      {
LABEL_79:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v20,
          v24,
          (unsigned int)&v43,
          (_DWORD)v3,
          *((_DWORD *)v3 + 12),
          v36,
          v28,
          v24,
          v37,
          v38,
          (char)v3);
        goto LABEL_82;
      }
LABEL_78:
      LOBYTE(v24) = 0;
      v37 = 0;
      v38 = 0;
      goto LABEL_79;
    }
    v2 = 0;
    goto LABEL_77;
  }
  if ( *(_DWORD *)(v24 + 20) )
    goto LABEL_82;
  v25 = *(_DWORD *)(v24 + 56);
  if ( !v25 )
    goto LABEL_82;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  while ( 1 )
  {
    v20 = *(unsigned int *)(v24 + 4 * v30 + 120);
    if ( (unsigned int)v20 >= 0x80 )
    {
      v32 = *(unsigned int *)(v24 + 16);
      if ( (unsigned int)v20 < (unsigned int)v32 )
        break;
    }
LABEL_52:
    v30 = (unsigned int)(v30 + 1);
    if ( (unsigned int)v30 >= v25 )
      goto LABEL_58;
  }
  v33 = (unsigned int)v20;
  v34 = *(_DWORD *)(v20 + v24) - 64;
  if ( v34 )
  {
    LODWORD(v20) = v34 - 1;
    if ( (_DWORD)v20 )
    {
      if ( (_DWORD)v20 == 1 )
      {
        LODWORD(v20) = v33 + 40;
        if ( v33 + 40 <= v32 )
        {
          if ( *(_DWORD *)(v33 + v24 + 12) )
            v27 = (char *)(v33 + v24 + 32);
          v29 = *(_BYTE **)(v33 + v24 + 24);
          goto LABEL_57;
        }
      }
    }
    else
    {
      LODWORD(v20) = v33 + 56;
      if ( v33 + 56 <= v32 )
      {
        v31 = 1;
        if ( *(_BYTE *)(v33 + v24 + 10) )
          v27 = (char *)(v33 + v24 + 24);
        v28 = *(_BYTE *)(v33 + v24 + 8);
        v29 = *(_BYTE **)(v33 + v24 + 16);
        v26 = *(_BYTE *)(v33 + v24 + 9);
      }
    }
    goto LABEL_51;
  }
  LODWORD(v20) = v33 + 40;
  if ( v33 + 40 > v32 )
  {
LABEL_51:
    if ( v31 )
      goto LABEL_58;
    goto LABEL_52;
  }
  if ( *(_BYTE *)(v33 + v24 + 10) )
    v27 = (char *)(v33 + v24 + 24);
  v29 = *(_BYTE **)(v33 + v24 + 16);
LABEL_57:
  v26 = *(_BYTE *)(v33 + v24 + 9);
  v28 = *(_BYTE *)(v33 + v24 + 8);
LABEL_58:
  if ( v27 )
  {
    v35 = *v27;
    goto LABEL_61;
  }
LABEL_82:
  IofCompleteRequest((PIRP)v3, 0);
  return v7;
}

```

## disassembly

```asm
0x1401a4a3c  mov     [rsp+arg_10], rbx
0x1401a4a41  push    rbp
0x1401a4a42  push    rsi
0x1401a4a43  push    rdi
0x1401a4a44  push    r12
0x1401a4a46  push    r13
0x1401a4a48  push    r14
0x1401a4a4a  push    r15
0x1401a4a4c  sub     rsp, 80h
0x1401a4a53  mov     rax, cs:__security_cookie
0x1401a4a5a  xor     rax, rsp
0x1401a4a5d  mov     [rsp+0B8h+var_48], rax
0x1401a4a62  mov     esi, 1
0x1401a4a67  mov     qword ptr [rdx+38h], 0
0x1401a4a6f  mov     rdi, rdx
0x1401a4a72  mov     qword ptr [rsp+0B8h+var_58], rdx
0x1401a4a77  mov     rbp, rcx
0x1401a4a7a  lea     r12d, [rsi+7]
0x1401a4a7e  test    [rcx+98h], sil
0x1401a4a85  jz      loc_1401A4C7B
0x1401a4a8b  cmp     qword ptr [rcx+268h], 0
0x1401a4a93  jz      loc_1401A4C7B
0x1401a4a99  lea     r13, [rdx+0B8h]
0x1401a4aa0  mov     r14, [r13+0]
0x1401a4aa4  mov     eax, [r14+8]
0x1401a4aa8  cmp     eax, r12d
0x1401a4aab  jnb     short loc_1401A4AB8
0x1401a4aad  mov     r15d, 0C0000023h
0x1401a4ab3  jmp     loc_1401A4C88
0x1401a4ab8  mov     r15, [rdx+18h]
0x1401a4abc  mov     r8, rax; Size
0x1401a4abf  mov     rcx, r15; void *
0x1401a4ac2  xor     edx, edx; Val
0x1401a4ac4  call    memset_0
0x1401a4ac9  mov     [r15], si
0x1401a4acd  mov     rbx, [rbp+268h]
0x1401a4ad4  call    cs:__imp_KeEnterCriticalRegion
0x1401a4adb  nop     dword ptr [rax+rax+00h]
0x1401a4ae0  mov     dl, sil; Wait
0x1401a4ae3  lea     rcx, [rbx+18h]; Resource
0x1401a4ae7  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a4aee  nop     dword ptr [rax+rax+00h]
0x1401a4af3  mov     rcx, [rbp+268h]
0x1401a4afa  mov     r8d, 140h
0x1401a4b00  movzx   edx, word ptr [rcx+10h]
0x1401a4b04  imul    edx, r8d
0x1401a4b08  add     dx, r12w
0x1401a4b0c  movzx   ecx, dx
0x1401a4b0f  mov     [r15+2], cx
0x1401a4b14  cmp     [r14+8], ecx
0x1401a4b18  jb      loc_1401A4C4C
0x1401a4b1e  mov     rax, [rbp+268h]
0x1401a4b25  lea     rbx, [r15+8]
0x1401a4b29  mov     r12, [rax]
0x1401a4b2c  cmp     r12, rax
0x1401a4b2f  jz      loc_1401A4C23
0x1401a4b35  mov     edi, r8d
0x1401a4b38  lea     rcx, [r12-18h]
0x1401a4b3d  call    NvmeAdapterHostGatewayAcquireRundown
0x1401a4b42  test    eax, eax
0x1401a4b44  js      loc_1401A4BFF
0x1401a4b4a  mov     dword ptr [rbx], 1400001h
0x1401a4b50  lea     rax, [r12-18h]
0x1401a4b55  xor     rax, rbp
0x1401a4b58  lea     rcx, [r12+30h]
0x1401a4b5d  mov     [rbx+8], rax
0x1401a4b61  mov     edx, 2
0x1401a4b66  mov     eax, [r12-14h]
0x1401a4b6b  mov     [rbx+14h], eax
0x1401a4b6e  mov     eax, [r12-10h]
0x1401a4b73  mov     [rbx+18h], eax
0x1401a4b76  lea     r8d, [rdx+7Eh]
0x1401a4b7a  lea     rax, [rbx+1Ch]
0x1401a4b7e  movups  xmm0, xmmword ptr [rcx]
0x1401a4b81  movups  xmmword ptr [rax], xmm0
0x1401a4b84  movups  xmm1, xmmword ptr [rcx+10h]
0x1401a4b88  movups  xmmword ptr [rax+10h], xmm1
0x1401a4b8c  movups  xmm0, xmmword ptr [rcx+20h]
0x1401a4b90  movups  xmmword ptr [rax+20h], xmm0
0x1401a4b94  movups  xmm1, xmmword ptr [rcx+30h]
0x1401a4b98  movups  xmmword ptr [rax+30h], xmm1
0x1401a4b9c  movups  xmm0, xmmword ptr [rcx+40h]
0x1401a4ba0  movups  xmmword ptr [rax+40h], xmm0
0x1401a4ba4  movups  xmm1, xmmword ptr [rcx+50h]
0x1401a4ba8  movups  xmmword ptr [rax+50h], xmm1
0x1401a4bac  movups  xmm0, xmmword ptr [rcx+60h]
0x1401a4bb0  movups  xmmword ptr [rax+60h], xmm0
0x1401a4bb4  movups  xmm1, xmmword ptr [rcx+70h]
0x1401a4bb8  add     rcx, r8
0x1401a4bbb  movups  xmmword ptr [rax+70h], xmm1
0x1401a4bbf  add     rax, r8
0x1401a4bc2  sub     rdx, rsi
0x1401a4bc5  jnz     short loc_1401A4B7E
0x1401a4bc7  movups  xmm0, xmmword ptr [r12+130h]
0x1401a4bd0  movups  xmmword ptr [rbx+11Ch], xmm0
0x1401a4bd7  movups  xmm1, xmmword ptr [r12+140h]
0x1401a4be0  movups  xmmword ptr [rbx+12Ch], xmm1
0x1401a4be7  mov     rcx, [r12+20h]; RunRefCacheAware
0x1401a4bec  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a4bf3  nop     dword ptr [rax+rax+00h]
0x1401a4bf8  add     [r15+4], esi
0x1401a4bfc  add     rbx, rdi
0x1401a4bff  mov     r12, [r12]
0x1401a4c03  mov     rax, [rbp+268h]
0x1401a4c0a  cmp     r12, rax
0x1401a4c0d  jnz     loc_1401A4B38
0x1401a4c13  movzx   ecx, word ptr [r15+2]
0x1401a4c18  mov     r8d, 140h
0x1401a4c1e  mov     rdi, qword ptr [rsp+0B8h+var_58]
0x1401a4c23  mov     eax, [rax+10h]
0x1401a4c26  mov     r12d, 8
0x1401a4c2c  cmp     [r15+4], eax
0x1401a4c30  jnb     short loc_1401A4C47
0x1401a4c32  movzx   ecx, word ptr [r15+4]
0x1401a4c37  movzx   eax, r8w
0x1401a4c3b  imul    ecx, eax
0x1401a4c3e  add     cx, r12w
0x1401a4c42  mov     [r15+2], cx
0x1401a4c47  movzx   eax, cx
0x1401a4c4a  jmp     short loc_1401A4C4F
0x1401a4c4c  mov     rax, r12
0x1401a4c4f  mov     [rdi+38h], rax
0x1401a4c53  mov     rcx, [rbp+268h]
0x1401a4c5a  add     rcx, 18h; Resource
0x1401a4c5e  call    cs:__imp_ExReleaseResourceLite
0x1401a4c65  nop     dword ptr [rax+rax+00h]
0x1401a4c6a  call    cs:__imp_KeLeaveCriticalRegion
0x1401a4c71  nop     dword ptr [rax+rax+00h]
0x1401a4c76  xor     r15d, r15d
0x1401a4c79  jmp     short loc_1401A4C88
0x1401a4c7b  mov     r15d, 0C00000BBh
0x1401a4c81  lea     r13, [rdx+0B8h]
0x1401a4c88  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a4c8f  mov     byte ptr [rdi+8Dh], 0ACh
0x1401a4c96  mov     [rdi+30h], r15d
0x1401a4c9a  jz      loc_1401A4F57
0x1401a4ca0  xorps   xmm0, xmm0
0x1401a4ca3  lea     rdx, [rsp+0B8h+var_58]
0x1401a4ca8  mov     rcx, rdi
0x1401a4cab  movups  [rsp+0B8h+var_58], xmm0
0x1401a4cb0  call    cs:__imp_IoGetActivityIdIrp
0x1401a4cb7  nop     dword ptr [rax+rax+00h]
0x1401a4cbc  mov     rdx, [r13+0]
0x1401a4cc0  movzx   eax, byte ptr [rdx]
0x1401a4cc3  sub     eax, 0Eh
0x1401a4cc6  jz      loc_1401A4F33
0x1401a4ccc  sub     eax, esi
0x1401a4cce  jz      short loc_1401A4D3E
0x1401a4cd0  cmp     eax, 0Ch
0x1401a4cd3  jnz     loc_1401A4F57
0x1401a4cd9  cmp     byte ptr [rdx+1], 7
0x1401a4cdd  jnz     short loc_1401A4D1E
0x1401a4cdf  cmp     dword ptr [rdx+8], 0
0x1401a4ce3  jnz     short loc_1401A4D1E
0x1401a4ce5  test    cs:byte_140177432, 40h
0x1401a4cec  jz      loc_1401A4F57
0x1401a4cf2  mov     rax, [rdi+38h]
0x1401a4cf6  test    rax, rax
0x1401a4cf9  jz      short loc_1401A4CFF
0x1401a4cfb  mov     ecx, [rax]
0x1401a4cfd  jmp     short loc_1401A4D01
0x1401a4cff  xor     ecx, ecx
0x1401a4d01  mov     eax, [rdi+30h]
0x1401a4d04  lea     r8, [rsp+0B8h+var_58]
0x1401a4d09  mov     [rsp+0B8h+var_90], eax
0x1401a4d0d  mov     r9, rdi
0x1401a4d10  mov     [rsp+0B8h+var_98], ecx
0x1401a4d14  call    McTemplateK0pqd_EtwWriteTransfer
0x1401a4d19  jmp     loc_1401A4F57
0x1401a4d1e  test    cs:byte_140177432, 20h
0x1401a4d25  jz      loc_1401A4F57
0x1401a4d2b  mov     eax, [rdi+30h]
0x1401a4d2e  lea     rdx, EventPnpRequestComplete
0x1401a4d35  mov     [rsp+0B8h+var_98], eax
0x1401a4d39  jmp     loc_1401A4F4A
0x1401a4d3e  cmp     cs:byte_140177431, 0
0x1401a4d45  jge     loc_1401A4F57
0x1401a4d4b  mov     rdx, [rdx+8]
0x1401a4d4f  movzx   eax, byte ptr [rdx+2]
0x1401a4d53  cmp     al, 28h ; '('
0x1401a4d55  jnz     loc_1401A4E3D
0x1401a4d5b  cmp     dword ptr [rdx+14h], 0
0x1401a4d5f  jnz     loc_1401A4F57
0x1401a4d65  mov     r12d, [rdx+38h]
0x1401a4d69  test    r12d, r12d
0x1401a4d6c  jz      loc_1401A4F57
0x1401a4d72  xor     r10b, r10b
0x1401a4d75  xor     r11d, r11d
0x1401a4d78  xor     bl, bl
0x1401a4d7a  xor     r9d, r9d
0x1401a4d7d  xor     r14d, r14d
0x1401a4d80  xor     r13b, r13b
0x1401a4d83  mov     ecx, [rdx+r14*4+78h]
0x1401a4d88  cmp     ecx, 80h
0x1401a4d8e  jb      short loc_1401A4E03
0x1401a4d90  mov     ebp, [rdx+10h]
0x1401a4d93  cmp     ecx, ebp
0x1401a4d95  jnb     short loc_1401A4E03
0x1401a4d97  mov     r8d, ecx
0x1401a4d9a  mov     ecx, [rcx+rdx]
0x1401a4d9d  sub     ecx, 40h ; '@'
0x1401a4da0  jz      short loc_1401A4DF5
0x1401a4da2  sub     ecx, esi
0x1401a4da4  jz      short loc_1401A4DC9
0x1401a4da6  cmp     ecx, esi
0x1401a4da8  jnz     short loc_1401A4DFE
0x1401a4daa  lea     rcx, [r8+28h]
0x1401a4dae  cmp     rcx, rbp
0x1401a4db1  ja      short loc_1401A4DFE
0x1401a4db3  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401a4db9  jbe     short loc_1401A4DC2
0x1401a4dbb  lea     r11, [rdx+20h]
0x1401a4dbf  add     r11, r8
0x1401a4dc2  mov     r9, [r8+rdx+18h]
0x1401a4dc7  jmp     short loc_1401A4E25
0x1401a4dc9  lea     rcx, [r8+38h]
0x1401a4dcd  cmp     rcx, rbp
0x1401a4dd0  ja      short loc_1401A4DFE
0x1401a4dd2  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a4dd8  mov     r13b, sil
0x1401a4ddb  jbe     short loc_1401A4DE4
0x1401a4ddd  lea     r11, [rdx+18h]
0x1401a4de1  add     r11, r8
0x1401a4de4  mov     bl, [r8+rdx+8]
0x1401a4de9  mov     r9, [r8+rdx+10h]
0x1401a4dee  mov     r10b, [r8+rdx+9]
0x1401a4df3  jmp     short loc_1401A4DFE
0x1401a4df5  lea     rcx, [r8+28h]
0x1401a4df9  cmp     rcx, rbp
0x1401a4dfc  jbe     short loc_1401A4E11
0x1401a4dfe  test    r13b, r13b
0x1401a4e01  jnz     short loc_1401A4E2F
0x1401a4e03  add     r14d, esi
0x1401a4e06  cmp     r14d, r12d
0x1401a4e09  jb      loc_1401A4D83
0x1401a4e0f  jmp     short loc_1401A4E2F
0x1401a4e11  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a4e17  jbe     short loc_1401A4E20
0x1401a4e19  lea     r11, [rdx+18h]
0x1401a4e1d  add     r11, r8
0x1401a4e20  mov     r9, [r8+rdx+10h]
0x1401a4e25  mov     r10b, [r8+rdx+9]
0x1401a4e2a  mov     bl, [r8+rdx+8]
0x1401a4e2f  test    r11, r11
0x1401a4e32  jz      loc_1401A4F57
0x1401a4e38  mov     cl, [r11]
0x1401a4e3b  jmp     short loc_1401A4E53
0x1401a4e3d  mov     cl, [rdx+48h]
0x1401a4e40  mov     r9, [rdx+20h]
0x1401a4e44  mov     r10b, [rdx+0Bh]
0x1401a4e48  mov     bl, [rdx+4]
0x1401a4e4b  test    eax, eax
0x1401a4e4d  jnz     loc_1401A4F57
0x1401a4e53  sub     cl, 8
0x1401a4e56  test    cl, 5Dh
0x1401a4e59  jnz     loc_1401A4F57
0x1401a4e5f  mov     bpl, [rdx+3]
0x1401a4e63  cmp     bpl, sil
0x1401a4e66  jz      loc_1401A4EF9
0x1401a4e6c  test    r9, r9
0x1401a4e6f  jz      loc_1401A4EF9
0x1401a4e75  test    r10b, r10b
0x1401a4e78  jz      short loc_1401A4EF9
0x1401a4e7a  mov     al, [r9]
0x1401a4e7d  xor     dl, dl
0x1401a4e7f  and     al, 7Fh
0x1401a4e81  movzx   ecx, r10b
0x1401a4e85  sub     al, 72h ; 'r'
0x1401a4e87  xor     r11b, r11b
0x1401a4e8a  xor     r8b, r8b
0x1401a4e8d  add     rcx, r9
0x1401a4e90  cmp     al, sil
0x1401a4e93  lea     rax, [r9+8]
0x1401a4e97  jbe     short loc_1401A4EDB
0x1401a4e99  cmp     rax, rcx
0x1401a4e9c  ja      short loc_1401A4EF1
0x1401a4e9e  movzx   ecx, byte ptr [r9+7]
0x1401a4ea3  lea     r8, [r9+0Dh]
0x1401a4ea7  mov     dl, [r9+2]
0x1401a4eab  add     ecx, 8
0x1401a4eae  and     dl, 0Fh
0x1401a4eb1  movzx   eax, r10b
0x1401a4eb5  cmp     ecx, eax
0x1401a4eb7  cmovbe  eax, ecx
0x1401a4eba  mov     ecx, eax
0x1401a4ebc  add     rcx, r9
0x1401a4ebf  cmp     r8, rcx
0x1401a4ec2  ja      short loc_1401A4EC8
0x1401a4ec4  mov     r11b, [r9+0Ch]
0x1401a4ec8  lea     rax, [r9+0Eh]
0x1401a4ecc  cmp     rax, rcx
0x1401a4ecf  ja      short loc_1401A4ED6
0x1401a4ed1  mov     r8b, [r8]
0x1401a4ed4  jmp     short loc_1401A4EF4
0x1401a4ed6  xor     r8b, r8b
0x1401a4ed9  jmp     short loc_1401A4EF4
0x1401a4edb  cmp     rax, rcx
0x1401a4ede  ja      short loc_1401A4EF1
0x1401a4ee0  mov     dl, [r9+1]
0x1401a4ee4  mov     r11b, [r9+2]
  ... truncated ...
```
