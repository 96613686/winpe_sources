# WinNatTranslateIpHeader

- ea: `0x1400057b0`
- end: `0x140005a12`
- name: `WinNatTranslateIpHeader`
- size: `610`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char, char, char)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006c80`
- `0x14001cef8`
- `0x14001d310`

## callees

- `0x1400057b0`
- `0x140005a18`
- `0x14000caa0`
- `0x14001ee10`

## import_xrefs

- `NETIO!RtlCopyBufferToMdl` at `0x1400059dd`
- `NETIO!RtlCopyBufferToMdl` at `0x1400059dd`
- `NDIS!NdisGetDataBuffer` at `0x140005895`
- `NDIS!NdisGetDataBuffer` at `0x140005895`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400059a6`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400059a6`

## pseudocode

```c
__int64 __fastcall WinNatTranslateIpHeader(__int64 a1, __int64 a2, __int64 a3, char a4, char a5, char a6)
{
  char v6; // al
  int v11; // r8d
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 result; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  _DWORD *DataBuffer; // rdi
  int v20; // ecx
  __int16 v21; // ax
  __int16 v22; // cx
  int v23; // ecx
  NDIS_STATUS v24; // r14d
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // [rsp+90h] [rbp+18h] BYREF

  v6 = *(_BYTE *)(a3 + 17);
  if ( v6 == 4 )
  {
    if ( !a4 && **(_WORD **)(a1 + 88) == 23 )
    {
LABEL_4:
      v11 = 20;
      if ( !a4 )
        v11 = 40;
      v12 = 112;
      if ( !a4 )
        v12 = 88;
      v13 = *(_QWORD *)(v12 + a1);
      v14 = 104;
      v15 = v13 + 4;
      if ( !a4 )
        v14 = 96;
      return WinNatTranslateIpHeader64(*(_QWORD *)(v14 + a1) + 4LL, v15, *(_QWORD *)(a2 + 8), a3, v11, a4, a5);
    }
  }
  else if ( v6 == 6 && a4 && **(_WORD **)(a1 + 104) == 2 )
  {
    goto LABEL_4;
  }
  v27 = 0;
  if ( !a6 )
  {
    v24 = NdisRetreatNetBufferDataStart(*(PNET_BUFFER *)(a2 + 8), *(unsigned __int8 *)(a3 + 149), 0, 0);
    if ( v24 < 0 )
      goto LABEL_28;
    RtlCopyBufferToMdl(
      *(_QWORD *)a3,
      *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL),
      *(unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL),
      *(unsigned __int8 *)(a3 + 149),
      &v27);
    if ( v27 != *(unsigned __int8 *)(a3 + 149) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v26, v25);
  }
  DataBuffer = NdisGetDataBuffer(*(PNET_BUFFER *)(a2 + 8), *(unsigned __int8 *)(a3 + 149), 0, 1u, 0);
  if ( !DataBuffer )
  {
    v24 = -1073741823;
LABEL_28:
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v18, v17);
    return (unsigned int)v24;
  }
  if ( *(_BYTE *)(a3 + 17) != 4 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v18, v17);
  if ( !a4 )
  {
    v20 = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 4LL);
    if ( !a5 )
    {
      DataBuffer[4] = v20;
      if ( !*(_BYTE *)(a1 + 280) )
        goto LABEL_19;
      v20 = *(_DWORD *)(*(_QWORD *)(a1 + 96) + 4LL);
    }
    DataBuffer[3] = v20;
    goto LABEL_19;
  }
  v23 = *(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL);
  if ( !a5 )
  {
    DataBuffer[3] = v23;
    if ( !*(_BYTE *)(a1 + 280) )
      goto LABEL_19;
    v23 = *(_DWORD *)(*(_QWORD *)(a1 + 112) + 4LL);
  }
  DataBuffer[4] = v23;
