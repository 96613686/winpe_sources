# TlShimDirectClassify

- ea: `0x140134880`
- end: `0x140134f3c`
- name: `TlShimDirectClassify`
- size: `1724`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004e590`
- `0x140050c94`
- `0x140052a40`
- `0x140098370`

## callees

- `0x14004ca70`
- `0x14004d980`
- `0x14004db00`
- `0x140050750`
- `0x140051888`
- `0x140053af0`
- `0x140053bb0`
- `0x1400540a4`
- `0x140134880`
- `0x140134f44`
- `0x1401bf4d0`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401349fb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134c48`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134c8b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134eb8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134ef8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401349fb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134c48`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134c8b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134eb8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134ef8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140134938`
- `ntoskrnl!KeGetCurrentIrql` at `0x140134938`
- `ntoskrnl!ExFreePoolWithTag` at `0x140134f27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140134f27`
- `NETIO!KfdDirectClassify` at `0x140134bc4`
- `NETIO!KfdDirectClassify` at `0x140134bc4`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140134bf6`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140134e66`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140134bf6`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140134e66`

## pseudocode

```c
char __fastcall TlShimDirectClassify(
        KSPIN_LOCK *a1,
        unsigned __int16 a2,
        __int64 a3,
        int a4,
        __int16 a5,
        __int16 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        char a10,
        char a11,
        int *a12)
{
  int *v12; // rbx
  unsigned __int16 v15; // r14
  __int64 v16; // rax
  unsigned __int8 v17; // di
  char v18; // r12
  PVOID v19; // rsi
  PVOID *v20; // rbx
  char *v21; // rbx
  __int64 v22; // rdi
  int v23; // ecx
  bool v24; // zf
  __int128 *v25; // rax
  int v26; // eax
  __int64 v27; // r9
  __int64 v28; // rax
  PVOID *v29; // rdi
  char *v30; // rdi
  char *v31; // rbx
  char v32; // r15
  int v33; // edi
  int v34; // ecx
  __int64 v35; // r9
  PVOID *v36; // r14
  char *v37; // r14
  char *v38; // rbx
  unsigned __int8 v39; // [rsp+50h] [rbp-B0h]
  PVOID Entry; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v42; // [rsp+60h] [rbp-A0h]
  int v43; // [rsp+68h] [rbp-98h]
  PKSPIN_LOCK SpinLock; // [rsp+70h] [rbp-90h]
  PVOID *p_Entry; // [rsp+78h] [rbp-88h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h]
  __int128 v47; // [rsp+88h] [rbp-78h] BYREF
  __int128 v48; // [rsp+98h] [rbp-68h]
  __int128 v49; // [rsp+A8h] [rbp-58h]
  __int128 v50; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v51; // [rsp+C8h] [rbp-38h]
  __int128 v52; // [rsp+D8h] [rbp-28h]
  int *v53; // [rsp+E8h] [rbp-18h]
  PVOID P[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v55; // [rsp+100h] [rbp+0h] BYREF
  __int128 v56; // [rsp+110h] [rbp+10h]
  int v57; // [rsp+120h] [rbp+20h]

  v12 = a12;
  v46 = a8;
  v43 = a4;
  v57 = 0;
  SpinLock = a1;
  v53 = a12;
  v50 = 0;
  Entry = 0;
  v51 = 0;
  p_Entry = 0;
  v52 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v55 = 0;
  v56 = 0;
  *(_OWORD *)P = 0;
  if ( *(_QWORD *)(a3 + 16) == a3 + 16 )
  {
    *a12 = 1;
    return 1;
  }
  v15 = *(_WORD *)(a3 + 48);
  if ( KeGetCurrentIrql() >= 2u )
  {
    v17 = 0;
    v39 = 0;
    v18 = 0;
  }
  else
  {
    v16 = WfpRaiseIrqlToDispatchLevel();
    v17 = v16;
    v39 = v16;
    v18 = 1;
  }
  LODWORD(v16) = HIDWORD(KeGetPcr()[1].LockArray);
  if ( !*((_BYTE *)gPerProcessorContext + 72 * v16 + 32) )
  {
    v19 = (PVOID)*((_QWORD *)gPerProcessorContext + 9 * v16 + 3);
    v20 = (PVOID *)*((_QWORD *)gPerProcessorContext + 9 * v16 + 2);
    *((_BYTE *)gPerProcessorContext + 72 * v16 + 32) = 1;
    goto LABEL_18;
  }
  if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &Entry) )
  {
    if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &p_Entry) )
    {
      v19 = Entry;
      v20 = p_Entry;
LABEL_18:
      memset(v19, 0, 0x2A0u);
      memset(v20, 0, 0x2A8u);
      v22 = v46;
      v23 = (int)SpinLock;
      v20[79] = v20 + 78;
      v20[78] = v20 + 78;
      TlShimSetDirectClassifyMetadata(v23, a2, *(unsigned __int16 *)(a3 + 48), a7, v22, a9, a10, a11, (__int64)v20);
      WfpAleCopySecurityRealmIdFromEndpoint(SpinLock);
      if ( ((v15 - 12) & 0xFFFD) != 0 )
      {
        if ( ((v15 - 16) & 0xFFFD) != 0 )
          goto LABEL_42;
        *(_QWORD *)&v47 = SpinLock;
        WORD4(v47) = a2;
        HIDWORD(v47) = v43;
        LOWORD(v48) = a5;
        WORD1(v48) = a6;
        LODWORD(v49) = *(_DWORD *)(a3 + 40);
        v24 = *(_BYTE *)(v22 + 44) == 0;
        *((_QWORD *)&v48 + 1) = v22;
        DWORD1(v49) = !v24;
        *((_QWORD *)&v49 + 1) = P;
        v25 = &v47;
      }
      else
      {
        *(_QWORD *)&v50 = SpinLock;
        WORD4(v50) = a2;
        HIDWORD(v50) = v43;
        LOWORD(v51) = a5;
        WORD1(v51) = a6;
        LODWORD(v52) = *(_DWORD *)(a3 + 40);
        v26 = *(_BYTE *)(a7 + 16) & 1;
        *((_QWORD *)&v51 + 1) = a7;
        DWORD1(v52) = v26;
        *((_QWORD *)&v52 + 1) = P;
        v25 = &v50;
      }
      v20[1] = v25;
      if ( a7 )
        v27 = *(_QWORD *)(a7 + 8);
      else
        v27 = *(_QWORD *)(v22 + 48);
      v28 = KfdDirectClassify(v15, *(_QWORD *)(a3 + 32), v20, v27, a3 + 16, &v55);
      if ( !(_BYTE)v28 )
      {
        LODWORD(v28) = HIDWORD(KeGetPcr()[1].LockArray);
        v29 = (PVOID *)((char *)gPerProcessorContext + 72 * v28);
        KfdReleaseTerminatingFilters(v20 + 78);
        if ( v19 == v29[3] )
        {
          *((_BYTE *)v29 + 32) = 0;
        }
        else
        {
          v30 = (char *)gMetadataLookasideList
              + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
          if ( !v30[176] )
            PplpLazyInitializeLookasideList(gMetadataLookasideList, v30 + 64);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v30 + 64), v20);
          v31 = (char *)gIncomingValuesLookasideList
              + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
          if ( !v31[176] )
            PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v31 + 64);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v31 + 64), v19);
        }
        if ( v18 )
          WfpLowerIrqlFromDispatchLevel(v39);
        v32 = 0;
LABEL_61:
        if ( P[1] )
          ExFreePoolWithTag(P[1], 0x52537049u);
        return v32;
      }
      if ( (_DWORD)v55 != 4097 )
      {
        v33 = 1;
        goto LABEL_51;
      }
      if ( (BYTE12(v56) & 1) != 0 )
      {
        v33 = 2;
LABEL_51:
        LODWORD(v28) = HIDWORD(KeGetPcr()[1].LockArray);
        v32 = 1;
        v36 = (PVOID *)((char *)gPerProcessorContext + 72 * v28);
        KfdReleaseTerminatingFilters(v20 + 78);
        if ( v19 == v36[3] )
        {
          *((_BYTE *)v36 + 32) = 0;
        }
        else
        {
          v37 = (char *)gMetadataLookasideList
              + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
          if ( !v37[176] )
            PplpLazyInitializeLookasideList(gMetadataLookasideList, v37 + 64);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v37 + 64), v20);
          v38 = (char *)gIncomingValuesLookasideList
              + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
          if ( !v38[176] )
            PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v38 + 64);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v38 + 64), v19);
        }
        if ( v18 )
          WfpLowerIrqlFromDispatchLevel(v39);
        *v53 = v33;
        goto LABEL_61;
      }
      Entry = 0;
      LODWORD(v42) = 0;
      WORD2(v42) = 0;
      p_Entry = *(PVOID **)(a3 + 32);
      if ( !p_Entry )
      {
        if ( ((v15 - 12) & 0xFFFD) != 0 )
        {
          if ( ((v15 - 16) & 0xFFFD) != 0 )
LABEL_42:
            __fastfail(5u);
          TlShimMarshalOutTransportFields(
            WORD4(v47),
            HIDWORD(v47),
            (unsigned __int16)v48,
            WORD1(v48),
            *((__int64 *)&v48 + 1),
            v49,
            DWORD1(v49),
            *((__int64 *)&v49 + 1),
            (__int64)v19);
          HIDWORD(Entry) = 16;
        }
        else
        {
          TlShimMarshalInTransportFields(
            WORD4(v50),
            HIDWORD(v50),
            (unsigned __int16)v51,
            WORD1(v51),
            *((__int64 *)&v51 + 1),
            v52,
            DWORD1(v52),
            *((__int64 *)&v52 + 1),
            (__int64)v19);
          HIDWORD(Entry) = 15;
        }
        LOWORD(Entry) = v15;
        p_Entry = &Entry;
        v42 = v19;
      }
      v33 = 0;
      memset(v20, 0, 0x2A8u);
      v34 = (int)SpinLock;
      v20[79] = v20 + 78;
      v20[78] = v20 + 78;
      TlShimSetDirectClassifyMetadata(v34, a2, *(unsigned __int16 *)(a3 + 48), a7, v46, a9, a10, a11, (__int64)v20);
      if ( a7 )
        v35 = *(_QWORD *)(a7 + 8);
      else
        v35 = *(_QWORD *)(v46 + 48);
      v28 = WfpShimIndicateDiscardGeneral(v15, (_DWORD)p_Entry, (_DWORD)v20, v35, 0, (__int64)&v55);
      goto LABEL_51;
    }
    v21 = (char *)gIncomingValuesLookasideList
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v21[176] )
      PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v21 + 64);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v21 + 64), Entry);
    v12 = v53;
  }
  if ( v18 )
    WfpLowerIrqlFromDispatchLevel(v17);
  *v12 = 0;
  return 1;
}

```

