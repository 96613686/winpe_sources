# CEventBroker::aboutToChangeCell(long,long)

- ea: `0x18000eaf0`
- end: `0x18000eb16`
- name: `?aboutToChangeCell@CEventBroker@@UEAAJJJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000eaf0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::aboutToChangeCell(CEventBroker *this, int a2, int a3)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *((_QWORD *)this + 5);
  result = 0;
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 24LL))(v3, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000eaf0  sub     rsp, 28h
0x18000eaf4  mov     rcx, [rcx+28h]
0x18000eaf8  xor     eax, eax
0x18000eafa  test    rcx, rcx
0x18000eafd  jz      short loc_18000EB11
0x18000eaff  mov     rax, [rcx]
0x18000eb02  movsxd  r8, r8d
0x18000eb05  movsxd  rdx, edx
0x18000eb08  mov     rax, [rax+18h]
0x18000eb0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb11  add     rsp, 28h
0x18000eb15  retn
```
