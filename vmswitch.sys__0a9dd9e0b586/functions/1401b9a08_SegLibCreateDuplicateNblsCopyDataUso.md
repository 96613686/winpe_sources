# SegLibCreateDuplicateNblsCopyDataUso

- ea: `0x1401b9a08`
- end: `0x1401b9ef3`
- name: `SegLibCreateDuplicateNblsCopyDataUso`
- size: `1259`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x1400143ac`

## callees

- `0x140004ee0`
- `0x140006620`
- `0x140033fec`
- `0x1400346f0`
- `0x140034760`
- `0x140047f30`
- `0x1401b9a08`
- `0x1401b9efc`
- `0x1401ba944`
- `0x1401bbbc2`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b9b3f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b9b3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b9e64`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b9e8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b9e64`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b9e8b`
- `NDIS!NdisFreeNetBufferList` at `0x1401b9eaa`
- `NDIS!NdisFreeNetBufferList` at `0x1401b9eaa`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1401b9d62`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1401b9d62`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x1401b9d4d`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x1401b9d4d`

## pseudocode

```c
__int64 __fastcall SegLibCreateDuplicateNblsCopyDataUso(
        __int64 a1,
        struct _NET_BUFFER_LIST *a2,
        char a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned __int16 a7,
        int a8,
        PNET_BUFFER_LIST *a9,
        _DWORD *a10)
{
  int v10; // r12d
  BOOL v12; // r8d
  BOOL v13; // edx
  int v14; // ecx
  __int64 v15; // rbx
  unsigned int v16; // edi
  unsigned __int64 v17; // rcx
  __int64 v18; // rax
  void *v19; // rsp
  ULONG CurrentProcessorNumber; // eax
  bool v21; // cf
  int v22; // edi
  char v23; // r15
  unsigned int v24; // esi
  __int64 v25; // r14
  int v26; // r13d
  unsigned int v27; // ebx
  int MdlAndDataPpl; // eax
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // r8
  int v32; // r12d
  struct _NET_BUFFER_LIST *NetBufferAndNetBufferList; // rax
  __int64 v34; // r8
  struct _NET_BUFFER_LIST *v35; // rbx
  void **v36; // rdi
  __int64 v37; // r8
  unsigned int v38; // eax
  PNET_BUFFER_LIST v39; // rcx
  struct _NET_BUFFER_LIST *Alignment; // rbx
  int v42; // [rsp+20h] [rbp-20h]
  int v43; // [rsp+40h] [rbp+0h] BYREF
  unsigned __int16 v44; // [rsp+44h] [rbp+4h]
  BOOL v45; // [rsp+48h] [rbp+8h]
  BOOL v46; // [rsp+4Ch] [rbp+Ch]
  PVOID P; // [rsp+50h] [rbp+10h]
  __int64 v48; // [rsp+58h] [rbp+18h] BYREF
  PNET_BUFFER_LIST SrcNetBufferList; // [rsp+60h] [rbp+20h]
  PNET_BUFFER_LIST NetBufferList; // [rsp+68h] [rbp+28h] BYREF
  PNET_BUFFER_LIST *p_NetBufferList; // [rsp+70h] [rbp+30h]
  int v52[2]; // [rsp+78h] [rbp+38h]
  PNET_BUFFER_LIST *v53; // [rsp+80h] [rbp+40h]
  _DWORD *v54; // [rsp+88h] [rbp+48h]
  int v55[24]; // [rsp+90h] [rbp+50h] BYREF
  _QWORD v56[16]; // [rsp+F0h] [rbp+B0h] BYREF

  v10 = 0;
  *(_QWORD *)v52 = a6;
  v44 = a7;
  v53 = a9;
  SrcNetBufferList = a2;
  v54 = a10;
  P = 0;
  v48 = 0;
  memset(v56, 0, sizeof(v56));
  memset(v55, 0, sizeof(v55));
  LOBYTE(v12) = 0;
  v45 = v12;
  LOBYTE(v13) = 0;
  v46 = v13;
  if ( a5 )
  {
    v14 = *(_DWORD *)(a5 + 28);
    v12 = ((v14 - 1) & 0xFFFFFFFD) == 0;
    v45 = v12;
    v46 = v14 == 2;
  }
  v15 = qword_140224C88;
  v16 = 4;
  if ( qword_140224C88 && *(_BYTE *)(qword_140224C88 + 48) )
    v16 = *(_DWORD *)(qword_140224C88 + 16);
  v17 = 24LL * v16;
  v18 = v17 + 15;
  if ( v17 + 15 < v17 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( a3 != 1 || *(_QWORD *)(qword_140224C88 + 32) )
  {
    v55[0] = -267522035;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    LOBYTE(v55[1]) = 0;
    v55[3] = CurrentProcessorNumber;
    v55[2] = a3 & 1;
    *(_QWORD *)&v55[6] = 0;
    v21 = *(_QWORD *)(v15 + 32) != 0;
    *(_QWORD *)&v55[4] = 1;
    memset(&v55[11], 0, 24);
    LOBYTE(v55[10]) = 0;
    v55[2] |= v21 ? 4 : 0;
    *(_QWORD *)&v55[8] = &v55[14];
    if ( &v43 )
    {
      v55[17] = v16;
      *(_QWORD *)&v55[18] = &v43;
    }
    else
    {
      v55[17] = 0;
      *(_QWORD *)&v55[18] = 0;
    }
    *(_QWORD *)&v55[20] = v15;
  }
  p_NetBufferList = &NetBufferList;
  NetBufferList = 0;
  v43 = 0;
  v22 = SegLibOffloadUsoIteratorInitialize((unsigned int)v56, (_DWORD)SrcNetBufferList, v12, a5);
  if ( v22 >= 0 )
  {
    v23 = BYTE1(v56[14]);
    v24 = HIDWORD(v56[8]);
    v25 = v56[4];
    v26 = v56[0];
    while ( 1 )
    {
      if ( v23 == 1 )
      {
        v27 = *(_DWORD *)(v25 + 24) - v24;
      }
      else if ( BYTE6(v56[13]) == 1 )
      {
        if ( LODWORD(v56[9]) == LODWORD(v56[1]) )
          v27 = HIDWORD(v56[0]) + WORD1(v56[2]) - v26 * LODWORD(v56[9]);
        else
          v27 = v26 + WORD1(v56[2]);
      }
      else
      {
        v27 = *(_DWORD *)(v25 + 24);
      }
      if ( BYTE8(xmmword_140224C90) )
        MdlAndDataPpl = SegLibPvtAllocateMdlAndDataPpl(v27, (__int64)&v48, (__int64)&v43);
      else
        MdlAndDataPpl = SegLibPvtAllocateMdlAndData(v27, (__int64)&v43);
      v22 = MdlAndDataPpl;
      if ( MdlAndDataPpl < 0 )
        break;
      if ( BYTE6(v56[13]) == 1 || v23 == 1 )
      {
        v30 = SegLibOffloadUsoIteratorDeferredCopyFragment((__int64)v55, (__int64)v56, v27, (char *)v48);
        v23 = BYTE1(v56[14]);
        v24 = HIDWORD(v56[8]);
        v25 = v56[4];
        v26 = v56[0];
      }
      else
      {
        v30 = SegLibOffloadIteratorDeferredCopyNetBuffer((__int64)v55, (int *)v56, v29, (char *)v48);
      }
      v22 = v30;
      if ( v30 < 0 )
      {
        LOBYTE(v31) = 1;
        BLFlushBatchOpContextEx(v55, 0, v31);
        ExFreePoolWithTag(P, 0);
        break;
      }
      v32 = v43 + v10;
      NetBufferAndNetBufferList = (struct _NET_BUFFER_LIST *)SegLibPvtAllocateNetBufferAndNetBufferList(
                                                               v52[0],
                                                               v44,
                                                               v31,
                                                               (int)P,
                                                               v42,
                                                               v27,
                                                               (__int64)&v43);
      v35 = NetBufferAndNetBufferList;
      if ( !NetBufferAndNetBufferList )
      {
        LOBYTE(v34) = 1;
        BLFlushBatchOpContextEx(v55, 0, v34);
        ExFreePoolWithTag(P, 0);
        v22 = -1073741670;
        break;
      }
      v10 = v43 + v32;
      v36 = &NetBufferAndNetBufferList->NetBufferListInfo[17];
      if ( v45 )
      {
        NdisCopyReceiveNetBufferListInfo(NetBufferAndNetBufferList, SrcNetBufferList);
        *v36 = 0;
      }
      else
      {
        NdisCopySendNetBufferListInfo(NetBufferAndNetBufferList, SrcNetBufferList);
      }
      if ( v46 )
      {
        v35->NetBufferListInfo[0] = (void *)v56[5];
        v35->NetBufferListInfo[3] = 0;
        v35->NetBufferListInfo[22] = 0;
        *v36 = 0;
      }
      *p_NetBufferList = v35;
      if ( BYTE6(v56[13]) == 1 )
      {
        if ( v23 != 1 )
        {
          LODWORD(v56[8]) += v26;
          v24 += v26;
          ++LODWORD(v56[9]);
          v38 = HIDWORD(v56[0]);
          goto LABEL_45;
        }
      }
      else if ( v23 != 1 )
      {
        v56[4] = *(_QWORD *)v25;
        v25 = v56[4];
        if ( !v56[4] )
          goto LABEL_41;
        goto LABEL_47;
      }
      v38 = *(_DWORD *)(v25 + 24);
LABEL_45:
      HIDWORD(v56[8]) = v24;
      if ( v24 >= v38 )
      {
LABEL_41:
        LOBYTE(v37) = 1;
        BLFlushBatchOpContextEx(v55, 0, v37);
        v22 = 0;
        *v53 = NetBufferList;
        goto LABEL_53;
      }
      SegLibPvtReduceMdlChain(&v56[6], &v56[8]);
      v23 = BYTE1(v56[14]);
      v24 = HIDWORD(v56[8]);
      v25 = v56[4];
      v26 = v56[0];
LABEL_47:
      p_NetBufferList = &v35->Next;
    }
  }
  v39 = NetBufferList;
  if ( NetBufferList )
  {
    do
    {
      Alignment = (struct _NET_BUFFER_LIST *)v39->Link.Alignment;
      v39->Link.Alignment = 0;
      NdisFreeNetBufferList(v39);
      v39 = Alignment;
    }
    while ( Alignment );
  }
  v10 = 0;
LABEL_53:
  if ( v54 )
    *v54 = v10;
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1401b9a08  push    rbp
0x1401b9a0a  push    rbx
0x1401b9a0b  push    rsi
0x1401b9a0c  push    rdi
0x1401b9a0d  push    r12
0x1401b9a0f  push    r13
0x1401b9a11  push    r14
0x1401b9a13  push    r15
0x1401b9a15  sub     rsp, 188h
0x1401b9a1c  lea     rbp, [rsp+40h]
0x1401b9a21  mov     rax, cs:__security_cookie
0x1401b9a28  xor     rax, rbp
0x1401b9a2b  mov     [rbp+180h+var_50], rax
0x1401b9a32  mov     rax, [rbp+180h+arg_28]
0x1401b9a39  lea     rcx, [rbp+180h+var_D0]; void *
0x1401b9a40  mov     r14, [rbp+180h+arg_20]
0x1401b9a47  xor     r12d, r12d
0x1401b9a4a  mov     r13, [rbp+180h+arg_50]
0x1401b9a51  mov     qword ptr [rbp+180h+var_148], rax
0x1401b9a55  movzx   eax, [rbp+180h+arg_30]
0x1401b9a5c  mov     word ptr [rbp+180h+var_180+4], ax
0x1401b9a60  mov     rax, [rbp+180h+arg_40]
0x1401b9a67  mov     [rbp+180h+var_140], rax
0x1401b9a6b  mov     rax, [rbp+180h+arg_48]
0x1401b9a72  movzx   r15d, r8b
0x1401b9a76  mov     r8d, 80h; Size
0x1401b9a7c  mov     [rbp+180h+SrcNetBufferList], rdx
0x1401b9a80  xor     edx, edx; Val
0x1401b9a82  mov     [rbp+180h+var_138], rax
0x1401b9a86  mov     [rbp+180h+P], r12
0x1401b9a8a  mov     [rbp+180h+var_168], r12
0x1401b9a8e  call    memset
0x1401b9a93  xor     edx, edx; Val
0x1401b9a95  lea     r8d, [r12+60h]; Size
0x1401b9a9a  lea     rcx, [rbp+180h+var_130]; void *
0x1401b9a9e  call    memset
0x1401b9aa3  lea     r9d, [r12+1]
0x1401b9aa8  mov     r8b, r12b
0x1401b9aab  mov     [rbp+180h+var_178], r8d
0x1401b9aaf  mov     dl, r12b
0x1401b9ab2  mov     [rbp+180h+var_174], edx
0x1401b9ab5  test    r14, r14
0x1401b9ab8  jz      short loc_1401B9ADF
0x1401b9aba  mov     ecx, [r14+1Ch]
0x1401b9abe  movzx   r8d, r12b
0x1401b9ac2  movzx   edx, dl
0x1401b9ac5  lea     eax, [rcx-1]
0x1401b9ac8  test    eax, 0FFFFFFFDh
0x1401b9acd  cmovz   r8d, r9d
0x1401b9ad1  cmp     ecx, 2
0x1401b9ad4  mov     [rbp+180h+var_178], r8d
0x1401b9ad8  cmovz   edx, r9d
0x1401b9adc  mov     [rbp+180h+var_174], edx
0x1401b9adf  mov     rbx, cs:qword_140224C88
0x1401b9ae6  mov     edi, 4
0x1401b9aeb  test    rbx, rbx
0x1401b9aee  jz      short loc_1401B9AF9
0x1401b9af0  cmp     [rbx+30h], r12b
0x1401b9af4  jz      short loc_1401B9AF9
0x1401b9af6  mov     edi, [rbx+10h]
0x1401b9af9  mov     eax, edi
0x1401b9afb  lea     rcx, [rax+rax*2]
0x1401b9aff  shl     rcx, 3
0x1401b9b03  lea     rax, [rcx+0Fh]
0x1401b9b07  cmp     rax, rcx
0x1401b9b0a  ja      short loc_1401B9B16
0x1401b9b0c  mov     rax, 0FFFFFFFFFFFFFF0h
0x1401b9b16  and     rax, 0FFFFFFFFFFFFFFF0h
0x1401b9b1a  call    __chkstk_0
0x1401b9b1f  sub     rsp, rax
0x1401b9b22  lea     rsi, [rsp+1C0h+var_180]
0x1401b9b27  cmp     r15b, r9b
0x1401b9b2a  jnz     short loc_1401B9B36
0x1401b9b2c  cmp     [rbx+20h], r12
0x1401b9b30  jz      loc_1401B9BC9
0x1401b9b36  xor     ecx, ecx; ProcNumber
0x1401b9b38  mov     [rbp+180h+var_130], 0F00DF00Dh
0x1401b9b3f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b9b46  nop     dword ptr [rax+rax+00h]
0x1401b9b4b  mov     edx, r15d
0x1401b9b4e  mov     [rbp+180h+var_12C], r12b
0x1401b9b52  and     edx, 1
0x1401b9b55  mov     [rbp+180h+var_124], eax
0x1401b9b58  mov     [rbp+180h+var_128], edx
0x1401b9b5b  mov     [rbp+180h+var_118], r12
0x1401b9b5f  mov     rax, [rbx+20h]
0x1401b9b63  neg     rax
0x1401b9b66  mov     [rbp+180h+var_120], 1
0x1401b9b6e  lea     rax, [rbp+180h+var_F8]
0x1401b9b75  mov     [rbp+180h+var_100], r12
0x1401b9b7c  sbb     ecx, ecx
0x1401b9b7e  mov     [rbp+180h+var_104], r12d
0x1401b9b82  and     ecx, 4
0x1401b9b85  mov     [rbp+180h+var_108], r12b
0x1401b9b89  or      ecx, edx
0x1401b9b8b  mov     [rbp+180h+var_F8], r12
0x1401b9b92  mov     [rbp+180h+var_128], ecx
0x1401b9b95  mov     [rbp+180h+var_F0], r12d
0x1401b9b9c  mov     [rbp+180h+var_110], rax
0x1401b9ba0  test    rsi, rsi
0x1401b9ba3  jz      short loc_1401B9BB4
0x1401b9ba5  mov     [rbp+180h+var_EC], edi
0x1401b9bab  mov     [rbp+180h+var_E8], rsi
0x1401b9bb2  jmp     short loc_1401B9BC2
0x1401b9bb4  mov     [rbp+180h+var_EC], r12d
0x1401b9bbb  mov     [rbp+180h+var_E8], r12
0x1401b9bc2  mov     [rbp+180h+var_E0], rbx
0x1401b9bc9  mov     rdx, [rbp+180h+SrcNetBufferList]
0x1401b9bcd  lea     rbx, [rbp+180h+NetBufferList]
0x1401b9bd1  mov     r9, r14
0x1401b9bd4  mov     [rbp+180h+var_150], rbx
0x1401b9bd8  lea     rcx, [rbp+180h+var_D0]
0x1401b9bdf  mov     [rbp+180h+NetBufferList], r12
0x1401b9be3  mov     dword ptr [rbp+180h+var_180], r12d
0x1401b9be7  mov     [rsp+1C0h+var_198], r13
0x1401b9bec  call    SegLibOffloadUsoIteratorInitialize
0x1401b9bf1  mov     edi, eax
0x1401b9bf3  test    eax, eax
0x1401b9bf5  js      loc_1401B9E97
0x1401b9bfb  mov     r15b, [rbp+180h+var_5F]
0x1401b9c02  mov     ecx, 1
0x1401b9c07  mov     esi, [rbp+180h+var_8C]
0x1401b9c0d  mov     r14, [rbp+180h+var_B0]
0x1401b9c14  mov     r13d, [rbp+180h+var_D0]
0x1401b9c1b  cmp     r15b, cl
0x1401b9c1e  jnz     short loc_1401B9C28
0x1401b9c20  mov     ebx, [r14+18h]
0x1401b9c24  sub     ebx, esi
0x1401b9c26  jmp     short loc_1401B9C5C
0x1401b9c28  cmp     [rbp+180h+var_62], cl
0x1401b9c2e  jnz     short loc_1401B9C58
0x1401b9c30  mov     eax, [rbp+180h+var_88]
0x1401b9c36  movzx   ebx, [rbp+180h+var_BE]
0x1401b9c3d  cmp     eax, [rbp+180h+var_C8]
0x1401b9c43  jnz     short loc_1401B9C53
0x1401b9c45  imul    eax, r13d
0x1401b9c49  sub     ebx, eax
0x1401b9c4b  add     ebx, [rbp+180h+var_CC]
0x1401b9c51  jmp     short loc_1401B9C5C
0x1401b9c53  add     ebx, r13d
0x1401b9c56  jmp     short loc_1401B9C5C
0x1401b9c58  mov     ebx, [r14+18h]
0x1401b9c5c  cmp     byte ptr cs:xmmword_140224C90+8, 0
0x1401b9c63  lea     rax, [rbp+180h+var_180]
0x1401b9c67  mov     ecx, ebx; Length
0x1401b9c69  jz      short loc_1401B9C8B
0x1401b9c6b  mov     r8, qword ptr cs:xmmword_140224C90
0x1401b9c72  lea     r9, [rbp+180h+P]
0x1401b9c76  mov     [rsp+1C0h+var_198], rax; __int64
0x1401b9c7b  lea     rax, [rbp+180h+var_168]
0x1401b9c7f  mov     [rsp+1C0h+var_1A0], rax; __int64
0x1401b9c84  call    SegLibPvtAllocateMdlAndDataPpl
0x1401b9c89  jmp     short loc_1401B9C9D
0x1401b9c8b  lea     r9, [rbp+180h+var_168]
0x1401b9c8f  mov     [rsp+1C0h+var_1A0], rax; int
0x1401b9c94  lea     r8, [rbp+180h+P]
0x1401b9c98  call    SegLibPvtAllocateMdlAndData
0x1401b9c9d  mov     edi, eax
0x1401b9c9f  test    eax, eax
0x1401b9ca1  js      loc_1401B9E97
0x1401b9ca7  cmp     [rbp+180h+var_62], 1
0x1401b9cae  mov     r9, [rbp+180h+var_168]
0x1401b9cb2  jz      short loc_1401B9CCC
0x1401b9cb4  cmp     r15b, 1
0x1401b9cb8  jz      short loc_1401B9CCC
0x1401b9cba  lea     rdx, [rbp+180h+var_D0]
0x1401b9cc1  lea     rcx, [rbp+180h+var_130]; int
0x1401b9cc5  call    SegLibOffloadIteratorDeferredCopyNetBuffer
0x1401b9cca  jmp     short loc_1401B9CFA
0x1401b9ccc  mov     r8d, ebx
0x1401b9ccf  lea     rdx, [rbp+180h+var_D0]
0x1401b9cd6  lea     rcx, [rbp+180h+var_130]
0x1401b9cda  call    SegLibOffloadUsoIteratorDeferredCopyFragment
0x1401b9cdf  mov     r15b, [rbp+180h+var_5F]
0x1401b9ce6  mov     esi, [rbp+180h+var_8C]
0x1401b9cec  mov     r14, [rbp+180h+var_B0]
0x1401b9cf3  mov     r13d, [rbp+180h+var_D0]
0x1401b9cfa  mov     edi, eax
0x1401b9cfc  test    eax, eax
0x1401b9cfe  js      loc_1401B9E77
0x1401b9d04  mov     r9, [rbp+180h+P]; int
0x1401b9d08  lea     rcx, [rbp+180h+var_180]
0x1401b9d0c  movzx   edx, word ptr [rbp+180h+var_180+4]; int
0x1401b9d10  add     r12d, dword ptr [rbp+180h+var_180]
0x1401b9d14  mov     [rsp+1C0h+var_190], rcx; __int64
0x1401b9d19  mov     rcx, qword ptr [rbp+180h+var_148]; int
0x1401b9d1d  mov     eax, ebx
0x1401b9d1f  mov     [rsp+1C0h+var_198], rax; SIZE_T
0x1401b9d24  call    SegLibPvtAllocateNetBufferAndNetBufferList
0x1401b9d29  mov     rbx, rax
0x1401b9d2c  test    rax, rax
0x1401b9d2f  jz      loc_1401B9E50
0x1401b9d35  add     r12d, dword ptr [rbp+180h+var_180]
0x1401b9d39  lea     rdi, [rax+118h]
0x1401b9d40  cmp     byte ptr [rbp+180h+var_178], 1
0x1401b9d44  mov     rcx, rax; DestNetBufferList
0x1401b9d47  mov     rdx, [rbp+180h+SrcNetBufferList]; SrcNetBufferList
0x1401b9d4b  jnz     short loc_1401B9D62
0x1401b9d4d  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x1401b9d54  nop     dword ptr [rax+rax+00h]
0x1401b9d59  mov     qword ptr [rdi], 0
0x1401b9d60  jmp     short loc_1401B9D6E
0x1401b9d62  call    cs:__imp_NdisCopySendNetBufferListInfo
0x1401b9d69  nop     dword ptr [rax+rax+00h]
0x1401b9d6e  mov     ecx, 1
0x1401b9d73  cmp     byte ptr [rbp+180h+var_174], cl
0x1401b9d76  jnz     short loc_1401B9DA3
0x1401b9d78  mov     rax, [rbp+180h+var_A8]
0x1401b9d7f  mov     [rbx+90h], rax
0x1401b9d86  mov     qword ptr [rbx+0A8h], 0
0x1401b9d91  mov     qword ptr [rbx+140h], 0
0x1401b9d9c  mov     qword ptr [rdi], 0
0x1401b9da3  mov     rax, [rbp+180h+var_150]
0x1401b9da7  mov     [rax], rbx
0x1401b9daa  cmp     [rbp+180h+var_62], cl
0x1401b9db0  jz      short loc_1401B9DE9
0x1401b9db2  cmp     r15b, cl
0x1401b9db5  jz      short loc_1401B9DEE
0x1401b9db7  mov     rax, [r14]
0x1401b9dba  mov     [rbp+180h+var_B0], rax
0x1401b9dc1  mov     r14, rax
0x1401b9dc4  test    rax, rax
0x1401b9dc7  jnz     short loc_1401B9E47
0x1401b9dc9  mov     r8b, cl
0x1401b9dcc  xor     edx, edx
0x1401b9dce  lea     rcx, [rbp+180h+var_130]
0x1401b9dd2  call    BLFlushBatchOpContextEx
0x1401b9dd7  mov     rcx, [rbp+180h+var_140]
0x1401b9ddb  xor     edi, edi
0x1401b9ddd  mov     rax, [rbp+180h+NetBufferList]
0x1401b9de1  mov     [rcx], rax
0x1401b9de4  jmp     loc_1401B9EC1
0x1401b9de9  cmp     r15b, cl
0x1401b9dec  jnz     short loc_1401B9DF4
0x1401b9dee  mov     eax, [r14+18h]
0x1401b9df2  jmp     short loc_1401B9E0A
0x1401b9df4  add     [rbp+180h+var_90], r13d
0x1401b9dfb  add     esi, r13d
0x1401b9dfe  add     [rbp+180h+var_88], ecx
0x1401b9e04  mov     eax, [rbp+180h+var_CC]
0x1401b9e0a  mov     [rbp+180h+var_8C], esi
0x1401b9e10  cmp     esi, eax
0x1401b9e12  jnb     short loc_1401B9DC9
0x1401b9e14  lea     rdx, [rbp+180h+var_90]
0x1401b9e1b  lea     rcx, [rbp+180h+var_A0]
0x1401b9e22  call    SegLibPvtReduceMdlChain
0x1401b9e27  mov     r15b, [rbp+180h+var_5F]
0x1401b9e2e  mov     ecx, 1
0x1401b9e33  mov     esi, [rbp+180h+var_8C]
0x1401b9e39  mov     r14, [rbp+180h+var_B0]
0x1401b9e40  mov     r13d, [rbp+180h+var_D0]
0x1401b9e47  mov     [rbp+180h+var_150], rbx
0x1401b9e4b  jmp     loc_1401B9C1B
0x1401b9e50  mov     r8b, 1
0x1401b9e53  lea     rcx, [rbp+180h+var_130]
0x1401b9e57  xor     edx, edx
0x1401b9e59  call    BLFlushBatchOpContextEx
0x1401b9e5e  mov     rcx, [rbp+180h+P]; P
0x1401b9e62  xor     edx, edx; Tag
0x1401b9e64  call    cs:__imp_ExFreePoolWithTag
0x1401b9e6b  nop     dword ptr [rax+rax+00h]
0x1401b9e70  mov     edi, 0C000009Ah
0x1401b9e75  jmp     short loc_1401B9E97
0x1401b9e77  mov     r8b, 1
0x1401b9e7a  lea     rcx, [rbp+180h+var_130]
0x1401b9e7e  xor     edx, edx
0x1401b9e80  call    BLFlushBatchOpContextEx
0x1401b9e85  mov     rcx, [rbp+180h+P]; P
0x1401b9e89  xor     edx, edx; Tag
0x1401b9e8b  call    cs:__imp_ExFreePoolWithTag
0x1401b9e92  nop     dword ptr [rax+rax+00h]
0x1401b9e97  mov     rcx, [rbp+180h+NetBufferList]; NetBufferList
0x1401b9e9b  test    rcx, rcx
0x1401b9e9e  jz      short loc_1401B9EBE
0x1401b9ea0  mov     rbx, [rcx]
0x1401b9ea3  mov     qword ptr [rcx], 0
0x1401b9eaa  call    cs:__imp_NdisFreeNetBufferList
0x1401b9eb1  nop     dword ptr [rax+rax+00h]
0x1401b9eb6  mov     rcx, rbx
0x1401b9eb9  test    rbx, rbx
0x1401b9ebc  jnz     short loc_1401B9EA0
0x1401b9ebe  xor     r12d, r12d
0x1401b9ec1  mov     rax, [rbp+180h+var_138]
0x1401b9ec5  test    rax, rax
0x1401b9ec8  jz      short loc_1401B9ECD
0x1401b9eca  mov     [rax], r12d
0x1401b9ecd  mov     eax, edi
0x1401b9ecf  mov     rcx, [rbp+180h+var_50]
0x1401b9ed6  xor     rcx, rbp; StackCookie
0x1401b9ed9  call    __security_check_cookie
0x1401b9ede  lea     rsp, [rbp+148h]
0x1401b9ee5  pop     r15
0x1401b9ee7  pop     r14
0x1401b9ee9  pop     r13
0x1401b9eeb  pop     r12
0x1401b9eed  pop     rdi
0x1401b9eee  pop     rsi
0x1401b9eef  pop     rbx
0x1401b9ef0  pop     rbp
0x1401b9ef1  retn
  ... truncated ...
```
