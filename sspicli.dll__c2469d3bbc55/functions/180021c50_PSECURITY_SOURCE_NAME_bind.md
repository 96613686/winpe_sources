# PSECURITY_SOURCE_NAME_bind

- ea: `0x180021c50`
- end: `0x180021c7f`
- name: `PSECURITY_SOURCE_NAME_bind`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016eb0`

## string_xrefs

- `0x180021c69`: `securityevent`

## pseudocode

```c
__int64 PSECURITY_SOURCE_NAME_bind()
{
  __int64 v1; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  LsapCreateBindingHandleForLocal(L"securityevent", qword_180024060, &v1);
  return v1;
}

```

## disassembly

```asm
0x180021c50  sub     rsp, 28h
0x180021c54  lea     r8, [rsp+28h+arg_8]
0x180021c59  mov     [rsp+28h+arg_8], 0
0x180021c62  lea     rdx, qword_180024060
0x180021c69  lea     rcx, aSecurityevent; "securityevent"
0x180021c70  call    LsapCreateBindingHandleForLocal
0x180021c75  mov     rax, [rsp+28h+arg_8]
0x180021c7a  add     rsp, 28h
0x180021c7e  retn
```
