# CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)

- ea: `0x18005c2d4`
- end: `0x18005c35a`
- name: `?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z`
- size: `134`
- prototype: `int(HKEY, const wchar_t *, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *, void *)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055b58`
- `0x180059508`
- `0x18005b6a0`
- `0x18005c040`
- `0x18009642c`
- `0x1800bf644`
- `0x1800bff1c`

## callees

- `0x18005c2d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005c352`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005c352`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18005c31b`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18005c31b`

## pseudocode

```c
LSTATUS __fastcall CreateRegKey(
        HKEY a1,
        const wchar_t *a2,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *const a4,
        HKEY *phkResult,
        unsigned int *lpdwDisposition,
        void *a7)
{
  if ( a7 == (void *)-1LL )
    return RegCreateKeyExW(a1, a2, 0, 0, 0, samDesired, 0, phkResult, lpdwDisposition);
  else
    return RegCreateKeyTransactedW(a1, a2, 0, 0, 0, samDesired, 0, phkResult, lpdwDisposition, a7, 0);
}

```

## disassembly

```asm
0x18005c2d4  mov     r11, rsp
0x18005c2d7  sub     rsp, 68h
0x18005c2db  mov     rax, [rsp+68h+arg_30]
0x18005c2e3  xor     r9d, r9d; lpClass
0x18005c2e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005c2ea  jz      short loc_18005C326
0x18005c2ec  mov     [r11-18h], r9
0x18005c2f0  mov     [r11-20h], rax
0x18005c2f4  mov     rax, [rsp+68h+arg_28]
0x18005c2fc  mov     [r11-28h], rax
0x18005c300  mov     rax, [rsp+68h+arg_20]
0x18005c308  mov     [r11-30h], rax
0x18005c30c  mov     [r11-38h], r9
0x18005c310  mov     [r11-40h], r8d
0x18005c314  xor     r8d, r8d; Reserved
0x18005c317  mov     [r11-48h], r9d
0x18005c31b  call    cs:__imp_RegCreateKeyTransactedW
0x18005c321  add     rsp, 68h
0x18005c325  retn
0x18005c326  mov     rax, [rsp+68h+arg_28]
0x18005c32e  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18005c333  mov     rax, [rsp+68h+arg_20]
0x18005c33b  mov     [rsp+68h+phkResult], rax; phkResult
0x18005c340  mov     [rsp+68h+lpSecurityAttributes], r9; lpSecurityAttributes
0x18005c345  mov     [rsp+68h+samDesired], r8d; samDesired
0x18005c34a  xor     r8d, r8d; Reserved
0x18005c34d  mov     [rsp+68h+dwOptions], r9d; dwOptions
0x18005c352  call    cs:__imp_RegCreateKeyExW
0x18005c358  jmp     short loc_18005C321
```
