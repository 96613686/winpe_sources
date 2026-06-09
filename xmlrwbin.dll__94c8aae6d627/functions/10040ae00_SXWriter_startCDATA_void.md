# SXWriter::startCDATA(void)

- ea: `0x10040ae00`
- end: `0x10040ae54`
- name: `?startCDATA@SXWriter@@UEAAJXZ`
- size: `84`
- prototype: `__int64 __fastcall(SXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1004086f0`
- `0x10040ae00`

## pseudocode

```c
__int64 __fastcall SXWriter::startCDATA(SXWriter *this)
{
  char *v1; // rbx
  _BYTE *v2; // rax

  v1 = (char *)this - 32;
  *((_WORD *)this + 108) = 257;
  if ( *((_BYTE *)this + 224) )
  {
    v2 = (_BYTE *)*((_QWORD *)v1 + 38);
    if ( v2 == *((_BYTE **)v1 + 39) )
    {
      SXWriter::writeBuffer((SXWriter *)((char *)this - 32));
      v2 = (_BYTE *)*((_QWORD *)v1 + 38);
    }
    *v2 = -11;
    ++*((_QWORD *)v1 + 38);
    v1[256] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x10040ae00  push    rbx
0x10040ae02  sub     rsp, 20h
0x10040ae06  lea     rbx, [rcx-20h]
0x10040ae0a  mov     word ptr [rcx+0D8h], 101h
0x10040ae13  cmp     byte ptr [rbx+100h], 0
0x10040ae1a  jz      short loc_10040AE4C
0x10040ae1c  mov     rax, [rbx+130h]
0x10040ae23  cmp     rax, [rbx+138h]
0x10040ae2a  jnz     short loc_10040AE3B
0x10040ae2c  mov     rcx, rbx; this
0x10040ae2f  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040ae34  mov     rax, [rbx+130h]
0x10040ae3b  mov     byte ptr [rax], 0F5h
0x10040ae3e  inc     qword ptr [rbx+130h]
0x10040ae45  mov     byte ptr [rbx+100h], 0
0x10040ae4c  xor     eax, eax
0x10040ae4e  add     rsp, 20h
0x10040ae52  pop     rbx
0x10040ae53  retn
```
