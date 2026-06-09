# sub_C3F1C5

- ea: `0xc3f1c5`
- end: `0xc3f1e4`
- name: `sub_C3F1C5`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall __noreturn sub_C3F1C5(__int64 a1, __int64 a2, _DWORD *a3, _BYTE *a4)
{
  _DWORD *v4; // rax

  *a4 += (_BYTE)v4;
  *v4 += (_DWORD)v4;
  *v4 += (_DWORD)v4;
  *a3 += (_DWORD)v4;
  BYTE1(a3) += BYTE1(a4);
  __debugbreak();
  *v4 += (_DWORD)v4;
  *(_DWORD *)a4 += (_DWORD)v4;
  *(_BYTE *)v4 += BYTE1(a3);
  *v4 += (_DWORD)v4;
  *a3 += (_DWORD)v4;
  LOBYTE(v4) = (unsigned __int8)v4 & 1;
  *a4 += (_BYTE)v4;
  *v4 += (_DWORD)v4;
  __halt();
}

```

## disassembly

```asm
0xc3f1c5  add     [rcx], al
0xc3f1c7  add     [rax], eax
0xc3f1c9  cld
0xc3f1ca  add     [rax], eax
0xc3f1cc  add     [rdx], eax
0xc3f1ce  add     dh, ch
0xc3f1d0  int     3; Trap to Debugger
0xc3f1d1  add     [rax], eax
0xc3f1d3  add     [rcx], eax
0xc3f1d5  add     [rax], dh
0xc3f1d7  add     [rax], eax
0xc3f1d9  add     [rdx], eax
0xc3f1db  add     dh, ch
0xc3f1dd  and     al, 1
0xc3f1df  add     [rcx], al
0xc3f1e1  add     [rax], eax
0xc3f1e3  hlt
```
