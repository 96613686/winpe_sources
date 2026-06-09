# CMcTpOptions::ParseOptions<CMcTpPacket>(CMcTpPacket *,_WDSMCTP_OPTIONS *,ulong)

- ea: `0x1800200e0`
- end: `0x180020251`
- name: `??$ParseOptions@VCMcTpPacket@@@CMcTpOptions@@SAKPEAVCMcTpPacket@@PEAU_WDSMCTP_OPTIONS@@K@Z`
- size: `369`
- prototype: `__int64 __fastcall(CMcTpPacket *this, u_short *, unsigned int)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ed10`
- `0x18001eed0`
- `0x18001ef8c`
- `0x18001f148`
- `0x18001f25c`
- `0x18001f414`
- `0x18001f538`
- `0x18001f658`
- `0x18001f714`
- `0x18001f870`
- `0x18001f9b0`
- `0x18001faf0`
- `0x18001fbec`
- `0x18001fd14`
- `0x18001fe54`

## callees

- `0x18001ec1c`
- `0x1800200e0`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x180020121`
- `WS2_32!__imp_ntohs` at `0x180020159`
- `WS2_32!__imp_ntohs` at `0x180020166`
- `WS2_32!__imp_ntohs` at `0x180020121`
- `WS2_32!__imp_ntohs` at `0x180020159`
- `WS2_32!__imp_ntohs` at `0x180020166`

## pseudocode

```c
__int64 __fastcall CMcTpOptions::ParseOptions<CMcTpPacket>(CMcTpPacket *this, u_short *a2, unsigned int a3)
{
  unsigned int v6; // ebx
  u_short v7; // bp
  u_short *v8; // rsi
  unsigned int v9; // edi
  __int16 v10; // r14
  u_short v11; // bx
  u_short v12; // r8
  unsigned int v13; // r15d
  bool v14; // zf
  __int16 v15; // cx
  unsigned int v16; // eax

  v6 = 0;
  if ( a3 >= 2 )
  {
    v7 = ntohs(*a2);
    if ( !v7 )
      return v6;
    if ( a3 >= 7 )
    {
      v8 = a2 + 1;
      v9 = a3 - 2;
      v10 = 0;
      while ( 1 )
      {
        if ( v9 < 4 )
          return 13;
        v11 = ntohs(*v8);
        v12 = ntohs(v8[1]);
        v13 = v12 + 4;
        if ( v9 < v13 )
          return 13;
        if ( HIBYTE(v11) == 1 )
        {
          v15 = 1;
          goto LABEL_21;
        }
        if ( HIBYTE(v11) == 2 )
          break;
        if ( HIBYTE(v11) == 3 )
        {
          v15 = 4;
LABEL_21:
          v14 = v12 == (u_short)v15;
          goto LABEL_22;
        }
        if ( HIBYTE(v11) != 4 )
        {
          if ( HIBYTE(v11) == 6 && (!v12 || (v12 & 1) != 0 || v8[(v12 >> 1) + 1]) )
            return 13;
          goto LABEL_23;
        }
        v14 = v12 == 8;
LABEL_22:
        if ( !v14 )
          return 13;
LABEL_23:
        v6 = CMcTpPacket::ParseOption(this, v11, v12, v8 + 2);
        if ( v6 )
          return v6;
        v9 -= v13;
        v8 = (u_short *)((char *)v8 + v13);
        if ( (unsigned __int16)++v10 >= v7 )
        {
          v16 = 0;
          if ( v9 )
            return 13;
          return v16;
        }
      }
      v15 = 2;
      goto LABEL_21;
    }
  }
  return 13;
}

