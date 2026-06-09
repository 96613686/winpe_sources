# SaslEnumerateProfilesW

- ea: `0x180019c10`
- end: `0x180019c15`
- name: `SaslEnumerateProfilesW`
- size: `5`
- prototype: `SECURITY_STATUS __stdcall(LPWSTR *ProfileList, ULONG *ProfileCount)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d25c`

## pseudocode

```c
// attributes: thunk
SECURITY_STATUS __stdcall SaslEnumerateProfilesW(LPWSTR *ProfileList, ULONG *ProfileCount)
{
  return SecEnumerateSaslProfilesW(ProfileList, ProfileCount);
}

```

## disassembly

```asm
0x180019c10  jmp     SecEnumerateSaslProfilesW
```
