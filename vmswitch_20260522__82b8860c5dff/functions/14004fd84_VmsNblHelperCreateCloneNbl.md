# VmsNblHelperCreateCloneNbl

- ea: `0x14004fd84`
- end: `0x1400505ef`
- name: `VmsNblHelperCreateCloneNbl`
- size: `2155`
- prototype: `__int64 __usercall@<rax>(PNET_BUFFER_LIST NetBufferList@<rcx>, NDIS_HANDLE NetBufferListPoolHandle@<rdx>, char, char, int, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x140026000`
- `0x140032d3c`
- `0x14004eb20`

## callees

- `0x140003e34`
- `0x140006620`
- `0x140012f34`
- `0x1400288ec`
- `0x14004fd84`
- `0x140051528`
- `0x140052460`
- `0x14006b248`
- `0x1401149f8`
- `0x1401bbb52`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004feb0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005026a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004feb0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005026a`
- `NDIS!NdisFreeCloneNetBufferList` at `0x1400505de`
- `NDIS!NdisFreeCloneNetBufferList` at `0x1400505de`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140050209`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140050209`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140050194`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x1400501c3`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x1400505a7`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140050194`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x1400501c3`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x1400505a7`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x14004ff82`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x14004ff82`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400504c6`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400505cd`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400504c6`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400505cd`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14004fffd`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14004fffd`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14005036f`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x14005036f`

## string_xrefs

- `0x1400500fb`: `VmsNblHelperCreateCloneNbl`

## pseudocode

```c
__int64 __fastcall VmsNblHelperCreateCloneNbl(
        PNET_BUFFER_LIST NetBufferList,
        NDIS_HANDLE NetBufferListPoolHandle,
        void *a3,
        char a4,
        char a5,
        char a6,
        int a7,
        struct _NET_BUFFER_LIST **a8)
{
  char v8; // r15
  __int64 v11; // rdi
  _QWORD *v12; // rax
  bool v13; // bl
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // rax
  void *v17; // rsp
  void *v18; // rbx
  int v19; // r12d
  struct _NET_BUFFER_LIST *CloneNetBufferList; // rax
  int v21; // edx
  struct _NET_BUFFER_LIST *v22; // rsi
  NDIS_STATUS NetBufferListContext; // edi
  void **v24; // r8
  _DWORD *v25; // rcx
  unsigned __int16 v26; // r12
  char v27; // di
  int v28; // eax
  int v29; // edx
  unsigned int v30; // edx
  _QWORD *v32; // rax
  __int64 v33; // rax
  _QWORD *v34; // rax
  __int64 v35; // rax
  NDIS_STATUS v36; // eax
  int v37; // edx
  _NET_BUFFER *FirstNetBuffer; // r12
  struct _NET_BUFFER *Alignment; // r13
  ULONG CurrentProcessorNumber; // eax
  _QWORD *v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // rdx
  int v45; // eax
  int v46; // ecx
  int v47; // eax
  int v48; // ecx
  int v49; // eax
  int BytesCopied; // [rsp+28h] [rbp-28h]
  _BYTE v51[4]; // [rsp+50h] [rbp+0h] BYREF
  int v52; // [rsp+54h] [rbp+4h]
  __int16 v53; // [rsp+58h] [rbp+8h]
  char v54; // [rsp+5Ah] [rbp+Ah]
  __int16 v55[2]; // [rsp+5Ch] [rbp+Ch]
  ULONG v56; // [rsp+60h] [rbp+10h] BYREF
  __int64 v57; // [rsp+68h] [rbp+18h]
  NDIS_HANDLE NetBufferPoolHandle; // [rsp+70h] [rbp+20h]
  struct _NET_BUFFER_LIST **v59; // [rsp+78h] [rbp+28h]
  _WORD v60[72]; // [rsp+80h] [rbp+30h] BYREF
  int v61[24]; // [rsp+110h] [rbp+C0h] BYREF
  _UNKNOWN *retaddr; // [rsp+1B8h] [rbp+168h]

