# CIndexCache::~CIndexCache(void)

- ea: `0x18000b9ac`
- end: `0x18000b9e4`
- name: `??1CIndexCache@@UEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CIndexCache *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a0f0`
- `0x18000d9c0`
- `0x18000fae8`
- `0x180015b82`
- `0x1800163aa`
- `0x180016af2`

## callees

- `0x18000a5ec`

## import_xrefs

- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18000b9cd`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18000b9cd`

## pseudocode

```c
void __fastcall CIndexCache::~CIndexCache(CIndexCache *this)
{
  *(_QWORD *)this = &CIndexCache::`vftable';
  CIndexCache::Empty(this);
  CFlexArray::~CFlexArray((CIndexCache *)((char *)this + 8));
  *(_QWORD *)this = &CObject::`vftable';
}

```

## disassembly

```asm
0x18000b9ac  mov     [rsp+arg_0], rcx
0x18000b9b1  push    rbx
0x18000b9b2  sub     rsp, 20h
0x18000b9b6  mov     rbx, rcx
0x18000b9b9  lea     rax, ??_7CIndexCache@@6B@; const CIndexCache::`vftable'
0x18000b9c0  mov     [rcx], rax
0x18000b9c3  call    ?Empty@CIndexCache@@QEAAXXZ; CIndexCache::Empty(void)
0x18000b9c8  nop
0x18000b9c9  lea     rcx, [rbx+8]
0x18000b9cd  call    cs:__imp_??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
0x18000b9d3  nop
0x18000b9d4  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x18000b9db  mov     [rbx], rax
0x18000b9de  add     rsp, 20h
0x18000b9e2  pop     rbx
0x18000b9e3  retn
```
