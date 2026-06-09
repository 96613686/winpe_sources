# SspirConnectRpc

- ea: `0x180001b50`
- end: `0x180001ba4`
- name: `SspirConnectRpc`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001b50`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirConnectRpc(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64, __int64, __int64); // rax

  if ( gLsapSspiExtension
    && (v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64))(gLsapSspiExtension + 24)) != 0 )
  {
    return v6(a2, a3, a4, a5, a6);
  }
  else
  {
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x180001b50  push    rbx
0x180001b52  sub     rsp, 30h
0x180001b56  mov     rax, cs:gLsapSspiExtension
0x180001b5d  mov     r10, r9
0x180001b60  mov     r11d, r8d
0x180001b63  mov     rbx, rdx
0x180001b66  test    rax, rax
0x180001b69  jz      short loc_180001B74
0x180001b6b  mov     rax, [rax+18h]
0x180001b6f  test    rax, rax
0x180001b72  jnz     short loc_180001B80
0x180001b74  mov     eax, 0C00000BBh
0x180001b79  add     rsp, 30h
0x180001b7d  pop     rbx
0x180001b7e  retn
0x180001b80  mov     rcx, [rsp+38h+arg_28]
0x180001b85  mov     r8, r10
0x180001b88  mov     r9, [rsp+38h+arg_20]
0x180001b8d  mov     edx, r11d
0x180001b90  mov     [rsp+38h+var_18], rcx
0x180001b95  mov     rcx, rbx
0x180001b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b9d  add     rsp, 30h
0x180001ba1  pop     rbx
0x180001ba2  retn
```
