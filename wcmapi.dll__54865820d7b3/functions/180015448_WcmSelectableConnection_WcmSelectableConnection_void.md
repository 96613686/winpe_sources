# WcmSelectableConnection::~WcmSelectableConnection(void)

- ea: `0x180015448`
- end: `0x180015467`
- name: `??1WcmSelectableConnection@@AEAA@XZ`
- size: `31`
- prototype: `void __fastcall(WcmSelectableConnection *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180016510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015460`

## pseudocode

```c
void __fastcall WcmSelectableConnection::~WcmSelectableConnection(struct _RTL_CRITICAL_SECTION *this)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&WcmSelectableConnection::`vftable';
  _InterlockedDecrement(&g_moduleRefs);
  DeleteCriticalSection(this + 14);
}

```

## disassembly

```asm
0x180015448  lea     rax, ??_7WcmSelectableConnection@@6B@; const WcmSelectableConnection::`vftable'
0x18001544f  mov     [rcx], rax
0x180015452  add     rcx, 230h
0x180015459  lock dec cs:?g_moduleRefs@@3JA; long g_moduleRefs
0x180015460  jmp     cs:__imp_DeleteCriticalSection
```
