# CEventBroker::deletedRows(long,long)

- ea: `0x18000ebb0`
- end: `0x18000ebd6`
- name: `?deletedRows@CEventBroker@@UEAAJJJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ebb0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::deletedRows(CEventBroker *this, int a2, int a3)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *((_QWORD *)this + 5);
  result = 0;
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 48LL))(v3, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000ebb0  sub     rsp, 28h
0x18000ebb4  mov     rcx, [rcx+28h]
0x18000ebb8  xor     eax, eax
0x18000ebba  test    rcx, rcx
0x18000ebbd  jz      short loc_18000EBD1
0x18000ebbf  mov     rax, [rcx]
0x18000ebc2  movsxd  r8, r8d
0x18000ebc5  movsxd  rdx, edx
0x18000ebc8  mov     rax, [rax+30h]
0x18000ebcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebd1  add     rsp, 28h
0x18000ebd5  retn
```
