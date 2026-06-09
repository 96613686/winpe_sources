# HUBDSM_ComparingSerialNumberOnReEnumeration

- ea: `0x1400209d0`
- end: `0x140020b62`
- name: `HUBDSM_ComparingSerialNumberOnReEnumeration`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400025a4`
- `0x1400067ac`
- `0x1400209d0`
- `0x140033530`
- `0x1400338f8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140020a7f`
- `ntoskrnl!RtlCompareMemory` at `0x140020a7f`

## pseudocode

```c
__int64 __fastcall HUBDSM_ComparingSerialNumberOnReEnumeration(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  const void *v7; // rbp
  int v8; // ecx
  int v9; // r15d
  unsigned int v10; // r14d
  __int64 v11; // rsi
  unsigned int v12; // edi
  char v14; // [rsp+28h] [rbp-50h]

  v4 = *(_QWORD *)(a1 + 960);
  v5 = *(_QWORD *)(v4 + 2160);
  v6 = *(_DWORD *)(v4 + 1644) & 0x800;
  v7 = (const void *)(v5 + 12);
  v8 = (*(_DWORD *)(v4 + 1644) & 0x800) != 0 ? 14 : 2;
  v9 = *(_DWORD *)(v4 + 2156) - v8;
  if ( !(_DWORD)v6 )
    v7 = *(const void **)(v4 + 2160);
  v10 = *(_DWORD *)(v4 + 264) - 2;
  if ( v9 == v10 )
  {
    v11 = v4 + 1740;
    v12 = 4089;
    LODWORD(v5) = RtlCompareMemory((const void *)(v4 + 1742), v7, v10);
    if ( (_DWORD)v5 == v10 )
      return v12;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = v5;
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(*(_QWORD *)(v4 + 8) + 1432LL),
        v5,
        5,
        115,
        (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
        v14,
        v10);
    }
  }
  else
  {
    v11 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v4 + 8) + 1432LL),
        v5,
        5,
        114,
        (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
    }
  }
  v12 = 4061;
  if ( (*(_DWORD *)(v4 + 2444) & 0x20) != 0 )
    HUBMISC_VerifierDbgBreak("DeviceHwVerifierSerialNumberMismatchOnRenumeration", v4 + 512, v6, a4);
  if ( v11 )
  {
    if ( (byte_14006ED42 & 0x40) != 0 )
      McTemplateK0psqzq_EtwWriteTransfer(
        v8,
        v5,
        v4 + 1524,
        *(_QWORD *)(*(_QWORD *)v4 + 248LL),
        (__int64)v7,
        v9,
        v11 + 2,
        v10);
  }
  else if ( (byte_14006ED42 & 0x40) != 0 )
  {
    McTemplateK0psqzq_EtwWriteTransfer(v8, v5, v4 + 1524, *(_QWORD *)(*(_QWORD *)v4 + 248LL), (__int64)v7, v9, 0, 0);
  }
  return v12;
}

