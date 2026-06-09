# SrvNetEncryptData

- ea: `0x140001d70`
- end: `0x140002056`
- name: `SrvNetEncryptData`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400010f0`

## callees

- `0x140001d70`
- `0x140002060`
- `0x1400094e0`
- `0x140009af0`
- `0x14001389c`

## import_xrefs

- `TDI!TdiCopyMdlToBuffer` at `0x140001e81`
- `TDI!TdiCopyMdlToBuffer` at `0x140001e81`
- `ksecdd!BCryptEncrypt` at `0x140001f7a`
- `ksecdd!BCryptEncrypt` at `0x140001f7a`

## pseudocode

```c
__int64 __fastcall SrvNetEncryptData(unsigned int *a1)
{
  __int64 v1; // rax
  int LockArray_high; // esi
  __int64 v4; // rdx
  NTSTATUS v5; // r14d
  __int64 v7; // rsi
  __int64 v8; // r11
  ULONG cbOutput; // r10d
  unsigned int v10; // r8d
  __int64 v11; // rax
  int v12; // edx
  int v13; // ecx
  signed __int64 v14; // rbp
  void *v15; // rcx
  unsigned int v16; // eax
  int v17; // ebp
  __int16 v18; // r14
  PVOID BufferFromPool; // rax
  unsigned __int64 v20; // rax
  __int64 v21; // rbp
  unsigned __int16 *v22; // rdi
  __int128 pPaddingInfo; // [rsp+50h] [rbp-88h] BYREF
  __int128 v24; // [rsp+60h] [rbp-78h]
  __int128 v25; // [rsp+70h] [rbp-68h]
  __int128 v26; // [rsp+80h] [rbp-58h]
  __int128 v27; // [rsp+90h] [rbp-48h]
  __int64 v28; // [rsp+A0h] [rbp-38h]
  ULONG BytesCopied; // [rsp+E0h] [rbp+8h] BYREF
  ULONG pcbResult; // [rsp+E8h] [rbp+10h] BYREF

  v1 = *a1 + 52;
  BytesCopied = v1;
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  pcbResult = 0;
  v4 = (unsigned int)v1;
  if ( SrvDisableNetBufferLookAsideList )
  {
    if ( (unsigned int)v1 < 0x100uLL )
    {
      v4 = 256;
LABEL_22:
      LOWORD(v17) = 0;
      v18 = 0;
      BufferFromPool = (PVOID)SrvNetAllocateBufferFromPool(a1, v4);
      goto LABEL_29;
    }
LABEL_3:
    if ( (unsigned int)v1 > 0x1000100uLL )
    {
LABEL_4:
      v5 = -1073741670;
      goto LABEL_5;
    }
    goto LABEL_22;
  }
  if ( (unsigned int)v1 > 0x100100uLL )
    goto LABEL_3;
  if ( (unsigned int)v1 > 0x1100uLL )
  {
    v20 = v1 - 256;
    _BitScanReverse64((unsigned __int64 *)&v21, v20);
    _BitScanForward64(&v20, v20);
    if ( (_DWORD)v21 == (_DWORD)v20 )
      v17 = v21 - 12;
    else
      v17 = v21 - 11;
  }
  else
  {
    v17 = 0;
  }
  BufferFromPool = PplAllocateFromLookasideListProcessor(SrvNetBufferLookasides[v17], (unsigned __int16)LockArray_high);
  v18 = 2;
LABEL_29:
  v22 = (unsigned __int16 *)BufferFromPool;
  if ( !BufferFromPool )
    goto LABEL_4;
  *((_WORD *)BufferFromPool + 8) |= v18;
  *((_WORD *)BufferFromPool + 9) = v17;
  *((_WORD *)BufferFromPool + 10) = LockArray_high;
  *((_DWORD *)BufferFromPool + 9) = 0;
  v7 = *((_QWORD *)BufferFromPool + 3);
  *((_DWORD *)BufferFromPool + 9) = BytesCopied;
  *(_DWORD *)v7 = 1112364029;
  *(_DWORD *)(v7 + 36) = *a1;
  *(_DWORD *)(v7 + 40) = 0x10000;
  *(_QWORD *)(v7 + 44) = *((_QWORD *)a1 + 9);
  v5 = TdiCopyMdlToBuffer(
         *((PMDL *)a1 + 1),
         0,
         *((PVOID *)BufferFromPool + 3),
         0x34u,
         *((_DWORD *)BufferFromPool + 9),
         &BytesCopied);
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147483643 )
    goto LABEL_17;
  v8 = *((_QWORD *)a1 + 10);
  cbOutput = *a1;
  v28 = 0;
  pPaddingInfo = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v10 = HIDWORD(KeGetPcr()[1].LockArray);
  v11 = *(_QWORD *)(v8 + 8);
  v12 = *(_DWORD *)(v11 + 8);
  v13 = *(_DWORD *)(v11 + 12);
  *((_QWORD *)&v25 + 1) = v7 + 4;
  LODWORD(v24) = v12;
  *(_QWORD *)&pPaddingInfo = 0x100000058LL;
  *((_QWORD *)&v24 + 1) = v7 + 20;
  LODWORD(v25) = 32;
  LODWORD(v26) = v13;
  *((_QWORD *)&pPaddingInfo + 1) = v7 + 20;
  v14 = _InterlockedIncrement64((volatile signed __int64 *)SmbCryptoNonceCounter + 8 * (unsigned __int64)v10);
  *(_QWORD *)(v7 + 28) = v10;
  *(_QWORD *)(v7 + 20) = v14;
  v15 = *(void **)v8;
  pcbResult = 0;
  v5 = BCryptEncrypt(v15, (PUCHAR)(v7 + 52), cbOutput, &pPaddingInfo, 0, 0, (PUCHAR)(v7 + 52), cbOutput, &pcbResult, 0);
  if ( v5 < 0 )
  {
LABEL_17:
    SrvNetFreeBuffer(v22);
LABEL_5:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids,
          (unsigned int)v5);
    }
    return (unsigned int)v5;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids, *a1);
  }
  **((_QWORD **)v22 + 7) = *((_QWORD *)a1 + 1);
  *((_QWORD *)a1 + 1) = *((_QWORD *)v22 + 7);
  v16 = *((_DWORD *)v22 + 9);
  a1[12] |= 8u;
  *a1 = v16;
  return 0;
}

