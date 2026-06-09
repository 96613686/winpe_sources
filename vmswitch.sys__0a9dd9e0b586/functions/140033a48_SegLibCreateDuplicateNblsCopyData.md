# SegLibCreateDuplicateNblsCopyData

- ea: `0x140033a48`
- end: `0x140033f8b`
- name: `SegLibCreateDuplicateNblsCopyData`
- size: `1347`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1400143ac`

## callees

- `0x140006620`
- `0x140006b00`
- `0x140033a48`
- `0x140033fa0`
- `0x140033fec`
- `0x140034130`
- `0x1400341b4`
- `0x1401bbbc2`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140033df8`
- `ntoskrnl!MmSizeOfMdl` at `0x140033df8`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140033e85`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140033e85`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033b84`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033b84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033ddf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033ddf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f4b`
- `ntoskrnl!ExAllocatePool2` at `0x140033e1c`
- `ntoskrnl!ExAllocatePool2` at `0x140033e1c`
- `NDIS!NdisFreeNetBufferList` at `0x140033f6f`
- `NDIS!NdisFreeNetBufferList` at `0x140033f6f`
- `NDIS!NdisAllocateNetBufferAndNetBufferList` at `0x140033cdf`
- `NDIS!NdisAllocateNetBufferAndNetBufferList` at `0x140033cdf`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140033ed1`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140033ed1`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140033d17`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140033d17`

## pseudocode

