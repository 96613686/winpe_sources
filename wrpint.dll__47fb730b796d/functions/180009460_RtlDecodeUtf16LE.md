# RtlDecodeUtf16LE

- ea: `0x180009460`
- end: `0x1800094eb`
- name: `RtlDecodeUtf16LE`
- size: `139`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007620`
- `0x180007f68`
- `0x180008248`
- `0x180008aac`

## callees

- `0x180009460`

## pseudocode

```c
__int64 __fastcall RtlDecodeUtf16LE(__int64 a1, unsigned __int16 *a2, unsigned __int64 a3)
{
  unsigned __int64 v4; // r8
  int v5; // ecx
  unsigned __int16 *v6; // rdx
  int v7; // r8d
  int v8; // eax

  *(_OWORD *)a1 = 0;
  if ( (unsigned __int64)a2 >= a3 )
    goto LABEL_11;
  v4 = a3 - (_QWORD)a2;
  if ( v4 < 2 )
    goto LABEL_11;
  v5 = *a2;
  v6 = a2 + 1;
  if ( (unsigned __int16)v5 < 0xD800u )
    goto LABEL_9;
  if ( (unsigned __int16)v5 > 0xDBFFu )
  {
    if ( (unsigned __int16)v5 <= 0xDFFFu )
    {
LABEL_11:
      *(_DWORD *)a1 = -1;
      *(_DWORD *)(a1 + 8) = -1073741471;
      return a1;
    }
LABEL_9:
    v8 = v5;
    goto LABEL_10;
  }
  if ( v4 < 4 )
    goto LABEL_11;
  v7 = *v6;
  if ( (unsigned __int16)(v7 + 9216) > 0x3FFu )
    goto LABEL_11;
  ++v6;
  v8 = (v5 << 10) - 56613888 + v7;
LABEL_10:
  *(_DWORD *)a1 = v8;
  *(_QWORD *)(a1 + 8) = v6;
  return a1;
}

```

## disassembly

```asm
0x180009460  xorps   xmm0, xmm0
0x180009463  mov     r9, rcx
0x180009466  movups  xmmword ptr [rcx], xmm0
0x180009469  cmp     rdx, r8
0x18000946c  jnb     short loc_1800094D8
0x18000946e  sub     r8, rdx
0x180009471  cmp     r8, 2
0x180009475  jb      short loc_1800094D8
0x180009477  movzx   ecx, word ptr [rdx]
0x18000947a  mov     eax, 0D800h
0x18000947f  add     rdx, 2
0x180009483  cmp     cx, ax
0x180009486  jb      short loc_1800094CD
0x180009488  mov     eax, 0DBFFh
0x18000948d  cmp     cx, ax
0x180009490  ja      short loc_1800094C3
0x180009492  cmp     r8, 4
0x180009496  jb      short loc_1800094D8
0x180009498  movzx   r8d, word ptr [rdx]
0x18000949c  mov     eax, 2400h
0x1800094a1  add     eax, r8d
0x1800094a4  mov     r10d, 3FFh
0x1800094aa  cmp     ax, r10w
0x1800094ae  ja      short loc_1800094D8
0x1800094b0  add     rdx, 2
0x1800094b4  shl     ecx, 0Ah
0x1800094b7  add     ecx, 0FCA02400h
0x1800094bd  lea     eax, [rcx+r8]
0x1800094c1  jmp     short loc_1800094CF
0x1800094c3  mov     eax, 0DFFFh
0x1800094c8  cmp     cx, ax
0x1800094cb  jbe     short loc_1800094D8
0x1800094cd  mov     eax, ecx
0x1800094cf  mov     [r9], eax
0x1800094d2  mov     [r9+8], rdx
0x1800094d6  jmp     short loc_1800094E7
0x1800094d8  mov     dword ptr [r9], 0FFFFFFFFh
0x1800094df  mov     dword ptr [r9+8], 0C0000161h
0x1800094e7  mov     rax, r9
0x1800094ea  retn
```
