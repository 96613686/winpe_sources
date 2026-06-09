# OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)

- ea: `0x140007fd0`
- end: `0x140008016`
- name: `?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z`
- size: `70`
- prototype: `int(HKEY, const wchar_t *, unsigned int, HKEY *, void *)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140003b50`
- `0x140006008`
- `0x140006de0`
- `0x14001291c`
- `0x140013658`
- `0x140014988`
- `0x1400151ec`
- `0x140015cac`
- `0x14001aa58`
- `0x14001e0c0`
- `0x14001e458`
- `0x14002bd08`
- `0x14002e0cc`

## callees

- `0x140007fd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000800e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000800e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140007ff8`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140007ff8`

## pseudocode

```c
LSTATUS __fastcall OpenRegKey(HKEY a1, const wchar_t *a2, REGSAM a3, HKEY *phkResult, HANDLE hTransaction)
{
  if ( hTransaction == (HANDLE)-1LL )
    return RegOpenKeyExW(a1, a2, 0, a3, phkResult);
  else
    return RegOpenKeyTransactedW(a1, a2, 0, a3, phkResult, hTransaction, 0);
}

```

## disassembly

```asm
0x140007fd0  sub     rsp, 48h
0x140007fd4  mov     rax, [rsp+48h+arg_20]
0x140007fd9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140007fdd  jz      short loc_140008003
0x140007fdf  mov     [rsp+48h+pExtendedParemeter], 0; pExtendedParemeter
0x140007fe8  mov     [rsp+48h+hTransaction], rax; hTransaction
0x140007fed  mov     [rsp+48h+phkResult], r9; phkResult
0x140007ff2  mov     r9d, r8d; samDesired
0x140007ff5  xor     r8d, r8d; ulOptions
0x140007ff8  call    cs:__imp_RegOpenKeyTransactedW
0x140007ffe  add     rsp, 48h
0x140008002  retn
0x140008003  mov     [rsp+48h+phkResult], r9; phkResult
0x140008008  mov     r9d, r8d; samDesired
0x14000800b  xor     r8d, r8d; ulOptions
0x14000800e  call    cs:__imp_RegOpenKeyExW
0x140008014  jmp     short loc_140007FFE
```
