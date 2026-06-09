# WdsProviderServiceControl(void *,ulong)

- ea: `0x180007670`
- end: `0x18000768d`
- name: `?WdsProviderServiceControl@@YAXPEAXK@Z`
- size: `29`
- prototype: `void __fastcall(void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180002268`
- `0x180007670`

## pseudocode

```c
void __fastcall WdsProviderServiceControl(void *a1, int a2)
{
  if ( a2 == 128 )
    CWdsDeviceControllerManager::RefreshSettings(&CriticalSection);
}

```

## disassembly

```asm
0x180007670  sub     rsp, 28h
0x180007674  cmp     edx, 80h
0x18000767a  jnz     short loc_180007688
0x18000767c  lea     rcx, CriticalSection; lpCriticalSection
0x180007683  call    ?RefreshSettings@CWdsDeviceControllerManager@@AEAAKXZ; CWdsDeviceControllerManager::RefreshSettings(void)
0x180007688  add     rsp, 28h
0x18000768c  retn
```
