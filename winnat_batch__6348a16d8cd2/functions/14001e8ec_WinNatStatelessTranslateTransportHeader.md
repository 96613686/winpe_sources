# WinNatStatelessTranslateTransportHeader

- ea: `0x14001e8ec`
- end: `0x14001ec80`
- name: `WinNatStatelessTranslateTransportHeader`
- size: `916`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PNET_BUFFER NetBuffer, char, char, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001e2a0`
- `0x14001e77c`

## callees

- `0x140005fc8`
- `0x1400062f0`
- `0x1400093b8`
- `0x14000bb38`
- `0x14000caa0`
- `0x14001bb90`
- `0x14001d20c`
- `0x14001e8ec`

## import_xrefs

- `NETIO!RtlCopyBufferToMdl` at `0x14001e97c`
- `NETIO!RtlCopyBufferToMdl` at `0x14001e97c`
- `NDIS!NdisGetDataBuffer` at `0x14001e9b6`
- `NDIS!NdisGetDataBuffer` at `0x14001e9b6`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001e92f`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001e92f`

## pseudocode

```c
__int64 __fastcall WinNatStatelessTranslateTransportHeader(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        _QWORD *a5,
        PNET_BUFFER NetBuffer,
        char a7,
        char a8,
        char a9)
{
  PNET_BUFFER v9; // rbp
  ULONG v11; // edx
  unsigned int v14; // r14d
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  _QWORD *v21; // rdx
  __int64 v22; // rcx
  _WORD *DataBuffer; // rdi
  __int64 v24; // r8
  __int64 v25; // r9
  char v26; // r15
  unsigned __int16 v27; // r12
  char v28; // al
  __int64 v29; // r8
  unsigned __int16 v30; // si
  unsigned int v31; // ecx
  ULONG DataLength; // edx
  unsigned int v33; // ecx
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v40; // [rsp+A0h] [rbp+18h] BYREF

  v9 = NetBuffer;
  v11 = *(unsigned __int8 *)(a3 + 149);
  v14 = 0;
  v40 = 0;
  NdisAdvanceNetBufferDataStart(NetBuffer, v11, 0, 0);
  v15 = *(unsigned __int8 *)(a3 + 16);
  if ( (unsigned __int8)v15 > 0x3Au )
    return v14;
  v16 = 0x400000000020042LL;
  if ( !_bittest64(&v16, v15) )
    return v14;
  RtlCopyBufferToMdl(*(_QWORD *)(a3 + 8), v9->Link.Region, v9->CurrentMdlOffset, *(unsigned __int8 *)(a3 + 148), &v40);
  if ( *(unsigned __int8 *)(a3 + 148) != v40 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v18, v17, v19, v20);
  DataBuffer = NdisGetDataBuffer(v9, *(unsigned __int8 *)(a3 + 148), 0, 1u, 0);
  if ( !DataBuffer )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v22, v21, v24, v25);
    return (unsigned int)-1073741823;
  }
  v26 = a7;
  v27 = 0;
  v28 = *(_BYTE *)(a3 + 16);
  v29 = 2;
  if ( a7 )
  {
    if ( v28 == 17 || v28 == 6 )
    {
      LOBYTE(v25) = 16;
      v27 = WinNatFixupChecksum((int)a3 + 160, 16, (int)a3 + 188, v25, 0, a1, 4, a2, 4, 0);
    }
    v30 = *(_WORD *)(a3 + 154);
    goto LABEL_24;
  }
  if ( v28 == 6 )
  {
    v21 = a5;
    if ( (*a4 & 4) != 0 || *a5 )
    {
      v31 = *a4 & 0xFFFFFFFC | 2;
      *a4 = v31;
      *a4 = v31 & 0xFC00FFFF | (*(unsigned __int8 *)(a3 + 149) << 16);
      if ( *v21 )
        DataLength = 0;
      else
        DataLength = v9->DataLength;
      DataBuffer[8] = WinNatChecksumDatagram(0, DataLength, a1, a2, 16, *(unsigned __int8 *)(a3 + 16));
      goto LABEL_23;
    }
    goto LABEL_22;
  }
  if ( v28 != 17 || (*a4 & 8) == 0 )
  {
LABEL_22:
    LOBYTE(v21) = 4;
    v27 = WinNatFixupChecksum((int)a3 + 156, (_DWORD)v21, (int)a3 + 184, 4, 0, a1, 16, a2, 16, 0);
    goto LABEL_23;
  }
  v33 = *a4 & 0xFFFFFFFC | 2;
  *a4 = v33;
  *a4 = v33 & 0xFC00FFFF | (*(unsigned __int8 *)(a3 + 149) << 16);
  DataBuffer[3] = WinNatChecksumDatagram(0, v9->DataLength, a1, a2, 16, *(unsigned __int8 *)(a3 + 16));
