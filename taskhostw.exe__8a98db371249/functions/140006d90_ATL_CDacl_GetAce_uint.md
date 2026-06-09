# ATL::CDacl::GetAce(uint)

- ea: `0x140006d90`
- end: `0x140006db4`
- name: `?GetAce@CDacl@ATL@@EEBAPEBVCAce@CAcl@2@I@Z`
- size: `36`
- prototype: `const struct ATL::CAcl::CAce *__fastcall(ATL::CDacl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140006d90`
- `0x1400072bc`

## pseudocode

```c
const struct ATL::CAcl::CAce *__fastcall ATL::CDacl::GetAce(ATL::CDacl *this, unsigned int a2)
{
  if ( (unsigned __int64)a2 >= *((_QWORD *)this + 4) )
    ATL::PrivateAtlThrow(-2147024809);
  return *(const struct ATL::CAcl::CAce **)(*((_QWORD *)this + 3) + 8LL * a2);
}

```

## disassembly

```asm
0x140006d90  sub     rsp, 28h
0x140006d94  mov     eax, edx
0x140006d96  cmp     rax, [rcx+20h]
0x140006d9a  jnb     short loc_140006DA9
0x140006d9c  mov     rcx, [rcx+18h]
0x140006da0  mov     rax, [rcx+rax*8]
0x140006da4  add     rsp, 28h
0x140006da8  retn
0x140006da9  mov     ecx, 80070057h; int
0x140006dae  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
