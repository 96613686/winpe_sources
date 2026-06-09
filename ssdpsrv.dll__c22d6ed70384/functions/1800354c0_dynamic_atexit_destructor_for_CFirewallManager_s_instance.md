# _dynamic_atexit_destructor_for__CFirewallManager::s_instance__

- ea: `0x1800354c0`
- end: `0x1800354e2`
- name: `_dynamic_atexit_destructor_for__CFirewallManager::s_instance__`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022868`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800354db`

## pseudocode

```c
void dynamic_atexit_destructor_for__CFirewallManager::s_instance__()
{
  CFirewallManager::HrShutdown((CFirewallManager *)&CFirewallManager::s_instance);
  DeleteCriticalSection(&stru_180041070);
}

```

## disassembly

```asm
0x1800354c0  sub     rsp, 28h
0x1800354c4  lea     rcx, ?s_instance@CFirewallManager@@0V1@A; this
0x1800354cb  call    ?HrShutdown@CFirewallManager@@QEAAJXZ; CFirewallManager::HrShutdown(void)
0x1800354d0  lea     rcx, stru_180041070
0x1800354d7  add     rsp, 28h
0x1800354db  jmp     cs:__imp_DeleteCriticalSection
```
