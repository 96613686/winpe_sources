# CAPIDispatchSync::GetServiceStoppingEvent(CAPIDispatchSync *)

- ea: `0x1800069f4`
- end: `0x180006a01`
- name: `?GetServiceStoppingEvent@CAPIDispatchSync@@SAPEAXPEAV1@@Z`
- size: `13`
- prototype: `void *__fastcall(struct CAPIDispatchSync *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18000aefc`
- `0x18000d37c`

## callees

- `0x1800069f4`

## pseudocode

```c
void *__fastcall CAPIDispatchSync::GetServiceStoppingEvent(struct CAPIDispatchSync *a1)
{
  if ( a1 )
    return (void *)*((_QWORD *)a1 + 6);
  else
    return 0;
}

```

## disassembly

```asm
0x1800069f4  test    rcx, rcx
0x1800069f7  jz      short loc_1800069FE
0x1800069f9  mov     rax, [rcx+30h]
0x1800069fd  retn
0x1800069fe  xor     eax, eax
0x180006a00  retn
```
