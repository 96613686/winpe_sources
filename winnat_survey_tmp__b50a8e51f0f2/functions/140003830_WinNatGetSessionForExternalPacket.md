# WinNatGetSessionForExternalPacket

- ea: `0x140003830`
- end: `0x14000408c`
- name: `WinNatGetSessionForExternalPacket`
- size: `2140`
- prototype: `PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall(__int64, _BYTE *, _WORD *, __int64, unsigned __int8, _BYTE *, _DWORD *, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400020e0`
- `0x14001c210`

## callees

- `0x1400019f0`
- `0x140003830`
- `0x140004a40`
- `0x140004a80`
- `0x140004d20`
- `0x140009b04`
- `0x14000caa0`
- `0x1400158b8`
- `0x140019cd4`
- `0x14001ac70`
- `0x14001ede0`
- `0x14001f020`
- `0x14001f140`
- `0x14001f440`
- `0x14002d040`

## import_xrefs

- `ntoskrnl!KeTestSpinLock` at `0x140003909`
- `ntoskrnl!KeTestSpinLock` at `0x140003909`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140003923`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140003923`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140003936`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140003936`
- `ntoskrnl!KeLowerIrql` at `0x140003b6c`
- `ntoskrnl!KeLowerIrql` at `0x140003c56`
- `ntoskrnl!KeLowerIrql` at `0x140003b6c`
- `ntoskrnl!KeLowerIrql` at `0x140003c56`
- `ntoskrnl!KfRaiseIrql` at `0x1400038c8`
- `ntoskrnl!KfRaiseIrql` at `0x140003bde`
- `ntoskrnl!KfRaiseIrql` at `0x1400038c8`
- `ntoskrnl!KfRaiseIrql` at `0x140003bde`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140003a1f`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140003a1f`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140003b09`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140003b09`
- `NETIO!RtlComputeToeplitzHash` at `0x14000397c`
- `NETIO!RtlComputeToeplitzHash` at `0x14000399a`
- `NETIO!RtlComputeToeplitzHash` at `0x1400039cb`
- `NETIO!RtlComputeToeplitzHash` at `0x1400039ec`
- `NETIO!RtlComputeToeplitzHash` at `0x14000397c`
- `NETIO!RtlComputeToeplitzHash` at `0x14000399a`
- `NETIO!RtlComputeToeplitzHash` at `0x1400039cb`
- `NETIO!RtlComputeToeplitzHash` at `0x1400039ec`

## pseudocode