  v8 = 0;
  v54 = a4;
  NetBufferPoolHandle = a3;
  v59 = a8;
  if ( g_NVBugFixes2507Enabled )
    return VmsNblHelperCreateCloneNbl2507(NetBufferList, NetBufferListPoolHandle, a5, a6, a7, (__int64)a8);
  v56 = 0;
  memset(v60, 0, 0x88u);
  memset(v61, 0, sizeof(v61));
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( NetBufferList )
    {
      v32 = NetBufferList->NetBufferListInfo[18];
      if ( v32 )
      {
        v33 = v32[2];
        if ( v33 )
        {
          *(_DWORD *)(v33 + 184) = 584;
          *(_QWORD *)(v33 + 176) = "VmsNblHelperCreateCloneNbl";
          *(_QWORD *)(v33 + 168) = retaddr;
        }
      }
    }
  }
  v11 = 4;
  if ( byte_1401F96F0 )
    v11 = HIDWORD(qword_1401F96CC);
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( NetBufferList )
    {
      v34 = NetBufferList->NetBufferListInfo[18];
      if ( v34 )
      {
        v35 = v34[2];
        if ( v35 )
        {
          *(_DWORD *)(v35 + 184) = 75;
          *(_QWORD *)(v35 + 176) = "VmsNblIsSourceNicUntrusted";
          *(_QWORD *)(v35 + 168) = retaddr;
        }
      }
    }
  }
  v12 = NetBufferList->NetBufferListInfo[18];
  v13 = 0;
  if ( v12 )
  {
    v14 = v12[2];
    if ( v14 )
    {
      v15 = *(_QWORD *)(v14 + 24);
      if ( v15 )
      {
        if ( *(_DWORD *)(v15 + 1872) == 3 )
          v13 = *(_BYTE *)(v15 + 1877) == 0;
      }
    }
  }
  v16 = 24 * v11 + 15;
  if ( v16 <= 24 * v11 )
    v16 = 0xFFFFFFFFFFFFFF0LL;
  v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( !v13 || qword_1401F96E0 )
  {
    v61[0] = -267522035;
    v61[3] = KeGetCurrentProcessorNumberEx(0);
    LOBYTE(v61[1]) = 0;
    *(_QWORD *)&v61[6] = 0;
    *(_QWORD *)&v61[4] = 1;
    v61[2] = v13 | (qword_1401F96E0 != 0 ? 4 : 0);
    memset(&v61[11], 0, 24);
    LOBYTE(v61[10]) = 0;
    *(_QWORD *)&v61[8] = &v61[14];
    if ( v51 )
    {
      v61[17] = v11;
      *(_QWORD *)&v61[18] = v51;
    }
    else
    {
      v61[17] = 0;
      *(_QWORD *)&v61[18] = 0;
    }
    *(_QWORD *)&v61[20] = &g_BatchLibContext;
  }
  v18 = NetBufferList->NetBufferListInfo[0];
  LOWORD(v19) = 0;
  v57 = 0;
  v51[0] = 0;
  v52 = 0;
  *(_DWORD *)v55 = 0;
  v53 = 0;
  if ( !v18 )
    goto LABEL_18;
  if ( ((unsigned __int8)v18 & 0x1C) == 0 )
    goto LABEL_18;
  v8 = a6;
  if ( !a6 )
    goto LABEL_18;
  if ( ((unsigned __int8)v18 & 4) != 0 )
  {
    v55[0] = WORD1(v18) & 0x3FF;
    v19 = (WORD1(v18) & 0x3FF) + 20;
    goto LABEL_86;
  }
  if ( ((unsigned __int8)v18 & 8) != 0 )
  {
    HIDWORD(v57) = 70;
    v22 = 0;
    if ( (int)VmsPktParseFirstPacket(NetBufferList, v57, v60) >= 0 )
    {
      if ( v60[9] == 2048 )
      {
LABEL_81:
        *(_DWORD *)v55 = LOBYTE(v60[40]);
        v19 = LOBYTE(v60[40]) + 8;
        goto LABEL_86;
      }
      if ( v60[9] == 0x86DD )
      {
        LOBYTE(v53) = 1;
        goto LABEL_81;
      }
    }
    NetBufferListContext = -1073676273;
    goto LABEL_83;
  }
  if ( ((unsigned __int8)v18 & 0x11) != 0x11 )
  {
    v8 = 0;
    goto LABEL_18;
  }
  v19 = 34;
