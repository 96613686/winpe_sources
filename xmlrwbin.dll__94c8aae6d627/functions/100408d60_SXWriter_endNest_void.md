# SXWriter::endNest(void)

- ea: `0x100408d60`
- end: `0x100408dde`
- name: `?endNest@SXWriter@@UEAAJXZ`
- size: `126`
- prototype: `__int64 __fastcall(SXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1004086f0`
- `0x100408d60`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXWriter::endNest(SXWriter *this)
{
  _BYTE *v1; // rax
  __int64 v3; // rcx
  __int64 result; // rax

  v1 = (_BYTE *)*((_QWORD *)this + 35);
  if ( v1 == *((_BYTE **)this + 36) )
  {
    SXWriter::writeBuffer((SXWriter *)((char *)this - 24));
    v1 = (_BYTE *)*((_QWORD *)this + 35);
  }
  *v1 = -21;
  ++*((_QWORD *)this + 35);
  v3 = *((_QWORD *)this + 7);
  if ( v3 )
  {
    *((_QWORD *)this + 7) = *(_QWORD *)(v3 + 168);
    (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
    return 0;
  }
  else
  {
    result = 0;
    *((_QWORD *)this + 7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x100408d60  mov     [rsp+arg_0], rbx
0x100408d65  push    rdi
0x100408d66  sub     rsp, 20h
0x100408d6a  mov     rax, [rcx+118h]
0x100408d71  mov     rdi, rcx
0x100408d74  cmp     rax, [rcx+120h]
0x100408d7b  jnz     short loc_100408D8D
0x100408d7d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x100408d81  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x100408d86  mov     rax, [rdi+118h]
0x100408d8d  mov     byte ptr [rax], 0EBh
0x100408d90  inc     qword ptr [rdi+118h]
0x100408d97  mov     rcx, [rdi+38h]
0x100408d9b  test    rcx, rcx
0x100408d9e  jz      short loc_100408DC9
0x100408da0  mov     rax, [rcx+0A8h]
0x100408da7  mov     edx, 1
0x100408dac  mov     [rdi+38h], rax
0x100408db0  mov     rax, [rcx]
0x100408db3  mov     rax, [rax]
0x100408db6  call    cs:__guard_dispatch_icall_fptr
0x100408dbc  xor     eax, eax
0x100408dbe  mov     rbx, [rsp+28h+arg_0]
0x100408dc3  add     rsp, 20h
0x100408dc7  pop     rdi
0x100408dc8  retn
0x100408dc9  mov     rbx, [rsp+28h+arg_0]
0x100408dce  xor     eax, eax
0x100408dd0  mov     qword ptr [rdi+38h], 0
0x100408dd8  add     rsp, 20h
0x100408ddc  pop     rdi
0x100408ddd  retn
```
