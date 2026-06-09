# ATL::CStringData::Release(void)

- ea: `0x180011d80`
- end: `0x180011da8`
- name: `?Release@CStringData@ATL@@QEAAXXZ`
- size: `40`
- prototype: `void __fastcall(ATL::CStringData *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007880`
- `0x180011714`
- `0x180011860`
- `0x180011948`
- `0x180011de8`

## callees

- `0x180011d80`
- `0x180016010`

## pseudocode

```c
void __fastcall ATL::CStringData::Release(ATL::CStringData *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, ATL::CStringData *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, this);
}

```

## disassembly

```asm
0x180011d80  sub     rsp, 28h
0x180011d84  mov     rdx, rcx
0x180011d87  or      eax, 0FFFFFFFFh
0x180011d8a  lock xadd [rcx+10h], eax
0x180011d8f  sub     eax, 1
0x180011d92  jg      short loc_180011DA3
0x180011d94  mov     rcx, [rcx]
0x180011d97  mov     rax, [rcx]
0x180011d9a  mov     rax, [rax+8]
0x180011d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011da3  add     rsp, 28h
0x180011da7  retn
```
