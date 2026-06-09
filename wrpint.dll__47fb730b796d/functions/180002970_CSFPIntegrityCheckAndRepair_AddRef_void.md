# CSFPIntegrityCheckAndRepair::AddRef(void)

- ea: `0x180002970`
- end: `0x18000297d`
- name: `?AddRef@CSFPIntegrityCheckAndRepair@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::AddRef(CSFPIntegrityCheckAndRepair *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 3);
}

```

## disassembly

```asm
0x180002970  mov     eax, 1
0x180002975  lock xadd [rcx+0Ch], eax
0x18000297a  inc     eax
0x18000297c  retn
```
