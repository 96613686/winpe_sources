# WinNatFragmentIpv6Packet

- ea: `0x14001bf20`
- end: `0x14001c208`
- name: `WinNatFragmentIpv6Packet`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001c210`

## callees

- `0x14000caa0`
- `0x1400121c8`
- `0x14001bf20`

## import_xrefs

- `NETIO!RtlCopyMdlToMdl` at `0x14001c145`
- `NETIO!RtlCopyMdlToMdl` at `0x14001c145`
- `NDIS!NdisGetDataBuffer` at `0x14001bf66`
- `NDIS!NdisGetDataBuffer` at `0x14001c041`
- `NDIS!NdisGetDataBuffer` at `0x14001c0bb`
- `NDIS!NdisGetDataBuffer` at `0x14001bf66`
- `NDIS!NdisGetDataBuffer` at `0x14001c041`
- `NDIS!NdisGetDataBuffer` at `0x14001c0bb`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c010`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c17e`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c1d1`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c010`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c17e`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c1d1`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001bfad`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c06b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c0e5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c15e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001bfad`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c06b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c0e5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c15e`

## pseudocode

```c
__int64 __fastcall WinNatFragmentIpv6Packet(__int64 a1, __int64 a2, __int64 *a3, int a4)
{
  unsigned __int8 *DataBuffer; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int8 *v11; // rbp
  unsigned __int64 v13; // rax
  __int64 v14; // rax
  ULONG v15; // r12d
  unsigned int v16; // esi
  unsigned __int16 v17; // r15
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  _OWORD *v25; // rdi
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  _DWORD *v30; // rdi
  __int64 v31; // r8
  __int64 v32; // r9
  __int16 v33; // ax
  __int16 v34; // ax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v40; // [rsp+78h] [rbp+10h] BYREF
  int v41; // [rsp+88h] [rbp+20h]

  v41 = a4;
  v40 = 0;
  DataBuffer = (unsigned __int8 *)NdisGetDataBuffer(*(PNET_BUFFER *)(a2 + 8), 0x28u, 0, 1u, 0);
  v11 = DataBuffer;
  if ( !DataBuffer )
    return 3221225473LL;
  v13 = DataBuffer[6];
  if ( (unsigned __int8)v13 > 0x3Au || (v8 = 0x400000000020040LL, !_bittest64(&v8, v13)) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v7, v9, v10);
  NdisAdvanceNetBufferDataStart(*(PNET_BUFFER *)(a2 + 8), 0x28u, 0, 0);
  v14 = *(_QWORD *)(a2 + 8);
  v15 = 40;
  v41 = 0;
  v16 = *(_DWORD *)(v14 + 24);
  if ( v16 )
  {
    while ( 1 )
    {
      v17 = 1232;
      if ( v16 <= 0x4D0 )
        v17 = v16;
      v18 = WinNatCloneNblForTranslation(0, (unsigned int)v17 + 48);
      *a3 = v18;
      if ( !v18 )
        return 3221225626LL;
      if ( NdisRetreatNetBufferDataStart(*(PNET_BUFFER *)(v18 + 8), v17 + 48, 0, 0) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v19, v21, v22);
      v25 = NdisGetDataBuffer(*(PNET_BUFFER *)(*a3 + 8), 0x28u, 0, 1u, 0);
      if ( !v25 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v24, v23, v26, v27);
      NdisAdvanceNetBufferDataStart(*(PNET_BUFFER *)(*a3 + 8), 0x28u, 0, 0);
      *v25 = *(_OWORD *)v11;
      v25[1] = *((_OWORD *)v11 + 1);
      *((_QWORD *)v25 + 4) = *((_QWORD *)v11 + 4);
      *((_BYTE *)v25 + 6) = 44;
      *((_WORD *)v25 + 2) = __ROR2__(v17 + 8, 8);
      v30 = NdisGetDataBuffer(*(PNET_BUFFER *)(*a3 + 8), 8u, 0, 1u, 0);
      if ( !v30 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v29, v28, v31, v32);
      NdisAdvanceNetBufferDataStart(*(PNET_BUFFER *)(*a3 + 8), 8u, 0, 0);
      v30[1] = *(_DWORD *)(a1 + 220);
      *(_BYTE *)v30 = v11[6];
      v33 = v41;
      *((_BYTE *)v30 + 1) = 0;
      *((_WORD *)v30 + 1) = __ROR2__(v33, 8);
      RtlCopyMdlToMdl(
        *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL),
        *(unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL),
        *(_QWORD *)(*(_QWORD *)(*a3 + 8) + 8LL),
        *(unsigned int *)(*(_QWORD *)(*a3 + 8) + 16LL),
        v17,
        &v40);
      NdisAdvanceNetBufferDataStart(*(PNET_BUFFER *)(a2 + 8), v17, 0, 0);
      v15 += v17;
      NdisRetreatNetBufferDataStart(*(PNET_BUFFER *)(*a3 + 8), 0x30u, 0, 0);
      v16 -= v17;
      v34 = *((_WORD *)v30 + 1);
      v41 += v17;
      *((_WORD *)v30 + 1) = v34 & 0xFEFF | (v16 != 0 ? 0x100 : 0);
      a3 = (__int64 *)*a3;
      if ( !v16 )
        goto LABEL_17;
    }
  }
  else
  {
LABEL_17:
    if ( NdisRetreatNetBufferDataStart(*(PNET_BUFFER *)(a2 + 8), v15, 0, 0) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v36, v35, v37, v38);
    return 0;
  }
}

```

