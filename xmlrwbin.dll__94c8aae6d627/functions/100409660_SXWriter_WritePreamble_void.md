# SXWriter::WritePreamble(void)

- ea: `0x100409660`
- end: `0x100409739`
- name: `?WritePreamble@SXWriter@@AEAAXXZ`
- size: `217`
- prototype: `void __fastcall(SXWriter *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100408d00`
- `0x100408e10`

## callees

- `0x1004086f0`
- `0x100409660`

## pseudocode

```c
void __fastcall SXWriter::WritePreamble(SXWriter *this)
{
  _BYTE *v1; // rax
  _BYTE *v3; // rax
  _BYTE *v4; // rax
  _BYTE *v5; // rax
  _BYTE *v6; // rax

  v1 = (_BYTE *)*((_QWORD *)this + 38);
  if ( v1 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    v1 = (_BYTE *)*((_QWORD *)this + 38);
  }
  *v1 = -33;
  v3 = (_BYTE *)++*((_QWORD *)this + 38);
  if ( v3 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    v3 = (_BYTE *)*((_QWORD *)this + 38);
  }
  *v3 = -1;
  v4 = (_BYTE *)++*((_QWORD *)this + 38);
  if ( v4 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    v4 = (_BYTE *)*((_QWORD *)this + 38);
  }
  *v4 = 1;
  v5 = (_BYTE *)++*((_QWORD *)this + 38);
  if ( v5 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    v5 = (_BYTE *)*((_QWORD *)this + 38);
  }
  *v5 = -80;
  v6 = (_BYTE *)++*((_QWORD *)this + 38);
  if ( v6 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    v6 = (_BYTE *)*((_QWORD *)this + 38);
  }
  *v6 = 4;
  ++*((_QWORD *)this + 38);
}

```

## disassembly

```asm
0x100409660  push    rbx
0x100409662  sub     rsp, 20h
0x100409666  mov     rax, [rcx+130h]
0x10040966d  mov     rbx, rcx
0x100409670  cmp     rax, [rcx+138h]
0x100409677  jnz     short loc_100409685
0x100409679  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040967e  mov     rax, [rbx+130h]
0x100409685  mov     byte ptr [rax], 0DFh
0x100409688  inc     qword ptr [rbx+130h]
0x10040968f  mov     rax, [rbx+130h]
0x100409696  cmp     rax, [rbx+138h]
0x10040969d  jnz     short loc_1004096AE
0x10040969f  mov     rcx, rbx; this
0x1004096a2  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x1004096a7  mov     rax, [rbx+130h]
0x1004096ae  mov     byte ptr [rax], 0FFh
0x1004096b1  inc     qword ptr [rbx+130h]
0x1004096b8  mov     rax, [rbx+130h]
0x1004096bf  cmp     rax, [rbx+138h]
0x1004096c6  jnz     short loc_1004096D7
0x1004096c8  mov     rcx, rbx; this
0x1004096cb  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x1004096d0  mov     rax, [rbx+130h]
0x1004096d7  mov     byte ptr [rax], 1
0x1004096da  inc     qword ptr [rbx+130h]
0x1004096e1  mov     rax, [rbx+130h]
0x1004096e8  cmp     rax, [rbx+138h]
0x1004096ef  jnz     short loc_100409700
0x1004096f1  mov     rcx, rbx; this
0x1004096f4  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x1004096f9  mov     rax, [rbx+130h]
0x100409700  mov     byte ptr [rax], 0B0h
0x100409703  inc     qword ptr [rbx+130h]
0x10040970a  mov     rax, [rbx+130h]
0x100409711  cmp     rax, [rbx+138h]
0x100409718  jnz     short loc_100409729
0x10040971a  mov     rcx, rbx; this
0x10040971d  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x100409722  mov     rax, [rbx+130h]
0x100409729  mov     byte ptr [rax], 4
0x10040972c  inc     qword ptr [rbx+130h]
0x100409733  add     rsp, 20h
0x100409737  pop     rbx
0x100409738  retn
```
