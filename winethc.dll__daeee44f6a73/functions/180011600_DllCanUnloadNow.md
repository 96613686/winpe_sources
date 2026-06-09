# DllCanUnloadNow

- ea: `0x180011600`
- end: `0x18001162a`
- name: `DllCanUnloadNow`
- size: `42`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180014010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(qword_18001BE10 + 24LL))(&qword_18001BE10) != 0;
}

```

## disassembly

```asm
0x180011600  sub     rsp, 28h
0x180011604  mov     rax, cs:qword_18001BE10
0x18001160b  lea     rcx, qword_18001BE10
0x180011612  mov     rax, [rax+18h]
0x180011616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001161b  xor     ecx, ecx
0x18001161d  test    eax, eax
0x18001161f  setnz   cl
0x180011622  mov     eax, ecx
0x180011624  add     rsp, 28h
0x180011628  retn
```
