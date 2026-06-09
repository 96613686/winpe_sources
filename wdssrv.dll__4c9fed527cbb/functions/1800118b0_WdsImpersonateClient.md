# WdsImpersonateClient

- ea: `0x1800118b0`
- end: `0x1800118de`
- name: `WdsImpersonateClient`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800118b0`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall WdsImpersonateClient(__int64 a1)
{
  if ( a1 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 24) + 88LL))(
             *(_QWORD *)(a1 + 24),
             *(_QWORD *)a1);
  else
    return 87;
}

```

## disassembly

```asm
0x1800118b0  sub     rsp, 28h
0x1800118b4  mov     rdx, rcx
0x1800118b7  test    rcx, rcx
0x1800118ba  jnz     short loc_1800118C5
0x1800118bc  lea     eax, [rcx+57h]
0x1800118bf  add     rsp, 28h
0x1800118c3  retn
0x1800118c5  mov     rcx, [rcx+18h]
0x1800118c9  mov     rdx, [rdx]
0x1800118cc  mov     rax, [rcx]
0x1800118cf  mov     rax, [rax+58h]
0x1800118d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118d8  add     rsp, 28h
0x1800118dc  retn
```
