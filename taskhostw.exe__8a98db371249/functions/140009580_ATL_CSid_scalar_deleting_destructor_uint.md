# ATL::CSid::`scalar deleting destructor'(uint)

- ea: `0x140009580`
- end: `0x1400095b0`
- name: `??_GCSid@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `ATL::CSid *__fastcall(ATL::CSid *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400028b0`
- `0x140009580`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000959c`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000959c`

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
0x140009580  mov     [rsp+arg_0], rbx
0x140009585  push    rdi
0x140009586  sub     rsp, 20h
0x14000958a  mov     ebx, edx
0x14000958c  mov     rdi, rcx
0x14000958f  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140009594  test    bl, 1
0x140009597  jz      short loc_1400095A2
0x140009599  mov     rcx, rdi
0x14000959c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400095a2  mov     rbx, [rsp+28h+arg_0]
0x1400095a7  mov     rax, rdi
0x1400095aa  add     rsp, 20h
0x1400095ae  pop     rdi
0x1400095af  retn
```