```c
PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall WinNatGetSessionForExternalPacket(
        __int64 a1,
        _BYTE *a2,
        _WORD *a3,
        __int64 a4,
        unsigned __int8 a5,
        _BYTE *a6,
        _DWORD *a7,
        int a8)
{
  __int64 v8; // r15
  __int64 v9; // rdi
  KIRQL v12; // al
  unsigned int LockArray_high; // ecx
  unsigned int v14; // ebx
  volatile signed __int32 *v15; // rbx
  _BYTE *v16; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v17; // rdi
  bool v18; // zf
  __int64 v19; // r12
  __int64 v20; // r8
  int v21; // ebx
  int v22; // eax
  _WORD *v23; // rdx
  __int64 v24; // r8
  int v25; // ebx
  int v26; // eax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rax
  unsigned __int8 v28; // r12
  struct _LIST_ENTRY *Blink; // rdx
  __int64 v30; // rcx
  int Flink; // eax
  _WORD *Signature; // rdx
  size_t v33; // r8
  const void *v34; // rcx
  struct _LIST_ENTRY *v35; // rdx
  size_t v36; // r8
  const void *v37; // rcx
  __int64 v38; // r15
  char DoesExtTransAddrNeedTranslation; // al
  KIRQL v41; // al
  unsigned int v42; // r12d
  __int64 v43; // rdi
  KIRQL v44; // r13
  __int64 BindingUnderLock; // rax
  __int64 MultiMapInternalBindingUnderLock; // r15
  __int16 *v47; // rbx
  size_t v48; // r8
  __int16 v49; // r9
  char *v50; // rcx
  size_t v51; // r8
  __int64 v52; // rdx
  __int64 v53; // rcx
  char v54; // bl
  __int64 v55; // rdx
  __int64 v56; // rcx
  int v57; // ebx
  unsigned int v58; // r12d
  char *v59; // r8
  unsigned int v60; // ecx
  _BYTE *v61; // r8
  char *v62; // rcx
  __int16 v63; // bx
  size_t v64; // r8
  char v65; // di
  __int64 SessionEntry; // rax
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // rbx
  unsigned __int8 v70; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v71; // [rsp+61h] [rbp-9Fh]
  KIRQL v72; // [rsp+62h] [rbp-9Eh]
  __int64 v73; // [rsp+68h] [rbp-98h]
  int v74; // [rsp+70h] [rbp-90h]
  _BYTE *v75; // [rsp+78h] [rbp-88h]
  __int64 v76; // [rsp+80h] [rbp-80h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-78h] BYREF
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+A0h] [rbp-60h]
  __int64 v79; // [rsp+A8h] [rbp-58h]
  _OWORD v80[3]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v81; // [rsp+E0h] [rbp-20h]
  __int64 v82; // [rsp+F0h] [rbp-10h]
  __int128 v83; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v84[2]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v85[16]; // [rsp+130h] [rbp+30h] BYREF

  v8 = a1 + 128;
  v71 = a5;
  v9 = a1 + 192;
  v75 = a6;
  v74 = a8;
  v73 = a1;
  memset(v85, 0, 28);
  v70 = 0;
  memset(v84, 0, 28);
  v82 = 0;
  v76 = a4;
  v83 = 0;
  memset(v80, 0, sizeof(v80));
  v81 = 0;
  v12 = KfRaiseIrql(2u);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v14 = *(_DWORD *)(v9 + 8);
  v72 = v12;
  v79 = LockArray_high;
  v15 = (volatile signed __int32 *)(v9 + (((LockArray_high & v14) + 1LL) << 6));
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement(v15);
  if ( !KeTestSpinLock((PKSPIN_LOCK)v9) )
  {
    _InterlockedDecrement(v15);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v9, &LockHandle);
    _InterlockedIncrement(v15);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v16 = a2 + 4;
  v17 = 0;
  v18 = *(_WORD *)a2 == 2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !v18 )
    v16 = a2 + 8;
  v19 = v8 + 408;
  v20 = 4;
  if ( !v18 )
    v20 = 16;
  v21 = RtlComputeToeplitzHash(v19, v16, v20, 0);
  v22 = RtlComputeToeplitzHash(v19, a2 + 2, 2, 0);
  v23 = a3 + 2;
  if ( *a3 != 2 )
    v23 = a3 + 4;
  v24 = 4;
  if ( *a3 != 2 )
    v24 = 16;
  v25 = v21 ^ v22 ^ RtlComputeToeplitzHash(v19, v23, v24, 0);
  v26 = v25 ^ RtlComputeToeplitzHash(v19, a3 + 1, 2, 0);
  HashTable = *(PRTL_DYNAMIC_HASH_TABLE *)(v73 + 520);
  LockHandle.LockQueue = 0;
  NextEntryHashTable = RtlLookupEntryHashTable(
                         HashTable,
                         v26 | 0x80000000,
                         (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle);
  if ( NextEntryHashTable )
  {
    v28 = v71;
    while ( 1 )
    {
      Blink = NextEntryHashTable[-4].Linkage.Blink;
      v17 = NextEntryHashTable - 8;
      v30 = *(unsigned __int16 *)NextEntryHashTable[-4].Signature;
      if ( LOWORD(Blink->Flink) != (_WORD)v30 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v30, Blink);
      Flink = (int)v17[5].Linkage.Flink;
      if ( Flink == v71 || Flink == 58 && v71 == 1 )
      {
        Signature = (_WORD *)v17[4].Signature;
        if ( *(_WORD *)a2 == *Signature && *((_WORD *)a2 + 1) == Signature[1] )
        {
          v33 = 4;
          v34 = a2 + 4;
          if ( *Signature != 2 )
            v33 = 16;
          if ( *(_WORD *)a2 != 2 )
            v34 = a2 + 8;
          if ( !memcmp(v34, Signature + 2, v33) )
          {
            v35 = v17[4].Linkage.Blink;
            if ( *a3 == LOWORD(v35->Flink) && a3[1] == WORD1(v35->Flink) )
            {
              v36 = 4;
              v37 = a3 + 2;
              if ( LOWORD(v35->Flink) != 2 )
                v36 = 16;
              if ( *a3 != 2 )
                v37 = a3 + 4;
              if ( !memcmp(v37, (char *)&v35->Flink + 4, v36) )
                break;
            }
          }
        }
      }
      v17 = 0;
      NextEntryHashTable = RtlGetNextEntryHashTable(HashTable, (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle);
      if ( !NextEntryHashTable )
        goto LABEL_38;
    }
    if ( v17 && _InterlockedIncrement64((volatile signed __int64 *)v17) <= 1 )
      __fastfail(0xEu);
  }
  else
  {
    v28 = v71;
  }
LABEL_38:
  v38 = v73;
  _InterlockedDecrement((volatile signed __int32 *)(((((unsigned int)v79 & *(_DWORD *)(v73 + 200)) + 1LL) << 6)
                                                  + v73
                                                  + 192));
  KeLowerIrql(v72);
  if ( v17 )
    return v17;
  if ( v28 == 1 || v28 == 58 )
  {
    *v75 = 0;
    return 0;
  }
  if ( *a3 == 2 && v76 )
  {
    *v75 = 0;
  }
  else
  {
    DoesExtTransAddrNeedTranslation = WinNatDoesExtTransAddrNeedTranslation(
                                        v73,
                                        (_DWORD)a3,
                                        (_DWORD)a2,
                                        (unsigned int)&v83,
                                        (__int64)&v70);
    *v75 = DoesExtTransAddrNeedTranslation;
    if ( !DoesExtTransAddrNeedTranslation )
      return 0;
  }
  v41 = KfRaiseIrql(2u);
  v42 = HIDWORD(KeGetPcr()[1].LockArray);
  v43 = v38 + 832;
  v44 = v41;
  RtlAcquireScalableReadLockAtDpcLevel((PKSPIN_LOCK)(v38 + 832));
  BindingUnderLock = WinNatFindBindingUnderLock((int)v38 + 768, 1, (_DWORD)a3, 0, v71, 0, v74);
  MultiMapInternalBindingUnderLock = BindingUnderLock;
  if ( !BindingUnderLock )
  {
    _InterlockedDecrement((volatile signed __int32 *)((((v42 & *(_DWORD *)(v43 + 8)) + 1LL) << 6) + v43));
    KeLowerIrql(v44);
    return 0;
  }
  if ( (*(_BYTE *)(BindingUnderLock + 88) & 4) != 0 )
  {
    MultiMapInternalBindingUnderLock = WinNatFindMultiMapInternalBindingUnderLock(BindingUnderLock, a2);
    if ( !MultiMapInternalBindingUnderLock )
    {
      RtlReleaseScalableReadLock(v43, v42, v44);
      return 0;
    }
  }
  v47 = *(__int16 **)(MultiMapInternalBindingUnderLock + 96);
  v48 = 28;
  if ( v85[0] == 2 )
    v48 = 16;
  memset(v85, 0, v48);
  v49 = *v47;
  v50 = (char *)&v85[4];
  v85[0] = *v47;
  v51 = 4;
  v85[1] = v47[1];
  if ( *v47 != 2 )
    v51 = 16;
  if ( v49 == 2 )
    v50 = (char *)&v85[2];
  memmove(v50, v47 + 2, v51);
  v54 = *(_BYTE *)(MultiMapInternalBindingUnderLock + 88);
  LODWORD(v75) = *(_DWORD *)(MultiMapInternalBindingUnderLock + 112);
  LODWORD(v80[0]) = *(_DWORD *)(MultiMapInternalBindingUnderLock + 92);
  if ( !LODWORD(v80[0]) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v53, v52);
  RtlReleaseScalableReadLock(v43, v42, v44);
  if ( (_DWORD)v75 == 1 && (v54 & 1) == 0 )
  {
    v57 = v73;
    if ( (unsigned __int8)WinNatApplyAddressDependentFiltering(v73 + 128, LODWORD(v80[0]), a3, a2, v84, &v70) )
      return 0;
    LOBYTE(v58) = v70;
    goto LABEL_119;
  }
  v58 = v70;
  if ( v70 )
  {
    if ( *a3 != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v56, v55);
    v59 = (char *)v84 + 4;
    if ( LOWORD(v84[0]) != 2 )
      v59 = (char *)v84 + 8;
    v60 = v58 >> 3;
    if ( v58 >> 3 )
    {
      *v59 = v83;
      if ( v60 > 1 )
      {
        v59[1] = BYTE1(v83);
        if ( v60 > 2 )
        {
          v59[2] = BYTE2(v83);
          if ( v60 > 3 )
          {
            v59[3] = BYTE3(v83);
            if ( v60 > 4 )
            {
              v59[4] = BYTE4(v83);
              if ( v60 > 5 )
              {
                v59[5] = BYTE5(v83);
                if ( v60 > 6 )
                {
                  v59[6] = BYTE6(v83);
                  if ( v60 > 7 )
                  {
                    v59[7] = BYTE7(v83);
                    if ( v60 > 8 )
                    {
                      v59[8] = BYTE8(v83);
                      if ( v60 > 9 )
                      {
                        v59[9] = BYTE9(v83);
                        if ( v60 > 0xA )
                        {
                          v59[10] = BYTE10(v83);
                          if ( v60 > 0xB )
                          {
                            v59[11] = BYTE11(v83);
                            if ( v60 > 0xC )
                            {
                              v59[12] = BYTE12(v83);
                              if ( v60 > 0xD )
                              {
                                v59[13] = BYTE13(v83);
                                if ( v60 > 0xE )
                                {
                                  v59[14] = BYTE14(v83);
                                  if ( v60 > 0xF )
                                  {
                                    v59[15] = HIBYTE(v83);
LABEL_101:
                                    if ( (v58 & 7) != 0 )
                                      v59[v60] = *((_BYTE *)&v84[-1] + v60) & (-1 << (8 - (v58 & 7)));
                                    v61 = a2 + 4;
                                    if ( *(_WORD *)a2 != 2 )
                                      v61 = a2 + 8;
                                    v62 = (char *)v84 + 4;
                                    if ( LOWORD(v84[0]) != 2 )
                                      v62 = (char *)v84 + 8;
                                    IN6_SET_V4ADDR_IN_V4EMBV6(v62, (unsigned __int8)v58, v61);
                                    WORD1(v84[0]) = *((_WORD *)a2 + 1);
                                    LOWORD(v84[0]) = 23;
LABEL_118:
                                    v57 = v73;
LABEL_119:
                                    v65 = 0;
                                    goto LABEL_120;
                                  }
LABEL_100:
                                  v59[15] = 0;
                                  goto LABEL_101;
                                }
LABEL_99:
                                v59[14] = 0;
                                goto LABEL_100;
                              }
LABEL_98:
                              v59[13] = 0;
                              goto LABEL_99;
                            }
LABEL_97:
                            v59[12] = 0;
                            goto LABEL_98;
                          }
LABEL_96:
                          v59[11] = 0;
                          goto LABEL_97;
                        }
LABEL_95:
                        v59[10] = 0;
                        goto LABEL_96;
                      }
LABEL_94:
                      v59[9] = 0;
                      goto LABEL_95;
                    }
LABEL_93:
                    v59[8] = 0;
                    goto LABEL_94;
                  }
LABEL_92:
                  v59[7] = 0;
                  goto LABEL_93;
                }
LABEL_91:
                v59[6] = 0;
                goto LABEL_92;
              }
LABEL_90:
              v59[5] = 0;
              goto LABEL_91;
            }
LABEL_89:
            v59[4] = 0;
            goto LABEL_90;
          }
LABEL_88:
          v59[3] = 0;
          goto LABEL_89;
        }
LABEL_87:
        v59[2] = 0;
        goto LABEL_88;
      }
    }
    else
    {
      *v59 = 0;
    }
    v59[1] = 0;
    goto LABEL_87;
  }
  if ( v85[0] == 23 && *(_WORD *)a2 == 2 )
    return 0;
  v63 = *(_WORD *)a2;
  v64 = 16;
  if ( *(_WORD *)a2 != 2 )
    v64 = 28;
  memmove(v84, a2, v64);
  if ( v63 != 2 || a2[4] != 127 )
    goto LABEL_118;
  if ( !a7 )
  {
    if ( (xmmword_1400262D0 & 8) != 0 )
      WPP_SF_(515, 10, WPP_6b5d6271391b37248aab835b4b36cb2a_Traceguids);
    goto LABEL_118;
  }
  v65 = 1;
  v57 = v73;
  DWORD1(v84[0]) = *a7;
LABEL_120:
  DWORD2(v81) = v74;
  SessionEntry = WinNatCreateSessionEntry(
                   v57,
                   0,
                   (unsigned int)v85,
                   (unsigned int)v84,
                   (__int64)a3,
                   v76,
                   (__int64)a2,
                   v71,
                   v58,
                   (__int64)v80,
                   0);
  v69 = SessionEntry;
  if ( SessionEntry )
  {
    if ( *(_QWORD *)(SessionEntry + 80) != MultiMapInternalBindingUnderLock )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v68, v67);
    if ( *(_DWORD *)(v69 + 68) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v68, v67);
  }
  if ( v65 )
  {
    *(_BYTE *)(v69 + 280) = 1;
    if ( (xmmword_1400262E0 & 8) != 0 )
      WPP_SF_(1027, 11, WPP_6b5d6271391b37248aab835b4b36cb2a_Traceguids);
  }
  return (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v69;
}

```

