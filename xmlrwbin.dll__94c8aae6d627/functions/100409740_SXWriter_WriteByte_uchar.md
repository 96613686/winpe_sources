# SXWriter::WriteByte(uchar)

- ea: `0x100409740`
- end: `0x100409796`
- name: `?WriteByte@SXWriter@@IEAAXE@Z`
- size: `86`
- prototype: `void __fastcall(SXWriter *__hidden this, unsigned __int8)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1004089c0`
- `0x100408bb0`
- `0x100408e10`
- `0x1004098d0`
- `0x10040a5c0`
- `0x10040a660`
- `0x10040a700`
- `0x10040a980`
- `0x10040a9e0`
- `0x10040aa20`
- `0x10040aee0`

## callees

- `0x1004086f0`
- `0x100409740`

## pseudocode

```c
void __fastcall SXWriter::WriteByte(SXWriter *this, char a2)
{
  _BYTE *v2; // rax

  v2 = (_BYTE *)*((_QWORD *)this + 38);
  if ( v2 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    *(_BYTE *)(*((_QWORD *)this + 38))++ = a2;
  }
  else
  {
    *v2 = a2;
    ++*((_QWORD *)this + 38);
  }
}

```

## disassembly

```asm
0x100409740  mov     [rsp+arg_0], rbx
0x100409745  push    rdi
0x100409746  sub     rsp, 20h
0x10040974a  mov     rax, [rcx+130h]
0x100409751  movzx   edi, dl
0x100409754  mov     rbx, rcx
0x100409757  cmp     rax, [rcx+138h]
0x10040975e  jnz     short loc_100409781
0x100409760  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x100409765  mov     rax, [rbx+130h]
0x10040976c  mov     [rax], dil
0x10040976f  inc     qword ptr [rbx+130h]
0x100409776  mov     rbx, [rsp+28h+arg_0]
0x10040977b  add     rsp, 20h
0x10040977f  pop     rdi
0x100409780  retn
0x100409781  mov     rbx, [rsp+28h+arg_0]
0x100409786  mov     [rax], dil
0x100409789  inc     qword ptr [rcx+130h]
0x100409790  add     rsp, 20h
0x100409794  pop     rdi
0x100409795  retn
```
