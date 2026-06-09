# GetSecurityUserInfo

- ea: `0x18001fe80`
- end: `0x18001fe85`
- name: `GetSecurityUserInfo`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002145c`

## pseudocode

```c
// attributes: thunk
__int64 GetSecurityUserInfo()
{
  return SecpGetUserInfo();
}

```

## disassembly

```asm
0x18001fe80  jmp     SecpGetUserInfo
```