```c
__int64 __fastcall SegLibCreateDuplicateNblsCopyData(
        __int64 a1,
        struct _NET_BUFFER_LIST *a2,
        char a3,
        __int64 a4,
        __int64 a5,
        void *a6,
        USHORT a7,
        int a8,
        PNET_BUFFER_LIST *a9,
        _DWORD *a10,
        __int64 a11)
{
  PMDL v11; // r12
  int v13; // r8d
  BOOL v14; // edx
  int v15; // r13d
  int v16; // ecx
  __int64 v17; // rbx
  unsigned int v18; // edi
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  void *v21; // rsp
  ULONG CurrentProcessorNumber; // eax
  bool v23; // cf
  int v24; // r14d
  int v25; // edi
  PNET_BUFFER_LIST *i; // r13
  unsigned int v27; // eax
  SIZE_T DataLength; // rsi
  int MdlAndDataPpl; // eax
  __int64 v30; // rbx
  int v31; // r15d
  __int64 v32; // r8
  int v33; // edi
  struct _NET_BUFFER_LIST *NetBufferAndNetBufferList; // rax
  __int64 v35; // r8
  struct _NET_BUFFER_LIST *v36; // rbx
  __int64 v37; // r8
  __int64 v39; // rbx
  struct _MDL *Pool2; // rax
  struct _MDL *v41; // rdi
  bool v42; // zf
  PNET_BUFFER_LIST v43; // rcx
  struct _NET_BUFFER_LIST *Alignment; // rbx
  char v45; // [rsp+30h] [rbp+0h] BYREF
  char v46; // [rsp+31h] [rbp+1h]
  int v47; // [rsp+34h] [rbp+4h] BYREF
  USHORT v48; // [rsp+38h] [rbp+8h]
  BOOL v49; // [rsp+3Ch] [rbp+Ch]
  __int64 v50; // [rsp+40h] [rbp+10h]
  PMDL MdlChain; // [rsp+48h] [rbp+18h]
  __int64 v52; // [rsp+50h] [rbp+20h] BYREF
  PNET_BUFFER_LIST SrcNetBufferList; // [rsp+58h] [rbp+28h]
  PNET_BUFFER_LIST NetBufferList; // [rsp+60h] [rbp+30h] BYREF
  __int64 v55; // [rsp+68h] [rbp+38h]
  NDIS_HANDLE PoolHandle; // [rsp+70h] [rbp+40h]
  PNET_BUFFER_LIST *v57; // [rsp+78h] [rbp+48h]
  _DWORD *v58; // [rsp+80h] [rbp+50h]
  int v59[24]; // [rsp+90h] [rbp+60h] BYREF
  _QWORD v60[16]; // [rsp+F0h] [rbp+C0h] BYREF

  v11 = 0;
  PoolHandle = a6;
  v48 = a7;
  v57 = a9;
  v58 = a10;
  v55 = a11;
  SrcNetBufferList = a2;
  v50 = 0;
  v52 = 0;
  MdlChain = 0;
  memset(v60, 0, sizeof(v60));
  memset(v59, 0, sizeof(v59));
  v13 = 0;
  v45 = 0;
  LOBYTE(v14) = 0;
  v49 = v14;
  v15 = 0;
  v46 = 0;
  if ( a5 )
  {
    v16 = *(_DWORD *)(a5 + 28);
    v49 = ((v16 - 1) & 0xFFFFFFFD) == 0;
    if ( v16 == 2 )
    {
      v42 = (*(_BYTE *)a5 & 4) == 0;
      v45 = 1;
      if ( !v42 )
      {
        v15 = 2;
        v46 = 1;
      }
    }
  }
  v17 = qword_140224C88;
  v18 = 4;
  if ( qword_140224C88 && *(_BYTE *)(qword_140224C88 + 48) )
    v18 = *(_DWORD *)(qword_140224C88 + 16);
  v19 = 24LL * v18;
  v20 = v19 + 15;
  if ( v19 + 15 < v19 )
    v20 = 0xFFFFFFFFFFFFFF0LL;
  v21 = alloca(v20 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( a3 != 1 || *(_QWORD *)(qword_140224C88 + 32) )
  {
    v59[0] = -267522035;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v13 = 0;
    v59[3] = CurrentProcessorNumber;
    LOBYTE(v59[1]) = 0;
    *(_QWORD *)&v59[6] = 0;
    v59[2] = a3 & 1;
    v23 = *(_QWORD *)(v17 + 32) != 0;
    *(_QWORD *)&v59[4] = 1;
    memset(&v59[11], 0, 24);
    LOBYTE(v59[10]) = 0;
    v59[2] |= v23 ? 4 : 0;
    *(_QWORD *)&v59[8] = &v59[14];
    if ( &v45 )
    {
      v59[17] = v18;
      *(_QWORD *)&v59[18] = &v45;
    }
    else
    {
      v59[17] = 0;
      *(_QWORD *)&v59[18] = 0;
    }
    *(_QWORD *)&v59[20] = v17;
  }
  v24 = 0;
  NetBufferList = 0;
  v47 = 0;
  LOBYTE(v13) = 14;
  v25 = SegLibOffloadIteratorInitialize((unsigned int)v60, (_DWORD)SrcNetBufferList, v13, a5, v15, v55);
  if ( v25 >= 0 )
  {
    for ( i = &NetBufferList; ; i = &v36->Next )
    {
      v27 = SegLibOffloadIteratorPacketSize(v60);
      DataLength = v27;
      if ( BYTE8(xmmword_140224C90) )
      {
        MdlAndDataPpl = SegLibPvtAllocateMdlAndDataPpl(v27, (__int64)&v52, (__int64)&v47);
        v30 = v52;
        v25 = MdlAndDataPpl;
        v11 = MdlChain;
        v31 = v47;
        v50 = v52;
      }
      else
      {
        v39 = ((unsigned int)MmSizeOfMdl((PVOID)0xFFF, v27) + 7) & 0xFFFFFFF8;
        v31 = v39 + DataLength;
        Pool2 = (struct _MDL *)ExAllocatePool2(66, (unsigned int)(v39 + DataLength), 1819243340);
        v41 = Pool2;
        if ( Pool2 )
        {
          Pool2->Next = 0;
          Pool2->ByteCount = DataLength;
          v30 = (__int64)Pool2 + v39;
          v50 = v30;
          Pool2->ByteOffset = v30 & 0xFFF;
          Pool2->Size = 8 * (((DataLength + (v30 & 0xFFF) + 4095) >> 12) + 6);
          Pool2->MdlFlags = 0;
          Pool2->StartVa = (void *)(v30 & 0xFFFFFFFFFFFFF000uLL);
          MmBuildMdlForNonPagedPool(Pool2);
          v11 = v41;
          MdlChain = v41;
          v25 = 0;
          v52 = v30;
        }
        else
        {
          v30 = v50;
          v25 = -1073741670;
          v31 = 0;
        }
      }
      if ( v25 < 0 )
        break;
      v25 = SegLibDeferredOffloadIteratorCopyPacket((__int64)v59, (__int64)v60, (unsigned int)DataLength, (char *)v30);
      if ( v25 < 0 )
      {
        LOBYTE(v32) = 1;
        BLFlushBatchOpContextEx(v59, 0, v32);
        ExFreePoolWithTag(v11, 0);
        break;
      }
      v33 = v48;
      NetBufferAndNetBufferList = NdisAllocateNetBufferAndNetBufferList(PoolHandle, v48, 0, v11, 0, DataLength);
      v36 = NetBufferAndNetBufferList;
      if ( !NetBufferAndNetBufferList )
      {
        LOBYTE(v35) = 1;
        v47 = 0;
        BLFlushBatchOpContextEx(v59, 0, v35);
        ExFreePoolWithTag(v11, 0);
        v25 = -1073741670;
        break;
      }
      v47 = v33 + 544;
      v24 += v33 + 544 + v31;
      if ( v49 )
      {
        NdisCopyReceiveNetBufferListInfo(NetBufferAndNetBufferList, SrcNetBufferList);
        v36->NetBufferListInfo[22] = 0;
      }
      else
      {
        NdisCopySendNetBufferListInfo(NetBufferAndNetBufferList, SrcNetBufferList);
      }
      if ( v45 )
      {
        v36->NetBufferListInfo[0] = (void *)v60[5];
        v36->NetBufferListInfo[22] = (void *)v60[12];
        v36->NetBufferListInfo[23] = (void *)LODWORD(v60[13]);
        v36->NetBufferListInfo[3] = 0;
        v36->NetBufferListInfo[2] = 0;
        v36->NetBufferListInfo[17] = 0;
      }
      v23 = v46 != 0;
      *i = v36;
      if ( !(unsigned __int8)SegLibOffloadIteratorNext(v60, v23 ? (unsigned int)DataLength : 0) )
      {
        LOBYTE(v37) = 1;
        BLFlushBatchOpContextEx(v59, 0, v37);
        v25 = 0;
        *v57 = NetBufferList;
        goto LABEL_29;
      }
    }
  }
  v43 = NetBufferList;
  if ( NetBufferList )
  {
    do
    {
      Alignment = (struct _NET_BUFFER_LIST *)v43->Link.Alignment;
      v43->Link.Alignment = 0;
      NdisFreeNetBufferList(v43);
      v43 = Alignment;
    }
    while ( Alignment );
  }
  v24 = 0;
LABEL_29:
  if ( v58 )
    *v58 = v24;
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x140033a48  push    rbp
0x140033a4a  push    rbx
0x140033a4b  push    rsi
0x140033a4c  push    rdi
0x140033a4d  push    r12
0x140033a4f  push    r13
0x140033a51  push    r14
0x140033a53  push    r15
0x140033a55  sub     rsp, 188h
0x140033a5c  lea     rbp, [rsp+30h]
0x140033a61  mov     rax, cs:__security_cookie
0x140033a68  xor     rax, rbp
0x140033a6b  mov     [rbp+190h+var_50], rax
0x140033a72  mov     rax, [rbp+190h+arg_28]
0x140033a79  lea     rcx, [rbp+190h+var_D0]; void *
0x140033a80  mov     r15, [rbp+190h+arg_20]
0x140033a87  xor     r12d, r12d
0x140033a8a  mov     [rbp+190h+PoolHandle], rax
0x140033a8e  movzx   eax, [rbp+190h+arg_30]
0x140033a95  mov     word ptr [rbp+190h+var_18C+4], ax
0x140033a99  mov     rax, [rbp+190h+arg_40]
0x140033aa0  mov     [rbp+190h+var_148], rax
0x140033aa4  mov     rax, [rbp+190h+arg_48]
0x140033aab  mov     [rbp+190h+var_140], rax
0x140033aaf  mov     rax, [rbp+190h+arg_50]
0x140033ab6  mov     [rbp+190h+var_158], rax
0x140033aba  xor     eax, eax
0x140033abc  movzx   r14d, r8b
0x140033ac0  mov     r8d, 80h; Size
0x140033ac6  mov     [rbp+190h+SrcNetBufferList], rdx
0x140033aca  xor     edx, edx; Val
0x140033acc  mov     [rbp+190h+var_180], rax
0x140033ad0  mov     [rbp+190h+var_170], rax
0x140033ad4  mov     [rbp+190h+MdlChain], r12
0x140033ad8  call    memset
0x140033add  xor     edx, edx; Val
0x140033adf  lea     r8d, [r12+60h]; Size
0x140033ae4  lea     rcx, [rbp+190h+var_130]; void *
0x140033ae8  call    memset
0x140033aed  xor     r8d, r8d
0x140033af0  lea     r9d, [r12+1]
0x140033af5  mov     [rbp+190h+var_190], r8b
0x140033af9  mov     dl, r8b
0x140033afc  mov     [rbp+190h+var_184], edx
0x140033aff  mov     r13d, r8d
0x140033b02  mov     [rbp+190h+var_18F], r8b
0x140033b06  test    r15, r15
0x140033b09  jz      short loc_140033B2A
0x140033b0b  mov     ecx, [r15+1Ch]
0x140033b0f  movzx   edx, dl
0x140033b12  lea     eax, [rcx-1]
0x140033b15  test    eax, 0FFFFFFFDh
0x140033b1a  cmovz   edx, r9d
0x140033b1e  mov     [rbp+190h+var_184], edx
0x140033b21  cmp     ecx, 2
0x140033b24  jz      loc_140033EA3
0x140033b2a  mov     rbx, cs:qword_140224C88
0x140033b31  mov     edi, 4
0x140033b36  test    rbx, rbx
0x140033b39  jz      short loc_140033B44
0x140033b3b  cmp     [rbx+30h], r8b
0x140033b3f  jz      short loc_140033B44
0x140033b41  mov     edi, [rbx+10h]
0x140033b44  mov     eax, edi
0x140033b46  lea     rcx, [rax+rax*2]
0x140033b4a  shl     rcx, 3
0x140033b4e  lea     rax, [rcx+0Fh]
0x140033b52  cmp     rax, rcx
0x140033b55  ja      short loc_140033B61
0x140033b57  mov     rax, 0FFFFFFFFFFFFFF0h
0x140033b61  and     rax, 0FFFFFFFFFFFFFFF0h
0x140033b65  call    __chkstk_0
0x140033b6a  sub     rsp, rax
0x140033b6d  lea     rsi, [rsp+1C0h+var_190]
0x140033b72  cmp     r14b, r9b
0x140033b75  jz      loc_140033D70
0x140033b7b  xor     ecx, ecx; ProcNumber
0x140033b7d  mov     [rbp+190h+var_130], 0F00DF00Dh
0x140033b84  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140033b8b  nop     dword ptr [rax+rax+00h]
0x140033b90  xor     r8d, r8d
0x140033b93  mov     [rbp+190h+var_124], eax
0x140033b96  mov     edx, r14d
0x140033b99  mov     [rbp+190h+var_12C], r8b
0x140033b9d  and     edx, 1
0x140033ba0  mov     [rbp+190h+var_118], r8
0x140033ba4  mov     [rbp+190h+var_128], edx
0x140033ba7  mov     rax, [rbx+20h]
0x140033bab  neg     rax
0x140033bae  mov     [rbp+190h+var_120], 1
0x140033bb6  lea     rax, [rbp+190h+var_F8]
0x140033bbd  mov     [rbp+190h+var_100], r8
0x140033bc4  sbb     ecx, ecx
0x140033bc6  mov     [rbp+190h+var_104], r8d
0x140033bcd  and     ecx, 4
0x140033bd0  mov     [rbp+190h+var_108], r8b
0x140033bd7  or      ecx, edx
0x140033bd9  mov     [rbp+190h+var_F8], r8
0x140033be0  mov     [rbp+190h+var_128], ecx
0x140033be3  mov     [rbp+190h+var_F0], r8d
0x140033bea  mov     [rbp+190h+var_110], rax
0x140033bf1  test    rsi, rsi
0x140033bf4  jz      loc_140033D5D
0x140033bfa  mov     [rbp+190h+var_EC], edi
0x140033c00  mov     [rbp+190h+var_E8], rsi
0x140033c07  mov     [rbp+190h+var_E0], rbx
0x140033c0e  mov     rax, [rbp+190h+var_158]
0x140033c12  lea     rcx, [rbp+190h+var_D0]
0x140033c19  mov     rdx, [rbp+190h+SrcNetBufferList]
0x140033c1d  mov     r14d, r8d
0x140033c20  mov     [rbp+190h+NetBufferList], r8
0x140033c24  mov     r9, r15
0x140033c27  mov     dword ptr [rbp+190h+var_18C], r8d
0x140033c2b  mov     r8b, 0Eh
0x140033c2e  mov     [rsp+1C0h+DataLength], rax
0x140033c33  mov     [rsp+1C0h+DataOffset], r13d
0x140033c38  call    SegLibOffloadIteratorInitialize
0x140033c3d  mov     edi, eax
0x140033c3f  test    eax, eax
0x140033c41  js      loc_140033F5C
0x140033c47  lea     r13, [rbp+190h+NetBufferList]
0x140033c4b  lea     rcx, [rbp+190h+var_D0]
0x140033c52  call    SegLibOffloadIteratorPacketSize
0x140033c57  cmp     byte ptr cs:xmmword_140224C90+8, 0
0x140033c5e  mov     esi, eax
0x140033c60  jz      loc_140033DF0
0x140033c66  mov     r8, qword ptr cs:xmmword_140224C90
0x140033c6d  lea     rax, [rbp+190h+var_18C]
0x140033c71  mov     [rsp+1C0h+DataLength], rax; __int64
0x140033c76  lea     r9, [rbp+190h+MdlChain]
0x140033c7a  lea     rax, [rbp+190h+var_170]
0x140033c7e  mov     ecx, esi; Length
0x140033c80  mov     qword ptr [rsp+1C0h+DataOffset], rax; __int64
0x140033c85  call    SegLibPvtAllocateMdlAndDataPpl
0x140033c8a  mov     rbx, [rbp+190h+var_170]
0x140033c8e  mov     edi, eax
0x140033c90  mov     r12, [rbp+190h+MdlChain]
0x140033c94  mov     r15d, dword ptr [rbp+190h+var_18C]
0x140033c98  mov     [rbp+190h+var_180], rbx
0x140033c9c  test    edi, edi
0x140033c9e  js      loc_140033F5C
0x140033ca4  mov     r9, rbx
0x140033ca7  lea     rdx, [rbp+190h+var_D0]
0x140033cae  mov     r8d, esi
0x140033cb1  lea     rcx, [rbp+190h+var_130]; int
0x140033cb5  call    SegLibDeferredOffloadIteratorCopyPacket
0x140033cba  mov     edi, eax
0x140033cbc  test    eax, eax
0x140033cbe  js      loc_140033DCC
0x140033cc4  movzx   edi, word ptr [rbp+190h+var_18C+4]
0x140033cc8  xor     r8d, r8d; ContextBackFill
0x140033ccb  mov     rcx, [rbp+190h+PoolHandle]; PoolHandle
0x140033ccf  movzx   edx, di; ContextSize
0x140033cd2  mov     [rsp+1C0h+DataLength], rsi; DataLength
0x140033cd7  mov     r9, r12; MdlChain
0x140033cda  mov     [rsp+1C0h+DataOffset], r8d; DataOffset
0x140033cdf  call    cs:__imp_NdisAllocateNetBufferAndNetBufferList
0x140033ce6  nop     dword ptr [rax+rax+00h]
0x140033ceb  mov     rbx, rax
0x140033cee  test    rax, rax
0x140033cf1  jz      loc_140033F31
0x140033cf7  mov     rdx, [rbp+190h+SrcNetBufferList]; SrcNetBufferList
0x140033cfb  lea     ecx, [rdi+220h]
0x140033d01  add     r14d, r15d
0x140033d04  mov     dword ptr [rbp+190h+var_18C], ecx
0x140033d07  add     r14d, ecx
0x140033d0a  mov     rcx, rax; DestNetBufferList
0x140033d0d  cmp     byte ptr [rbp+190h+var_184], 0
0x140033d11  jz      loc_140033ED1
0x140033d17  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x140033d1e  nop     dword ptr [rax+rax+00h]
0x140033d23  mov     qword ptr [rbx+140h], 0
0x140033d2e  cmp     [rbp+190h+var_190], 0
0x140033d32  jnz     loc_140033EE2
0x140033d38  mov     al, [rbp+190h+var_18F]
0x140033d3b  lea     rcx, [rbp+190h+var_D0]
0x140033d42  neg     al
0x140033d44  mov     [r13+0], rbx
0x140033d48  sbb     edx, edx
0x140033d4a  and     edx, esi
0x140033d4c  call    SegLibOffloadIteratorNext
0x140033d51  test    al, al
0x140033d53  jz      short loc_140033D7F
0x140033d55  mov     r13, rbx
0x140033d58  jmp     loc_140033C4B
0x140033d5d  mov     [rbp+190h+var_EC], r8d
0x140033d64  mov     [rbp+190h+var_E8], r8
0x140033d6b  jmp     loc_140033C07
0x140033d70  cmp     [rbx+20h], r8
0x140033d74  jnz     loc_140033B7B
0x140033d7a  jmp     loc_140033C0E
0x140033d7f  mov     r8b, 1
0x140033d82  lea     rcx, [rbp+190h+var_130]
0x140033d86  xor     edx, edx
0x140033d88  call    BLFlushBatchOpContextEx
0x140033d8d  mov     rcx, [rbp+190h+var_148]
0x140033d91  xor     edi, edi
0x140033d93  mov     rax, [rbp+190h+NetBufferList]
0x140033d97  mov     [rcx], rax
0x140033d9a  mov     rax, [rbp+190h+var_140]
0x140033d9e  test    rax, rax
0x140033da1  jz      short loc_140033DA6
0x140033da3  mov     [rax], r14d
0x140033da6  mov     eax, edi
0x140033da8  mov     rcx, [rbp+190h+var_50]
0x140033daf  xor     rcx, rbp; StackCookie
0x140033db2  call    __security_check_cookie
0x140033db7  lea     rsp, [rbp+158h]
0x140033dbe  pop     r15
0x140033dc0  pop     r14
0x140033dc2  pop     r13
0x140033dc4  pop     r12
0x140033dc6  pop     rdi
0x140033dc7  pop     rsi
0x140033dc8  pop     rbx
0x140033dc9  pop     rbp
0x140033dca  retn
0x140033dcc  mov     r8b, 1
0x140033dcf  lea     rcx, [rbp+190h+var_130]
0x140033dd3  xor     edx, edx
0x140033dd5  call    BLFlushBatchOpContextEx
0x140033dda  xor     edx, edx; Tag
0x140033ddc  mov     rcx, r12; P
0x140033ddf  call    cs:__imp_ExFreePoolWithTag
0x140033de6  nop     dword ptr [rax+rax+00h]
0x140033deb  jmp     loc_140033F5C
0x140033df0  mov     rdx, rsi; Length
0x140033df3  mov     ecx, 0FFFh; Base
0x140033df8  call    cs:__imp_MmSizeOfMdl
0x140033dff  nop     dword ptr [rax+rax+00h]
0x140033e04  mov     ecx, 42h ; 'B'
0x140033e09  mov     r8d, 6C6F734Ch
0x140033e0f  lea     ebx, [rax+7]
0x140033e12  and     ebx, 0FFFFFFF8h
0x140033e15  lea     r15d, [rbx+rsi]
0x140033e19  mov     edx, r15d
0x140033e1c  call    cs:__imp_ExAllocatePool2
0x140033e23  nop     dword ptr [rax+rax+00h]
0x140033e28  mov     rdi, rax
0x140033e2b  test    rax, rax
0x140033e2e  jz      loc_140033EC0
0x140033e34  lea     edx, [rbx+rax]
0x140033e37  mov     qword ptr [rax], 0
0x140033e3e  mov     r8d, 0FFFh
0x140033e44  mov     [rdi+28h], esi
0x140033e47  mov     ecx, edx
0x140033e49  add     rbx, rdi
0x140033e4c  and     rcx, r8
0x140033e4f  mov     [rbp+190h+var_180], rbx
0x140033e53  add     rcx, r8
0x140033e56  and     edx, r8d
0x140033e59  add     rcx, rsi
0x140033e5c  mov     [rdi+2Ch], edx
0x140033e5f  shr     rcx, 0Ch
0x140033e63  add     cx, 6
0x140033e67  shl     cx, 3
0x140033e6b  mov     [rax+8], cx
0x140033e6f  xor     eax, eax
0x140033e71  mov     [rdi+0Ah], ax
0x140033e75  mov     rcx, rdi; MemoryDescriptorList
0x140033e78  mov     rax, rbx
0x140033e7b  and     rax, 0FFFFFFFFFFFFF000h
0x140033e81  mov     [rdi+20h], rax
0x140033e85  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140033e8c  nop     dword ptr [rax+rax+00h]
0x140033e91  mov     r12, rdi
0x140033e94  mov     [rbp+190h+MdlChain], rdi
0x140033e98  xor     edi, edi
0x140033e9a  mov     [rbp+190h+var_170], rbx
0x140033e9e  jmp     loc_140033C9C
0x140033ea3  test    byte ptr [r15], 4
0x140033ea7  mov     [rbp+190h+var_190], r9b
0x140033eab  jz      loc_140033B2A
0x140033eb1  mov     r13d, 2
0x140033eb7  mov     [rbp+190h+var_18F], r9b
0x140033ebb  jmp     loc_140033B2A
0x140033ec0  mov     rbx, [rbp+190h+var_180]
0x140033ec4  mov     edi, 0C000009Ah
0x140033ec9  xor     r15d, r15d
0x140033ecc  jmp     loc_140033C9C
0x140033ed1  call    cs:__imp_NdisCopySendNetBufferListInfo
0x140033ed8  nop     dword ptr [rax+rax+00h]
0x140033edd  jmp     loc_140033D2E
0x140033ee2  mov     rax, [rbp+190h+var_A8]
0x140033ee9  mov     [rbx+90h], rax
0x140033ef0  mov     rax, [rbp+190h+var_70]
0x140033ef7  mov     [rbx+140h], rax
0x140033efe  mov     eax, [rbp+190h+var_68]
0x140033f04  mov     [rbx+148h], rax
0x140033f0b  mov     qword ptr [rbx+0A8h], 0
0x140033f16  mov     qword ptr [rbx+0A0h], 0
0x140033f21  mov     qword ptr [rbx+118h], 0
0x140033f2c  jmp     loc_140033D38
0x140033f31  mov     r8b, 1
0x140033f34  mov     dword ptr [rbp+190h+var_18C], 0
0x140033f3b  xor     edx, edx
0x140033f3d  lea     rcx, [rbp+190h+var_130]
0x140033f41  call    BLFlushBatchOpContextEx
0x140033f46  xor     edx, edx; Tag
0x140033f48  mov     rcx, r12; P
  ... truncated ...
```
