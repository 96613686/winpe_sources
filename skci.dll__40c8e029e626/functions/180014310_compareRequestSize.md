# compareRequestSize

- ea: `0x180014310`
- end: `0x18001432d`
- name: `compareRequestSize`
- size: `29`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014310`

## pseudocode

```c
__int64 __fastcall compareRequestSize(const void *a1, const void *a2)
{
  unsigned __int64 v2; // rcx
  unsigned __int64 v3; // rdx

  v2 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
  v3 = *(_QWORD *)(*(_QWORD *)a2 + 16LL);
  if ( v3 <= v2 )
    return (unsigned int)-(v3 < v2);
  else
    return 1;
}

```

## disassembly

```asm
0x180014310  mov     rax, [rcx]
0x180014313  mov     rcx, [rax+10h]
0x180014317  mov     rax, [rdx]
0x18001431a  mov     rdx, [rax+10h]
0x18001431e  cmp     rdx, rcx
0x180014321  jbe     short loc_18001432A
0x180014323  mov     eax, 1
0x180014328  retn
0x18001432a  sbb     eax, eax
0x18001432c  retn
```
