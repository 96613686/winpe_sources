# CHandleCache::~CHandleCache(void)

- ea: `0x18000941c`
- end: `0x18000949f`
- name: `??1CHandleCache@@UEAA@XZ`
- size: `131`
- prototype: `void __fastcall(CHandleCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800093e0`

## callees

- `0x18000941c`
- `0x180017010`

## import_xrefs

- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180009473`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180009473`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000944d`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000944d`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18000947e`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18000947e`

## pseudocode

```c
void __fastcall CHandleCache::~CHandleCache(CHandleCache *this)
{
  CFlexArray *v2; // rdi
  int i; // ebx
  void (__fastcall ***v4)(void *, __int64); // rax

  *(_QWORD *)this = &CHandleCache::`vftable';
  v2 = (CHandleCache *)((char *)this + 8);
  for ( i = *((_DWORD *)this + 2); --i >= 0; CFlexArray::RemoveAt(v2, i) )
  {
    v4 = (void (__fastcall ***)(void *, __int64))CFlexArray::GetAt(v2, i);
    if ( v4 )
      (**v4)(v4, 1);
  }
  CFlexArray::~CFlexArray(v2);
  *(_QWORD *)this = &CObject::`vftable';
}

```

## disassembly

```asm
0x18000941c  mov     [rsp+arg_8], rbx
0x180009421  mov     [rsp+arg_10], rsi
0x180009426  mov     [rsp+arg_0], rcx
0x18000942b  push    rdi
0x18000942c  sub     rsp, 20h
0x180009430  mov     rsi, rcx
0x180009433  lea     rax, ??_7CHandleCache@@6B@; const CHandleCache::`vftable'
0x18000943a  mov     [rcx], rax
0x18000943d  lea     rdi, [rcx+8]
0x180009441  mov     ebx, [rdi]
0x180009443  sub     ebx, 1
0x180009446  js      short loc_18000947B
0x180009448  mov     edx, ebx
0x18000944a  mov     rcx, rdi
0x18000944d  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180009453  mov     r8, rax
0x180009456  test    rax, rax
0x180009459  jz      short loc_18000946E
0x18000945b  mov     rcx, [rax]
0x18000945e  mov     rax, [rcx]
0x180009461  mov     edx, 1
0x180009466  mov     rcx, r8
0x180009469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000946e  mov     edx, ebx
0x180009470  mov     rcx, rdi
0x180009473  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x180009479  jmp     short loc_180009443
0x18000947b  mov     rcx, rdi
0x18000947e  call    cs:__imp_??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
0x180009484  nop
0x180009485  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x18000948c  mov     [rsi], rax
0x18000948f  mov     rbx, [rsp+28h+arg_8]
0x180009494  mov     rsi, [rsp+28h+arg_10]
0x180009499  add     rsp, 20h
0x18000949d  pop     rdi
0x18000949e  retn
```
