# CEventBroker::RowChanged(long)

- ea: `0x18000e7d0`
- end: `0x18000e7f7`
- name: `?RowChanged@CEventBroker@@UEAAJJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e7d0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::RowChanged(CEventBroker *this, int a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *((_QWORD *)this + 5);
  result = 0;
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v2 + 32LL))(v2, a2, -1);
  return result;
}

```

## disassembly

```asm
0x18000e7d0  sub     rsp, 28h
0x18000e7d4  mov     rcx, [rcx+28h]
0x18000e7d8  xor     eax, eax
0x18000e7da  test    rcx, rcx
0x18000e7dd  jz      short loc_18000E7F2
0x18000e7df  mov     rax, [rcx]
0x18000e7e2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000e7e6  movsxd  rdx, edx
0x18000e7e9  mov     rax, [rax+20h]
0x18000e7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f2  add     rsp, 28h
0x18000e7f6  retn
```
