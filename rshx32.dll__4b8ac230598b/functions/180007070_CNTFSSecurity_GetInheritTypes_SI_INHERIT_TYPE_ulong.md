# CNTFSSecurity::GetInheritTypes(_SI_INHERIT_TYPE * *,ulong *)

- ea: `0x180007070`
- end: `0x1800070a0`
- name: `?GetInheritTypes@CNTFSSecurity@@UEAAJPEAPEAU_SI_INHERIT_TYPE@@PEAK@Z`
- size: `48`
- prototype: `__int64 __fastcall(CNTFSSecurity *__hidden this, struct _SI_INHERIT_TYPE **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007070`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::GetInheritTypes(CNTFSSecurity *this, struct _SI_INHERIT_TYPE **a2, unsigned int *a3)
{
  __int64 result; // rax

  if ( !a2 || !a3 )
    return 2147500035LL;
  if ( (*((_BYTE *)this + 64) & 4) == 0 )
    return 2147500033LL;
  *a2 = (struct _SI_INHERIT_TYPE *)&siNTFSInheritTypes;
  result = 0;
  *a3 = 7;
  return result;
}

```

## disassembly

```asm
0x180007070  test    rdx, rdx
0x180007073  jz      short loc_18000709A
0x180007075  test    r8, r8
0x180007078  jz      short loc_18000709A
0x18000707a  test    byte ptr [rcx+40h], 4
0x18000707e  jz      short loc_180007094
0x180007080  lea     rax, ?siNTFSInheritTypes@@3PAU_SI_INHERIT_TYPE@@A; _SI_INHERIT_TYPE near * siNTFSInheritTypes
0x180007087  mov     [rdx], rax
0x18000708a  xor     eax, eax
0x18000708c  mov     dword ptr [r8], 7
0x180007093  retn
0x180007094  mov     eax, 80004001h
0x180007099  retn
0x18000709a  mov     eax, 80004003h
0x18000709f  retn
```
