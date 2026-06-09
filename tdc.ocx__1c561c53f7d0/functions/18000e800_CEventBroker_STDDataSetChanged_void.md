# CEventBroker::STDDataSetChanged(void)

- ea: `0x18000e800`
- end: `0x18000e843`
- name: `?STDDataSetChanged@CEventBroker@@UEAAJXZ`
- size: `67`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e800`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::STDDataSetChanged(CEventBroker *this)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  result = 0;
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
    result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 24LL))(v3, 0);
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v4 + 24LL))(v4, 0, 1);
  return result;
}

```

## disassembly

```asm
0x18000e800  push    rbx
0x18000e802  sub     rsp, 20h
0x18000e806  mov     rbx, rcx
0x18000e809  xor     eax, eax
0x18000e80b  mov     rcx, [rcx+18h]
0x18000e80f  test    rcx, rcx
0x18000e812  jz      short loc_18000E822
0x18000e814  mov     rax, [rcx]
0x18000e817  xor     edx, edx
0x18000e819  mov     rax, [rax+18h]
0x18000e81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e822  mov     rcx, [rbx+20h]
0x18000e826  test    rcx, rcx
0x18000e829  jz      short loc_18000E83D
0x18000e82b  mov     rax, [rcx]
0x18000e82e  xor     edx, edx
0x18000e830  mov     rax, [rax+18h]
0x18000e834  lea     r8d, [rdx+1]
0x18000e838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e83d  add     rsp, 20h
0x18000e841  pop     rbx
0x18000e842  retn
```
