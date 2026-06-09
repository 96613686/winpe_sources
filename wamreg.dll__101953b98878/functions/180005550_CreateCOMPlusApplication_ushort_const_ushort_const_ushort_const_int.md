# CreateCOMPlusApplication(ushort const *,ushort const *,ushort const *,int *)

- ea: `0x180005550`
- end: `0x180005556`
- name: `?CreateCOMPlusApplication@@YAJPEBG00PEAH@Z`
- size: `6`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CreateCOMPlusApplication(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180005550  mov     eax, 80004001h; CreateIISPackage
0x180005555  retn
```
