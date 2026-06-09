# __security_check_cookie

- ea: `0x180001d60`
- end: `0x180001d7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `50`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180005268`
- `0x1800059a8`
- `0x18000669c`
- `0x1800087c0`
- `0x180008c54`
- `0x1800091dc`
- `0x180009df8`
- `0x18000a9f0`
- `0x18000b13c`
- `0x18000d1e4`
- `0x18000e640`
- `0x18000e99c`
- `0x18000ec90`
- `0x18000f020`
- `0x18000f1cc`
- `0x18000f95c`
- `0x18000fbd0`
- `0x18000fd88`
- `0x1800100ac`
- `0x180010590`
- `0x180010914`
- `0x180010bec`
- `0x180011390`
- `0x180011e10`
- `0x180011f80`
- `0x1800120ec`
- `0x1800125c0`
- `0x180012cb0`
- `0x180013490`
- `0x1800142d0`
- `0x18001458c`
- `0x180014ba4`
- `0x180014cdc`
- `0x1800150b0`
- `0x1800161bc`
- `0x180018400`
- `0x1800185c0`
- `0x180019460`
- `0x1800196fc`
- `0x180019824`
- `0x180019a58`
- `0x180019cb8`
- `0x18001a05c`
- `0x18001a8c4`
- `0x18001ac3c`
- `0x18001b6b8`
- `0x18001c66c`
- `0x18001d210`

## callees

- `0x180001d60`
- `0x180001d90`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180001d60  cmp     rcx, cs:__security_cookie
0x180001d67  jnz     short ReportFailure
0x180001d69  rol     rcx, 10h
0x180001d6d  test    cx, 0FFFFh
0x180001d72  jnz     short RestoreRcx
0x180001d74  retn
0x180001d75  ror     rcx, 10h; StackCookie
0x180001d79  jmp     __report_gsfailure
```
