# WinNatStatelessTranslateTransportHeader

- ea: `0x14001ee24`
- end: `0x14001f1b8`
- name: `WinNatStatelessTranslateTransportHeader`
- size: `916`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int *, _QWORD *, PNET_BUFFER NetBuffer, char, char, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001e7d8`
- `0x14001ecb4`

## callees

- `0x140005fc8`
- `0x1400062f0`
- `0x1400093b8`
- `0x14000bb38`
- `0x14000caa0`
- `0x14001c070`
- `0x14001d6ec`
- `0x14001ee24`

## import_xrefs

- `NETIO!RtlCopyBufferToMdl` at `0x14001eeb4`
- `NETIO!RtlCopyBufferToMdl` at `0x14001eeb4`
- `NDIS!NdisGetDataBuffer` at `0x14001eeee`
- `NDIS!NdisGetDataBuffer` at `0x14001eeee`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001ee67`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001ee67`

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
  _QWORD *v20; // rdx
  __int64 v21; // rcx
  _WORD *DataBuffer; // rdi
  __int64 v23; // r8
  int v24; // r9d
  char v25; // r15
  unsigned __int16 v26; // r12
  char v27; // al
  __int64 v28; // r8
  unsigned __int16 v29; // si
  unsigned int v30; // ecx
  ULONG DataLength; // edx
  unsigned int v32; // ecx
  int v33; // r9d
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v39; // [rsp+A0h] [rbp+18h] BYREF

  v9 = NetBuffer;
  v11 = *(unsigned __int8 *)(a3 + 149);
  v14 = 0;
  v39 = 0;
  NdisAdvanceNetBufferDataStart(NetBuffer, v11, 0, 0);
  v15 = *(unsigned __int8 *)(a3 + 16);
  if ( (unsigned __int8)v15 > 0x3Au )
    return v14;
  v16 = 0x400000000020042LL;
  if ( !_bittest64(&v16, v15) )
    return v14;
  RtlCopyBufferToMdl(*(_QWORD *)(a3 + 8), v9->Link.Region, v9->CurrentMdlOffset, *(unsigned __int8 *)(a3 + 148), &v39);
  if ( *(unsigned __int8 *)(a3 + 148) != v39 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v18, v17, v19);
  DataBuffer = NdisGetDataBuffer(v9, *(unsigned __int8 *)(a3 + 148), 0, 1u, 0);
  if ( !DataBuffer )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, v20, v23);
    return (unsigned int)-1073741823;
  }
  v25 = a7;
  v26 = 0;
  v27 = *(_BYTE *)(a3 + 16);
  v28 = 2;
  if ( a7 )
  {
    if ( v27 == 17 || v27 == 6 )
    {
      LOBYTE(v24) = 16;
      v26 = WinNatFixupChecksum((int)a3 + 160, 16, (int)a3 + 188, v24, 0, a1, 4, a2, 4, 0);
    }
    v29 = *(_WORD *)(a3 + 154);
    goto LABEL_24;
  }
  if ( v27 == 6 )
  {
    v20 = a5;
    if ( (*a4 & 4) != 0 || *a5 )
    {
      v30 = *a4 & 0xFFFFFFFC | 2;
      *a4 = v30;
      *a4 = v30 & 0xFC00FFFF | (*(unsigned __int8 *)(a3 + 149) << 16);
      if ( *v20 )
        DataLength = 0;
      else
        DataLength = v9->DataLength;
      DataBuffer[8] = WinNatChecksumDatagram(0, DataLength, a1, a2, 16, *(unsigned __int8 *)(a3 + 16));
      goto LABEL_23;
    }
    goto LABEL_22;
  }
  if ( v27 != 17 || (*a4 & 8) == 0 )
  {
LABEL_22:
    LOBYTE(v20) = 4;
    v26 = WinNatFixupChecksum((int)a3 + 156, (_DWORD)v20, (int)a3 + 184, 4, 0, a1, 16, a2, 16, 0);
    goto LABEL_23;
  }
  v32 = *a4 & 0xFFFFFFFC | 2;
  *a4 = v32;
  *a4 = v32 & 0xFC00FFFF | (*(unsigned __int8 *)(a3 + 149) << 16);
  DataBuffer[3] = WinNatChecksumDatagram(0, v9->DataLength, a1, a2, 16, *(unsigned __int8 *)(a3 + 16));
LABEL_23:
  v29 = *(_WORD *)(a3 + 182);
LABEL_24:
  v33 = *(unsigned __int8 *)(a3 + 16);
  v34 = (unsigned int)(v33 - 1);
  if ( v33 == 1 )
    goto LABEL_41;
  if ( v33 == 6 )
  {
    LOBYTE(v33) = v25;
    WinNatTranslateTcpHeader(v29, v26, (_DWORD)DataBuffer, v33, a8, a9);
    return v14;
  }
  v34 = (unsigned int)(v33 - 17);
  if ( v33 == 17 )
  {
    LOBYTE(v33) = v25;
    WinNatTranslateUdpHeader(v29, v26, (_DWORD)DataBuffer, v33, a8, a9);
    return v14;
  }
  if ( v33 == 58 )
  {
LABEL_41:
    if ( a9 )
    {
      LOBYTE(v20) = *(_BYTE *)DataBuffer;
      LOBYTE(v34) = *(_BYTE *)(a3 + 16);
      if ( (unsigned __int8)WinNatIsIcmpErrorMessage(v34, v20, v28) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v34, v35, v36);
        LOBYTE(v33) = *(_BYTE *)(a3 + 16);
      }
    }
    if ( v25 )
    {
      LODWORD(a1) = a3 + 160;
      LODWORD(a2) = a3 + 188;
    }
    LOWORD(v34) = 23;
    if ( !(unsigned __int8)WinNatTranslateIcmpHeader(
                             v34,
                             2,
                             a1,
                             a2,
                             v29,
                             v33,
                             (__int64)DataBuffer,
                             v25,
                             a8,
                             v9->DataLength) )
      return (unsigned int)-1073741285;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v34, v20, v28);
  }
  return v14;
}

```

