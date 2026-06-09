# NvmeAdapterFabricsDisconnectControllerIoctl

- ea: `0x1401a34ac`
- end: `0x1401a3a06`
- name: `NvmeAdapterFabricsDisconnectControllerIoctl`
- size: `1370`
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
- `0x1400f8094`
- `0x1400f8b90`
- `0x14014b400`
- `0x14014b800`
- `0x1401a34ac`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a35e7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a35e7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a3600`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a3600`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a3713`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a3713`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a363b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a363b`
- `ntoskrnl!IofCompleteRequest` at `0x1401a39cd`
- `ntoskrnl!IofCompleteRequest` at `0x1401a39cd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a35b6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a36af`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a35b6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a36af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a3647`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a3647`

## pseudocode

```c
__int64 __fastcall NvmeAdapterFabricsDisconnectControllerIoctl(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  char v5; // di
  __int64 v6; // rcx
  __int64 NvmeController; // rax
  __int64 v8; // r14
  unsigned int v9; // esi
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // r13
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  _OWORD *v15; // rax
  _OWORD *v16; // rdx
  __int128 v17; // xmm1
  __int64 v18; // r9
  bool v19; // zf
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  int *v22; // rax
  int v23; // ecx
  __int64 v24; // rdx
  unsigned int v25; // r13d
  _BYTE *v26; // r9
  unsigned __int8 v27; // r11
  char *v28; // r10
  char v29; // r12
  __int64 v30; // r15
  unsigned __int64 v31; // r14
  __int64 v32; // r8
  int v33; // ecx
  char v34; // cl
  char v35; // r14
  char v36; // r10
  char v37; // r8
  _BYTE *v38; // rax
  char *v39; // r8
  unsigned int v40; // eax
  char v42; // [rsp+60h] [rbp-A0h]
  __int128 v43; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v44[272]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v44, 0, 0x101u);
  v5 = 1;
  *(_QWORD *)(a2 + 56) = 0;
  *(_QWORD *)&v43 = 0;
  if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && *(_QWORD *)(a1 + 616) )
  {
    v6 = *(_QWORD *)(a2 + 24);
    if ( v6 && *(_DWORD *)(*(_QWORD *)(a2 + 184) + 16LL) >= 0x10u && *(_WORD *)v6 == 1 && *(_WORD *)(v6 + 2) >= 0x10u )
    {
      LOBYTE(v4) = 1;
      NvmeController = NvmeAdapterFindNvmeController(a1, *(_QWORD *)(v6 + 8) ^ a1, v4, &v43);
      v8 = NvmeController;
      if ( !NvmeController )
      {
        v9 = -1073741275;
        goto LABEL_24;
      }
      v10 = 2;
      if ( ((*(_DWORD *)(NvmeController + 568) - 2) & 0xFFFFFFFD) != 0 )
      {
        v9 = -1073741808;
LABEL_13:
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v43 + 40));
        goto LABEL_24;
      }
      v11 = *(_QWORD *)(NvmeController + 136);
      if ( (v11 & 8) != 0 )
      {
        v9 = -2147483631;
        goto LABEL_13;
      }
      v12 = v43;
      *(_DWORD *)(v8 + 568) = 3;
      if ( (v11 & 1) == 0 )
      {
        *(_QWORD *)(v8 + 136) = v11 | 8;
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite((PERESOURCE)(v12 + 632), 1u);
        v13 = *(_QWORD *)(v8 + 64);
        if ( *(_QWORD *)(v13 + 8) != v8 + 64 || (v14 = *(_QWORD **)(v8 + 72), *v14 != v8 + 64) )
          __fastfail(3u);
        *v14 = v13;
        *(_QWORD *)(v13 + 8) = v14;
        --*(_DWORD *)(v12 + 624);
        ExReleaseResourceLite((PERESOURCE)(v12 + 632));
        KeLeaveCriticalRegion();
      }
      v9 = 0;
      v15 = (_OWORD *)(v12 + 60);
      v16 = v44;
      do
      {
        *v16 = *v15;
        v16[1] = v15[1];
        v16[2] = v15[2];
        v16[3] = v15[3];
        v16[4] = v15[4];
        v16[5] = v15[5];
        v16[6] = v15[6];
        v17 = v15[7];
        v15 += 8;
        v16[7] = v17;
        v16 += 8;
        --v10;
      }
      while ( v10 );
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v12 + 40));
      LOBYTE(v18) = (*(_BYTE *)(v8 + 136) & 1) == 0;
      NvmeAdapterDisconnectFabricsControllerInternal(a1, v8, v44, v18);
    }
    else
    {
      v9 = -1073741811;
    }
  }
  else
  {
    v9 = -1073741637;
  }