LABEL_23:
  v30 = *(_WORD *)(a3 + 182);
LABEL_24:
  v34 = *(unsigned __int8 *)(a3 + 16);
  v35 = (unsigned int)*(unsigned __int8 *)(a3 + 16) - 1;
  if ( *(_BYTE *)(a3 + 16) == 1 )
    goto LABEL_41;
  if ( *(_BYTE *)(a3 + 16) == 6 )
  {
    LOBYTE(v34) = v26;
    WinNatTranslateTcpHeader(v30, v27, (_DWORD)DataBuffer, v34, a8, a9);
    return v14;
  }
  v35 = (unsigned int)*(unsigned __int8 *)(a3 + 16) - 17;
  if ( *(_BYTE *)(a3 + 16) == 17 )
  {
    LOBYTE(v34) = v26;
    WinNatTranslateUdpHeader(v30, v27, (_DWORD)DataBuffer, v34, a8, a9);
    return v14;
  }
  if ( *(_BYTE *)(a3 + 16) == 58 )
  {
LABEL_41:
    if ( a9 )
    {
      LOBYTE(v21) = *(_BYTE *)DataBuffer;
      LOBYTE(v35) = *(_BYTE *)(a3 + 16);
      if ( (unsigned __int8)WinNatIsIcmpErrorMessage(v35, v21, v29) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v35, v36, v37, v34);
        LOBYTE(v34) = *(_BYTE *)(a3 + 16);
      }
    }
    if ( v26 )
    {
      LODWORD(a1) = a3 + 160;
      LODWORD(a2) = a3 + 188;
    }
    LOWORD(v35) = 23;
    if ( !(unsigned __int8)WinNatTranslateIcmpHeader(
                             v35,
                             2,
                             a1,
                             a2,
                             v30,
                             v34,
                             (__int64)DataBuffer,
                             v26,
                             a8,
                             v9->DataLength) )
      return (unsigned int)-1073741285;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v35, v21, v29, v34);
  }
  return v14;
}

