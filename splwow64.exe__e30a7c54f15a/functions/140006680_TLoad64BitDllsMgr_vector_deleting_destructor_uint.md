# TLoad64BitDllsMgr::`vector deleting destructor'(uint)

- ea: `0x140006680`
- end: `0x1400066b4`
- name: `??_ETLoad64BitDllsMgr@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(TLoad64BitDllsMgr *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140006670`

## callees

- `0x140001b90`
- `0x140006620`
- `0x140006680`

## pseudocode

```c
TLoad64BitDllsMgr *__fastcall TLoad64BitDllsMgr::`vector deleting destructor'(TLoad64BitDllsMgr *this, char a2)
{
  TLoad64BitDllsMgr::~TLoad64BitDllsMgr(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140006680  mov     [rsp+arg_0], rbx
0x140006685  push    rdi
0x140006686  sub     rsp, 20h
0x14000668a  mov     ebx, edx
0x14000668c  mov     rdi, rcx
0x14000668f  call    ??1TLoad64BitDllsMgr@@UEAA@XZ; TLoad64BitDllsMgr::~TLoad64BitDllsMgr(void)
0x140006694  test    bl, 1
0x140006697  jz      short loc_1400066A6
0x140006699  mov     edx, 88h
0x14000669e  mov     rcx, rdi; Block
0x1400066a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400066a6  mov     rbx, [rsp+28h+arg_0]
0x1400066ab  mov     rax, rdi
0x1400066ae  add     rsp, 20h
0x1400066b2  pop     rdi
0x1400066b3  retn
```