LABEL_24:
  v19 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v9;
  if ( v19 )
    goto LABEL_87;
  v43 = 0;
  IoGetActivityIdIrp(a2, &v43);
  v21 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v21 == 14 )
  {
    if ( (byte_140177432 & 8) != 0 )
      McTemplateK0pd_EtwWriteTransfer(v20, EventNonReadWriteRequestComplete, &v43, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_87;
  }
  if ( *(_BYTE *)v21 != 15 )
  {
    if ( *(_BYTE *)v21 == 27 )
    {
      if ( *(_BYTE *)(v21 + 1) != 7 || *(_DWORD *)(v21 + 8) )
      {
        if ( (byte_140177432 & 0x20) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v20, EventPnpRequestComplete, &v43, a2, *(_DWORD *)(a2 + 48));
      }
      else if ( (byte_140177432 & 0x40) != 0 )
      {
        v22 = *(int **)(a2 + 56);
        if ( v22 )
          v23 = *v22;
        else
          v23 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v23, v21, (unsigned int)&v43, a2, v23, *(_DWORD *)(a2 + 48));
      }
    }
    goto LABEL_87;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_87;
  v24 = *(_QWORD *)(v21 + 8);
  if ( *(_BYTE *)(v24 + 2) != 40 )
  {
    v34 = *(_BYTE *)(v24 + 72);
    v26 = *(_BYTE **)(v24 + 32);
    v27 = *(_BYTE *)(v24 + 11);
    v29 = *(_BYTE *)(v24 + 4);
    if ( *(_BYTE *)(v24 + 2) )
      goto LABEL_87;
LABEL_66:
    LOBYTE(v20) = v34 - 8;
    if ( (v20 & 0x5D) != 0 )
      goto LABEL_87;
    v35 = *(_BYTE *)(v24 + 3);
    if ( v35 == 1 || !v26 || !v27 )
      goto LABEL_83;
    LOBYTE(v24) = 0;
    v36 = 0;
    v37 = 0;
    v20 = (unsigned __int64)&v26[v27];
    v38 = v26 + 8;
    if ( (unsigned __int8)((*v26 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v38 <= v20 )
      {
        v36 = v26[2];
        LOBYTE(v24) = v26[1] & 0xF;
        v37 = v26[3];
        goto LABEL_82;
      }
    }
    else if ( (unsigned __int64)v38 <= v20 )
    {
      v39 = v26 + 13;
      LOBYTE(v24) = v26[2] & 0xF;
      v40 = v27;
      if ( (unsigned int)(unsigned __int8)v26[7] + 8 <= v27 )
        v40 = (unsigned __int8)v26[7] + 8;
      v20 = (unsigned __int64)&v26[v40];
      if ( (unsigned __int64)v39 <= v20 )
        v36 = v26[12];
      if ( (unsigned __int64)(v26 + 14) > v20 )
        v37 = 0;
      else
        v37 = *v39;
LABEL_82:
      if ( v5 )
      {
LABEL_84:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v20,
          v24,
          (unsigned int)&v43,
          a2,
          *(_DWORD *)(a2 + 48),
          v35,
          v29,
          v24,
          v36,
          v37,
          a2);
        goto LABEL_87;
      }
LABEL_83:
      LOBYTE(v24) = 0;
      v36 = 0;
      v37 = 0;
      goto LABEL_84;
    }
    v5 = 0;
    goto LABEL_82;
  }
  if ( *(_DWORD *)(v24 + 20) )
    goto LABEL_87;
  v25 = *(_DWORD *)(v24 + 56);
  if ( !v25 )
    goto LABEL_87;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v42 = 0;
  v29 = 0;
  v30 = 0;
  while ( 1 )
  {
    v20 = *(unsigned int *)(v24 + 4 * v30 + 120);
    if ( (unsigned int)v20 >= 0x80 )
    {
      v31 = *(unsigned int *)(v24 + 16);
      if ( (unsigned int)v20 < (unsigned int)v31 )
        break;
    }
LABEL_57:
    v30 = (unsigned int)(v30 + 1);
    if ( (unsigned int)v30 >= v25 )
      goto LABEL_63;
  }
  v32 = (unsigned int)v20;
  v33 = *(_DWORD *)(v20 + v24) - 64;
  if ( v33 )
  {
    LODWORD(v20) = v33 - 1;
    if ( (_DWORD)v20 )
    {
      if ( (_DWORD)v20 == 1 )
      {
        LODWORD(v20) = v32 + 40;
        if ( v32 + 40 <= v31 )
        {
          if ( *(_DWORD *)(v32 + v24 + 12) )
            v28 = (char *)(v32 + v24 + 32);
          v26 = *(_BYTE **)(v32 + v24 + 24);
          goto LABEL_62;
        }
      }
    }
    else
    {
      LODWORD(v20) = v32 + 56;
      if ( v32 + 56 <= v31 )
      {
        v42 = 1;
        if ( *(_BYTE *)(v32 + v24 + 10) )
          v28 = (char *)(v32 + v24 + 24);
        v29 = *(_BYTE *)(v32 + v24 + 8);
        v26 = *(_BYTE **)(v32 + v24 + 16);
        v27 = *(_BYTE *)(v32 + v24 + 9);
      }
    }
    goto LABEL_56;
  }
  LODWORD(v20) = v32 + 40;
  if ( v32 + 40 > v31 )
  {
LABEL_56:
    if ( v42 )
      goto LABEL_63;
    goto LABEL_57;
  }
  if ( *(_BYTE *)(v32 + v24 + 10) )
    v28 = (char *)(v32 + v24 + 24);
  v26 = *(_BYTE **)(v32 + v24 + 16);
LABEL_62:
  v27 = *(_BYTE *)(v32 + v24 + 9);
  v29 = *(_BYTE *)(v32 + v24 + 8);
LABEL_63:
  if ( v28 )
  {
    v34 = *v28;
    goto LABEL_66;
  }
LABEL_87:
  IofCompleteRequest((PIRP)a2, 0);
  return v9;
}

