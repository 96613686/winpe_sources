# std::vector<std::unique_ptr<Finder,std::default_delete<Finder>>,std::allocator<std::unique_ptr<Finder,std::default_delete<Finder>>>>::_Destroy(std::unique_ptr<Finder,std::default_delete<Finder>> *,std::unique_ptr<Finder,std::default_delete<Finder>> *)

- ea: `0x18000ad08`
- end: `0x18000ad49`
- name: `?_Destroy@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@2@0@Z`
- size: `65`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004018`
- `0x1800046f0`
- `0x180014e28`
- `0x180017718`

## callees

- `0x18000ad08`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<Finder>>::_Destroy(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // rbx
  __int64 result; // rax

  if ( a2 != a3 )
  {
    v4 = a2;
    do
    {
      if ( *v4 )
        result = (**(__int64 (__fastcall ***)(_QWORD, __int64))*v4)(*v4, 1);
      ++v4;
    }
    while ( v4 != a3 );
  }
  return result;
}

```

## disassembly

```asm
0x18000ad08  cmp     rdx, r8
0x18000ad0b  jz      short locret_18000AD48
0x18000ad0d  mov     [rsp+arg_0], rbx
0x18000ad12  push    rdi
0x18000ad13  sub     rsp, 20h
0x18000ad17  mov     rdi, r8
0x18000ad1a  mov     rbx, rdx
0x18000ad1d  mov     rcx, [rbx]
0x18000ad20  test    rcx, rcx
0x18000ad23  jz      short loc_18000AD35
0x18000ad25  mov     rax, [rcx]
0x18000ad28  mov     edx, 1
0x18000ad2d  mov     rax, [rax]
0x18000ad30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad35  add     rbx, 8
0x18000ad39  cmp     rbx, rdi
0x18000ad3c  jnz     short loc_18000AD1D
0x18000ad3e  mov     rbx, [rsp+28h+arg_0]
0x18000ad43  add     rsp, 20h
0x18000ad47  pop     rdi
0x18000ad48  retn
```