```

## disassembly

```asm
0x1400209d0  push    rbx
0x1400209d2  push    rbp
0x1400209d3  push    rsi
0x1400209d4  push    rdi
0x1400209d5  push    r14
0x1400209d7  push    r15
0x1400209d9  sub     rsp, 48h
0x1400209dd  mov     rbx, [rcx+3C0h]
0x1400209e4  mov     rdx, [rbx+870h]
0x1400209eb  mov     r8d, [rbx+66Ch]
0x1400209f2  mov     r15d, [rbx+86Ch]
0x1400209f9  and     r8d, 800h
0x140020a00  mov     r14d, [rbx+108h]
0x140020a07  mov     eax, r8d
0x140020a0a  neg     eax
0x140020a0c  lea     rbp, [rdx+0Ch]
0x140020a10  sbb     ecx, ecx
0x140020a12  and     ecx, 0Ch
0x140020a15  add     ecx, 2
0x140020a18  sub     r15d, ecx
0x140020a1b  test    r8d, r8d
0x140020a1e  cmovz   rbp, rdx
0x140020a22  add     r14d, 0FFFFFFFEh
0x140020a26  cmp     r15d, r14d
0x140020a29  jz      short loc_140020A69
0x140020a2b  xor     esi, esi
0x140020a2d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140020a34  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020a3b  jz      loc_140020AD8
0x140020a41  mov     rcx, [rbx+8]
0x140020a45  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140020a4c  lea     r9d, [rsi+72h]
0x140020a50  mov     [rsp+78h+var_58], rax
0x140020a55  lea     r8d, [rsi+5]
0x140020a59  mov     dl, 2
0x140020a5b  mov     rcx, [rcx+598h]
0x140020a62  call    WPP_RECORDER_SF_
0x140020a67  jmp     short loc_140020AD8
0x140020a69  lea     rsi, [rbx+6CCh]
0x140020a70  mov     r8d, r14d; Length
0x140020a73  lea     rcx, [rsi+2]; Source1
0x140020a77  mov     rdx, rbp; Source2
0x140020a7a  mov     edi, 0FF9h
0x140020a7f  call    cs:__imp_RtlCompareMemory
0x140020a86  nop     dword ptr [rax+rax+00h]
0x140020a8b  mov     rdx, rax
0x140020a8e  cmp     eax, r14d
0x140020a91  jz      loc_140020B52
0x140020a97  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140020a9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020aa5  jz      short loc_140020AD8
0x140020aa7  mov     rcx, [rbx+8]
0x140020aab  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140020ab2  mov     r9d, 73h ; 's'
0x140020ab8  mov     dword ptr [rsp+78h+var_48], r14d
0x140020abd  mov     dword ptr [rsp+78h+var_50], edx
0x140020ac1  mov     dl, 2
0x140020ac3  mov     [rsp+78h+var_58], rax
0x140020ac8  mov     rcx, [rcx+598h]
0x140020acf  lea     r8d, [r9-6Eh]
0x140020ad3  call    WPP_RECORDER_SF_dD
0x140020ad8  mov     edi, 0FDDh
0x140020add  mov     eax, [rbx+98Ch]
0x140020ae3  test    al, 20h
0x140020ae5  jz      short loc_140020AFA
0x140020ae7  lea     rdx, [rbx+200h]
0x140020aee  lea     rcx, aDevicehwverifi_7; "DeviceHwVerifierSerialNumberMismatchOnR"...
0x140020af5  call    HUBMISC_VerifierDbgBreak
0x140020afa  test    rsi, rsi
0x140020afd  jz      short loc_140020B18
0x140020aff  test    cs:byte_14006ED42, 40h
0x140020b06  jz      short loc_140020B52
0x140020b08  lea     rax, [rsi+2]
0x140020b0c  mov     [rsp+78h+var_40], r14d
0x140020b11  mov     [rsp+78h+var_48], rax
0x140020b16  jmp     short loc_140020B32
0x140020b18  test    cs:byte_14006ED42, 40h
0x140020b1f  jz      short loc_140020B52
0x140020b21  mov     [rsp+78h+var_40], 0
0x140020b29  mov     [rsp+78h+var_48], 0
0x140020b32  mov     r9, [rbx]
0x140020b35  lea     r8, [rbx+5F4h]
0x140020b3c  mov     dword ptr [rsp+78h+var_50], r15d
0x140020b41  mov     [rsp+78h+var_58], rbp
0x140020b46  mov     r9, [r9+0F8h]
0x140020b4d  call    McTemplateK0psqzq_EtwWriteTransfer
0x140020b52  mov     eax, edi
0x140020b54  add     rsp, 48h
0x140020b58  pop     r15
0x140020b5a  pop     r14
0x140020b5c  pop     rdi
0x140020b5d  pop     rsi
0x140020b5e  pop     rbp
0x140020b5f  pop     rbx
0x140020b60  retn
```
