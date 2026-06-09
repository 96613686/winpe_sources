# wil::details::ResultStatus::FromResult(long)

- ea: `0x1800049e0`
- end: `0x180004a04`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d94`
- `0x180005df8`
- `0x18000bbdc`
- `0x18000c0c8`
- `0x18000d978`

## callees

- `0x180004d50`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStatus::FromResult(unsigned int *a1, unsigned int a2)
{
  int v2; // eax
  __int64 v3; // r8
  __int64 result; // rax

  *a1 = a2;
  v2 = wil::details::HrToNtStatus((wil::details *)a2, a2);
  *(_DWORD *)(v3 + 4) = v2;
  result = v3;
  *(_DWORD *)(v3 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x1800049e0  sub     rsp, 28h
0x1800049e4  mov     r8, rcx
0x1800049e7  mov     [rcx], edx
0x1800049e9  mov     ecx, edx; this
0x1800049eb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800049f0  mov     [r8+4], eax
0x1800049f4  mov     rax, r8
0x1800049f7  mov     dword ptr [r8+8], 0
0x1800049ff  add     rsp, 28h
0x180004a03  retn
```
