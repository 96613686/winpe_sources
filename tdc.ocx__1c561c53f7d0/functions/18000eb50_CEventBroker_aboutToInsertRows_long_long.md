# CEventBroker::aboutToInsertRows(long,long)

- ea: `0x18000eb50`
- end: `0x18000eb76`
- name: `?aboutToInsertRows@CEventBroker@@UEAAJJJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000eb50`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::aboutToInsertRows(CEventBroker *this, int a2, int a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 5);
  if ( v3 )
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 56LL))(v3, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x18000eb50  sub     rsp, 28h
0x18000eb54  mov     rcx, [rcx+28h]
0x18000eb58  test    rcx, rcx
0x18000eb5b  jz      short loc_18000EB6F
0x18000eb5d  mov     rax, [rcx]
0x18000eb60  movsxd  r8, r8d
0x18000eb63  movsxd  rdx, edx
0x18000eb66  mov     rax, [rax+38h]
0x18000eb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb6f  xor     eax, eax
0x18000eb71  add     rsp, 28h
0x18000eb75  retn
```
