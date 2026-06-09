# Microsoft::WRL::ComPtr<ID2D1ImageSource>::~ComPtr<ID2D1ImageSource>(void)

- ea: `0x18003b6b0`
- end: `0x18003b6d8`
- name: `??1?$ComPtr@UID2D1ImageSource@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180043af0`
- `0x180043b50`
- `0x180043b70`
- `0x180043b90`
- `0x180043bf0`
- `0x180043c10`
- `0x180043c30`

## callees

- `0x18003b6b0`
- `0x180044010`

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
0x18003b6b0  sub     rsp, 28h
0x18003b6b4  mov     rax, rcx
0x18003b6b7  mov     rcx, [rcx]
0x18003b6ba  test    rcx, rcx
0x18003b6bd  jz      short loc_18003B6D3
0x18003b6bf  mov     qword ptr [rax], 0
0x18003b6c6  mov     rax, [rcx]
0x18003b6c9  mov     rax, [rax+10h]
0x18003b6cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6d2  nop
0x18003b6d3  add     rsp, 28h
0x18003b6d7  retn
```
