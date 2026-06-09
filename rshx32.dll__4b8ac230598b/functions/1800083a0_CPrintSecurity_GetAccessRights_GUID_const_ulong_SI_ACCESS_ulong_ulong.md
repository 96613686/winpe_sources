# CPrintSecurity::GetAccessRights(_GUID const *,ulong,_SI_ACCESS * *,ulong *,ulong *)

- ea: `0x1800083a0`
- end: `0x1800083e7`
- name: `?GetAccessRights@CPrintSecurity@@UEAAJPEBU_GUID@@KPEAPEAU_SI_ACCESS@@PEAK2@Z`
- size: `71`
- prototype: `__int64 __fastcall(CPrintSecurity *this, const struct _GUID *, char, struct _SI_ACCESS near ***, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800083a0`

## pseudocode

```c
__int64 __fastcall CPrintSecurity::GetAccessRights(
        CPrintSecurity *this,
        const struct _GUID *a2,
        char a3,
        struct _SI_ACCESS near ***a4,
        unsigned int *a5,
        unsigned int *a6)
{
  struct _SI_ACCESS near **v6; // rax
  __int64 result; // rax

  if ( !a4 || !a5 || !a6 )
    return 2147500035LL;
  v6 = &siPrintAudits;
  if ( (a3 & 2) == 0 )
    v6 = &siPrintAccesses;
  *a4 = v6;
  result = 0;
  *a5 = 8;
  *a6 = 0;
  return result;
}

```

## disassembly

```asm
0x1800083a0  test    r9, r9
0x1800083a3  jz      short loc_1800083E1
0x1800083a5  mov     rcx, [rsp+arg_20]
0x1800083aa  test    rcx, rcx
0x1800083ad  jz      short loc_1800083E1
0x1800083af  mov     rdx, [rsp+arg_28]
0x1800083b4  test    rdx, rdx
0x1800083b7  jz      short loc_1800083E1
0x1800083b9  test    r8b, 2
0x1800083bd  lea     rax, ?siPrintAudits@@3PAU_SI_ACCESS@@A; _SI_ACCESS near * siPrintAudits
0x1800083c4  lea     r8, ?siPrintAccesses@@3PAU_SI_ACCESS@@A; _SI_ACCESS near * siPrintAccesses
0x1800083cb  cmovz   rax, r8
0x1800083cf  mov     [r9], rax
0x1800083d2  xor     eax, eax
0x1800083d4  mov     dword ptr [rcx], 8
0x1800083da  mov     dword ptr [rdx], 0
0x1800083e0  retn
0x1800083e1  mov     eax, 80004003h
0x1800083e6  retn
```