LABEL_86:
  v52 = v19;
  NdisAdvanceNetBufferListDataStart(NetBufferList, (unsigned __int16)v19, 0, 0);
  v51[0] = 1;
LABEL_18:
  CloneNetBufferList = NdisAllocateCloneNetBufferList(NetBufferList, NetBufferListPoolHandle, NetBufferPoolHandle, 0);
  v22 = CloneNetBufferList;
  if ( !CloneNetBufferList )
  {
    NetBufferListContext = -1073741670;
    LOBYTE(v21) = 2;
    WPP_RECORDER_SF_qqqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      12,
      13,
      (__int64)WPP_8b26f454089231c5607d0d1238616a13_Traceguids,
      (char)NetBufferList,
      (char)NetBufferListPoolHandle,
      (char)NetBufferPoolHandle,
      154);
    goto LABEL_83;
  }
  if ( !v8 )
    goto LABEL_20;
  v36 = NdisRetreatNetBufferListDataStart(CloneNetBufferList, (unsigned __int16)v19, 0, 0, 0);
  NetBufferListContext = v36;
  if ( v36 < 0 )
  {
    LOBYTE(v37) = 2;
    WPP_RECORDER_SF_qDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v37,
      12,
      14,
      (__int64)WPP_8b26f454089231c5607d0d1238616a13_Traceguids,
      (char)v22,
      v19,
      v36);
    goto LABEL_83;
  }
  HIBYTE(v53) = 1;
  NdisRetreatNetBufferListDataStart(NetBufferList, (unsigned __int16)v19, 0, 0, 0);
  FirstNetBuffer = NetBufferList->FirstNetBuffer;
  Alignment = v22->FirstNetBuffer;
  v51[0] = 0;
  while ( 1 )
  {
    if ( !FirstNetBuffer || !Alignment )
    {
      CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
      v41 = NetBufferList->NetBufferListInfo[18];
      v42 = CurrentProcessorNumber;
      if ( v41 )
      {
        v43 = v41[2];
        if ( v43 )
        {
          v44 = *(_QWORD *)(v43 + 24);
          if ( v44 )
          {
            if ( NetBufferList->NetBufferListInfo[2] )
            {
              v49 = (int)NetBufferList->NetBufferListInfo[2];
              if ( (v49 & 0x40000000) == 0 || v49 >= 0 )
                _InterlockedIncrement64((volatile signed __int64 *)(640 * v42 + v44 + 10224));
            }
            else
            {
              if ( ((__int64)NetBufferList->NetBufferListInfo[0] & 0x11) == 0x11 )
                _InterlockedIncrement64((volatile signed __int64 *)(640LL * CurrentProcessorNumber + v44 + 10224));
              v45 = (int)NetBufferList->NetBufferListInfo[0];
              if ( (v45 & 4) == 0 )
              {
                if ( (v45 & 8) != 0 )
                  _InterlockedIncrement64((volatile signed __int64 *)(640 * (v42 + 16) + v44));
                goto LABEL_20;
              }
            }
            _InterlockedIncrement64((volatile signed __int64 *)(640 * v42 + v44 + 10232));
          }
        }
      }
LABEL_20:
      NetBufferListContext = VmsNblHelperAllocateNetBufferListContext(v22, a7);
      if ( NetBufferListContext < 0 )
        goto LABEL_83;
      v25 = v22->NetBufferListInfo[18];
      v26 = v52;
      v27 = v54;
      v28 = (unsigned __int16)v52;
      *(_QWORD *)v25 = 1;
      v25[6] = 1;
      v25[8] = v28;
      if ( v27 )
        NdisCopyReceiveNetBufferListInfo(v22, NetBufferList);
      else
        NdisCopySendNetBufferListInfo(v22, NetBufferList);
      if ( v8 )
      {
        v22->NetBufferListInfo[0] = 0;
        if ( !v27 )
          v22->NetBufferListInfo[2] = 0;
      }
      v22->ParentNetBufferList = NetBufferList;
      if ( !a7 )
      {
        v24 = &NetBufferList->NetBufferListInfo[19];
        WORD1(v22->NetBufferListInfo[19]) = WORD1(NetBufferList->NetBufferListInfo[19]);
        BYTE4(v22->NetBufferListInfo[19]) = BYTE4(NetBufferList->NetBufferListInfo[19]);
        v29 = HIDWORD(v22->NetBufferListInfo[19]);
        if ( NetBufferList == (PNET_BUFFER_LIST)-296LL )
        {
          v30 = v29 & 0xFEFFFBFF | 0x400;
        }
        else
        {
          v46 = v29 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v29) & 0x400;
          HIDWORD(v22->NetBufferListInfo[19]) = v46;
          v47 = v46 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v46) & 0x7FF800;
          HIDWORD(v22->NetBufferListInfo[19]) = v47;
          v48 = v47 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v47) & 0x800000;
          HIDWORD(v22->NetBufferListInfo[19]) = v48;
          v30 = v48 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v48) & 0x1000000;
        }
        HIDWORD(v22->NetBufferListInfo[19]) = v30;
        HIDWORD(v22->NetBufferListInfo[19]) = v30 ^ (HIDWORD(NetBufferList->NetBufferListInfo[19]) ^ v30) & 0x100;
      }
      if ( !a5 )
        VmsNblHelperRefCountIncrement(NetBufferList);
      NetBufferListContext = 0;
      *v59 = v22;
      goto LABEL_31;
    }
    NetBufferListContext = NdisCopyFromNetBufferToNetBuffer(
                             Alignment,
                             0,
                             (unsigned __int16)v52,
                             FirstNetBuffer,
                             0,
                             &v56);
    if ( NetBufferListContext < 0 )
      goto LABEL_83;
    if ( v56 != (unsigned __int16)v52 && v56 < FirstNetBuffer->DataLength )
      break;
    LOBYTE(BytesCopied) = v53;
    NetBufferListContext = SegLibDeferredChecksumPacket((int)v61, (int)Alignment, v55[0], BytesCopied);
    if ( NetBufferListContext < 0 )
      goto LABEL_83;
    FirstNetBuffer = (_NET_BUFFER *)FirstNetBuffer->Link.Alignment;
    Alignment = (struct _NET_BUFFER *)Alignment->Link.Alignment;
  }
  NetBufferListContext = -1073741670;
