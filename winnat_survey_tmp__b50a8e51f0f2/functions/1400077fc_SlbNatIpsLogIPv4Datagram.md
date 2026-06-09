# SlbNatIpsLogIPv4Datagram

- ea: `0x1400077fc`
- end: `0x140007ba3`
- name: `SlbNatIpsLogIPv4Datagram`
- size: `935`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001c30`
- `0x1400020e0`
- `0x140006340`
- `0x140006b74`
- `0x140006f04`
- `0x14001515c`

## callees

- `0x1400077fc`
- `0x1400093b8`
- `0x1400093f0`
- `0x140009a20`
- `0x14002d220`

## import_xrefs

- `NDIS!NdisGetDataBuffer` at `0x14000788a`
- `NDIS!NdisGetDataBuffer` at `0x14000788a`

## pseudocode

```c
__int64 __fastcall SlbNatIpsLogIPv4Datagram(
        char a1,
        unsigned int a2,
        __int64 a3,
        char a4,
        char a5,
        _QWORD *a6,
        int a7,
        int a8)
{
  _QWORD *v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // r13
  __int64 result; // rax
  int v12; // eax
  struct _NET_BUFFER *v13; // rcx
  unsigned int DataLength; // r14d
  _BYTE *DataBuffer; // rax
  __int64 v16; // rcx
  char v17; // r15
  _BYTE *v18; // r11
  int v19; // ebx
  __int64 v20; // rdx
  _BYTE *v21; // rdx
  unsigned int v22; // r9d
  __int64 v23; // rdi
  __int64 v24; // rbx
  int v25; // edx
  int v26; // ecx
  unsigned int v27; // r9d
  unsigned int v28; // r10d
  int v29; // [rsp+B8h] [rbp-29h] BYREF
  unsigned int v30; // [rsp+BCh] [rbp-25h] BYREF
  unsigned int v31; // [rsp+C0h] [rbp-21h]
  int v32; // [rsp+C4h] [rbp-1Dh]
  _BYTE *v33; // [rsp+C8h] [rbp-19h]
  __int64 v34; // [rsp+D0h] [rbp-11h] BYREF
  __int64 v35[8]; // [rsp+D8h] [rbp-9h] BYREF

  v8 = a6;
  v9 = 0;
  v10 = a3;
  result = a2;
  if ( !a6 )
    goto LABEL_23;
  do
  {
    v30 = 0;
    v29 = 0;
    LODWORD(a6) = 0;
    v35[0] = 0;
    v34 = 0;
    if ( dword_1400264E8 <= 0 )
    {
      if ( !v10 || !*(_DWORD *)(v10 + 40) )
      {
LABEL_4:
        v12 = 0;
        goto LABEL_5;
      }
    }
    else if ( !v10 || (*(_DWORD *)(v10 + 24) & 4) != 0 )
    {
      goto LABEL_4;
    }
    v12 = 1;
LABEL_5:
    v13 = (struct _NET_BUFFER *)v8[1];
    v32 = v12 + 1;
    DataLength = *(_DWORD *)(v13->Link.Region + 40) - v13->CurrentMdlOffset;
    if ( DataLength >= v13->DataLength )
      DataLength = v13->DataLength;
    DataBuffer = NdisGetDataBuffer(v13, DataLength, 0, 1u, 0);
    v17 = 0;
    a3 = 0;
    v18 = DataBuffer;
    v19 = 0;
    v20 = 0;
    if ( DataBuffer )
    {
      if ( DataLength )
      {
        LOBYTE(v16) = 4 * (*DataBuffer & 0xF);
        if ( DataLength >= (unsigned __int8)v16 )
        {
          v17 = DataBuffer[9];
          v21 = &DataBuffer[(unsigned __int8)v16];
          v31 = (unsigned __int8)v16;
          v22 = DataLength - (unsigned __int8)v16;
          v33 = DataBuffer;
          a3 = (unsigned __int8)v16;
          if ( v17 == 6 )
          {
            v9 = (__int64)&DataBuffer[(unsigned __int8)v16];
            v19 = v22 >= 0x14 ? 0x14 : 0;
            if ( v22 < 0x14 )
              v9 = 0;
            goto LABEL_44;
          }
          if ( v17 == 17 )
          {
            if ( v22 >= 8 )
              v9 = (__int64)&DataBuffer[(unsigned __int8)v16];
            v19 = v22 < 8 ? 0 : 8;
LABEL_15:
            v20 = (__int64)DataBuffer;
            goto LABEL_16;
          }
          if ( v17 != 1 || v22 < 8 )
            goto LABEL_15;
          v9 = (__int64)&DataBuffer[(unsigned __int8)v16];
          LOBYTE(v16) = 1;
          LOBYTE(v21) = *v21;
          v19 = 8;
          if ( !(unsigned __int8)WinNatIsIcmpErrorMessage(v16, v21) || v27 < 0x1C )
          {
            a3 = v28;
LABEL_44:
            v20 = (__int64)v18;
            goto LABEL_16;
          }
          SlbNatIpsExtractIPv4EventInfo(
            (_DWORD)v18 + v28 + 8,
            DataLength - v28 - 8,
            (unsigned int)&v30,
            (unsigned int)&v29,
            (__int64)&a6,
            (__int64)v35,
            (__int64)&v34);
          a3 = v31;
          v20 = (__int64)v33;
        }
      }
    }
LABEL_16:
    if ( !a7 )
      goto LABEL_51;
    if ( a7 != 1 )
    {
      if ( a7 == 2 )
      {
        if ( (byte_140026BED & 4) != 0 )
          McTemplateK0qqqqqqqqqqqqqqbr9br10br12br13_EtwWriteTransfer(
            v30,
            (const EVENT_DESCRIPTOR *)WINNATM_SKIPPED_IPV4_PACKET,
            a3,
            a8,
            a1,
            a2,
            v32,
            v17,
            a4,
            a5,
            *(_DWORD *)(v8[1] + 24LL),
            DataLength,
            a3,
            v19,
            v30,
            v29,
            (int)a6,
            v20,
            v9,
            v35[0],
            v34);
        goto LABEL_21;
      }
      if ( a7 != 3 )
        goto LABEL_21;
LABEL_51:
      if ( (byte_140026BED & 8) != 0 )
        McTemplateK0qqqqqqqqqqqqqqbr9br10br12br13_EtwWriteTransfer(
          v30,
          (const EVENT_DESCRIPTOR *)WINNATM_FORWARDED_IPV4_PACKET,
          a3,
          a8,
          a1,
          a2,
          v32,
          v17,
          a4,
          a5,
          *(_DWORD *)(v8[1] + 24LL),
          DataLength,
          a3,
          v19,
          v30,
          v29,
          (int)a6,
          v20,
          v9,
          v35[0],
          v34);
      goto LABEL_21;
    }
    if ( Microsoft_Windows_WinNatEnableBits < 0 )
      McTemplateK0qqqqqqqqqqqqqqbr9br10br12br13_EtwWriteTransfer(
        v30,
        (const EVENT_DESCRIPTOR *)WINNATM_DROPPED_IPV4_PACKET,
        a3,
        a8,
        a1,
        a2,
        v32,
        v17,
        a4,
        a5,
        *(_DWORD *)(v8[1] + 24LL),
        DataLength,
        a3,
        v19,
        v30,
        v29,
        (int)a6,
        v20,
        v9,
        v35[0],
        v34);
LABEL_21:
    v8 = (_QWORD *)*v8;
    v9 = 0;
  }
  while ( v8 );
  result = a2;
LABEL_23:
  v23 = 0;
  v24 = 0;
  do
  {
    v25 = *(_DWORD *)&SlbNatGlobalState[v24 + 456];
    if ( v25 == (_DWORD)result || !v25 && *(_DWORD *)&SlbNatGlobalState[v24 + 460] )
    {
      v26 = a8 - 15;
      if ( a8 == 15 || (v26 = a8 - 16, a8 == 16) || a8 == 25 )
      {
        if ( (xmmword_1400262E0 & 4) != 0 )
          WPP_SF_Sdd(
            v26,
            v25,
            a3,
            *(_QWORD *)&SlbNatGlobalState[v24 + 464],
            v25,
            *(_DWORD *)&SlbNatGlobalState[v24 + 460]);
      }
      result = a2;
    }
    ++v23;
    v24 += 16;
  }
  while ( v23 != 30 );
  return result;
}

