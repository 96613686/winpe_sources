# VmsScExtendedPortAclApply

- ea: `0x1401577b8`
- end: `0x140157dfb`
- name: `VmsScExtendedPortAclApply`
- size: `1603`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001df10`

## callees

- `0x14014b3dc`
- `0x140157594`
- `0x1401577b8`
- `0x140159364`
- `0x1401bbc40`
- `0x1401bbea0`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1401579be`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1401579be`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140157985`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140157985`
- `NDIS!NdisReleaseRWLock` at `0x140157a1b`
- `NDIS!NdisReleaseRWLock` at `0x140157dc5`
- `NDIS!NdisReleaseRWLock` at `0x140157a1b`
- `NDIS!NdisReleaseRWLock` at `0x140157dc5`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157968`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157cad`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157d88`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157968`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157cad`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157d88`

## pseudocode

```c
__int64 __fastcall VmsScExtendedPortAclApply(__int64 a1, __int64 a2, char a3, _QWORD *a4)
{
  char v7; // r13
  unsigned int v8; // ebx
  __int16 v9; // ax
  __int64 v10; // rcx
  int v11; // eax
  char v12; // al
  __int16 v13; // ax
  __int64 v14; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v15; // r14
  int v16; // eax
  struct _NDIS_RW_LOCK_EX *v17; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v18; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v20; // rsi
  int v21; // eax
  __int64 v22; // r8
  __int64 v23; // rdx
  unsigned int *v24; // rbx
  _QWORD *p_Flink; // rax
  _QWORD *v26; // rcx
  __int64 v27; // rbx
  unsigned __int64 v28; // r13
  __int64 **v29; // rsi
  __int64 *j; // rbx
  char v31; // al
  __int64 *v32; // rdx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  int v35; // eax
  __int16 v36; // ax
  unsigned __int32 v37; // ecx
  unsigned __int32 v38; // ecx
  int Blink; // ecx
  __int64 v40; // rdi
  char v41; // si
  bool v42; // al
  __int64 v43; // rax
  unsigned __int64 v44; // rax
  _LIST_ENTRY **v45; // rax
  unsigned __int64 v46; // rax
  int v47; // r9d
  ULONG_PTR v49; // [rsp+20h] [rbp-69h]
  char v50; // [rsp+30h] [rbp-59h]
  char v51; // [rsp+31h] [rbp-58h]
  struct _LOCK_STATE_EX LockState; // [rsp+34h] [rbp-55h] BYREF
  int v53; // [rsp+38h] [rbp-51h]
  _DWORD Signature[3]; // [rsp+3Ch] [rbp-4Dh]
  unsigned __int64 v55; // [rsp+48h] [rbp-41h]
  int v56[2]; // [rsp+50h] [rbp-39h]
  __int64 *v57; // [rsp+58h] [rbp-31h]
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+60h] [rbp-29h] BYREF
  _OWORD Buf1[3]; // [rsp+78h] [rbp-11h] BYREF

  *(_QWORD *)v56 = a2;
  *(_QWORD *)&Signature[1] = a4;
  Context.Signature = 0;
  *a4 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  memset(Buf1, 0, 44);
  LockState.Flags = 0;
  *(_OWORD *)&Context.ChainHead = 0;
  v7 = 0;
  DWORD2(Buf1[2]) = *(_DWORD *)(a1 + 40);
  v8 = 1;
  v9 = *(_WORD *)(a1 + 18);
  v51 = 0;
  DWORD1(Buf1[2]) = 0;
  Buf1[0] = 0;
  LOBYTE(Buf1[0]) = -1;
  if ( v9 == 2048 )
  {
    if ( *(_BYTE *)(a1 + 65) )
    {
      if ( *(unsigned __int16 *)(a1 + 62) < (unsigned int)VmsMinFragmentOffset )
        return 2;
      return v8;
    }
    v10 = *(_QWORD *)(a1 + 48);
    LOWORD(v53) = 2;
    if ( a3 )
    {
      DWORD1(Buf1[0]) = *(_DWORD *)(v10 + 12);
      v11 = *(_DWORD *)(v10 + 16);
    }
    else
    {
      DWORD1(Buf1[0]) = *(_DWORD *)(v10 + 16);
      v11 = *(_DWORD *)(v10 + 12);
    }
    DWORD1(Buf1[1]) = v11;
    v12 = *(_BYTE *)(a1 + 60);
  }
  else
  {
    if ( v9 != -31011 || *(_BYTE *)(a1 + 66) )
      return v8;
    v14 = *(_QWORD *)(a1 + 48);
    v53 = 23;
    v12 = *(_BYTE *)(a1 + 64);
    *(_OWORD *)((char *)Buf1 + 4) = *(_OWORD *)((-(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + v14 + 24);
    *(_OWORD *)((char *)&Buf1[1] + 4) = *(_OWORD *)((a3 != 0 ? 0x10 : 0) + v14 + 8);
  }
  LOBYTE(Buf1[0]) = v12;
  if ( v12 == 6 )
  {
    v7 = *(_BYTE *)(a1 + 73);
    v51 = v7;
LABEL_11:
    if ( a3 )
    {
      WORD2(Buf1[2]) = *(_WORD *)(a1 + 74);
      v13 = *(_WORD *)(a1 + 76);
    }
    else
    {
      WORD2(Buf1[2]) = *(_WORD *)(a1 + 76);
      v13 = *(_WORD *)(a1 + 74);
    }
    WORD3(Buf1[2]) = v13;
    goto LABEL_20;
  }
  if ( v12 == 17 )
    goto LABEL_11;
LABEL_20:
  v50 = 0;
  v15 = 0;
  v55 = MEMORY[0xFFFFF78000000008] / 0x989680uLL;
  v16 = VmsUtilComputeFlowSignature((__int64)Buf1);
  v17 = *(struct _NDIS_RW_LOCK_EX **)(a2 + 10792);
  Signature[0] = v16;
  NdisAcquireRWLockWrite(v17, &LockState, 1u);
  v18 = (struct _RTL_DYNAMIC_HASH_TABLE *)(a2 + 10616);
  for ( i = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(a2 + 10616), Signature[0], &Context);
        ;
        i = RtlGetNextEntryHashTable(v18, &Context) )
  {
    v20 = i;
    if ( !i )
      goto LABEL_29;
    v15 = i;
    v21 = memcmp(Buf1, &i[1], 0x2Cu);
    v23 = 0;
    if ( !v21 )
      break;
  }
  if ( a3 )
  {
    v24 = (unsigned int *)&v20[3];
    p_Flink = &v20[4].Linkage.Flink;
  }
  else
  {
    v24 = (unsigned int *)&v20[2].Signature + 1;
    p_Flink = &v20[3].Signature;
  }
  v26 = *(_QWORD **)&Signature[1];
  **(_QWORD **)&Signature[1] = *p_Flink;
  v8 = *v24;
  if ( v8 - 1 <= 1 )
  {
    if ( LOBYTE(Buf1[0]) == 6 && (Blink = (int)v20[3].Linkage.Blink, (unsigned int)(Blink - 2) <= 1) )
    {
      if ( (v7 & 2) == 0 )
      {
LABEL_59:
        LOBYTE(v22) = a3;
        goto LABEL_60;
      }
      if ( a3 )
      {
        if ( Blink != 2 || (unsigned int)(LODWORD(v20[4].Signature) - 1) <= 1 )
          goto LABEL_59;
      }
      else if ( Blink != 3 || (v20[4].Signature & 0xFFFFFFFD) == 0 )
      {
        v22 = 0;
LABEL_60:
        LOBYTE(v23) = v7;
        if ( (unsigned __int8)VmsScpExtendedPortAclUpdateFlowState(v20, v23, v22) )
          v8 = 2;
        goto LABEL_68;
      }
      v8 = 2;
    }
    else
    {
      v20[4].Linkage.Blink = (_LIST_ENTRY *)(v55 + HIDWORD(v20[3].Linkage.Flink));
    }
LABEL_68:
    v40 = *(_QWORD *)v56;
    goto LABEL_97;
  }
  *v26 = 0;
  v50 = 1;
LABEL_29:
  v27 = *(_QWORD *)v56;
  v28 = 0;
  v57 = 0;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)v56 + 10792LL), &LockState);
  v29 = (__int64 **)(v27 + 10592);
  if ( !a3 )
    v29 = (__int64 **)(v27 + 10576);
  for ( j = *v29; j != (__int64 *)v29; j = (__int64 *)*j )
  {
    v31 = *((_BYTE *)j + 556);
    v32 = j + 4;
    v57 = j + 4;
    v28 = (unsigned __int64)j;
    if ( (v31 == -1 || v31 == LOBYTE(Buf1[0]))
      && ((v33 = *((_DWORD *)j + 135)) == 0 && !*((_DWORD *)j + 136)
       || WORD2(Buf1[2]) >= v33 && (unsigned int)WORD2(Buf1[2]) <= *((_DWORD *)j + 136))
      && ((v34 = *((_DWORD *)j + 137)) == 0 && !*((_DWORD *)j + 138)
       || WORD3(Buf1[2]) >= v34 && (unsigned int)WORD3(Buf1[2]) <= *((_DWORD *)j + 138)) )
    {
      v35 = *((_DWORD *)j + 117);
      if ( !v35 || DWORD2(Buf1[2]) == v35 )
      {
        v36 = *((_WORD *)j + 236);
        if ( !v36 )
          goto LABEL_77;
        if ( v36 == 2 )
        {
          if ( (_WORD)v53 == 2 )
          {
            v37 = _byteswap_ulong(DWORD1(Buf1[0]));
            if ( v37 >= _byteswap_ulong(*((_DWORD *)j + 119)) && v37 <= _byteswap_ulong(*((_DWORD *)j + 120)) )
            {
              v38 = _byteswap_ulong(DWORD1(Buf1[1]));
              if ( v38 >= _byteswap_ulong(*((_DWORD *)j + 127)) && v38 <= _byteswap_ulong(*((_DWORD *)j + 128)) )
                goto LABEL_77;
            }
          }
        }
        else if ( v36 == 23
               && (_WORD)v53 == 23
               && memcmp((char *)Buf1 + 4, (char *)j + 476, 0x10u) >= 0
               && memcmp((char *)Buf1 + 4, (char *)j + 492, 0x10u) <= 0
               && memcmp((char *)&Buf1[1] + 4, (char *)j + 508, 0x10u) >= 0
               && memcmp((char *)&Buf1[1] + 4, (char *)j + 524, 0x10u) <= 0 )
        {
          v32 = v57;
LABEL_77:
          v41 = 1;
          **(_QWORD **)&Signature[1] = j;
          v8 = *((unsigned __int8 *)v32 + 133);
          if ( *((_BYTE *)v32 + 430) && LOBYTE(Buf1[0]) == 6 )
          {
            v50 = (v51 & 2) != 0 ? v50 : 0;
            v42 = (v51 & 2) == 0;
            goto LABEL_84;
          }
          if ( *(_BYTE *)(a1 + 44) )
          {
            v42 = 1;
            goto LABEL_84;
          }
          goto LABEL_83;
        }
      }
    }
  }
  v8 = 1;
  v41 = 0;
  v42 = 1;
  if ( *(_BYTE *)(a1 + 44) )
    goto LABEL_84;
