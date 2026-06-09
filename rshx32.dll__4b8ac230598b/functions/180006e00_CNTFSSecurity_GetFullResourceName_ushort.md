# CNTFSSecurity::GetFullResourceName(ushort * *)

- ea: `0x180006e00`
- end: `0x180006e15`
- name: `?GetFullResourceName@CNTFSSecurity@@UEAAJPEAPEAG@Z`
- size: `21`
- prototype: `__int64 __fastcall(CNTFSSecurity *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006e00`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::GetFullResourceName(CNTFSSecurity *this, unsigned __int16 **a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = (unsigned __int16 *)*((_QWORD *)this + 3);
  return 0;
}

```

## disassembly

```asm
0x180006e00  test    rdx, rdx
0x180006e03  jnz     short loc_180006E0B
0x180006e05  mov     eax, 80004003h
0x180006e0a  retn
0x180006e0b  mov     rax, [rcx+18h]
0x180006e0f  mov     [rdx], rax
0x180006e12  xor     eax, eax
0x180006e14  retn
```
