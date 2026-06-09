# VmsNblHelperCreateCloneNbl2507

- ea: `0x1401149f8`
- end: `0x14011502f`
- name: `VmsNblHelperCreateCloneNbl2507`
- size: `1591`
- prototype: `__int64 __usercall@<rax>(PNET_BUFFER_LIST NetBufferList@<rcx>, NDIS_HANDLE NetBufferListPoolHandle@<rdx>, char, char, int, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x14004fd84`

## callees

- `0x1400025a0`
- `0x140003e34`
- `0x140006620`
- `0x140012f34`
- `0x1400478b0`
- `0x140051528`
- `0x140052460`
- `0x14006b248`
- `0x1401149f8`
- `0x1401bbb52`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140114b8c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140114b8c`
- `NDIS!NdisFreeCloneNetBufferList` at `0x140114ff6`
- `NDIS!NdisFreeCloneNetBufferList` at `0x140114ff6`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140114dc4`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140114dc4`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114d1c`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114d82`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114fc3`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114d1c`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114d82`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114fc3`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x140114c9d`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x140114c9d`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140114c7a`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140114fe5`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140114c7a`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140114fe5`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140114ea3`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140114ea3`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140114e8a`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140114e8a`

## string_xrefs

- `0x140114a94`: `VmsNblHelperCreateCloneNbl2507`

## pseudocode

```c
__int64 __fastcall VmsNblHelperCreateCloneNbl2507(
        PNET_BUFFER_LIST NetBufferList,
        NDIS_HANDLE NetBufferListPoolHandle,
        void *a3,
        char a4,
        char a5,
        char a6,
        int a7,
        struct _NET_BUFFER_LIST **a8)
{
  int v10; // r13d
  __int16 v11; // di
  _QWORD *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rsi
  _QWORD *v15; // rax
  __int64 v16; // rax
  _QWORD *v17; // rax
  bool v18; // bl
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // rax
  void *v22; // rsp
  void *v23; // rbx
  struct _NET_BUFFER_LIST *v24; // rsi
  void **v25; // r8
  NDIS_STATUS TxChecksumOffloadInfo; // r14d
  char v27; // r14
  struct _NET_BUFFER_LIST *CloneNetBufferList; // rax
  int v29; // edx
  NDIS_STATUS v30; // eax
  int v31; // edx
  struct _NET_BUFFER *FirstNetBuffer; // rax
  _NET_BUFFER *Alignment; // r12
  _DWORD *v34; // rax
  char v35; // di
  int v36; // edx
  unsigned int v37; // edx
  int v38; // ecx
  int v39; // eax
  int v40; // ecx
  int BytesCopied; // [rsp+28h] [rbp-28h]
  char v43; // [rsp+50h] [rbp+0h] BYREF
  char v44; // [rsp+51h] [rbp+1h]
  char v45; // [rsp+52h] [rbp+2h]
  int v46; // [rsp+54h] [rbp+4h]
  __int16 v47[2]; // [rsp+58h] [rbp+8h] BYREF
  NDIS_HANDLE NetBufferPoolHandle; // [rsp+60h] [rbp+10h]
  ULONG v49; // [rsp+68h] [rbp+18h] BYREF
  struct _NET_BUFFER_LIST **v50; // [rsp+70h] [rbp+20h]
  int v51[24]; // [rsp+80h] [rbp+30h] BYREF
  _UNKNOWN *retaddr; // [rsp+128h] [rbp+D8h]

