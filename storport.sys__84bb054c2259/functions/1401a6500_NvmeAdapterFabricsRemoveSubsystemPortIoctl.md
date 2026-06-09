# NvmeAdapterFabricsRemoveSubsystemPortIoctl

- ea: `0x1401a6500`
- end: `0x1401a6a21`
- name: `NvmeAdapterFabricsRemoveSubsystemPortIoctl`
- size: `1313`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x140078b48`
- `0x1400848c4`
- `0x1400f3fa0`
- `0x1400f8d6c`
- `0x14014b400`
- `0x1401a6500`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a65f4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a65f4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a6611`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a6611`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a6738`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a6738`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a664f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a664f`
- `ntoskrnl!IofCompleteRequest` at `0x1401a69ea`
- `ntoskrnl!IofCompleteRequest` at `0x1401a69ea`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a65c8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a65dc`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a666b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a667b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a65c8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a65dc`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a666b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a667b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a665b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a665b`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401a66e8`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401a66e8`

## pseudocode

```c
__int64 __fastcall NvmeAdapterFabricsRemoveSubsystemPortIoctl(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  char v6; // si
  __int64 SubsystemPort; // rax
  __int64 v8; // rdi
  unsigned int v9; // r14d
  __int64 v10; // rax
  __int64 v11; // r13
  struct _ERESOURCE *v12; // r12
  __int64 v13; // r8
  _QWORD *v14; // rdx
  __int64 v15; // rdx
  bool v16; // zf
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  int *v19; // rax
  int v20; // ecx
  __int64 v21; // rdx
  unsigned int v22; // r12d
  _BYTE *v23; // r9
  unsigned __int8 v24; // r10
  char *v25; // r11
  char v26; // r13
  __int64 v27; // r15
  unsigned __int64 v28; // rdi
  __int64 v29; // r8
  int v30; // ecx
  char v31; // cl
  char v32; // di
  char v33; // r11
  char v34; // r8
  _BYTE *v35; // rax
  char *v36; // r8
  unsigned int v37; // eax
  char v39; // [rsp+60h] [rbp-9h]
  __int64 v40; // [rsp+68h] [rbp-1h] BYREF
  __int128 v41; // [rsp+70h] [rbp+7h] BYREF

  v40 = 0;
  v4 = *(_QWORD *)(a2 + 24);
  *(_QWORD *)(a2 + 56) = 0;
  v6 = 1;
  if ( v4 && *(_DWORD *)(*(_QWORD *)(a2 + 184) + 16LL) >= 0x10u && *(_WORD *)v4 == 1 && *(_WORD *)(v4 + 2) >= 0x10u )
  {
    LOBYTE(a3) = 1;
    SubsystemPort = NvmeAdapterFindSubsystemPort(a1, *(_QWORD *)(v4 + 8) ^ a1, a3, &v40);
    *(_QWORD *)&v41 = SubsystemPort;
    v8 = SubsystemPort;
    if ( !SubsystemPort )
    {
      v9 = -1073741275;
      goto LABEL_19;
    }
    v10 = *(_QWORD *)(SubsystemPort + 32);
    if ( (v10 & 1) == 0 )
    {
      v9 = -1073741637;
LABEL_11:
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v8 + 40));
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v40 + 56));
      goto LABEL_19;
    }
    if ( (v10 & 0x10) != 0 )
    {
      v9 = -2147483631;
      goto LABEL_11;
    }
    *(_QWORD *)(v8 + 32) = v10 | 0x10;
    KeEnterCriticalRegion();
    v11 = v40;
    v12 = (struct _ERESOURCE *)(v40 + 384);
    ExAcquireResourceExclusiveLite((PERESOURCE)(v40 + 384), 1u);
    v13 = *(_QWORD *)(v8 + 8);
    if ( *(_QWORD *)(v13 + 8) != v8 + 8 || (v14 = *(_QWORD **)(v8 + 16), *v14 != v8 + 8) )
      __fastfail(3u);
    *v14 = v13;
    *(_QWORD *)(v13 + 8) = v14;
    v9 = 0;
    --*(_DWORD *)(v11 + 376);
    ExReleaseResourceLite(v12);
    KeLeaveCriticalRegion();
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v8 + 40));
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v11 + 56));
    if ( (byte_14017743A & 4) != 0 )
      McTemplateK0qjzshsss_EtwWriteTransfer(
        v8 + 316,
        v8 + 60,
        v11 + 72,
        *(_DWORD *)(a1 + 56),
        a1 + 1048,
        *(_QWORD *)(a1 + 1032),
        v11 + 72,
        *(_WORD *)(v8 + 4),
        v8 + 60,
        v8 + 316,
        v8 + 572);
    ExWaitForRundownProtectionReleaseCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v8 + 40));
    LOBYTE(v15) = 1;
    NvmeAdapterCleanupSubsystemPort(a1, v15, &v41);
  }
  else
  {
    v9 = -1073741811;
  }
