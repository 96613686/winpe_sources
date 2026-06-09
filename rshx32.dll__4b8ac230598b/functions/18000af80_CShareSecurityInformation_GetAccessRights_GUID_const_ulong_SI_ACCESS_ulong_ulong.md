# CShareSecurityInformation::GetAccessRights(_GUID const *,ulong,_SI_ACCESS * *,ulong *,ulong *)

- ea: `0x18000af80`
- end: `0x18000afa3`
- name: `?GetAccessRights@CShareSecurityInformation@@UEAAJPEBU_GUID@@KPEAPEAU_SI_ACCESS@@PEAK2@Z`
- size: `35`
- prototype: `__int64 __fastcall(CShareSecurityInformation *this, const struct _GUID *, __int64, struct _SI_ACCESS **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CShareSecurityInformation::GetAccessRights(
        CShareSecurityInformation *this,
        const struct _GUID *a2,
        __int64 a3,
        struct _SI_ACCESS **a4,
        unsigned int *a5,
        unsigned int *a6)
{
  *a4 = (struct _SI_ACCESS *)&siShareAccesses;
  *a5 = 3;
  *a6 = 2;
  return 0;
}

```

## disassembly

```asm
0x18000af80  lea     rax, ?siShareAccesses@@3PAU_SI_ACCESS@@A; _SI_ACCESS near * siShareAccesses
0x18000af87  mov     [r9], rax
0x18000af8a  mov     rax, [rsp+arg_20]
0x18000af8f  mov     dword ptr [rax], 3
0x18000af95  mov     rax, [rsp+arg_28]
0x18000af9a  mov     dword ptr [rax], 2
0x18000afa0  xor     eax, eax
0x18000afa2  retn
```
