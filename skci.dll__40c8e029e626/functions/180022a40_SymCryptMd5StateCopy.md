# SymCryptMd5StateCopy

- ea: `0x180022a40`
- end: `0x180022a77`
- name: `SymCryptMd5StateCopy`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall SymCryptMd5StateCopy(_OWORD *a1, _OWORD *a2)
{
  *a2 = *a1;
  a2[1] = a1[1];
  a2[2] = a1[2];
  a2[3] = a1[3];
  a2[4] = a1[4];
  a2[5] = a1[5];
  a2[6] = a1[6];
}

```

## disassembly

```asm
0x180022a40  movaps  xmm0, xmmword ptr [rcx]
0x180022a43  movaps  xmmword ptr [rdx], xmm0
0x180022a46  movaps  xmm1, xmmword ptr [rcx+10h]
0x180022a4a  movaps  xmmword ptr [rdx+10h], xmm1
0x180022a4e  movaps  xmm0, xmmword ptr [rcx+20h]
0x180022a52  movaps  xmmword ptr [rdx+20h], xmm0
0x180022a56  movaps  xmm1, xmmword ptr [rcx+30h]
0x180022a5a  movaps  xmmword ptr [rdx+30h], xmm1
0x180022a5e  movaps  xmm0, xmmword ptr [rcx+40h]
0x180022a62  movaps  xmmword ptr [rdx+40h], xmm0
0x180022a66  movaps  xmm1, xmmword ptr [rcx+50h]
0x180022a6a  movaps  xmmword ptr [rdx+50h], xmm1
0x180022a6e  movaps  xmm0, xmmword ptr [rcx+60h]
0x180022a72  movaps  xmmword ptr [rdx+60h], xmm0
0x180022a76  retn
```
