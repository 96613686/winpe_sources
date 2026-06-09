# SaslEnumerateProfilesA

- ea: `0x180019c00`
- end: `0x180019c05`
- name: `SaslEnumerateProfilesA`
- size: `5`
- prototype: `SECURITY_STATUS __stdcall(LPSTR *ProfileList, ULONG *ProfileCount)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d124`

## pseudocode

```c
// attributes: thunk
SECURITY_STATUS __stdcall SaslEnumerateProfilesA(LPSTR *ProfileList, ULONG *ProfileCount)
{
  return SecEnumerateSaslProfilesA(ProfileList, ProfileCount);
}

```

## disassembly

```asm
0x180019c00  jmp     SecEnumerateSaslProfilesA
```