LABEL_19:
  v16 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v9;
  if ( v16 )
    goto LABEL_82;
  v41 = 0;
  IoGetActivityIdIrp(a2, &v41);
  v18 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v18 == 14 )
  {
    if ( (byte_140177432 & 8) != 0 )
      McTemplateK0pd_EtwWriteTransfer(v17, EventNonReadWriteRequestComplete, &v41, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_82;
  }
  if ( *(_BYTE *)v18 != 15 )
  {
    if ( *(_BYTE *)v18 == 27 )
    {
      if ( *(_BYTE *)(v18 + 1) != 7 || *(_DWORD *)(v18 + 8) )
      {
        if ( (byte_140177432 & 0x20) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v17, EventPnpRequestComplete, &v41, a2, *(_DWORD *)(a2 + 48));
      }
      else if ( (byte_140177432 & 0x40) != 0 )
      {
        v19 = *(int **)(a2 + 56);
        if ( v19 )
          v20 = *v19;
        else
          v20 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v20, v18, (unsigned int)&v41, a2, v20, *(_DWORD *)(a2 + 48));
      }
    }
    goto LABEL_82;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_82;
  v21 = *(_QWORD *)(v18 + 8);
  if ( *(_BYTE *)(v21 + 2) != 40 )
  {
    v31 = *(_BYTE *)(v21 + 72);
    v23 = *(_BYTE **)(v21 + 32);
    v24 = *(_BYTE *)(v21 + 11);
    v26 = *(_BYTE *)(v21 + 4);
    if ( *(_BYTE *)(v21 + 2) )
      goto LABEL_82;
LABEL_61:
    LOBYTE(v17) = v31 - 8;
    if ( (v17 & 0x5D) != 0 )
      goto LABEL_82;
    v32 = *(_BYTE *)(v21 + 3);
    if ( v32 == 1 || !v23 || !v24 )
      goto LABEL_78;
    LOBYTE(v21) = 0;
    v33 = 0;
    v34 = 0;
    v17 = (unsigned __int64)&v23[v24];
    v35 = v23 + 8;
    if ( (unsigned __int8)((*v23 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v35 <= v17 )
      {
        v33 = v23[2];
        LOBYTE(v21) = v23[1] & 0xF;
        v34 = v23[3];
        goto LABEL_77;
      }
    }
    else if ( (unsigned __int64)v35 <= v17 )
    {
      v36 = v23 + 13;
      LOBYTE(v21) = v23[2] & 0xF;
      v37 = v24;
      if ( (unsigned int)(unsigned __int8)v23[7] + 8 <= v24 )
        v37 = (unsigned __int8)v23[7] + 8;
      v17 = (unsigned __int64)&v23[v37];
      if ( (unsigned __int64)v36 <= v17 )
        v33 = v23[12];
      if ( (unsigned __int64)(v23 + 14) > v17 )
        v34 = 0;
      else
        v34 = *v36;
LABEL_77:
      if ( v6 )
      {
LABEL_79:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v17,
          v21,
          (unsigned int)&v41,
          a2,
          *(_DWORD *)(a2 + 48),
          v32,
          v26,
          v21,
          v33,
          v34,
          a2);
        goto LABEL_82;
      }
LABEL_78:
      LOBYTE(v21) = 0;
      v33 = 0;
      v34 = 0;
      goto LABEL_79;
    }
    v6 = 0;
    goto LABEL_77;
  }
  if ( *(_DWORD *)(v21 + 20) )
    goto LABEL_82;
  v22 = *(_DWORD *)(v21 + 56);
  if ( !v22 )
    goto LABEL_82;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v39 = 0;
  v26 = 0;
  v27 = 0;
  while ( 1 )
  {
    v17 = *(unsigned int *)(v21 + 4 * v27 + 120);
    if ( (unsigned int)v17 >= 0x80 )
    {
      v28 = *(unsigned int *)(v21 + 16);
      if ( (unsigned int)v17 < (unsigned int)v28 )
        break;
    }
LABEL_52:
    v27 = (unsigned int)(v27 + 1);
    if ( (unsigned int)v27 >= v22 )
      goto LABEL_58;
  }
  v29 = (unsigned int)v17;
  v30 = *(_DWORD *)(v17 + v21) - 64;
  if ( v30 )
  {
    LODWORD(v17) = v30 - 1;
    if ( (_DWORD)v17 )
    {
      if ( (_DWORD)v17 == 1 )
      {
        LODWORD(v17) = v29 + 40;
        if ( v29 + 40 <= v28 )
        {
          if ( *(_DWORD *)(v29 + v21 + 12) )
            v25 = (char *)(v29 + v21 + 32);
          v23 = *(_BYTE **)(v29 + v21 + 24);
          goto LABEL_57;
        }
      }
    }
    else
    {
      LODWORD(v17) = v29 + 56;
      if ( v29 + 56 <= v28 )
      {
        v39 = 1;
        if ( *(_BYTE *)(v29 + v21 + 10) )
          v25 = (char *)(v29 + v21 + 24);
        v26 = *(_BYTE *)(v29 + v21 + 8);
        v23 = *(_BYTE **)(v29 + v21 + 16);
        v24 = *(_BYTE *)(v29 + v21 + 9);
      }
    }
    goto LABEL_51;
  }
  LODWORD(v17) = v29 + 40;
  if ( v29 + 40 > v28 )
  {
LABEL_51:
    if ( v39 )
      goto LABEL_58;
    goto LABEL_52;
  }
  if ( *(_BYTE *)(v29 + v21 + 10) )
    v25 = (char *)(v29 + v21 + 24);
  v23 = *(_BYTE **)(v29 + v21 + 16);
LABEL_57:
  v24 = *(_BYTE *)(v29 + v21 + 9);
  v26 = *(_BYTE *)(v29 + v21 + 8);
LABEL_58:
  if ( v25 )
  {
    v31 = *v25;
    goto LABEL_61;
  }
LABEL_82:
  IofCompleteRequest((PIRP)a2, 0);
  return v9;
}

