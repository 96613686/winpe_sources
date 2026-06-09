# Microsoft::WRL::ComPtr<ID2D1ImageSource>::~ComPtr<ID2D1ImageSource>(void)

- ea: `0x18003bfa0`
- end: `0x18003bfc9`
- name: `??1?$ComPtr@UID2D1ImageSource@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180044300`
- `0x180044360`
- `0x180044380`
- `0x1800443a0`
- `0x180044400`
- `0x180044420`
- `0x180044440`

## callees

- `0x18003bfa0`
- `0x180045010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<ID2D1ImageSource>::~ComPtr<ID2D1ImageSource>(_QWORD *a1)
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
0x18003bfa0  sub     rsp, 28h
0x18003bfa4  mov     rax, rcx
0x18003bfa7  mov     rcx, [rcx]
0x18003bfaa  test    rcx, rcx
0x18003bfad  jz      short loc_18003BFC3
0x18003bfaf  mov     qword ptr [rax], 0
0x18003bfb6  mov     rax, [rcx]
0x18003bfb9  mov     rax, [rax+10h]
0x18003bfbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfc2  nop
0x18003bfc3  add     rsp, 28h
0x18003bfc7  retn
```
