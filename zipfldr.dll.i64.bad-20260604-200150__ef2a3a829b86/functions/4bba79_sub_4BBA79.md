# sub_4BBA79

- ea: `0x4bba79`
- end: `0x4bba9a`
- name: `sub_4BBA79`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_4BBA79(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        _DWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        __int64 a27,
        __int64 a28,
        __int64 a29,
        __int64 a30,
        __int64 a31,
        __int64 a32,
        __int64 a33,
        __int64 a34,
        __int64 a35,
        __int64 a36,
        __int64 a37,
        __int64 a38,
        __int64 a39,
        __int64 a40,
        __int64 a41,
        __int64 a42,
        __int64 a43,
        __int64 a44,
        __int64 a45,
        __int64 a46,
        __int64 a47,
        __int64 a48,
        __int64 a49,
        __int64 a50,
        __int64 a51,
        __int64 a52,
        __int64 a53,
        __int64 a54,
        __int64 a55)
{
  _DWORD *v55; // rax
  bool v56; // cf

  LOBYTE(v55) = *(_BYTE *)v55 + (_BYTE)v55;
  v56 = __CFADD__((_DWORD)v55, *v55);
  *v55 += (_DWORD)v55;
  *a3 += (_DWORD)v55 + v56;
  BYTE1(v55) += (_BYTE)a3;
  *a4 |= (unsigned int)v55;
  *(_BYTE *)a4 += (_BYTE)a3;
  v56 = __CFADD__(*(_BYTE *)v55, (_BYTE)v55);
  LOBYTE(v55) = *(_BYTE *)v55 + (_BYTE)v55;
  *a3 += (_DWORD)v55 + v56;
}

```

## disassembly

```asm
0x4bba79  add     al, [rax]
0x4bba7b  fcmovnbe st, st
0x4bba7d  add     [rax], eax
0x4bba7f  adc     [rdx], eax
0x4bba81  add     ah, dl
0x4bba83  or      [rcx], eax
0x4bba85  add     [rcx], dl
0x4bba87  add     al, [rax]
0x4bba89  enter   156h, 0
0x4bba8d  adc     [rdx], eax
0x4bba8f  add     bh, al
0x4bba91  imul    eax, [rcx], 21100h
0x4bba97  retn    183h
```
