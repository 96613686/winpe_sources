# MyService::FinalCleanup(void)

- ea: `0x180011c20`
- end: `0x180011c36`
- name: `?FinalCleanup@MyService@@UEAAXXZ`
- size: `22`
- prototype: `void __fastcall(MyService *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000a18c`

## string_xrefs

- `0x180011c23`: `ProcessID`

## pseudocode

```c
void __fastcall MyService::FinalCleanup(MyService *this)
{
  RegSetDWORD((HKEY)this, L"Software\\Microsoft\\WBEM\\CIMOM", L"ProcessID", 0);
}

```

## disassembly

```asm
0x180011c20  xor     r9d, r9d; unsigned int
0x180011c23  lea     r8, aProcessid; "ProcessID"
0x180011c2a  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x180011c31  jmp     ?RegSetDWORD@@YAKPEAUHKEY__@@PEBG1K@Z; RegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
```
