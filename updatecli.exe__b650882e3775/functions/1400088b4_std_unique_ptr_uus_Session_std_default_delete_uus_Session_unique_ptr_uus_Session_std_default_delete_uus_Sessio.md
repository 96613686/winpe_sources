# std::unique_ptr<uus::Session,std::default_delete<uus::Session>>::~unique_ptr<uus::Session,std::default_delete<uus::Session>>(void)

- ea: `0x1400088b4`
- end: `0x1400088d5`
- name: `??1?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000affe`

## callees

- `0x1400088b4`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(
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
0x1400088b4  sub     rsp, 28h
0x1400088b8  mov     rcx, [rcx]
0x1400088bb  test    rcx, rcx
0x1400088be  jz      short loc_1400088D0
0x1400088c0  mov     rax, [rcx]
0x1400088c3  mov     edx, 1
0x1400088c8  mov     rax, [rax]
0x1400088cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088d0  add     rsp, 28h
0x1400088d4  retn
```