LABEL_83:
  v42 = 0;
LABEL_84:
  if ( v50 )
  {
    v40 = *(_QWORD *)v56;
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)v56 + 10792LL), &LockState, 1u);
    if ( v41 && *((_BYTE *)v57 + 430) )
    {
      LODWORD(v15[3].Linkage.Blink) = (*(_BYTE *)(v28 + 164) != 1) + 2;
      HIDWORD(v15[2].Signature) = *(unsigned __int8 *)(v28 + 165);
      LODWORD(v15[3].Linkage.Flink) = *(unsigned __int8 *)(v28 + 165);
      v43 = *(unsigned __int16 *)(v28 + 464);
      HIDWORD(v15[3].Linkage.Flink) = v43;
      if ( *(_BYTE *)(v28 + 556) == 6 )
      {
        LODWORD(v15[4].Signature) = a3 == 0;
        v44 = v55 + 21;
      }
      else
      {
        v44 = v55 + v43;
      }
      v15[4].Linkage.Blink = (_LIST_ENTRY *)v44;
      v15[3].Signature = v28;
      v15[4].Linkage.Flink = (_LIST_ENTRY *)v28;
    }
    else
    {
      v45 = *(_LIST_ENTRY ***)&Signature[1];
      if ( a3 )
      {
        LODWORD(v15[3].Linkage.Flink) = v8;
        v15[4].Linkage.Flink = *v45;
      }
      else
      {
        HIDWORD(v15[2].Signature) = v8;
        v15[3].Signature = (unsigned __int64)*v45;
      }
      v46 = v55 + 255;
      HIDWORD(v15[3].Linkage.Flink) = 255;
      v15[4].Linkage.Blink = (_LIST_ENTRY *)v46;
    }
  }
  else
  {
    if ( v42 )
      return v8;
    v40 = *(_QWORD *)v56;
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)v56 + 10792LL), &LockState, 1u);
    LOBYTE(v47) = a3;
    LODWORD(v49) = Signature[0];
    VmsScExtendedPortAclAddFlowEntry(v40, **(_QWORD **)&Signature[1], (int)Buf1, v47, v49, 0);
  }
