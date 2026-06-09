# SymCryptSha256StateCopy

- ea: `0x180013d60`
- end: `0x180013d9f`
- name: `SymCryptSha256StateCopy`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall SymCryptSha256StateCopy(_OWORD *a1, _OWORD *a2)
{
  *a2 = *a1;
  a2[1] = a1[1];
  a2[2] = a1[2];
  a2[3] = a1[3];
  a2[4] = a1[4];
  a2[5] = a1[5];
  a2[6] = a1[6];
  a2[7] = a1[7];
}

```

## disassembly

```asm
0x180013d60  movaps  xmm0, xmmword ptr [rcx]
0x180013d63  movaps  xmmword ptr [rdx], xmm0
0x180013d66  movaps  xmm1, xmmword ptr [rcx+10h]
0x180013d6a  movaps  xmmword ptr [rdx+10h], xmm1
0x180013d6e  movaps  xmm0, xmmword ptr [rcx+20h]
0x180013d72  movaps  xmmword ptr [rdx+20h], xmm0
0x180013d76  movaps  xmm1, xmmword ptr [rcx+30h]
0x180013d7a  movaps  xmmword ptr [rdx+30h], xmm1
0x180013d7e  movaps  xmm0, xmmword ptr [rcx+40h]
0x180013d82  movaps  xmmword ptr [rdx+40h], xmm0
0x180013d86  movaps  xmm1, xmmword ptr [rcx+50h]
0x180013d8a  movaps  xmmword ptr [rdx+50h], xmm1
0x180013d8e  movaps  xmm0, xmmword ptr [rcx+60h]
0x180013d92  movaps  xmmword ptr [rdx+60h], xmm0
0x180013d96  movaps  xmm1, xmmword ptr [rcx+70h]
0x180013d9a  movaps  xmmword ptr [rdx+70h], xmm1
0x180013d9e  retn
```