## disassembly

```asm
0x140003830  push    rbp
0x140003832  push    rbx
0x140003833  push    rsi
0x140003834  push    rdi
0x140003835  push    r12
0x140003837  push    r13
0x140003839  push    r14
0x14000383b  push    r15
0x14000383d  lea     rbp, [rsp-68h]
0x140003842  sub     rsp, 168h
0x140003849  mov     rax, cs:__security_cookie
0x140003850  xor     rax, rsp
0x140003853  mov     [rbp+0A0h+var_50], rax
0x140003857  movzx   eax, [rbp+0A0h+arg_20]
0x14000385e  lea     r15, [rcx+80h]
0x140003865  xorps   xmm1, xmm1
0x140003868  mov     [rsp+1A0h+var_13F], al
0x14000386c  mov     rax, [rbp+0A0h+arg_28]
0x140003873  lea     rdi, [r15+40h]
0x140003877  xorps   xmm0, xmm0
0x14000387a  mov     [rsp+1A0h+var_128], rax
0x14000387f  mov     eax, [rbp+0A0h+arg_38]
0x140003885  mov     r14, r8
0x140003888  mov     [rsp+1A0h+var_130], eax
0x14000388c  mov     rsi, rdx
0x14000388f  xor     eax, eax
0x140003891  mov     [rsp+1A0h+var_138], rcx
0x140003896  movups  xmmword ptr [rbp+0A0h+var_70], xmm0
0x14000389a  mov     cl, 2; NewIrql
0x14000389c  mov     [rsp+1A0h+var_140], al
0x1400038a0  movups  [rbp+0A0h+var_90], xmm1
0x1400038a4  mov     [rbp+0A0h+var_B0], rax
0x1400038a8  mov     [rbp+0A0h+var_120], r9
0x1400038ac  movups  xmmword ptr [rbp+0A0h+var_70+0Ch], xmm0
0x1400038b0  movups  [rbp+0A0h+var_90+0Ch], xmm1
0x1400038b4  movups  [rbp+0A0h+var_A0], xmm0
0x1400038b8  movups  [rbp+0A0h+var_F0], xmm1
0x1400038bc  movups  [rbp+0A0h+var_E0], xmm1
0x1400038c0  movups  [rbp+0A0h+var_D0], xmm1
0x1400038c4  movups  [rbp+0A0h+var_C0], xmm1
0x1400038c8  call    cs:__imp_KfRaiseIrql
0x1400038cf  nop     dword ptr [rax+rax+00h]
0x1400038d4  mov     ecx, gs:1A4h
0x1400038dc  xorps   xmm0, xmm0
0x1400038df  mov     ebx, [rdi+8]
0x1400038e2  mov     [rsp+1A0h+var_13E], al
0x1400038e6  xor     eax, eax
0x1400038e8  mov     qword ptr [rbp+0A0h+LockHandle.OldIrql], rax
0x1400038ec  mov     eax, ecx
0x1400038ee  and     rbx, rax
0x1400038f1  mov     [rbp+0A0h+var_F8], rax
0x1400038f5  inc     rbx
0x1400038f8  shl     rbx, 6
0x1400038fc  add     rbx, rdi
0x1400038ff  movups  xmmword ptr [rbp+0A0h+LockHandle.LockQueue.Next], xmm0
0x140003903  lock inc dword ptr [rbx]
0x140003906  mov     rcx, rdi; SpinLock
0x140003909  call    cs:__imp_KeTestSpinLock
0x140003910  nop     dword ptr [rax+rax+00h]
0x140003915  test    al, al
0x140003917  jnz     short loc_140003942
0x140003919  lock dec dword ptr [rbx]
0x14000391c  lea     rdx, [rbp+0A0h+LockHandle]; LockHandle
0x140003920  mov     rcx, rdi; SpinLock
0x140003923  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000392a  nop     dword ptr [rax+rax+00h]
0x14000392f  lock inc dword ptr [rbx]
0x140003932  lea     rcx, [rbp+0A0h+LockHandle]; LockHandle
0x140003936  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000393d  nop     dword ptr [rax+rax+00h]
0x140003942  xor     eax, eax
0x140003944  lea     rdx, [rsi+4]
0x140003948  xor     edi, edi
0x14000394a  mov     qword ptr [rbp+0A0h+LockHandle.OldIrql], rax
0x14000394e  cmp     word ptr [rsi], 2
0x140003952  xorps   xmm0, xmm0
0x140003955  movups  xmmword ptr [rbp+0A0h+LockHandle.LockQueue.Next], xmm0
0x140003959  jz      short loc_14000395F
0x14000395b  lea     rdx, [rsi+8]
0x14000395f  lea     r12, [r15+198h]
0x140003966  mov     r8d, 4
0x14000396c  mov     r15d, 10h
0x140003972  mov     rcx, r12
0x140003975  cmovnz  r8d, r15d
0x140003979  xor     r9d, r9d
0x14000397c  call    cs:__imp_RtlComputeToeplitzHash
0x140003983  nop     dword ptr [rax+rax+00h]
0x140003988  lea     rdx, [rsi+2]
0x14000398c  xor     r9d, r9d
0x14000398f  mov     r8d, 2
0x140003995  mov     rcx, r12
0x140003998  mov     ebx, eax
0x14000399a  call    cs:__imp_RtlComputeToeplitzHash
0x1400039a1  nop     dword ptr [rax+rax+00h]
0x1400039a6  mov     r13d, eax
0x1400039a9  lea     rdx, [r14+4]
0x1400039ad  xor     r13d, ebx
0x1400039b0  cmp     word ptr [r14], 2
0x1400039b5  jz      short loc_1400039BB
0x1400039b7  lea     rdx, [r14+8]
0x1400039bb  mov     r8d, 4
0x1400039c1  mov     rcx, r12
0x1400039c4  cmovnz  r8d, r15d
0x1400039c8  xor     r9d, r9d
0x1400039cb  call    cs:__imp_RtlComputeToeplitzHash
0x1400039d2  nop     dword ptr [rax+rax+00h]
0x1400039d7  lea     rdx, [r14+2]
0x1400039db  xor     r9d, r9d
0x1400039de  mov     ebx, eax
0x1400039e0  mov     r8d, 2
0x1400039e6  mov     rcx, r12
0x1400039e9  xor     ebx, r13d
0x1400039ec  call    cs:__imp_RtlComputeToeplitzHash
0x1400039f3  nop     dword ptr [rax+rax+00h]
0x1400039f8  xorps   xmm0, xmm0
0x1400039fb  lea     r8, [rbp+0A0h+LockHandle]; Context
0x1400039ff  xor     eax, ebx
0x140003a01  mov     rbx, [rsp+1A0h+var_138]
0x140003a06  bts     eax, 1Fh
0x140003a0a  mov     edx, eax; Signature
0x140003a0c  mov     rax, [rbx+208h]
0x140003a13  mov     rcx, rax; HashTable
0x140003a16  mov     [rbp+0A0h+HashTable], rax
0x140003a1a  movdqu  xmmword ptr [rbp+0A0h+LockHandle.LockQueue.Next], xmm0
0x140003a1f  call    cs:__imp_RtlLookupEntryHashTable
0x140003a26  nop     dword ptr [rax+rax+00h]
0x140003a2b  test    rax, rax
0x140003a2e  jz      loc_140003B41
0x140003a34  movzx   r12d, [rsp+1A0h+var_13F]
0x140003a3a  nop     word ptr [rax+rax+00h]
0x140003a40  mov     rdx, [rax-58h]
0x140003a44  lea     rdi, [rax-0C0h]
0x140003a4b  mov     rax, [rax-50h]
0x140003a4f  movzx   ecx, word ptr [rax]
0x140003a52  cmp     [rdx], cx
0x140003a55  jz      short loc_140003A5C
0x140003a57  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140003a5c  mov     eax, [rdi+78h]
0x140003a5f  cmp     eax, r12d
0x140003a62  jz      short loc_140003A77
0x140003a64  cmp     eax, 3Ah ; ':'
0x140003a67  jnz     loc_140003AFF
0x140003a6d  cmp     r12b, 1
0x140003a71  jnz     loc_140003AFF
0x140003a77  mov     rdx, [rdi+70h]
0x140003a7b  movzx   r9d, word ptr [rsi]
0x140003a7f  movzx   ecx, word ptr [rdx]
0x140003a82  cmp     r9w, cx
0x140003a86  jnz     short loc_140003AFF
0x140003a88  movzx   eax, word ptr [rdx+2]
0x140003a8c  cmp     [rsi+2], ax
0x140003a90  jnz     short loc_140003AFF
0x140003a92  cmp     cx, 2
0x140003a96  mov     ebx, 4
0x140003a9b  mov     r8d, ebx
0x140003a9e  lea     rcx, [rsi+4]
0x140003aa2  cmovnz  r8, r15; Size
0x140003aa6  cmp     r9w, 2
0x140003aab  jz      short loc_140003AB1
0x140003aad  lea     rcx, [rsi+8]; Buf1
0x140003ab1  add     rdx, rbx; Buf2
0x140003ab4  call    memcmp
0x140003ab9  test    eax, eax
0x140003abb  jnz     short loc_140003AFF
0x140003abd  mov     rdx, [rdi+68h]
0x140003ac1  movzx   r9d, word ptr [r14]
0x140003ac5  movzx   ecx, word ptr [rdx]
0x140003ac8  cmp     r9w, cx
0x140003acc  jnz     short loc_140003AFF
0x140003ace  movzx   eax, word ptr [rdx+2]
0x140003ad2  cmp     [r14+2], ax
0x140003ad7  jnz     short loc_140003AFF
0x140003ad9  cmp     cx, 2
0x140003add  mov     r8, rbx
0x140003ae0  lea     rcx, [r14+4]
0x140003ae4  cmovnz  r8, r15; Size
0x140003ae8  cmp     r9w, 2
0x140003aed  jz      short loc_140003AF3
0x140003aef  lea     rcx, [r14+8]; Buf1
0x140003af3  add     rdx, rbx; Buf2
0x140003af6  call    memcmp
0x140003afb  test    eax, eax
0x140003afd  jz      short loc_140003B20
0x140003aff  mov     rcx, [rbp+0A0h+HashTable]; HashTable
0x140003b03  lea     rdx, [rbp+0A0h+LockHandle]; Context
0x140003b07  xor     edi, edi
0x140003b09  call    cs:__imp_RtlGetNextEntryHashTable
0x140003b10  nop     dword ptr [rax+rax+00h]
0x140003b15  test    rax, rax
0x140003b18  jnz     loc_140003A40
0x140003b1e  jmp     short loc_140003B47
0x140003b20  test    rdi, rdi
0x140003b23  jz      short loc_140003B47
0x140003b25  mov     eax, 1
0x140003b2a  lock xadd [rdi], rax
0x140003b2f  inc     rax
0x140003b32  cmp     rax, 1
0x140003b36  jg      short loc_140003B47
0x140003b38  mov     ecx, 0Eh
0x140003b3d  int     29h; Win8: RtlFailFast(ecx)
0x140003b3f  jmp     short loc_140003B47
0x140003b41  movzx   r12d, [rsp+1A0h+var_13F]
0x140003b47  mov     r15, [rsp+1A0h+var_138]
0x140003b4c  mov     ecx, [r15+0C8h]
0x140003b53  and     rcx, [rbp+0A0h+var_F8]
0x140003b57  inc     rcx
0x140003b5a  shl     rcx, 6
0x140003b5e  lock dec dword ptr [rcx+r15+0C0h]
0x140003b67  movzx   ecx, [rsp+1A0h+var_13E]; NewIrql
0x140003b6c  call    cs:__imp_KeLowerIrql
0x140003b73  nop     dword ptr [rax+rax+00h]
0x140003b78  test    rdi, rdi
0x140003b7b  jz      short loc_140003B85
0x140003b7d  mov     rax, rdi
0x140003b80  jmp     loc_14000406B
0x140003b85  cmp     r12b, 1
0x140003b89  jz      loc_140004061
0x140003b8f  cmp     r12b, 3Ah ; ':'
0x140003b93  jz      loc_140004061
0x140003b99  cmp     word ptr [r14], 2
0x140003b9e  jnz     short loc_140003BB1
0x140003ba0  cmp     [rbp+0A0h+var_120], 0
0x140003ba5  jz      short loc_140003BB1
0x140003ba7  mov     rcx, [rsp+1A0h+var_128]
0x140003bac  mov     byte ptr [rcx], 0
0x140003baf  jmp     short loc_140003BDC
0x140003bb1  lea     rax, [rsp+1A0h+var_140]
0x140003bb6  mov     r8, rsi
0x140003bb9  lea     r9, [rbp+0A0h+var_A0]
0x140003bbd  mov     [rsp+1A0h+var_180], rax
0x140003bc2  mov     rdx, r14
0x140003bc5  mov     rcx, r15
0x140003bc8  call    WinNatDoesExtTransAddrNeedTranslation
0x140003bcd  mov     rcx, [rsp+1A0h+var_128]
0x140003bd2  mov     [rcx], al
0x140003bd4  test    al, al
0x140003bd6  jz      loc_140004069
0x140003bdc  mov     cl, 2; NewIrql
0x140003bde  call    cs:__imp_KfRaiseIrql
0x140003be5  nop     dword ptr [rax+rax+00h]
0x140003bea  mov     r12d, gs:1A4h
0x140003bf3  lea     rdi, [r15+340h]
0x140003bfa  mov     rcx, rdi; SpinLock
0x140003bfd  mov     edx, r12d
0x140003c00  movzx   r13d, al
0x140003c04  call    RtlAcquireScalableReadLockAtDpcLevel
0x140003c09  mov     eax, [rsp+1A0h+var_130]
0x140003c0d  lea     rcx, [r15+300h]
0x140003c14  mov     dword ptr [rsp+1A0h+var_170], eax
0x140003c18  xor     r9d, r9d
0x140003c1b  movzx   eax, [rsp+1A0h+var_13F]
0x140003c20  mov     r8, r14
0x140003c23  mov     byte ptr [rsp+1A0h+var_178], 0
0x140003c28  mov     edx, 1
0x140003c2d  mov     byte ptr [rsp+1A0h+var_180], al
0x140003c31  call    WinNatFindBindingUnderLock
0x140003c36  mov     r15, rax
0x140003c39  test    rax, rax
0x140003c3c  jnz     short loc_140003C67
0x140003c3e  mov     ecx, [rdi+8]
0x140003c41  mov     eax, r12d
0x140003c44  and     rcx, rax
0x140003c47  inc     rcx
0x140003c4a  shl     rcx, 6
0x140003c4e  lock dec dword ptr [rcx+rdi]
0x140003c52  movzx   ecx, r13b; NewIrql
0x140003c56  call    cs:__imp_KeLowerIrql
0x140003c5d  nop     dword ptr [rax+rax+00h]
0x140003c62  jmp     loc_140004069
0x140003c67  test    byte ptr [rax+58h], 4
0x140003c6b  jz      short loc_140003C94
0x140003c6d  mov     rdx, rsi
0x140003c70  mov     rcx, rax
0x140003c73  call    WinNatFindMultiMapInternalBindingUnderLock
0x140003c78  mov     r15, rax
0x140003c7b  test    rax, rax
0x140003c7e  jnz     short loc_140003C94
0x140003c80  movzx   r8d, r13b
0x140003c84  mov     edx, r12d
0x140003c87  mov     rcx, rdi
0x140003c8a  call    RtlReleaseScalableReadLock
0x140003c8f  jmp     loc_140004069
0x140003c94  cmp     [rbp+0A0h+var_70], 2
0x140003c99  lea     rcx, [rbp+0A0h+var_70]; void *
0x140003c9d  mov     rbx, [r15+60h]
0x140003ca1  mov     eax, 10h
0x140003ca6  mov     r8d, 1Ch
0x140003cac  cmovz   r8d, eax; Size
0x140003cb0  xor     edx, edx; Val
0x140003cb2  call    memset
0x140003cb7  movzx   r9d, word ptr [rbx]
0x140003cbb  lea     rcx, [rbp+0A0h+var_70+8]
0x140003cbf  mov     [rbp+0A0h+var_70], r9w
0x140003cc4  lea     rdx, [rbx+4]; Src
0x140003cc8  movzx   eax, word ptr [rbx+2]
0x140003ccc  mov     r8d, 4
0x140003cd2  mov     [rbp+0A0h+var_70+2], ax
0x140003cd6  mov     eax, 10h
0x140003cdb  cmp     word ptr [rbx], 2
0x140003cdf  cmovnz  r8d, eax; Size
  ... truncated ...
```
