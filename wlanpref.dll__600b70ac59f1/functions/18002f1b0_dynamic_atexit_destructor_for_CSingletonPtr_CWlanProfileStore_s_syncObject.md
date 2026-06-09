# _dynamic_atexit_destructor_for__CSingletonPtr_CWlanProfileStore_::s_syncObject__

- ea: `0x18002f1b0`
- end: `0x18002f1be`
- name: `_dynamic_atexit_destructor_for__CSingletonPtr_CWlanProfileStore_::s_syncObject__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f1b7`

## pseudocode

```c
void dynamic_atexit_destructor_for__CSingletonPtr_CWlanProfileStore_::s_syncObject__()
{
  DeleteCriticalSection((LPCRITICAL_SECTION)CSingletonPtr<CWlanProfileStore>::s_syncObject);
}

```

## disassembly

```asm
0x18002f1b0  lea     rcx, ?s_syncObject@?$CSingletonPtr@VCWlanProfileStore@@@@0VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection CSingletonPtr<CWlanProfileStore>::s_syncObject
0x18002f1b7  jmp     cs:__imp_DeleteCriticalSection
```