## disassembly

```asm
0x14001bf20  mov     rax, rsp
0x14001bf23  mov     [rax+18h], rbx
0x14001bf27  mov     [rax+20h], r9d
0x14001bf2b  mov     [rax+8], rcx
0x14001bf2f  push    rbp
0x14001bf30  push    rsi
0x14001bf31  push    rdi
0x14001bf32  push    r12
0x14001bf34  push    r13
0x14001bf36  push    r14
0x14001bf38  push    r15
0x14001bf3a  sub     rsp, 30h
0x14001bf3e  mov     rbx, rdx
0x14001bf41  mov     qword ptr [rax+10h], 0
0x14001bf49  mov     r9d, 1; AlignMultiple
0x14001bf4f  mov     dword ptr [rax-48h], 0
0x14001bf56  mov     r14, r8
0x14001bf59  xor     r8d, r8d; Storage
0x14001bf5c  mov     rcx, [rbx+8]; NetBuffer
0x14001bf60  lea     edi, [r9+27h]
0x14001bf64  mov     edx, edi; BytesNeeded
0x14001bf66  call    cs:__imp_NdisGetDataBuffer
0x14001bf6d  nop     dword ptr [rax+rax+00h]
0x14001bf72  mov     rbp, rax
0x14001bf75  test    rax, rax
0x14001bf78  jnz     short loc_14001BF84
0x14001bf7a  mov     eax, 0C0000001h
0x14001bf7f  jmp     loc_14001C1E8
0x14001bf84  movzx   eax, byte ptr [rax+6]
0x14001bf88  cmp     al, 3Ah ; ':'
0x14001bf8a  ja      short loc_14001BF9C
0x14001bf8c  mov     rcx, 400000000020040h
0x14001bf96  bt      rcx, rax
0x14001bf9a  jb      short loc_14001BFA1
0x14001bf9c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001bfa1  mov     rcx, [rbx+8]; NetBuffer
0x14001bfa5  xor     r9d, r9d; FreeMdlHandler
0x14001bfa8  xor     r8d, r8d; FreeMdl
0x14001bfab  mov     edx, edi; DataOffsetDelta
0x14001bfad  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001bfb4  nop     dword ptr [rax+rax+00h]
0x14001bfb9  mov     rax, [rbx+8]
0x14001bfbd  mov     r12d, edi
0x14001bfc0  mov     [rsp+68h+arg_18], 0
0x14001bfcb  mov     esi, [rax+18h]
0x14001bfce  test    esi, esi
0x14001bfd0  jz      loc_14001C1C4
0x14001bfd6  mov     eax, 4D0h
0x14001bfdb  movzx   r15d, ax
0x14001bfdf  cmp     esi, eax
0x14001bfe1  ja      short loc_14001BFE7
0x14001bfe3  movzx   r15d, si
0x14001bfe7  movzx   r13d, r15w
0x14001bfeb  xor     ecx, ecx; originalNetBufferList
0x14001bfed  lea     edx, [r13+30h]; DataOffsetDelta
0x14001bff1  call    WinNatCloneNblForTranslation
0x14001bff6  mov     [r14], rax
0x14001bff9  test    rax, rax
0x14001bffc  jz      loc_14001C201
0x14001c002  mov     rcx, [rax+8]; NetBuffer
0x14001c006  lea     edx, [r13+30h]; DataOffsetDelta
0x14001c00a  xor     r9d, r9d; AllocateMdlHandler
0x14001c00d  xor     r8d, r8d; DataBackFill
0x14001c010  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001c017  nop     dword ptr [rax+rax+00h]
0x14001c01c  test    eax, eax
0x14001c01e  jns     short loc_14001C025
0x14001c020  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c025  mov     rcx, [r14]
0x14001c028  mov     r9d, 1; AlignMultiple
0x14001c02e  xor     r8d, r8d; Storage
0x14001c031  mov     [rsp+68h+AlignOffset], 0; AlignOffset
0x14001c039  mov     rcx, [rcx+8]; NetBuffer
0x14001c03d  lea     edx, [r9+27h]; BytesNeeded
0x14001c041  call    cs:__imp_NdisGetDataBuffer
0x14001c048  nop     dword ptr [rax+rax+00h]
0x14001c04d  mov     rdi, rax
0x14001c050  test    rax, rax
0x14001c053  jnz     short loc_14001C05A
0x14001c055  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c05a  mov     rcx, [r14]
0x14001c05d  xor     r9d, r9d; FreeMdlHandler
0x14001c060  xor     r8d, r8d; FreeMdl
0x14001c063  mov     rcx, [rcx+8]; NetBuffer
0x14001c067  lea     edx, [r9+28h]; DataOffsetDelta
0x14001c06b  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001c072  nop     dword ptr [rax+rax+00h]
0x14001c077  movups  xmm0, xmmword ptr [rbp+0]
0x14001c07b  mov     edx, 8; BytesNeeded
0x14001c080  mov     [rsp+68h+AlignOffset], 0; AlignOffset
0x14001c088  xor     r8d, r8d; Storage
0x14001c08b  movups  xmmword ptr [rdi], xmm0
0x14001c08e  movups  xmm1, xmmword ptr [rbp+10h]
0x14001c092  lea     eax, [rdx+r15]
0x14001c096  ror     ax, 8
0x14001c09a  lea     r9d, [rdx-7]; AlignMultiple
0x14001c09e  movups  xmmword ptr [rdi+10h], xmm1
0x14001c0a2  movsd   xmm0, qword ptr [rbp+20h]
0x14001c0a7  movsd   qword ptr [rdi+20h], xmm0
0x14001c0ac  mov     byte ptr [rdi+6], 2Ch ; ','
0x14001c0b0  mov     [rdi+4], ax
0x14001c0b4  mov     rcx, [r14]
0x14001c0b7  mov     rcx, [rcx+8]; NetBuffer
0x14001c0bb  call    cs:__imp_NdisGetDataBuffer
0x14001c0c2  nop     dword ptr [rax+rax+00h]
0x14001c0c7  mov     rdi, rax
0x14001c0ca  test    rax, rax
0x14001c0cd  jnz     short loc_14001C0D4
0x14001c0cf  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c0d4  mov     rcx, [r14]
0x14001c0d7  xor     r9d, r9d; FreeMdlHandler
0x14001c0da  xor     r8d, r8d; FreeMdl
0x14001c0dd  mov     rcx, [rcx+8]; NetBuffer
0x14001c0e1  lea     edx, [r9+8]; DataOffsetDelta
0x14001c0e5  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001c0ec  nop     dword ptr [rax+rax+00h]
0x14001c0f1  mov     rax, [rsp+68h+arg_0]
0x14001c0f6  lea     r10, [rsp+68h+arg_8]
0x14001c0fb  mov     [rsp+68h+var_40], r10
0x14001c100  mov     ecx, [rax+0DCh]
0x14001c106  mov     [rdi+4], ecx
0x14001c109  mov     al, [rbp+6]
0x14001c10c  mov     [rdi], al
0x14001c10e  movzx   eax, word ptr [rsp+68h+arg_18]
0x14001c116  mov     byte ptr [rdi+1], 0
0x14001c11a  ror     ax, 8
0x14001c11e  mov     [rdi+2], ax
0x14001c122  mov     rax, [r14]
0x14001c125  mov     rcx, [rbx+8]
0x14001c129  mov     r8, [rax+8]
0x14001c12d  mov     edx, [rcx+10h]
0x14001c130  mov     rcx, [rcx+8]
0x14001c134  movzx   eax, r15w
0x14001c138  mov     r9d, [r8+10h]
0x14001c13c  mov     r8, [r8+8]
0x14001c140  mov     qword ptr [rsp+68h+AlignOffset], rax
0x14001c145  call    cs:__imp_RtlCopyMdlToMdl
0x14001c14c  nop     dword ptr [rax+rax+00h]
0x14001c151  mov     rcx, [rbx+8]; NetBuffer
0x14001c155  xor     r9d, r9d; FreeMdlHandler
0x14001c158  xor     r8d, r8d; FreeMdl
0x14001c15b  mov     edx, r13d; DataOffsetDelta
0x14001c15e  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001c165  nop     dword ptr [rax+rax+00h]
0x14001c16a  mov     rcx, [r14]
0x14001c16d  xor     r9d, r9d; AllocateMdlHandler
0x14001c170  xor     r8d, r8d; DataBackFill
0x14001c173  add     r12d, r13d
0x14001c176  mov     rcx, [rcx+8]; NetBuffer
0x14001c17a  lea     edx, [r9+30h]; DataOffsetDelta
0x14001c17e  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001c185  nop     dword ptr [rax+rax+00h]
0x14001c18a  sub     esi, r13d
0x14001c18d  mov     edx, 0FEFFh
0x14001c192  mov     eax, esi
0x14001c194  neg     eax
0x14001c196  movzx   eax, word ptr [rdi+2]
0x14001c19a  sbb     cx, cx
0x14001c19d  add     [rsp+68h+arg_18], r13d
0x14001c1a5  and     ax, dx
0x14001c1a8  and     cx, 100h
0x14001c1ad  or      cx, ax
0x14001c1b0  mov     eax, 4D0h
0x14001c1b5  mov     [rdi+2], cx
0x14001c1b9  mov     r14, [r14]
0x14001c1bc  test    esi, esi
0x14001c1be  jnz     loc_14001BFDB
0x14001c1c4  mov     rcx, [rbx+8]; NetBuffer
0x14001c1c8  xor     r9d, r9d; AllocateMdlHandler
0x14001c1cb  xor     r8d, r8d; DataBackFill
0x14001c1ce  mov     edx, r12d; DataOffsetDelta
0x14001c1d1  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001c1d8  nop     dword ptr [rax+rax+00h]
0x14001c1dd  test    eax, eax
0x14001c1df  jns     short loc_14001C1E6
0x14001c1e1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c1e6  xor     eax, eax
0x14001c1e8  mov     rbx, [rsp+68h+arg_10]
0x14001c1f0  add     rsp, 30h
0x14001c1f4  pop     r15
0x14001c1f6  pop     r14
0x14001c1f8  pop     r13
0x14001c1fa  pop     r12
0x14001c1fc  pop     rdi
0x14001c1fd  pop     rsi
0x14001c1fe  pop     rbp
0x14001c1ff  retn
0x14001c201  mov     eax, 0C000009Ah
0x14001c206  jmp     short loc_14001C1E8
```
