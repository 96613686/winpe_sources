# ATL::CDacl::CAccessAce::`vector deleting destructor'(uint)

- ea: `0x1400021f0`
- end: `0x14000223c`
- name: `??_ECAccessAce@CDacl@ATL@@UEAAPEAXI@Z`
- size: `76`
- prototype: `void **__fastcall(void **this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400021f0`
- `0x1400028b0`

## import_xrefs

- `msvcrt!free` at `0x140002210`
- `msvcrt!free` at `0x140002210`
- `msvcrt!??3@YAXPEAX@Z` at `0x140002228`
- `msvcrt!??3@YAXPEAX@Z` at `0x140002228`

## pseudocode

```c
void **__fastcall ATL::CDacl::CAccessAce::`vector deleting destructor'(void **this, char a2)
{
  *this = &ATL::CAcl::CAce::`vftable';
  free(this[17]);
  ATL::CSid::~CSid((ATL::CSid *)(this + 1));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400021f0  mov     [rsp+arg_0], rbx
0x1400021f5  push    rdi
0x1400021f6  sub     rsp, 20h
0x1400021fa  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x140002201  mov     rbx, rcx
0x140002204  mov     [rcx], rax
0x140002207  mov     edi, edx
0x140002209  mov     rcx, [rcx+88h]; Block
0x140002210  call    cs:__imp_free
0x140002216  lea     rcx, [rbx+8]; this
0x14000221a  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000221f  test    dil, 1
0x140002223  jz      short loc_14000222E
0x140002225  mov     rcx, rbx
0x140002228  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000222e  mov     rax, rbx
0x140002231  mov     rbx, [rsp+28h+arg_0]
0x140002236  add     rsp, 20h
0x14000223a  pop     rdi
0x14000223b  retn
```