```

## disassembly

```asm
0x14001e8ec  mov     rax, rsp
0x14001e8ef  mov     [rax+10h], rbx
0x14001e8f3  mov     [rax+8], rcx
0x14001e8f7  push    rbp
0x14001e8f8  push    rsi
0x14001e8f9  push    rdi
0x14001e8fa  push    r12
0x14001e8fc  push    r13
0x14001e8fe  push    r14
0x14001e900  push    r15
0x14001e902  sub     rsp, 50h
0x14001e906  mov     rbp, [rsp+88h+NetBuffer]
0x14001e90e  mov     r13, rdx
0x14001e911  movzx   edx, byte ptr [r8+95h]; DataOffsetDelta
0x14001e919  mov     rsi, r9
0x14001e91c  mov     rbx, r8
0x14001e91f  xor     r14d, r14d
0x14001e922  xor     r8d, r8d; FreeMdl
0x14001e925  mov     [rax+18h], r14
0x14001e929  mov     rcx, rbp; NetBuffer
0x14001e92c  xor     r9d, r9d; FreeMdlHandler
0x14001e92f  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001e936  nop     dword ptr [rax+rax+00h]
0x14001e93b  movzx   eax, byte ptr [rbx+10h]
0x14001e93f  cmp     al, 3Ah ; ':'
0x14001e941  ja      loc_14001EC64
0x14001e947  mov     rcx, 400000000020042h
0x14001e951  bt      rcx, rax
0x14001e955  jnb     loc_14001EC64
0x14001e95b  movzx   r9d, byte ptr [rbx+94h]
0x14001e963  lea     rax, [rsp+88h+arg_10]
0x14001e96b  mov     r8d, [rbp+10h]
0x14001e96f  mov     rdx, [rbp+8]
0x14001e973  mov     rcx, [rbx+8]
0x14001e977  mov     qword ptr [rsp+88h+AlignOffset], rax
0x14001e97c  call    cs:__imp_RtlCopyBufferToMdl
0x14001e983  nop     dword ptr [rax+rax+00h]
0x14001e988  movzx   eax, byte ptr [rbx+94h]
0x14001e98f  cmp     rax, [rsp+88h+arg_10]
0x14001e997  jz      short loc_14001E99E
0x14001e999  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001e99e  movzx   edx, byte ptr [rbx+94h]; BytesNeeded
0x14001e9a5  mov     r9d, 1; AlignMultiple
0x14001e9ab  xor     r8d, r8d; Storage
0x14001e9ae  mov     [rsp+88h+AlignOffset], r14d; AlignOffset
0x14001e9b3  mov     rcx, rbp; NetBuffer
0x14001e9b6  call    cs:__imp_NdisGetDataBuffer
0x14001e9bd  nop     dword ptr [rax+rax+00h]
0x14001e9c2  mov     rdi, rax
0x14001e9c5  test    rax, rax
0x14001e9c8  jnz     short loc_14001E9DA
0x14001e9ca  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001e9cf  mov     r14d, 0C0000001h
0x14001e9d5  jmp     loc_14001EC64
0x14001e9da  mov     r15b, [rsp+88h+arg_30]
0x14001e9e2  xor     r12d, r12d
0x14001e9e5  mov     al, [rbx+10h]
0x14001e9e8  lea     r8d, [r12+2]
0x14001e9ed  test    r15b, r15b
0x14001e9f0  jz      short loc_14001EA4D
0x14001e9f2  cmp     al, 11h
0x14001e9f4  jz      short loc_14001E9FA
0x14001e9f6  cmp     al, 6
0x14001e9f8  jnz     short loc_14001EA41
0x14001e9fa  xor     eax, eax
0x14001e9fc  lea     r8, [rbx+0BCh]
0x14001ea03  mov     word ptr [rsp+88h+var_40], ax
0x14001ea08  lea     rcx, [rbx+0A0h]
0x14001ea0f  mov     rax, [rsp+88h+arg_0]
0x14001ea17  xor     edx, edx
0x14001ea19  mov     [rsp+88h+var_48], 4
0x14001ea1e  mov     r9b, 10h
0x14001ea21  mov     [rsp+88h+var_50], r13
0x14001ea26  mov     byte ptr [rsp+88h+var_58], 4
0x14001ea2b  mov     [rsp+88h+var_60], rax
0x14001ea30  mov     word ptr [rsp+88h+AlignOffset], dx
0x14001ea35  mov     dl, r9b
0x14001ea38  call    WinNatFixupChecksum
0x14001ea3d  movzx   r12d, ax
0x14001ea41  movzx   esi, word ptr [rbx+9Ah]
0x14001ea48  jmp     loc_14001EB5E
0x14001ea4d  cmp     al, 6
0x14001ea4f  jnz     short loc_14001EABC
0x14001ea51  mov     ecx, [rsi]
0x14001ea53  mov     rdx, [rsp+88h+arg_20]
0x14001ea5b  test    cl, 4
0x14001ea5e  jnz     short loc_14001EA69
0x14001ea60  cmp     [rdx], r12
0x14001ea63  jz      loc_14001EB0E
0x14001ea69  and     ecx, 0FFFFFFFEh
0x14001ea6c  or      ecx, r8d
0x14001ea6f  mov     [rsi], ecx
0x14001ea71  and     ecx, 0FC00FFFFh
0x14001ea77  movzx   eax, byte ptr [rbx+95h]
0x14001ea7e  shl     eax, 10h
0x14001ea81  or      eax, ecx
0x14001ea83  mov     [rsi], eax
0x14001ea85  cmp     [rdx], r12
0x14001ea88  jz      short loc_14001EA8E
0x14001ea8a  xor     edx, edx
0x14001ea8c  jmp     short loc_14001EA91
0x14001ea8e  mov     edx, [rbp+18h]
0x14001ea91  movzx   eax, byte ptr [rbx+10h]
0x14001ea95  mov     r9, r13
0x14001ea98  mov     r8, [rsp+88h+arg_0]
0x14001eaa0  xor     ecx, ecx
0x14001eaa2  mov     dword ptr [rsp+88h+var_60], eax
0x14001eaa6  mov     [rsp+88h+AlignOffset], 10h
0x14001eaae  call    WinNatChecksumDatagram
0x14001eab3  mov     [rdi+10h], ax
0x14001eab7  jmp     loc_14001EB57
0x14001eabc  cmp     al, 11h
0x14001eabe  jnz     short loc_14001EB0E
0x14001eac0  mov     ecx, [rsi]
0x14001eac2  test    cl, 8
0x14001eac5  jz      short loc_14001EB0E
0x14001eac7  and     ecx, 0FFFFFFFEh
0x14001eaca  mov     r9, r13
0x14001eacd  or      ecx, r8d
0x14001ead0  mov     r8, [rsp+88h+arg_0]
0x14001ead8  mov     [rsi], ecx
0x14001eada  and     ecx, 0FC00FFFFh
0x14001eae0  movzx   eax, byte ptr [rbx+95h]
0x14001eae7  shl     eax, 10h
0x14001eaea  or      eax, ecx
0x14001eaec  xor     ecx, ecx
0x14001eaee  mov     [rsi], eax
0x14001eaf0  movzx   eax, byte ptr [rbx+10h]
0x14001eaf4  mov     edx, [rbp+18h]
0x14001eaf7  mov     dword ptr [rsp+88h+var_60], eax
0x14001eafb  mov     [rsp+88h+AlignOffset], 10h
0x14001eb03  call    WinNatChecksumDatagram
0x14001eb08  mov     [rdi+6], ax
0x14001eb0c  jmp     short loc_14001EB57
0x14001eb0e  xor     eax, eax
0x14001eb10  lea     r8, [rbx+0B8h]
0x14001eb17  mov     word ptr [rsp+88h+var_40], ax
0x14001eb1c  lea     rcx, [rbx+9Ch]
0x14001eb23  mov     rax, [rsp+88h+arg_0]
0x14001eb2b  xor     r9d, r9d
0x14001eb2e  mov     [rsp+88h+var_48], 10h
0x14001eb33  mov     [rsp+88h+var_50], r13
0x14001eb38  mov     byte ptr [rsp+88h+var_58], 10h
0x14001eb3d  mov     [rsp+88h+var_60], rax
0x14001eb42  mov     word ptr [rsp+88h+AlignOffset], r9w
0x14001eb48  mov     r9b, 4
0x14001eb4b  mov     dl, r9b
0x14001eb4e  call    WinNatFixupChecksum
0x14001eb53  movzx   r12d, ax
0x14001eb57  movzx   esi, word ptr [rbx+0B6h]
0x14001eb5e  movzx   r9d, byte ptr [rbx+10h]
0x14001eb63  mov     ecx, r9d
0x14001eb66  sub     ecx, 1
0x14001eb69  jz      short loc_14001EBDE
0x14001eb6b  sub     ecx, 5
0x14001eb6e  jz      short loc_14001EBB1
0x14001eb70  sub     ecx, 0Bh
0x14001eb73  jz      short loc_14001EB84
0x14001eb75  cmp     ecx, 29h ; ')'
0x14001eb78  jz      short loc_14001EBDE
0x14001eb7a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001eb7f  jmp     loc_14001EC64
0x14001eb84  mov     al, [rsp+88h+arg_40]
0x14001eb8b  mov     r9b, r15b
0x14001eb8e  mov     byte ptr [rsp+88h+var_60], al
0x14001eb92  mov     r8, rdi
0x14001eb95  mov     al, [rsp+88h+arg_38]
0x14001eb9c  movzx   edx, r12w
0x14001eba0  movzx   ecx, si
0x14001eba3  mov     byte ptr [rsp+88h+AlignOffset], al
0x14001eba7  call    WinNatTranslateUdpHeader
0x14001ebac  jmp     loc_14001EC64
0x14001ebb1  mov     al, [rsp+88h+arg_40]
0x14001ebb8  mov     r9b, r15b
0x14001ebbb  mov     byte ptr [rsp+88h+var_60], al
0x14001ebbf  mov     r8, rdi
0x14001ebc2  mov     al, [rsp+88h+arg_38]
0x14001ebc9  movzx   edx, r12w
0x14001ebcd  movzx   ecx, si
0x14001ebd0  mov     byte ptr [rsp+88h+AlignOffset], al
0x14001ebd4  call    WinNatTranslateTcpHeader
0x14001ebd9  jmp     loc_14001EC64
0x14001ebde  cmp     [rsp+88h+arg_40], r14b
0x14001ebe6  jz      short loc_14001EBFF
0x14001ebe8  mov     dl, [rdi]
0x14001ebea  mov     cl, r9b
0x14001ebed  call    WinNatIsIcmpErrorMessage
0x14001ebf2  test    al, al
0x14001ebf4  jz      short loc_14001EBFF
0x14001ebf6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001ebfb  mov     r9b, [rbx+10h]
0x14001ebff  test    r15b, r15b
0x14001ec02  jz      short loc_14001EC1A
0x14001ec04  lea     rax, [rbx+0A0h]
0x14001ec0b  mov     [rsp+88h+arg_0], rax
0x14001ec13  lea     r13, [rbx+0BCh]
0x14001ec1a  mov     eax, [rbp+18h]
0x14001ec1d  mov     edx, 2
0x14001ec22  mov     r8, [rsp+88h+arg_0]
0x14001ec2a  mov     cx, 17h
0x14001ec2e  mov     [rsp+88h+var_40], eax
0x14001ec32  mov     al, [rsp+88h+arg_38]
0x14001ec39  mov     [rsp+88h+var_48], al
0x14001ec3d  mov     byte ptr [rsp+88h+var_50], r15b
0x14001ec42  mov     [rsp+88h+var_58], rdi
0x14001ec47  mov     byte ptr [rsp+88h+var_60], r9b
0x14001ec4c  mov     r9, r13
0x14001ec4f  mov     word ptr [rsp+88h+AlignOffset], si
0x14001ec54  call    WinNatTranslateIcmpHeader
0x14001ec59  test    al, al
0x14001ec5b  mov     ecx, 0C000021Bh
0x14001ec60  cmovz   r14d, ecx
0x14001ec64  mov     rbx, [rsp+88h+arg_8]
0x14001ec6c  mov     eax, r14d
0x14001ec6f  add     rsp, 50h
0x14001ec73  pop     r15
0x14001ec75  pop     r14
0x14001ec77  pop     r13
0x14001ec79  pop     r12
0x14001ec7b  pop     rdi
0x14001ec7c  pop     rsi
0x14001ec7d  pop     rbp
0x14001ec7e  retn
```
