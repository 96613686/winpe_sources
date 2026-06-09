# RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)

- ea: `0x140008870`
- end: `0x1400088ac`
- name: `?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z`
- size: `60`
- prototype: `int(HKEY, const wchar_t *, const wchar_t *, unsigned int *)`
- caller_count: `9`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140013658`
- `0x140015b0c`
- `0x140019248`
- `0x14001ad34`
- `0x14001eb9c`
- `0x1400201e8`
- `0x1400203a8`
- `0x1400215a8`
- `0x14002e0cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400088a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400088a1`

## pseudocode

```c
LSTATUS __fastcall RegReadDWORDValueNoThrow(HKEY a1, const wchar_t *a2, const wchar_t *a3, unsigned int *pvData)
{
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  int v6; // [rsp+5Ch] [rbp+14h]

  v6 = HIDWORD(a2);
  pcbData = 4;
  return RegGetValueW(a1, 0, a3, 0x10u, 0, pvData, &pcbData);
}

```

## disassembly

```asm
0x140008870  mov     qword ptr [rsp+arg_8], rdx
0x140008875  sub     rsp, 48h
0x140008879  lea     rax, [rsp+48h+arg_8]
0x14000887e  mov     [rsp+48h+arg_8], 4
0x140008886  mov     [rsp+48h+pcbData], rax; pcbData
0x14000888b  xor     edx, edx; lpSubKey
0x14000888d  mov     [rsp+48h+pvData], r9; pvData
0x140008892  mov     r9d, 10h; dwFlags
0x140008898  mov     [rsp+48h+pdwType], 0; pdwType
0x1400088a1  call    cs:__imp_RegGetValueW
0x1400088a7  add     rsp, 48h
0x1400088ab  retn
```
