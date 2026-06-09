# CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::_StandardDestroyCB(_SID *,void *)

- ea: `0x18000bda0`
- end: `0x18000bda6`
- name: `?_StandardDestroyCB@?$CDPA_Base@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@CAHPEAU_SID@@PEAX@Z`
- size: `6`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c3b8`

## pseudocode

```c
__int64 __fastcall CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::_StandardDestroyCB(void *p, void *pData)
{
  return 1;
}

```

## disassembly

```asm
0x18000bda0  mov     eax, 1
0x18000bda5  retn
```
