# CFirewallManager::~CFirewallManager(void)

- ea: `0x180027b80`
- end: `0x180027ba3`
- name: `??1CFirewallManager@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(CFirewallManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800380a0`

## callees

- `0x180024254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027b97`

## pseudocode

```c
void __fastcall CFirewallManager::~CFirewallManager(CFirewallManager *this)
{
  CFirewallManager::HrShutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180027b80  push    rbx
0x180027b82  sub     rsp, 20h
0x180027b86  mov     rbx, rcx
0x180027b89  call    ?HrShutdown@CFirewallManager@@QEAAJXZ; CFirewallManager::HrShutdown(void)
0x180027b8e  lea     rcx, [rbx+10h]
0x180027b92  add     rsp, 20h
0x180027b96  pop     rbx
0x180027b97  jmp     cs:__imp_DeleteCriticalSection
```
