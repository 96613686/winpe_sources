# CUwfConfiguration::OpenKey(HKEY__ *,ushort const *,ulong,CUwfRegKey &)

- ea: `0x180008900`
- end: `0x18000891e`
- name: `?OpenKey@CUwfConfiguration@@QEAAJPEAUHKEY__@@PEBGKAEAVCUwfRegKey@@@Z`
- size: `30`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, HKEY, const unsigned __int16 *, REGSAM, PHKEY phkResult)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180008900`
- `0x18000de30`
- `0x18000df60`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::OpenKey(
        CUwfConfiguration *this,
        HKEY a2,
        const unsigned __int16 *a3,
        REGSAM a4,
        PHKEY phkResult)
{
  void *v5; // rax

  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 == (void *)-1LL )
    return CUwfRegKey::Open(phkResult, a2, a3, a4);
  else
    return CUwfRegKey::OpenTransacted(phkResult, a2, a3, a4, v5);
}

```

## disassembly

```asm
0x180008900  mov     rax, [rcx+8]
0x180008904  mov     rcx, [rsp+phkResult]; phkResult
0x180008909  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000890d  jz      short loc_180008919
0x18000890f  mov     [rsp+phkResult], rax; HANDLE
0x180008914  jmp     ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x180008919  jmp     ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
```
