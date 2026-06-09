# WinNatAllocatePort

- ea: `0x14000c03c`
- end: `0x14000c22a`
- name: `WinNatAllocatePort`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008a7c`

## callees

- `0x14000c03c`
- `0x14000caa0`
- `0x14001a040`

## import_xrefs

- `ntoskrnl!RtlSetBits` at `0x14000c1c4`
- `ntoskrnl!RtlSetBits` at `0x14000c1c4`
- `ntoskrnl!RtlFindClearBitsAndSet` at `0x14000c1ed`
- `ntoskrnl!RtlFindClearBitsAndSet` at `0x14000c1ed`
- `ntoskrnl!RtlFindClearBits` at `0x14000c130`
- `ntoskrnl!RtlFindClearBits` at `0x14000c130`
- `NETIO!RtlCompute37Hash` at `0x14000c0ce`
- `NETIO!RtlCompute37Hash` at `0x14000c0e2`
- `NETIO!RtlCompute37Hash` at `0x14000c0ce`
- `NETIO!RtlCompute37Hash` at `0x14000c0e2`

## pseudocode

```c
__int64 __fastcall WinNatAllocatePort(__int64 a1, struct _RTL_BITMAP *a2, _WORD *a3, char a4)
{
  _WORD *v4; // rsi
  unsigned __int16 v7; // r12
  ULONG ClearBitsAndSet; // ebx
  _WORD *v11; // rdx
  ULONG v12; // r14d
  __int64 v13; // r8
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned __int16 v16; // cx
  int v17; // r9d
  ULONG v18; // edx
  bool i; // r15
  ULONG ClearBits; // eax
  unsigned __int16 v21; // si
  __int64 v22; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  char v28; // [rsp+88h] [rbp+20h]

  v4 = a3 + 1;
  v7 = __ROR2__(a3[1], 8);
  if ( a4 == 1 || a4 == 58 )
  {
    ClearBitsAndSet = RtlFindClearBitsAndSet(a2, 1u, *(unsigned __int16 *)(a1 + 104));
    if ( ClearBitsAndSet == -1 )
    {
      LOWORD(ClearBitsAndSet) = 0;
    }
    else
    {
      if ( ClearBitsAndSet > 0xFFFF )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v25, v24, v26, v27);
      *(_WORD *)(a1 + 104) = ClearBitsAndSet;
    }
    return (unsigned __int16)ClearBitsAndSet;
  }
  LOWORD(ClearBitsAndSet) = 0;
  if ( !*(_BYTE *)(a1 + 206) )
    goto LABEL_9;
  if ( a4 != 6 )
  {
    if ( a4 == 17 && *(_BYTE *)(a1 + 207) )
      return (unsigned __int16)ClearBitsAndSet;
    goto LABEL_9;
  }
  if ( *(_BYTE *)(a1 + 207) )
  {
LABEL_9:
    v28 = 0;
    v11 = a3 + 2;
    v12 = 0;
    v13 = 4;
    if ( *a3 != 2 )
      v13 = 16;
    v14 = RtlCompute37Hash(0, v11, v13);
    v15 = RtlCompute37Hash(v14, v4, 2);
    v16 = *(_WORD *)(a1 + 108);
    if ( v7 <= 0x3FFu && *(_WORD *)(a1 + 106) <= 0x3FFu && v16 > 0x3FFu )
      v16 = 1023;
    v17 = *(unsigned __int16 *)(a1 + 106);
    v18 = v17 + v15 % ((unsigned int)v16 - v17 + 1);
    for ( i = v18 != v17; ; i = 0 )
    {
      while ( 1 )
      {
        ClearBits = RtlFindClearBits(a2, 1u, v18);
        v21 = ClearBits;
        if ( ClearBits == -1 )
          return (unsigned __int16)ClearBitsAndSet;
        if ( v28 )
          goto LABEL_34;
        if ( (((unsigned __int8)v7 ^ (unsigned __int8)ClearBits) & 1) == 0 )
          break;
        v18 = ClearBits + 1;
LABEL_28:
        if ( v12 )
        {
          if ( v12 >= ClearBits )
          {
            if ( i )
            {
              v18 = *(unsigned __int16 *)(a1 + 106);
              goto LABEL_24;
            }
            v28 = 1;
            v18 = 0;
          }
        }
        else
        {
          v12 = ClearBits;
        }
      }
      if ( v7 > 0x3FFu )
      {
        if ( ClearBits > 0x3FF )
          goto LABEL_34;
        v18 = 1024;
        goto LABEL_28;
      }
      if ( !i || ClearBits <= 0x3FF || *(_WORD *)(a1 + 106) > 0x3FFu )
      {
LABEL_34:
        RtlSetBits(a2, ClearBits, 1u);
        LOBYTE(v22) = a4;
        WinNatIncrementPortUsage(v22, a1);
        return v21;
      }
      v18 = *(unsigned __int16 *)(a1 + 106);
LABEL_24:
      v12 = 0;
    }
  }
  return (unsigned __int16)ClearBitsAndSet;
}

