# User::IsLocalAdmin(void)

- ea: `0x180028ce0`
- end: `0x180028dcc`
- name: `?IsLocalAdmin@User@@QEBA_NXZ`
- size: `236`
- prototype: `char __fastcall(User *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c1b0`
- `0x180045df0`

## callees

- `0x180028ce0`
- `0x180028dd4`
- `0x180042f40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180028da4`
- `msvcrt!_wcsicmp` at `0x180028da4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028d20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028db3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028d20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028db3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028d04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028d04`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180028d5a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180028d5a`

## pseudocode

```c

```
