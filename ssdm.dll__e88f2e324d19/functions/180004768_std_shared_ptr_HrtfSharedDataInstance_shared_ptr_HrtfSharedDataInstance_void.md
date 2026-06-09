# std::shared_ptr<HrtfSharedDataInstance>::~shared_ptr<HrtfSharedDataInstance>(void)

- ea: `0x180004768`
- end: `0x1800047b5`
- name: `??1?$shared_ptr@VHrtfSharedDataInstance@@@std@@QEAA@XZ`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eed7`
- `0x18000f153`
- `0x18000fa02`

## callees

- `0x180004768`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<HrtfSharedDataInstance>::~shared_ptr<HrtfSharedDataInstance>(__int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      result = (unsigned int)_InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004768  push    rbx
0x18000476a  sub     rsp, 20h
0x18000476e  mov     rbx, [rcx+8]
0x180004772  test    rbx, rbx
0x180004775  jz      short loc_1800047AF
0x180004777  or      eax, 0FFFFFFFFh
0x18000477a  lock xadd [rbx+8], eax
0x18000477f  cmp     eax, 1
0x180004782  jnz     short loc_1800047AF
0x180004784  mov     rax, [rbx]
0x180004787  mov     rcx, rbx
0x18000478a  mov     rax, [rax]
0x18000478d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004792  or      eax, 0FFFFFFFFh
0x180004795  lock xadd [rbx+0Ch], eax
0x18000479a  cmp     eax, 1
0x18000479d  jnz     short loc_1800047AF
0x18000479f  mov     rax, [rbx]
0x1800047a2  mov     rcx, rbx
0x1800047a5  mov     rax, [rax+8]
0x1800047a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ae  nop
0x1800047af  add     rsp, 20h
0x1800047b3  pop     rbx
0x1800047b4  retn
```