```

## disassembly

```asm
0x1800200e0  mov     [rsp+arg_0], rbx
0x1800200e5  mov     [rsp+arg_8], rbp
0x1800200ea  mov     [rsp+arg_10], rsi
0x1800200ef  push    rdi
0x1800200f0  push    r12
0x1800200f2  push    r13
0x1800200f4  push    r14
0x1800200f6  push    r15
0x1800200f8  sub     rsp, 20h
0x1800200fc  xor     r13d, r13d
0x1800200ff  mov     edi, r8d
0x180020102  mov     rsi, rdx
0x180020105  mov     r12, rcx
0x180020108  mov     ebx, r13d
0x18002010b  lea     eax, [r13+2]
0x18002010f  cmp     r8d, eax
0x180020112  jnb     short loc_18002011E
0x180020114  mov     ebx, 0Dh
0x180020119  jmp     loc_180020232
0x18002011e  movzx   ecx, word ptr [rdx]; netshort
0x180020121  call    cs:__imp_ntohs
0x180020127  movzx   ebp, ax
0x18002012a  test    ax, ax
0x18002012d  jz      loc_180020232
0x180020133  cmp     edi, 7
0x180020136  jb      short loc_180020114
0x180020138  add     rsi, 2
0x18002013c  add     edi, 0FFFFFFFEh
0x18002013f  movzx   r14d, r13w
0x180020143  cmp     r13w, ax
0x180020147  jnb     loc_180020224
0x18002014d  mov     ecx, 4
0x180020152  cmp     edi, ecx
0x180020154  jb      short loc_180020114
0x180020156  movzx   ecx, word ptr [rsi]; netshort
0x180020159  call    cs:__imp_ntohs
0x18002015f  movzx   ecx, word ptr [rsi+2]; netshort
0x180020163  movzx   ebx, ax
0x180020166  call    cs:__imp_ntohs
0x18002016c  movzx   r8d, ax; unsigned __int16
0x180020170  mov     edx, r8d
0x180020173  lea     r15d, [r8+4]
0x180020177  cmp     edi, r15d
0x18002017a  jb      short loc_180020114
0x18002017c  movzx   ecx, bx
0x18002017f  shr     ecx, 8
0x180020182  sub     ecx, 1
0x180020185  jz      short loc_1800201DE
0x180020187  sub     ecx, 1
0x18002018a  jz      short loc_1800201D7
0x18002018c  sub     ecx, 1
0x18002018f  jz      short loc_1800201D0
0x180020191  sub     ecx, 1
0x180020194  jz      short loc_1800201C9
0x180020196  mov     eax, 2
0x18002019b  cmp     ecx, eax
0x18002019d  jnz     short loc_1800201F5
0x18002019f  test    r8w, r8w
0x1800201a3  jz      loc_180020114
0x1800201a9  mov     eax, 1
0x1800201ae  test    al, r8b
0x1800201b1  jnz     loc_180020114
0x1800201b7  shr     edx, 1
0x1800201b9  sub     edx, eax
0x1800201bb  cmp     [rsi+rdx*2+4], r13w
0x1800201c1  jnz     loc_180020114
0x1800201c7  jmp     short loc_1800201F5
0x1800201c9  cmp     r8w, 8
0x1800201ce  jmp     short loc_1800201E7
0x1800201d0  mov     ecx, 4
0x1800201d5  jmp     short loc_1800201E3
0x1800201d7  mov     ecx, 2
0x1800201dc  jmp     short loc_1800201E3
0x1800201de  mov     ecx, 1
0x1800201e3  cmp     r8w, cx
0x1800201e7  mov     eax, r13d
0x1800201ea  setz    al
0x1800201ed  test    eax, eax
0x1800201ef  jz      loc_180020114
0x1800201f5  lea     r9, [rsi+4]; void *
0x1800201f9  movzx   edx, bx; unsigned __int16
0x1800201fc  mov     rcx, r12; this
0x1800201ff  call    ?ParseOption@CMcTpPacket@@QEAAKGGPEAX@Z; CMcTpPacket::ParseOption(ushort,ushort,void *)
0x180020204  mov     ebx, eax
0x180020206  test    eax, eax
0x180020208  jnz     short loc_180020232
0x18002020a  mov     ecx, r15d
0x18002020d  sub     edi, r15d
0x180020210  add     rsi, rcx
0x180020213  inc     r14w
0x180020217  lea     ecx, [rax+4]
0x18002021a  cmp     r14w, bp
0x18002021e  jb      loc_180020152
0x180020224  mov     eax, ebx
0x180020226  test    edi, edi
0x180020228  mov     ebx, 0Dh
0x18002022d  cmovnz  eax, ebx
0x180020230  mov     ebx, eax
0x180020232  mov     rbp, [rsp+48h+arg_8]
0x180020237  mov     eax, ebx
0x180020239  mov     rbx, [rsp+48h+arg_0]
0x18002023e  mov     rsi, [rsp+48h+arg_10]
0x180020243  add     rsp, 20h
0x180020247  pop     r15
0x180020249  pop     r14
0x18002024b  pop     r13
0x18002024d  pop     r12
0x18002024f  pop     rdi
0x180020250  retn
```
