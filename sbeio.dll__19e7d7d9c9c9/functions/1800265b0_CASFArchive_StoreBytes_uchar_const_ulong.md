# CASFArchive::StoreBytes(uchar const *,ulong)

- ea: `0x1800265b0`
- end: `0x1800265ee`
- name: `?StoreBytes@CASFArchive@@QEAAJPEBEK@Z`
- size: `62`
- prototype: `int(CASFArchive *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x18001da90`
- `0x18001dce0`
- `0x18001dd70`
- `0x18001df60`
- `0x18001e080`
- `0x18001e190`
- `0x18001e2e0`
- `0x18001e360`
- `0x18001e440`
- `0x18001e4c0`
- `0x18001e950`
- `0x18001eb10`
- `0x18001ecf0`
- `0x18001efa0`
- `0x18001f0c0`
- `0x18001f380`
- `0x18001f400`
- `0x18001f4c0`
- `0x18001f620`
- `0x180028100`

## callees

- `0x1800265b0`
- `0x18002a070`

## pseudocode

```c
__int64 __fastcall CASFArchive::StoreBytes(CASFArchive *this, const unsigned __int8 *a2, unsigned int a3)
{
  __int64 v4; // rdi
  void *v5; // rcx

  v4 = a3;
  v5 = (void *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)v5 + a3 > *((_QWORD *)this + 2) )
    return 3222079440LL;
  memcpy_0(v5, a2, a3);
  *((_QWORD *)this + 1) += v4;
  return 0;
}

```

## disassembly

```asm
0x1800265b0  mov     [rsp+arg_0], rbx
0x1800265b5  push    rdi
0x1800265b6  sub     rsp, 20h
0x1800265ba  mov     rbx, rcx
0x1800265bd  mov     edi, r8d
0x1800265c0  mov     rcx, [rcx+8]; void *
0x1800265c4  lea     rax, [rcx+rdi]
0x1800265c8  cmp     rax, [rbx+10h]
0x1800265cc  jbe     short loc_1800265D5
0x1800265ce  mov     eax, 0C00D07D0h
0x1800265d3  jmp     short loc_1800265E3
0x1800265d5  mov     r8, rdi; Size
0x1800265d8  call    memcpy_0
0x1800265dd  add     [rbx+8], rdi
0x1800265e1  xor     eax, eax
0x1800265e3  mov     rbx, [rsp+28h+arg_0]
0x1800265e8  add     rsp, 20h
0x1800265ec  pop     rdi
0x1800265ed  retn
```
