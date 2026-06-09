# Microsoft::WRL::ComPtr<com::application_reputation_static>::~ComPtr<com::application_reputation_static>(void)

- ea: `0x18000aadc`
- end: `0x18000ab05`
- name: `??1?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d170`
- `0x18000d264`
- `0x18000d2b5`

## callees

- `0x18000aadc`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<com::application_reputation_static>::~ComPtr<com::application_reputation_static>(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18000aadc  sub     rsp, 28h
0x18000aae0  mov     rax, rcx
0x18000aae3  mov     rcx, [rcx]
0x18000aae6  test    rcx, rcx
0x18000aae9  jz      short loc_18000AAFF
0x18000aaeb  mov     qword ptr [rax], 0
0x18000aaf2  mov     rax, [rcx]
0x18000aaf5  mov     rax, [rax+10h]
0x18000aaf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aafe  nop
0x18000aaff  add     rsp, 28h
0x18000ab03  retn
```
