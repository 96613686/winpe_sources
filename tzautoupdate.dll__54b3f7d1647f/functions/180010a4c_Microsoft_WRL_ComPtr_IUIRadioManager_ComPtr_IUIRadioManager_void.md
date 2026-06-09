# Microsoft::WRL::ComPtr<IUIRadioManager>::~ComPtr<IUIRadioManager>(void)

- ea: `0x180010a4c`
- end: `0x180010a74`
- name: `??1?$ComPtr@UIUIRadioManager@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bdab`
- `0x18001bdd7`
- `0x18001c010`

## callees

- `0x180010a4c`
- `0x18001d010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<IUIRadioManager>::~ComPtr<IUIRadioManager>(_QWORD *a1)
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
0x180010a4c  sub     rsp, 28h
0x180010a50  mov     rax, rcx
0x180010a53  mov     rcx, [rcx]
0x180010a56  test    rcx, rcx
0x180010a59  jz      short loc_180010A6F
0x180010a5b  mov     qword ptr [rax], 0
0x180010a62  mov     rax, [rcx]
0x180010a65  mov     rax, [rax+10h]
0x180010a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a6e  nop
0x180010a6f  add     rsp, 28h
0x180010a73  retn
```
