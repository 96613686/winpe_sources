# StringTokenizer::~StringTokenizer(void)

- ea: `0x18000a380`
- end: `0x18000a3d9`
- name: `??1StringTokenizer@@QEAA@XZ`
- size: `89`
- prototype: `void __fastcall(StringTokenizer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c708`
- `0x18000c72c`

## callees

- `0x1800026c0`
- `0x18000a380`

## pseudocode

```c
void __fastcall StringTokenizer::~StringTokenizer(void **this)
{
  if ( (unsigned __int64)this[7] >= 8 )
    operator delete(this[4]);
  this[7] = (void *)7;
  this[6] = 0;
  *((_WORD *)this + 16) = 0;
  if ( (unsigned __int64)this[3] >= 8 )
    operator delete(*this);
  this[3] = (void *)7;
  this[2] = 0;
  *(_WORD *)this = 0;
}

```

## disassembly

```asm
0x18000a380  push    rbx
0x18000a382  sub     rsp, 20h
0x18000a386  cmp     qword ptr [rcx+38h], 8
0x18000a38b  mov     rbx, rcx
0x18000a38e  jb      short loc_18000A399
0x18000a390  mov     rcx, [rcx+20h]; void *
0x18000a394  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a399  xor     eax, eax
0x18000a39b  mov     qword ptr [rbx+38h], 7
0x18000a3a3  mov     qword ptr [rbx+30h], 0
0x18000a3ab  mov     [rbx+20h], ax
0x18000a3af  cmp     qword ptr [rbx+18h], 8
0x18000a3b4  jb      short loc_18000A3BE
0x18000a3b6  mov     rcx, [rbx]; void *
0x18000a3b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a3be  xor     eax, eax
0x18000a3c0  mov     qword ptr [rbx+18h], 7
0x18000a3c8  mov     qword ptr [rbx+10h], 0
0x18000a3d0  mov     [rbx], ax
0x18000a3d3  add     rsp, 20h
0x18000a3d7  pop     rbx
0x18000a3d8  retn
```
