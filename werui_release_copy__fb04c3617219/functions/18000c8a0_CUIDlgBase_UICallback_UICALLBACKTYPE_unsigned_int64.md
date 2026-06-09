# CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)

- ea: `0x18000c8a0`
- end: `0x18000c8d1`
- name: `?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z`
- size: `49`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x180006550`
- `0x180006870`
- `0x180006b10`
- `0x180006bdc`
- `0x180006ee0`
- `0x180007e50`
- `0x18000801c`
- `0x1800080d8`
- `0x180008528`
- `0x180008668`
- `0x18000884c`
- `0x180009350`
- `0x180009fc8`
- `0x18000a14c`
- `0x18000a238`
- `0x18000a640`
- `0x18000a880`
- `0x18000ab00`
- `0x18000cb5c`
- `0x18000cbc8`
- `0x18000d114`
- `0x18000de20`
- `0x18000df18`

## callees

- `0x18000c8a0`
- `0x180018010`

## pseudocode

```c
__int64 (__fastcall *__fastcall CUIDlgBase::UICallback(__int64 a1, int a2, __int64 a3))(__int64, _DWORD *)
{
  __int64 (__fastcall *result)(__int64, _DWORD *); // rax
  __int64 v4; // rcx
  _DWORD v5[2]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v6; // [rsp+28h] [rbp-10h]

  result = *(__int64 (__fastcall **)(__int64, _DWORD *))(a1 + 24);
  if ( result )
  {
    v4 = *(_QWORD *)(a1 + 32);
    v5[0] = a2;
    v5[1] = 0;
    v6 = a3;
    return (__int64 (__fastcall *)(__int64, _DWORD *))result(v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000c8a0  sub     rsp, 38h
0x18000c8a4  mov     rax, [rcx+18h]
0x18000c8a8  test    rax, rax
0x18000c8ab  jz      short loc_18000C8CC
0x18000c8ad  mov     rcx, [rcx+20h]
0x18000c8b1  mov     [rsp+38h+var_18], edx
0x18000c8b5  lea     rdx, [rsp+38h+var_18]
0x18000c8ba  mov     [rsp+38h+var_14], 0
0x18000c8c2  mov     [rsp+38h+var_10], r8
0x18000c8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8cc  add     rsp, 38h
0x18000c8d0  retn
```