```

## disassembly

```asm
0x1401a34ac  mov     [rsp-8+arg_10], rbx
0x1401a34b1  push    rbp
0x1401a34b2  push    rsi
0x1401a34b3  push    rdi
0x1401a34b4  push    r12
0x1401a34b6  push    r13
0x1401a34b8  push    r14
0x1401a34ba  push    r15
0x1401a34bc  lea     rbp, [rsp-0A0h]
0x1401a34c4  sub     rsp, 1A0h
0x1401a34cb  mov     rax, cs:__security_cookie
0x1401a34d2  xor     rax, rsp
0x1401a34d5  mov     [rbp+0D0h+var_40], rax
0x1401a34dc  mov     rbx, rdx
0x1401a34df  mov     r15, rcx
0x1401a34e2  xor     edx, edx; Val
0x1401a34e4  lea     rcx, [rbp+0D0h+var_150]; void *
0x1401a34e8  mov     r8d, 101h; Size
0x1401a34ee  call    memset_0
0x1401a34f3  mov     edi, 1
0x1401a34f8  mov     qword ptr [rbx+38h], 0
0x1401a3500  mov     qword ptr [rsp+1D0h+var_168], 0
0x1401a3509  test    [r15+98h], dil
0x1401a3510  jz      loc_1401A36E7
0x1401a3516  cmp     qword ptr [r15+268h], 0
0x1401a351e  jz      loc_1401A36E7
0x1401a3524  mov     rcx, [rbx+18h]
0x1401a3528  test    rcx, rcx
0x1401a352b  jz      loc_1401A36E0
0x1401a3531  mov     rax, [rbx+0B8h]
0x1401a3538  lea     edx, [rdi+0Fh]
0x1401a353b  cmp     [rax+10h], edx
0x1401a353e  jb      loc_1401A36E0
0x1401a3544  cmp     [rcx], di
0x1401a3547  jnz     loc_1401A36E0
0x1401a354d  cmp     [rcx+2], dx
0x1401a3551  jb      loc_1401A36E0
0x1401a3557  mov     rdx, r15
0x1401a355a  lea     r9, [rsp+1D0h+var_168]
0x1401a355f  xor     rdx, [rcx+8]
0x1401a3563  mov     r8b, dil
0x1401a3566  mov     rcx, r15
0x1401a3569  call    NvmeAdapterFindNvmeController
0x1401a356e  mov     r14, rax
0x1401a3571  test    rax, rax
0x1401a3574  jnz     short loc_1401A3580
0x1401a3576  mov     esi, 0C0000225h
0x1401a357b  jmp     loc_1401A36EC
0x1401a3580  mov     eax, [rax+238h]
0x1401a3586  mov     r12d, 2
0x1401a358c  sub     eax, r12d
0x1401a358f  test    eax, 0FFFFFFFDh
0x1401a3594  jz      short loc_1401A359D
0x1401a3596  mov     esi, 0C0000010h
0x1401a359b  jmp     short loc_1401A35AD
0x1401a359d  mov     rax, [r14+88h]
0x1401a35a4  test    al, 8
0x1401a35a6  jz      short loc_1401A35C7
0x1401a35a8  mov     esi, 80000011h
0x1401a35ad  mov     rcx, qword ptr [rsp+1D0h+var_168]
0x1401a35b2  mov     rcx, [rcx+28h]; RunRefCacheAware
0x1401a35b6  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a35bd  nop     dword ptr [rax+rax+00h]
0x1401a35c2  jmp     loc_1401A36EC
0x1401a35c7  mov     r13, qword ptr [rsp+1D0h+var_168]
0x1401a35cc  mov     dword ptr [r14+238h], 3
0x1401a35d7  test    dil, al
0x1401a35da  jnz     short loc_1401A3653
0x1401a35dc  or      rax, 8
0x1401a35e0  mov     [r14+88h], rax
0x1401a35e7  call    cs:__imp_KeEnterCriticalRegion
0x1401a35ee  nop     dword ptr [rax+rax+00h]
0x1401a35f3  lea     rsi, [r13+278h]
0x1401a35fa  mov     dl, dil; Wait
0x1401a35fd  mov     rcx, rsi; Resource
0x1401a3600  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401a3607  nop     dword ptr [rax+rax+00h]
0x1401a360c  lea     rax, [r14+40h]
0x1401a3610  mov     rdx, [rax]
0x1401a3613  cmp     [rdx+8], rax
0x1401a3617  jnz     loc_1401A36D9
0x1401a361d  mov     rcx, [rax+8]
0x1401a3621  cmp     [rcx], rax
0x1401a3624  jnz     loc_1401A36D9
0x1401a362a  mov     [rcx], rdx
0x1401a362d  mov     [rdx+8], rcx
0x1401a3631  mov     rcx, rsi; Resource
0x1401a3634  dec     dword ptr [r13+270h]
0x1401a363b  call    cs:__imp_ExReleaseResourceLite
0x1401a3642  nop     dword ptr [rax+rax+00h]
0x1401a3647  call    cs:__imp_KeLeaveCriticalRegion
0x1401a364e  nop     dword ptr [rax+rax+00h]
0x1401a3653  xor     esi, esi
0x1401a3655  lea     rax, [r13+3Ch]
0x1401a3659  lea     rdx, [rbp+0D0h+var_150]
0x1401a365d  mov     ecx, 80h
0x1401a3662  movups  xmm0, xmmword ptr [rax]
0x1401a3665  movups  xmmword ptr [rdx], xmm0
0x1401a3668  movups  xmm1, xmmword ptr [rax+10h]
0x1401a366c  movups  xmmword ptr [rdx+10h], xmm1
0x1401a3670  movups  xmm0, xmmword ptr [rax+20h]
0x1401a3674  movups  xmmword ptr [rdx+20h], xmm0
0x1401a3678  movups  xmm1, xmmword ptr [rax+30h]
0x1401a367c  movups  xmmword ptr [rdx+30h], xmm1
0x1401a3680  movups  xmm0, xmmword ptr [rax+40h]
0x1401a3684  movups  xmmword ptr [rdx+40h], xmm0
0x1401a3688  movups  xmm1, xmmword ptr [rax+50h]
0x1401a368c  movups  xmmword ptr [rdx+50h], xmm1
0x1401a3690  movups  xmm0, xmmword ptr [rax+60h]
0x1401a3694  movups  xmmword ptr [rdx+60h], xmm0
0x1401a3698  movups  xmm1, xmmword ptr [rax+70h]
0x1401a369c  add     rax, rcx
0x1401a369f  movups  xmmword ptr [rdx+70h], xmm1
0x1401a36a3  add     rdx, rcx
0x1401a36a6  sub     r12, rdi
0x1401a36a9  jnz     short loc_1401A3662
0x1401a36ab  mov     rcx, [r13+28h]; RunRefCacheAware
0x1401a36af  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a36b6  nop     dword ptr [rax+rax+00h]
0x1401a36bb  mov     r9b, [r14+88h]
0x1401a36c2  lea     r8, [rbp+0D0h+var_150]
0x1401a36c6  not     r9b
0x1401a36c9  mov     rdx, r14
0x1401a36cc  and     r9b, dil
0x1401a36cf  mov     rcx, r15
0x1401a36d2  call    NvmeAdapterDisconnectFabricsControllerInternal
0x1401a36d7  jmp     short loc_1401A36EC
0x1401a36d9  mov     ecx, 3
0x1401a36de  int     29h; Win8: RtlFailFast(ecx)
0x1401a36e0  mov     esi, 0C000000Dh
0x1401a36e5  jmp     short loc_1401A36EC
0x1401a36e7  mov     esi, 0C00000BBh
0x1401a36ec  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a36f3  mov     byte ptr [rbx+8Dh], 0ACh
0x1401a36fa  mov     [rbx+30h], esi
0x1401a36fd  jz      loc_1401A39C8
0x1401a3703  xorps   xmm0, xmm0
0x1401a3706  lea     rdx, [rsp+1D0h+var_168]
0x1401a370b  mov     rcx, rbx
0x1401a370e  movups  [rsp+1D0h+var_168], xmm0
0x1401a3713  call    cs:__imp_IoGetActivityIdIrp
0x1401a371a  nop     dword ptr [rax+rax+00h]
0x1401a371f  mov     rdx, [rbx+0B8h]
0x1401a3726  movzx   eax, byte ptr [rdx]
0x1401a3729  sub     eax, 0Eh
0x1401a372c  jz      loc_1401A39A4
0x1401a3732  sub     eax, edi
0x1401a3734  jz      short loc_1401A37A4
0x1401a3736  cmp     eax, 0Ch
0x1401a3739  jnz     loc_1401A39C8
0x1401a373f  cmp     byte ptr [rdx+1], 7
0x1401a3743  jnz     short loc_1401A3784
0x1401a3745  cmp     dword ptr [rdx+8], 0
0x1401a3749  jnz     short loc_1401A3784
0x1401a374b  test    cs:byte_140177432, 40h
0x1401a3752  jz      loc_1401A39C8
0x1401a3758  mov     rax, [rbx+38h]
0x1401a375c  test    rax, rax
0x1401a375f  jz      short loc_1401A3765
0x1401a3761  mov     ecx, [rax]
0x1401a3763  jmp     short loc_1401A3767
0x1401a3765  xor     ecx, ecx
0x1401a3767  mov     eax, [rbx+30h]
0x1401a376a  lea     r8, [rsp+1D0h+var_168]
0x1401a376f  mov     [rsp+1D0h+var_1A8], eax
0x1401a3773  mov     r9, rbx
0x1401a3776  mov     [rsp+1D0h+var_1B0], ecx
0x1401a377a  call    McTemplateK0pqd_EtwWriteTransfer
0x1401a377f  jmp     loc_1401A39C8
0x1401a3784  test    cs:byte_140177432, 20h
0x1401a378b  jz      loc_1401A39C8
0x1401a3791  mov     eax, [rbx+30h]
0x1401a3794  lea     rdx, EventPnpRequestComplete
0x1401a379b  mov     [rsp+1D0h+var_1B0], eax
0x1401a379f  jmp     loc_1401A39BB
0x1401a37a4  cmp     cs:byte_140177431, 0
0x1401a37ab  jge     loc_1401A39C8
0x1401a37b1  mov     rdx, [rdx+8]
0x1401a37b5  movzx   eax, byte ptr [rdx+2]
0x1401a37b9  cmp     al, 28h ; '('
0x1401a37bb  jnz     loc_1401A38AC
0x1401a37c1  cmp     dword ptr [rdx+14h], 0
0x1401a37c5  jnz     loc_1401A39C8
0x1401a37cb  mov     r13d, [rdx+38h]
0x1401a37cf  test    r13d, r13d
0x1401a37d2  jz      loc_1401A39C8
0x1401a37d8  xor     r9d, r9d
0x1401a37db  xor     r11b, r11b
0x1401a37de  xor     r10d, r10d
0x1401a37e1  mov     [rsp+1D0h+var_170], r9b
0x1401a37e6  xor     r12b, r12b
0x1401a37e9  xor     r15d, r15d
0x1401a37ec  mov     ecx, [rdx+r15*4+78h]
0x1401a37f1  cmp     ecx, 80h
0x1401a37f7  jb      short loc_1401A3872
0x1401a37f9  mov     r14d, [rdx+10h]
0x1401a37fd  cmp     ecx, r14d
0x1401a3800  jnb     short loc_1401A3872
0x1401a3802  mov     r8d, ecx
0x1401a3805  mov     ecx, [rcx+rdx]
0x1401a3808  sub     ecx, 40h ; '@'
0x1401a380b  jz      short loc_1401A3862
0x1401a380d  sub     ecx, edi
0x1401a380f  jz      short loc_1401A3834
0x1401a3811  cmp     ecx, edi
0x1401a3813  jnz     short loc_1401A386B
0x1401a3815  lea     rcx, [r8+28h]
0x1401a3819  cmp     rcx, r14
0x1401a381c  ja      short loc_1401A386B
0x1401a381e  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401a3824  jbe     short loc_1401A382D
0x1401a3826  lea     r10, [rdx+20h]
0x1401a382a  add     r10, r8
0x1401a382d  mov     r9, [r8+rdx+18h]
0x1401a3832  jmp     short loc_1401A3894
0x1401a3834  lea     rcx, [r8+38h]
0x1401a3838  cmp     rcx, r14
0x1401a383b  ja      short loc_1401A386B
0x1401a383d  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a3843  mov     [rsp+1D0h+var_170], dil
0x1401a3848  jbe     short loc_1401A3851
0x1401a384a  lea     r10, [rdx+18h]
0x1401a384e  add     r10, r8
0x1401a3851  mov     r12b, [r8+rdx+8]
0x1401a3856  mov     r9, [r8+rdx+10h]
0x1401a385b  mov     r11b, [r8+rdx+9]
0x1401a3860  jmp     short loc_1401A386B
0x1401a3862  lea     rcx, [r8+28h]
0x1401a3866  cmp     rcx, r14
0x1401a3869  jbe     short loc_1401A3880
0x1401a386b  cmp     [rsp+1D0h+var_170], 0
0x1401a3870  jnz     short loc_1401A389E
0x1401a3872  add     r15d, edi
0x1401a3875  cmp     r15d, r13d
0x1401a3878  jb      loc_1401A37EC
0x1401a387e  jmp     short loc_1401A389E
0x1401a3880  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a3886  jbe     short loc_1401A388F
0x1401a3888  lea     r10, [rdx+18h]
0x1401a388c  add     r10, r8
0x1401a388f  mov     r9, [r8+rdx+10h]
0x1401a3894  mov     r11b, [r8+rdx+9]
0x1401a3899  mov     r12b, [r8+rdx+8]
0x1401a389e  test    r10, r10
0x1401a38a1  jz      loc_1401A39C8
0x1401a38a7  mov     cl, [r10]
0x1401a38aa  jmp     short loc_1401A38C3
0x1401a38ac  mov     cl, [rdx+48h]
0x1401a38af  mov     r9, [rdx+20h]
0x1401a38b3  mov     r11b, [rdx+0Bh]
0x1401a38b7  mov     r12b, [rdx+4]
0x1401a38bb  test    eax, eax
0x1401a38bd  jnz     loc_1401A39C8
0x1401a38c3  sub     cl, 8
0x1401a38c6  test    cl, 5Dh
0x1401a38c9  jnz     loc_1401A39C8
0x1401a38cf  mov     r14b, [rdx+3]
0x1401a38d3  cmp     r14b, dil
0x1401a38d6  jz      loc_1401A3969
0x1401a38dc  test    r9, r9
0x1401a38df  jz      loc_1401A3969
0x1401a38e5  test    r11b, r11b
0x1401a38e8  jz      short loc_1401A3969
0x1401a38ea  mov     al, [r9]
0x1401a38ed  xor     dl, dl
0x1401a38ef  and     al, 7Fh
0x1401a38f1  movzx   ecx, r11b
0x1401a38f5  sub     al, 72h ; 'r'
0x1401a38f7  xor     r10b, r10b
0x1401a38fa  xor     r8b, r8b
0x1401a38fd  add     rcx, r9
0x1401a3900  cmp     al, dil
0x1401a3903  lea     rax, [r9+8]
0x1401a3907  jbe     short loc_1401A394B
0x1401a3909  cmp     rax, rcx
0x1401a390c  ja      short loc_1401A3961
0x1401a390e  movzx   ecx, byte ptr [r9+7]
0x1401a3913  lea     r8, [r9+0Dh]
0x1401a3917  mov     dl, [r9+2]
0x1401a391b  add     ecx, 8
0x1401a391e  and     dl, 0Fh
0x1401a3921  movzx   eax, r11b
0x1401a3925  cmp     ecx, eax
0x1401a3927  cmovbe  eax, ecx
0x1401a392a  mov     ecx, eax
0x1401a392c  add     rcx, r9
0x1401a392f  cmp     r8, rcx
0x1401a3932  ja      short loc_1401A3938
0x1401a3934  mov     r10b, [r9+0Ch]
0x1401a3938  lea     rax, [r9+0Eh]
0x1401a393c  cmp     rax, rcx
0x1401a393f  ja      short loc_1401A3946
0x1401a3941  mov     r8b, [r8]
0x1401a3944  jmp     short loc_1401A3964
0x1401a3946  xor     r8b, r8b
0x1401a3949  jmp     short loc_1401A3964
0x1401a394b  cmp     rax, rcx
0x1401a394e  ja      short loc_1401A3961
0x1401a3950  mov     dl, [r9+1]
0x1401a3954  mov     r10b, [r9+2]
  ... truncated ...
```