LABEL_97:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v40 + 10792), &LockState);
  return v8;
}

```

## disassembly

```asm
0x1401577b8  mov     [rsp-8+arg_10], rbx
0x1401577bd  push    rbp
0x1401577be  push    rsi
0x1401577bf  push    rdi
0x1401577c0  push    r12
0x1401577c2  push    r13
0x1401577c4  push    r14
0x1401577c6  push    r15
0x1401577c8  lea     rbp, [rsp-27h]
0x1401577cd  sub     rsp, 0B0h
0x1401577d4  mov     rax, cs:__security_cookie
0x1401577db  xor     rax, rsp
0x1401577de  mov     [rbp+57h+var_38], rax
0x1401577e2  xorps   xmm0, xmm0
0x1401577e5  mov     qword ptr [rbp+57h+var_90], rdx
0x1401577e9  mov     rax, r9
0x1401577ec  mov     rdi, rcx
0x1401577ef  xor     ecx, ecx
0x1401577f1  mov     qword ptr [rbp+57h+Signature+4], rax
0x1401577f5  xor     r9d, r9d
0x1401577f8  mov     [rbp+57h+Context.Signature], rcx
0x1401577fc  movups  [rbp+57h+var_58], xmm0
0x140157800  mov     [rax], r9
0x140157803  mov     r12b, r8b
0x140157806  movups  [rbp+57h+var_58+9], xmm0
0x14015780a  mov     word ptr [rbp+57h+LockState.OldIrql], cx
0x14015780e  mov     r8, 0FFFFF78000000008h
0x140157818  movups  [rbp+57h+Buf1], xmm0
0x14015781c  mov     [rbp+57h+LockState.Flags], cl
0x14015781f  lea     r15d, [r9+2]
0x140157823  movups  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x140157827  mov     r8, [r8]
0x14015782a  mov     rsi, rdx
0x14015782d  mov     eax, [rdi+28h]
0x140157830  lea     edx, [rcx+1]
0x140157833  movups  [rbp+57h+var_58], xmm0
0x140157837  mov     ecx, 800h
0x14015783c  mov     r13b, r9b
0x14015783f  movups  [rbp+57h+var_58+0Ch], xmm0
0x140157843  mov     [rbp+57h+var_40], eax
0x140157846  mov     ebx, edx
0x140157848  movzx   eax, word ptr [rdi+12h]
0x14015784c  mov     [rbp+57h+var_AF], r9b
0x140157850  mov     [rbp+57h+var_44], r9d
0x140157854  movups  [rbp+57h+Buf1], xmm0
0x140157858  mov     byte ptr [rbp+57h+Buf1], 0FFh
0x14015785c  cmp     ax, cx
0x14015785f  jnz     short loc_1401578CF
0x140157861  cmp     [rdi+41h], r9b
0x140157865  jz      short loc_14015787F
0x140157867  movzx   eax, word ptr [rdi+3Eh]
0x14015786b  cmp     eax, cs:VmsMinFragmentOffset
0x140157871  jnb     loc_140157DD1
0x140157877  mov     ebx, r15d
0x14015787a  jmp     loc_140157DD1
0x14015787f  mov     rcx, [rdi+30h]
0x140157883  mov     word ptr [rbp+57h+var_A8], r15w
0x140157888  test    r12b, r12b
0x14015788b  jz      short loc_140157898
0x14015788d  mov     eax, [rcx+0Ch]
0x140157890  mov     dword ptr [rbp+57h+Buf1+4], eax
0x140157893  mov     eax, [rcx+10h]
0x140157896  jmp     short loc_1401578A1
0x140157898  mov     eax, [rcx+10h]
0x14015789b  mov     dword ptr [rbp+57h+Buf1+4], eax
0x14015789e  mov     eax, [rcx+0Ch]
0x1401578a1  mov     dword ptr [rbp+57h+var_58+4], eax
0x1401578a4  mov     al, [rdi+3Ch]
0x1401578a7  mov     byte ptr [rbp+57h+Buf1], al
0x1401578aa  cmp     al, 6
0x1401578ac  jnz     short loc_1401578C9
0x1401578ae  mov     r13b, [rdi+49h]
0x1401578b2  mov     [rbp+57h+var_AF], r13b
0x1401578b6  test    r12b, r12b
0x1401578b9  jz      short loc_140157922
0x1401578bb  movzx   eax, word ptr [rdi+4Ah]
0x1401578bf  mov     word ptr [rbp+57h+var_44], ax
0x1401578c3  movzx   eax, word ptr [rdi+4Ch]
0x1401578c7  jmp     short loc_14015792E
0x1401578c9  cmp     al, 11h
0x1401578cb  jnz     short loc_140157932
0x1401578cd  jmp     short loc_1401578B6
0x1401578cf  mov     ecx, 86DDh
0x1401578d4  cmp     ax, cx
0x1401578d7  jnz     loc_140157DD1
0x1401578dd  cmp     [rdi+42h], r9b
0x1401578e1  jnz     loc_140157DD1
0x1401578e7  mov     rdx, [rdi+30h]
0x1401578eb  mov     al, r12b
0x1401578ee  neg     al
0x1401578f0  mov     [rbp+57h+var_A8], 17h
0x1401578f7  mov     al, r12b
0x1401578fa  sbb     rcx, rcx
0x1401578fd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140157901  neg     al
0x140157903  mov     al, [rdi+40h]
0x140157906  movups  xmm0, xmmword ptr [rcx+rdx+18h]
0x14015790b  sbb     rcx, rcx
0x14015790e  and     ecx, 10h
0x140157911  movdqu  [rbp+57h+Buf1+4], xmm0
0x140157916  movups  xmm0, xmmword ptr [rcx+rdx+8]
0x14015791b  movdqu  [rbp+57h+var_58+4], xmm0
0x140157920  jmp     short loc_1401578A7
0x140157922  movzx   eax, word ptr [rdi+4Ch]
0x140157926  mov     word ptr [rbp+57h+var_44], ax
0x14015792a  movzx   eax, word ptr [rdi+4Ah]
0x14015792e  mov     word ptr [rbp+57h+var_44+2], ax
0x140157932  mov     rax, 0D6BF94D5E57A42BDh
0x14015793c  mov     [rbp+57h+var_B0], r9b
0x140157940  mul     r8
0x140157943  lea     rcx, [rbp+57h+Buf1]
0x140157947  mov     r14, r9
0x14015794a  shr     rdx, 17h
0x14015794e  mov     [rbp+57h+var_98], rdx
0x140157952  call    VmsUtilComputeFlowSignature
0x140157957  mov     rcx, [rsi+2A28h]; Lock
0x14015795e  lea     rdx, [rbp+57h+LockState]; LockState
0x140157962  mov     r8b, bl; Flags
0x140157965  mov     dword ptr [rbp+57h+Signature], eax
0x140157968  call    cs:__imp_NdisAcquireRWLockWrite
0x14015796f  nop     dword ptr [rax+rax+00h]
0x140157974  mov     edx, dword ptr [rbp+57h+Signature]; Signature
0x140157977  lea     rbx, [rsi+2978h]
0x14015797e  mov     rcx, rbx; HashTable
0x140157981  lea     r8, [rbp+57h+Context]; Context
0x140157985  call    cs:__imp_RtlLookupEntryHashTable
0x14015798c  nop     dword ptr [rax+rax+00h]
0x140157991  xor     edx, edx
0x140157993  mov     rsi, rax
0x140157996  test    rax, rax
0x140157999  jz      short loc_140157A02
0x14015799b  lea     rdx, [rax+18h]; Buf2
0x14015799f  mov     r8d, 2Ch ; ','; Size
0x1401579a5  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1401579a9  mov     r14, rax
0x1401579ac  call    memcmp
0x1401579b1  xor     edx, edx
0x1401579b3  test    eax, eax
0x1401579b5  jz      short loc_1401579CC
0x1401579b7  lea     rdx, [rbp+57h+Context]; Context
0x1401579bb  mov     rcx, rbx; HashTable
0x1401579be  call    cs:__imp_RtlGetNextEntryHashTable
0x1401579c5  nop     dword ptr [rax+rax+00h]
0x1401579ca  jmp     short loc_140157991
0x1401579cc  test    r12b, r12b
0x1401579cf  jz      short loc_1401579DB
0x1401579d1  lea     rbx, [rsi+48h]
0x1401579d5  lea     rax, [rsi+60h]
0x1401579d9  jmp     short loc_1401579E3
0x1401579db  lea     rbx, [rsi+44h]
0x1401579df  lea     rax, [rsi+58h]
0x1401579e3  mov     rax, [rax]
0x1401579e6  mov     rcx, qword ptr [rbp+57h+Signature+4]
0x1401579ea  mov     [rcx], rax
0x1401579ed  mov     ebx, [rbx]
0x1401579ef  lea     eax, [rbx-1]
0x1401579f2  cmp     eax, 1
0x1401579f5  jbe     loc_140157B44
0x1401579fb  mov     [rcx], rdx
0x1401579fe  mov     [rbp+57h+var_B0], 1
0x140157a02  mov     rbx, qword ptr [rbp+57h+var_90]
0x140157a06  mov     r13, rdx
0x140157a09  mov     [rbp+57h+var_88], rdx
0x140157a0d  mov     [rbp+57h+var_AE], dl
0x140157a10  lea     rdx, [rbp+57h+LockState]; LockState
0x140157a14  mov     rcx, [rbx+2A28h]; Lock
0x140157a1b  call    cs:__imp_NdisReleaseRWLock
0x140157a22  nop     dword ptr [rax+rax+00h]
0x140157a27  xor     r8d, r8d
0x140157a2a  lea     rsi, [rbx+2960h]
0x140157a31  test    r12b, r12b
0x140157a34  jnz     short loc_140157A3D
0x140157a36  lea     rsi, [rbx+2950h]
0x140157a3d  mov     rbx, [rsi]
0x140157a40  cmp     rbx, rsi
0x140157a43  jz      loc_140157C7E
0x140157a49  mov     al, [rbx+22Ch]
0x140157a4f  lea     rdx, [rbx+20h]
0x140157a53  mov     [rbp+57h+var_88], rdx
0x140157a57  mov     r13, rbx
0x140157a5a  cmp     al, 0FFh
0x140157a5c  jz      short loc_140157A67
0x140157a5e  cmp     al, byte ptr [rbp+57h+Buf1]
0x140157a61  jnz     loc_140157C32
0x140157a67  mov     ecx, [rbx+21Ch]
0x140157a6d  test    ecx, ecx
0x140157a6f  jnz     short loc_140157A7A
0x140157a71  cmp     [rbx+220h], r8d
0x140157a78  jz      short loc_140157A92
0x140157a7a  movzx   eax, word ptr [rbp+57h+var_44]
0x140157a7e  cmp     eax, ecx
0x140157a80  jb      loc_140157C32
0x140157a86  cmp     eax, [rbx+220h]
0x140157a8c  ja      loc_140157C32
0x140157a92  mov     ecx, [rbx+224h]
0x140157a98  test    ecx, ecx
0x140157a9a  jnz     short loc_140157AA5
0x140157a9c  cmp     [rbx+228h], r8d
0x140157aa3  jz      short loc_140157ABD
0x140157aa5  movzx   eax, word ptr [rbp+57h+var_44+2]
0x140157aa9  cmp     eax, ecx
0x140157aab  jb      loc_140157C32
0x140157ab1  cmp     eax, [rbx+228h]
0x140157ab7  ja      loc_140157C32
0x140157abd  mov     eax, [rdx+1B4h]
0x140157ac3  test    eax, eax
0x140157ac5  jz      short loc_140157AD0
0x140157ac7  cmp     [rbp+57h+var_40], eax
0x140157aca  jnz     loc_140157C32
0x140157ad0  movzx   eax, word ptr [rbx+1D8h]
0x140157ad7  test    ax, ax
0x140157ada  jz      loc_140157C3E
0x140157ae0  cmp     ax, r15w
0x140157ae4  jnz     loc_140157BB0
0x140157aea  cmp     word ptr [rbp+57h+var_A8], r15w
0x140157aef  jnz     loc_140157C32
0x140157af5  mov     ecx, dword ptr [rbp+57h+Buf1+4]
0x140157af8  mov     eax, [rbx+1DCh]
0x140157afe  bswap   ecx
0x140157b00  bswap   eax
0x140157b02  cmp     ecx, eax
0x140157b04  jb      loc_140157C32
0x140157b0a  mov     eax, [rbx+1E0h]
0x140157b10  bswap   eax
0x140157b12  cmp     ecx, eax
0x140157b14  ja      loc_140157C32
0x140157b1a  mov     ecx, dword ptr [rbp+57h+var_58+4]
0x140157b1d  mov     eax, [rbx+1FCh]
0x140157b23  bswap   ecx
0x140157b25  bswap   eax
0x140157b27  cmp     ecx, eax
0x140157b29  jb      loc_140157C32
0x140157b2f  mov     eax, [rbx+200h]
0x140157b35  bswap   eax
0x140157b37  cmp     ecx, eax
0x140157b39  jbe     loc_140157C3E
0x140157b3f  jmp     loc_140157C32
0x140157b44  cmp     byte ptr [rbp+57h+Buf1], 6
0x140157b48  jnz     short loc_140157B9C
0x140157b4a  mov     ecx, [rsi+50h]
0x140157b4d  lea     eax, [rcx-2]
0x140157b50  cmp     eax, 1
0x140157b53  ja      short loc_140157B9C
0x140157b55  test    r15b, r13b
0x140157b58  jz      short loc_140157B6E
0x140157b5a  test    r12b, r12b
0x140157b5d  jz      short loc_140157B84
0x140157b5f  cmp     ecx, r15d
0x140157b62  jnz     short loc_140157B6E
0x140157b64  mov     eax, [rsi+70h]
0x140157b67  dec     eax
0x140157b69  cmp     eax, 1
0x140157b6c  ja      short loc_140157B92
0x140157b6e  mov     r8b, r12b
0x140157b71  mov     dl, r13b
0x140157b74  mov     rcx, rsi
0x140157b77  call    VmsScpExtendedPortAclUpdateFlowState
0x140157b7c  test    al, al
0x140157b7e  cmovnz  ebx, r15d
0x140157b82  jmp     short loc_140157BA7
0x140157b84  cmp     ecx, 3
0x140157b87  jnz     short loc_140157B97
0x140157b89  test    dword ptr [rsi+70h], 0FFFFFFFDh
0x140157b90  jz      short loc_140157B97
0x140157b92  mov     ebx, r15d
0x140157b95  jmp     short loc_140157BA7
0x140157b97  xor     r8d, r8d
0x140157b9a  jmp     short loc_140157B71
0x140157b9c  mov     eax, [rsi+4Ch]
0x140157b9f  add     rax, [rbp+57h+var_98]
0x140157ba3  mov     [rsi+68h], rax
0x140157ba7  mov     rdi, qword ptr [rbp+57h+var_90]
0x140157bab  jmp     loc_140157DBA
0x140157bb0  mov     ecx, 17h
0x140157bb5  cmp     ax, cx
0x140157bb8  jnz     short loc_140157C32
0x140157bba  cmp     word ptr [rbp+57h+var_A8], cx
0x140157bbe  jnz     short loc_140157C32
0x140157bc0  lea     r8d, [rcx-7]; Size
0x140157bc4  lea     rcx, [rbp+57h+Buf1+4]; Buf1
0x140157bc8  lea     rdx, [rbx+1DCh]; Buf2
0x140157bcf  call    memcmp
0x140157bd4  xor     r8d, r8d
0x140157bd7  test    eax, eax
0x140157bd9  js      short loc_140157C32
0x140157bdb  lea     rdx, [rbx+1ECh]; Buf2
0x140157be2  mov     r8d, 10h; Size
0x140157be8  lea     rcx, [rbp+57h+Buf1+4]; Buf1
0x140157bec  call    memcmp
0x140157bf1  xor     r8d, r8d
0x140157bf4  test    eax, eax
0x140157bf6  jg      short loc_140157C32
0x140157bf8  lea     rdx, [rbx+1FCh]; Buf2
0x140157bff  mov     r8d, 10h; Size
0x140157c05  lea     rcx, [rbp+57h+var_58+4]; Buf1
0x140157c09  call    memcmp
0x140157c0e  xor     r8d, r8d
0x140157c11  test    eax, eax
0x140157c13  js      short loc_140157C32
0x140157c15  lea     rdx, [rbx+20Ch]; Buf2
  ... truncated ...
```
