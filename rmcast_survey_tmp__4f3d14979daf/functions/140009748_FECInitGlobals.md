# FECInitGlobals

- ea: `0x140009748`
- end: `0x140009914`
- name: `FECInitGlobals`
- size: `460`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400378c0`

## callees

- `0x140005744`
- `0x140009748`
- `0x140009e08`
- `0x14001d300`

## string_xrefs

- `0x140009780`: `                                                                       \n  *                                                                       \n  * THIS SOFTWARE IS PROVIDED BY THE AUTHORS ``AS IS'' AND                \n  * ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,     \n  * THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A           \n  * PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE AUTHORS      \n  * BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDEN`
- `0x140009791`: `                                                                       \n  /*                                                                      \n  * fec.c -- forward error correction based on Vandermonde matrices       \n  * 980624                                                                \n  * (C) 1997-98 Luigi Rizzo (luigi@iet.unipi.it)                          \n  *                                                                       \n  * Portions derived from code by Phil Karn (ka`

## pseudocode

```c
__int64 FECInitGlobals()
{
  unsigned __int8 v0; // bl
  int i; // ecx
  __int64 v2; // rax
  unsigned __int8 v3; // cl
  __int64 v4; // rdx
  unsigned int v5; // edx
  unsigned __int8 v6; // cl
  __int64 j; // rcx
  __int64 k; // rcx
  __int64 m; // r8
  int v10; // r11d
  __int64 n; // r10
  unsigned __int8 v12; // al
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r10
  __int64 ii; // rcx

  if ( fPrintCopyright
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_ss(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_b1821e6972a431908bada29dc83e0a17_Traceguids,
      (unsigned int)FEC_COPYRIGHT_STRING1,
      (__int64)FEC_COPYRIGHT_STRING2);
  }
  v0 = 1;
  memset(gFECLog2, 0, 0x81u);
  for ( i = 0; i < 8; ++i )
  {
    v2 = v0;
    v0 *= 2;
    *((_BYTE *)gFECLog2 + v2) = i;
  }
  memset(gFECLog, 0, 0x400u);
  memset(&gFECExp, 0, 0x1FEu);
  v3 = 1;
  v4 = 0;
  do
  {
    *((_BYTE *)&gFECExp + v4) = v3;
    gFECLog[v3] = v4;
    if ( a101110001[v4] == 49 )
      byte_140022268 ^= v3;
    v4 = (unsigned int)(v4 + 1);
    v3 *= 2;
  }
  while ( (int)v4 < 8 );
  v5 = 9;
  gFECLog[(unsigned __int8)byte_140022268] = 8;
  do
  {
    v6 = 2 * *((_BYTE *)&gFECExp + v5 - 1);
    if ( *((_BYTE *)&gFECExp + v5 - 1) >= 0x80u )
      v6 ^= byte_140022268;
    *((_BYTE *)&gFECExp + v5) = v6;
    gFECLog[v6] = v5++;
  }
  while ( (int)v5 < 255 );
  gFECLog[0] = 255;
  for ( j = 0; j != 255; ++j )
    *((_BYTE *)&gFECExp + j + 255) = *((_BYTE *)&gFECExp + j);
  gFECInverse = 256;
  for ( k = 2; k != 256; ++k )
    *((_BYTE *)&gFECInverse + k) = *((_BYTE *)&gFECExp + 255 - gFECLog[k]);
  for ( m = 0; m != 256; m = v13 + 1 )
  {
    v10 = gFECLog[m];
    for ( n = 0; n != 256; n = v15 + 1 )
    {
      v12 = ModNN((unsigned int)(v10 + gFECLog[n]));
      *(_BYTE *)(v14 + v15) = *((_BYTE *)&gFECExp + v12);
    }
  }
  for ( ii = 0; ii != 256; ++ii )
  {
    LOBYTE(gFECMultTable[32 * ii]) = 0;
    *((_BYTE *)gFECMultTable + ii) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140009748  push    rbx
0x14000974a  push    rbp
0x14000974b  push    rdi
0x14000974c  push    r14
0x14000974e  sub     rsp, 38h
0x140009752  cmp     cs:fPrintCopyright, 0
0x140009759  mov     rdi, cs:off_14001F040; "101110001"
0x140009760  jz      short loc_1400097A4
0x140009762  mov     rcx, cs:WPP_GLOBAL_Control
0x140009769  lea     rax, WPP_GLOBAL_Control
0x140009770  cmp     rcx, rax
0x140009773  jz      short loc_1400097A4
0x140009775  mov     eax, [rcx+2Ch]
0x140009778  test    al, 4
0x14000977a  jz      short loc_1400097A4
0x14000977c  mov     rcx, [rcx+18h]
0x140009780  lea     rax, FEC_COPYRIGHT_STRING2; "                                       "...
0x140009787  mov     edx, 0Ah
0x14000978c  mov     [rsp+58h+var_38], rax
0x140009791  lea     r9, FEC_COPYRIGHT_STRING1; "                                       "...
0x140009798  lea     r8, WPP_b1821e6972a431908bada29dc83e0a17_Traceguids
0x14000979f  call    WPP_SF_ss
0x1400097a4  lea     rbp, gFECLog2
0x1400097ab  xor     edx, edx; Val
0x1400097ad  mov     rcx, rbp; void *
0x1400097b0  mov     r8d, 81h; Size
0x1400097b6  mov     bl, 1
0x1400097b8  call    memset
0x1400097bd  xor     ecx, ecx
0x1400097bf  movzx   eax, bl
0x1400097c2  add     bl, bl
0x1400097c4  mov     [rax+rbp], cl
0x1400097c7  inc     ecx
0x1400097c9  cmp     ecx, 8
0x1400097cc  jl      short loc_1400097BF
0x1400097ce  lea     r14, gFECLog
0x1400097d5  xor     edx, edx; Val
0x1400097d7  mov     rcx, r14; void *
0x1400097da  mov     r8d, 400h; Size
0x1400097e0  call    memset
0x1400097e5  lea     rbx, gFECExp
0x1400097ec  xor     edx, edx; Val
0x1400097ee  mov     rcx, rbx; void *
0x1400097f1  mov     r8d, 1FEh; Size
0x1400097f7  call    memset
0x1400097fc  mov     cl, 1
0x1400097fe  xor     edx, edx
0x140009800  movzx   eax, cl
0x140009803  mov     [rdx+rbx], cl
0x140009806  mov     [r14+rax*4], edx
0x14000980a  cmp     byte ptr [rdx+rdi], 31h ; '1'
0x14000980e  jnz     short loc_140009816
0x140009810  xor     cs:byte_140022268, cl
0x140009816  inc     edx
0x140009818  add     cl, cl
0x14000981a  cmp     edx, 8
0x14000981d  jl      short loc_140009800
0x14000981f  movzx   eax, cs:byte_140022268
0x140009826  mov     edx, 9
0x14000982b  mov     r9d, 0FFh
0x140009831  mov     dword ptr [r14+rax*4], 8
0x140009839  mov     r8d, edx
0x14000983c  mov     al, [r8+rbx-1]
0x140009841  mov     cl, al
0x140009843  add     cl, cl
0x140009845  cmp     al, 80h
0x140009847  jb      short loc_14000984F
0x140009849  xor     cl, cs:byte_140022268
0x14000984f  movzx   eax, cl
0x140009852  mov     [r8+rbx], cl
0x140009856  mov     [r14+rax*4], edx
0x14000985a  inc     edx
0x14000985c  cmp     edx, r9d
0x14000985f  jl      short loc_140009839
0x140009861  mov     cs:gFECLog, r9d
0x140009868  xor     ecx, ecx
0x14000986a  mov     al, [rcx+rbx]
0x14000986d  mov     [rcx+rbx+0FFh], al
0x140009874  inc     rcx
0x140009877  cmp     rcx, r9
0x14000987a  jnz     short loc_14000986A
0x14000987c  mov     cs:gFECInverse, 100h
0x140009885  mov     ecx, 2
0x14000988a  mov     edi, 100h
0x14000988f  mov     eax, r9d
0x140009892  lea     rdx, gFECInverse
0x140009899  sub     eax, [r14+rcx*4]
0x14000989d  cdqe
0x14000989f  mov     al, [rax+rbx]
0x1400098a2  mov     [rcx+rdx], al
0x1400098a5  inc     rcx
0x1400098a8  cmp     rcx, rdi
0x1400098ab  jnz     short loc_14000988F
0x1400098ad  xor     r8d, r8d
0x1400098b0  lea     rbp, gFECMultTable
0x1400098b7  mov     r11d, [r14+r8*4]
0x1400098bb  mov     r9, r8
0x1400098be  shl     r9, 8
0x1400098c2  add     r9, rbp
0x1400098c5  xor     r10d, r10d
0x1400098c8  mov     ecx, [r14+r10*4]
0x1400098cc  add     ecx, r11d
0x1400098cf  call    ModNN
0x1400098d4  movzx   eax, al
0x1400098d7  mov     al, [rax+rbx]
0x1400098da  mov     [r9+r10], al
0x1400098de  inc     r10
0x1400098e1  cmp     r10, rdi
0x1400098e4  jnz     short loc_1400098C8
0x1400098e6  inc     r8
0x1400098e9  cmp     r8, rdi
0x1400098ec  jnz     short loc_1400098B7
0x1400098ee  xor     ecx, ecx
0x1400098f0  mov     rax, rcx
0x1400098f3  shl     rax, 8
0x1400098f7  mov     byte ptr [rax+rbp], 0
0x1400098fb  mov     byte ptr [rcx+rbp], 0
0x1400098ff  inc     rcx
0x140009902  cmp     rcx, rdi
0x140009905  jnz     short loc_1400098F0
0x140009907  xor     eax, eax
0x140009909  add     rsp, 38h
0x14000990d  pop     r14
0x14000990f  pop     rdi
0x140009910  pop     rbp
0x140009911  pop     rbx
0x140009912  retn
```
