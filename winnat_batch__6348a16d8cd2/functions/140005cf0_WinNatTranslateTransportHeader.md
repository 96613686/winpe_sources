# WinNatTranslateTransportHeader

- ea: `0x140005cf0`
- end: `0x140005fc0`
- name: `WinNatTranslateTransportHeader`
- size: `720`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140006c80`
- `0x14001cef8`
- `0x14001d310`

## callees

- `0x140005cf0`
- `0x140005fc8`
- `0x1400093b8`
- `0x14000caa0`
- `0x14001d20c`

## import_xrefs

- `NETIO!RtlCopyBufferToMdl` at `0x140005ef8`
- `NETIO!RtlCopyBufferToMdl` at `0x140005ef8`
- `NDIS!NdisGetDataBuffer` at `0x140005d5f`
- `NDIS!NdisGetDataBuffer` at `0x140005d5f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140005de6`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140005eb9`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140005de6`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140005eb9`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140005d3a`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140005d3a`

## pseudocode

```c
__int64 __fastcall WinNatTranslateTransportHeader(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 a4,
        char a5,
        char a6,
        char a7)
{
  struct _NET_BUFFER *v9; // rcx
  NDIS_STATUS v12; // r14d
  _WORD *DataBuffer; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rsi
  __int64 v19; // rcx
  int v20; // edx
  __int16 v21; // cx
  unsigned int v22; // edx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  unsigned __int16 *v38; // r8
  unsigned __int16 *v39; // rcx
  int v40; // r9d
  __int16 v41; // r10
  _QWORD v42[11]; // [rsp+50h] [rbp-58h] BYREF

  v42[0] = 0;
  v9 = *(struct _NET_BUFFER **)(a2 + 8);
  if ( a7 )
  {
    v12 = 0;
    NdisAdvanceNetBufferDataStart(v9, *(_DWORD *)(a3 + 140), 0, 0);
  }
  else
  {
    v12 = NdisRetreatNetBufferDataStart(v9, *(unsigned __int8 *)(a3 + 148), 0, 0);
    if ( v12 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v27, v26, v28, v29);
      return (unsigned int)v12;
    }
    RtlCopyBufferToMdl(
      *(_QWORD *)(a3 + 8),
      *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL),
      *(unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL),
      *(unsigned __int8 *)(a3 + 148),
      v42);
    if ( v42[0] != *(unsigned __int8 *)(a3 + 148) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v31, v30, v32, v33);
  }
  DataBuffer = NdisGetDataBuffer(*(PNET_BUFFER *)(a2 + 8), *(unsigned __int8 *)(a3 + 148), 0, 1u, 0);
  v18 = (__int64)DataBuffer;
  if ( DataBuffer )
  {
    v19 = *(unsigned __int8 *)(a3 + 16);
    switch ( (_DWORD)v19 )
    {
      case 6:
        if ( a4 )
        {
          v20 = *(unsigned __int16 *)(a1 + 252);
          v21 = *(_WORD *)(*(_QWORD *)(a1 + 104) + 2LL);
          if ( a6 )
            goto LABEL_7;
        }
        else
        {
          v20 = *(unsigned __int16 *)(a1 + 254);
          v21 = *(_WORD *)(*(_QWORD *)(a1 + 88) + 2LL);
          if ( !a6 )
          {
LABEL_7:
            DataBuffer[1] = v21;
            goto LABEL_8;
          }
        }
        *DataBuffer = v21;
LABEL_8:
        if ( a5 )
        {
          v22 = (((unsigned int)(unsigned __int16)DataBuffer[8] + v20) >> 16) + (unsigned __int16)(DataBuffer[8] + v20);
          DataBuffer[8] = v22 + HIWORD(v22);
        }
        break;
      case 1:
        goto LABEL_40;
      case 0x11:
        v24 = 252;
        if ( !a4 )
          v24 = 254;
        v25 = 104;
        if ( !a4 )
          v25 = 88;
        WinNatTranslateUdpHeader(
          *(unsigned __int16 *)(*(_QWORD *)(v25 + a1) + 2LL),
          *(unsigned __int16 *)(v24 + a1),
          v18,
          a4,
          a5,
          a6);
        break;
      case 0x3A:
LABEL_40:
        if ( a6 && (unsigned __int8)WinNatIsIcmpErrorMessage(v19, *(unsigned __int8 *)DataBuffer, v16) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v35, v34, v36, v37);
        if ( a4 )
        {
          v38 = *(unsigned __int16 **)(a1 + 88);
          v39 = v38;
          v40 = *(_QWORD *)(a1 + 96) + 4;
          v41 = *(_WORD *)(*(_QWORD *)(a1 + 104) + 2LL);
        }
        else
        {
          v39 = *(unsigned __int16 **)(a1 + 88);
          v38 = *(unsigned __int16 **)(a1 + 96);
          v41 = v39[1];
          v40 = (_DWORD)v39 + 4;
        }
        if ( !(unsigned __int8)WinNatTranslateIcmpHeader(
                                 *v39,
                                 **(unsigned __int16 **)(a1 + 104),
                                 (int)v38 + 4,
                                 v40,
                                 v41,
                                 *(_BYTE *)(a3 + 16),
                                 v18,
                                 a4,
                                 a5,
                                 *(_DWORD *)(*(_QWORD *)(a2 + 8) + 24LL)) )
          v12 = -1073741285;
        break;
      default:
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v19, (unsigned int)(v19 - 17), v16, v17);
        break;
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v14, v16, v17);
    v12 = -1073741823;
  }
  if ( a7 )
    NdisRetreatNetBufferDataStart(*(PNET_BUFFER *)(a2 + 8), *(_DWORD *)(a3 + 140), 0, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140005cf0  push    rbx
0x140005cf2  push    rbp
0x140005cf3  push    rsi
0x140005cf4  push    rdi
0x140005cf5  push    r12
0x140005cf7  push    r13
0x140005cf9  push    r14
0x140005cfb  push    r15
0x140005cfd  sub     rsp, 68h
0x140005d01  movzx   ebp, [rsp+0A8h+arg_30]
0x140005d09  xor     r13d, r13d
0x140005d0c  movzx   r12d, r9b
0x140005d10  mov     [rsp+0A8h+var_58], r13
0x140005d15  xor     r9d, r9d; AllocateMdlHandler
0x140005d18  mov     r15, rcx
0x140005d1b  mov     rcx, [rdx+8]; NetBuffer
0x140005d1f  mov     rbx, r8
0x140005d22  mov     rdi, rdx
0x140005d25  test    bpl, bpl
0x140005d28  jz      loc_140005EAE
0x140005d2e  mov     edx, [rbx+8Ch]; DataOffsetDelta
0x140005d34  xor     r8d, r8d; FreeMdl
0x140005d37  mov     r14d, r13d
0x140005d3a  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140005d41  nop     dword ptr [rax+rax+00h]
0x140005d46  movzx   edx, byte ptr [rbx+94h]; BytesNeeded
0x140005d4d  mov     r9d, 1; AlignMultiple
0x140005d53  mov     rcx, [rdi+8]; NetBuffer
0x140005d57  xor     r8d, r8d; Storage
0x140005d5a  mov     [rsp+0A8h+AlignOffset], r13d; AlignOffset
0x140005d5f  call    cs:__imp_NdisGetDataBuffer
0x140005d66  nop     dword ptr [rax+rax+00h]
0x140005d6b  mov     rsi, rax
0x140005d6e  test    rax, rax
0x140005d71  jz      loc_140005E0C
0x140005d77  movzx   ecx, byte ptr [rbx+10h]
0x140005d7b  cmp     ecx, 6
0x140005d7e  jnz     loc_140005E38
0x140005d84  test    r12b, r12b
0x140005d87  jnz     loc_140005E19
0x140005d8d  mov     rax, [r15+58h]
0x140005d91  movzx   edx, word ptr [r15+0FEh]
0x140005d99  movzx   ecx, word ptr [rax+2]
0x140005d9d  cmp     [rsp+0A8h+arg_28], r13b
0x140005da5  jnz     short loc_140005E07
0x140005da7  mov     [rsi+2], cx
0x140005dab  cmp     [rsp+0A8h+arg_20], r13b
0x140005db3  jz      short loc_140005DD1
0x140005db5  movzx   ecx, word ptr [rsi+10h]
0x140005db9  add     edx, ecx
0x140005dbb  mov     ecx, edx
0x140005dbd  movzx   edx, dx
0x140005dc0  shr     ecx, 10h
0x140005dc3  add     edx, ecx
0x140005dc5  mov     eax, edx
0x140005dc7  shr     eax, 10h
0x140005dca  add     ax, dx
0x140005dcd  mov     [rsi+10h], ax
0x140005dd1  test    bpl, bpl
0x140005dd4  jz      short loc_140005DF2
0x140005dd6  mov     edx, [rbx+8Ch]; DataOffsetDelta
0x140005ddc  xor     r9d, r9d; AllocateMdlHandler
0x140005ddf  mov     rcx, [rdi+8]; NetBuffer
0x140005de3  xor     r8d, r8d; DataBackFill
0x140005de6  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140005ded  nop     dword ptr [rax+rax+00h]
0x140005df2  mov     eax, r14d
0x140005df5  add     rsp, 68h
0x140005df9  pop     r15
0x140005dfb  pop     r14
0x140005dfd  pop     r13
0x140005dff  pop     r12
0x140005e01  pop     rdi
0x140005e02  pop     rsi
0x140005e03  pop     rbp
0x140005e04  pop     rbx
0x140005e05  retn
0x140005e07  mov     [rsi], cx
0x140005e0a  jmp     short loc_140005DAB
0x140005e0c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140005e11  mov     r14d, 0C0000001h
0x140005e17  jmp     short loc_140005DD1
0x140005e19  mov     rax, [r15+68h]
0x140005e1d  movzx   edx, word ptr [r15+0FCh]
0x140005e25  movzx   ecx, word ptr [rax+2]
0x140005e29  cmp     [rsp+0A8h+arg_28], r13b
0x140005e31  jz      short loc_140005E07
0x140005e33  jmp     loc_140005DA7
0x140005e38  mov     edx, ecx
0x140005e3a  sub     edx, 1
0x140005e3d  jz      loc_140005F20
0x140005e43  sub     edx, 10h
0x140005e46  jz      short loc_140005E5B
0x140005e48  cmp     edx, 29h ; ')'
0x140005e4b  jz      loc_140005F20
0x140005e51  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140005e56  jmp     loc_140005DD1
0x140005e5b  test    r12b, r12b
0x140005e5e  mov     eax, 0FEh
0x140005e63  mov     ecx, 58h ; 'X'
0x140005e68  mov     edx, 0FCh
0x140005e6d  cmovz   edx, eax
0x140005e70  movzx   r9d, r12b
0x140005e74  mov     eax, 68h ; 'h'
0x140005e79  mov     r8, rsi
0x140005e7c  cmovz   eax, ecx
0x140005e7f  movzx   edx, word ptr [rdx+r15]
0x140005e84  mov     rcx, [rax+r15]
0x140005e88  movzx   eax, [rsp+0A8h+arg_28]
0x140005e90  mov     [rsp+0A8h+var_80], al
0x140005e94  movzx   eax, [rsp+0A8h+arg_20]
0x140005e9c  movzx   ecx, word ptr [rcx+2]
0x140005ea0  mov     byte ptr [rsp+0A8h+AlignOffset], al
0x140005ea4  call    WinNatTranslateUdpHeader
0x140005ea9  jmp     loc_140005DD1
0x140005eae  movzx   edx, byte ptr [r8+94h]; DataOffsetDelta
0x140005eb6  xor     r8d, r8d; DataBackFill
0x140005eb9  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140005ec0  nop     dword ptr [rax+rax+00h]
0x140005ec5  mov     r14d, eax
0x140005ec8  test    eax, eax
0x140005eca  jns     short loc_140005ED6
0x140005ecc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140005ed1  jmp     loc_140005DF2
0x140005ed6  mov     rdx, [rdi+8]
0x140005eda  lea     rax, [rsp+0A8h+var_58]
0x140005edf  movzx   r9d, byte ptr [rbx+94h]
0x140005ee7  mov     rcx, [rbx+8]
0x140005eeb  mov     qword ptr [rsp+0A8h+AlignOffset], rax
0x140005ef0  mov     r8d, [rdx+10h]
0x140005ef4  mov     rdx, [rdx+8]
0x140005ef8  call    cs:__imp_RtlCopyBufferToMdl
0x140005eff  nop     dword ptr [rax+rax+00h]
0x140005f04  movzx   eax, byte ptr [rbx+94h]
0x140005f0b  cmp     [rsp+0A8h+var_58], rax
0x140005f10  jz      loc_140005D46
0x140005f16  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140005f1b  jmp     loc_140005D46
0x140005f20  cmp     [rsp+0A8h+arg_28], r13b
0x140005f28  jz      short loc_140005F3B
0x140005f2a  movzx   edx, byte ptr [rax]
0x140005f2d  call    WinNatIsIcmpErrorMessage
0x140005f32  test    al, al
0x140005f34  jz      short loc_140005F3B
0x140005f36  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140005f3b  test    r12b, r12b
0x140005f3e  jz      short loc_140005F5A
0x140005f40  mov     rax, [r15+68h]
0x140005f44  mov     r8, [r15+58h]
0x140005f48  mov     r9, [r15+60h]
0x140005f4c  mov     rcx, r8
0x140005f4f  add     r9, 4
0x140005f53  movzx   r10d, word ptr [rax+2]
0x140005f58  jmp     short loc_140005F6B
0x140005f5a  mov     rcx, [r15+58h]
0x140005f5e  mov     r8, [r15+60h]
0x140005f62  movzx   r10d, word ptr [rcx+2]
0x140005f67  lea     r9, [rcx+4]
0x140005f6b  mov     rax, [rdi+8]
0x140005f6f  add     r8, 4
0x140005f73  mov     rdx, [r15+68h]
0x140005f77  movzx   ecx, word ptr [rcx]
0x140005f7a  mov     eax, [rax+18h]
0x140005f7d  movzx   edx, word ptr [rdx]
0x140005f80  mov     [rsp+0A8h+var_60], eax
0x140005f84  movzx   eax, [rsp+0A8h+arg_20]
0x140005f8c  mov     [rsp+0A8h+var_68], al
0x140005f90  movzx   eax, byte ptr [rbx+10h]
0x140005f94  mov     [rsp+0A8h+var_70], r12b
0x140005f99  mov     [rsp+0A8h+var_78], rsi
0x140005f9e  mov     [rsp+0A8h+var_80], al
0x140005fa2  mov     word ptr [rsp+0A8h+AlignOffset], r10w
0x140005fa8  call    WinNatTranslateIcmpHeader
0x140005fad  test    al, al
0x140005faf  jnz     loc_140005DD1
0x140005fb5  mov     r14d, 0C000021Bh
0x140005fbb  jmp     loc_140005DD1
```
