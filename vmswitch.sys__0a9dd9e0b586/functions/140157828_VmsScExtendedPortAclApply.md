# VmsScExtendedPortAclApply

- ea: `0x140157828`
- end: `0x140157e6b`
- name: `VmsScExtendedPortAclApply`
- size: `1603`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001df10`

## callees

- `0x14014b44c`
- `0x140157604`
- `0x140157828`
- `0x1401593d4`
- `0x1401bbcb0`
- `0x1401bbf20`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140157a2e`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140157a2e`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1401579f5`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1401579f5`
- `NDIS!NdisReleaseRWLock` at `0x140157a8b`
- `NDIS!NdisReleaseRWLock` at `0x140157e35`
- `NDIS!NdisReleaseRWLock` at `0x140157a8b`
- `NDIS!NdisReleaseRWLock` at `0x140157e35`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401579d8`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157d1d`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157df8`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401579d8`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157d1d`
- `NDIS!NdisAcquireRWLockWrite` at `0x140157df8`

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
0x140157828  mov     [rsp-8+arg_10], rbx
0x14015782d  push    rbp
0x14015782e  push    rsi
0x14015782f  push    rdi
0x140157830  push    r12
0x140157832  push    r13
0x140157834  push    r14
0x140157836  push    r15
0x140157838  lea     rbp, [rsp-27h]
0x14015783d  sub     rsp, 0B0h
0x140157844  mov     rax, cs:__security_cookie
0x14015784b  xor     rax, rsp
0x14015784e  mov     [rbp+57h+var_38], rax
0x140157852  xorps   xmm0, xmm0
0x140157855  mov     qword ptr [rbp+57h+var_90], rdx
0x140157859  mov     rax, r9
0x14015785c  mov     rdi, rcx
0x14015785f  xor     ecx, ecx
0x140157861  mov     qword ptr [rbp+57h+Signature+4], rax
0x140157865  xor     r9d, r9d
0x140157868  mov     [rbp+57h+Context.Signature], rcx
0x14015786c  movups  [rbp+57h+var_58], xmm0
0x140157870  mov     [rax], r9
0x140157873  mov     r12b, r8b
0x140157876  movups  [rbp+57h+var_58+9], xmm0
0x14015787a  mov     word ptr [rbp+57h+LockState.OldIrql], cx
0x14015787e  mov     r8, 0FFFFF78000000008h
0x140157888  movups  [rbp+57h+Buf1], xmm0
0x14015788c  mov     [rbp+57h+LockState.Flags], cl
0x14015788f  lea     r15d, [r9+2]
0x140157893  movups  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x140157897  mov     r8, [r8]
0x14015789a  mov     rsi, rdx
0x14015789d  mov     eax, [rdi+28h]
0x1401578a0  lea     edx, [rcx+1]
0x1401578a3  movups  [rbp+57h+var_58], xmm0
0x1401578a7  mov     ecx, 800h
0x1401578ac  mov     r13b, r9b
0x1401578af  movups  [rbp+57h+var_58+0Ch], xmm0
0x1401578b3  mov     [rbp+57h+var_40], eax
0x1401578b6  mov     ebx, edx
0x1401578b8  movzx   eax, word ptr [rdi+12h]
0x1401578bc  mov     [rbp+57h+var_AF], r9b
0x1401578c0  mov     [rbp+57h+var_44], r9d
0x1401578c4  movups  [rbp+57h+Buf1], xmm0
0x1401578c8  mov     byte ptr [rbp+57h+Buf1], 0FFh
0x1401578cc  cmp     ax, cx
0x1401578cf  jnz     short loc_14015793F
0x1401578d1  cmp     [rdi+41h], r9b
0x1401578d5  jz      short loc_1401578EF
0x1401578d7  movzx   eax, word ptr [rdi+3Eh]
0x1401578db  cmp     eax, cs:VmsMinFragmentOffset
0x1401578e1  jnb     loc_140157E41
0x1401578e7  mov     ebx, r15d
0x1401578ea  jmp     loc_140157E41
0x1401578ef  mov     rcx, [rdi+30h]
0x1401578f3  mov     word ptr [rbp+57h+var_A8], r15w
0x1401578f8  test    r12b, r12b
0x1401578fb  jz      short loc_140157908
0x1401578fd  mov     eax, [rcx+0Ch]
0x140157900  mov     dword ptr [rbp+57h+Buf1+4], eax
0x140157903  mov     eax, [rcx+10h]
0x140157906  jmp     short loc_140157911
0x140157908  mov     eax, [rcx+10h]
0x14015790b  mov     dword ptr [rbp+57h+Buf1+4], eax
0x14015790e  mov     eax, [rcx+0Ch]
0x140157911  mov     dword ptr [rbp+57h+var_58+4], eax
0x140157914  mov     al, [rdi+3Ch]
0x140157917  mov     byte ptr [rbp+57h+Buf1], al
0x14015791a  cmp     al, 6
0x14015791c  jnz     short loc_140157939
0x14015791e  mov     r13b, [rdi+49h]
0x140157922  mov     [rbp+57h+var_AF], r13b
0x140157926  test    r12b, r12b
0x140157929  jz      short loc_140157992
0x14015792b  movzx   eax, word ptr [rdi+4Ah]
0x14015792f  mov     word ptr [rbp+57h+var_44], ax
0x140157933  movzx   eax, word ptr [rdi+4Ch]
0x140157937  jmp     short loc_14015799E
0x140157939  cmp     al, 11h
0x14015793b  jnz     short loc_1401579A2
0x14015793d  jmp     short loc_140157926
0x14015793f  mov     ecx, 86DDh
0x140157944  cmp     ax, cx
0x140157947  jnz     loc_140157E41
0x14015794d  cmp     [rdi+42h], r9b
0x140157951  jnz     loc_140157E41
0x140157957  mov     rdx, [rdi+30h]
0x14015795b  mov     al, r12b
0x14015795e  neg     al
0x140157960  mov     [rbp+57h+var_A8], 17h
0x140157967  mov     al, r12b
0x14015796a  sbb     rcx, rcx
0x14015796d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140157971  neg     al
0x140157973  mov     al, [rdi+40h]
0x140157976  movups  xmm0, xmmword ptr [rcx+rdx+18h]
0x14015797b  sbb     rcx, rcx
0x14015797e  and     ecx, 10h
0x140157981  movdqu  [rbp+57h+Buf1+4], xmm0
0x140157986  movups  xmm0, xmmword ptr [rcx+rdx+8]
0x14015798b  movdqu  [rbp+57h+var_58+4], xmm0
0x140157990  jmp     short loc_140157917
0x140157992  movzx   eax, word ptr [rdi+4Ch]
0x140157996  mov     word ptr [rbp+57h+var_44], ax
0x14015799a  movzx   eax, word ptr [rdi+4Ah]
0x14015799e  mov     word ptr [rbp+57h+var_44+2], ax
0x1401579a2  mov     rax, 0D6BF94D5E57A42BDh
0x1401579ac  mov     [rbp+57h+var_B0], r9b
0x1401579b0  mul     r8
0x1401579b3  lea     rcx, [rbp+57h+Buf1]
0x1401579b7  mov     r14, r9
0x1401579ba  shr     rdx, 17h
0x1401579be  mov     [rbp+57h+var_98], rdx
0x1401579c2  call    VmsUtilComputeFlowSignature
0x1401579c7  mov     rcx, [rsi+2A28h]; Lock
0x1401579ce  lea     rdx, [rbp+57h+LockState]; LockState
0x1401579d2  mov     r8b, bl; Flags
0x1401579d5  mov     dword ptr [rbp+57h+Signature], eax
0x1401579d8  call    cs:__imp_NdisAcquireRWLockWrite
0x1401579df  nop     dword ptr [rax+rax+00h]
0x1401579e4  mov     edx, dword ptr [rbp+57h+Signature]; Signature
0x1401579e7  lea     rbx, [rsi+2978h]
0x1401579ee  mov     rcx, rbx; HashTable
0x1401579f1  lea     r8, [rbp+57h+Context]; Context
0x1401579f5  call    cs:__imp_RtlLookupEntryHashTable
0x1401579fc  nop     dword ptr [rax+rax+00h]
0x140157a01  xor     edx, edx
0x140157a03  mov     rsi, rax
0x140157a06  test    rax, rax
0x140157a09  jz      short loc_140157A72
0x140157a0b  lea     rdx, [rax+18h]; Buf2
0x140157a0f  mov     r8d, 2Ch ; ','; Size
0x140157a15  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140157a19  mov     r14, rax
0x140157a1c  call    memcmp
0x140157a21  xor     edx, edx
0x140157a23  test    eax, eax
0x140157a25  jz      short loc_140157A3C
0x140157a27  lea     rdx, [rbp+57h+Context]; Context
0x140157a2b  mov     rcx, rbx; HashTable
0x140157a2e  call    cs:__imp_RtlGetNextEntryHashTable
0x140157a35  nop     dword ptr [rax+rax+00h]
0x140157a3a  jmp     short loc_140157A01
0x140157a3c  test    r12b, r12b
0x140157a3f  jz      short loc_140157A4B
0x140157a41  lea     rbx, [rsi+48h]
0x140157a45  lea     rax, [rsi+60h]
0x140157a49  jmp     short loc_140157A53
0x140157a4b  lea     rbx, [rsi+44h]
0x140157a4f  lea     rax, [rsi+58h]
0x140157a53  mov     rax, [rax]
0x140157a56  mov     rcx, qword ptr [rbp+57h+Signature+4]
0x140157a5a  mov     [rcx], rax
0x140157a5d  mov     ebx, [rbx]
0x140157a5f  lea     eax, [rbx-1]
0x140157a62  cmp     eax, 1
0x140157a65  jbe     loc_140157BB4
0x140157a6b  mov     [rcx], rdx
0x140157a6e  mov     [rbp+57h+var_B0], 1
0x140157a72  mov     rbx, qword ptr [rbp+57h+var_90]
0x140157a76  mov     r13, rdx
0x140157a79  mov     [rbp+57h+var_88], rdx
0x140157a7d  mov     [rbp+57h+var_AE], dl
0x140157a80  lea     rdx, [rbp+57h+LockState]; LockState
0x140157a84  mov     rcx, [rbx+2A28h]; Lock
0x140157a8b  call    cs:__imp_NdisReleaseRWLock
0x140157a92  nop     dword ptr [rax+rax+00h]
0x140157a97  xor     r8d, r8d
0x140157a9a  lea     rsi, [rbx+2960h]
0x140157aa1  test    r12b, r12b
0x140157aa4  jnz     short loc_140157AAD
0x140157aa6  lea     rsi, [rbx+2950h]
0x140157aad  mov     rbx, [rsi]
0x140157ab0  cmp     rbx, rsi
0x140157ab3  jz      loc_140157CEE
0x140157ab9  mov     al, [rbx+22Ch]
0x140157abf  lea     rdx, [rbx+20h]
0x140157ac3  mov     [rbp+57h+var_88], rdx
0x140157ac7  mov     r13, rbx
0x140157aca  cmp     al, 0FFh
0x140157acc  jz      short loc_140157AD7
0x140157ace  cmp     al, byte ptr [rbp+57h+Buf1]
0x140157ad1  jnz     loc_140157CA2
0x140157ad7  mov     ecx, [rbx+21Ch]
0x140157add  test    ecx, ecx
0x140157adf  jnz     short loc_140157AEA
0x140157ae1  cmp     [rbx+220h], r8d
0x140157ae8  jz      short loc_140157B02
0x140157aea  movzx   eax, word ptr [rbp+57h+var_44]
0x140157aee  cmp     eax, ecx
0x140157af0  jb      loc_140157CA2
0x140157af6  cmp     eax, [rbx+220h]
0x140157afc  ja      loc_140157CA2
0x140157b02  mov     ecx, [rbx+224h]
0x140157b08  test    ecx, ecx
0x140157b0a  jnz     short loc_140157B15
0x140157b0c  cmp     [rbx+228h], r8d
0x140157b13  jz      short loc_140157B2D
0x140157b15  movzx   eax, word ptr [rbp+57h+var_44+2]
0x140157b19  cmp     eax, ecx
0x140157b1b  jb      loc_140157CA2
0x140157b21  cmp     eax, [rbx+228h]
0x140157b27  ja      loc_140157CA2
0x140157b2d  mov     eax, [rdx+1B4h]
0x140157b33  test    eax, eax
0x140157b35  jz      short loc_140157B40
0x140157b37  cmp     [rbp+57h+var_40], eax
0x140157b3a  jnz     loc_140157CA2
0x140157b40  movzx   eax, word ptr [rbx+1D8h]
0x140157b47  test    ax, ax
0x140157b4a  jz      loc_140157CAE
0x140157b50  cmp     ax, r15w
0x140157b54  jnz     loc_140157C20
0x140157b5a  cmp     word ptr [rbp+57h+var_A8], r15w
0x140157b5f  jnz     loc_140157CA2
0x140157b65  mov     ecx, dword ptr [rbp+57h+Buf1+4]
0x140157b68  mov     eax, [rbx+1DCh]
0x140157b6e  bswap   ecx
0x140157b70  bswap   eax
0x140157b72  cmp     ecx, eax
0x140157b74  jb      loc_140157CA2
0x140157b7a  mov     eax, [rbx+1E0h]
0x140157b80  bswap   eax
0x140157b82  cmp     ecx, eax
0x140157b84  ja      loc_140157CA2
0x140157b8a  mov     ecx, dword ptr [rbp+57h+var_58+4]
0x140157b8d  mov     eax, [rbx+1FCh]
0x140157b93  bswap   ecx
0x140157b95  bswap   eax
0x140157b97  cmp     ecx, eax
0x140157b99  jb      loc_140157CA2
0x140157b9f  mov     eax, [rbx+200h]
0x140157ba5  bswap   eax
0x140157ba7  cmp     ecx, eax
0x140157ba9  jbe     loc_140157CAE
0x140157baf  jmp     loc_140157CA2
0x140157bb4  cmp     byte ptr [rbp+57h+Buf1], 6
0x140157bb8  jnz     short loc_140157C0C
0x140157bba  mov     ecx, [rsi+50h]
0x140157bbd  lea     eax, [rcx-2]
0x140157bc0  cmp     eax, 1
0x140157bc3  ja      short loc_140157C0C
0x140157bc5  test    r15b, r13b
0x140157bc8  jz      short loc_140157BDE
0x140157bca  test    r12b, r12b
0x140157bcd  jz      short loc_140157BF4
0x140157bcf  cmp     ecx, r15d
0x140157bd2  jnz     short loc_140157BDE
0x140157bd4  mov     eax, [rsi+70h]
0x140157bd7  dec     eax
0x140157bd9  cmp     eax, 1
0x140157bdc  ja      short loc_140157C02
0x140157bde  mov     r8b, r12b
0x140157be1  mov     dl, r13b
0x140157be4  mov     rcx, rsi
0x140157be7  call    VmsScpExtendedPortAclUpdateFlowState
0x140157bec  test    al, al
0x140157bee  cmovnz  ebx, r15d
0x140157bf2  jmp     short loc_140157C17
0x140157bf4  cmp     ecx, 3
0x140157bf7  jnz     short loc_140157C07
0x140157bf9  test    dword ptr [rsi+70h], 0FFFFFFFDh
0x140157c00  jz      short loc_140157C07
0x140157c02  mov     ebx, r15d
0x140157c05  jmp     short loc_140157C17
0x140157c07  xor     r8d, r8d
0x140157c0a  jmp     short loc_140157BE1
0x140157c0c  mov     eax, [rsi+4Ch]
0x140157c0f  add     rax, [rbp+57h+var_98]
0x140157c13  mov     [rsi+68h], rax
0x140157c17  mov     rdi, qword ptr [rbp+57h+var_90]
0x140157c1b  jmp     loc_140157E2A
0x140157c20  mov     ecx, 17h
0x140157c25  cmp     ax, cx
0x140157c28  jnz     short loc_140157CA2
0x140157c2a  cmp     word ptr [rbp+57h+var_A8], cx
0x140157c2e  jnz     short loc_140157CA2
0x140157c30  lea     r8d, [rcx-7]; Size
0x140157c34  lea     rcx, [rbp+57h+Buf1+4]; Buf1
0x140157c38  lea     rdx, [rbx+1DCh]; Buf2
0x140157c3f  call    memcmp
0x140157c44  xor     r8d, r8d
0x140157c47  test    eax, eax
0x140157c49  js      short loc_140157CA2
0x140157c4b  lea     rdx, [rbx+1ECh]; Buf2
0x140157c52  mov     r8d, 10h; Size
0x140157c58  lea     rcx, [rbp+57h+Buf1+4]; Buf1
0x140157c5c  call    memcmp
0x140157c61  xor     r8d, r8d
0x140157c64  test    eax, eax
0x140157c66  jg      short loc_140157CA2
0x140157c68  lea     rdx, [rbx+1FCh]; Buf2
0x140157c6f  mov     r8d, 10h; Size
0x140157c75  lea     rcx, [rbp+57h+var_58+4]; Buf1
0x140157c79  call    memcmp
0x140157c7e  xor     r8d, r8d
0x140157c81  test    eax, eax
0x140157c83  js      short loc_140157CA2
0x140157c85  lea     rdx, [rbx+20Ch]; Buf2
  ... truncated ...
```