```

## disassembly

```asm
0x1401a6500  mov     [rsp-8+arg_10], rbx
0x1401a6505  push    rbp
0x1401a6506  push    rsi
0x1401a6507  push    rdi
0x1401a6508  push    r12
0x1401a650a  push    r13
0x1401a650c  push    r14
0x1401a650e  push    r15
0x1401a6510  lea     rbp, [rsp-27h]
0x1401a6515  sub     rsp, 90h
0x1401a651c  mov     rax, cs:__security_cookie
0x1401a6523  xor     rax, rsp
0x1401a6526  mov     [rbp+57h+var_40], rax
0x1401a652a  mov     r15, rcx
0x1401a652d  mov     [rbp+57h+var_58], 0
0x1401a6535  mov     rcx, [rdx+18h]
0x1401a6539  mov     rbx, rdx
0x1401a653c  mov     qword ptr [rdx+38h], 0
0x1401a6544  mov     esi, 1
0x1401a6549  test    rcx, rcx
0x1401a654c  jz      loc_1401A670C
0x1401a6552  mov     rax, [rdx+0B8h]
0x1401a6559  lea     r14d, [rsi+0Fh]
0x1401a655d  cmp     [rax+10h], r14d
0x1401a6561  jb      loc_1401A670C
0x1401a6567  cmp     [rcx], si
0x1401a656a  jnz     loc_1401A670C
0x1401a6570  cmp     [rcx+2], r14w
0x1401a6575  jb      loc_1401A670C
0x1401a657b  mov     rdx, r15
0x1401a657e  lea     r9, [rbp+57h+var_58]
0x1401a6582  xor     rdx, [rcx+8]
0x1401a6586  mov     r8b, sil
0x1401a6589  mov     rcx, r15
0x1401a658c  call    NvmeAdapterFindSubsystemPort
0x1401a6591  mov     qword ptr [rbp+57h+var_50], rax
0x1401a6595  mov     rdi, rax
0x1401a6598  test    rax, rax
0x1401a659b  jnz     short loc_1401A65A8
0x1401a659d  mov     r14d, 0C0000225h
0x1401a65a3  jmp     loc_1401A6712
0x1401a65a8  mov     rax, [rax+20h]
0x1401a65ac  test    sil, al
0x1401a65af  jnz     short loc_1401A65B9
0x1401a65b1  mov     r14d, 0C00000BBh
0x1401a65b7  jmp     short loc_1401A65C4
0x1401a65b9  test    r14b, al
0x1401a65bc  jz      short loc_1401A65ED
0x1401a65be  mov     r14d, 80000011h
0x1401a65c4  mov     rcx, [rdi+28h]; RunRefCacheAware
0x1401a65c8  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a65cf  nop     dword ptr [rax+rax+00h]
0x1401a65d4  mov     rcx, [rbp+57h+var_58]
0x1401a65d8  mov     rcx, [rcx+38h]; RunRefCacheAware
0x1401a65dc  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a65e3  nop     dword ptr [rax+rax+00h]
0x1401a65e8  jmp     loc_1401A6712
0x1401a65ed  or      rax, r14
0x1401a65f0  mov     [rdi+20h], rax
0x1401a65f4  call    cs:__imp_KeEnterCriticalRegion
0x1401a65fb  nop     dword ptr [rax+rax+00h]
0x1401a6600  mov     r13, [rbp+57h+var_58]
0x1401a6604  mov     dl, sil; Wait
0x1401a6607  lea     r12, [r13+180h]
0x1401a660e  mov     rcx, r12; Resource
0x1401a6611  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401a6618  nop     dword ptr [rax+rax+00h]
0x1401a661d  lea     rax, [rdi+8]
0x1401a6621  mov     r8, [rax]
0x1401a6624  cmp     [r8+8], rax
0x1401a6628  jnz     loc_1401A6705
0x1401a662e  mov     rdx, [rax+8]
0x1401a6632  cmp     [rdx], rax
0x1401a6635  jnz     loc_1401A6705
0x1401a663b  mov     [rdx], r8
0x1401a663e  mov     rcx, r12; Resource
0x1401a6641  mov     [r8+8], rdx
0x1401a6645  xor     r14d, r14d
0x1401a6648  dec     dword ptr [r13+178h]
0x1401a664f  call    cs:__imp_ExReleaseResourceLite
0x1401a6656  nop     dword ptr [rax+rax+00h]
0x1401a665b  call    cs:__imp_KeLeaveCriticalRegion
0x1401a6662  nop     dword ptr [rax+rax+00h]
0x1401a6667  mov     rcx, [rdi+28h]; RunRefCacheAware
0x1401a666b  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a6672  nop     dword ptr [rax+rax+00h]
0x1401a6677  mov     rcx, [r13+38h]; RunRefCacheAware
0x1401a667b  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a6682  nop     dword ptr [rax+rax+00h]
0x1401a6687  test    cs:byte_14017743A, 4
0x1401a668e  jz      short loc_1401A66E4
0x1401a6690  lea     rax, [rdi+23Ch]
0x1401a6697  mov     [rsp+0C0h+var_70], rax
0x1401a669c  lea     r9, [r15+418h]
0x1401a66a3  movzx   eax, word ptr [rdi+4]
0x1401a66a7  lea     rcx, [rdi+13Ch]
0x1401a66ae  mov     [rsp+0C0h+var_78], rcx
0x1401a66b3  lea     rdx, [rdi+3Ch]
0x1401a66b7  mov     [rsp+0C0h+var_80], rdx
0x1401a66bc  lea     r8, [r13+48h]
0x1401a66c0  mov     [rsp+0C0h+var_88], ax
0x1401a66c5  mov     rax, [r15+408h]
0x1401a66cc  mov     [rsp+0C0h+var_90], r8
0x1401a66d1  mov     [rsp+0C0h+var_98], rax
0x1401a66d6  mov     [rsp+0C0h+var_A0], r9
0x1401a66db  mov     r9d, [r15+38h]
0x1401a66df  call    McTemplateK0qjzshsss_EtwWriteTransfer
0x1401a66e4  mov     rcx, [rdi+28h]; RunRef
0x1401a66e8  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1401a66ef  nop     dword ptr [rax+rax+00h]
0x1401a66f4  lea     r8, [rbp+57h+var_50]
0x1401a66f8  mov     dl, sil
0x1401a66fb  mov     rcx, r15
0x1401a66fe  call    NvmeAdapterCleanupSubsystemPort
0x1401a6703  jmp     short loc_1401A6712
0x1401a6705  mov     ecx, 3
0x1401a670a  int     29h; Win8: RtlFailFast(ecx)
0x1401a670c  mov     r14d, 0C000000Dh
0x1401a6712  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a6719  mov     byte ptr [rbx+8Dh], 0ACh
0x1401a6720  mov     [rbx+30h], r14d
0x1401a6724  jz      loc_1401A69E5
0x1401a672a  xorps   xmm0, xmm0
0x1401a672d  lea     rdx, [rbp+57h+var_50]
0x1401a6731  mov     rcx, rbx
0x1401a6734  movups  [rbp+57h+var_50], xmm0
0x1401a6738  call    cs:__imp_IoGetActivityIdIrp
0x1401a673f  nop     dword ptr [rax+rax+00h]
0x1401a6744  mov     rdx, [rbx+0B8h]
0x1401a674b  movzx   eax, byte ptr [rdx]
0x1401a674e  sub     eax, 0Eh
0x1401a6751  jz      loc_1401A69C2
0x1401a6757  sub     eax, esi
0x1401a6759  jz      short loc_1401A67C8
0x1401a675b  cmp     eax, 0Ch
0x1401a675e  jnz     loc_1401A69E5
0x1401a6764  cmp     byte ptr [rdx+1], 7
0x1401a6768  jnz     short loc_1401A67A8
0x1401a676a  cmp     dword ptr [rdx+8], 0
0x1401a676e  jnz     short loc_1401A67A8
0x1401a6770  test    cs:byte_140177432, 40h
0x1401a6777  jz      loc_1401A69E5
0x1401a677d  mov     rax, [rbx+38h]
0x1401a6781  test    rax, rax
0x1401a6784  jz      short loc_1401A678A
0x1401a6786  mov     ecx, [rax]
0x1401a6788  jmp     short loc_1401A678C
0x1401a678a  xor     ecx, ecx
0x1401a678c  mov     eax, [rbx+30h]
0x1401a678f  lea     r8, [rbp+57h+var_50]
0x1401a6793  mov     dword ptr [rsp+0C0h+var_98], eax
0x1401a6797  mov     r9, rbx
0x1401a679a  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x1401a679e  call    McTemplateK0pqd_EtwWriteTransfer
0x1401a67a3  jmp     loc_1401A69E5
0x1401a67a8  test    cs:byte_140177432, 20h
0x1401a67af  jz      loc_1401A69E5
0x1401a67b5  mov     eax, [rbx+30h]
0x1401a67b8  lea     rdx, EventPnpRequestComplete
0x1401a67bf  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1401a67c3  jmp     loc_1401A69D9
0x1401a67c8  cmp     cs:byte_140177431, 0
0x1401a67cf  jge     loc_1401A69E5
0x1401a67d5  mov     rdx, [rdx+8]
0x1401a67d9  movzx   eax, byte ptr [rdx+2]
0x1401a67dd  cmp     al, 28h ; '('
0x1401a67df  jnz     loc_1401A68CB
0x1401a67e5  cmp     dword ptr [rdx+14h], 0
0x1401a67e9  jnz     loc_1401A69E5
0x1401a67ef  mov     r12d, [rdx+38h]
0x1401a67f3  test    r12d, r12d
0x1401a67f6  jz      loc_1401A69E5
0x1401a67fc  xor     r9d, r9d
0x1401a67ff  xor     r10b, r10b
0x1401a6802  xor     r11d, r11d
0x1401a6805  mov     [rbp+57h+var_60], r9b
0x1401a6809  xor     r13b, r13b
0x1401a680c  xor     r15d, r15d
0x1401a680f  mov     ecx, [rdx+r15*4+78h]
0x1401a6814  cmp     ecx, 80h
0x1401a681a  jb      short loc_1401A6891
0x1401a681c  mov     edi, [rdx+10h]
0x1401a681f  cmp     ecx, edi
0x1401a6821  jnb     short loc_1401A6891
0x1401a6823  mov     r8d, ecx
0x1401a6826  mov     ecx, [rcx+rdx]
0x1401a6829  sub     ecx, 40h ; '@'
0x1401a682c  jz      short loc_1401A6882
0x1401a682e  sub     ecx, esi
0x1401a6830  jz      short loc_1401A6855
0x1401a6832  cmp     ecx, esi
0x1401a6834  jnz     short loc_1401A688B
0x1401a6836  lea     rcx, [r8+28h]
0x1401a683a  cmp     rcx, rdi
0x1401a683d  ja      short loc_1401A688B
0x1401a683f  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401a6845  jbe     short loc_1401A684E
0x1401a6847  lea     r11, [rdx+20h]
0x1401a684b  add     r11, r8
0x1401a684e  mov     r9, [r8+rdx+18h]
0x1401a6853  jmp     short loc_1401A68B3
0x1401a6855  lea     rcx, [r8+38h]
0x1401a6859  cmp     rcx, rdi
0x1401a685c  ja      short loc_1401A688B
0x1401a685e  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a6864  mov     [rbp+57h+var_60], sil
0x1401a6868  jbe     short loc_1401A6871
0x1401a686a  lea     r11, [rdx+18h]
0x1401a686e  add     r11, r8
0x1401a6871  mov     r13b, [r8+rdx+8]
0x1401a6876  mov     r9, [r8+rdx+10h]
0x1401a687b  mov     r10b, [r8+rdx+9]
0x1401a6880  jmp     short loc_1401A688B
0x1401a6882  lea     rcx, [r8+28h]
0x1401a6886  cmp     rcx, rdi
0x1401a6889  jbe     short loc_1401A689F
0x1401a688b  cmp     [rbp+57h+var_60], 0
0x1401a688f  jnz     short loc_1401A68BD
0x1401a6891  add     r15d, esi
0x1401a6894  cmp     r15d, r12d
0x1401a6897  jb      loc_1401A680F
0x1401a689d  jmp     short loc_1401A68BD
0x1401a689f  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a68a5  jbe     short loc_1401A68AE
0x1401a68a7  lea     r11, [rdx+18h]
0x1401a68ab  add     r11, r8
0x1401a68ae  mov     r9, [r8+rdx+10h]
0x1401a68b3  mov     r10b, [r8+rdx+9]
0x1401a68b8  mov     r13b, [r8+rdx+8]
0x1401a68bd  test    r11, r11
0x1401a68c0  jz      loc_1401A69E5
0x1401a68c6  mov     cl, [r11]
0x1401a68c9  jmp     short loc_1401A68E2
0x1401a68cb  mov     cl, [rdx+48h]
0x1401a68ce  mov     r9, [rdx+20h]
0x1401a68d2  mov     r10b, [rdx+0Bh]
0x1401a68d6  mov     r13b, [rdx+4]
0x1401a68da  test    eax, eax
0x1401a68dc  jnz     loc_1401A69E5
0x1401a68e2  sub     cl, 8
0x1401a68e5  test    cl, 5Dh
0x1401a68e8  jnz     loc_1401A69E5
0x1401a68ee  mov     dil, [rdx+3]
0x1401a68f2  cmp     dil, sil
0x1401a68f5  jz      loc_1401A6988
0x1401a68fb  test    r9, r9
0x1401a68fe  jz      loc_1401A6988
0x1401a6904  test    r10b, r10b
0x1401a6907  jz      short loc_1401A6988
0x1401a6909  mov     al, [r9]
0x1401a690c  xor     dl, dl
0x1401a690e  and     al, 7Fh
0x1401a6910  movzx   ecx, r10b
0x1401a6914  sub     al, 72h ; 'r'
0x1401a6916  xor     r11b, r11b
0x1401a6919  xor     r8b, r8b
0x1401a691c  add     rcx, r9
0x1401a691f  cmp     al, sil
0x1401a6922  lea     rax, [r9+8]
0x1401a6926  jbe     short loc_1401A696A
0x1401a6928  cmp     rax, rcx
0x1401a692b  ja      short loc_1401A6980
0x1401a692d  movzx   ecx, byte ptr [r9+7]
0x1401a6932  lea     r8, [r9+0Dh]
0x1401a6936  mov     dl, [r9+2]
0x1401a693a  add     ecx, 8
0x1401a693d  and     dl, 0Fh
0x1401a6940  movzx   eax, r10b
0x1401a6944  cmp     ecx, eax
0x1401a6946  cmovbe  eax, ecx
0x1401a6949  mov     ecx, eax
0x1401a694b  add     rcx, r9
0x1401a694e  cmp     r8, rcx
0x1401a6951  ja      short loc_1401A6957
0x1401a6953  mov     r11b, [r9+0Ch]
0x1401a6957  lea     rax, [r9+0Eh]
0x1401a695b  cmp     rax, rcx
0x1401a695e  ja      short loc_1401A6965
0x1401a6960  mov     r8b, [r8]
0x1401a6963  jmp     short loc_1401A6983
0x1401a6965  xor     r8b, r8b
0x1401a6968  jmp     short loc_1401A6983
0x1401a696a  cmp     rax, rcx
0x1401a696d  ja      short loc_1401A6980
0x1401a696f  mov     dl, [r9+1]
0x1401a6973  mov     r11b, [r9+2]
0x1401a6977  and     dl, 0Fh
0x1401a697a  mov     r8b, [r9+3]
0x1401a697e  jmp     short loc_1401A6983
0x1401a6980  xor     sil, sil
0x1401a6983  test    sil, sil
0x1401a6986  jnz     short loc_1401A6990
0x1401a6988  xor     dl, dl
0x1401a698a  xor     r11b, r11b
0x1401a698d  xor     r8b, r8b
0x1401a6990  mov     eax, [rbx+30h]
0x1401a6993  mov     r9, rbx
0x1401a6996  mov     [rsp+0C0h+var_70], rbx
0x1401a699b  mov     byte ptr [rsp+0C0h+var_78], r8b
0x1401a69a0  lea     r8, [rbp+57h+var_50]
  ... truncated ...
```
