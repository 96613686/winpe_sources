# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x1800023e0`
- end: `0x18000241e`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001534`
- `0x180002248`
- `0x1800023e0`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::~CAtlModule(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800023e0  mov     [rsp+arg_0], rbx
0x1800023e5  push    rdi
0x1800023e6  sub     rsp, 20h
0x1800023ea  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800023f1  mov     ebx, edx
0x1800023f3  mov     [rcx], rax
0x1800023f6  mov     rdi, rcx
0x1800023f9  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x1800023fe  test    bl, 1
0x180002401  jz      short loc_180002410
0x180002403  mov     edx, 50h ; 'P'
0x180002408  mov     rcx, rdi; Block
0x18000240b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002410  mov     rbx, [rsp+28h+arg_0]
0x180002415  mov     rax, rdi
0x180002418  add     rsp, 20h
0x18000241c  pop     rdi
0x18000241d  retn
```
