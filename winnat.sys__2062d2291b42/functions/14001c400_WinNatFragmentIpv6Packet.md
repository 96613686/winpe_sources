# WinNatFragmentIpv6Packet

- ea: `0x14001c400`
- end: `0x14001c6e8`
- name: `WinNatFragmentIpv6Packet`
- size: `744`
- prototype: `__int64 __fastcall(__int64, __int64, NET_BUFFER_LIST **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001c6f0`

## callees

- `0x14000caa0`
- `0x140012b08`
- `0x14001c400`

## import_xrefs

- `NETIO!RtlCopyMdlToMdl` at `0x14001c625`
- `NETIO!RtlCopyMdlToMdl` at `0x14001c625`
- `NDIS!NdisGetDataBuffer` at `0x14001c446`
- `NDIS!NdisGetDataBuffer` at `0x14001c521`
- `NDIS!NdisGetDataBuffer` at `0x14001c59b`
- `NDIS!NdisGetDataBuffer` at `0x14001c446`
- `NDIS!NdisGetDataBuffer` at `0x14001c521`
- `NDIS!NdisGetDataBuffer` at `0x14001c59b`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c4f0`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c65e`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c6b1`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c4f0`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c65e`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001c6b1`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c48d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c54b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c5c5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c63e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c48d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c54b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c5c5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001c63e`

## pseudocode

```c
__int64 __fastcall WinNatFragmentIpv6Packet(__int64 a1, __int64 a2, NET_BUFFER_LIST **a3, int a4)
{
  unsigned __int8 *DataBuffer; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned __int8 *v10; // rbp
  unsigned __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  ULONG v15; // r12d
  unsigned int v16; // esi
  unsigned __int16 v17; // r15
  NET_BUFFER_LIST *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  _OWORD *v24; // rdi
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  _DWORD *v28; // rdi
  __int64 v29; // r8
  __int16 v30; // ax
  __int16 v31; // ax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v36; // [rsp+78h] [rbp+10h] BYREF
  int v37; // [rsp+88h] [rbp+20h]

  v37 = a4;
  v36 = 0;
  DataBuffer = (unsigned __int8 *)NdisGetDataBuffer(*(PNET_BUFFER *)(a2 + 8), 0x28u, 0, 1u, 0);
  v10 = DataBuffer;
  if ( !DataBuffer )
    return 3221225473LL;
  v12 = DataBuffer[6];
  if ( (unsigned __int8)v12 > 0x3Au || (v8 = 0x400000000020040LL, !_bittest64(&v8, v12)) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v7, v9);
  NdisAdvanceNetBufferDataStart(*(PNET_BUFFER *)(a2 + 8), 0x28u, 0, 0);
  v14 = *(_QWORD *)(a2 + 8);
  v15 = 40;
  v37 = 0;
  v16 = *(_DWORD *)(v14 + 24);
  if ( v16 )
  {
    while ( 1 )
    {
      v17 = 1232;
      if ( v16 <= 0x4D0 )
        v17 = v16;
      v18 = WinNatCloneNblForTranslation(0, (unsigned int)v17 + 48, v13);
      *a3 = v18;
      if ( !v18 )
        return 3221225626LL;
      if ( NdisRetreatNetBufferDataStart(v18->FirstNetBuffer, v17 + 48, 0, 0) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v20, v19, v21);
      v24 = NdisGetDataBuffer((*a3)->FirstNetBuffer, 0x28u, 0, 1u, 0);
      if ( !v24 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v23, v22, v25);
      NdisAdvanceNetBufferDataStart((*a3)->FirstNetBuffer, 0x28u, 0, 0);
      *v24 = *(_OWORD *)v10;
      v24[1] = *((_OWORD *)v10 + 1);
      *((_QWORD *)v24 + 4) = *((_QWORD *)v10 + 4);
      *((_BYTE *)v24 + 6) = 44;
      *((_WORD *)v24 + 2) = __ROR2__(v17 + 8, 8);
      v28 = NdisGetDataBuffer((*a3)->FirstNetBuffer, 8u, 0, 1u, 0);
      if ( !v28 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v27, v26, v29);
      NdisAdvanceNetBufferDataStart((*a3)->FirstNetBuffer, 8u, 0, 0);
      v28[1] = *(_DWORD *)(a1 + 220);
      *(_BYTE *)v28 = v10[6];
      v30 = v37;
      *((_BYTE *)v28 + 1) = 0;
      *((_WORD *)v28 + 1) = __ROR2__(v30, 8);
      RtlCopyMdlToMdl(
        *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL),
        *(unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL),
        *(_QWORD *)((*a3)->Link.Region + 8),
        *(unsigned int *)((*a3)->Link.Region + 16),
        v17,
        &v36);
      NdisAdvanceNetBufferDataStart(*(PNET_BUFFER *)(a2 + 8), v17, 0, 0);
      v15 += v17;
      NdisRetreatNetBufferDataStart((*a3)->FirstNetBuffer, 0x30u, 0, 0);
      v16 -= v17;
      v31 = *((_WORD *)v28 + 1);
      v37 += v17;
      *((_WORD *)v28 + 1) = v31 & 0xFEFF | (v16 != 0 ? 0x100 : 0);
      a3 = (NET_BUFFER_LIST **)*a3;
      if ( !v16 )
        goto LABEL_17;
    }
  }
  else
  {
LABEL_17:
    if ( NdisRetreatNetBufferDataStart(*(PNET_BUFFER *)(a2 + 8), v15, 0, 0) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v33, v32, v34);
    return 0;
  }
}

