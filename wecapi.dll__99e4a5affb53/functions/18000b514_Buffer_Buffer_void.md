# Buffer::~Buffer(void)

- ea: `0x18000b514`
- end: `0x18000b536`
- name: `??1Buffer@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(Buffer *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006818`
- `0x18000a820`
- `0x18000c4e0`
- `0x18000c6e4`

## callees

- `0x1800026c0`
- `0x18000b514`

## pseudocode

```c
void __fastcall Buffer::~Buffer(Buffer *this)
{
  bool v1; // zf

  v1 = *((_BYTE *)this + 32) == 0;
  *(_QWORD *)this = &Buffer::`vftable';
  if ( !v1 )
    operator delete(*((void **)this + 2));
}

```

## disassembly

```asm
0x18000b514  sub     rsp, 28h
0x18000b518  cmp     byte ptr [rcx+20h], 0
0x18000b51c  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x18000b523  mov     [rcx], rax
0x18000b526  jz      short loc_18000B531
0x18000b528  mov     rcx, [rcx+10h]; void *
0x18000b52c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b531  add     rsp, 28h
0x18000b535  retn
```
