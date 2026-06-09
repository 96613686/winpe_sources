# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x1800082a0`
- end: `0x1800082da`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `58`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007d4c`
- `0x1800082a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800082c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800082c6`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(
        ATL::CComModule *this,
        int a2,
        unsigned int a3)
{
  char v3; // bl

  v3 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::~CAtlModule(this, a2, a3);
  if ( (v3 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800082a0  mov     [rsp+arg_0], rbx
0x1800082a5  push    rdi
0x1800082a6  sub     rsp, 20h
0x1800082aa  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800082b1  mov     ebx, edx
0x1800082b3  mov     [rcx], rax
0x1800082b6  mov     rdi, rcx
0x1800082b9  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x1800082be  test    bl, 1
0x1800082c1  jz      short loc_1800082CC
0x1800082c3  mov     rcx, rdi
0x1800082c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800082cc  mov     rbx, [rsp+28h+arg_0]
0x1800082d1  mov     rax, rdi
0x1800082d4  add     rsp, 20h
0x1800082d8  pop     rdi
0x1800082d9  retn
```
