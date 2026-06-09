# CbsUIHandler::Initiate(IEnumCbsUpdate *,int *)

- ea: `0x140011180`
- end: `0x14001118a`
- name: `?Initiate@CbsUIHandler@@UEAAJPEAUIEnumCbsUpdate@@PEAH@Z`
- size: `10`
- prototype: `__int64 __fastcall(CbsUIHandler *__hidden this, struct IEnumCbsUpdate *, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## pseudocode

```c
__int64 __fastcall CbsUIHandler::Initiate(CbsUIHandler *this, struct IEnumCbsUpdate *a2, int *a3)
{
  *a3 = 1;
  return 0;
}

```

## disassembly

```asm
0x140011180  mov     dword ptr [r8], 1
0x140011187  xor     eax, eax
0x140011189  retn
```
