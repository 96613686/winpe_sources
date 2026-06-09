# TlShimDirectClassify

- ea: `0x140134740`
- end: `0x140134dfc`
- name: `TlShimDirectClassify`
- size: `1724`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004e2f0`
- `0x1400509f4`
- `0x1400527a0`
- `0x1400974c0`

## callees

- `0x14004c7d0`
- `0x14004d6e0`
- `0x14004d860`
- `0x1400504b0`
- `0x1400515e8`
- `0x140053850`
- `0x140053910`
- `0x140053e04`
- `0x140134740`
- `0x140134e04`
- `0x1401bf390`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401348bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134b08`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134b4b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134d78`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134db8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401348bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134b08`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134b4b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134d78`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140134db8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401347f8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401347f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140134de7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140134de7`
- `NETIO!KfdDirectClassify` at `0x140134a84`
- `NETIO!KfdDirectClassify` at `0x140134a84`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140134ab6`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140134d26`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140134ab6`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140134d26`

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
0x140134740  push    rbp
0x140134742  push    rbx
0x140134743  push    rsi
0x140134744  push    rdi
0x140134745  push    r13
0x140134747  push    r15
0x140134749  lea     rbp, [rsp-48h]
0x14013474e  sub     rsp, 148h
0x140134755  mov     rax, cs:__security_cookie
0x14013475c  xor     rax, rsp
0x14013475f  mov     [rbp+70h+var_48], rax
0x140134763  mov     rax, [rbp+70h+arg_38]
0x14013476a  xorps   xmm0, xmm0
0x14013476d  mov     rbx, [rbp+70h+arg_58]
0x140134774  xor     esi, esi
0x140134776  mov     r13, [rbp+70h+arg_30]
0x14013477d  xorps   xmm1, xmm1
0x140134780  mov     [rbp+70h+var_F0], rax
0x140134784  mov     r15, r8
0x140134787  xor     eax, eax
0x140134789  mov     [rsp+170h+var_108], r9d
0x14013478e  mov     [rbp+70h+var_50], eax
0x140134791  lea     rax, [r8+10h]
0x140134795  mov     [rsp+170h+var_11E], dx
0x14013479a  mov     [rsp+170h+SpinLock], rcx
0x14013479f  mov     [rbp+70h+var_88], rbx
0x1401347a3  movups  [rbp+70h+var_B8], xmm0
0x1401347a7  mov     [rsp+170h+Entry], rsi
0x1401347ac  movups  [rbp+70h+var_A8], xmm0
0x1401347b0  mov     [rsp+170h+var_F8], rsi
0x1401347b5  movups  [rbp+70h+var_98], xmm0
0x1401347b9  movups  [rbp+70h+var_E8], xmm1
0x1401347bd  movups  [rbp+70h+var_D8], xmm1
0x1401347c1  movups  [rbp+70h+var_C8], xmm1
0x1401347c5  movups  [rbp+70h+var_70], xmm0
0x1401347c9  movups  [rbp+70h+var_60], xmm0
0x1401347cd  movups  xmmword ptr [rbp+70h+P], xmm0
0x1401347d1  cmp     [rax], rax
0x1401347d4  jnz     short loc_1401347E3
0x1401347d6  mov     dword ptr [rbx], 1
0x1401347dc  mov     al, 1
0x1401347de  jmp     loc_1401348ED
0x1401347e3  mov     [rsp+170h+var_30], r12
0x1401347eb  mov     [rsp+170h+var_38], r14
0x1401347f3  movzx   r14d, word ptr [r8+30h]
0x1401347f8  call    cs:__imp_KeGetCurrentIrql
0x1401347ff  nop     dword ptr [rax+rax+00h]
0x140134804  cmp     al, 2
0x140134806  jnb     short loc_140134819
0x140134808  call    WfpRaiseIrqlToDispatchLevel
0x14013480d  movzx   edi, al
0x140134810  mov     [rsp+170h+var_120], al
0x140134814  mov     r12b, 1
0x140134817  jmp     short loc_140134824
0x140134819  xor     dil, dil
0x14013481c  mov     [rsp+170h+var_120], dil
0x140134821  xor     r12b, r12b
0x140134824  mov     eax, gs:1A4h
0x14013482c  lea     rdx, [rax+rax*8]
0x140134830  mov     rax, cs:gPerProcessorContext
0x140134837  cmp     [rax+rdx*8+20h], sil
0x14013483c  jnz     short loc_140134852
0x14013483e  mov     rsi, [rax+rdx*8+18h]
0x140134843  mov     rbx, [rax+rdx*8+10h]
0x140134848  mov     byte ptr [rax+rdx*8+20h], 1
0x14013484d  jmp     loc_140134914
0x140134852  mov     rcx, cs:gIncomingValuesLookasideList
0x140134859  lea     rdx, [rsp+170h+Entry]
0x14013485e  call    WfpAllocateFromPerProcessorLookasideList
0x140134863  test    rax, rax
0x140134866  jnz     short loc_1401348CB
0x140134868  mov     rcx, cs:gMetadataLookasideList
0x14013486f  lea     rdx, [rsp+170h+var_F8]
0x140134874  call    WfpAllocateFromPerProcessorLookasideList
0x140134879  test    rax, rax
0x14013487c  jz      loc_14013490A
0x140134882  mov     eax, gs:1A4h
0x14013488a  mov     r8, cs:gIncomingValuesLookasideList
0x140134891  lea     ebx, [rax+1]
0x140134894  shl     rbx, 7
0x140134898  add     rbx, r8
0x14013489b  movzx   eax, byte ptr [rbx+0B0h]
0x1401348a2  test    al, al
0x1401348a4  jnz     short loc_1401348B2
0x1401348a6  lea     rdx, [rbx+40h]
0x1401348aa  mov     rcx, r8
0x1401348ad  call    PplpLazyInitializeLookasideList
0x1401348b2  mov     rdx, [rsp+170h+Entry]; Entry
0x1401348b7  lea     rcx, [rbx+40h]; Lookaside
0x1401348bb  call    cs:__imp_ExFreeToLookasideListEx
0x1401348c2  nop     dword ptr [rax+rax+00h]
0x1401348c7  mov     rbx, [rbp+70h+var_88]
0x1401348cb  test    r12b, r12b
0x1401348ce  jz      short loc_1401348D9
0x1401348d0  movzx   ecx, dil
0x1401348d4  call    WfpLowerIrqlFromDispatchLevel
0x1401348d9  mov     [rbx], esi
0x1401348db  mov     al, 1
0x1401348dd  mov     r12, [rsp+170h+var_30]
0x1401348e5  mov     r14, [rsp+170h+var_38]
0x1401348ed  mov     rcx, [rbp+70h+var_48]
0x1401348f1  xor     rcx, rsp; StackCookie
0x1401348f4  call    __security_check_cookie
0x1401348f9  add     rsp, 148h
0x140134900  pop     r15
0x140134902  pop     r13
0x140134904  pop     rdi
0x140134905  pop     rsi
0x140134906  pop     rbx
0x140134907  pop     rbp
0x140134908  retn
0x14013490a  mov     rsi, [rsp+170h+Entry]
0x14013490f  mov     rbx, [rsp+170h+var_F8]
0x140134914  xor     edx, edx; Val
0x140134916  mov     r8d, 2A0h; Size
0x14013491c  mov     rcx, rsi; void *
0x14013491f  call    memset
0x140134924  xor     edx, edx; Val
0x140134926  mov     r8d, 2A8h; Size
0x14013492c  mov     rcx, rbx; void *
0x14013492f  call    memset
0x140134934  mov     rdi, [rbp+70h+var_F0]
0x140134938  lea     rax, [rbx+270h]
0x14013493f  movzx   edx, [rsp+170h+var_11E]
0x140134944  mov     r9, r13
0x140134947  mov     rcx, [rsp+170h+SpinLock]
0x14013494c  mov     [rax+8], rax
0x140134950  mov     [rax], rax
0x140134953  movzx   eax, [rbp+70h+arg_50]
0x14013495a  movzx   r8d, word ptr [r15+30h]
0x14013495f  mov     [rsp+170h+var_130], rbx
0x140134964  mov     byte ptr [rsp+170h+var_138], al
0x140134968  movzx   eax, [rbp+70h+arg_48]
0x14013496f  mov     byte ptr [rsp+170h+var_140], al
0x140134973  mov     eax, [rbp+70h+arg_40]
0x140134979  mov     dword ptr [rsp+170h+var_148], eax
0x14013497d  mov     [rsp+170h+var_150], rdi
0x140134982  call    TlShimSetDirectClassifyMetadata
0x140134987  mov     rcx, [rsp+170h+SpinLock]; SpinLock
0x14013498c  lea     rdx, [rbp+70h+P]
0x140134990  call    WfpAleCopySecurityRealmIdFromEndpoint
0x140134995  lea     eax, [r14-0Ch]
0x140134999  mov     ecx, 0FFFDh
0x14013499e  test    cx, ax
0x1401349a1  jz      short loc_140134A03
0x1401349a3  lea     eax, [r14-10h]
0x1401349a7  test    cx, ax
0x1401349aa  jnz     loc_140134BC4
0x1401349b0  mov     rax, [rsp+170h+SpinLock]
0x1401349b5  mov     qword ptr [rbp+70h+var_E8], rax
0x1401349b9  movzx   eax, [rsp+170h+var_11E]
0x1401349be  mov     word ptr [rbp+70h+var_E8+8], ax
0x1401349c2  mov     eax, [rsp+170h+var_108]
0x1401349c6  mov     dword ptr [rbp+70h+var_E8+0Ch], eax
0x1401349c9  movzx   eax, [rbp+70h+arg_20]
0x1401349d0  mov     word ptr [rbp+70h+var_D8], ax
0x1401349d4  movzx   eax, [rbp+70h+arg_28]
0x1401349db  mov     word ptr [rbp+70h+var_D8+2], ax
0x1401349df  mov     eax, [r15+28h]
0x1401349e3  mov     dword ptr [rbp+70h+var_C8], eax
0x1401349e6  xor     eax, eax
0x1401349e8  cmp     [rdi+2Ch], al
0x1401349eb  mov     qword ptr [rbp+70h+var_D8+8], rdi
0x1401349ef  setnz   al
0x1401349f2  mov     dword ptr [rbp+70h+var_C8+4], eax
0x1401349f5  lea     rax, [rbp+70h+P]
0x1401349f9  mov     qword ptr [rbp+70h+var_C8+8], rax
0x1401349fd  lea     rax, [rbp+70h+var_E8]
0x140134a01  jmp     short loc_140134A54
0x140134a03  mov     rax, [rsp+170h+SpinLock]
0x140134a08  mov     qword ptr [rbp+70h+var_B8], rax
0x140134a0c  movzx   eax, [rsp+170h+var_11E]
0x140134a11  mov     word ptr [rbp+70h+var_B8+8], ax
0x140134a15  mov     eax, [rsp+170h+var_108]
0x140134a19  mov     dword ptr [rbp+70h+var_B8+0Ch], eax
0x140134a1c  movzx   eax, [rbp+70h+arg_20]
0x140134a23  mov     word ptr [rbp+70h+var_A8], ax
0x140134a27  movzx   eax, [rbp+70h+arg_28]
0x140134a2e  mov     word ptr [rbp+70h+var_A8+2], ax
0x140134a32  mov     eax, [r15+28h]
0x140134a36  mov     dword ptr [rbp+70h+var_98], eax
0x140134a39  movzx   eax, byte ptr [r13+10h]
0x140134a3e  and     eax, 1
0x140134a41  mov     qword ptr [rbp+70h+var_A8+8], r13
0x140134a45  mov     dword ptr [rbp+70h+var_98+4], eax
0x140134a48  lea     rax, [rbp+70h+P]
0x140134a4c  mov     qword ptr [rbp+70h+var_98+8], rax
0x140134a50  lea     rax, [rbp+70h+var_B8]
0x140134a54  mov     [rbx+8], rax
0x140134a58  test    r13, r13
0x140134a5b  jz      short loc_140134A63
0x140134a5d  mov     r9, [r13+8]
0x140134a61  jmp     short loc_140134A67
0x140134a63  mov     r9, [rdi+30h]
0x140134a67  mov     rdx, [r15+20h]
0x140134a6b  lea     rax, [rbp+70h+var_70]
0x140134a6f  mov     [rsp+170h+var_148], rax
0x140134a74  mov     r8, rbx
0x140134a77  lea     rax, [r15+10h]
0x140134a7b  movzx   ecx, r14w
0x140134a7f  mov     [rsp+170h+var_150], rax
0x140134a84  call    cs:__imp_KfdDirectClassify
0x140134a8b  nop     dword ptr [rax+rax+00h]
0x140134a90  test    al, al
0x140134a92  jnz     loc_140134B6E
0x140134a98  mov     eax, gs:1A4h
0x140134aa0  lea     rcx, [rbx+270h]
0x140134aa7  lea     rdx, [rax+rax*8]
0x140134aab  mov     rax, cs:gPerProcessorContext
0x140134ab2  lea     rdi, [rax+rdx*8]
0x140134ab6  call    cs:__imp_KfdReleaseTerminatingFilters
0x140134abd  nop     dword ptr [rax+rax+00h]
0x140134ac2  cmp     rsi, [rdi+18h]
0x140134ac6  jnz     short loc_140134AD1
0x140134ac8  mov     byte ptr [rdi+20h], 0
0x140134acc  jmp     loc_140134B57
0x140134ad1  mov     eax, gs:1A4h
0x140134ad9  mov     r8, cs:gMetadataLookasideList
0x140134ae0  lea     edi, [rax+1]
0x140134ae3  shl     rdi, 7
0x140134ae7  add     rdi, r8
0x140134aea  movzx   eax, byte ptr [rdi+0B0h]
0x140134af1  test    al, al
0x140134af3  jnz     short loc_140134B01
0x140134af5  lea     rdx, [rdi+40h]
0x140134af9  mov     rcx, r8
0x140134afc  call    PplpLazyInitializeLookasideList
0x140134b01  mov     rdx, rbx; Entry
0x140134b04  lea     rcx, [rdi+40h]; Lookaside
0x140134b08  call    cs:__imp_ExFreeToLookasideListEx
0x140134b0f  nop     dword ptr [rax+rax+00h]
0x140134b14  mov     eax, gs:1A4h
0x140134b1c  mov     r8, cs:gIncomingValuesLookasideList
0x140134b23  lea     ebx, [rax+1]
0x140134b26  shl     rbx, 7
0x140134b2a  add     rbx, r8
0x140134b2d  movzx   eax, byte ptr [rbx+0B0h]
0x140134b34  test    al, al
0x140134b36  jnz     short loc_140134B44
0x140134b38  lea     rdx, [rbx+40h]
0x140134b3c  mov     rcx, r8
0x140134b3f  call    PplpLazyInitializeLookasideList
0x140134b44  mov     rdx, rsi; Entry
0x140134b47  lea     rcx, [rbx+40h]; Lookaside
0x140134b4b  call    cs:__imp_ExFreeToLookasideListEx
0x140134b52  nop     dword ptr [rax+rax+00h]
0x140134b57  test    r12b, r12b
0x140134b5a  jz      short loc_140134B66
0x140134b5c  movzx   ecx, [rsp+170h+var_120]
0x140134b61  call    WfpLowerIrqlFromDispatchLevel
0x140134b66  xor     r15b, r15b
0x140134b69  jmp     loc_140134DD9
0x140134b6e  cmp     dword ptr [rbp+70h+var_70], 1001h
0x140134b75  jnz     loc_140134D00
0x140134b7b  test    byte ptr [rbp+70h+var_60+0Ch], 1
0x140134b7f  jz      short loc_140134B8B
0x140134b81  mov     edi, 2
0x140134b86  jmp     loc_140134D05
0x140134b8b  xor     eax, eax
0x140134b8d  mov     [rsp+170h+Entry], rax
0x140134b92  mov     dword ptr [rsp+170h+var_110], eax
0x140134b96  mov     word ptr [rsp+170h+var_110+4], ax
0x140134b9b  mov     rax, [r15+20h]
0x140134b9f  mov     [rsp+170h+var_F8], rax
0x140134ba4  test    rax, rax
0x140134ba7  jnz     loc_140134C68
0x140134bad  lea     eax, [r14-0Ch]
0x140134bb1  mov     ecx, 0FFFDh
0x140134bb6  test    cx, ax
0x140134bb9  jz      short loc_140134C10
0x140134bbb  lea     eax, [r14-10h]
0x140134bbf  test    cx, ax
0x140134bc2  jz      short loc_140134BCB
0x140134bc4  mov     ecx, 5
0x140134bc9  int     29h; Win8: RtlFailFast(ecx)
0x140134bcb  mov     rax, qword ptr [rbp+70h+var_C8+8]
0x140134bcf  movzx   r9d, word ptr [rbp+70h+var_D8+2]
0x140134bd4  movzx   r8d, word ptr [rbp+70h+var_D8]
0x140134bd9  mov     edx, dword ptr [rbp+70h+var_E8+0Ch]
0x140134bdc  movzx   ecx, word ptr [rbp+70h+var_E8+8]
0x140134be0  mov     [rsp+170h+var_130], rsi
0x140134be5  mov     [rsp+170h+var_138], rax
0x140134bea  mov     eax, dword ptr [rbp+70h+var_C8+4]
0x140134bed  mov     [rsp+170h+var_140], eax
0x140134bf1  mov     eax, dword ptr [rbp+70h+var_C8]
0x140134bf4  mov     dword ptr [rsp+170h+var_148], eax
0x140134bf8  mov     rax, qword ptr [rbp+70h+var_D8+8]
0x140134bfc  mov     [rsp+170h+var_150], rax
0x140134c01  call    TlShimMarshalOutTransportFields
0x140134c06  mov     dword ptr [rsp+170h+Entry+4], 10h
0x140134c0e  jmp     short loc_140134C53
0x140134c10  mov     rax, qword ptr [rbp+70h+var_98+8]
0x140134c14  movzx   r9d, word ptr [rbp+70h+var_A8+2]
0x140134c19  movzx   r8d, word ptr [rbp+70h+var_A8]
0x140134c1e  mov     edx, dword ptr [rbp+70h+var_B8+0Ch]
0x140134c21  movzx   ecx, word ptr [rbp+70h+var_B8+8]
0x140134c25  mov     [rsp+170h+var_130], rsi
0x140134c2a  mov     [rsp+170h+var_138], rax
0x140134c2f  mov     eax, dword ptr [rbp+70h+var_98+4]
0x140134c32  mov     [rsp+170h+var_140], eax
  ... truncated ...
```