LABEL_83:
  v26 = v52;
LABEL_31:
  LOBYTE(v24) = 1;
  BLFlushBatchOpContextEx(v61, 0, v24);
  if ( NetBufferListContext < 0 )
  {
    if ( v51[0] )
      NdisRetreatNetBufferListDataStart(NetBufferList, v26, 0, 0, 0);
    if ( v22 )
    {
      if ( HIBYTE(v53) )
        NdisAdvanceNetBufferListDataStart(v22, v26, 1u, 0);
      NdisFreeCloneNetBufferList(v22, 0);
    }
  }
  return (unsigned int)NetBufferListContext;
}

```

## disassembly

```asm
0x14004fd84  push    rbp
0x14004fd86  push    rsi
0x14004fd87  push    rdi
0x14004fd88  push    r12
0x14004fd8a  push    r13
0x14004fd8c  push    r14
0x14004fd8e  push    r15
0x14004fd90  sub     rsp, 180h
0x14004fd97  lea     rbp, [rsp+50h]
0x14004fd9c  mov     [rbp+160h+arg_18], rbx
0x14004fda3  mov     rax, cs:__security_cookie
0x14004fdaa  xor     rax, rbp
0x14004fdad  mov     [rbp+160h+var_40], rax
0x14004fdb4  mov     rax, [rbp+160h+arg_38]
0x14004fdbb  xor     r15d, r15d
0x14004fdbe  cmp     cs:g_NVBugFixes2507Enabled, r15d
0x14004fdc5  mov     r13, rdx
0x14004fdc8  mov     byte ptr [rbp+160h+var_158+2], r9b
0x14004fdcc  mov     r14, rcx
0x14004fdcf  mov     [rbp+160h+NetBufferPoolHandle], r8
0x14004fdd3  mov     [rbp+160h+var_138], rax
0x14004fdd7  jnz     loc_140050414
0x14004fddd  xor     edx, edx; Val
0x14004fddf  mov     [rbp+160h+var_150], r15d
0x14004fde3  mov     r8d, 88h; Size
0x14004fde9  lea     rcx, [rbp+160h+var_130]; void *
0x14004fded  call    memset
0x14004fdf2  xor     edx, edx; Val
0x14004fdf4  lea     r8d, [r15+60h]; Size
0x14004fdf8  lea     rcx, [rbp+160h+var_A0]; void *
0x14004fdff  call    memset
0x14004fe04  mov     eax, cs:VmsDiagnosticFlags
0x14004fe0a  mov     rcx, [rbp+168h]
0x14004fe11  test    al, 1
0x14004fe13  jnz     loc_1400500D5
0x14004fe19  cmp     cs:byte_1401F96F0, r15b
0x14004fe20  mov     edi, 4
0x14004fe25  mov     eax, cs:VmsDiagnosticFlags
0x14004fe2b  cmovnz  edi, dword ptr cs:qword_1401F96CC+4
0x14004fe32  mov     rcx, [rbp+168h]
0x14004fe39  test    al, 1
0x14004fe3b  jnz     loc_14005011F
0x14004fe41  mov     rax, [r14+120h]
0x14004fe48  mov     bl, r15b
0x14004fe4b  test    rax, rax
0x14004fe4e  jz      short loc_14004FE6F
0x14004fe50  mov     rax, [rax+10h]
0x14004fe54  test    rax, rax
0x14004fe57  jz      short loc_14004FE6F
0x14004fe59  mov     rax, [rax+18h]
0x14004fe5d  test    rax, rax
0x14004fe60  jz      short loc_14004FE6F
0x14004fe62  cmp     dword ptr [rax+750h], 3
0x14004fe69  jz      loc_140050380
0x14004fe6f  lea     rcx, [rdi+rdi*2]
0x14004fe73  shl     rcx, 3
0x14004fe77  lea     rax, [rcx+0Fh]
0x14004fe7b  cmp     rax, rcx
0x14004fe7e  ja      short loc_14004FE8A
0x14004fe80  mov     rax, 0FFFFFFFFFFFFFF0h
0x14004fe8a  and     rax, 0FFFFFFFFFFFFFFF0h
0x14004fe8e  call    __chkstk_0
0x14004fe93  sub     rsp, rax
0x14004fe96  lea     rsi, [rsp+1B0h+var_160]
0x14004fe9b  cmp     bl, 1
0x14004fe9e  jz      loc_140050169
0x14004fea4  xor     ecx, ecx; ProcNumber
0x14004fea6  mov     [rbp+160h+var_A0], 0F00DF00Dh
0x14004feb0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004feb7  nop     dword ptr [rax+rax+00h]
0x14004febc  mov     [rbp+160h+var_94], eax
0x14004fec2  mov     rax, cs:qword_1401F96E0
0x14004fec9  neg     rax
0x14004fecc  movzx   edx, bl
0x14004fecf  lea     rax, [rbp+160h+var_68]
0x14004fed6  mov     [rbp+160h+var_9C], r15b
0x14004fedd  sbb     ecx, ecx
0x14004fedf  mov     [rbp+160h+var_88], r15
0x14004fee6  and     ecx, 4
0x14004fee9  mov     [rbp+160h+var_90], 1
0x14004fef4  or      ecx, edx
0x14004fef6  mov     [rbp+160h+var_70], r15
0x14004fefd  mov     [rbp+160h+var_98], ecx
0x14004ff03  mov     [rbp+160h+var_74], r15d
0x14004ff0a  mov     [rbp+160h+var_78], r15b
0x14004ff11  mov     [rbp+160h+var_68], r15
0x14004ff18  mov     [rbp+160h+var_60], r15d
0x14004ff1f  mov     [rbp+160h+var_80], rax
0x14004ff26  test    rsi, rsi
0x14004ff29  jz      loc_1400500C2
0x14004ff2f  mov     [rbp+160h+var_5C], edi
0x14004ff35  mov     [rbp+160h+var_58], rsi
0x14004ff3c  lea     rax, g_BatchLibContext
0x14004ff43  mov     [rbp+160h+var_50], rax
0x14004ff4a  mov     rbx, [r14+90h]
0x14004ff51  mov     r12d, r15d
0x14004ff54  mov     [rbp+160h+var_148], r15
0x14004ff58  mov     [rbp+160h+var_160], r15b
0x14004ff5c  mov     byte ptr [rbp+160h+var_158+1], r15b
0x14004ff60  mov     [rbp+160h+var_15C], r15d
0x14004ff64  mov     dword ptr [rbp+160h+var_154], r15d
0x14004ff68  mov     byte ptr [rbp+160h+var_158], r15b
0x14004ff6c  test    rbx, rbx
0x14004ff6f  jnz     loc_140050441
0x14004ff75  mov     r8, [rbp+160h+NetBufferPoolHandle]; NetBufferPoolHandle
0x14004ff79  xor     r9d, r9d; AllocateCloneFlags
0x14004ff7c  mov     rdx, r13; NetBufferListPoolHandle
0x14004ff7f  mov     rcx, r14; OriginalNetBufferList
0x14004ff82  call    cs:__imp_NdisAllocateCloneNetBufferList
0x14004ff89  nop     dword ptr [rax+rax+00h]
0x14004ff8e  mov     rsi, rax
0x14004ff91  test    rax, rax
0x14004ff94  jz      loc_1400504E3
0x14004ff9a  test    r15b, r15b
0x14004ff9d  jnz     loc_14005017B
0x14004ffa3  mov     ebx, [rbp+160h+arg_30]
0x14004ffa9  mov     edx, 28h ; '('
0x14004ffae  mov     r9d, 624E7356h
0x14004ffb4  mov     dword ptr [rsp+1B0h+FreeMdlHandler], ebx; int
0x14004ffb8  mov     rcx, rsi; NetBufferList
0x14004ffbb  call    VmsNblHelperAllocateNetBufferListContext
0x14004ffc0  mov     edi, eax
0x14004ffc2  test    eax, eax
0x14004ffc4  js      loc_14005049D
0x14004ffca  mov     rcx, [rsi+120h]
0x14004ffd1  mov     rdx, r14; SrcNetBufferList
0x14004ffd4  mov     r12d, [rbp+160h+var_15C]
0x14004ffd8  mov     dil, byte ptr [rbp+160h+var_158+2]
0x14004ffdc  movzx   eax, r12w
0x14004ffe0  mov     qword ptr [rcx], 1
0x14004ffe7  mov     dword ptr [rcx+18h], 1
0x14004ffee  mov     [rcx+20h], eax
0x14004fff1  mov     rcx, rsi; DestNetBufferList
0x14004fff4  test    dil, dil
0x14004fff7  jnz     loc_14005036F
0x14004fffd  call    cs:__imp_NdisCopySendNetBufferListInfo
0x140050004  nop     dword ptr [rax+rax+00h]
0x140050009  test    r15b, r15b
0x14005000c  jnz     loc_1400502FD
0x140050012  mov     [rsi+18h], r14
0x140050016  test    ebx, ebx
0x140050018  jnz     short loc_140050067
0x14005001a  lea     r8, [r14+128h]
0x140050021  movzx   eax, word ptr [r8+2]
0x140050026  mov     [rsi+12Ah], ax
0x14005002d  mov     al, [r8+4]
0x140050031  mov     [rsi+12Ch], al
0x140050037  mov     edx, [rsi+12Ch]
0x14005003d  test    r8, r8
0x140050040  jnz     loc_140050321
0x140050046  btr     edx, 18h
0x14005004a  bts     edx, 0Ah
0x14005004e  mov     [rsi+12Ch], edx
0x140050054  mov     eax, edx
0x140050056  xor     eax, [r8+4]
0x14005005a  and     eax, 100h
0x14005005f  xor     eax, edx
0x140050061  mov     [rsi+12Ch], eax
0x140050067  cmp     [rbp+160h+arg_20], 0
0x14005006e  jz      loc_14005057C
0x140050074  mov     rax, [rbp+160h+var_138]
0x140050078  xor     edi, edi
0x14005007a  mov     [rax], rsi
0x14005007d  mov     r8b, 1
0x140050080  lea     rcx, [rbp+160h+var_A0]
0x140050087  xor     edx, edx
0x140050089  call    BLFlushBatchOpContextEx
0x14005008e  test    edi, edi
0x140050090  js      loc_140050589
0x140050096  mov     eax, edi
0x140050098  mov     rcx, [rbp+160h+var_40]
0x14005009f  xor     rcx, rbp; StackCookie
0x1400500a2  call    __security_check_cookie
0x1400500a7  mov     rbx, [rbp+160h+arg_18]
0x1400500ae  lea     rsp, [rbp+130h]
0x1400500b5  pop     r15
0x1400500b7  pop     r14
0x1400500b9  pop     r13
0x1400500bb  pop     r12
0x1400500bd  pop     rdi
0x1400500be  pop     rsi
0x1400500bf  pop     rbp
0x1400500c0  retn
0x1400500c2  mov     [rbp+160h+var_5C], r15d
0x1400500c9  mov     [rbp+160h+var_58], r15
0x1400500d0  jmp     loc_14004FF3C
0x1400500d5  test    r14, r14
0x1400500d8  jz      loc_14004FE19
0x1400500de  mov     rax, [r14+120h]
0x1400500e5  test    rax, rax
0x1400500e8  jz      loc_14004FE19
0x1400500ee  mov     rax, [rax+10h]
0x1400500f2  test    rax, rax
0x1400500f5  jz      loc_14004FE19
0x1400500fb  lea     rdx, aVmsnblhelpercr_1; "VmsNblHelperCreateCloneNbl"
0x140050102  mov     dword ptr [rax+0B8h], 248h
0x14005010c  mov     [rax+0B0h], rdx
0x140050113  mov     [rax+0A8h], rcx
0x14005011a  jmp     loc_14004FE19
0x14005011f  test    r14, r14
0x140050122  jz      loc_14004FE41
0x140050128  mov     rax, [r14+120h]
0x14005012f  test    rax, rax
0x140050132  jz      loc_14004FE41
0x140050138  mov     rax, [rax+10h]
0x14005013c  test    rax, rax
0x14005013f  jz      loc_14004FE41
0x140050145  lea     rdx, aVmsnblissource; "VmsNblIsSourceNicUntrusted"
0x14005014c  mov     dword ptr [rax+0B8h], 4Bh ; 'K'
0x140050156  mov     [rax+0B0h], rdx
0x14005015d  mov     [rax+0A8h], rcx
0x140050164  jmp     loc_14004FE41
0x140050169  cmp     cs:qword_1401F96E0, r15
0x140050170  jnz     loc_14004FEA4
0x140050176  jmp     loc_14004FF4A
0x14005017b  movzx   r12d, r12w
0x14005017f  xor     r9d, r9d; AllocateMdlHandler
0x140050182  mov     edx, r12d; DataOffsetDelta
0x140050185  mov     [rsp+1B0h+FreeMdlHandler], 0; FreeMdlHandler
0x14005018e  xor     r8d, r8d; DataBackFill
0x140050191  mov     rcx, rsi; NetBufferList
0x140050194  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x14005019b  nop     dword ptr [rax+rax+00h]
0x1400501a0  mov     edi, eax
0x1400501a2  test    eax, eax
0x1400501a4  js      loc_14005052C
0x1400501aa  xor     r9d, r9d; AllocateMdlHandler
0x1400501ad  mov     byte ptr [rbp+160h+var_158+1], 1
0x1400501b1  xor     r8d, r8d; DataBackFill
0x1400501b4  mov     [rsp+1B0h+FreeMdlHandler], 0; FreeMdlHandler
0x1400501bd  mov     edx, r12d; DataOffsetDelta
0x1400501c0  mov     rcx, r14; NetBufferList
0x1400501c3  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x1400501ca  nop     dword ptr [rax+rax+00h]
0x1400501cf  mov     r12, [r14+8]
0x1400501d3  mov     r13, [rsi+8]
0x1400501d7  mov     [rbp+160h+var_160], 0
0x1400501db  test    r12, r12
0x1400501de  jz      loc_140050268
0x1400501e4  test    r13, r13
0x1400501e7  jz      short loc_140050268
0x1400501e9  lea     rax, [rbp+160h+var_150]
0x1400501ed  mov     r9, r12; Source
0x1400501f0  mov     [rsp+1B0h+BytesCopied], rax; BytesCopied
0x1400501f5  xor     edx, edx; DestinationOffset
0x1400501f7  mov     eax, [rbp+160h+var_15C]
0x1400501fa  mov     rcx, r13; Destination
0x1400501fd  movzx   r8d, ax; BytesToCopy
0x140050201  mov     dword ptr [rsp+1B0h+FreeMdlHandler], 0; SourceOffset
0x140050209  call    cs:__imp_NdisCopyFromNetBufferToNetBuffer
0x140050210  nop     dword ptr [rax+rax+00h]
0x140050215  mov     edi, eax
0x140050217  test    eax, eax
0x140050219  js      loc_14005049D
0x14005021f  mov     edx, [rbp+160h+var_15C]
0x140050222  mov     ecx, [rbp+160h+var_150]
0x140050225  movzx   eax, dx
0x140050228  cmp     ecx, eax
0x14005022a  jnz     loc_140050567
0x140050230  mov     al, byte ptr [rbp+160h+var_158]
0x140050233  lea     rcx, [rbp+160h+var_A0]; int
0x14005023a  mov     byte ptr [rsp+1B0h+BytesCopied], al; int
0x14005023e  mov     r8, rbx
0x140050241  mov     eax, dword ptr [rbp+160h+var_154]
0x140050244  mov     rdx, r13; int
0x140050247  mov     word ptr [rsp+1B0h+FreeMdlHandler], ax; __int16
0x14005024c  call    SegLibDeferredChecksumPacket
0x140050251  mov     edi, eax
0x140050253  test    eax, eax
0x140050255  js      loc_14005049D
0x14005025b  mov     r12, [r12]
0x14005025f  mov     r13, [r13+0]
0x140050263  jmp     loc_1400501DB
0x140050268  xor     ecx, ecx; ProcNumber
0x14005026a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140050271  nop     dword ptr [rax+rax+00h]
0x140050276  mov     rdx, [r14+120h]
0x14005027d  mov     r8d, eax
0x140050280  test    rdx, rdx
0x140050283  jz      loc_14004FFA3
0x140050289  mov     rdx, [rdx+10h]
0x14005028d  test    rdx, rdx
0x140050290  jz      loc_14004FFA3
0x140050296  mov     rdx, [rdx+18h]
0x14005029a  test    rdx, rdx
0x14005029d  jz      loc_14004FFA3
0x1400502a3  cmp     qword ptr [r14+0A0h], 0
0x1400502ab  jnz     loc_1400503AA
0x1400502b1  mov     eax, [r14+90h]
0x1400502b8  and     eax, 11h
0x1400502bb  cmp     al, 11h
0x1400502bd  jnz     short loc_1400502D0
0x1400502bf  lea     rcx, [r8+r8*4]
0x1400502c3  shl     rcx, 7
0x1400502c7  lock inc qword ptr [rcx+rdx+27F0h]
0x1400502d0  mov     eax, [r14+90h]
0x1400502d7  test    al, 4
0x1400502d9  jnz     loc_140050394
0x1400502df  test    al, 8
0x1400502e1  jz      loc_14004FFA3
  ... truncated ...
```
