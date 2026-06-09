# CEventBroker::aboutToDeleteRows(long,long)

- ea: `0x18000eb20`
- end: `0x18000eb46`
- name: `?aboutToDeleteRows@CEventBroker@@UEAAJJJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000eb20`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::aboutToDeleteRows(CEventBroker *this, int a2, int a3)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *((_QWORD *)this + 5);
  result = 0;
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 40LL))(v3, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000eb20  sub     rsp, 28h
0x18000eb24  mov     rcx, [rcx+28h]
0x18000eb28  xor     eax, eax
0x18000eb2a  test    rcx, rcx
0x18000eb2d  jz      short loc_18000EB41
0x18000eb2f  mov     rax, [rcx]
0x18000eb32  movsxd  r8, r8d
0x18000eb35  movsxd  rdx, edx
0x18000eb38  mov     rax, [rax+28h]
0x18000eb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb41  add     rsp, 28h
0x18000eb45  retn
```