```

## disassembly

```asm
0x14001c400  mov     rax, rsp
0x14001c403  mov     [rax+18h], rbx
0x14001c407  mov     [rax+20h], r9d
0x14001c40b  mov     [rax+8], rcx
0x14001c40f  push    rbp
0x14001c410  push    rsi
0x14001c411  push    rdi
0x14001c412  push    r12
0x14001c414  push    r13
0x14001c416  push    r14
0x14001c418  push    r15
0x14001c41a  sub     rsp, 30h
0x14001c41e  mov     rbx, rdx
0x14001c421  mov     qword ptr [rax+10h], 0
0x14001c429  mov     r9d, 1; AlignMultiple
0x14001c42f  mov     dword ptr [rax-48h], 0
0x14001c436  mov     r14, r8
0x14001c439  xor     r8d, r8d; Storage
0x14001c43c  mov     rcx, [rbx+8]; NetBuffer
0x14001c440  lea     edi, [r9+27h]
0x14001c444  mov     edx, edi; BytesNeeded
0x14001c446  call    cs:__imp_NdisGetDataBuffer
0x14001c44d  nop     dword ptr [rax+rax+00h]
0x14001c452  mov     rbp, rax
0x14001c455  test    rax, rax
0x14001c458  jnz     short loc_14001C464
0x14001c45a  mov     eax, 0C0000001h
0x14001c45f  jmp     loc_14001C6C8
0x14001c464  movzx   eax, byte ptr [rax+6]
0x14001c468  cmp     al, 3Ah ; ':'
0x14001c46a  ja      short loc_14001C47C
0x14001c46c  mov     rcx, 400000000020040h
0x14001c476  bt      rcx, rax
0x14001c47a  jb      short loc_14001C481
0x14001c47c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c481  mov     rcx, [rbx+8]; NetBuffer
0x14001c485  xor     r9d, r9d; FreeMdlHandler
0x14001c488  xor     r8d, r8d; FreeMdl
0x14001c48b  mov     edx, edi; DataOffsetDelta
0x14001c48d  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001c494  nop     dword ptr [rax+rax+00h]
0x14001c499  mov     rax, [rbx+8]
0x14001c49d  mov     r12d, edi
0x14001c4a0  mov     [rsp+68h+arg_18], 0
0x14001c4ab  mov     esi, [rax+18h]
0x14001c4ae  test    esi, esi
0x14001c4b0  jz      loc_14001C6A4
0x14001c4b6  mov     eax, 4D0h
0x14001c4bb  movzx   r15d, ax
0x14001c4bf  cmp     esi, eax
0x14001c4c1  ja      short loc_14001C4C7
0x14001c4c3  movzx   r15d, si
0x14001c4c7  movzx   r13d, r15w
0x14001c4cb  xor     ecx, ecx; originalNetBufferList
0x14001c4cd  lea     edx, [r13+30h]; DataOffsetDelta
0x14001c4d1  call    WinNatCloneNblForTranslation
0x14001c4d6  mov     [r14], rax
0x14001c4d9  test    rax, rax
0x14001c4dc  jz      loc_14001C6E1
0x14001c4e2  mov     rcx, [rax+8]; NetBuffer
0x14001c4e6  lea     edx, [r13+30h]; DataOffsetDelta
0x14001c4ea  xor     r9d, r9d; AllocateMdlHandler
0x14001c4ed  xor     r8d, r8d; DataBackFill
0x14001c4f0  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001c4f7  nop     dword ptr [rax+rax+00h]
0x14001c4fc  test    eax, eax
0x14001c4fe  jns     short loc_14001C505
0x14001c500  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c505  mov     rcx, [r14]
0x14001c508  mov     r9d, 1; AlignMultiple
0x14001c50e  xor     r8d, r8d; Storage
0x14001c511  mov     [rsp+68h+AlignOffset], 0; AlignOffset
0x14001c519  mov     rcx, [rcx+8]; NetBuffer
0x14001c51d  lea     edx, [r9+27h]; BytesNeeded
0x14001c521  call    cs:__imp_NdisGetDataBuffer
0x14001c528  nop     dword ptr [rax+rax+00h]
0x14001c52d  mov     rdi, rax
0x14001c530  test    rax, rax
0x14001c533  jnz     short loc_14001C53A
0x14001c535  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c53a  mov     rcx, [r14]
0x14001c53d  xor     r9d, r9d; FreeMdlHandler
0x14001c540  xor     r8d, r8d; FreeMdl
0x14001c543  mov     rcx, [rcx+8]; NetBuffer
0x14001c547  lea     edx, [r9+28h]; DataOffsetDelta
0x14001c54b  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001c552  nop     dword ptr [rax+rax+00h]
0x14001c557  movups  xmm0, xmmword ptr [rbp+0]
0x14001c55b  mov     edx, 8; BytesNeeded
0x14001c560  mov     [rsp+68h+AlignOffset], 0; AlignOffset
0x14001c568  xor     r8d, r8d; Storage
0x14001c56b  movups  xmmword ptr [rdi], xmm0
0x14001c56e  movups  xmm1, xmmword ptr [rbp+10h]
0x14001c572  lea     eax, [rdx+r15]
0x14001c576  ror     ax, 8
0x14001c57a  lea     r9d, [rdx-7]; AlignMultiple
0x14001c57e  movups  xmmword ptr [rdi+10h], xmm1
0x14001c582  movsd   xmm0, qword ptr [rbp+20h]
0x14001c587  movsd   qword ptr [rdi+20h], xmm0
0x14001c58c  mov     byte ptr [rdi+6], 2Ch ; ','
0x14001c590  mov     [rdi+4], ax
0x14001c594  mov     rcx, [r14]
0x14001c597  mov     rcx, [rcx+8]; NetBuffer
0x14001c59b  call    cs:__imp_NdisGetDataBuffer
0x14001c5a2  nop     dword ptr [rax+rax+00h]
0x14001c5a7  mov     rdi, rax
0x14001c5aa  test    rax, rax
0x14001c5ad  jnz     short loc_14001C5B4
0x14001c5af  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c5b4  mov     rcx, [r14]
0x14001c5b7  xor     r9d, r9d; FreeMdlHandler
0x14001c5ba  xor     r8d, r8d; FreeMdl
0x14001c5bd  mov     rcx, [rcx+8]; NetBuffer
0x14001c5c1  lea     edx, [r9+8]; DataOffsetDelta
0x14001c5c5  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001c5cc  nop     dword ptr [rax+rax+00h]
0x14001c5d1  mov     rax, [rsp+68h+arg_0]
0x14001c5d6  lea     r10, [rsp+68h+arg_8]
0x14001c5db  mov     [rsp+68h+var_40], r10
0x14001c5e0  mov     ecx, [rax+0DCh]
0x14001c5e6  mov     [rdi+4], ecx
0x14001c5e9  mov     al, [rbp+6]
0x14001c5ec  mov     [rdi], al
0x14001c5ee  movzx   eax, word ptr [rsp+68h+arg_18]
0x14001c5f6  mov     byte ptr [rdi+1], 0
0x14001c5fa  ror     ax, 8
0x14001c5fe  mov     [rdi+2], ax
0x14001c602  mov     rax, [r14]
0x14001c605  mov     rcx, [rbx+8]
0x14001c609  mov     r8, [rax+8]
0x14001c60d  mov     edx, [rcx+10h]
0x14001c610  mov     rcx, [rcx+8]
0x14001c614  movzx   eax, r15w
0x14001c618  mov     r9d, [r8+10h]
0x14001c61c  mov     r8, [r8+8]
0x14001c620  mov     qword ptr [rsp+68h+AlignOffset], rax
0x14001c625  call    cs:__imp_RtlCopyMdlToMdl
0x14001c62c  nop     dword ptr [rax+rax+00h]
0x14001c631  mov     rcx, [rbx+8]; NetBuffer
0x14001c635  xor     r9d, r9d; FreeMdlHandler
0x14001c638  xor     r8d, r8d; FreeMdl
0x14001c63b  mov     edx, r13d; DataOffsetDelta
0x14001c63e  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001c645  nop     dword ptr [rax+rax+00h]
0x14001c64a  mov     rcx, [r14]
0x14001c64d  xor     r9d, r9d; AllocateMdlHandler
0x14001c650  xor     r8d, r8d; DataBackFill
0x14001c653  add     r12d, r13d
0x14001c656  mov     rcx, [rcx+8]; NetBuffer
0x14001c65a  lea     edx, [r9+30h]; DataOffsetDelta
0x14001c65e  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001c665  nop     dword ptr [rax+rax+00h]
0x14001c66a  sub     esi, r13d
0x14001c66d  mov     edx, 0FEFFh
0x14001c672  mov     eax, esi
0x14001c674  neg     eax
0x14001c676  movzx   eax, word ptr [rdi+2]
0x14001c67a  sbb     cx, cx
0x14001c67d  add     [rsp+68h+arg_18], r13d
0x14001c685  and     ax, dx
0x14001c688  and     cx, 100h
0x14001c68d  or      cx, ax
0x14001c690  mov     eax, 4D0h
0x14001c695  mov     [rdi+2], cx
0x14001c699  mov     r14, [r14]
0x14001c69c  test    esi, esi
0x14001c69e  jnz     loc_14001C4BB
0x14001c6a4  mov     rcx, [rbx+8]; NetBuffer
0x14001c6a8  xor     r9d, r9d; AllocateMdlHandler
0x14001c6ab  xor     r8d, r8d; DataBackFill
0x14001c6ae  mov     edx, r12d; DataOffsetDelta
0x14001c6b1  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001c6b8  nop     dword ptr [rax+rax+00h]
0x14001c6bd  test    eax, eax
0x14001c6bf  jns     short loc_14001C6C6
0x14001c6c1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001c6c6  xor     eax, eax
0x14001c6c8  mov     rbx, [rsp+68h+arg_10]
0x14001c6d0  add     rsp, 30h
0x14001c6d4  pop     r15
0x14001c6d6  pop     r14
0x14001c6d8  pop     r13
0x14001c6da  pop     r12
0x14001c6dc  pop     rdi
0x14001c6dd  pop     rsi
0x14001c6de  pop     rbp
0x14001c6df  retn
0x14001c6e1  mov     eax, 0C000009Ah
0x14001c6e6  jmp     short loc_14001C6C8
```
