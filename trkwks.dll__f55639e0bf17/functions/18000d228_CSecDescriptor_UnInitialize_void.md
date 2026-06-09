# CSecDescriptor::UnInitialize(void)

- ea: `0x18000d228`
- end: `0x18000d262`
- name: `?UnInitialize@CSecDescriptor@@QEAAXXZ`
- size: `58`
- prototype: `void __fastcall(CSecDescriptor *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000a65c`
- `0x18000a880`
- `0x18000d1a0`
- `0x18000d1d0`
- `0x180010638`

## callees

- `0x18000d1fc`
- `0x18000d228`
- `0x18000db28`

## pseudocode

```c
void __fastcall CSecDescriptor::UnInitialize(CSecDescriptor *this)
{
  void *v2; // rcx

  if ( *(_DWORD *)this )
  {
    v2 = (void *)*((_QWORD *)this + 1);
    if ( v2 )
      operator delete(v2);
    CACL::UnInitialize((CSecDescriptor *)((char *)this + 16));
    CACL::UnInitialize((CSecDescriptor *)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000d228  push    rbx
0x18000d22a  sub     rsp, 20h
0x18000d22e  cmp     dword ptr [rcx], 0
0x18000d231  mov     rbx, rcx
0x18000d234  jz      short loc_18000D25C
0x18000d236  mov     rcx, [rcx+8]; Block
0x18000d23a  test    rcx, rcx
0x18000d23d  jz      short loc_18000D244
0x18000d23f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d244  lea     rcx, [rbx+10h]; this
0x18000d248  call    ?UnInitialize@CACL@@QEAAXXZ; CACL::UnInitialize(void)
0x18000d24d  lea     rcx, [rbx+20h]; this
0x18000d251  call    ?UnInitialize@CACL@@QEAAXXZ; CACL::UnInitialize(void)
0x18000d256  mov     dword ptr [rbx], 0
0x18000d25c  add     rsp, 20h
0x18000d260  pop     rbx
0x18000d261  retn
```
