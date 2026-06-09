# ATL::CDacl::`vector deleting destructor'(uint)

- ea: `0x140009500`
- end: `0x140009530`
- name: `??_ECDacl@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void **__fastcall(void **this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140002250`
- `0x140009500`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000951c`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000951c`

## pseudocode

```c
void **__fastcall ATL::CDacl::`vector deleting destructor'(void **this, char a2)
{
  ATL::CDacl::~CDacl(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140009500  mov     [rsp+arg_0], rbx
0x140009505  push    rdi
0x140009506  sub     rsp, 20h
0x14000950a  mov     ebx, edx
0x14000950c  mov     rdi, rcx
0x14000950f  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x140009514  test    bl, 1
0x140009517  jz      short loc_140009522
0x140009519  mov     rcx, rdi
0x14000951c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140009522  mov     rbx, [rsp+28h+arg_0]
0x140009527  mov     rax, rdi
0x14000952a  add     rsp, 20h
0x14000952e  pop     rdi
0x14000952f  retn
```