## disassembly

```asm
0x140134880  push    rbp
0x140134882  push    rbx
0x140134883  push    rsi
0x140134884  push    rdi
0x140134885  push    r13
0x140134887  push    r15
0x140134889  lea     rbp, [rsp-48h]
0x14013488e  sub     rsp, 148h
0x140134895  mov     rax, cs:__security_cookie
0x14013489c  xor     rax, rsp
0x14013489f  mov     [rbp+70h+var_48], rax
0x1401348a3  mov     rax, [rbp+70h+arg_38]
0x1401348aa  xorps   xmm0, xmm0
0x1401348ad  mov     rbx, [rbp+70h+arg_58]
0x1401348b4  xor     esi, esi
0x1401348b6  mov     r13, [rbp+70h+arg_30]
0x1401348bd  xorps   xmm1, xmm1
0x1401348c0  mov     [rbp+70h+var_F0], rax
0x1401348c4  mov     r15, r8
0x1401348c7  xor     eax, eax
0x1401348c9  mov     [rsp+170h+var_108], r9d
0x1401348ce  mov     [rbp+70h+var_50], eax
0x1401348d1  lea     rax, [r8+10h]
0x1401348d5  mov     [rsp+170h+var_11E], dx
0x1401348da  mov     [rsp+170h+SpinLock], rcx
0x1401348df  mov     [rbp+70h+var_88], rbx
0x1401348e3  movups  [rbp+70h+var_B8], xmm0
0x1401348e7  mov     [rsp+170h+Entry], rsi
0x1401348ec  movups  [rbp+70h+var_A8], xmm0
0x1401348f0  mov     [rsp+170h+var_F8], rsi
0x1401348f5  movups  [rbp+70h+var_98], xmm0
0x1401348f9  movups  [rbp+70h+var_E8], xmm1
0x1401348fd  movups  [rbp+70h+var_D8], xmm1
0x140134901  movups  [rbp+70h+var_C8], xmm1
0x140134905  movups  [rbp+70h+var_70], xmm0
0x140134909  movups  [rbp+70h+var_60], xmm0
0x14013490d  movups  xmmword ptr [rbp+70h+P], xmm0
0x140134911  cmp     [rax], rax
0x140134914  jnz     short loc_140134923
0x140134916  mov     dword ptr [rbx], 1
0x14013491c  mov     al, 1
0x14013491e  jmp     loc_140134A2D
0x140134923  mov     [rsp+170h+var_30], r12
0x14013492b  mov     [rsp+170h+var_38], r14
0x140134933  movzx   r14d, word ptr [r8+30h]
0x140134938  call    cs:__imp_KeGetCurrentIrql
0x14013493f  nop     dword ptr [rax+rax+00h]
0x140134944  cmp     al, 2
0x140134946  jnb     short loc_140134959
0x140134948  call    WfpRaiseIrqlToDispatchLevel
0x14013494d  movzx   edi, al
0x140134950  mov     [rsp+170h+var_120], al
0x140134954  mov     r12b, 1
0x140134957  jmp     short loc_140134964
0x140134959  xor     dil, dil
0x14013495c  mov     [rsp+170h+var_120], dil
0x140134961  xor     r12b, r12b
0x140134964  mov     eax, gs:1A4h
0x14013496c  lea     rdx, [rax+rax*8]
0x140134970  mov     rax, cs:gPerProcessorContext
0x140134977  cmp     [rax+rdx*8+20h], sil
0x14013497c  jnz     short loc_140134992
0x14013497e  mov     rsi, [rax+rdx*8+18h]
0x140134983  mov     rbx, [rax+rdx*8+10h]
0x140134988  mov     byte ptr [rax+rdx*8+20h], 1
0x14013498d  jmp     loc_140134A54
0x140134992  mov     rcx, cs:gIncomingValuesLookasideList
0x140134999  lea     rdx, [rsp+170h+Entry]
0x14013499e  call    WfpAllocateFromPerProcessorLookasideList
0x1401349a3  test    rax, rax
0x1401349a6  jnz     short loc_140134A0B
0x1401349a8  mov     rcx, cs:gMetadataLookasideList
0x1401349af  lea     rdx, [rsp+170h+var_F8]
0x1401349b4  call    WfpAllocateFromPerProcessorLookasideList
0x1401349b9  test    rax, rax
0x1401349bc  jz      loc_140134A4A
0x1401349c2  mov     eax, gs:1A4h
0x1401349ca  mov     r8, cs:gIncomingValuesLookasideList
0x1401349d1  lea     ebx, [rax+1]
0x1401349d4  shl     rbx, 7
0x1401349d8  add     rbx, r8
0x1401349db  movzx   eax, byte ptr [rbx+0B0h]
0x1401349e2  test    al, al
0x1401349e4  jnz     short loc_1401349F2
0x1401349e6  lea     rdx, [rbx+40h]
0x1401349ea  mov     rcx, r8
0x1401349ed  call    PplpLazyInitializeLookasideList
0x1401349f2  mov     rdx, [rsp+170h+Entry]; Entry
0x1401349f7  lea     rcx, [rbx+40h]; Lookaside
0x1401349fb  call    cs:__imp_ExFreeToLookasideListEx
0x140134a02  nop     dword ptr [rax+rax+00h]
0x140134a07  mov     rbx, [rbp+70h+var_88]
0x140134a0b  test    r12b, r12b
0x140134a0e  jz      short loc_140134A19
0x140134a10  movzx   ecx, dil
0x140134a14  call    WfpLowerIrqlFromDispatchLevel
0x140134a19  mov     [rbx], esi
0x140134a1b  mov     al, 1
0x140134a1d  mov     r12, [rsp+170h+var_30]
0x140134a25  mov     r14, [rsp+170h+var_38]
0x140134a2d  mov     rcx, [rbp+70h+var_48]
0x140134a31  xor     rcx, rsp; StackCookie
0x140134a34  call    __security_check_cookie
0x140134a39  add     rsp, 148h
0x140134a40  pop     r15
0x140134a42  pop     r13
0x140134a44  pop     rdi
0x140134a45  pop     rsi
0x140134a46  pop     rbx
0x140134a47  pop     rbp
0x140134a48  retn
0x140134a4a  mov     rsi, [rsp+170h+Entry]
0x140134a4f  mov     rbx, [rsp+170h+var_F8]
0x140134a54  xor     edx, edx; Val
0x140134a56  mov     r8d, 2A0h; Size
0x140134a5c  mov     rcx, rsi; void *
0x140134a5f  call    memset
0x140134a64  xor     edx, edx; Val
0x140134a66  mov     r8d, 2A8h; Size
0x140134a6c  mov     rcx, rbx; void *
0x140134a6f  call    memset
0x140134a74  mov     rdi, [rbp+70h+var_F0]
0x140134a78  lea     rax, [rbx+270h]
0x140134a7f  movzx   edx, [rsp+170h+var_11E]
0x140134a84  mov     r9, r13
0x140134a87  mov     rcx, [rsp+170h+SpinLock]
0x140134a8c  mov     [rax+8], rax
0x140134a90  mov     [rax], rax
0x140134a93  movzx   eax, [rbp+70h+arg_50]
0x140134a9a  movzx   r8d, word ptr [r15+30h]
0x140134a9f  mov     [rsp+170h+var_130], rbx
0x140134aa4  mov     byte ptr [rsp+170h+var_138], al
0x140134aa8  movzx   eax, [rbp+70h+arg_48]
0x140134aaf  mov     byte ptr [rsp+170h+var_140], al
0x140134ab3  mov     eax, [rbp+70h+arg_40]
0x140134ab9  mov     dword ptr [rsp+170h+var_148], eax
0x140134abd  mov     [rsp+170h+var_150], rdi
0x140134ac2  call    TlShimSetDirectClassifyMetadata
0x140134ac7  mov     rcx, [rsp+170h+SpinLock]; SpinLock
0x140134acc  lea     rdx, [rbp+70h+P]
0x140134ad0  call    WfpAleCopySecurityRealmIdFromEndpoint
0x140134ad5  lea     eax, [r14-0Ch]
0x140134ad9  mov     ecx, 0FFFDh
0x140134ade  test    cx, ax
0x140134ae1  jz      short loc_140134B43
0x140134ae3  lea     eax, [r14-10h]
0x140134ae7  test    cx, ax
0x140134aea  jnz     loc_140134D04
0x140134af0  mov     rax, [rsp+170h+SpinLock]
0x140134af5  mov     qword ptr [rbp+70h+var_E8], rax
0x140134af9  movzx   eax, [rsp+170h+var_11E]
0x140134afe  mov     word ptr [rbp+70h+var_E8+8], ax
0x140134b02  mov     eax, [rsp+170h+var_108]
0x140134b06  mov     dword ptr [rbp+70h+var_E8+0Ch], eax
0x140134b09  movzx   eax, [rbp+70h+arg_20]
0x140134b10  mov     word ptr [rbp+70h+var_D8], ax
0x140134b14  movzx   eax, [rbp+70h+arg_28]
0x140134b1b  mov     word ptr [rbp+70h+var_D8+2], ax
0x140134b1f  mov     eax, [r15+28h]
0x140134b23  mov     dword ptr [rbp+70h+var_C8], eax
0x140134b26  xor     eax, eax
0x140134b28  cmp     [rdi+2Ch], al
0x140134b2b  mov     qword ptr [rbp+70h+var_D8+8], rdi
0x140134b2f  setnz   al
0x140134b32  mov     dword ptr [rbp+70h+var_C8+4], eax
0x140134b35  lea     rax, [rbp+70h+P]
0x140134b39  mov     qword ptr [rbp+70h+var_C8+8], rax
0x140134b3d  lea     rax, [rbp+70h+var_E8]
0x140134b41  jmp     short loc_140134B94
0x140134b43  mov     rax, [rsp+170h+SpinLock]
0x140134b48  mov     qword ptr [rbp+70h+var_B8], rax
0x140134b4c  movzx   eax, [rsp+170h+var_11E]
0x140134b51  mov     word ptr [rbp+70h+var_B8+8], ax
0x140134b55  mov     eax, [rsp+170h+var_108]
0x140134b59  mov     dword ptr [rbp+70h+var_B8+0Ch], eax
0x140134b5c  movzx   eax, [rbp+70h+arg_20]
0x140134b63  mov     word ptr [rbp+70h+var_A8], ax
0x140134b67  movzx   eax, [rbp+70h+arg_28]
0x140134b6e  mov     word ptr [rbp+70h+var_A8+2], ax
0x140134b72  mov     eax, [r15+28h]
0x140134b76  mov     dword ptr [rbp+70h+var_98], eax
0x140134b79  movzx   eax, byte ptr [r13+10h]
0x140134b7e  and     eax, 1
0x140134b81  mov     qword ptr [rbp+70h+var_A8+8], r13
0x140134b85  mov     dword ptr [rbp+70h+var_98+4], eax
0x140134b88  lea     rax, [rbp+70h+P]
0x140134b8c  mov     qword ptr [rbp+70h+var_98+8], rax
0x140134b90  lea     rax, [rbp+70h+var_B8]
0x140134b94  mov     [rbx+8], rax
0x140134b98  test    r13, r13
0x140134b9b  jz      short loc_140134BA3
0x140134b9d  mov     r9, [r13+8]
0x140134ba1  jmp     short loc_140134BA7
0x140134ba3  mov     r9, [rdi+30h]
0x140134ba7  mov     rdx, [r15+20h]
0x140134bab  lea     rax, [rbp+70h+var_70]
0x140134baf  mov     [rsp+170h+var_148], rax
0x140134bb4  mov     r8, rbx
0x140134bb7  lea     rax, [r15+10h]
0x140134bbb  movzx   ecx, r14w
0x140134bbf  mov     [rsp+170h+var_150], rax
0x140134bc4  call    cs:__imp_KfdDirectClassify
0x140134bcb  nop     dword ptr [rax+rax+00h]
0x140134bd0  test    al, al
0x140134bd2  jnz     loc_140134CAE
0x140134bd8  mov     eax, gs:1A4h
0x140134be0  lea     rcx, [rbx+270h]
0x140134be7  lea     rdx, [rax+rax*8]
0x140134beb  mov     rax, cs:gPerProcessorContext
0x140134bf2  lea     rdi, [rax+rdx*8]
0x140134bf6  call    cs:__imp_KfdReleaseTerminatingFilters
0x140134bfd  nop     dword ptr [rax+rax+00h]
0x140134c02  cmp     rsi, [rdi+18h]
0x140134c06  jnz     short loc_140134C11
0x140134c08  mov     byte ptr [rdi+20h], 0
0x140134c0c  jmp     loc_140134C97
0x140134c11  mov     eax, gs:1A4h
0x140134c19  mov     r8, cs:gMetadataLookasideList
0x140134c20  lea     edi, [rax+1]
0x140134c23  shl     rdi, 7
0x140134c27  add     rdi, r8
0x140134c2a  movzx   eax, byte ptr [rdi+0B0h]
0x140134c31  test    al, al
0x140134c33  jnz     short loc_140134C41
0x140134c35  lea     rdx, [rdi+40h]
0x140134c39  mov     rcx, r8
0x140134c3c  call    PplpLazyInitializeLookasideList
0x140134c41  mov     rdx, rbx; Entry
0x140134c44  lea     rcx, [rdi+40h]; Lookaside
0x140134c48  call    cs:__imp_ExFreeToLookasideListEx
0x140134c4f  nop     dword ptr [rax+rax+00h]
0x140134c54  mov     eax, gs:1A4h
0x140134c5c  mov     r8, cs:gIncomingValuesLookasideList
0x140134c63  lea     ebx, [rax+1]
0x140134c66  shl     rbx, 7
0x140134c6a  add     rbx, r8
0x140134c6d  movzx   eax, byte ptr [rbx+0B0h]
0x140134c74  test    al, al
0x140134c76  jnz     short loc_140134C84
0x140134c78  lea     rdx, [rbx+40h]
0x140134c7c  mov     rcx, r8
0x140134c7f  call    PplpLazyInitializeLookasideList
0x140134c84  mov     rdx, rsi; Entry
0x140134c87  lea     rcx, [rbx+40h]; Lookaside
0x140134c8b  call    cs:__imp_ExFreeToLookasideListEx
0x140134c92  nop     dword ptr [rax+rax+00h]
0x140134c97  test    r12b, r12b
0x140134c9a  jz      short loc_140134CA6
0x140134c9c  movzx   ecx, [rsp+170h+var_120]
0x140134ca1  call    WfpLowerIrqlFromDispatchLevel
0x140134ca6  xor     r15b, r15b
0x140134ca9  jmp     loc_140134F19
0x140134cae  cmp     dword ptr [rbp+70h+var_70], 1001h
0x140134cb5  jnz     loc_140134E40
0x140134cbb  test    byte ptr [rbp+70h+var_60+0Ch], 1
0x140134cbf  jz      short loc_140134CCB
0x140134cc1  mov     edi, 2
0x140134cc6  jmp     loc_140134E45
0x140134ccb  xor     eax, eax
0x140134ccd  mov     [rsp+170h+Entry], rax
0x140134cd2  mov     dword ptr [rsp+170h+var_110], eax
0x140134cd6  mov     word ptr [rsp+170h+var_110+4], ax
0x140134cdb  mov     rax, [r15+20h]
0x140134cdf  mov     [rsp+170h+var_F8], rax
0x140134ce4  test    rax, rax
0x140134ce7  jnz     loc_140134DA8
0x140134ced  lea     eax, [r14-0Ch]
0x140134cf1  mov     ecx, 0FFFDh
0x140134cf6  test    cx, ax
0x140134cf9  jz      short loc_140134D50
0x140134cfb  lea     eax, [r14-10h]
0x140134cff  test    cx, ax
0x140134d02  jz      short loc_140134D0B
0x140134d04  mov     ecx, 5
0x140134d09  int     29h; Win8: RtlFailFast(ecx)
0x140134d0b  mov     rax, qword ptr [rbp+70h+var_C8+8]
0x140134d0f  movzx   r9d, word ptr [rbp+70h+var_D8+2]
0x140134d14  movzx   r8d, word ptr [rbp+70h+var_D8]
0x140134d19  mov     edx, dword ptr [rbp+70h+var_E8+0Ch]
0x140134d1c  movzx   ecx, word ptr [rbp+70h+var_E8+8]
0x140134d20  mov     [rsp+170h+var_130], rsi
0x140134d25  mov     [rsp+170h+var_138], rax
0x140134d2a  mov     eax, dword ptr [rbp+70h+var_C8+4]
0x140134d2d  mov     [rsp+170h+var_140], eax
0x140134d31  mov     eax, dword ptr [rbp+70h+var_C8]
0x140134d34  mov     dword ptr [rsp+170h+var_148], eax
0x140134d38  mov     rax, qword ptr [rbp+70h+var_D8+8]
0x140134d3c  mov     [rsp+170h+var_150], rax
0x140134d41  call    TlShimMarshalOutTransportFields
0x140134d46  mov     dword ptr [rsp+170h+Entry+4], 10h
0x140134d4e  jmp     short loc_140134D93
0x140134d50  mov     rax, qword ptr [rbp+70h+var_98+8]
0x140134d54  movzx   r9d, word ptr [rbp+70h+var_A8+2]
0x140134d59  movzx   r8d, word ptr [rbp+70h+var_A8]
0x140134d5e  mov     edx, dword ptr [rbp+70h+var_B8+0Ch]
0x140134d61  movzx   ecx, word ptr [rbp+70h+var_B8+8]
0x140134d65  mov     [rsp+170h+var_130], rsi
0x140134d6a  mov     [rsp+170h+var_138], rax
0x140134d6f  mov     eax, dword ptr [rbp+70h+var_98+4]
0x140134d72  mov     [rsp+170h+var_140], eax
  ... truncated ...
```
