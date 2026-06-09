# wil::details::ResultStatus::FromResult(long)

- ea: `0x1800046d8`
- end: `0x1800046fc`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032a4`
- `0x180003480`
- `0x180006ea0`
- `0x180006f18`
- `0x180006fa4`

## callees

- `0x18000510c`

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
0x1800046d8  sub     rsp, 28h
0x1800046dc  mov     r8, rcx
0x1800046df  mov     [rcx], edx
0x1800046e1  mov     ecx, edx; this
0x1800046e3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800046e8  mov     [r8+4], eax
0x1800046ec  mov     rax, r8
0x1800046ef  mov     dword ptr [r8+8], 0
0x1800046f7  add     rsp, 28h
0x1800046fb  retn
```
