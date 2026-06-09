# ATL::CSid::`scalar deleting destructor'(uint)

- ea: `0x140006d40`
- end: `0x140006d74`
- name: `??_GCSid@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(ATL::CSid *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400011b0`
- `0x140006c7c`
- `0x140006d40`

## pseudocode

```c
ATL::CSid *__fastcall ATL::CSid::`scalar deleting destructor'(ATL::CSid *this, char a2)
{
  ATL::CSid::~CSid(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140006d40  mov     [rsp+arg_0], rbx
0x140006d45  push    rdi
0x140006d46  sub     rsp, 20h
0x140006d4a  mov     ebx, edx
0x140006d4c  mov     rdi, rcx
0x140006d4f  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140006d54  test    bl, 1
0x140006d57  jz      short loc_140006D66
0x140006d59  mov     edx, 78h ; 'x'
0x140006d5e  mov     rcx, rdi; Block
0x140006d61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006d66  mov     rbx, [rsp+28h+arg_0]
0x140006d6b  mov     rax, rdi
0x140006d6e  add     rsp, 20h
0x140006d72  pop     rdi
0x140006d73  retn
```
