# _tlgCreate1Sz_char

- ea: `0x140001008`
- end: `0x140001038`
- name: `_tlgCreate1Sz_char`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140010d50`

## callees

- `0x140001008`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_char(__int64 a1, int *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( *((_BYTE *)a2 + v2) );
    result = (unsigned int)(v2 + 1);
  }
  else
  {
    a2 = &dword_1400147C4;
    result = 1;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x140001008  test    rdx, rdx
0x14000100b  jz      short loc_14000101E
0x14000100d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001011  inc     rax
0x140001014  cmp     byte ptr [rdx+rax], 0
0x140001018  jnz     short loc_140001011
0x14000101a  inc     eax
0x14000101c  jmp     short loc_14000102A
0x14000101e  lea     rdx, dword_1400147C4
0x140001025  mov     eax, 1
0x14000102a  mov     [rcx], rdx
0x14000102d  mov     [rcx+8], eax
0x140001030  mov     dword ptr [rcx+0Ch], 0
0x140001037  retn
```
