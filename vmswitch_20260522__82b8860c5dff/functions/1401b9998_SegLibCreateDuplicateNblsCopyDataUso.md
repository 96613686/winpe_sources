# SegLibCreateDuplicateNblsCopyDataUso

- ea: `0x1401b9998`
- end: `0x1401b9e83`
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
- `0x1401b9998`
- `0x1401b9e8c`
- `0x1401ba8d4`
- `0x1401bbb52`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b9acf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401b9acf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b9df4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b9e1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b9df4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401b9e1b`
- `NDIS!NdisFreeNetBufferList` at `0x1401b9e3a`
- `NDIS!NdisFreeNetBufferList` at `0x1401b9e3a`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1401b9cf2`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1401b9cf2`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x1401b9cdd`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x1401b9cdd`

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
0x1401b9998  push    rbp
0x1401b999a  push    rbx
0x1401b999b  push    rsi
0x1401b999c  push    rdi
0x1401b999d  push    r12
0x1401b999f  push    r13
0x1401b99a1  push    r14
0x1401b99a3  push    r15
0x1401b99a5  sub     rsp, 188h
0x1401b99ac  lea     rbp, [rsp+40h]
0x1401b99b1  mov     rax, cs:__security_cookie
0x1401b99b8  xor     rax, rbp
0x1401b99bb  mov     [rbp+180h+var_50], rax
0x1401b99c2  mov     rax, [rbp+180h+arg_28]
0x1401b99c9  lea     rcx, [rbp+180h+var_D0]; void *
0x1401b99d0  mov     r14, [rbp+180h+arg_20]
0x1401b99d7  xor     r12d, r12d
0x1401b99da  mov     r13, [rbp+180h+arg_50]
0x1401b99e1  mov     qword ptr [rbp+180h+var_148], rax
0x1401b99e5  movzx   eax, [rbp+180h+arg_30]
0x1401b99ec  mov     word ptr [rbp+180h+var_180+4], ax
0x1401b99f0  mov     rax, [rbp+180h+arg_40]
0x1401b99f7  mov     [rbp+180h+var_140], rax
0x1401b99fb  mov     rax, [rbp+180h+arg_48]
0x1401b9a02  movzx   r15d, r8b
0x1401b9a06  mov     r8d, 80h; Size
0x1401b9a0c  mov     [rbp+180h+SrcNetBufferList], rdx
0x1401b9a10  xor     edx, edx; Val
0x1401b9a12  mov     [rbp+180h+var_138], rax
0x1401b9a16  mov     [rbp+180h+P], r12
0x1401b9a1a  mov     [rbp+180h+var_168], r12
0x1401b9a1e  call    memset
0x1401b9a23  xor     edx, edx; Val
0x1401b9a25  lea     r8d, [r12+60h]; Size
0x1401b9a2a  lea     rcx, [rbp+180h+var_130]; void *
0x1401b9a2e  call    memset
0x1401b9a33  lea     r9d, [r12+1]
0x1401b9a38  mov     r8b, r12b
0x1401b9a3b  mov     [rbp+180h+var_178], r8d
0x1401b9a3f  mov     dl, r12b
0x1401b9a42  mov     [rbp+180h+var_174], edx
0x1401b9a45  test    r14, r14
0x1401b9a48  jz      short loc_1401B9A6F
0x1401b9a4a  mov     ecx, [r14+1Ch]
0x1401b9a4e  movzx   r8d, r12b
0x1401b9a52  movzx   edx, dl
0x1401b9a55  lea     eax, [rcx-1]
0x1401b9a58  test    eax, 0FFFFFFFDh
0x1401b9a5d  cmovz   r8d, r9d
0x1401b9a61  cmp     ecx, 2
0x1401b9a64  mov     [rbp+180h+var_178], r8d
0x1401b9a68  cmovz   edx, r9d
0x1401b9a6c  mov     [rbp+180h+var_174], edx
0x1401b9a6f  mov     rbx, cs:qword_140224C88
0x1401b9a76  mov     edi, 4
0x1401b9a7b  test    rbx, rbx
0x1401b9a7e  jz      short loc_1401B9A89
0x1401b9a80  cmp     [rbx+30h], r12b
0x1401b9a84  jz      short loc_1401B9A89
0x1401b9a86  mov     edi, [rbx+10h]
0x1401b9a89  mov     eax, edi
0x1401b9a8b  lea     rcx, [rax+rax*2]
0x1401b9a8f  shl     rcx, 3
0x1401b9a93  lea     rax, [rcx+0Fh]
0x1401b9a97  cmp     rax, rcx
0x1401b9a9a  ja      short loc_1401B9AA6
0x1401b9a9c  mov     rax, 0FFFFFFFFFFFFFF0h
0x1401b9aa6  and     rax, 0FFFFFFFFFFFFFFF0h
0x1401b9aaa  call    __chkstk_0
0x1401b9aaf  sub     rsp, rax
0x1401b9ab2  lea     rsi, [rsp+1C0h+var_180]
0x1401b9ab7  cmp     r15b, r9b
0x1401b9aba  jnz     short loc_1401B9AC6
0x1401b9abc  cmp     [rbx+20h], r12
0x1401b9ac0  jz      loc_1401B9B59
0x1401b9ac6  xor     ecx, ecx; ProcNumber
0x1401b9ac8  mov     [rbp+180h+var_130], 0F00DF00Dh
0x1401b9acf  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401b9ad6  nop     dword ptr [rax+rax+00h]
0x1401b9adb  mov     edx, r15d
0x1401b9ade  mov     [rbp+180h+var_12C], r12b
0x1401b9ae2  and     edx, 1
0x1401b9ae5  mov     [rbp+180h+var_124], eax
0x1401b9ae8  mov     [rbp+180h+var_128], edx
0x1401b9aeb  mov     [rbp+180h+var_118], r12
0x1401b9aef  mov     rax, [rbx+20h]
0x1401b9af3  neg     rax
0x1401b9af6  mov     [rbp+180h+var_120], 1
0x1401b9afe  lea     rax, [rbp+180h+var_F8]
0x1401b9b05  mov     [rbp+180h+var_100], r12
0x1401b9b0c  sbb     ecx, ecx
0x1401b9b0e  mov     [rbp+180h+var_104], r12d
0x1401b9b12  and     ecx, 4
0x1401b9b15  mov     [rbp+180h+var_108], r12b
0x1401b9b19  or      ecx, edx
0x1401b9b1b  mov     [rbp+180h+var_F8], r12
0x1401b9b22  mov     [rbp+180h+var_128], ecx
0x1401b9b25  mov     [rbp+180h+var_F0], r12d
0x1401b9b2c  mov     [rbp+180h+var_110], rax
0x1401b9b30  test    rsi, rsi
0x1401b9b33  jz      short loc_1401B9B44
0x1401b9b35  mov     [rbp+180h+var_EC], edi
0x1401b9b3b  mov     [rbp+180h+var_E8], rsi
0x1401b9b42  jmp     short loc_1401B9B52
0x1401b9b44  mov     [rbp+180h+var_EC], r12d
0x1401b9b4b  mov     [rbp+180h+var_E8], r12
0x1401b9b52  mov     [rbp+180h+var_E0], rbx
0x1401b9b59  mov     rdx, [rbp+180h+SrcNetBufferList]
0x1401b9b5d  lea     rbx, [rbp+180h+NetBufferList]
0x1401b9b61  mov     r9, r14
0x1401b9b64  mov     [rbp+180h+var_150], rbx
0x1401b9b68  lea     rcx, [rbp+180h+var_D0]
0x1401b9b6f  mov     [rbp+180h+NetBufferList], r12
0x1401b9b73  mov     dword ptr [rbp+180h+var_180], r12d
0x1401b9b77  mov     [rsp+1C0h+var_198], r13
0x1401b9b7c  call    SegLibOffloadUsoIteratorInitialize
0x1401b9b81  mov     edi, eax
0x1401b9b83  test    eax, eax
0x1401b9b85  js      loc_1401B9E27
0x1401b9b8b  mov     r15b, [rbp+180h+var_5F]
0x1401b9b92  mov     ecx, 1
0x1401b9b97  mov     esi, [rbp+180h+var_8C]
0x1401b9b9d  mov     r14, [rbp+180h+var_B0]
0x1401b9ba4  mov     r13d, [rbp+180h+var_D0]
0x1401b9bab  cmp     r15b, cl
0x1401b9bae  jnz     short loc_1401B9BB8
0x1401b9bb0  mov     ebx, [r14+18h]
0x1401b9bb4  sub     ebx, esi
0x1401b9bb6  jmp     short loc_1401B9BEC
0x1401b9bb8  cmp     [rbp+180h+var_62], cl
0x1401b9bbe  jnz     short loc_1401B9BE8
0x1401b9bc0  mov     eax, [rbp+180h+var_88]
0x1401b9bc6  movzx   ebx, [rbp+180h+var_BE]
0x1401b9bcd  cmp     eax, [rbp+180h+var_C8]
0x1401b9bd3  jnz     short loc_1401B9BE3
0x1401b9bd5  imul    eax, r13d
0x1401b9bd9  sub     ebx, eax
0x1401b9bdb  add     ebx, [rbp+180h+var_CC]
0x1401b9be1  jmp     short loc_1401B9BEC
0x1401b9be3  add     ebx, r13d
0x1401b9be6  jmp     short loc_1401B9BEC
0x1401b9be8  mov     ebx, [r14+18h]
0x1401b9bec  cmp     byte ptr cs:xmmword_140224C90+8, 0
0x1401b9bf3  lea     rax, [rbp+180h+var_180]
0x1401b9bf7  mov     ecx, ebx; Length
0x1401b9bf9  jz      short loc_1401B9C1B
0x1401b9bfb  mov     r8, qword ptr cs:xmmword_140224C90
0x1401b9c02  lea     r9, [rbp+180h+P]
0x1401b9c06  mov     [rsp+1C0h+var_198], rax; __int64
0x1401b9c0b  lea     rax, [rbp+180h+var_168]
0x1401b9c0f  mov     [rsp+1C0h+var_1A0], rax; __int64
0x1401b9c14  call    SegLibPvtAllocateMdlAndDataPpl
0x1401b9c19  jmp     short loc_1401B9C2D
0x1401b9c1b  lea     r9, [rbp+180h+var_168]
0x1401b9c1f  mov     [rsp+1C0h+var_1A0], rax; int
0x1401b9c24  lea     r8, [rbp+180h+P]
0x1401b9c28  call    SegLibPvtAllocateMdlAndData
0x1401b9c2d  mov     edi, eax
0x1401b9c2f  test    eax, eax
0x1401b9c31  js      loc_1401B9E27
0x1401b9c37  cmp     [rbp+180h+var_62], 1
0x1401b9c3e  mov     r9, [rbp+180h+var_168]
0x1401b9c42  jz      short loc_1401B9C5C
0x1401b9c44  cmp     r15b, 1
0x1401b9c48  jz      short loc_1401B9C5C
0x1401b9c4a  lea     rdx, [rbp+180h+var_D0]
0x1401b9c51  lea     rcx, [rbp+180h+var_130]; int
0x1401b9c55  call    SegLibOffloadIteratorDeferredCopyNetBuffer
0x1401b9c5a  jmp     short loc_1401B9C8A
0x1401b9c5c  mov     r8d, ebx
0x1401b9c5f  lea     rdx, [rbp+180h+var_D0]
0x1401b9c66  lea     rcx, [rbp+180h+var_130]
0x1401b9c6a  call    SegLibOffloadUsoIteratorDeferredCopyFragment
0x1401b9c6f  mov     r15b, [rbp+180h+var_5F]
0x1401b9c76  mov     esi, [rbp+180h+var_8C]
0x1401b9c7c  mov     r14, [rbp+180h+var_B0]
0x1401b9c83  mov     r13d, [rbp+180h+var_D0]
0x1401b9c8a  mov     edi, eax
0x1401b9c8c  test    eax, eax
0x1401b9c8e  js      loc_1401B9E07
0x1401b9c94  mov     r9, [rbp+180h+P]; int
0x1401b9c98  lea     rcx, [rbp+180h+var_180]
0x1401b9c9c  movzx   edx, word ptr [rbp+180h+var_180+4]; int
0x1401b9ca0  add     r12d, dword ptr [rbp+180h+var_180]
0x1401b9ca4  mov     [rsp+1C0h+var_190], rcx; __int64
0x1401b9ca9  mov     rcx, qword ptr [rbp+180h+var_148]; int
0x1401b9cad  mov     eax, ebx
0x1401b9caf  mov     [rsp+1C0h+var_198], rax; SIZE_T
0x1401b9cb4  call    SegLibPvtAllocateNetBufferAndNetBufferList
0x1401b9cb9  mov     rbx, rax
0x1401b9cbc  test    rax, rax
0x1401b9cbf  jz      loc_1401B9DE0
0x1401b9cc5  add     r12d, dword ptr [rbp+180h+var_180]
0x1401b9cc9  lea     rdi, [rax+118h]
0x1401b9cd0  cmp     byte ptr [rbp+180h+var_178], 1
0x1401b9cd4  mov     rcx, rax; DestNetBufferList
0x1401b9cd7  mov     rdx, [rbp+180h+SrcNetBufferList]; SrcNetBufferList
0x1401b9cdb  jnz     short loc_1401B9CF2
0x1401b9cdd  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x1401b9ce4  nop     dword ptr [rax+rax+00h]
0x1401b9ce9  mov     qword ptr [rdi], 0
0x1401b9cf0  jmp     short loc_1401B9CFE
0x1401b9cf2  call    cs:__imp_NdisCopySendNetBufferListInfo
0x1401b9cf9  nop     dword ptr [rax+rax+00h]
0x1401b9cfe  mov     ecx, 1
0x1401b9d03  cmp     byte ptr [rbp+180h+var_174], cl
0x1401b9d06  jnz     short loc_1401B9D33
0x1401b9d08  mov     rax, [rbp+180h+var_A8]
0x1401b9d0f  mov     [rbx+90h], rax
0x1401b9d16  mov     qword ptr [rbx+0A8h], 0
0x1401b9d21  mov     qword ptr [rbx+140h], 0
0x1401b9d2c  mov     qword ptr [rdi], 0
0x1401b9d33  mov     rax, [rbp+180h+var_150]
0x1401b9d37  mov     [rax], rbx
0x1401b9d3a  cmp     [rbp+180h+var_62], cl
0x1401b9d40  jz      short loc_1401B9D79
0x1401b9d42  cmp     r15b, cl
0x1401b9d45  jz      short loc_1401B9D7E
0x1401b9d47  mov     rax, [r14]
0x1401b9d4a  mov     [rbp+180h+var_B0], rax
0x1401b9d51  mov     r14, rax
0x1401b9d54  test    rax, rax
0x1401b9d57  jnz     short loc_1401B9DD7
0x1401b9d59  mov     r8b, cl
0x1401b9d5c  xor     edx, edx
0x1401b9d5e  lea     rcx, [rbp+180h+var_130]
0x1401b9d62  call    BLFlushBatchOpContextEx
0x1401b9d67  mov     rcx, [rbp+180h+var_140]
0x1401b9d6b  xor     edi, edi
0x1401b9d6d  mov     rax, [rbp+180h+NetBufferList]
0x1401b9d71  mov     [rcx], rax
0x1401b9d74  jmp     loc_1401B9E51
0x1401b9d79  cmp     r15b, cl
0x1401b9d7c  jnz     short loc_1401B9D84
0x1401b9d7e  mov     eax, [r14+18h]
0x1401b9d82  jmp     short loc_1401B9D9A
0x1401b9d84  add     [rbp+180h+var_90], r13d
0x1401b9d8b  add     esi, r13d
0x1401b9d8e  add     [rbp+180h+var_88], ecx
0x1401b9d94  mov     eax, [rbp+180h+var_CC]
0x1401b9d9a  mov     [rbp+180h+var_8C], esi
0x1401b9da0  cmp     esi, eax
0x1401b9da2  jnb     short loc_1401B9D59
0x1401b9da4  lea     rdx, [rbp+180h+var_90]
0x1401b9dab  lea     rcx, [rbp+180h+var_A0]
0x1401b9db2  call    SegLibPvtReduceMdlChain
0x1401b9db7  mov     r15b, [rbp+180h+var_5F]
0x1401b9dbe  mov     ecx, 1
0x1401b9dc3  mov     esi, [rbp+180h+var_8C]
0x1401b9dc9  mov     r14, [rbp+180h+var_B0]
0x1401b9dd0  mov     r13d, [rbp+180h+var_D0]
0x1401b9dd7  mov     [rbp+180h+var_150], rbx
0x1401b9ddb  jmp     loc_1401B9BAB
0x1401b9de0  mov     r8b, 1
0x1401b9de3  lea     rcx, [rbp+180h+var_130]
0x1401b9de7  xor     edx, edx
0x1401b9de9  call    BLFlushBatchOpContextEx
0x1401b9dee  mov     rcx, [rbp+180h+P]; P
0x1401b9df2  xor     edx, edx; Tag
0x1401b9df4  call    cs:__imp_ExFreePoolWithTag
0x1401b9dfb  nop     dword ptr [rax+rax+00h]
0x1401b9e00  mov     edi, 0C000009Ah
0x1401b9e05  jmp     short loc_1401B9E27
0x1401b9e07  mov     r8b, 1
0x1401b9e0a  lea     rcx, [rbp+180h+var_130]
0x1401b9e0e  xor     edx, edx
0x1401b9e10  call    BLFlushBatchOpContextEx
0x1401b9e15  mov     rcx, [rbp+180h+P]; P
0x1401b9e19  xor     edx, edx; Tag
0x1401b9e1b  call    cs:__imp_ExFreePoolWithTag
0x1401b9e22  nop     dword ptr [rax+rax+00h]
0x1401b9e27  mov     rcx, [rbp+180h+NetBufferList]; NetBufferList
0x1401b9e2b  test    rcx, rcx
0x1401b9e2e  jz      short loc_1401B9E4E
0x1401b9e30  mov     rbx, [rcx]
0x1401b9e33  mov     qword ptr [rcx], 0
0x1401b9e3a  call    cs:__imp_NdisFreeNetBufferList
0x1401b9e41  nop     dword ptr [rax+rax+00h]
0x1401b9e46  mov     rcx, rbx
0x1401b9e49  test    rbx, rbx
0x1401b9e4c  jnz     short loc_1401B9E30
0x1401b9e4e  xor     r12d, r12d
0x1401b9e51  mov     rax, [rbp+180h+var_138]
0x1401b9e55  test    rax, rax
0x1401b9e58  jz      short loc_1401B9E5D
0x1401b9e5a  mov     [rax], r12d
0x1401b9e5d  mov     eax, edi
0x1401b9e5f  mov     rcx, [rbp+180h+var_50]
0x1401b9e66  xor     rcx, rbp; StackCookie
0x1401b9e69  call    __security_check_cookie
0x1401b9e6e  lea     rsp, [rbp+148h]
0x1401b9e75  pop     r15
0x1401b9e77  pop     r14
0x1401b9e79  pop     r13
0x1401b9e7b  pop     r12
0x1401b9e7d  pop     rdi
0x1401b9e7e  pop     rsi
0x1401b9e7f  pop     rbx
0x1401b9e80  pop     rbp
0x1401b9e81  retn
  ... truncated ...
```
