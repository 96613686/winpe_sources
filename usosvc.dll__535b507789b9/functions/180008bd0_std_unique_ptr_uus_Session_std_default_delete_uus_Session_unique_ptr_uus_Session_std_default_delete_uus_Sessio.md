# std::unique_ptr<uus::Session,std::default_delete<uus::Session>>::~unique_ptr<uus::Session,std::default_delete<uus::Session>>(void)

- ea: `0x180008bd0`
- end: `0x180008bf1`
- name: `??1?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e87b`

## callees

- `0x180008bd0`
- `0x18000f010`

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
0x180008bd0  sub     rsp, 28h
0x180008bd4  mov     rcx, [rcx]
0x180008bd7  test    rcx, rcx
0x180008bda  jz      short loc_180008BEC
0x180008bdc  mov     rax, [rcx]
0x180008bdf  mov     edx, 1
0x180008be4  mov     rax, [rax]
0x180008be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bec  add     rsp, 28h
0x180008bf0  retn
```
