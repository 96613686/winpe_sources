# std::unique_ptr<CProfileTask_OnCreate,std::default_delete<CProfileTask_OnCreate>>::~unique_ptr<CProfileTask_OnCreate,std::default_delete<CProfileTask_OnCreate>>(void)

- ea: `0x180004cbc`
- end: `0x180004cdd`
- name: `??1?$unique_ptr@VCProfileTask_OnCreate@@U?$default_delete@VCProfileTask_OnCreate@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000dd4c`

## callees

- `0x180004cbc`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<CProfileTask_OnCreate>::~unique_ptr<CProfileTask_OnCreate>(
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
0x180004cbc  sub     rsp, 28h
0x180004cc0  mov     rcx, [rcx]
0x180004cc3  test    rcx, rcx
0x180004cc6  jz      short loc_180004CD8
0x180004cc8  mov     rax, [rcx]
0x180004ccb  mov     edx, 1
0x180004cd0  mov     rax, [rax]
0x180004cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cd8  add     rsp, 28h
0x180004cdc  retn
```
