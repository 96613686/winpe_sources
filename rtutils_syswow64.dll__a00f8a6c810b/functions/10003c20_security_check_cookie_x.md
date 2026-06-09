# __security_check_cookie(x)

- ea: `0x10003c20`
- end: `0x10003c2e`
- name: `@__security_check_cookie@4`
- size: `14`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100020d0`
- `0x10002870`
- `0x10003000`
- `0x100032d0`
- `0x100049a9`
- `0x10004ab6`
- `0x10004de8`
- `0x10004ef5`
- `0x10005dd0`
- `0x100062d0`
- `0x10006770`
- `0x10006b80`
- `0x10006fd6`
- `0x10007174`
- `0x100075de`
- `0x10007954`
- `0x10007bcc`
- `0x100080a7`
- `0x100083b2`
- `0x100086c3`
- `0x1000872c`
- `0x10008cb0`
- `0x10008d80`
- `0x10009330`
- `0x10009400`
- `0x1000976a`
- `0x10009977`
- `0x10009dd0`
- `0x1000a2ae`

## callees

- `0x10003c20`
- `0x10003c34`

## pseudocode

```c
void __fastcall __security_check_cookie(uintptr_t StackCookie)
{
  if ( StackCookie != __security_cookie )
    __report_gsfailure();
}

```

## disassembly

```asm
0x10003c20  cmp     ecx, ___security_cookie
0x10003c26  jnz     short loc_10003C29
0x10003c28  retn
0x10003c29  jmp     ___report_gsfailure
```
