# SXWriter::startNest(void)

- ea: `0x100408d00`
- end: `0x100408d5a`
- name: `?startNest@SXWriter@@UEAAJXZ`
- size: `90`
- prototype: `__int64 __fastcall(SXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100407050`
- `0x1004086f0`
- `0x100408d00`
- `0x100409660`

## pseudocode

```c
__int64 __fastcall SXWriter::startNest(SXWriter *this)
{
  _BYTE *v1; // rax

  v1 = (_BYTE *)*((_QWORD *)this + 35);
  if ( v1 == *((_BYTE **)this + 36) )
  {
    SXWriter::writeBuffer((SXWriter *)((char *)this - 24));
    v1 = (_BYTE *)*((_QWORD *)this + 35);
  }
  *v1 = -20;
  ++*((_QWORD *)this + 35);
  SXWriter::WritePreamble((SXWriter *)((char *)this - 24));
  SXTokenTable::PushTokenTable(*((struct IMalloc **)this - 2), (struct SXTokenTable **)this + 7);
  return 0;
}

```

## disassembly

```asm
0x100408d00  mov     [rsp+arg_0], rbx
0x100408d05  push    rdi
0x100408d06  sub     rsp, 20h
0x100408d0a  mov     rax, [rcx+118h]
0x100408d11  mov     rdi, rcx
0x100408d14  cmp     rax, [rcx+120h]
0x100408d1b  jnz     short loc_100408D2D
0x100408d1d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x100408d21  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x100408d26  mov     rax, [rdi+118h]
0x100408d2d  mov     byte ptr [rax], 0ECh
0x100408d30  lea     rcx, [rdi-18h]; this
0x100408d34  inc     qword ptr [rdi+118h]
0x100408d3b  call    ?WritePreamble@SXWriter@@AEAAXXZ; SXWriter::WritePreamble(void)
0x100408d40  mov     rcx, [rdi-10h]; struct IMalloc *
0x100408d44  lea     rdx, [rdi+38h]; struct SXTokenTable **
0x100408d48  call    ?PushTokenTable@SXTokenTable@@SAXPEAUIMalloc@@PEAPEAV1@@Z; SXTokenTable::PushTokenTable(IMalloc *,SXTokenTable * *)
0x100408d4d  mov     rbx, [rsp+28h+arg_0]
0x100408d52  xor     eax, eax
0x100408d54  add     rsp, 20h
0x100408d58  pop     rdi
0x100408d59  retn
```
