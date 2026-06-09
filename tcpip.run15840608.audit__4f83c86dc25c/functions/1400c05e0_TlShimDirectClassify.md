# TlShimDirectClassify

- ea: `0x1400c05e0`
- end: `0x1400c0c9c`
- name: `TlShimDirectClassify`
- size: `1724`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140011568`
- `0x140013310`
- `0x14005e2b0`
- `0x1400be9e0`

## callees

- `0x140011220`
- `0x14001215c`
- `0x1400143c0`
- `0x140014480`
- `0x140014974`
- `0x1400bf390`
- `0x1400bf510`
- `0x1400bf840`
- `0x1400c05e0`
- `0x14013a1ec`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c075b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c09a8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c09eb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c0c18`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c0c58`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c075b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c09a8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c09eb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c0c18`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c0c58`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c0698`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c0698`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0c87`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0c87`
- `NETIO!KfdDirectClassify` at `0x1400c0924`
- `NETIO!KfdDirectClassify` at `0x1400c0924`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400c0956`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400c0bc6`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400c0956`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400c0bc6`

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
0x1400c05e0  push    rbp
0x1400c05e2  push    rbx
0x1400c05e3  push    rsi
0x1400c05e4  push    rdi
0x1400c05e5  push    r13
0x1400c05e7  push    r15
0x1400c05e9  lea     rbp, [rsp-48h]
0x1400c05ee  sub     rsp, 148h
0x1400c05f5  mov     rax, cs:__security_cookie
0x1400c05fc  xor     rax, rsp
0x1400c05ff  mov     [rbp+70h+var_48], rax
0x1400c0603  mov     rax, [rbp+70h+arg_38]
0x1400c060a  xorps   xmm0, xmm0
0x1400c060d  mov     rbx, [rbp+70h+arg_58]
0x1400c0614  xor     esi, esi
0x1400c0616  mov     r13, [rbp+70h+arg_30]
0x1400c061d  xorps   xmm1, xmm1
0x1400c0620  mov     [rbp+70h+var_F0], rax
0x1400c0624  mov     r15, r8
0x1400c0627  xor     eax, eax
0x1400c0629  mov     [rsp+170h+var_108], r9d
0x1400c062e  mov     [rbp+70h+var_50], eax
0x1400c0631  lea     rax, [r8+10h]
0x1400c0635  mov     [rsp+170h+var_11E], dx
0x1400c063a  mov     [rsp+170h+SpinLock], rcx
0x1400c063f  mov     [rbp+70h+var_88], rbx
0x1400c0643  movups  [rbp+70h+var_B8], xmm0
0x1400c0647  mov     [rsp+170h+Entry], rsi
0x1400c064c  movups  [rbp+70h+var_A8], xmm0
0x1400c0650  mov     [rsp+170h+var_F8], rsi
0x1400c0655  movups  [rbp+70h+var_98], xmm0
0x1400c0659  movups  [rbp+70h+var_E8], xmm1
0x1400c065d  movups  [rbp+70h+var_D8], xmm1
0x1400c0661  movups  [rbp+70h+var_C8], xmm1
0x1400c0665  movups  [rbp+70h+var_70], xmm0
0x1400c0669  movups  [rbp+70h+var_60], xmm0
0x1400c066d  movups  xmmword ptr [rbp+70h+P], xmm0
0x1400c0671  cmp     [rax], rax
0x1400c0674  jnz     short loc_1400C0683
0x1400c0676  mov     dword ptr [rbx], 1
0x1400c067c  mov     al, 1
0x1400c067e  jmp     loc_1400C078D
0x1400c0683  mov     [rsp+170h+var_30], r12
0x1400c068b  mov     [rsp+170h+var_38], r14
0x1400c0693  movzx   r14d, word ptr [r8+30h]
0x1400c0698  call    cs:__imp_KeGetCurrentIrql
0x1400c069f  nop     dword ptr [rax+rax+00h]
0x1400c06a4  cmp     al, 2
0x1400c06a6  jnb     short loc_1400C06B9
0x1400c06a8  call    WfpRaiseIrqlToDispatchLevel
0x1400c06ad  movzx   edi, al
0x1400c06b0  mov     [rsp+170h+var_120], al
0x1400c06b4  mov     r12b, 1
0x1400c06b7  jmp     short loc_1400C06C4
0x1400c06b9  xor     dil, dil
0x1400c06bc  mov     [rsp+170h+var_120], dil
0x1400c06c1  xor     r12b, r12b
0x1400c06c4  mov     eax, gs:1A4h
0x1400c06cc  lea     rdx, [rax+rax*8]
0x1400c06d0  mov     rax, cs:gPerProcessorContext
0x1400c06d7  cmp     [rax+rdx*8+20h], sil
0x1400c06dc  jnz     short loc_1400C06F2
0x1400c06de  mov     rsi, [rax+rdx*8+18h]
0x1400c06e3  mov     rbx, [rax+rdx*8+10h]
0x1400c06e8  mov     byte ptr [rax+rdx*8+20h], 1
0x1400c06ed  jmp     loc_1400C07B4
0x1400c06f2  mov     rcx, cs:gIncomingValuesLookasideList
0x1400c06f9  lea     rdx, [rsp+170h+Entry]
0x1400c06fe  call    WfpAllocateFromPerProcessorLookasideList
0x1400c0703  test    rax, rax
0x1400c0706  jnz     short loc_1400C076B
0x1400c0708  mov     rcx, cs:gMetadataLookasideList
0x1400c070f  lea     rdx, [rsp+170h+var_F8]
0x1400c0714  call    WfpAllocateFromPerProcessorLookasideList
0x1400c0719  test    rax, rax
0x1400c071c  jz      loc_1400C07AA
0x1400c0722  mov     eax, gs:1A4h
0x1400c072a  mov     r8, cs:gIncomingValuesLookasideList
0x1400c0731  lea     ebx, [rax+1]
0x1400c0734  shl     rbx, 7
0x1400c0738  add     rbx, r8
0x1400c073b  movzx   eax, byte ptr [rbx+0B0h]
0x1400c0742  test    al, al
0x1400c0744  jnz     short loc_1400C0752
0x1400c0746  lea     rdx, [rbx+40h]
0x1400c074a  mov     rcx, r8
0x1400c074d  call    PplpLazyInitializeLookasideList
0x1400c0752  mov     rdx, [rsp+170h+Entry]; Entry
0x1400c0757  lea     rcx, [rbx+40h]; Lookaside
0x1400c075b  call    cs:__imp_ExFreeToLookasideListEx
0x1400c0762  nop     dword ptr [rax+rax+00h]
0x1400c0767  mov     rbx, [rbp+70h+var_88]
0x1400c076b  test    r12b, r12b
0x1400c076e  jz      short loc_1400C0779
0x1400c0770  movzx   ecx, dil
0x1400c0774  call    WfpLowerIrqlFromDispatchLevel
0x1400c0779  mov     [rbx], esi
0x1400c077b  mov     al, 1
0x1400c077d  mov     r12, [rsp+170h+var_30]
0x1400c0785  mov     r14, [rsp+170h+var_38]
0x1400c078d  mov     rcx, [rbp+70h+var_48]
0x1400c0791  xor     rcx, rsp; StackCookie
0x1400c0794  call    __security_check_cookie
0x1400c0799  add     rsp, 148h
0x1400c07a0  pop     r15
0x1400c07a2  pop     r13
0x1400c07a4  pop     rdi
0x1400c07a5  pop     rsi
0x1400c07a6  pop     rbx
0x1400c07a7  pop     rbp
0x1400c07a8  retn
0x1400c07aa  mov     rsi, [rsp+170h+Entry]
0x1400c07af  mov     rbx, [rsp+170h+var_F8]
0x1400c07b4  xor     edx, edx; Val
0x1400c07b6  mov     r8d, 2A0h; Size
0x1400c07bc  mov     rcx, rsi; void *
0x1400c07bf  call    memset
0x1400c07c4  xor     edx, edx; Val
0x1400c07c6  mov     r8d, 2A8h; Size
0x1400c07cc  mov     rcx, rbx; void *
0x1400c07cf  call    memset
0x1400c07d4  mov     rdi, [rbp+70h+var_F0]
0x1400c07d8  lea     rax, [rbx+270h]
0x1400c07df  movzx   edx, [rsp+170h+var_11E]
0x1400c07e4  mov     r9, r13
0x1400c07e7  mov     rcx, [rsp+170h+SpinLock]
0x1400c07ec  mov     [rax+8], rax
0x1400c07f0  mov     [rax], rax
0x1400c07f3  movzx   eax, [rbp+70h+arg_50]
0x1400c07fa  movzx   r8d, word ptr [r15+30h]
0x1400c07ff  mov     [rsp+170h+var_130], rbx
0x1400c0804  mov     byte ptr [rsp+170h+var_138], al
0x1400c0808  movzx   eax, [rbp+70h+arg_48]
0x1400c080f  mov     byte ptr [rsp+170h+var_140], al
0x1400c0813  mov     eax, [rbp+70h+arg_40]
0x1400c0819  mov     dword ptr [rsp+170h+var_148], eax
0x1400c081d  mov     [rsp+170h+var_150], rdi
0x1400c0822  call    TlShimSetDirectClassifyMetadata
0x1400c0827  mov     rcx, [rsp+170h+SpinLock]; SpinLock
0x1400c082c  lea     rdx, [rbp+70h+P]
0x1400c0830  call    WfpAleCopySecurityRealmIdFromEndpoint
0x1400c0835  lea     eax, [r14-0Ch]
0x1400c0839  mov     ecx, 0FFFDh
0x1400c083e  test    cx, ax
0x1400c0841  jz      short loc_1400C08A3
0x1400c0843  lea     eax, [r14-10h]
0x1400c0847  test    cx, ax
0x1400c084a  jnz     loc_1400C0A64
0x1400c0850  mov     rax, [rsp+170h+SpinLock]
0x1400c0855  mov     qword ptr [rbp+70h+var_E8], rax
0x1400c0859  movzx   eax, [rsp+170h+var_11E]
0x1400c085e  mov     word ptr [rbp+70h+var_E8+8], ax
0x1400c0862  mov     eax, [rsp+170h+var_108]
0x1400c0866  mov     dword ptr [rbp+70h+var_E8+0Ch], eax
0x1400c0869  movzx   eax, [rbp+70h+arg_20]
0x1400c0870  mov     word ptr [rbp+70h+var_D8], ax
0x1400c0874  movzx   eax, [rbp+70h+arg_28]
0x1400c087b  mov     word ptr [rbp+70h+var_D8+2], ax
0x1400c087f  mov     eax, [r15+28h]
0x1400c0883  mov     dword ptr [rbp+70h+var_C8], eax
0x1400c0886  xor     eax, eax
0x1400c0888  cmp     [rdi+2Ch], al
0x1400c088b  mov     qword ptr [rbp+70h+var_D8+8], rdi
0x1400c088f  setnz   al
0x1400c0892  mov     dword ptr [rbp+70h+var_C8+4], eax
0x1400c0895  lea     rax, [rbp+70h+P]
0x1400c0899  mov     qword ptr [rbp+70h+var_C8+8], rax
0x1400c089d  lea     rax, [rbp+70h+var_E8]
0x1400c08a1  jmp     short loc_1400C08F4
0x1400c08a3  mov     rax, [rsp+170h+SpinLock]
0x1400c08a8  mov     qword ptr [rbp+70h+var_B8], rax
0x1400c08ac  movzx   eax, [rsp+170h+var_11E]
0x1400c08b1  mov     word ptr [rbp+70h+var_B8+8], ax
0x1400c08b5  mov     eax, [rsp+170h+var_108]
0x1400c08b9  mov     dword ptr [rbp+70h+var_B8+0Ch], eax
0x1400c08bc  movzx   eax, [rbp+70h+arg_20]
0x1400c08c3  mov     word ptr [rbp+70h+var_A8], ax
0x1400c08c7  movzx   eax, [rbp+70h+arg_28]
0x1400c08ce  mov     word ptr [rbp+70h+var_A8+2], ax
0x1400c08d2  mov     eax, [r15+28h]
0x1400c08d6  mov     dword ptr [rbp+70h+var_98], eax
0x1400c08d9  movzx   eax, byte ptr [r13+10h]
0x1400c08de  and     eax, 1
0x1400c08e1  mov     qword ptr [rbp+70h+var_A8+8], r13
0x1400c08e5  mov     dword ptr [rbp+70h+var_98+4], eax
0x1400c08e8  lea     rax, [rbp+70h+P]
0x1400c08ec  mov     qword ptr [rbp+70h+var_98+8], rax
0x1400c08f0  lea     rax, [rbp+70h+var_B8]
0x1400c08f4  mov     [rbx+8], rax
0x1400c08f8  test    r13, r13
0x1400c08fb  jz      short loc_1400C0903
0x1400c08fd  mov     r9, [r13+8]
0x1400c0901  jmp     short loc_1400C0907
0x1400c0903  mov     r9, [rdi+30h]
0x1400c0907  mov     rdx, [r15+20h]
0x1400c090b  lea     rax, [rbp+70h+var_70]
0x1400c090f  mov     [rsp+170h+var_148], rax
0x1400c0914  mov     r8, rbx
0x1400c0917  lea     rax, [r15+10h]
0x1400c091b  movzx   ecx, r14w
0x1400c091f  mov     [rsp+170h+var_150], rax
0x1400c0924  call    cs:__imp_KfdDirectClassify
0x1400c092b  nop     dword ptr [rax+rax+00h]
0x1400c0930  test    al, al
0x1400c0932  jnz     loc_1400C0A0E
0x1400c0938  mov     eax, gs:1A4h
0x1400c0940  lea     rcx, [rbx+270h]
0x1400c0947  lea     rdx, [rax+rax*8]
0x1400c094b  mov     rax, cs:gPerProcessorContext
0x1400c0952  lea     rdi, [rax+rdx*8]
0x1400c0956  call    cs:__imp_KfdReleaseTerminatingFilters
0x1400c095d  nop     dword ptr [rax+rax+00h]
0x1400c0962  cmp     rsi, [rdi+18h]
0x1400c0966  jnz     short loc_1400C0971
0x1400c0968  mov     byte ptr [rdi+20h], 0
0x1400c096c  jmp     loc_1400C09F7
0x1400c0971  mov     eax, gs:1A4h
0x1400c0979  mov     r8, cs:gMetadataLookasideList
0x1400c0980  lea     edi, [rax+1]
0x1400c0983  shl     rdi, 7
0x1400c0987  add     rdi, r8
0x1400c098a  movzx   eax, byte ptr [rdi+0B0h]
0x1400c0991  test    al, al
0x1400c0993  jnz     short loc_1400C09A1
0x1400c0995  lea     rdx, [rdi+40h]
0x1400c0999  mov     rcx, r8
0x1400c099c  call    PplpLazyInitializeLookasideList
0x1400c09a1  mov     rdx, rbx; Entry
0x1400c09a4  lea     rcx, [rdi+40h]; Lookaside
0x1400c09a8  call    cs:__imp_ExFreeToLookasideListEx
0x1400c09af  nop     dword ptr [rax+rax+00h]
0x1400c09b4  mov     eax, gs:1A4h
0x1400c09bc  mov     r8, cs:gIncomingValuesLookasideList
0x1400c09c3  lea     ebx, [rax+1]
0x1400c09c6  shl     rbx, 7
0x1400c09ca  add     rbx, r8
0x1400c09cd  movzx   eax, byte ptr [rbx+0B0h]
0x1400c09d4  test    al, al
0x1400c09d6  jnz     short loc_1400C09E4
0x1400c09d8  lea     rdx, [rbx+40h]
0x1400c09dc  mov     rcx, r8
0x1400c09df  call    PplpLazyInitializeLookasideList
0x1400c09e4  mov     rdx, rsi; Entry
0x1400c09e7  lea     rcx, [rbx+40h]; Lookaside
0x1400c09eb  call    cs:__imp_ExFreeToLookasideListEx
0x1400c09f2  nop     dword ptr [rax+rax+00h]
0x1400c09f7  test    r12b, r12b
0x1400c09fa  jz      short loc_1400C0A06
0x1400c09fc  movzx   ecx, [rsp+170h+var_120]
0x1400c0a01  call    WfpLowerIrqlFromDispatchLevel
0x1400c0a06  xor     r15b, r15b
0x1400c0a09  jmp     loc_1400C0C79
0x1400c0a0e  cmp     dword ptr [rbp+70h+var_70], 1001h
0x1400c0a15  jnz     loc_1400C0BA0
0x1400c0a1b  test    byte ptr [rbp+70h+var_60+0Ch], 1
0x1400c0a1f  jz      short loc_1400C0A2B
0x1400c0a21  mov     edi, 2
0x1400c0a26  jmp     loc_1400C0BA5
0x1400c0a2b  xor     eax, eax
0x1400c0a2d  mov     [rsp+170h+Entry], rax
0x1400c0a32  mov     dword ptr [rsp+170h+var_110], eax
0x1400c0a36  mov     word ptr [rsp+170h+var_110+4], ax
0x1400c0a3b  mov     rax, [r15+20h]
0x1400c0a3f  mov     [rsp+170h+var_F8], rax
0x1400c0a44  test    rax, rax
0x1400c0a47  jnz     loc_1400C0B08
0x1400c0a4d  lea     eax, [r14-0Ch]
0x1400c0a51  mov     ecx, 0FFFDh
0x1400c0a56  test    cx, ax
0x1400c0a59  jz      short loc_1400C0AB0
0x1400c0a5b  lea     eax, [r14-10h]
0x1400c0a5f  test    cx, ax
0x1400c0a62  jz      short loc_1400C0A6B
0x1400c0a64  mov     ecx, 5
0x1400c0a69  int     29h; Win8: RtlFailFast(ecx)
0x1400c0a6b  mov     rax, qword ptr [rbp+70h+var_C8+8]
0x1400c0a6f  movzx   r9d, word ptr [rbp+70h+var_D8+2]
0x1400c0a74  movzx   r8d, word ptr [rbp+70h+var_D8]
0x1400c0a79  mov     edx, dword ptr [rbp+70h+var_E8+0Ch]
0x1400c0a7c  movzx   ecx, word ptr [rbp+70h+var_E8+8]
0x1400c0a80  mov     [rsp+170h+var_130], rsi
0x1400c0a85  mov     [rsp+170h+var_138], rax
0x1400c0a8a  mov     eax, dword ptr [rbp+70h+var_C8+4]
0x1400c0a8d  mov     [rsp+170h+var_140], eax
0x1400c0a91  mov     eax, dword ptr [rbp+70h+var_C8]
0x1400c0a94  mov     dword ptr [rsp+170h+var_148], eax
0x1400c0a98  mov     rax, qword ptr [rbp+70h+var_D8+8]
0x1400c0a9c  mov     [rsp+170h+var_150], rax
0x1400c0aa1  call    TlShimMarshalOutTransportFields
0x1400c0aa6  mov     dword ptr [rsp+170h+Entry+4], 10h
0x1400c0aae  jmp     short loc_1400C0AF3
0x1400c0ab0  mov     rax, qword ptr [rbp+70h+var_98+8]
0x1400c0ab4  movzx   r9d, word ptr [rbp+70h+var_A8+2]
0x1400c0ab9  movzx   r8d, word ptr [rbp+70h+var_A8]
0x1400c0abe  mov     edx, dword ptr [rbp+70h+var_B8+0Ch]
0x1400c0ac1  movzx   ecx, word ptr [rbp+70h+var_B8+8]
0x1400c0ac5  mov     [rsp+170h+var_130], rsi
0x1400c0aca  mov     [rsp+170h+var_138], rax
0x1400c0acf  mov     eax, dword ptr [rbp+70h+var_98+4]
0x1400c0ad2  mov     [rsp+170h+var_140], eax
  ... truncated ...
```
