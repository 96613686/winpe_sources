# CEventBroker::insertedRows(long,long)

- ea: `0x18000ebe0`
- end: `0x18000ec06`
- name: `?insertedRows@CEventBroker@@UEAAJJJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ebe0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::insertedRows(CEventBroker *this, int a2, int a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 5);
  if ( v3 )
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 64LL))(v3, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x18000ebe0  sub     rsp, 28h
0x18000ebe4  mov     rcx, [rcx+28h]
0x18000ebe8  test    rcx, rcx
0x18000ebeb  jz      short loc_18000EBFF
0x18000ebed  mov     rax, [rcx]
0x18000ebf0  movsxd  r8, r8d
0x18000ebf3  movsxd  rdx, edx
0x18000ebf6  mov     rax, [rax+40h]
0x18000ebfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebff  xor     eax, eax
0x18000ec01  add     rsp, 28h
0x18000ec05  retn
```
