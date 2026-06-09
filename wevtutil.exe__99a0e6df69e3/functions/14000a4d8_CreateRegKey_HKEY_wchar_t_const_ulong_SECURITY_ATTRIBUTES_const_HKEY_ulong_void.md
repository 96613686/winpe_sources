# CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)

- ea: `0x14000a4d8`
- end: `0x14000a56c`
- name: `?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z`
- size: `148`
- prototype: `int(HKEY, const wchar_t *, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *, void *)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009b58`
- `0x14001291c`
- `0x140013658`
- `0x140014988`
- `0x1400151ec`
- `0x14001663c`
- `0x14001e458`
- `0x14002ab70`
- `0x14002bd08`
- `0x14002ecf4`

## callees

- `0x14000a4d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000a561`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000a561`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x14000a527`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x14000a527`

## pseudocode

```c
LSTATUS __fastcall CreateRegKey(
        HKEY a1,
        const wchar_t *a2,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *const lpSecurityAttributes,
        HKEY *phkResult,
        unsigned int *lpdwDisposition,
        void *a7)
{
  if ( a7 == (void *)-1LL )
    return RegCreateKeyExW(a1, a2, 0, 0, 0, samDesired, lpSecurityAttributes, phkResult, lpdwDisposition);
  else
    return RegCreateKeyTransactedW(a1, a2, 0, 0, 0, samDesired, lpSecurityAttributes, phkResult, lpdwDisposition, a7, 0);
}

```

## disassembly

```asm
0x14000a4d8  mov     r11, rsp
0x14000a4db  sub     rsp, 68h
0x14000a4df  mov     rax, [rsp+68h+arg_30]
0x14000a4e7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a4eb  jz      short loc_14000A52F
0x14000a4ed  mov     qword ptr [r11-18h], 0
0x14000a4f5  mov     [r11-20h], rax
0x14000a4f9  mov     rax, [rsp+68h+arg_28]
0x14000a501  mov     [r11-28h], rax
0x14000a505  mov     rax, [rsp+68h+arg_20]
0x14000a50d  mov     [r11-30h], rax
0x14000a511  mov     [r11-38h], r9
0x14000a515  xor     r9d, r9d; lpClass
0x14000a518  mov     [r11-40h], r8d
0x14000a51c  xor     r8d, r8d; Reserved
0x14000a51f  mov     [rsp+68h+dwOptions], 0; dwOptions
0x14000a527  call    cs:__imp_RegCreateKeyTransactedW
0x14000a52d  jmp     short loc_14000A567
0x14000a52f  mov     rax, [rsp+68h+arg_28]
0x14000a537  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x14000a53c  mov     rax, [rsp+68h+arg_20]
0x14000a544  mov     [rsp+68h+phkResult], rax; phkResult
0x14000a549  mov     [rsp+68h+lpSecurityAttributes], r9; lpSecurityAttributes
0x14000a54e  xor     r9d, r9d; lpClass
0x14000a551  mov     [rsp+68h+samDesired], r8d; samDesired
0x14000a556  xor     r8d, r8d; Reserved
0x14000a559  mov     [rsp+68h+dwOptions], 0; dwOptions
0x14000a561  call    cs:__imp_RegCreateKeyExW
0x14000a567  add     rsp, 68h
0x14000a56b  retn
```
