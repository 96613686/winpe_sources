# VsmmDmpDecommitGpasBalloonRange

- ea: `0x140039428`
- end: `0x140039c9c`
- name: `VsmmDmpDecommitGpasBalloonRange`
- size: `2164`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002c404`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140007660`
- `0x1400081d4`
- `0x14000a4e0`
- `0x14000f93c`
- `0x140021650`
- `0x140023224`
- `0x140028954`
- `0x140029340`
- `0x14002c780`
- `0x14002cbc4`
- `0x14002cd50`
- `0x14002df90`
- `0x14002f524`
- `0x140030790`
- `0x1400307d0`
- `0x140039428`
- `0x1400ad558`
- `0x1400ee634`
- `0x1400fad08`
- `0x1400fc8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140039bee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039bee`
- `ntoskrnl!RtlSetBitsEx` at `0x140039ae7`
- `ntoskrnl!RtlSetBitsEx` at `0x140039ae7`

## string_xrefs

- `0x14003957f`: `VsmmDmpDecommitGpasBalloonRange`
- `0x140039759`: `VsmmDmpDecommitGpasBalloonRange`
- `0x140039a81`: `VsmmDmpDecommitGpasBalloonRange`
- `0x140039a9f`: `VsmmDmpDecommitGpasBalloonRange`
- `0x140039abd`: `VsmmDmpDecommitGpasBalloonRange`

## pseudocode

