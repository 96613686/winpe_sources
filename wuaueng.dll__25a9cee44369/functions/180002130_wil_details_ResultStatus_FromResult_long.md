# wil::details::ResultStatus::FromResult(long)

- ea: `0x180002130`
- end: `0x180002154`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003674`
- `0x1800036d8`
- `0x180008554`
- `0x180008670`
- `0x180009e04`

## callees

- `0x180002580`

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
0x180002130  sub     rsp, 28h
0x180002134  mov     r8, rcx
0x180002137  mov     [rcx], edx
0x180002139  mov     ecx, edx; this
0x18000213b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002140  mov     [r8+4], eax
0x180002144  mov     rax, r8
0x180002147  mov     dword ptr [r8+8], 0
0x18000214f  add     rsp, 28h
0x180002153  retn
```
