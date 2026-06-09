# ATL::CComAggObject<CXmlContentFilter>::`scalar deleting destructor'(uint)

- ea: `0x18000ff10`
- end: `0x18000ff6c`
- name: `??_G?$CComAggObject@VCXmlContentFilter@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000213c`
- `0x18000fe98`
- `0x18000ff10`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_DWORD *__fastcall ATL::CComAggObject<CXmlContentFilter>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CXmlContentFilter>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CXmlContentFilter::~CXmlContentFilter((CXmlContentFilter *)(Block + 6));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000ff10  mov     [rsp+arg_0], rbx
0x18000ff15  push    rdi
0x18000ff16  sub     rsp, 20h
0x18000ff1a  mov     dword ptr [rcx+8], 0C0000001h
0x18000ff21  lea     rax, ??_7?$CComAggObject@VCXmlContentFilter@@@ATL@@6B@; const ATL::CComAggObject<CXmlContentFilter>::`vftable'
0x18000ff28  mov     [rcx], rax
0x18000ff2b  mov     rdi, rcx
0x18000ff2e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ff35  mov     ebx, edx
0x18000ff37  mov     rax, [rcx]
0x18000ff3a  mov     rax, [rax+10h]
0x18000ff3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff43  lea     rcx, [rdi+18h]; this
0x18000ff47  call    ??1CXmlContentFilter@@QEAA@XZ; CXmlContentFilter::~CXmlContentFilter(void)
0x18000ff4c  test    bl, 1
0x18000ff4f  jz      short loc_18000FF5E
0x18000ff51  mov     edx, 238h
0x18000ff56  mov     rcx, rdi; Block
0x18000ff59  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ff5e  mov     rbx, [rsp+28h+arg_0]
0x18000ff63  mov     rax, rdi
0x18000ff66  add     rsp, 20h
0x18000ff6a  pop     rdi
0x18000ff6b  retn
```
