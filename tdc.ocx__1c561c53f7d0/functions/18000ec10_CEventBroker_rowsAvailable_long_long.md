# CEventBroker::rowsAvailable(long,long)

- ea: `0x18000ec10`
- end: `0x18000ec36`
- name: `?rowsAvailable@CEventBroker@@UEAAJJJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ec10`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::rowsAvailable(CEventBroker *this, int a2, int a3)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *((_QWORD *)this + 5);
  result = 0;
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 72LL))(v3, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000ec10  sub     rsp, 28h
0x18000ec14  mov     rcx, [rcx+28h]
0x18000ec18  xor     eax, eax
0x18000ec1a  test    rcx, rcx
0x18000ec1d  jz      short loc_18000EC31
0x18000ec1f  mov     rax, [rcx]
0x18000ec22  movsxd  r8, r8d
0x18000ec25  movsxd  rdx, edx
0x18000ec28  mov     rax, [rax+48h]
0x18000ec2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec31  add     rsp, 28h
0x18000ec35  retn
```