  v50 = a8;
  NetBufferPoolHandle = a3;
  v44 = a4;
  v43 = 0;
  v45 = 0;
  LOWORD(v10) = 0;
  v46 = 0;
  v49 = 0;
  v11 = 0;
  *(_DWORD *)v47 = 0;
  memset(v51, 0, sizeof(v51));
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( NetBufferList )
    {
      v12 = NetBufferList->NetBufferListInfo[18];
      if ( v12 )
      {
        v13 = v12[2];
        if ( v13 )
        {
          *(_DWORD *)(v13 + 184) = 293;
          *(_QWORD *)(v13 + 176) = "VmsNblHelperCreateCloneNbl2507";
          *(_QWORD *)(v13 + 168) = retaddr;
        }
      }
    }
  }
  v14 = 4;
  if ( byte_1401F96F0 )
    v14 = HIDWORD(qword_1401F96CC);
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( NetBufferList )
    {
      v15 = NetBufferList->NetBufferListInfo[18];
      if ( v15 )
      {
        v16 = v15[2];
        if ( v16 )
        {
          *(_DWORD *)(v16 + 184) = 75;
          *(_QWORD *)(v16 + 176) = "VmsNblIsSourceNicUntrusted";
          *(_QWORD *)(v16 + 168) = retaddr;
        }
      }
    }
  }
  v17 = NetBufferList->NetBufferListInfo[18];
  v18 = 0;
  if ( v17 )
  {
    v19 = v17[2];
    if ( v19 )
    {
      v20 = *(_QWORD *)(v19 + 24);
      if ( v20 )
      {
        if ( *(_DWORD *)(v20 + 1872) == 3 )
          v18 = *(_BYTE *)(v20 + 1877) == 0;
      }
    }
  }
  v21 = 24 * v14 + 15;
  if ( v21 <= 24 * v14 )
    v21 = 0xFFFFFFFFFFFFFF0LL;
  v22 = alloca(v21 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( !v18 || qword_1401F96E0 )
  {
    v51[0] = -267522035;
    v51[3] = KeGetCurrentProcessorNumberEx(0);
    LOBYTE(v51[1]) = 0;
    *(_QWORD *)&v51[6] = 0;
    *(_QWORD *)&v51[4] = 1;
    memset(&v51[11], 0, 24);
    v51[2] = (qword_1401F96E0 != 0 ? 4 : 0) | v18;
    LOBYTE(v51[10]) = 0;
    *(_QWORD *)&v51[8] = &v51[14];
    if ( &v43 )
    {
      v51[17] = v14;
      *(_QWORD *)&v51[18] = &v43;
    }
    else
    {
      v51[17] = 0;
      *(_QWORD *)&v51[18] = 0;
    }
    *(_QWORD *)&v51[20] = &g_BatchLibContext;
  }
  v23 = NetBufferList->NetBufferListInfo[0];
  if ( !a6 || v44 )
  {
    v27 = HIBYTE(v47[1]);
  }
  else
  {
    v24 = 0;
    TxChecksumOffloadInfo = VncGetTxChecksumOffloadInfo(NetBufferList, v47, 0);
    if ( TxChecksumOffloadInfo < 0 )
      goto LABEL_70;
    v27 = HIBYTE(v47[1]);
    v11 = v47[0];
    if ( HIBYTE(v47[1]) )
    {
      if ( ((unsigned __int8)v23 & 4) != 0 )
      {
        v10 = *(_DWORD *)v47 + 20;
      }
      else if ( ((unsigned __int8)v23 & 8) != 0 )
      {
        v10 = *(_DWORD *)v47 + 8;
      }
      else
      {
        if ( ((unsigned __int8)v23 & 0x11) != 0x11 )
        {
LABEL_37:
          NdisAdvanceNetBufferListDataStart(NetBufferList, (unsigned __int16)v10, 0, 0);
          v43 = 1;
          goto LABEL_39;
        }
        v10 = 34;
      }
      v46 = v10;
      goto LABEL_37;
    }
  }
LABEL_39:
  CloneNetBufferList = NdisAllocateCloneNetBufferList(NetBufferList, NetBufferListPoolHandle, NetBufferPoolHandle, 0);
  v24 = CloneNetBufferList;
  if ( CloneNetBufferList )
  {
    if ( v27 )
    {
      v30 = NdisRetreatNetBufferListDataStart(CloneNetBufferList, (unsigned __int16)v10, 0, 0, 0);
      TxChecksumOffloadInfo = v30;
      if ( v30 >= 0 )
      {
        v45 = 1;
        NdisRetreatNetBufferListDataStart(NetBufferList, (unsigned __int16)v10, 0, 0, 0);
        FirstNetBuffer = v24->FirstNetBuffer;
        Alignment = NetBufferList->FirstNetBuffer;
        v43 = 0;
        while ( 1 )
        {
          NetBufferPoolHandle = FirstNetBuffer;
          if ( !Alignment || !FirstNetBuffer )
          {
            VmsNblHelperIncrementSuccessCsoStats(NetBufferList, 0, 0, 0);
            goto LABEL_53;
          }
          TxChecksumOffloadInfo = NdisCopyFromNetBufferToNetBuffer(
                                    FirstNetBuffer,
                                    0,
                                    (unsigned __int16)v10,
                                    Alignment,
                                    0,
                                    &v49);
          if ( TxChecksumOffloadInfo < 0 )
            goto LABEL_69;
          if ( v49 != (unsigned __int16)v10 && v49 < Alignment->DataLength )
            break;
          LOBYTE(BytesCopied) = v47[1];
          TxChecksumOffloadInfo = SegLibDeferredChecksumPacket((int)v51, (int)NetBufferPoolHandle, v11, BytesCopied);
          if ( TxChecksumOffloadInfo < 0 )
            goto LABEL_69;
          Alignment = (_NET_BUFFER *)Alignment->Link.Alignment;
          FirstNetBuffer = *(struct _NET_BUFFER **)NetBufferPoolHandle;
        }
        TxChecksumOffloadInfo = -1073741670;
      }
      else
      {
        LOBYTE(v31) = 2;
        WPP_RECORDER_SF_qDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v31,
          12,
          12,
          (__int64)WPP_8b26f454089231c5607d0d1238616a13_Traceguids,
          (char)v24,
          v10,
          v30);
      }
    }
    else
    {
LABEL_53:
      TxChecksumOffloadInfo = VmsNblHelperAllocateNetBufferListContext(v24, a7);
      if ( TxChecksumOffloadInfo >= 0 )
      {
        v34 = v24->NetBufferListInfo[18];
        v35 = v44;
        *(_QWORD *)v34 = 1;
        v34[6] = 1;
        v34[8] = (unsigned __int16)v10;
        if ( v35 )
          NdisCopyReceiveNetBufferListInfo(v24, NetBufferList);
        else
          NdisCopySendNetBufferListInfo(v24, NetBufferList);
        if ( a6 )
        {
          v24->NetBufferListInfo[0] = 0;
          if ( !v35 )
            v24->NetBufferListInfo[2] = 0;
        }
        v24->ParentNetBufferList = NetBufferList;
        if ( !a7 )
        {
          v25 = &NetBufferList->NetBufferListInfo[19];
          WORD1(v24->NetBufferListInfo[19]) = WORD1(NetBufferList->NetBufferListInfo[19]);
          BYTE4(v24->NetBufferListInfo[19]) = BYTE4(NetBufferList->NetBufferListInfo[19]);
          v36 = HIDWORD(v24->NetBufferListInfo[19]);
          if ( NetBufferList == (PNET_BUFFER_LIST)-296LL )
          {
            v37 = v36 & 0xFEFFFBFF | 0x400;
          }
          else
          {
            v38 = v36 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v36) & 0x400;
            HIDWORD(v24->NetBufferListInfo[19]) = v38;
            v39 = v38 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v38) & 0x7FF800;
            HIDWORD(v24->NetBufferListInfo[19]) = v39;
            v40 = v39 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v39) & 0x800000;
            HIDWORD(v24->NetBufferListInfo[19]) = v40;
            v37 = v40 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v40) & 0x1000000;
          }
          HIDWORD(v24->NetBufferListInfo[19]) = v37;
          HIDWORD(v24->NetBufferListInfo[19]) = v37 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v37) & 0x100;
        }
        if ( !a5 )
          VmsNblHelperRefCountIncrement(NetBufferList);
        TxChecksumOffloadInfo = 0;
        *v50 = v24;
      }
    }