```

## disassembly

```asm
0x1400077fc  mov     rax, rsp
0x1400077ff  mov     [rax+20h], r9d
0x140007803  mov     [rax+10h], edx
0x140007806  mov     [rax+8], ecx
0x140007809  push    rbp
0x14000780a  push    rbx
0x14000780b  push    rsi
0x14000780c  push    rdi
0x14000780d  push    r13
0x14000780f  push    r14
0x140007811  push    r15
0x140007813  lea     rbp, [rax-3Fh]
0x140007817  sub     rsp, 0E0h
0x14000781e  mov     rdi, [rbp+37h+arg_28]
0x140007822  xor     esi, esi
0x140007824  mov     r13, r8
0x140007827  mov     eax, edx
0x140007829  test    rdi, rdi
0x14000782c  jz      loc_14000793A
0x140007832  cmp     cs:dword_1400264E8, esi
0x140007838  mov     [rbp+37h+var_5C], esi
0x14000783b  mov     [rbp+37h+var_60], esi
0x14000783e  mov     dword ptr [rbp+37h+arg_28], esi
0x140007841  mov     [rbp+37h+var_40], rsi
0x140007845  mov     [rbp+37h+var_48], rsi
0x140007849  jle     loc_1400079D4
0x14000784f  test    r13, r13
0x140007852  jnz     loc_1400079BE
0x140007858  mov     eax, esi
0x14000785a  mov     rcx, [rdi+8]; NetBuffer
0x14000785e  inc     eax
0x140007860  mov     [rbp+37h+var_54], eax
0x140007863  mov     r9d, 1; AlignMultiple
0x140007869  mov     [rsp+110h+AlignOffset], esi; AlignOffset
0x14000786d  mov     r8d, [rcx+18h]
0x140007871  mov     rax, [rcx+8]
0x140007875  mov     r14d, [rax+28h]
0x140007879  sub     r14d, [rcx+10h]
0x14000787d  cmp     r14d, r8d
0x140007880  cmovnb  r14d, r8d
0x140007884  xor     r8d, r8d; Storage
0x140007887  mov     edx, r14d; BytesNeeded
0x14000788a  call    cs:__imp_NdisGetDataBuffer
0x140007891  nop     dword ptr [rax+rax+00h]
0x140007896  mov     r15d, esi
0x140007899  mov     r8d, esi
0x14000789c  mov     r11, rax
0x14000789f  mov     ebx, esi
0x1400078a1  mov     rdx, rsi
0x1400078a4  test    rax, rax
0x1400078a7  jz      short loc_1400078FF
0x1400078a9  test    r14d, r14d
0x1400078ac  jz      short loc_1400078FF
0x1400078ae  mov     cl, [rax]
0x1400078b0  and     cl, 0Fh
0x1400078b3  shl     cl, 2
0x1400078b6  movzx   r10d, cl
0x1400078ba  cmp     r14d, r10d
0x1400078bd  jb      short loc_1400078FF
0x1400078bf  movzx   r15d, byte ptr [rax+9]
0x1400078c4  lea     rdx, [rax+r10]
0x1400078c8  mov     r9d, r14d
0x1400078cb  mov     [rbp+37h+var_58], r10d
0x1400078cf  sub     r9d, r10d
0x1400078d2  mov     [rbp+37h+var_50], rax
0x1400078d6  mov     r8d, r10d
0x1400078d9  cmp     r15b, 6
0x1400078dd  jz      loc_1400079E9
0x1400078e3  cmp     r15b, 11h
0x1400078e7  jnz     loc_140007A0E
0x1400078ed  cmp     r9d, 8
0x1400078f1  cmovnb  rsi, rdx
0x1400078f5  sbb     ebx, ebx
0x1400078f7  not     ebx
0x1400078f9  and     ebx, 8
0x1400078fc  mov     rdx, rax
0x1400078ff  mov     ecx, [rbp+37h+arg_30]
0x140007902  test    ecx, ecx
0x140007904  jz      loc_140007A8B
0x14000790a  sub     ecx, 1
0x14000790d  jz      loc_140007B62
0x140007913  sub     ecx, 1
0x140007916  jnz     loc_140007A82
0x14000791c  test    cs:byte_140026BED, 4
0x140007923  jnz     loc_140007B2E
0x140007929  mov     rdi, [rdi]
0x14000792c  xor     esi, esi
0x14000792e  test    rdi, rdi
0x140007931  jnz     loc_140007832
0x140007937  mov     eax, [rbp+37h+arg_8]
0x14000793a  mov     rdi, rsi
0x14000793d  lea     r14, SlbNatGlobalState
0x140007944  mov     rbx, rsi
0x140007947  mov     edx, [rbx+r14+1C8h]
0x14000794f  cmp     edx, eax
0x140007951  jz      short loc_140007981
0x140007953  test    edx, edx
0x140007955  jz      short loc_140007977
0x140007957  inc     rdi
0x14000795a  add     rbx, 10h
0x14000795e  cmp     rdi, 1Eh
0x140007962  jnz     short loc_140007947
0x140007964  add     rsp, 0E0h
0x14000796b  pop     r15
0x14000796d  pop     r14
0x14000796f  pop     r13
0x140007971  pop     rdi
0x140007972  pop     rsi
0x140007973  pop     rbx
0x140007974  pop     rbp
0x140007975  retn
0x140007977  cmp     [rbx+r14+1CCh], esi
0x14000797f  jz      short loc_140007957
0x140007981  mov     ecx, [rbp+37h+arg_38]
0x140007984  sub     ecx, 0Fh
0x140007987  jz      short loc_140007993
0x140007989  sub     ecx, 1
0x14000798c  jz      short loc_140007993
0x14000798e  cmp     ecx, 9
0x140007991  jnz     short loc_1400079B9
0x140007993  test    byte ptr cs:xmmword_1400262E0, 4
0x14000799a  jz      short loc_1400079B9
0x14000799c  mov     eax, [rbx+r14+1CCh]
0x1400079a4  mov     r9, [rbx+r14+1D0h]
0x1400079ac  mov     dword ptr [rsp+110h+var_E8], eax
0x1400079b0  mov     [rsp+110h+AlignOffset], edx
0x1400079b4  call    WPP_SF_Sdd
0x1400079b9  mov     eax, [rbp+37h+arg_8]
0x1400079bc  jmp     short loc_140007957
0x1400079be  mov     eax, [r13+18h]
0x1400079c2  test    al, 4
0x1400079c4  jnz     loc_140007858
0x1400079ca  mov     eax, 1
0x1400079cf  jmp     loc_14000785A
0x1400079d4  test    r13, r13
0x1400079d7  jz      loc_140007858
0x1400079dd  cmp     [r13+28h], esi
0x1400079e1  jz      loc_140007858
0x1400079e7  jmp     short loc_1400079CA
0x1400079e9  cmp     r9d, 14h
0x1400079ed  mov     rsi, rdx
0x1400079f0  sbb     ebx, ebx
0x1400079f2  xor     eax, eax
0x1400079f4  not     ebx
0x1400079f6  and     ebx, 14h
0x1400079f9  cmp     r9d, 14h
0x1400079fd  cmovb   rsi, rax
0x140007a01  jmp     short loc_140007A06
0x140007a03  mov     r8d, r10d
0x140007a06  mov     rdx, r11
0x140007a09  jmp     loc_1400078FF
0x140007a0e  cmp     r15b, 1
0x140007a12  jnz     loc_1400078FC
0x140007a18  cmp     r9d, 8
0x140007a1c  jb      loc_1400078FC
0x140007a22  mov     rsi, rdx
0x140007a25  mov     cl, r15b
0x140007a28  mov     dl, [rdx]
0x140007a2a  mov     ebx, 8
0x140007a2f  call    WinNatIsIcmpErrorMessage
0x140007a34  test    al, al
0x140007a36  jz      short loc_140007A03
0x140007a38  cmp     r9d, 1Ch
0x140007a3c  jb      short loc_140007A03
0x140007a3e  lea     rax, [rbp+37h+var_48]
0x140007a42  mov     edx, r14d
0x140007a45  mov     qword ptr [rsp+110h+var_E0], rax
0x140007a4a  lea     rcx, [r10+8]
0x140007a4e  lea     rax, [rbp+37h+var_40]
0x140007a52  sub     edx, r10d
0x140007a55  mov     [rsp+110h+var_E8], rax
0x140007a5a  lea     r9, [rbp+37h+var_60]
0x140007a5e  lea     rax, [rbp+37h+arg_28]
0x140007a62  sub     edx, ebx
0x140007a64  add     rcx, r11
0x140007a67  mov     qword ptr [rsp+110h+AlignOffset], rax
0x140007a6c  lea     r8, [rbp+37h+var_5C]
0x140007a70  call    SlbNatIpsExtractIPv4EventInfo
0x140007a75  mov     r8d, [rbp+37h+var_58]
0x140007a79  mov     rdx, [rbp+37h+var_50]
0x140007a7d  jmp     loc_1400078FF
0x140007a82  cmp     ecx, 1
0x140007a85  jnz     loc_140007929
0x140007a8b  test    cs:byte_140026BED, 8
0x140007a92  jz      loc_140007929
0x140007a98  mov     rcx, [rbp+37h+var_48]
0x140007a9c  mov     [rsp+0A0h], rcx
0x140007aa4  mov     rcx, [rbp+37h+var_40]
0x140007aa8  mov     [rsp+110h+var_78], rcx
0x140007ab0  mov     [rsp+110h+var_80], rsi
0x140007ab8  mov     [rsp+110h+var_88], rdx
0x140007ac0  lea     rdx, WINNATM_FORWARDED_IPV4_PACKET
0x140007ac7  mov     ecx, dword ptr [rbp+37h+arg_28]
0x140007aca  mov     rax, [rdi+8]
0x140007ace  mov     r9d, [rbp+37h+arg_38]
0x140007ad2  mov     dword ptr [rsp+110h+var_90], ecx
0x140007ad9  mov     ecx, [rbp+37h+var_60]
0x140007adc  mov     eax, [rax+18h]
0x140007adf  mov     [rsp+110h+var_98], ecx
0x140007ae3  mov     ecx, [rbp+37h+var_5C]
0x140007ae6  mov     [rsp+110h+var_A0], ecx
0x140007aea  mov     [rsp+110h+var_A8], ebx
0x140007aee  mov     [rsp+110h+var_B0], r8d
0x140007af3  mov     [rsp+110h+var_B8], r14d
0x140007af8  mov     [rsp+110h+var_C0], eax
0x140007afc  mov     eax, dword ptr [rbp+37h+arg_20]
0x140007aff  mov     [rsp+110h+var_C8], eax
0x140007b03  mov     eax, [rbp+37h+arg_18]
0x140007b06  mov     [rsp+110h+var_D0], eax
0x140007b0a  mov     eax, [rbp+37h+var_54]
0x140007b0d  mov     [rsp+110h+var_D8], r15d
0x140007b12  mov     [rsp+110h+var_E0], eax
0x140007b16  mov     eax, [rbp+37h+arg_8]
0x140007b19  mov     dword ptr [rsp+110h+var_E8], eax
0x140007b1d  mov     eax, [rbp+37h+arg_0]
0x140007b20  mov     [rsp+110h+AlignOffset], eax
0x140007b24  call    McTemplateK0qqqqqqqqqqqqqqbr9br10br12br13_EtwWriteTransfer
0x140007b29  jmp     loc_140007929
0x140007b2e  mov     rcx, [rbp+37h+var_48]
0x140007b32  mov     [rsp+0A0h], rcx
0x140007b3a  mov     rcx, [rbp+37h+var_40]
0x140007b3e  mov     [rsp+110h+var_78], rcx
0x140007b46  mov     [rsp+110h+var_80], rsi
0x140007b4e  mov     [rsp+110h+var_88], rdx
0x140007b56  lea     rdx, WINNATM_SKIPPED_IPV4_PACKET
0x140007b5d  jmp     loc_140007AC7
0x140007b62  cmp     cs:Microsoft_Windows_WinNatEnableBits, 0
0x140007b69  jge     loc_140007929
0x140007b6f  mov     rcx, [rbp+37h+var_48]
0x140007b73  mov     [rsp+0A0h], rcx
0x140007b7b  mov     rcx, [rbp+37h+var_40]
0x140007b7f  mov     [rsp+110h+var_78], rcx
0x140007b87  mov     [rsp+110h+var_80], rsi
0x140007b8f  mov     [rsp+110h+var_88], rdx
0x140007b97  lea     rdx, WINNATM_DROPPED_IPV4_PACKET
0x140007b9e  jmp     loc_140007AC7
```
