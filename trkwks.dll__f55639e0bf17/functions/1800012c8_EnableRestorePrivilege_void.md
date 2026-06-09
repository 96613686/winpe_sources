# EnableRestorePrivilege(void)

- ea: `0x1800012c8`
- end: `0x1800012e1`
- name: `?EnableRestorePrivilege@@YAXXZ`
- size: `25`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180001008`
- `0x180002f24`
- `0x18000f984`

## callees

- `0x1800012c8`
- `0x18000c078`

## pseudocode

```c
void EnableRestorePrivilege(void)
{
  if ( !g_fRestorePrivilegeEnabled )
  {
    g_fRestorePrivilegeEnabled = 1;
    EnablePrivilege();
  }
}

```

## disassembly

```asm
0x1800012c8  cmp     cs:?g_fRestorePrivilegeEnabled@@3HA, 0; int g_fRestorePrivilegeEnabled
0x1800012cf  jz      short loc_1800012D2
0x1800012d1  retn
0x1800012d2  mov     cs:?g_fRestorePrivilegeEnabled@@3HA, 1; int g_fRestorePrivilegeEnabled
0x1800012dc  jmp     ?EnablePrivilege@@YAHJ@Z; EnablePrivilege(long)
```