LABEL_69:
    LOWORD(v10) = v46;
  }
  else
  {
    TxChecksumOffloadInfo = -1073741670;
    LOBYTE(v29) = 2;
    WPP_RECORDER_SF_qqqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v29,
      12,
      11,
      (__int64)WPP_8b26f454089231c5607d0d1238616a13_Traceguids,
      (char)NetBufferList,
      (char)NetBufferListPoolHandle,
      (char)NetBufferPoolHandle,
      154);
  }
LABEL_70:
  LOBYTE(v25) = 1;
  BLFlushBatchOpContextEx(v51, 0, v25);
  if ( TxChecksumOffloadInfo < 0 )
  {
    if ( v43 )
      NdisRetreatNetBufferListDataStart(NetBufferList, (unsigned __int16)v10, 0, 0, 0);
    if ( v24 )
    {
      if ( v45 )
        NdisAdvanceNetBufferListDataStart(v24, (unsigned __int16)v10, 1u, 0);
      NdisFreeCloneNetBufferList(v24, 0);
    }
  }
  return (unsigned int)TxChecksumOffloadInfo;
}

```

## disassembly

```asm
0x1401149f8  push    rbp
0x1401149fa  push    rsi
0x1401149fb  push    rdi
0x1401149fc  push    r12
0x1401149fe  push    r13
0x140114a00  push    r14
0x140114a02  push    r15
0x140114a04  sub     rsp, 0F0h
0x140114a0b  lea     rbp, [rsp+50h]
0x140114a10  mov     [rbp+0D0h+arg_18], rbx
0x140114a17  mov     rax, cs:__security_cookie
0x140114a1e  xor     rax, rbp
0x140114a21  mov     [rbp+0D0h+var_40], rax
0x140114a28  mov     rax, [rbp+0D0h+arg_38]
0x140114a2f  mov     r12, rdx
0x140114a32  mov     [rbp+0D0h+var_B0], rax
0x140114a36  mov     r15, rcx
0x140114a39  xor     eax, eax
0x140114a3b  mov     [rbp+0D0h+NetBufferPoolHandle], r8
0x140114a3f  xor     edx, edx; Val
0x140114a41  mov     [rbp+0D0h+var_CF], r9b
0x140114a45  lea     rcx, [rbp+0D0h+var_A0]; void *
0x140114a49  mov     [rbp+0D0h+var_D0], al
0x140114a4c  mov     [rbp+0D0h+var_CE], al
0x140114a4f  mov     r13d, eax
0x140114a52  lea     r8d, [rax+60h]; Size
0x140114a56  mov     [rbp+0D0h+var_CC], eax
0x140114a59  mov     [rbp+0D0h+var_B8], eax
0x140114a5c  mov     edi, eax
0x140114a5e  mov     dword ptr [rbp+0D0h+var_C8], eax
0x140114a61  call    memset
0x140114a66  mov     eax, cs:VmsDiagnosticFlags
0x140114a6c  xor     r8d, r8d
0x140114a6f  mov     rcx, [rbp+0D8h]
0x140114a76  test    al, 1
0x140114a78  jz      short loc_140114AB3
0x140114a7a  test    r15, r15
0x140114a7d  jz      short loc_140114AB3
0x140114a7f  mov     rax, [r15+120h]
0x140114a86  test    rax, rax
0x140114a89  jz      short loc_140114AB3
0x140114a8b  mov     rax, [rax+10h]
0x140114a8f  test    rax, rax
0x140114a92  jz      short loc_140114AB3
0x140114a94  lea     rdx, aVmsnblhelpercr_0; "VmsNblHelperCreateCloneNbl2507"
0x140114a9b  mov     dword ptr [rax+0B8h], 125h
0x140114aa5  mov     [rax+0B0h], rdx
0x140114aac  mov     [rax+0A8h], rcx
0x140114ab3  cmp     cs:byte_1401F96F0, r8b
0x140114aba  mov     esi, 4
0x140114abf  mov     eax, cs:VmsDiagnosticFlags
0x140114ac5  cmovnz  esi, dword ptr cs:qword_1401F96CC+4
0x140114acc  mov     rcx, [rbp+0D8h]
0x140114ad3  test    al, 1
0x140114ad5  jz      short loc_140114B10
0x140114ad7  test    r15, r15
0x140114ada  jz      short loc_140114B10
0x140114adc  mov     rax, [r15+120h]
0x140114ae3  test    rax, rax
0x140114ae6  jz      short loc_140114B10
0x140114ae8  mov     rax, [rax+10h]
0x140114aec  test    rax, rax
0x140114aef  jz      short loc_140114B10
0x140114af1  lea     rdx, aVmsnblissource; "VmsNblIsSourceNicUntrusted"
0x140114af8  mov     dword ptr [rax+0B8h], 4Bh ; 'K'
0x140114b02  mov     [rax+0B0h], rdx
0x140114b09  mov     [rax+0A8h], rcx
0x140114b10  mov     rax, [r15+120h]
0x140114b17  mov     bl, r8b
0x140114b1a  test    rax, rax
0x140114b1d  jz      short loc_140114B45
0x140114b1f  mov     rax, [rax+10h]
0x140114b23  test    rax, rax
0x140114b26  jz      short loc_140114B45
0x140114b28  mov     rax, [rax+18h]
0x140114b2c  test    rax, rax
0x140114b2f  jz      short loc_140114B45
0x140114b31  cmp     dword ptr [rax+750h], 3
0x140114b38  jnz     short loc_140114B45
0x140114b3a  cmp     [rax+755h], r8b
0x140114b41  jnz     short loc_140114B45
0x140114b43  mov     bl, 1
0x140114b45  lea     rcx, [rsi+rsi*2]
0x140114b49  shl     rcx, 3
0x140114b4d  lea     rax, [rcx+0Fh]
0x140114b51  cmp     rax, rcx
0x140114b54  ja      short loc_140114B60
0x140114b56  mov     rax, 0FFFFFFFFFFFFFF0h
0x140114b60  and     rax, 0FFFFFFFFFFFFFFF0h
0x140114b64  call    __chkstk_0
0x140114b69  sub     rsp, rax
0x140114b6c  lea     r14, [rsp+120h+var_D0]
0x140114b71  cmp     bl, 1
0x140114b74  jnz     short loc_140114B83
0x140114b76  cmp     cs:qword_1401F96E0, r8
0x140114b7d  jz      loc_140114C05
0x140114b83  xor     ecx, ecx; ProcNumber
0x140114b85  mov     [rbp+0D0h+var_A0], 0F00DF00Dh
0x140114b8c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140114b93  nop     dword ptr [rax+rax+00h]
0x140114b98  xor     r8d, r8d
0x140114b9b  movzx   edx, bl
0x140114b9e  mov     [rbp+0D0h+var_94], eax
0x140114ba1  mov     rax, cs:qword_1401F96E0
0x140114ba8  neg     rax
0x140114bab  mov     [rbp+0D0h+var_9C], r8b
0x140114baf  lea     rax, [rbp+0D0h+var_68]
0x140114bb3  mov     [rbp+0D0h+var_88], r8
0x140114bb7  sbb     ecx, ecx
0x140114bb9  mov     [rbp+0D0h+var_90], 1
0x140114bc1  and     ecx, 4
0x140114bc4  mov     [rbp+0D0h+var_70], r8
0x140114bc8  or      edx, ecx
0x140114bca  mov     [rbp+0D0h+var_74], r8d
0x140114bce  mov     [rbp+0D0h+var_98], edx
0x140114bd1  mov     [rbp+0D0h+var_78], r8b
0x140114bd5  mov     [rbp+0D0h+var_68], r8
0x140114bd9  mov     [rbp+0D0h+var_60], r8d
0x140114bdd  mov     [rbp+0D0h+var_80], rax
0x140114be1  test    r14, r14
0x140114be4  jz      short loc_140114BEF
0x140114be6  mov     [rbp+0D0h+var_5C], esi
0x140114be9  mov     [rbp+0D0h+var_58], r14
0x140114bed  jmp     short loc_140114BF7
0x140114bef  mov     [rbp+0D0h+var_5C], r8d
0x140114bf3  mov     [rbp+0D0h+var_58], r8
0x140114bf7  lea     rax, g_BatchLibContext
0x140114bfe  mov     [rbp+0D0h+var_50], rax
0x140114c05  mov     rbx, [r15+90h]
0x140114c0c  cmp     [rbp+0D0h+arg_28], r8b
0x140114c13  jz      short loc_140114C8C
0x140114c15  cmp     [rbp+0D0h+var_CF], r8b
0x140114c19  jnz     short loc_140114C8C
0x140114c1b  mov     rsi, r8
0x140114c1e  lea     rdx, [rbp+0D0h+var_C8]
0x140114c22  xor     r8d, r8d
0x140114c25  mov     rcx, r15
0x140114c28  call    VncGetTxChecksumOffloadInfo
0x140114c2d  mov     r14d, eax
0x140114c30  test    eax, eax
0x140114c32  js      loc_140114F92
0x140114c38  mov     r14b, byte ptr [rbp+0D0h+var_C8+3]
0x140114c3c  mov     edi, dword ptr [rbp+0D0h+var_C8]
0x140114c3f  test    r14b, r14b
0x140114c42  jz      short loc_140114C90
0x140114c44  test    bl, 4
0x140114c47  jz      short loc_140114C4F
0x140114c49  lea     r13d, [rdi+14h]
0x140114c4d  jmp     short loc_140114C69
0x140114c4f  test    bl, 8
0x140114c52  jz      short loc_140114C5A
0x140114c54  lea     r13d, [rdi+8]
0x140114c58  jmp     short loc_140114C69
0x140114c5a  mov     eax, ebx
0x140114c5c  and     eax, 11h
0x140114c5f  cmp     al, 11h
0x140114c61  jnz     short loc_140114C6D
0x140114c63  mov     r13d, 22h ; '"'
0x140114c69  mov     [rbp+0D0h+var_CC], r13d
0x140114c6d  movzx   edx, r13w; DataOffsetDelta
0x140114c71  xor     r9d, r9d; FreeMdlMdlHandler
0x140114c74  xor     r8d, r8d; FreeMdl
0x140114c77  mov     rcx, r15; NetBufferList
0x140114c7a  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x140114c81  nop     dword ptr [rax+rax+00h]
0x140114c86  mov     [rbp+0D0h+var_D0], 1
0x140114c8a  jmp     short loc_140114C90
0x140114c8c  mov     r14b, byte ptr [rbp+0D0h+var_C8+3]
0x140114c90  mov     r8, [rbp+0D0h+NetBufferPoolHandle]; NetBufferPoolHandle
0x140114c94  xor     r9d, r9d; AllocateCloneFlags
0x140114c97  mov     rdx, r12; NetBufferListPoolHandle
0x140114c9a  mov     rcx, r15; OriginalNetBufferList
0x140114c9d  call    cs:__imp_NdisAllocateCloneNetBufferList
0x140114ca4  nop     dword ptr [rax+rax+00h]
0x140114ca9  mov     rsi, rax
0x140114cac  test    rax, rax
0x140114caf  jnz     short loc_140114CFA
0x140114cb1  mov     r14d, 0C000009Ah
0x140114cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140114cbe  lea     r9d, [rax+0Bh]
0x140114cc2  mov     rax, [rbp+0D0h+NetBufferPoolHandle]
0x140114cc6  lea     r8d, [rsi+0Ch]
0x140114cca  mov     [rsp+120h+var_E0], r14d
0x140114ccf  mov     dl, 2
0x140114cd1  mov     [rsp+120h+var_E8], rax
0x140114cd6  lea     rax, WPP_8b26f454089231c5607d0d1238616a13_Traceguids
0x140114cdd  mov     rcx, [rcx+40h]
0x140114ce1  mov     [rsp+120h+var_F0], r12
0x140114ce6  mov     [rsp+120h+BytesCopied], r15
0x140114ceb  mov     [rsp+120h+FreeMdlHandler], rax
0x140114cf0  call    WPP_RECORDER_SF_qqqd
0x140114cf5  jmp     loc_140114F92
0x140114cfa  movzx   r13d, r13w
0x140114cfe  test    r14b, r14b
0x140114d01  jz      loc_140114E3D
0x140114d07  xor     r9d, r9d; AllocateMdlHandler
0x140114d0a  mov     [rsp+120h+FreeMdlHandler], 0; FreeMdlHandler
0x140114d13  xor     r8d, r8d; DataBackFill
0x140114d16  mov     edx, r13d; DataOffsetDelta
0x140114d19  mov     rcx, rsi; NetBufferList
0x140114d1c  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140114d23  nop     dword ptr [rax+rax+00h]
0x140114d28  mov     r14d, eax
0x140114d2b  test    eax, eax
0x140114d2d  jns     short loc_140114D69
0x140114d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140114d36  mov     r8d, 0Ch
0x140114d3c  mov     dword ptr [rsp+120h+var_E8], eax
0x140114d40  mov     r9d, r8d
0x140114d43  mov     dword ptr [rsp+120h+var_F0], r13d
0x140114d48  lea     rax, WPP_8b26f454089231c5607d0d1238616a13_Traceguids
0x140114d4f  mov     [rsp+120h+BytesCopied], rsi
0x140114d54  mov     dl, 2
0x140114d56  mov     rcx, [rcx+40h]
0x140114d5a  mov     [rsp+120h+FreeMdlHandler], rax
0x140114d5f  call    WPP_RECORDER_SF_qDd
0x140114d64  jmp     loc_140114F8E
0x140114d69  xor     r9d, r9d; AllocateMdlHandler
0x140114d6c  mov     [rbp+0D0h+var_CE], 1
0x140114d70  xor     r8d, r8d; DataBackFill
0x140114d73  mov     [rsp+120h+FreeMdlHandler], 0; FreeMdlHandler
0x140114d7c  mov     edx, r13d; DataOffsetDelta
0x140114d7f  mov     rcx, r15; NetBufferList
0x140114d82  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140114d89  nop     dword ptr [rax+rax+00h]
0x140114d8e  mov     rax, [rsi+8]
0x140114d92  mov     r12, [r15+8]
0x140114d96  mov     [rbp+0D0h+var_D0], 0
0x140114d9a  jmp     loc_140114E20
0x140114d9f  test    rax, rax
0x140114da2  jz      loc_140114E2D
0x140114da8  lea     rcx, [rbp+0D0h+var_B8]
0x140114dac  mov     r9, r12; Source
0x140114daf  mov     [rsp+120h+BytesCopied], rcx; BytesCopied
0x140114db4  mov     r8d, r13d; BytesToCopy
0x140114db7  mov     rcx, rax; Destination
0x140114dba  mov     dword ptr [rsp+120h+FreeMdlHandler], 0; SourceOffset
0x140114dc2  xor     edx, edx; DestinationOffset
0x140114dc4  call    cs:__imp_NdisCopyFromNetBufferToNetBuffer
0x140114dcb  nop     dword ptr [rax+rax+00h]
0x140114dd0  mov     r14d, eax
0x140114dd3  test    eax, eax
0x140114dd5  js      loc_140114F8E
0x140114ddb  mov     eax, [rbp+0D0h+var_B8]
0x140114dde  cmp     eax, r13d
0x140114de1  jz      short loc_140114DEE
0x140114de3  cmp     eax, [r12+18h]
0x140114de8  jb      loc_140114E98
0x140114dee  mov     al, byte ptr [rbp+0D0h+var_C8+2]
0x140114df1  lea     rcx, [rbp+0D0h+var_A0]; int
0x140114df5  mov     rdx, [rbp+0D0h+NetBufferPoolHandle]; int
0x140114df9  mov     r8, rbx
0x140114dfc  mov     byte ptr [rsp+120h+BytesCopied], al; int
0x140114e00  mov     word ptr [rsp+120h+FreeMdlHandler], di; __int16
0x140114e05  call    SegLibDeferredChecksumPacket
0x140114e0a  mov     r14d, eax
0x140114e0d  test    eax, eax
0x140114e0f  js      loc_140114F8E
0x140114e15  mov     rax, [rbp+0D0h+NetBufferPoolHandle]
0x140114e19  mov     r12, [r12]
0x140114e1d  mov     rax, [rax]
0x140114e20  mov     [rbp+0D0h+NetBufferPoolHandle], rax
0x140114e24  test    r12, r12
0x140114e27  jnz     loc_140114D9F
0x140114e2d  xor     r9d, r9d
0x140114e30  xor     r8d, r8d
0x140114e33  xor     edx, edx
0x140114e35  mov     rcx, r15
0x140114e38  call    VmsNblHelperIncrementSuccessCsoStats
0x140114e3d  mov     ebx, [rbp+0D0h+arg_30]
0x140114e43  mov     edx, 28h ; '('
0x140114e48  mov     r9d, 624E7356h
0x140114e4e  mov     dword ptr [rsp+120h+FreeMdlHandler], ebx; int
0x140114e52  mov     rcx, rsi; NetBufferList
0x140114e55  call    VmsNblHelperAllocateNetBufferListContext
0x140114e5a  mov     r14d, eax
0x140114e5d  test    eax, eax
0x140114e5f  js      loc_140114F8E
0x140114e65  mov     rax, [rsi+120h]
0x140114e6c  mov     ecx, 1
0x140114e71  mov     dil, [rbp+0D0h+var_CF]
0x140114e75  mov     rdx, r15; SrcNetBufferList
0x140114e78  mov     [rax], rcx
0x140114e7b  mov     [rax+18h], ecx
0x140114e7e  mov     rcx, rsi; DestNetBufferList
0x140114e81  mov     [rax+20h], r13d
0x140114e85  test    dil, dil
0x140114e88  jz      short loc_140114EA3
0x140114e8a  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x140114e91  nop     dword ptr [rax+rax+00h]
0x140114e96  jmp     short loc_140114EAF
0x140114e98  mov     r14d, 0C000009Ah
0x140114e9e  jmp     loc_140114F8E
0x140114ea3  call    cs:__imp_NdisCopySendNetBufferListInfo
0x140114eaa  nop     dword ptr [rax+rax+00h]
0x140114eaf  cmp     [rbp+0D0h+arg_28], 0
0x140114eb6  jz      short loc_140114ED3
0x140114eb8  mov     qword ptr [rsi+90h], 0
0x140114ec3  test    dil, dil
0x140114ec6  jnz     short loc_140114ED3
  ... truncated ...
```