LABEL_19:
  *(_BYTE *)(a3 + 208) = 4;
  *((_WORD *)DataBuffer + 5) = 0;
  v21 = tcpxsum(0, DataBuffer, 20);
  v22 = ~v21;
  if ( v21 == -1 )
    v22 = -1;
  result = 0;
  *((_WORD *)DataBuffer + 5) = v22;
  return result;
}

```

## disassembly

```asm
0x1400057b0  push    rbx
0x1400057b2  push    rbp
0x1400057b3  push    rsi
0x1400057b4  push    rdi
0x1400057b5  push    r14
0x1400057b7  push    r15
0x1400057b9  sub     rsp, 48h
0x1400057bd  movzx   eax, byte ptr [r8+11h]
0x1400057c2  movzx   ebp, r9b
0x1400057c6  mov     rbx, r8
0x1400057c9  mov     rdi, rdx
0x1400057cc  mov     rsi, rcx
0x1400057cf  cmp     al, 4
0x1400057d1  jnz     loc_140005924
0x1400057d7  test    r9b, r9b
0x1400057da  jnz     loc_140005863
0x1400057e0  mov     rax, [rcx+58h]
0x1400057e4  cmp     word ptr [rax], 17h
0x1400057e8  jnz     short loc_140005863
0x1400057ea  test    bpl, bpl
0x1400057ed  mov     eax, 28h ; '('
0x1400057f2  mov     r8d, 14h
0x1400057f8  mov     ecx, 58h ; 'X'
0x1400057fd  cmovz   r8d, eax
0x140005801  mov     r9, rbx
0x140005804  mov     eax, 70h ; 'p'
0x140005809  cmovz   eax, ecx
0x14000580c  mov     ecx, 60h ; '`'
0x140005811  mov     rdx, [rax+rsi]
0x140005815  mov     eax, 68h ; 'h'
0x14000581a  add     rdx, 4
0x14000581e  test    bpl, bpl
0x140005821  cmovz   eax, ecx
0x140005824  mov     rcx, [rax+rsi]
0x140005828  movzx   eax, [rsp+78h+arg_20]
0x140005830  add     rcx, 4
0x140005834  mov     [rsp+78h+var_48], al
0x140005838  mov     [rsp+78h+var_50], bpl
0x14000583d  mov     [rsp+78h+AlignOffset], r8d
0x140005842  mov     r8, [rdi+8]
0x140005846  call    WinNatTranslateIpHeader64
0x14000584b  add     rsp, 48h
0x14000584f  pop     r15
0x140005851  pop     r14
0x140005853  pop     rdi
0x140005854  pop     rsi
0x140005855  pop     rbp
0x140005856  pop     rbx
0x140005857  retn
0x140005859  mov     rax, [rcx+68h]
0x14000585d  cmp     word ptr [rax], 2
0x140005861  jz      short loc_1400057EA
0x140005863  xor     r15d, r15d
0x140005866  mov     [rsp+78h+arg_10], r15
0x14000586e  cmp     [rsp+78h+arg_28], r15b
0x140005876  jz      loc_140005994
0x14000587c  movzx   edx, byte ptr [rbx+95h]; BytesNeeded
0x140005883  mov     r9d, 1; AlignMultiple
0x140005889  mov     rcx, [rdi+8]; NetBuffer
0x14000588d  xor     r8d, r8d; Storage
0x140005890  mov     [rsp+78h+AlignOffset], r15d; AlignOffset
0x140005895  call    cs:__imp_NdisGetDataBuffer
0x14000589c  nop     dword ptr [rax+rax+00h]
0x1400058a1  mov     rdi, rax
0x1400058a4  test    rax, rax
0x1400058a7  jz      loc_140005950
0x1400058ad  cmp     byte ptr [rbx+11h], 4
0x1400058b1  jnz     loc_140005A08
0x1400058b7  test    bpl, bpl
0x1400058ba  jnz     short loc_14000593A
0x1400058bc  mov     rax, [rsi+58h]
0x1400058c0  mov     ecx, [rax+4]
0x1400058c3  cmp     [rsp+78h+arg_20], r15b
0x1400058cb  jnz     loc_14000598C
0x1400058d1  mov     [rdi+10h], ecx
0x1400058d4  cmp     [rsi+118h], r15b
0x1400058db  jnz     loc_140005985
0x1400058e1  mov     byte ptr [rbx+0D0h], 4
0x1400058e8  mov     r8d, 14h
0x1400058ee  mov     rdx, rdi
0x1400058f1  mov     [rdi+0Ah], r15w
0x1400058f6  xor     ecx, ecx
0x1400058f8  call    tcpxsum
0x1400058fd  movzx   ecx, ax
0x140005900  mov     edx, 0FFFFh
0x140005905  cmp     ax, dx
0x140005908  not     cx
0x14000590b  cmovz   cx, ax
0x14000590f  mov     eax, r15d
0x140005912  mov     [rdi+0Ah], cx
0x140005916  add     rsp, 48h
0x14000591a  pop     r15
0x14000591c  pop     r14
0x14000591e  pop     rdi
0x14000591f  pop     rsi
0x140005920  pop     rbp
0x140005921  pop     rbx
0x140005922  retn
0x140005924  cmp     al, 6
0x140005926  jnz     loc_140005863
0x14000592c  test    bpl, bpl
0x14000592f  jz      loc_140005863
0x140005935  jmp     loc_140005859
0x14000593a  mov     rax, [rsi+68h]
0x14000593e  mov     ecx, [rax+4]
0x140005941  cmp     [rsp+78h+arg_20], r15b
0x140005949  jz      short loc_14000596C
0x14000594b  mov     [rdi+10h], ecx
0x14000594e  jmp     short loc_1400058E1
0x140005950  mov     r14d, 0C0000001h
0x140005956  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000595b  mov     eax, r14d
0x14000595e  add     rsp, 48h
0x140005962  pop     r15
0x140005964  pop     r14
0x140005966  pop     rdi
0x140005967  pop     rsi
0x140005968  pop     rbp
0x140005969  pop     rbx
0x14000596a  retn
0x14000596c  mov     [rdi+0Ch], ecx
0x14000596f  cmp     [rsi+118h], r15b
0x140005976  jz      loc_1400058E1
0x14000597c  mov     rax, [rsi+70h]
0x140005980  mov     ecx, [rax+4]
0x140005983  jmp     short loc_14000594B
0x140005985  mov     rax, [rsi+60h]
0x140005989  mov     ecx, [rax+4]
0x14000598c  mov     [rdi+0Ch], ecx
0x14000598f  jmp     loc_1400058E1
0x140005994  movzx   edx, byte ptr [r8+95h]; DataOffsetDelta
0x14000599c  xor     r9d, r9d; AllocateMdlHandler
0x14000599f  mov     rcx, [rdi+8]; NetBuffer
0x1400059a3  xor     r8d, r8d; DataBackFill
0x1400059a6  call    cs:__imp_NdisRetreatNetBufferDataStart
0x1400059ad  nop     dword ptr [rax+rax+00h]
0x1400059b2  mov     r14d, eax
0x1400059b5  test    eax, eax
0x1400059b7  js      short loc_140005956
0x1400059b9  mov     rdx, [rdi+8]
0x1400059bd  lea     rax, [rsp+78h+arg_10]
0x1400059c5  movzx   r9d, byte ptr [rbx+95h]
0x1400059cd  mov     rcx, [rbx]
0x1400059d0  mov     qword ptr [rsp+78h+AlignOffset], rax
0x1400059d5  mov     r8d, [rdx+10h]
0x1400059d9  mov     rdx, [rdx+8]
0x1400059dd  call    cs:__imp_RtlCopyBufferToMdl
0x1400059e4  nop     dword ptr [rax+rax+00h]
0x1400059e9  movzx   eax, byte ptr [rbx+95h]
0x1400059f0  cmp     [rsp+78h+arg_10], rax
0x1400059f8  jz      loc_14000587C
0x1400059fe  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140005a03  jmp     loc_14000587C
0x140005a08  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140005a0d  jmp     loc_1400058B7
```
