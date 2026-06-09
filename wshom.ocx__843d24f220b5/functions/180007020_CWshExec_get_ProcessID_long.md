# CWshExec::get_ProcessID(long *)

- ea: `0x180007020`
- end: `0x180007033`
- name: `?get_ProcessID@CWshExec@@UEAAJPEAJ@Z`
- size: `19`
- prototype: `__int64 __fastcall(CWshExec *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180007020`

## pseudocode

```c
__int64 __fastcall CWshExec::get_ProcessID(CWshExec *this, int *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = *((_DWORD *)this + 24);
  return 0;
}

```

## disassembly

```asm
0x180007020  test    rdx, rdx
0x180007023  jnz     short loc_18000702B
0x180007025  mov     eax, 80004003h
0x18000702a  retn
0x18000702b  mov     eax, [rcx+60h]
0x18000702e  mov     [rdx], eax
0x180007030  xor     eax, eax
0x180007032  retn
```
