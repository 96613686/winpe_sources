# CEventBroker::cellChanged(long,long)

- ea: `0x18000eb80`
- end: `0x18000eba6`
- name: `?cellChanged@CEventBroker@@UEAAJJJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000eb80`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::cellChanged(CEventBroker *this, int a2, int a3)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *((_QWORD *)this + 5);
  result = 0;
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18000eb80  sub     rsp, 28h
0x18000eb84  mov     rcx, [rcx+28h]
0x18000eb88  xor     eax, eax
0x18000eb8a  test    rcx, rcx
0x18000eb8d  jz      short loc_18000EBA1
0x18000eb8f  mov     rax, [rcx]
0x18000eb92  movsxd  r8, r8d
0x18000eb95  movsxd  rdx, edx
0x18000eb98  mov     rax, [rax+20h]
0x18000eb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eba1  add     rsp, 28h
0x18000eba5  retn
```