```

## disassembly

```asm
0x14000c03c  push    rbx
0x14000c03e  push    rbp
0x14000c03f  push    rsi
0x14000c040  push    rdi
0x14000c041  push    r12
0x14000c043  push    r13
0x14000c045  push    r14
0x14000c047  push    r15
0x14000c049  sub     rsp, 28h
0x14000c04d  lea     rsi, [r8+2]
0x14000c051  mov     bpl, r9b
0x14000c054  movzx   r12d, word ptr [rsi]
0x14000c058  mov     rax, r8
0x14000c05b  ror     r12w, 8
0x14000c060  mov     r13, rdx
0x14000c063  mov     rdi, rcx
0x14000c066  cmp     r9b, 1
0x14000c06a  jz      loc_14000C1E0
0x14000c070  cmp     r9b, 3Ah ; ':'
0x14000c074  jz      loc_14000C1E0
0x14000c07a  xor     ebx, ebx
0x14000c07c  cmp     [rcx+0CEh], bl
0x14000c082  jz      short loc_14000C0A9
0x14000c084  cmp     r9b, 6
0x14000c088  jnz     short loc_14000C097
0x14000c08a  cmp     [rcx+0CFh], bl
0x14000c090  jnz     short loc_14000C0A9
0x14000c092  jmp     loc_14000C215
0x14000c097  cmp     bpl, 11h
0x14000c09b  jnz     short loc_14000C0A9
0x14000c09d  cmp     [rcx+0CFh], bl
0x14000c0a3  jnz     loc_14000C215
0x14000c0a9  mov     ecx, 10h
0x14000c0ae  mov     [rsp+68h+arg_18], bl
0x14000c0b5  lea     rdx, [rax+4]
0x14000c0b9  mov     r14d, ebx
0x14000c0bc  lea     r15d, [rcx-0Eh]
0x14000c0c0  cmp     [rax], r15w
0x14000c0c4  lea     r8d, [rcx-0Ch]
0x14000c0c8  cmovnz  r8d, ecx
0x14000c0cc  xor     ecx, ecx
0x14000c0ce  call    cs:__imp_RtlCompute37Hash
0x14000c0d5  nop     dword ptr [rax+rax+00h]
0x14000c0da  mov     r8d, r15d
0x14000c0dd  mov     rdx, rsi
0x14000c0e0  mov     ecx, eax
0x14000c0e2  call    cs:__imp_RtlCompute37Hash
0x14000c0e9  nop     dword ptr [rax+rax+00h]
0x14000c0ee  movzx   ecx, word ptr [rdi+6Ch]
0x14000c0f2  mov     edx, 3FFh
0x14000c0f7  cmp     r12w, dx
0x14000c0fb  ja      short loc_14000C10A
0x14000c0fd  cmp     [rdi+6Ah], dx
0x14000c101  ja      short loc_14000C10A
0x14000c103  cmp     cx, dx
0x14000c106  jbe     short loc_14000C10A
0x14000c108  mov     ecx, edx
0x14000c10a  movzx   r9d, word ptr [rdi+6Ah]
0x14000c10f  xor     edx, edx
0x14000c111  movzx   ecx, cx
0x14000c114  sub     ecx, r9d
0x14000c117  inc     ecx
0x14000c119  div     ecx
0x14000c11b  add     edx, r9d
0x14000c11e  cmp     edx, r9d
0x14000c121  setnz   r15b
0x14000c125  mov     r8d, edx; HintIndex
0x14000c128  mov     rcx, r13; BitMapHeader
0x14000c12b  mov     edx, 1; NumberToFind
0x14000c130  call    cs:__imp_RtlFindClearBits
0x14000c137  nop     dword ptr [rax+rax+00h]
0x14000c13c  mov     esi, eax
0x14000c13e  cmp     eax, 0FFFFFFFFh
0x14000c141  jz      loc_14000C215
0x14000c147  cmp     [rsp+68h+arg_18], bl
0x14000c14e  jnz     short loc_14000C1B9
0x14000c150  mov     cl, sil
0x14000c153  xor     cl, r12b
0x14000c156  test    cl, 1
0x14000c159  jnz     short loc_14000C18D
0x14000c15b  mov     ecx, 3FFh
0x14000c160  cmp     r12w, cx
0x14000c164  ja      short loc_14000C182
0x14000c166  test    r15b, r15b
0x14000c169  jz      short loc_14000C1B9
0x14000c16b  cmp     eax, ecx
0x14000c16d  jbe     short loc_14000C1B9
0x14000c16f  movzx   eax, word ptr [rdi+6Ah]
0x14000c173  cmp     ax, cx
0x14000c176  ja      short loc_14000C1B9
0x14000c178  mov     edx, eax
0x14000c17a  mov     r15b, bl
0x14000c17d  mov     r14d, ebx
0x14000c180  jmp     short loc_14000C125
0x14000c182  cmp     esi, ecx
0x14000c184  ja      short loc_14000C1B9
0x14000c186  mov     edx, 400h
0x14000c18b  jmp     short loc_14000C190
0x14000c18d  lea     edx, [rax+1]
0x14000c190  test    r14d, r14d
0x14000c193  jnz     short loc_14000C19A
0x14000c195  mov     r14d, esi
0x14000c198  jmp     short loc_14000C125
0x14000c19a  cmp     r14d, esi
0x14000c19d  jb      short loc_14000C125
0x14000c19f  test    r15b, r15b
0x14000c1a2  jz      short loc_14000C1AA
0x14000c1a4  movzx   edx, word ptr [rdi+6Ah]
0x14000c1a8  jmp     short loc_14000C17A
0x14000c1aa  mov     [rsp+68h+arg_18], 1
0x14000c1b2  mov     edx, ebx
0x14000c1b4  jmp     loc_14000C125
0x14000c1b9  mov     r8d, 1; NumberToSet
0x14000c1bf  mov     edx, esi; StartingIndex
0x14000c1c1  mov     rcx, r13; BitMapHeader
0x14000c1c4  call    cs:__imp_RtlSetBits
0x14000c1cb  nop     dword ptr [rax+rax+00h]
0x14000c1d0  mov     rdx, rdi
0x14000c1d3  mov     cl, bpl
0x14000c1d6  call    WinNatIncrementPortUsage
0x14000c1db  movzx   eax, si
0x14000c1de  jmp     short loc_14000C218
0x14000c1e0  movzx   r8d, word ptr [rcx+68h]; HintIndex
0x14000c1e5  mov     edx, 1; NumberToFind
0x14000c1ea  mov     rcx, r13; BitMapHeader
0x14000c1ed  call    cs:__imp_RtlFindClearBitsAndSet
0x14000c1f4  nop     dword ptr [rax+rax+00h]
0x14000c1f9  mov     ebx, eax
0x14000c1fb  cmp     eax, 0FFFFFFFFh
0x14000c1fe  jnz     short loc_14000C204
0x14000c200  xor     ebx, ebx
0x14000c202  jmp     short loc_14000C215
0x14000c204  cmp     ebx, 0FFFFh
0x14000c20a  jbe     short loc_14000C211
0x14000c20c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000c211  mov     [rdi+68h], bx
0x14000c215  movzx   eax, bx
0x14000c218  add     rsp, 28h
0x14000c21c  pop     r15
0x14000c21e  pop     r14
0x14000c220  pop     r13
0x14000c222  pop     r12
0x14000c224  pop     rdi
0x14000c225  pop     rsi
0x14000c226  pop     rbp
0x14000c227  pop     rbx
0x14000c228  retn
```
