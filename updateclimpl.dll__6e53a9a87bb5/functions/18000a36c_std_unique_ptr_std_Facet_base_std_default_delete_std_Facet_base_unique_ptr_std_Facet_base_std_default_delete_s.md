# std::unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>::~unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>(void)

- ea: `0x18000a36c`
- end: `0x18000a38d`
- name: `??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015d03`

## callees

- `0x18000a36c`
- `0x1800148e0`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x18000a36c  sub     rsp, 28h
0x18000a370  mov     rcx, [rcx]
0x18000a373  test    rcx, rcx
0x18000a376  jz      short loc_18000A388
0x18000a378  mov     rax, [rcx]
0x18000a37b  mov     edx, 1
0x18000a380  mov     rax, [rax]
0x18000a383  call    _guard_dispatch_icall
0x18000a388  add     rsp, 28h
0x18000a38c  retn
```
