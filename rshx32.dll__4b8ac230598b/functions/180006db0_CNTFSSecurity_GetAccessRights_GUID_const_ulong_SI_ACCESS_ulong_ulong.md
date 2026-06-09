# CNTFSSecurity::GetAccessRights(_GUID const *,ulong,_SI_ACCESS * *,ulong *,ulong *)

- ea: `0x180006db0`
- end: `0x180006df9`
- name: `?GetAccessRights@CNTFSSecurity@@UEAAJPEBU_GUID@@KPEAPEAU_SI_ACCESS@@PEAK2@Z`
- size: `73`
- prototype: `__int64 __fastcall(CNTFSSecurity *this, const struct _GUID *, __int64, struct _SI_ACCESS **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006db0`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::GetAccessRights(
        CNTFSSecurity *this,
        const struct _GUID *a2,
        __int64 a3,
        struct _SI_ACCESS **a4,
        unsigned int *a5,
        unsigned int *a6)
{
  __int64 result; // rax

  if ( !a4 || !a5 || !a6 )
    return 2147500035LL;
  dword_1800283F8 = (*((_BYTE *)this + 64) & 4) << 14;
  *a4 = (struct _SI_ACCESS *)&siNTFSAccesses;
  result = 0;
  *a5 = 23;
  *a6 = 2;
  return result;
}

```

## disassembly

```asm
0x180006db0  test    r9, r9
0x180006db3  jz      short loc_180006DF3
0x180006db5  mov     rdx, [rsp+arg_20]
0x180006dba  test    rdx, rdx
0x180006dbd  jz      short loc_180006DF3
0x180006dbf  mov     r8, [rsp+arg_28]
0x180006dc4  test    r8, r8
0x180006dc7  jz      short loc_180006DF3
0x180006dc9  movzx   eax, byte ptr [rcx+40h]
0x180006dcd  and     eax, 4
0x180006dd0  shl     eax, 0Eh
0x180006dd3  mov     cs:dword_1800283F8, eax
0x180006dd9  lea     rax, ?siNTFSAccesses@@3PAU_SI_ACCESS@@A; _SI_ACCESS near * siNTFSAccesses
0x180006de0  mov     [r9], rax
0x180006de3  xor     eax, eax
0x180006de5  mov     dword ptr [rdx], 17h
0x180006deb  mov     dword ptr [r8], 2
0x180006df2  retn
0x180006df3  mov     eax, 80004003h
0x180006df8  retn
```
