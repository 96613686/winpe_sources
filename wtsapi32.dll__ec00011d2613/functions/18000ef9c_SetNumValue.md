# SetNumValue

- ea: `0x18000ef9c`
- end: `0x18000efd3`
- name: `SetNumValue`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000a580`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000efc8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000efc8`

## pseudocode

```c
LSTATUS __fastcall SetNumValue(__int64 a1, HKEY a2, const WCHAR *a3, int a4)
{
  int v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = a4;
  return RegSetValueExW(a2, a3, 0, 4u, (const BYTE *)&v5, 4u);
}

```

## disassembly

```asm
0x18000ef9c  mov     r11, rsp
0x18000ef9f  mov     [r11+20h], r9d
0x18000efa3  sub     rsp, 38h
0x18000efa7  lea     rcx, [r11+20h]
0x18000efab  mov     rax, r8
0x18000efae  mov     r10, rdx
0x18000efb1  mov     r9d, 4; dwType
0x18000efb7  mov     [r11-10h], r9d
0x18000efbb  xor     r8d, r8d; Reserved
0x18000efbe  mov     [r11-18h], rcx
0x18000efc2  mov     rdx, rax; lpValueName
0x18000efc5  mov     rcx, r10; hKey
0x18000efc8  call    cs:__imp_RegSetValueExW
0x18000efce  add     rsp, 38h
0x18000efd2  retn
```