```

## disassembly

```asm
0x140001d70  mov     r11, rsp
0x140001d73  mov     [r11+18h], rbx
0x140001d77  mov     [r11+20h], rbp
0x140001d7b  push    rsi
0x140001d7c  push    rdi
0x140001d7d  push    r12
0x140001d7f  push    r14
0x140001d81  push    r15
0x140001d83  sub     rsp, 0B0h
0x140001d8a  mov     eax, [rcx]
0x140001d8c  xor     r12d, r12d
0x140001d8f  add     eax, 34h ; '4'
0x140001d92  mov     rbx, rcx
0x140001d95  mov     [r11+8], eax
0x140001d99  mov     esi, gs:1A4h
0x140001da1  cmp     cs:SrvDisableNetBufferLookAsideList, r12b
0x140001da8  mov     [r11+10h], r12d
0x140001dac  mov     [r11+10h], r12d
0x140001db0  mov     edx, eax
0x140001db2  jnz     loc_14000201E
0x140001db8  cmp     rdx, 100100h
0x140001dbf  jbe     loc_140002041
0x140001dc5  cmp     rdx, 1000100h
0x140001dcc  jbe     loc_140002030
0x140001dd2  mov     r14d, 0C000009Ah
0x140001dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ddf  lea     rax, WPP_GLOBAL_Control
0x140001de6  cmp     rcx, rax
0x140001de9  jz      short loc_140001E12
0x140001deb  test    dword ptr [rcx+2Ch], 100000h
0x140001df2  jz      short loc_140001E12
0x140001df4  cmp     byte ptr [rcx+29h], 1
0x140001df8  jb      short loc_140001E12
0x140001dfa  mov     rcx, [rcx+18h]
0x140001dfe  lea     r8, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids
0x140001e05  mov     edx, 0Fh
0x140001e0a  mov     r9d, r14d
0x140001e0d  call    WPP_SF_d
0x140001e12  mov     eax, r14d
0x140001e15  jmp     loc_140001FC7
0x140001e1a  or      [rdi+10h], r14w
0x140001e1f  mov     [rdi+12h], bp
0x140001e23  mov     [rdi+14h], si
0x140001e27  mov     [rdi+24h], r12d
0x140001e2b  test    rdi, rdi
0x140001e2e  jz      short loc_140001DD2
0x140001e30  mov     eax, [rsp+0D8h+arg_0]
0x140001e37  mov     r9d, 34h ; '4'; DestinationOffset
0x140001e3d  mov     rsi, [rdi+18h]
0x140001e41  xor     edx, edx; SourceOffset
0x140001e43  mov     [rdi+24h], eax
0x140001e46  mov     ebp, 1
0x140001e4b  mov     dword ptr [rsi], 424D53FDh
0x140001e51  mov     eax, [rbx]
0x140001e53  mov     [rsi+24h], eax
0x140001e56  mov     dword ptr [rsi+28h], 10000h
0x140001e5d  mov     rax, [rbx+48h]
0x140001e61  mov     [rsi+2Ch], rax
0x140001e65  lea     rax, [rsp+0D8h+arg_0]
0x140001e6d  mov     r8, [rdi+18h]; DestinationBuffer
0x140001e71  mov     rcx, [rbx+8]; SourceMdlChain
0x140001e75  mov     [rsp+0D8h+BytesCopied], rax; BytesCopied
0x140001e7a  mov     eax, [rdi+24h]
0x140001e7d  mov     [rsp+0D8h+DestinationBufferSize], eax; DestinationBufferSize
0x140001e81  call    cs:__imp_TdiCopyMdlToBuffer
0x140001e88  nop     dword ptr [rax+rax+00h]
0x140001e8d  mov     r14d, eax
0x140001e90  mov     eax, 80000000h
0x140001e95  lea     ecx, [r14+rax]
0x140001e99  test    eax, ecx
0x140001e9b  jz      loc_140001FE4
0x140001ea1  mov     r11, [rbx+50h]
0x140001ea5  lea     r9, [rsi+14h]
0x140001ea9  mov     r10d, [rbx]
0x140001eac  xor     eax, eax
0x140001eae  mov     [rsp+0D8h+var_38], rax
0x140001eb6  xorps   xmm0, xmm0
0x140001eb9  movups  [rsp+0D8h+pPaddingInfo], xmm0
0x140001ebe  movups  [rsp+0D8h+var_78], xmm0
0x140001ec3  movups  [rsp+0D8h+var_68], xmm0
0x140001ec8  movups  [rsp+0D8h+var_58], xmm0
0x140001ed0  movups  [rsp+0D8h+var_48], xmm0
0x140001ed8  mov     r8d, gs:1A4h
0x140001ee1  mov     rax, [r11+8]
0x140001ee5  mov     edx, [rax+8]
0x140001ee8  mov     ecx, [rax+0Ch]
0x140001eeb  lea     rax, [rsi+4]
0x140001eef  mov     qword ptr [rsp+0D8h+var_68+8], rax
0x140001ef4  mov     eax, r8d
0x140001ef7  shl     rax, 6
0x140001efb  add     rax, cs:SmbCryptoNonceCounter
0x140001f02  mov     dword ptr [rsp+0D8h+var_78], edx
0x140001f06  mov     dword ptr [rsp+0D8h+pPaddingInfo], 58h ; 'X'
0x140001f0e  mov     dword ptr [rsp+0D8h+pPaddingInfo+4], ebp
0x140001f12  mov     qword ptr [rsp+0D8h+var_78+8], r9
0x140001f17  mov     dword ptr [rsp+0D8h+var_68], 20h ; ' '
0x140001f1f  mov     dword ptr [rsp+0D8h+var_58], ecx
0x140001f26  mov     qword ptr [rsp+0D8h+pPaddingInfo+8], r9
0x140001f2b  mov     edx, r8d
0x140001f2e  lock xadd [rax], rbp
0x140001f33  mov     [rsp+0D8h+dwFlags], r12d; dwFlags
0x140001f38  lea     rax, [rsp+0D8h+arg_8]
0x140001f40  mov     [rsp+0D8h+pcbResult], rax; pcbResult
0x140001f45  inc     rbp
0x140001f48  mov     [rsp+0D8h+cbOutput], r10d; cbOutput
0x140001f4d  mov     r8d, r10d; cbInput
0x140001f50  mov     [rsi+1Ch], rdx
0x140001f54  lea     rdx, [rsi+34h]; pbInput
0x140001f58  mov     [rsp+0D8h+pbOutput], rdx; pbOutput
0x140001f5d  mov     [r9], rbp
0x140001f60  lea     r9, [rsp+0D8h+pPaddingInfo]; pPaddingInfo
0x140001f65  mov     rcx, [r11]; hKey
0x140001f68  mov     dword ptr [rsp+0D8h+BytesCopied], r12d; cbIV
0x140001f6d  mov     qword ptr [rsp+0D8h+DestinationBufferSize], r12; pbIV
0x140001f72  mov     [rsp+0D8h+arg_8], r12d
0x140001f7a  call    cs:__imp_BCryptEncrypt
0x140001f81  nop     dword ptr [rax+rax+00h]
0x140001f86  mov     r14d, eax
0x140001f89  test    eax, eax
0x140001f8b  js      short loc_140001FF1
0x140001f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f94  lea     rax, WPP_GLOBAL_Control
0x140001f9b  cmp     rcx, rax
0x140001f9e  jz      short loc_140001FA9
0x140001fa0  test    dword ptr [rcx+2Ch], 100000h
0x140001fa7  jnz     short loc_140001FFE
0x140001fa9  mov     rcx, [rdi+38h]
0x140001fad  mov     rax, [rbx+8]
0x140001fb1  mov     [rcx], rax
0x140001fb4  mov     rax, [rdi+38h]
0x140001fb8  mov     [rbx+8], rax
0x140001fbc  mov     eax, [rdi+24h]
0x140001fbf  or      dword ptr [rbx+30h], 8
0x140001fc3  mov     [rbx], eax
0x140001fc5  xor     eax, eax
0x140001fc7  lea     r11, [rsp+0D8h+var_28]
0x140001fcf  mov     rbx, [r11+40h]
0x140001fd3  mov     rbp, [r11+48h]
0x140001fd7  mov     rsp, r11
0x140001fda  pop     r15
0x140001fdc  pop     r14
0x140001fde  pop     r12
0x140001fe0  pop     rdi
0x140001fe1  pop     rsi
0x140001fe2  retn
0x140001fe4  cmp     r14d, 80000005h
0x140001feb  jz      loc_140001EA1
0x140001ff1  mov     rcx, rdi; Entry
0x140001ff4  call    SrvNetFreeBuffer
0x140001ff9  jmp     loc_140001DD8
0x140001ffe  cmp     byte ptr [rcx+29h], 4
0x140002002  jb      short loc_140001FA9
0x140002004  mov     r9d, [rbx]
0x140002007  lea     r8, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids
0x14000200e  mov     rcx, [rcx+18h]
0x140002012  mov     edx, 0Eh
0x140002017  call    WPP_SF_d
0x14000201c  jmp     short loc_140001FA9
0x14000201e  cmp     rdx, 100h
0x140002025  jnb     loc_140001DC5
0x14000202b  mov     edx, 100h
0x140002030  mov     ebp, r12d
0x140002033  mov     r14d, r12d
0x140002036  call    SrvNetAllocateBufferFromPool
0x14000203b  nop
0x14000203c  jmp     loc_14002AF17
0x140002041  cmp     rdx, 1100h
0x140002048  ja      loc_14002AEE2
0x14000204e  mov     ebp, r12d
0x140002051  jmp     loc_14002AEFC
0x14002aee2  add     rax, 0FFFFFFFFFFFFFF00h
0x14002aee8  bsr     rbp, rax
0x14002aeec  bsf     rax, rax
0x14002aef0  cmp     ebp, eax
0x14002aef2  jnz     short loc_14002AEF9
0x14002aef4  add     ebp, 0FFFFFFF4h
0x14002aef7  jmp     short loc_14002AEFC
0x14002aef9  add     ebp, 0FFFFFFF5h
0x14002aefc  lea     rax, SrvNetBufferLookasides
0x14002af03  mov     ecx, ebp
0x14002af05  movzx   edx, si
0x14002af08  mov     rcx, [rax+rcx*8]
0x14002af0c  call    PplAllocateFromLookasideListProcessor
0x14002af11  mov     r14d, 2
0x14002af17  mov     rdi, rax
0x14002af1a  test    rax, rax
0x14002af1d  jz      loc_140001DD2
0x14002af23  jmp     loc_140001E1A
```
