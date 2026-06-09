# CLogConfigurableFilter::~CLogConfigurableFilter(void)

- ea: `0x180025604`
- end: `0x18002562a`
- name: `??1CLogConfigurableFilter@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(CLogConfigurableFilter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800259b0`

## callees

- `0x18001e224`
- `0x180025a4c`

## pseudocode

```c
void __fastcall CLogConfigurableFilter::~CLogConfigurableFilter(CLogConfigurableFilter *this)
{
  *(_QWORD *)this = &CLogConfigurableFilter::`vftable';
  CLogConfigurableFilter::DestroyRules(this);
  CPtrList<tagLOG_FILTER_CLAUSE *>::~CPtrList<tagLOG_FILTER_CLAUSE *>((char *)this + 8);
}

```

## disassembly

```asm
0x180025604  push    rbx
0x180025606  sub     rsp, 20h
0x18002560a  lea     rax, ??_7CLogConfigurableFilter@@6B@; const CLogConfigurableFilter::`vftable'
0x180025611  mov     rbx, rcx
0x180025614  mov     [rcx], rax
0x180025617  call    ?DestroyRules@CLogConfigurableFilter@@IEAAXXZ; CLogConfigurableFilter::DestroyRules(void)
0x18002561c  lea     rcx, [rbx+8]
0x180025620  add     rsp, 20h
0x180025624  pop     rbx
0x180025625  jmp     ??1?$CPtrList@PEAUtagLOG_FILTER_CLAUSE@@@@QEAA@XZ; CPtrList<tagLOG_FILTER_CLAUSE *>::~CPtrList<tagLOG_FILTER_CLAUSE *>(void)
```
