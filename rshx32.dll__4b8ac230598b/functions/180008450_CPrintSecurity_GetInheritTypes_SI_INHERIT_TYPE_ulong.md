# CPrintSecurity::GetInheritTypes(_SI_INHERIT_TYPE * *,ulong *)

- ea: `0x180008450`
- end: `0x180008474`
- name: `?GetInheritTypes@CPrintSecurity@@UEAAJPEAPEAU_SI_INHERIT_TYPE@@PEAK@Z`
- size: `36`
- prototype: `__int64 __fastcall(CPrintSecurity *__hidden this, struct _SI_INHERIT_TYPE **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008450`

## pseudocode

```c
__int64 __fastcall CPrintSecurity::GetInheritTypes(
        CPrintSecurity *this,
        struct _SI_INHERIT_TYPE **a2,
        unsigned int *a3)
{
  __int64 result; // rax

  if ( a2 || a3 )
    return 2147500035LL;
  MEMORY[0] = &siPrintInheritTypes;
  result = 0;
  MEMORY[0] = 3;
  return result;
}

```

## disassembly

```asm
0x180008450  test    rdx, rdx
0x180008453  jnz     short loc_18000846E
0x180008455  test    r8, r8
0x180008458  jnz     short loc_18000846E
0x18000845a  lea     rax, ?siPrintInheritTypes@@3PAU_SI_INHERIT_TYPE@@A; _SI_INHERIT_TYPE near * siPrintInheritTypes
0x180008461  mov     [rdx], rax
0x180008464  xor     eax, eax
0x180008466  mov     dword ptr [r8], 3
0x18000846d  retn
0x18000846e  mov     eax, 80004003h
0x180008473  retn
```