```c
__int64 __fastcall VsmmDmpDecommitGpasBalloonRange(__int64 a1, char *a2, unsigned __int64 a3, _QWORD *a4)
{
  _QWORD *v5; // rdi
  __int64 v6; // r14
  __int64 v8; // r15
  char *v9; // r13
  char v10; // al
  _DWORD *v11; // rsi
  __int64 v12; // rdx
  int v13; // ecx
  PVOID v14; // r8
  __int64 v15; // r9
  __int64 v16; // r10
  int v17; // r11d
  int v18; // edi
  __int64 v19; // r9
  __int64 v20; // r10
  unsigned __int64 v21; // rbx
  int IsHmeMemoryBlock; // eax
  int v23; // edx
  char *v24; // rax
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  _QWORD *v29; // rbx
  __int64 v30; // rcx
  int v31; // r12d
  char v33; // [rsp+50h] [rbp-B0h] BYREF
  char v34; // [rsp+51h] [rbp-AFh]
  char v35; // [rsp+52h] [rbp-AEh] BYREF
  char v36; // [rsp+53h] [rbp-ADh]
  char v37; // [rsp+54h] [rbp-ACh]
  char *v38; // [rsp+58h] [rbp-A8h]
  PVOID P; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h]
  __int64 v42; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v43; // [rsp+80h] [rbp-80h]
  unsigned __int64 v44; // [rsp+88h] [rbp-78h] BYREF
  __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h]
  char *v47; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v48; // [rsp+A8h] [rbp-58h] BYREF
  char *v49; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD *v51; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v52; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+D8h] [rbp-28h]
  __int64 v55; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v56[3]; // [rsp+E8h] [rbp-18h] BYREF
  char v57[32]; // [rsp+100h] [rbp+0h] BYREF
  char v58[16]; // [rsp+120h] [rbp+20h] BYREF
  char v59[16]; // [rsp+130h] [rbp+30h] BYREF
  __int64 *v60; // [rsp+140h] [rbp+40h]
  __int64 v61; // [rsp+148h] [rbp+48h]
  unsigned __int64 *v62; // [rsp+150h] [rbp+50h]
  __int64 v63; // [rsp+158h] [rbp+58h]
  __int64 v64; // [rsp+160h] [rbp+60h]
  __int64 v65; // [rsp+168h] [rbp+68h]
  _DWORD *v66; // [rsp+170h] [rbp+70h]
  __int64 v67; // [rsp+178h] [rbp+78h]
  __int64 v68; // [rsp+180h] [rbp+80h]
  _DWORD v69[2]; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int64 *v70; // [rsp+190h] [rbp+90h]
  __int64 v71; // [rsp+198h] [rbp+98h]
  char **v72; // [rsp+1A0h] [rbp+A0h]
  __int64 v73; // [rsp+1A8h] [rbp+A8h]
  __int64 *v74; // [rsp+1B0h] [rbp+B0h]
  __int64 v75; // [rsp+1B8h] [rbp+B8h]
  __int64 *v76; // [rsp+1C0h] [rbp+C0h]
  __int64 v77; // [rsp+1C8h] [rbp+C8h]
  unsigned __int64 *v78; // [rsp+1D0h] [rbp+D0h]
  __int64 v79; // [rsp+1D8h] [rbp+D8h]
  __int64 *v80; // [rsp+1E0h] [rbp+E0h]
  __int64 v81; // [rsp+1E8h] [rbp+E8h]
  _QWORD *v82; // [rsp+1F0h] [rbp+F0h]
  __int64 v83; // [rsp+1F8h] [rbp+F8h]
  _QWORD v84[32]; // [rsp+200h] [rbp+100h] BYREF

  v56[1] = a1;
  v51 = a4;
  *a4 = 0;
  v54 = 0;
  v5 = a4;
  v6 = *(_QWORD *)(a1 + 240);
  v8 = *(_QWORD *)(a1 + 384);
  v9 = &a2[*(_QWORD *)(a1 + 392) - *(_QWORD *)(a1 + 256)];
  v10 = *(_BYTE *)(v6 + 8460);
  v47 = a2;
  v42 = 0;
  v33 = 0;
  v11 = (_DWORD *)(v8 + 20);
  v37 = 0;
  P = 0;
  v34 = v10 != 0;
  v41 = 0;
  v45 = 0;
  v46 = 0;
  v53 = 0;
  v43 = 0;
  v38 = 0;
  v52 = 0;
  v35 = 0;
  v36 = v10;
  if ( (unsigned int)VsmmVsmGetEnabledSecureVtls(v6, 0, 0, 0) )
  {
    if ( ((unsigned __int8)*v11 & (unsigned __int8)(v12 + 8)) != 0 )
    {
      if ( !_bittest64(*(const signed __int64 **)(*((_QWORD *)VidDeviceExtension + 274) + 8LL), 1u) )
      {
        v18 = -1073741637;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v58, "VsmmDmpDecommitGpasBalloonRange");
          tlgCreate1Sz_char(v59, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c");
          v60 = &v42;
          v49 = v47;
          v62 = &v40;
          LODWORD(v42) = 3451;
          v64 = v6 + 656;
          v65 = 16;
          v66 = v69;
          v68 = *(_QWORD *)(v6 + 128);
          v69[0] = *(unsigned __int16 *)(v6 + 120);
          v50 = *(_QWORD *)(v6 + 648);
          v70 = &v50;
          v72 = &v49;
          v74 = (__int64 *)&v48;
          v45 = *(_QWORD *)(a1 + 248);
          v76 = &v45;
          v44 = *(_QWORD *)(a1 + 256);
          v78 = &v44;
          v55 = *(_QWORD *)(a1 + 264);
          v80 = &v55;
          v56[0] = *(int *)(a1 + 292);
          v82 = v56;
          v61 = 4;
          LODWORD(v40) = -1073741637;
          v63 = 4;
          v67 = 2;
          v69[1] = v19;
          v71 = v20;
          v73 = v20;
          v48 = a3;
          v75 = v20;
          v77 = v20;
          v79 = v20;
          v81 = v20;
          v83 = v20;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14005A8E9, 0, v19, 16, v57);
        }
        goto LABEL_52;
      }
      VsmmHvMapGpasFromPfnArray(v6, (_DWORD)v47, a3, 7);
    }
    else
    {
      VsmmUpdateGpaSpaceForMbpRangeModification(v13, v8, (_DWORD)v9, a3, 1, -1, v12);
    }
    v37 = 1;
    v18 = VsmmVsmVerifyGpaRangeDefaultVtlPermissions(a1, v47, a3, 0);
    if ( v18 < 0 )
    {
      VidTraceErrorStatusInternal0("VsmmDmpDecommitGpasBalloonRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c", 3486);
      goto LABEL_52;
    }
    v12 = (__int64)v38;
    v5 = v51;
    v14 = v38;
    v16 = v45;
    v15 = (__int64)v38;
    v17 = (int)v38;
  }
  v21 = 0;
  v44 = -1;
  v40 = -1;
  v49 = 0;
  v50 = 0;
  if ( !a3 )
  {
LABEL_51:
    v18 = 0;
    goto LABEL_52;
  }
  while ( 1 )
  {
    if ( (*v11 & 8) == 0 )
    {
      if ( v14 && v15 == v16 )
      {
        if ( v12 )
        {
          VsmmUpdateGpaSpaceForMbpRangeModification(v6, v8, v17 + (_DWORD)v9, v12, 0, -1, 0);
          v43 = v21;
          v38 = 0;
        }
        LOBYTE(v15) = v34;
        VsmmDmpRepurposePfns(v8, P, v41, v15);
        v41 = 0;
        if ( v36 )
        {
          P = 0;
          v35 = 0;
          v45 = 0;
        }
      }
      if ( v46 == 32 )
      {
        if ( v38 )
        {
          VsmmUpdateGpaSpaceForMbpRangeModification(v6, v8, (_DWORD)v9 + v43, (_DWORD)v38, 0, -1, 0);
          v43 = v21;
          v38 = 0;
        }
        IsHmeMemoryBlock = VsmmHmeIsHmeMemoryBlock(v8);
        LOBYTE(v23) = *(_BYTE *)(v8 + 16);
        VsmmFreePagesIoSpace(v6, v23, *(_DWORD *)(v8 + 252), 4, (__int64)v84, 32, IsHmeMemoryBlock);
        v46 = 0;
      }
      if ( !P )
      {
        v24 = (char *)VsmmDmpDecommitGpasMdlGet(v6, a3 - *v5, v34, &v35, &v45);
        P = v24;
        if ( !v24 )
        {
          v18 = -1073741670;
          VidTraceErrorStatusInternal0("VsmmDmpDecommitGpasBalloonRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c", 3571);
          goto LABEL_52;
        }
        v49 = v24 + 48;
      }
    }
    v48 = (unsigned __int64)&v9[v21];
    v18 = VsmmMbpDmBalloon(v8, (int)v21 + (int)v9, (unsigned int)&v42, (unsigned int)&v52, (__int64)&v33);
    if ( v18 < 0 )
      break;
LABEL_32:
    if ( (*v11 & 8) != 0 )
    {
      v12 = (__int64)v38;
      goto LABEL_46;
    }
    if ( v33 )
    {
      v25 = v40;
      if ( (v42 & 0xFFFFFFFFFFFC0000uLL) != v40 )
      {
        v25 = v42 & 0xFFFFFFFFFFFC0000uLL;
        v40 = v42 & 0xFFFFFFFFFFFC0000uLL;
        v26 = v21 & 0xFFFFFFFFFFFC0000uLL;
        v44 = v21 & 0xFFFFFFFFFFFC0000uLL;
        goto LABEL_41;
      }
    }
    else
    {
      if ( v42 == -1 )
      {
        ++v53;
      }
      else
      {
        v27 = v41;
        *(_QWORD *)&v49[8 * v41] = v42;
        v41 = v27 + 1;
      }
      v25 = v40;
    }
    v26 = v44;
LABEL_41:
    if ( v25 != -1 && v21 == v26 + 0x3FFFF )
    {
      v28 = v46;
      v40 = -1;
      v84[v46] = v25 << 12;
      v46 = v28 + 1;
    }
    v12 = (__int64)++v38;
LABEL_46:
    v5 = v51;
    v50 = ++v21;
    ++*v51;
    if ( v21 >= a3 )
      goto LABEL_51;
    v14 = P;
    v15 = v41;
    v16 = v45;
    v17 = v43;
  }
  while ( v18 == -2147483631 )
  {
    VidLockRelease(v6 + 3744);
    v18 = VsmmDmSlpWaitForTransientMbpOperationComplete(v8, v48);
    VidLockAcquireExclusive(v6 + 3744);
    if ( v18 < 0 )
    {
      VidTraceErrorStatusInternal0("VsmmDmpDecommitGpasBalloonRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c", 3607);
      goto LABEL_52;
    }
    v18 = VsmmMbpDmBalloon(v8, v48, (unsigned int)&v42, (unsigned int)&v52, (__int64)&v33);
    if ( v18 >= 0 )
    {
      v21 = v50;
      goto LABEL_32;
    }
  }
  VidTraceErrorStatusInternal0("VsmmDmpDecommitGpasBalloonRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c", 3593);
LABEL_52:
  v29 = v51;
  if ( *v51 )
  {
    RtlSetBitsEx(v8 + 352, v9, *v51);
    VidReaderCounterAdvanceAndWait(v6 + 3928, 1);
    if ( (*v11 & 8) != 0 )
    {
      VsmmMemoryBlockDecommitPrimaryRamRange(v8, v9, *v29, 1);
    }
    else
    {
      VsmmDmpDecommitGpasFlush(v6, v8, (_DWORD)P, v41, (__int64)v84, v46, (__int64)&v9[v43], (__int64)v38, v34);
      if ( *(_BYTE *)(v6 + 8460) )
      {
        VsmmDmSlpBitmapRangeClear(v8 + 552, v9, *v29);
        VsmmDmSlpBitmapRangeClear(v8 + 576, v9, *v29);
        if ( v52 )
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v6 + 1528) + 1096LL), v52);
        if ( v53 )
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v6 + 1528) + 1104LL), -v53);
      }
    }
    v18 = 0;
  }
  if ( v35 && (!v36 || !v38) )
    ExFreePoolWithTag(P, 0x6D4D6456u);
  if ( v37 )
  {
    v30 = *v29;
    if ( *v29 != a3 )
    {
      v31 = a3 - v30;
      if ( (*v11 & 8) != 0 )
        VsmmHvMapGpasFromPfnArray(v6, v30 + (_DWORD)v47, v31, 6);
      else
        VsmmUpdateGpaSpaceForMbpRangeModification(v6, v8, v30 + (_DWORD)v9, v31, 0, -1, 0);
    }
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140039428  push    rbp
0x14003942a  push    rbx
0x14003942b  push    rsi
0x14003942c  push    rdi
0x14003942d  push    r12
0x14003942f  push    r13
0x140039431  push    r14
0x140039433  push    r15
0x140039435  lea     rbp, [rsp-218h]
0x14003943d  sub     rsp, 318h
0x140039444  mov     rax, cs:__security_cookie
0x14003944b  xor     rax, rsp
0x14003944e  mov     [rbp+250h+var_50], rax
0x140039455  mov     rbx, rcx
0x140039458  mov     [rbp+250h+var_260], rcx
0x14003945c  xor     ecx, ecx
0x14003945e  mov     [rbp+250h+var_290], r9
0x140039462  mov     [r9], rcx
0x140039465  mov     rsi, rdx
0x140039468  mov     [rbp+250h+var_278], rcx
0x14003946c  mov     rdi, r9
0x14003946f  mov     r14, [rbx+0F0h]
0x140039476  mov     r12, r8
0x140039479  mov     r13, [rbx+188h]
0x140039480  mov     r8d, ecx
0x140039483  sub     r13, [rbx+100h]
0x14003948a  mov     r9d, ecx
0x14003948d  mov     r15, [rbx+180h]
0x140039494  add     r13, rsi
0x140039497  mov     al, [r14+210Ch]
0x14003949e  mov     r10d, ecx
0x1400394a1  test    al, al
0x1400394a3  mov     [rbp+250h+var_2B0], rdx
0x1400394a7  mov     [rsp+350h+var_2D8], rcx
0x1400394ac  mov     r11d, ecx
0x1400394af  mov     [rsp+350h+var_300], cl
0x1400394b3  lea     rsi, [r15+14h]
0x1400394b7  mov     [rsp+350h+var_2FC], cl
0x1400394bb  mov     edx, ecx
0x1400394bd  mov     [rsp+350h+P], rcx
0x1400394c2  setnz   [rsp+350h+var_2FF]
0x1400394c7  mov     [rsp+350h+var_2E0], rcx
0x1400394cc  mov     [rbp+250h+var_2C0], rcx
0x1400394d0  mov     [rbp+250h+var_2B8], rcx
0x1400394d4  mov     [rbp+250h+var_280], rcx
0x1400394d8  mov     [rbp+250h+var_2D0], rcx
0x1400394dc  mov     [rsp+350h+var_2F8], rcx
0x1400394e1  mov     [rbp+250h+var_288], rcx
0x1400394e5  mov     [rsp+350h+var_2FE], cl
0x1400394e9  mov     rcx, r14
0x1400394ec  mov     [rsp+350h+var_2FD], al
0x1400394f0  call    VsmmVsmGetEnabledSecureVtls
0x1400394f5  test    eax, eax
0x1400394f7  jz      loc_140039780
0x1400394fd  mov     eax, [rsi]
0x1400394ff  lea     r10d, [rdx+8]
0x140039503  test    r10b, al
0x140039506  jnz     short loc_140039530
0x140039508  mov     [rsp+350h+var_320], rdx
0x14003950d  mov     r9, r12
0x140039510  mov     dword ptr [rsp+350h+var_328], 0FFFFFFFFh
0x140039518  mov     rdx, r15
0x14003951b  mov     r8, r13
0x14003951e  mov     dword ptr [rsp+350h+var_330], 1
0x140039526  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x14003952b  jmp     loc_14003972C
0x140039530  mov     rax, cs:VidDeviceExtension
0x140039537  mov     rcx, [rax+890h]
0x14003953e  mov     rax, [rcx+8]
0x140039542  bt      qword ptr [rax], 1
0x140039547  setb    al
0x14003954a  test    al, al
0x14003954c  jnz     loc_1400396FF
0x140039552  mov     eax, cs:dword_140064110
0x140039558  mov     edi, 0C00000BBh
0x14003955d  cmp     eax, 2
0x140039560  jbe     loc_140039ACD
0x140039566  mov     edx, 100h
0x14003956b  lea     rcx, dword_140064110
0x140039572  call    _tlgKeywordOn
0x140039577  test    al, al
0x140039579  jz      loc_140039ACD
0x14003957f  lea     rdx, aVsmmdmpdecommi_0; "VsmmDmpDecommitGpasBalloonRange"
0x140039586  lea     rcx, [rbp+250h+var_230]
0x14003958a  call    _tlgCreate1Sz_char
0x14003958f  lea     rdx, aOnecoreVmVidSy_18; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c"
0x140039596  lea     rcx, [rbp+250h+var_220]
0x14003959a  call    _tlgCreate1Sz_char
0x14003959f  mov     rdx, [rbp+250h+var_2B0]
0x1400395a3  lea     rax, [rsp+350h+var_2D8]
0x1400395a8  mov     [rbp+250h+var_210], rax
0x1400395ac  lea     rcx, dword_140064110
0x1400395b3  lea     rax, [rsp+350h+var_2E8]
0x1400395b8  mov     [rbp+250h+var_2A0], rdx
0x1400395bc  mov     [rbp+250h+var_200], rax
0x1400395c0  lea     rdx, byte_14005A8E9
0x1400395c7  lea     rax, [r14+290h]
0x1400395ce  mov     dword ptr [rsp+350h+var_2D8], 0D7Bh
0x1400395d6  mov     [rbp+250h+var_1F0], rax
0x1400395da  mov     r8d, 10h
0x1400395e0  lea     rax, [rbp+250h+var_1C8]
0x1400395e7  mov     [rbp+250h+var_1E8], r8
0x1400395eb  mov     [rbp+250h+var_1E0], rax
0x1400395ef  mov     rax, [r14+80h]
0x1400395f6  mov     [rbp+250h+var_1D0], rax
0x1400395fd  movzx   eax, word ptr [r14+78h]
0x140039602  mov     [rbp+250h+var_1C8], eax
0x140039608  mov     rax, [r14+288h]
0x14003960f  mov     [rbp+250h+var_298], rax
0x140039613  lea     rax, [rbp+250h+var_298]
0x140039617  mov     [rbp+250h+var_1C0], rax
0x14003961e  lea     rax, [rbp+250h+var_2A0]
0x140039622  mov     [rbp+250h+var_1B0], rax
0x140039629  lea     rax, [rbp+250h+var_2A8]
0x14003962d  mov     [rbp+250h+var_1A0], rax
0x140039634  mov     rax, [rbx+0F8h]
0x14003963b  mov     [rbp+250h+var_2C0], rax
0x14003963f  lea     rax, [rbp+250h+var_2C0]
0x140039643  mov     [rbp+250h+var_190], rax
0x14003964a  mov     rax, [rbx+100h]
0x140039651  mov     [rbp+250h+var_2C8], rax
0x140039655  lea     rax, [rbp+250h+var_2C8]
0x140039659  mov     [rbp+250h+var_180], rax
0x140039660  mov     rax, [rbx+108h]
0x140039667  mov     [rbp+250h+var_270], rax
0x14003966b  lea     rax, [rbp+250h+var_270]
0x14003966f  mov     [rbp+250h+var_170], rax
0x140039676  movsxd  rax, dword ptr [rbx+124h]
0x14003967d  mov     [rbp+250h+var_268], rax
0x140039681  lea     rax, [rbp+250h+var_268]
0x140039685  mov     [rbp+250h+var_160], rax
0x14003968c  lea     rax, [rbp+250h+var_250]
0x140039690  mov     [rsp+350h+var_328], rax
0x140039695  mov     dword ptr [rsp+350h+var_330], r8d
0x14003969a  xor     r8d, r8d
0x14003969d  mov     [rbp+250h+var_208], 4
0x1400396a5  mov     dword ptr [rsp+350h+var_2E8], edi
0x1400396a9  mov     [rbp+250h+var_1F8], 4
0x1400396b1  mov     [rbp+250h+var_1D8], 2
0x1400396b9  mov     [rbp+250h+var_1C4], r9d
0x1400396c0  mov     [rbp+250h+var_1B8], r10
0x1400396c7  mov     [rbp+250h+var_1A8], r10
0x1400396ce  mov     [rbp+250h+var_2A8], r12
0x1400396d2  mov     [rbp+250h+var_198], r10
0x1400396d9  mov     [rbp+250h+var_188], r10
0x1400396e0  mov     [rbp+250h+var_178], r10
0x1400396e7  mov     [rbp+250h+var_168], r10
0x1400396ee  mov     [rbp+250h+var_158], r10
0x1400396f5  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400396fa  jmp     loc_140039ACD
0x1400396ff  mov     eax, [rbx+124h]
0x140039705  mov     r8, r12
0x140039708  mov     rdx, [rbp+250h+var_2B0]
0x14003970c  mov     rcx, r14
0x14003970f  mov     dword ptr [rsp+350h+var_318], r9d
0x140039714  mov     r9d, 7
0x14003971a  mov     dword ptr [rsp+350h+var_320], eax
0x14003971e  lea     rax, [rbp+250h+var_278]
0x140039722  mov     [rsp+350h+var_328], rax
0x140039727  call    VsmmHvMapGpasFromPfnArray
0x14003972c  mov     rdx, [rbp+250h+var_2B0]
0x140039730  xor     r9d, r9d
0x140039733  mov     r8, r12
0x140039736  mov     [rsp+350h+var_2FC], 1
0x14003973b  mov     rcx, rbx
0x14003973e  call    VsmmVsmVerifyGpaRangeDefaultVtlPermissions
0x140039743  mov     edi, eax
0x140039745  test    eax, eax
0x140039747  jns     short loc_14003976A
0x140039749  mov     r9d, eax
0x14003974c  lea     rdx, aOnecoreVmVidSy_18; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdm.c"
0x140039753  mov     r8d, 0D9Eh
0x140039759  lea     rcx, aVsmmdmpdecommi_0; "VsmmDmpDecommitGpasBalloonRange"
0x140039760  call    VidTraceErrorStatusInternal0
0x140039765  jmp     loc_140039ACD
0x14003976a  mov     rdx, [rsp+350h+var_2F8]
0x14003976f  mov     rdi, [rbp+250h+var_290]
0x140039773  mov     r8, rdx
0x140039776  mov     r10, [rbp+250h+var_2C0]
0x14003977a  mov     r9, rdx
0x14003977d  mov     r11, rdx
0x140039780  xor     ebx, ebx
0x140039782  mov     [rbp+250h+var_2C8], 0FFFFFFFFFFFFFFFFh
0x14003978a  mov     [rsp+350h+var_2E8], 0FFFFFFFFFFFFFFFFh
0x140039793  mov     [rbp+250h+var_2A0], 0
0x14003979b  mov     [rbp+250h+var_298], rbx
0x14003979f  test    r12, r12
0x1400397a2  jz      loc_140039ACB
0x1400397a8  mov     eax, [rsi]
0x1400397aa  test    al, 8
0x1400397ac  jnz     loc_140039907
0x1400397b2  test    r8, r8
0x1400397b5  jz      short loc_140039836
0x1400397b7  cmp     r9, r10
0x1400397ba  jnz     short loc_140039836
0x1400397bc  test    rdx, rdx
0x1400397bf  jz      short loc_1400397F9
0x1400397c1  mov     [rsp+350h+var_320], 0
0x1400397ca  lea     r8, [r11+r13]
0x1400397ce  mov     r9, rdx
0x1400397d1  mov     dword ptr [rsp+350h+var_328], 0FFFFFFFFh
0x1400397d9  mov     rdx, r15
0x1400397dc  mov     dword ptr [rsp+350h+var_330], 0
0x1400397e4  mov     rcx, r14
0x1400397e7  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x1400397ec  mov     [rbp+250h+var_2D0], rbx
0x1400397f0  mov     [rsp+350h+var_2F8], 0
0x1400397f9  mov     r9b, [rsp+350h+var_2FF]
0x1400397fe  mov     rcx, r15
0x140039801  mov     r8, [rsp+350h+var_2E0]
0x140039806  mov     rdx, [rsp+350h+P]
0x14003980b  call    VsmmDmpRepurposePfns
0x140039810  cmp     [rsp+350h+var_2FD], 0
0x140039815  mov     [rsp+350h+var_2E0], 0
0x14003981e  jz      short loc_140039836
0x140039820  mov     [rsp+350h+P], 0
0x140039829  mov     [rsp+350h+var_2FE], 0
0x14003982e  mov     [rbp+250h+var_2C0], 0
0x140039836  cmp     [rbp+250h+var_2B8], 20h ; ' '
0x14003983b  jnz     loc_1400398C8
0x140039841  mov     rax, [rsp+350h+var_2F8]
0x140039846  test    rax, rax
0x140039849  jz      short loc_140039886
0x14003984b  mov     r8, [rbp+250h+var_2D0]
0x14003984f  mov     r9, rax
0x140039852  mov     [rsp+350h+var_320], 0
0x14003985b  add     r8, r13
0x14003985e  mov     dword ptr [rsp+350h+var_328], 0FFFFFFFFh
0x140039866  mov     rdx, r15
0x140039869  mov     rcx, r14
0x14003986c  mov     dword ptr [rsp+350h+var_330], 0
0x140039874  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x140039879  mov     [rbp+250h+var_2D0], rbx
0x14003987d  mov     [rsp+350h+var_2F8], 0
0x140039886  mov     rcx, r15
0x140039889  call    VsmmHmeIsHmeMemoryBlock
0x14003988e  mov     r8d, [r15+0FCh]
0x140039895  mov     r9d, 4
0x14003989b  mov     dl, [r15+10h]
0x14003989f  mov     rcx, r14
0x1400398a2  mov     dword ptr [rsp+350h+var_320], eax
0x1400398a6  lea     rax, [rbp+250h+var_150]
0x1400398ad  mov     [rsp+350h+var_328], 20h ; ' '
0x1400398b6  mov     [rsp+350h+var_330], rax
0x1400398bb  call    VsmmFreePagesIoSpace
0x1400398c0  mov     [rbp+250h+var_2B8], 0
0x1400398c8  cmp     [rsp+350h+P], 0
0x1400398ce  jnz     short loc_140039907
0x1400398d0  mov     r8b, [rsp+350h+var_2FF]
0x1400398d5  lea     rax, [rbp+250h+var_2C0]
0x1400398d9  mov     rdx, r12
0x1400398dc  mov     [rsp+350h+var_330], rax
0x1400398e1  sub     rdx, [rdi]
0x1400398e4  lea     r9, [rsp+350h+var_2FE]
0x1400398e9  mov     rcx, r14
0x1400398ec  call    VsmmDmpDecommitGpasMdlGet
0x1400398f1  mov     [rsp+350h+P], rax
0x1400398f6  test    rax, rax
0x1400398f9  jz      loc_140039A6C
0x1400398ff  add     rax, 30h ; '0'
0x140039903  mov     [rbp+250h+var_2A0], rax
0x140039907  lea     rax, [rbx+r13]
0x14003990b  lea     rcx, [rsp+350h+var_300]
0x140039910  mov     [rbp+250h+var_2A8], rax
0x140039914  mov     [rsp+350h+var_330], rcx
0x140039919  lea     r9, [rbp+250h+var_288]
0x14003991d  mov     rcx, r15
0x140039920  lea     r8, [rsp+350h+var_2D8]
0x140039925  mov     rdx, rax
0x140039928  call    VsmmMbpDmBalloon
0x14003992d  mov     edi, eax
0x14003992f  test    eax, eax
0x140039931  jns     short loc_140039995
0x140039933  cmp     edi, 80000011h
0x140039939  jnz     loc_140039AAD
0x14003993f  lea     rbx, [r14+0EA0h]
0x140039946  mov     rcx, rbx
0x140039949  call    VidLockRelease
0x14003994e  mov     rdx, [rbp+250h+var_2A8]
0x140039952  mov     rcx, r15
0x140039955  call    VsmmDmSlpWaitForTransientMbpOperationComplete
0x14003995a  mov     rcx, rbx
0x14003995d  mov     edi, eax
0x14003995f  call    VidLockAcquireExclusive
0x140039964  test    edi, edi
0x140039966  js      loc_140039A8F
0x14003996c  mov     rdx, [rbp+250h+var_2A8]
0x140039970  lea     rax, [rsp+350h+var_300]
0x140039975  lea     r9, [rbp+250h+var_288]
0x140039979  mov     [rsp+350h+var_330], rax
0x14003997e  lea     r8, [rsp+350h+var_2D8]
0x140039983  mov     rcx, r15
0x140039986  call    VsmmMbpDmBalloon
0x14003998b  mov     edi, eax
0x14003998d  test    eax, eax
0x14003998f  js      short loc_140039933
0x140039991  mov     rbx, [rbp+250h+var_298]
0x140039995  mov     eax, [rsi]
0x140039997  test    al, 8
0x140039999  jnz     loc_140039A3D
  ... truncated ...
```
