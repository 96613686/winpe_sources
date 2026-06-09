# VmsNblHelperCreateCloneNbl2507

- ea: `0x140114a68`
- end: `0x14011509f`
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
- `0x140114a68`
- `0x1401bbbc2`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140114bfc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140114bfc`
- `NDIS!NdisFreeCloneNetBufferList` at `0x140115066`
- `NDIS!NdisFreeCloneNetBufferList` at `0x140115066`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140114e34`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140114e34`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114d8c`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114df2`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140115033`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114d8c`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140114df2`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140115033`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x140114d0d`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x140114d0d`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140114cea`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140115055`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140114cea`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140115055`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140114f13`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140114f13`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140114efa`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140114efa`

## string_xrefs

- `0x140114b04`: `VmsNblHelperCreateCloneNbl2507`

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
0x140114a68  push    rbp
0x140114a6a  push    rsi
0x140114a6b  push    rdi
0x140114a6c  push    r12
0x140114a6e  push    r13
0x140114a70  push    r14
0x140114a72  push    r15
0x140114a74  sub     rsp, 0F0h
0x140114a7b  lea     rbp, [rsp+50h]
0x140114a80  mov     [rbp+0D0h+arg_18], rbx
0x140114a87  mov     rax, cs:__security_cookie
0x140114a8e  xor     rax, rbp
0x140114a91  mov     [rbp+0D0h+var_40], rax
0x140114a98  mov     rax, [rbp+0D0h+arg_38]
0x140114a9f  mov     r12, rdx
0x140114aa2  mov     [rbp+0D0h+var_B0], rax
0x140114aa6  mov     r15, rcx
0x140114aa9  xor     eax, eax
0x140114aab  mov     [rbp+0D0h+NetBufferPoolHandle], r8
0x140114aaf  xor     edx, edx; Val
0x140114ab1  mov     [rbp+0D0h+var_CF], r9b
0x140114ab5  lea     rcx, [rbp+0D0h+var_A0]; void *
0x140114ab9  mov     [rbp+0D0h+var_D0], al
0x140114abc  mov     [rbp+0D0h+var_CE], al
0x140114abf  mov     r13d, eax
0x140114ac2  lea     r8d, [rax+60h]; Size
0x140114ac6  mov     [rbp+0D0h+var_CC], eax
0x140114ac9  mov     [rbp+0D0h+var_B8], eax
0x140114acc  mov     edi, eax
0x140114ace  mov     dword ptr [rbp+0D0h+var_C8], eax
0x140114ad1  call    memset
0x140114ad6  mov     eax, cs:VmsDiagnosticFlags
0x140114adc  xor     r8d, r8d
0x140114adf  mov     rcx, [rbp+0D8h]
0x140114ae6  test    al, 1
0x140114ae8  jz      short loc_140114B23
0x140114aea  test    r15, r15
0x140114aed  jz      short loc_140114B23
0x140114aef  mov     rax, [r15+120h]
0x140114af6  test    rax, rax
0x140114af9  jz      short loc_140114B23
0x140114afb  mov     rax, [rax+10h]
0x140114aff  test    rax, rax
0x140114b02  jz      short loc_140114B23
0x140114b04  lea     rdx, aVmsnblhelpercr_0; "VmsNblHelperCreateCloneNbl2507"
0x140114b0b  mov     dword ptr [rax+0B8h], 125h
0x140114b15  mov     [rax+0B0h], rdx
0x140114b1c  mov     [rax+0A8h], rcx
0x140114b23  cmp     cs:byte_1401F96F0, r8b
0x140114b2a  mov     esi, 4
0x140114b2f  mov     eax, cs:VmsDiagnosticFlags
0x140114b35  cmovnz  esi, dword ptr cs:qword_1401F96CC+4
0x140114b3c  mov     rcx, [rbp+0D8h]
0x140114b43  test    al, 1
0x140114b45  jz      short loc_140114B80
0x140114b47  test    r15, r15
0x140114b4a  jz      short loc_140114B80
0x140114b4c  mov     rax, [r15+120h]
0x140114b53  test    rax, rax
0x140114b56  jz      short loc_140114B80
0x140114b58  mov     rax, [rax+10h]
0x140114b5c  test    rax, rax
0x140114b5f  jz      short loc_140114B80
0x140114b61  lea     rdx, aVmsnblissource; "VmsNblIsSourceNicUntrusted"
0x140114b68  mov     dword ptr [rax+0B8h], 4Bh ; 'K'
0x140114b72  mov     [rax+0B0h], rdx
0x140114b79  mov     [rax+0A8h], rcx
0x140114b80  mov     rax, [r15+120h]
0x140114b87  mov     bl, r8b
0x140114b8a  test    rax, rax
0x140114b8d  jz      short loc_140114BB5
0x140114b8f  mov     rax, [rax+10h]
0x140114b93  test    rax, rax
0x140114b96  jz      short loc_140114BB5
0x140114b98  mov     rax, [rax+18h]
0x140114b9c  test    rax, rax
0x140114b9f  jz      short loc_140114BB5
0x140114ba1  cmp     dword ptr [rax+750h], 3
0x140114ba8  jnz     short loc_140114BB5
0x140114baa  cmp     [rax+755h], r8b
0x140114bb1  jnz     short loc_140114BB5
0x140114bb3  mov     bl, 1
0x140114bb5  lea     rcx, [rsi+rsi*2]
0x140114bb9  shl     rcx, 3
0x140114bbd  lea     rax, [rcx+0Fh]
0x140114bc1  cmp     rax, rcx
0x140114bc4  ja      short loc_140114BD0
0x140114bc6  mov     rax, 0FFFFFFFFFFFFFF0h
0x140114bd0  and     rax, 0FFFFFFFFFFFFFFF0h
0x140114bd4  call    __chkstk_0
0x140114bd9  sub     rsp, rax
0x140114bdc  lea     r14, [rsp+120h+var_D0]
0x140114be1  cmp     bl, 1
0x140114be4  jnz     short loc_140114BF3
0x140114be6  cmp     cs:qword_1401F96E0, r8
0x140114bed  jz      loc_140114C75
0x140114bf3  xor     ecx, ecx; ProcNumber
0x140114bf5  mov     [rbp+0D0h+var_A0], 0F00DF00Dh
0x140114bfc  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140114c03  nop     dword ptr [rax+rax+00h]
0x140114c08  xor     r8d, r8d
0x140114c0b  movzx   edx, bl
0x140114c0e  mov     [rbp+0D0h+var_94], eax
0x140114c11  mov     rax, cs:qword_1401F96E0
0x140114c18  neg     rax
0x140114c1b  mov     [rbp+0D0h+var_9C], r8b
0x140114c1f  lea     rax, [rbp+0D0h+var_68]
0x140114c23  mov     [rbp+0D0h+var_88], r8
0x140114c27  sbb     ecx, ecx
0x140114c29  mov     [rbp+0D0h+var_90], 1
0x140114c31  and     ecx, 4
0x140114c34  mov     [rbp+0D0h+var_70], r8
0x140114c38  or      edx, ecx
0x140114c3a  mov     [rbp+0D0h+var_74], r8d
0x140114c3e  mov     [rbp+0D0h+var_98], edx
0x140114c41  mov     [rbp+0D0h+var_78], r8b
0x140114c45  mov     [rbp+0D0h+var_68], r8
0x140114c49  mov     [rbp+0D0h+var_60], r8d
0x140114c4d  mov     [rbp+0D0h+var_80], rax
0x140114c51  test    r14, r14
0x140114c54  jz      short loc_140114C5F
0x140114c56  mov     [rbp+0D0h+var_5C], esi
0x140114c59  mov     [rbp+0D0h+var_58], r14
0x140114c5d  jmp     short loc_140114C67
0x140114c5f  mov     [rbp+0D0h+var_5C], r8d
0x140114c63  mov     [rbp+0D0h+var_58], r8
0x140114c67  lea     rax, g_BatchLibContext
0x140114c6e  mov     [rbp+0D0h+var_50], rax
0x140114c75  mov     rbx, [r15+90h]
0x140114c7c  cmp     [rbp+0D0h+arg_28], r8b
0x140114c83  jz      short loc_140114CFC
0x140114c85  cmp     [rbp+0D0h+var_CF], r8b
0x140114c89  jnz     short loc_140114CFC
0x140114c8b  mov     rsi, r8
0x140114c8e  lea     rdx, [rbp+0D0h+var_C8]
0x140114c92  xor     r8d, r8d
0x140114c95  mov     rcx, r15
0x140114c98  call    VncGetTxChecksumOffloadInfo
0x140114c9d  mov     r14d, eax
0x140114ca0  test    eax, eax
0x140114ca2  js      loc_140115002
0x140114ca8  mov     r14b, byte ptr [rbp+0D0h+var_C8+3]
0x140114cac  mov     edi, dword ptr [rbp+0D0h+var_C8]
0x140114caf  test    r14b, r14b
0x140114cb2  jz      short loc_140114D00
0x140114cb4  test    bl, 4
0x140114cb7  jz      short loc_140114CBF
0x140114cb9  lea     r13d, [rdi+14h]
0x140114cbd  jmp     short loc_140114CD9
0x140114cbf  test    bl, 8
0x140114cc2  jz      short loc_140114CCA
0x140114cc4  lea     r13d, [rdi+8]
0x140114cc8  jmp     short loc_140114CD9
0x140114cca  mov     eax, ebx
0x140114ccc  and     eax, 11h
0x140114ccf  cmp     al, 11h
0x140114cd1  jnz     short loc_140114CDD
0x140114cd3  mov     r13d, 22h ; '"'
0x140114cd9  mov     [rbp+0D0h+var_CC], r13d
0x140114cdd  movzx   edx, r13w; DataOffsetDelta
0x140114ce1  xor     r9d, r9d; FreeMdlMdlHandler
0x140114ce4  xor     r8d, r8d; FreeMdl
0x140114ce7  mov     rcx, r15; NetBufferList
0x140114cea  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x140114cf1  nop     dword ptr [rax+rax+00h]
0x140114cf6  mov     [rbp+0D0h+var_D0], 1
0x140114cfa  jmp     short loc_140114D00
0x140114cfc  mov     r14b, byte ptr [rbp+0D0h+var_C8+3]
0x140114d00  mov     r8, [rbp+0D0h+NetBufferPoolHandle]; NetBufferPoolHandle
0x140114d04  xor     r9d, r9d; AllocateCloneFlags
0x140114d07  mov     rdx, r12; NetBufferListPoolHandle
0x140114d0a  mov     rcx, r15; OriginalNetBufferList
0x140114d0d  call    cs:__imp_NdisAllocateCloneNetBufferList
0x140114d14  nop     dword ptr [rax+rax+00h]
0x140114d19  mov     rsi, rax
0x140114d1c  test    rax, rax
0x140114d1f  jnz     short loc_140114D6A
0x140114d21  mov     r14d, 0C000009Ah
0x140114d27  mov     rcx, cs:WPP_GLOBAL_Control
0x140114d2e  lea     r9d, [rax+0Bh]
0x140114d32  mov     rax, [rbp+0D0h+NetBufferPoolHandle]
0x140114d36  lea     r8d, [rsi+0Ch]
0x140114d3a  mov     [rsp+120h+var_E0], r14d
0x140114d3f  mov     dl, 2
0x140114d41  mov     [rsp+120h+var_E8], rax
0x140114d46  lea     rax, WPP_8b26f454089231c5607d0d1238616a13_Traceguids
0x140114d4d  mov     rcx, [rcx+40h]
0x140114d51  mov     [rsp+120h+var_F0], r12
0x140114d56  mov     [rsp+120h+BytesCopied], r15
0x140114d5b  mov     [rsp+120h+FreeMdlHandler], rax
0x140114d60  call    WPP_RECORDER_SF_qqqd
0x140114d65  jmp     loc_140115002
0x140114d6a  movzx   r13d, r13w
0x140114d6e  test    r14b, r14b
0x140114d71  jz      loc_140114EAD
0x140114d77  xor     r9d, r9d; AllocateMdlHandler
0x140114d7a  mov     [rsp+120h+FreeMdlHandler], 0; FreeMdlHandler
0x140114d83  xor     r8d, r8d; DataBackFill
0x140114d86  mov     edx, r13d; DataOffsetDelta
0x140114d89  mov     rcx, rsi; NetBufferList
0x140114d8c  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140114d93  nop     dword ptr [rax+rax+00h]
0x140114d98  mov     r14d, eax
0x140114d9b  test    eax, eax
0x140114d9d  jns     short loc_140114DD9
0x140114d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140114da6  mov     r8d, 0Ch
0x140114dac  mov     dword ptr [rsp+120h+var_E8], eax
0x140114db0  mov     r9d, r8d
0x140114db3  mov     dword ptr [rsp+120h+var_F0], r13d
0x140114db8  lea     rax, WPP_8b26f454089231c5607d0d1238616a13_Traceguids
0x140114dbf  mov     [rsp+120h+BytesCopied], rsi
0x140114dc4  mov     dl, 2
0x140114dc6  mov     rcx, [rcx+40h]
0x140114dca  mov     [rsp+120h+FreeMdlHandler], rax
0x140114dcf  call    WPP_RECORDER_SF_qDd
0x140114dd4  jmp     loc_140114FFE
0x140114dd9  xor     r9d, r9d; AllocateMdlHandler
0x140114ddc  mov     [rbp+0D0h+var_CE], 1
0x140114de0  xor     r8d, r8d; DataBackFill
0x140114de3  mov     [rsp+120h+FreeMdlHandler], 0; FreeMdlHandler
0x140114dec  mov     edx, r13d; DataOffsetDelta
0x140114def  mov     rcx, r15; NetBufferList
0x140114df2  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140114df9  nop     dword ptr [rax+rax+00h]
0x140114dfe  mov     rax, [rsi+8]
0x140114e02  mov     r12, [r15+8]
0x140114e06  mov     [rbp+0D0h+var_D0], 0
0x140114e0a  jmp     loc_140114E90
0x140114e0f  test    rax, rax
0x140114e12  jz      loc_140114E9D
0x140114e18  lea     rcx, [rbp+0D0h+var_B8]
0x140114e1c  mov     r9, r12; Source
0x140114e1f  mov     [rsp+120h+BytesCopied], rcx; BytesCopied
0x140114e24  mov     r8d, r13d; BytesToCopy
0x140114e27  mov     rcx, rax; Destination
0x140114e2a  mov     dword ptr [rsp+120h+FreeMdlHandler], 0; SourceOffset
0x140114e32  xor     edx, edx; DestinationOffset
0x140114e34  call    cs:__imp_NdisCopyFromNetBufferToNetBuffer
0x140114e3b  nop     dword ptr [rax+rax+00h]
0x140114e40  mov     r14d, eax
0x140114e43  test    eax, eax
0x140114e45  js      loc_140114FFE
0x140114e4b  mov     eax, [rbp+0D0h+var_B8]
0x140114e4e  cmp     eax, r13d
0x140114e51  jz      short loc_140114E5E
0x140114e53  cmp     eax, [r12+18h]
0x140114e58  jb      loc_140114F08
0x140114e5e  mov     al, byte ptr [rbp+0D0h+var_C8+2]
0x140114e61  lea     rcx, [rbp+0D0h+var_A0]; int
0x140114e65  mov     rdx, [rbp+0D0h+NetBufferPoolHandle]; int
0x140114e69  mov     r8, rbx
0x140114e6c  mov     byte ptr [rsp+120h+BytesCopied], al; int
0x140114e70  mov     word ptr [rsp+120h+FreeMdlHandler], di; __int16
0x140114e75  call    SegLibDeferredChecksumPacket
0x140114e7a  mov     r14d, eax
0x140114e7d  test    eax, eax
0x140114e7f  js      loc_140114FFE
0x140114e85  mov     rax, [rbp+0D0h+NetBufferPoolHandle]
0x140114e89  mov     r12, [r12]
0x140114e8d  mov     rax, [rax]
0x140114e90  mov     [rbp+0D0h+NetBufferPoolHandle], rax
0x140114e94  test    r12, r12
0x140114e97  jnz     loc_140114E0F
0x140114e9d  xor     r9d, r9d
0x140114ea0  xor     r8d, r8d
0x140114ea3  xor     edx, edx
0x140114ea5  mov     rcx, r15
0x140114ea8  call    VmsNblHelperIncrementSuccessCsoStats
0x140114ead  mov     ebx, [rbp+0D0h+arg_30]
0x140114eb3  mov     edx, 28h ; '('
0x140114eb8  mov     r9d, 624E7356h
0x140114ebe  mov     dword ptr [rsp+120h+FreeMdlHandler], ebx; int
0x140114ec2  mov     rcx, rsi; NetBufferList
0x140114ec5  call    VmsNblHelperAllocateNetBufferListContext
0x140114eca  mov     r14d, eax
0x140114ecd  test    eax, eax
0x140114ecf  js      loc_140114FFE
0x140114ed5  mov     rax, [rsi+120h]
0x140114edc  mov     ecx, 1
0x140114ee1  mov     dil, [rbp+0D0h+var_CF]
0x140114ee5  mov     rdx, r15; SrcNetBufferList
0x140114ee8  mov     [rax], rcx
0x140114eeb  mov     [rax+18h], ecx
0x140114eee  mov     rcx, rsi; DestNetBufferList
0x140114ef1  mov     [rax+20h], r13d
0x140114ef5  test    dil, dil
0x140114ef8  jz      short loc_140114F13
0x140114efa  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x140114f01  nop     dword ptr [rax+rax+00h]
0x140114f06  jmp     short loc_140114F1F
0x140114f08  mov     r14d, 0C000009Ah
0x140114f0e  jmp     loc_140114FFE
0x140114f13  call    cs:__imp_NdisCopySendNetBufferListInfo
0x140114f1a  nop     dword ptr [rax+rax+00h]
0x140114f1f  cmp     [rbp+0D0h+arg_28], 0
0x140114f26  jz      short loc_140114F43
0x140114f28  mov     qword ptr [rsi+90h], 0
0x140114f33  test    dil, dil
0x140114f36  jnz     short loc_140114F43
  ... truncated ...
```
