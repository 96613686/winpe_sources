# CIndexCache::CIndexCache(void)

- ea: `0x1800042ac`
- end: `0x1800042ea`
- name: `??0CIndexCache@@QEAA@XZ`
- size: `62`
- prototype: `CIndexCache *__fastcall(CIndexCache *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003f64`
- `0x18000f914`

## import_xrefs

- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x1800042da`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x1800042da`

## pseudocode

```c
CIndexCache *__fastcall CIndexCache::CIndexCache(CIndexCache *this)
{
  *(_QWORD *)this = &CObject::`vftable';
  *(_QWORD *)this = &CIndexCache::`vftable';
  CFlexArray::CFlexArray((CIndexCache *)((char *)this + 8), 8, 100);
  return this;
}

```

## disassembly

```asm
0x1800042ac  mov     [rsp+arg_0], rcx
0x1800042b1  push    rbx
0x1800042b2  sub     rsp, 20h
0x1800042b6  mov     rbx, rcx
0x1800042b9  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x1800042c0  mov     [rcx], rax
0x1800042c3  lea     rax, ??_7CIndexCache@@6B@; const CIndexCache::`vftable'
0x1800042ca  mov     [rcx], rax
0x1800042cd  add     rcx, 8
0x1800042d1  mov     edx, 8
0x1800042d6  lea     r8d, [rdx+5Ch]
0x1800042da  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x1800042e0  nop
0x1800042e1  mov     rax, rbx
0x1800042e4  add     rsp, 20h
0x1800042e8  pop     rbx
0x1800042e9  retn
```
