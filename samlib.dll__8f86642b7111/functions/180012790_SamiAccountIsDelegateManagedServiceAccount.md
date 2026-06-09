# SamiAccountIsDelegateManagedServiceAccount

- ea: `0x180012790`
- end: `0x180012795`
- name: `SamiAccountIsDelegateManagedServiceAccount`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008dc4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall SamiAccountIsDelegateManagedServiceAccount(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  return SamClientAccountIsDelegatedManagedServiceAccount(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180012790  jmp     ?SamClientAccountIsDelegatedManagedServiceAccount@@YAJPEAU_UNICODE_STRING@@0PEAE1@Z; SamClientAccountIsDelegatedManagedServiceAccount(_UNICODE_STRING *,_UNICODE_STRING *,uchar *,uchar *)
```
