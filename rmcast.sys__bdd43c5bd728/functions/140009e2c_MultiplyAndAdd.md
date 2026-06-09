# MultiplyAndAdd

- ea: `0x140009e2c`
- end: `0x140009f48`
- name: `MultiplyAndAdd`
- size: `284`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140009500`
- `0x140009630`
- `0x14000991c`

## callees

- `0x140009e2c`

## pseudocode

```c
__int64 *__fastcall MultiplyAndAdd(_BYTE *a1, unsigned __int8 *a2, unsigned __int8 a3, int a4)
{
  _BYTE *v4; // r10
  __int64 *result; // rax
  unsigned __int64 v6; // r9
  __int64 *v7; // r8
  unsigned __int64 v8; // r9

  v4 = a1;
  if ( a3 )
  {
    result = gFECMultTable;
    v6 = (unsigned __int64)&a1[a4 - 15];
    v7 = &gFECMultTable[32 * (unsigned __int64)a3];
    if ( (unsigned __int64)a1 < v6 )
    {
      do
      {
        *v4 ^= *((_BYTE *)v7 + *a2);
        v4[1] ^= *((_BYTE *)v7 + a2[1]);
        v4[2] ^= *((_BYTE *)v7 + a2[2]);
        v4[3] ^= *((_BYTE *)v7 + a2[3]);
        v4[4] ^= *((_BYTE *)v7 + a2[4]);
        v4[5] ^= *((_BYTE *)v7 + a2[5]);
        v4[6] ^= *((_BYTE *)v7 + a2[6]);
        v4[7] ^= *((_BYTE *)v7 + a2[7]);
        v4[8] ^= *((_BYTE *)v7 + a2[8]);
        v4[9] ^= *((_BYTE *)v7 + a2[9]);
        v4[10] ^= *((_BYTE *)v7 + a2[10]);
        v4[11] ^= *((_BYTE *)v7 + a2[11]);
        v4[12] ^= *((_BYTE *)v7 + a2[12]);
        v4[13] ^= *((_BYTE *)v7 + a2[13]);
        v4[14] ^= *((_BYTE *)v7 + a2[14]);
        result = (__int64 *)a2[15];
        a2 += 16;
        v4[15] ^= *((_BYTE *)v7 + (_QWORD)result);
        v4 += 16;
      }
      while ( (unsigned __int64)v4 < v6 );
    }
    v8 = v6 + 15;
    while ( (unsigned __int64)v4 < v8 )
    {
      result = (__int64 *)*a2++;
      *v4++ ^= *((_BYTE *)v7 + (_QWORD)result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140009e2c  mov     r10, rcx
0x140009e2f  test    r8b, r8b
0x140009e32  jz      locret_140009F47
0x140009e38  lea     eax, [r9-0Fh]
0x140009e3c  movzx   r8d, r8b
0x140009e40  movsxd  r9, eax
0x140009e43  lea     rax, gFECMultTable
0x140009e4a  shl     r8, 8
0x140009e4e  add     r9, rcx
0x140009e51  add     r8, rax
0x140009e54  cmp     rcx, r9
0x140009e57  jnb     loc_140009F2C
0x140009e5d  movzx   eax, byte ptr [rdx]
0x140009e60  mov     cl, [rax+r8]
0x140009e64  xor     [r10], cl
0x140009e67  movzx   eax, byte ptr [rdx+1]
0x140009e6b  mov     cl, [rax+r8]
0x140009e6f  xor     [r10+1], cl
0x140009e73  movzx   eax, byte ptr [rdx+2]
0x140009e77  mov     cl, [rax+r8]
0x140009e7b  xor     [r10+2], cl
0x140009e7f  movzx   eax, byte ptr [rdx+3]
0x140009e83  mov     cl, [rax+r8]
0x140009e87  xor     [r10+3], cl
0x140009e8b  movzx   eax, byte ptr [rdx+4]
0x140009e8f  mov     cl, [rax+r8]
0x140009e93  xor     [r10+4], cl
0x140009e97  movzx   eax, byte ptr [rdx+5]
0x140009e9b  mov     cl, [rax+r8]
0x140009e9f  xor     [r10+5], cl
0x140009ea3  movzx   eax, byte ptr [rdx+6]
0x140009ea7  mov     cl, [rax+r8]
0x140009eab  xor     [r10+6], cl
0x140009eaf  movzx   eax, byte ptr [rdx+7]
0x140009eb3  mov     cl, [rax+r8]
0x140009eb7  xor     [r10+7], cl
0x140009ebb  movzx   eax, byte ptr [rdx+8]
0x140009ebf  mov     cl, [rax+r8]
0x140009ec3  xor     [r10+8], cl
0x140009ec7  movzx   eax, byte ptr [rdx+9]
0x140009ecb  mov     cl, [rax+r8]
0x140009ecf  xor     [r10+9], cl
0x140009ed3  movzx   eax, byte ptr [rdx+0Ah]
0x140009ed7  mov     cl, [rax+r8]
0x140009edb  xor     [r10+0Ah], cl
0x140009edf  movzx   eax, byte ptr [rdx+0Bh]
0x140009ee3  mov     cl, [rax+r8]
0x140009ee7  xor     [r10+0Bh], cl
0x140009eeb  movzx   eax, byte ptr [rdx+0Ch]
0x140009eef  mov     cl, [rax+r8]
0x140009ef3  xor     [r10+0Ch], cl
0x140009ef7  movzx   eax, byte ptr [rdx+0Dh]
0x140009efb  mov     cl, [rax+r8]
0x140009eff  xor     [r10+0Dh], cl
0x140009f03  movzx   eax, byte ptr [rdx+0Eh]
0x140009f07  mov     cl, [rax+r8]
0x140009f0b  xor     [r10+0Eh], cl
0x140009f0f  movzx   eax, byte ptr [rdx+0Fh]
0x140009f13  add     rdx, 10h
0x140009f17  mov     cl, [rax+r8]
0x140009f1b  xor     [r10+0Fh], cl
0x140009f1f  add     r10, 10h
0x140009f23  cmp     r10, r9
0x140009f26  jb      loc_140009E5D
0x140009f2c  add     r9, 0Fh
0x140009f30  jmp     short loc_140009F42
0x140009f32  movzx   eax, byte ptr [rdx]
0x140009f35  inc     rdx
0x140009f38  mov     cl, [rax+r8]
0x140009f3c  xor     [r10], cl
0x140009f3f  inc     r10
0x140009f42  cmp     r10, r9
0x140009f45  jb      short loc_140009F32
0x140009f47  retn
```
