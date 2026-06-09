# CEventBroker::ColChanged(long)

- ea: `0x18000e750`
- end: `0x18000e777`
- name: `?ColChanged@CEventBroker@@UEAAJJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e750`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::ColChanged(CEventBroker *this, int a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *((_QWORD *)this + 5);
  result = 0;
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v2 + 32LL))(v2, -1, a2);
  return result;
}

```

## disassembly

```asm
0x18000e750  sub     rsp, 28h
0x18000e754  mov     rcx, [rcx+28h]
0x18000e758  xor     eax, eax
0x18000e75a  test    rcx, rcx
0x18000e75d  jz      short loc_18000E772
0x18000e75f  mov     rax, [rcx]
0x18000e762  movsxd  r8, edx
0x18000e765  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000e769  mov     rax, [rax+20h]
0x18000e76d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e772  add     rsp, 28h
0x18000e776  retn
```
