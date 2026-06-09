# CSmHashTable<PacketVariable,CNoLock,113>::RemoveItem<ushort const *>(ulong,ushort const *)

- ea: `0x18000bfcc`
- end: `0x18000c0d6`
- name: `??$RemoveItem@PEBG@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@QEAAPEAUPacketVariable@@KPEBG@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d320`

## callees

- `0x18000bfcc`

## pseudocode

```c
unsigned __int16 *__fastcall CSmHashTable<PacketVariable,CNoLock,113>::RemoveItem<unsigned short const *>(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v6; // r10
  __int64 v7; // r8
  unsigned __int16 *v8; // rcx
  unsigned __int16 *v9; // rdx
  unsigned __int16 *v10; // rax
  int v11; // edi
  int v12; // r11d
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax

  v6 = 0;
  v7 = 3LL * (a2 % 0x71);
  v8 = *(unsigned __int16 **)(a1 + 24LL * (a2 % 0x71) + 8);
  if ( v8 )
  {
    v9 = v8;
    while ( 1 )
    {
      if ( *((_DWORD *)v9 + 28) == a2 )
      {
        v10 = v9;
        do
        {
          v11 = *(unsigned __int16 *)((char *)v10 + a3 - (_QWORD)v9);
          v12 = *v10 - v11;
          if ( v12 )
            break;
          ++v10;
        }
        while ( v11 );
        if ( !v12 )
          break;
      }
      v9 = (unsigned __int16 *)*((_QWORD *)v9 + 12);
      if ( !v9 )
        return (unsigned __int16 *)v6;
    }
    v13 = *(_QWORD *)(a1 + 8 * v7 + 16);
    if ( v8 == (unsigned __int16 *)v13 )
    {
      *(_QWORD *)(a1 + 8 * v7 + 16) = 0;
      *(_QWORD *)(a1 + 8 * v7 + 8) = 0;
    }
    else if ( v9 == v8 )
    {
      v14 = *((_QWORD *)v8 + 12);
      *(_QWORD *)(a1 + 8 * v7 + 8) = v14;
      *(_QWORD *)(v14 + 104) = 0;
    }
    else if ( v9 == (unsigned __int16 *)v13 )
    {
      v15 = *(_QWORD *)(v13 + 104);
      *(_QWORD *)(a1 + 8 * v7 + 16) = v15;
      *(_QWORD *)(v15 + 96) = 0;
    }
    else
    {
      *(_QWORD *)(*((_QWORD *)v9 + 13) + 96LL) = *((_QWORD *)v9 + 12);
      *(_QWORD *)(*((_QWORD *)v9 + 12) + 104LL) = *((_QWORD *)v9 + 13);
    }
    --*(_DWORD *)(a1 + 8 * v7 + 28);
    --*(_DWORD *)(a1 + 2720);
    return v9;
  }
  return (unsigned __int16 *)v6;
}

```

## disassembly

```asm
0x18000bfcc  mov     rax, rsp
0x18000bfcf  mov     [rax+8], rbx
0x18000bfd3  mov     [rax+10h], rbp
0x18000bfd7  mov     [rax+18h], rsi
0x18000bfdb  mov     [rax+20h], rdi
0x18000bfdf  mov     esi, edx
0x18000bfe1  mov     r9, rcx
0x18000bfe4  mov     ecx, esi
0x18000bfe6  mov     eax, 21FB7813h
0x18000bfeb  mul     edx
0x18000bfed  mov     eax, esi
0x18000bfef  mov     rbp, r8
0x18000bff2  sub     eax, edx
0x18000bff4  xor     r10d, r10d
0x18000bff7  shr     eax, 1
0x18000bff9  add     eax, edx
0x18000bffb  shr     eax, 6
0x18000bffe  imul    eax, 71h ; 'q'
0x18000c001  sub     ecx, eax
0x18000c003  lea     r8, [rcx+rcx*2]
0x18000c007  mov     rcx, [r9+r8*8+8]
0x18000c00c  test    rcx, rcx
0x18000c00f  jz      loc_18000C0BD
0x18000c015  mov     rdx, rcx
0x18000c018  cmp     [rdx+70h], esi
0x18000c01b  jnz     short loc_18000C040
0x18000c01d  mov     rbx, rbp
0x18000c020  mov     rax, rdx
0x18000c023  sub     rbx, rdx
0x18000c026  movzx   r11d, word ptr [rax]
0x18000c02a  movzx   edi, word ptr [rax+rbx]
0x18000c02e  sub     r11d, edi
0x18000c031  jnz     short loc_18000C03B
0x18000c033  add     rax, 2
0x18000c037  test    edi, edi
0x18000c039  jnz     short loc_18000C026
0x18000c03b  test    r11d, r11d
0x18000c03e  jz      short loc_18000C04B
0x18000c040  mov     rdx, [rdx+60h]
0x18000c044  test    rdx, rdx
0x18000c047  jnz     short loc_18000C018
0x18000c049  jmp     short loc_18000C0BD
0x18000c04b  or      r10d, 0FFFFFFFFh
0x18000c04f  test    rdx, rdx
0x18000c052  jz      short loc_18000C0B3
0x18000c054  mov     rax, [r9+r8*8+10h]
0x18000c059  cmp     rcx, rax
0x18000c05c  jnz     short loc_18000C06C
0x18000c05e  and     qword ptr [r9+r8*8+10h], 0
0x18000c064  and     qword ptr [r9+r8*8+8], 0
0x18000c06a  jmp     short loc_18000C0AE
0x18000c06c  cmp     rdx, rcx
0x18000c06f  jnz     short loc_18000C081
0x18000c071  mov     rax, [rcx+60h]
0x18000c075  mov     [r9+r8*8+8], rax
0x18000c07a  and     qword ptr [rax+68h], 0
0x18000c07f  jmp     short loc_18000C0AE
0x18000c081  cmp     rdx, rax
0x18000c084  jnz     short loc_18000C096
0x18000c086  mov     rax, [rax+68h]
0x18000c08a  mov     [r9+r8*8+10h], rax
0x18000c08f  and     qword ptr [rax+60h], 0
0x18000c094  jmp     short loc_18000C0AE
0x18000c096  mov     rcx, [rdx+68h]
0x18000c09a  mov     rax, [rdx+60h]
0x18000c09e  mov     [rcx+60h], rax
0x18000c0a2  mov     rcx, [rdx+60h]
0x18000c0a6  mov     rax, [rdx+68h]
0x18000c0aa  mov     [rcx+68h], rax
0x18000c0ae  add     [r9+r8*8+1Ch], r10d
0x18000c0b3  add     [r9+0AA0h], r10d
0x18000c0ba  mov     r10, rdx
0x18000c0bd  mov     rbx, [rsp+arg_0]
0x18000c0c2  mov     rax, r10
0x18000c0c5  mov     rbp, [rsp+arg_8]
0x18000c0ca  mov     rsi, [rsp+arg_10]
0x18000c0cf  mov     rdi, [rsp+arg_18]
0x18000c0d4  retn
```