## disassembly

```asm
0x14001ee24  mov     rax, rsp
0x14001ee27  mov     [rax+10h], rbx
0x14001ee2b  mov     [rax+8], rcx
0x14001ee2f  push    rbp
0x14001ee30  push    rsi
0x14001ee31  push    rdi
0x14001ee32  push    r12
0x14001ee34  push    r13
0x14001ee36  push    r14
0x14001ee38  push    r15
0x14001ee3a  sub     rsp, 50h
0x14001ee3e  mov     rbp, [rsp+88h+NetBuffer]
0x14001ee46  mov     r13, rdx
0x14001ee49  movzx   edx, byte ptr [r8+95h]; DataOffsetDelta
0x14001ee51  mov     rsi, r9
0x14001ee54  mov     rbx, r8
0x14001ee57  xor     r14d, r14d
0x14001ee5a  xor     r8d, r8d; FreeMdl
0x14001ee5d  mov     [rax+18h], r14
0x14001ee61  mov     rcx, rbp; NetBuffer
0x14001ee64  xor     r9d, r9d; FreeMdlHandler
0x14001ee67  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001ee6e  nop     dword ptr [rax+rax+00h]
0x14001ee73  movzx   eax, byte ptr [rbx+10h]
0x14001ee77  cmp     al, 3Ah ; ':'
0x14001ee79  ja      loc_14001F19C
0x14001ee7f  mov     rcx, 400000000020042h
0x14001ee89  bt      rcx, rax
0x14001ee8d  jnb     loc_14001F19C
0x14001ee93  movzx   r9d, byte ptr [rbx+94h]
0x14001ee9b  lea     rax, [rsp+88h+arg_10]
0x14001eea3  mov     r8d, [rbp+10h]
0x14001eea7  mov     rdx, [rbp+8]
0x14001eeab  mov     rcx, [rbx+8]
0x14001eeaf  mov     qword ptr [rsp+88h+AlignOffset], rax
0x14001eeb4  call    cs:__imp_RtlCopyBufferToMdl
0x14001eebb  nop     dword ptr [rax+rax+00h]
0x14001eec0  movzx   eax, byte ptr [rbx+94h]
0x14001eec7  cmp     rax, [rsp+88h+arg_10]
0x14001eecf  jz      short loc_14001EED6
0x14001eed1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001eed6  movzx   edx, byte ptr [rbx+94h]; BytesNeeded
0x14001eedd  mov     r9d, 1; AlignMultiple
0x14001eee3  xor     r8d, r8d; Storage
0x14001eee6  mov     [rsp+88h+AlignOffset], r14d; AlignOffset
0x14001eeeb  mov     rcx, rbp; NetBuffer
0x14001eeee  call    cs:__imp_NdisGetDataBuffer
0x14001eef5  nop     dword ptr [rax+rax+00h]
0x14001eefa  mov     rdi, rax
0x14001eefd  test    rax, rax
0x14001ef00  jnz     short loc_14001EF12
0x14001ef02  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001ef07  mov     r14d, 0C0000001h
0x14001ef0d  jmp     loc_14001F19C
0x14001ef12  mov     r15b, [rsp+88h+arg_30]
0x14001ef1a  xor     r12d, r12d
0x14001ef1d  mov     al, [rbx+10h]
0x14001ef20  lea     r8d, [r12+2]
0x14001ef25  test    r15b, r15b
0x14001ef28  jz      short loc_14001EF85
0x14001ef2a  cmp     al, 11h
0x14001ef2c  jz      short loc_14001EF32
0x14001ef2e  cmp     al, 6
0x14001ef30  jnz     short loc_14001EF79
0x14001ef32  xor     eax, eax
0x14001ef34  lea     r8, [rbx+0BCh]
0x14001ef3b  mov     word ptr [rsp+88h+var_40], ax
0x14001ef40  lea     rcx, [rbx+0A0h]
0x14001ef47  mov     rax, [rsp+88h+arg_0]
0x14001ef4f  xor     edx, edx
0x14001ef51  mov     [rsp+88h+var_48], 4
0x14001ef56  mov     r9b, 10h
0x14001ef59  mov     [rsp+88h+var_50], r13
0x14001ef5e  mov     byte ptr [rsp+88h+var_58], 4
0x14001ef63  mov     [rsp+88h+var_60], rax
0x14001ef68  mov     word ptr [rsp+88h+AlignOffset], dx
0x14001ef6d  mov     dl, r9b
0x14001ef70  call    WinNatFixupChecksum
0x14001ef75  movzx   r12d, ax
0x14001ef79  movzx   esi, word ptr [rbx+9Ah]
0x14001ef80  jmp     loc_14001F096
0x14001ef85  cmp     al, 6
0x14001ef87  jnz     short loc_14001EFF4
0x14001ef89  mov     ecx, [rsi]
0x14001ef8b  mov     rdx, [rsp+88h+arg_20]
0x14001ef93  test    cl, 4
0x14001ef96  jnz     short loc_14001EFA1
0x14001ef98  cmp     [rdx], r12
0x14001ef9b  jz      loc_14001F046
0x14001efa1  and     ecx, 0FFFFFFFEh
0x14001efa4  or      ecx, r8d
0x14001efa7  mov     [rsi], ecx
0x14001efa9  and     ecx, 0FC00FFFFh
0x14001efaf  movzx   eax, byte ptr [rbx+95h]
0x14001efb6  shl     eax, 10h
0x14001efb9  or      eax, ecx
0x14001efbb  mov     [rsi], eax
0x14001efbd  cmp     [rdx], r12
0x14001efc0  jz      short loc_14001EFC6
0x14001efc2  xor     edx, edx
0x14001efc4  jmp     short loc_14001EFC9
0x14001efc6  mov     edx, [rbp+18h]
0x14001efc9  movzx   eax, byte ptr [rbx+10h]
0x14001efcd  mov     r9, r13
0x14001efd0  mov     r8, [rsp+88h+arg_0]
0x14001efd8  xor     ecx, ecx
0x14001efda  mov     dword ptr [rsp+88h+var_60], eax
0x14001efde  mov     [rsp+88h+AlignOffset], 10h
0x14001efe6  call    WinNatChecksumDatagram
0x14001efeb  mov     [rdi+10h], ax
0x14001efef  jmp     loc_14001F08F
0x14001eff4  cmp     al, 11h
0x14001eff6  jnz     short loc_14001F046
0x14001eff8  mov     ecx, [rsi]
0x14001effa  test    cl, 8
0x14001effd  jz      short loc_14001F046
0x14001efff  and     ecx, 0FFFFFFFEh
0x14001f002  mov     r9, r13
0x14001f005  or      ecx, r8d
0x14001f008  mov     r8, [rsp+88h+arg_0]
0x14001f010  mov     [rsi], ecx
0x14001f012  and     ecx, 0FC00FFFFh
0x14001f018  movzx   eax, byte ptr [rbx+95h]
0x14001f01f  shl     eax, 10h
0x14001f022  or      eax, ecx
0x14001f024  xor     ecx, ecx
0x14001f026  mov     [rsi], eax
0x14001f028  movzx   eax, byte ptr [rbx+10h]
0x14001f02c  mov     edx, [rbp+18h]
0x14001f02f  mov     dword ptr [rsp+88h+var_60], eax
0x14001f033  mov     [rsp+88h+AlignOffset], 10h
0x14001f03b  call    WinNatChecksumDatagram
0x14001f040  mov     [rdi+6], ax
0x14001f044  jmp     short loc_14001F08F
0x14001f046  xor     eax, eax
0x14001f048  lea     r8, [rbx+0B8h]
0x14001f04f  mov     word ptr [rsp+88h+var_40], ax
0x14001f054  lea     rcx, [rbx+9Ch]
0x14001f05b  mov     rax, [rsp+88h+arg_0]
0x14001f063  xor     r9d, r9d
0x14001f066  mov     [rsp+88h+var_48], 10h
0x14001f06b  mov     [rsp+88h+var_50], r13
0x14001f070  mov     byte ptr [rsp+88h+var_58], 10h
0x14001f075  mov     [rsp+88h+var_60], rax
0x14001f07a  mov     word ptr [rsp+88h+AlignOffset], r9w
0x14001f080  mov     r9b, 4
0x14001f083  mov     dl, r9b
0x14001f086  call    WinNatFixupChecksum
0x14001f08b  movzx   r12d, ax
0x14001f08f  movzx   esi, word ptr [rbx+0B6h]
0x14001f096  movzx   r9d, byte ptr [rbx+10h]
0x14001f09b  mov     ecx, r9d
0x14001f09e  sub     ecx, 1
0x14001f0a1  jz      short loc_14001F116
0x14001f0a3  sub     ecx, 5
0x14001f0a6  jz      short loc_14001F0E9
0x14001f0a8  sub     ecx, 0Bh
0x14001f0ab  jz      short loc_14001F0BC
0x14001f0ad  cmp     ecx, 29h ; ')'
0x14001f0b0  jz      short loc_14001F116
0x14001f0b2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001f0b7  jmp     loc_14001F19C
0x14001f0bc  mov     al, [rsp+88h+arg_40]
0x14001f0c3  mov     r9b, r15b
0x14001f0c6  mov     byte ptr [rsp+88h+var_60], al
0x14001f0ca  mov     r8, rdi
0x14001f0cd  mov     al, [rsp+88h+arg_38]
0x14001f0d4  movzx   edx, r12w
0x14001f0d8  movzx   ecx, si
0x14001f0db  mov     byte ptr [rsp+88h+AlignOffset], al
0x14001f0df  call    WinNatTranslateUdpHeader
0x14001f0e4  jmp     loc_14001F19C
0x14001f0e9  mov     al, [rsp+88h+arg_40]
0x14001f0f0  mov     r9b, r15b
0x14001f0f3  mov     byte ptr [rsp+88h+var_60], al
0x14001f0f7  mov     r8, rdi
0x14001f0fa  mov     al, [rsp+88h+arg_38]
0x14001f101  movzx   edx, r12w
0x14001f105  movzx   ecx, si
0x14001f108  mov     byte ptr [rsp+88h+AlignOffset], al
0x14001f10c  call    WinNatTranslateTcpHeader
0x14001f111  jmp     loc_14001F19C
0x14001f116  cmp     [rsp+88h+arg_40], r14b
0x14001f11e  jz      short loc_14001F137
0x14001f120  mov     dl, [rdi]
0x14001f122  mov     cl, r9b
0x14001f125  call    WinNatIsIcmpErrorMessage
0x14001f12a  test    al, al
0x14001f12c  jz      short loc_14001F137
0x14001f12e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001f133  mov     r9b, [rbx+10h]
0x14001f137  test    r15b, r15b
0x14001f13a  jz      short loc_14001F152
0x14001f13c  lea     rax, [rbx+0A0h]
0x14001f143  mov     [rsp+88h+arg_0], rax
0x14001f14b  lea     r13, [rbx+0BCh]
0x14001f152  mov     eax, [rbp+18h]
0x14001f155  mov     edx, 2
0x14001f15a  mov     r8, [rsp+88h+arg_0]
0x14001f162  mov     cx, 17h
0x14001f166  mov     [rsp+88h+var_40], eax
0x14001f16a  mov     al, [rsp+88h+arg_38]
0x14001f171  mov     [rsp+88h+var_48], al
0x14001f175  mov     byte ptr [rsp+88h+var_50], r15b
0x14001f17a  mov     [rsp+88h+var_58], rdi
0x14001f17f  mov     byte ptr [rsp+88h+var_60], r9b
0x14001f184  mov     r9, r13
0x14001f187  mov     word ptr [rsp+88h+AlignOffset], si
0x14001f18c  call    WinNatTranslateIcmpHeader
0x14001f191  test    al, al
0x14001f193  mov     ecx, 0C000021Bh
0x14001f198  cmovz   r14d, ecx
0x14001f19c  mov     rbx, [rsp+88h+arg_8]
0x14001f1a4  mov     eax, r14d
0x14001f1a7  add     rsp, 50h
0x14001f1ab  pop     r15
0x14001f1ad  pop     r14
0x14001f1af  pop     r13
0x14001f1b1  pop     r12
0x14001f1b3  pop     rdi
0x14001f1b4  pop     rsi
0x14001f1b5  pop     rbp
0x14001f1b6  retn
```
