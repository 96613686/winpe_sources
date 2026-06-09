# sub_D3FA70

- ea: `0xd3fa70`
- end: `0xd3fa8a`
- name: `sub_D3FA70`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall sub_D3FA70(__int64 a1, __int64 a2, int a3, char a4)
{
  __int64 v4; // rax
  _DWORD *v5; // rbx
  int v6; // edx
  __int64 v7; // rdx
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  MEMORY[0xFFFFFFFF8DD40A79] += BYTE1(v4);
  __sgdt((void *)(v4 + 80));
  v6 = *(_DWORD *)v4 + a3;
  LOBYTE(v4) = BYTE1(v6) + v4;
  v7 = (unsigned int)(*(_DWORD *)v4 + v6);
  *(_BYTE *)(v4 + 15) += a4;
  *(_DWORD *)v4 += v4;
  *(_BYTE *)(unsigned int)*v5 &= *v5;
  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)(a1, a2, v7);
}

```

## disassembly

```asm
0xd3fa70  add     cs:0FFFFFFFF8DD40A79h, ah
0xd3fa76  sgdt    fword ptr [rax+50h]
0xd3fa7a  add     edx, [rax]
0xd3fa7c  add     al, dh
0xd3fa7e  add     edx, [rax]
0xd3fa80  add     [rax+0Fh], cl
0xd3fa83  add     [rax], eax
0xd3fa85  mov     eax, [rbx]
0xd3fa87  and     [rax], al
0xd3fa89  retf
```
