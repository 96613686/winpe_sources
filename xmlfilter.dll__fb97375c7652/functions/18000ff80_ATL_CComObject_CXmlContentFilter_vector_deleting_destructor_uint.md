# ATL::CComObject<CXmlContentFilter>::`vector deleting destructor'(uint)

- ea: `0x18000ff80`
- end: `0x18000fff1`
- name: `??_E?$CComObject@VCXmlContentFilter@@@ATL@@UEAAPEAXI@Z`
- size: `113`
- prototype: `CXmlContentFilter *__fastcall(CXmlContentFilter *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000213c`
- `0x18000fe98`
- `0x18000ff80`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CXmlContentFilter *__fastcall ATL::CComObject<CXmlContentFilter>::`vector deleting destructor'(
        CXmlContentFilter *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CXmlContentFilter>::`vftable'{for `IFilter'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CXmlContentFilter>::`vftable'{for `IPersistFile'};
  *((_QWORD *)this + 2) = &ATL::CComObject<CXmlContentFilter>::`vftable'{for `IPersistStream'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CXmlContentFilter::~CXmlContentFilter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ff80  mov     [rsp+arg_0], rbx
0x18000ff85  push    rdi
0x18000ff86  sub     rsp, 20h
0x18000ff8a  mov     dword ptr [rcx+18h], 0C0000001h
0x18000ff91  lea     rax, ??_7?$CComObject@VCXmlContentFilter@@@ATL@@6BIFilter@@@; const ATL::CComObject<CXmlContentFilter>::`vftable'{for `IFilter'}
0x18000ff98  mov     [rcx], rax
0x18000ff9b  mov     rdi, rcx
0x18000ff9e  lea     rax, ??_7?$CComObject@VCXmlContentFilter@@@ATL@@6BIPersistFile@@@; const ATL::CComObject<CXmlContentFilter>::`vftable'{for `IPersistFile'}
0x18000ffa5  mov     ebx, edx
0x18000ffa7  mov     [rcx+8], rax
0x18000ffab  lea     rax, ??_7?$CComObject@VCXmlContentFilter@@@ATL@@6BIPersistStream@@@; const ATL::CComObject<CXmlContentFilter>::`vftable'{for `IPersistStream'}
0x18000ffb2  mov     [rcx+10h], rax
0x18000ffb6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ffbd  mov     rax, [rcx]
0x18000ffc0  mov     rax, [rax+10h]
0x18000ffc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffc9  mov     rcx, rdi; this
0x18000ffcc  call    ??1CXmlContentFilter@@QEAA@XZ; CXmlContentFilter::~CXmlContentFilter(void)
0x18000ffd1  test    bl, 1
0x18000ffd4  jz      short loc_18000FFE3
0x18000ffd6  mov     edx, 220h
0x18000ffdb  mov     rcx, rdi; Block
0x18000ffde  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ffe3  mov     rbx, [rsp+28h+arg_0]
0x18000ffe8  mov     rax, rdi
0x18000ffeb  add     rsp, 20h
0x18000ffef  pop     rdi
0x18000fff0  retn
```
