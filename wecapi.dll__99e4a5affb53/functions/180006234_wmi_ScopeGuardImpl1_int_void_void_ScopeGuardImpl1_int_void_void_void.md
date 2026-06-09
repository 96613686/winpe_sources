# wmi::ScopeGuardImpl1<int (*)(void *),void *>::~ScopeGuardImpl1<int (*)(void *),void *>(void)

- ea: `0x180006234`
- end: `0x180006253`
- name: `??1?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@wmi@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c504`
- `0x18000c5a6`
- `0x18000c5b8`
- `0x18000c5ca`

## callees

- `0x180006234`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wmi::ScopeGuardImpl1<int (*)(void *),void *>::~ScopeGuardImpl1<int (*)(void *),void *>(__int64 a1)
{
  __int64 result; // rax

  result = a1;
  if ( !*(_BYTE *)a1 )
    return (*(__int64 (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x180006234  sub     rsp, 28h
0x180006238  mov     rax, rcx
0x18000623b  cmp     byte ptr [rcx], 0
0x18000623e  jnz     short loc_18000624E
0x180006240  mov     rcx, [rcx+10h]
0x180006244  mov     rax, [rax+8]
0x180006248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000624d  nop
0x18000624e  add     rsp, 28h
0x180006252  retn
```
