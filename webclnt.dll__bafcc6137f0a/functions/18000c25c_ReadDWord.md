# ReadDWord

- ea: `0x18000c25c`
- end: `0x18000c2b1`
- name: `ReadDWord`
- size: `85`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180025f10`

## callees

- `0x18000c25c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c29b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c29b`

## pseudocode

```c
__int64 __fastcall ReadDWord(HKEY a1, const WCHAR *a2, unsigned int a3)
{
  bool v4; // zf
  __int64 result; // rax
  DWORD v6[6]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v7; // [rsp+50h] [rbp+8h] BYREF
  DWORD v8; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  v8 = 4;
  v6[0] = 0;
  if ( !a1 )
    return a3;
  v4 = RegQueryValueExW(a1, a2, 0, v6, (LPBYTE)&v7, &v8) == 0;
  result = v7;
  if ( !v4 )
    return a3;
  return result;
}

```

## disassembly

```asm
0x18000c25c  mov     r11, rsp
0x18000c25f  push    rbx
0x18000c260  sub     rsp, 40h
0x18000c264  mov     [rsp+48h+arg_0], 0
0x18000c26c  mov     ebx, r8d
0x18000c26f  mov     [rsp+48h+arg_18], 4
0x18000c277  mov     [rsp+48h+var_18], 0
0x18000c27f  test    rcx, rcx
0x18000c282  jz      short loc_18000C2A9
0x18000c284  lea     rax, [r11+20h]
0x18000c288  xor     r8d, r8d; lpReserved
0x18000c28b  mov     [r11-20h], rax
0x18000c28f  lea     r9, [r11-18h]; lpType
0x18000c293  lea     rax, [r11+8]
0x18000c297  mov     [r11-28h], rax
0x18000c29b  call    cs:__imp_RegQueryValueExW
0x18000c2a1  test    eax, eax
0x18000c2a3  mov     eax, [rsp+48h+arg_0]
0x18000c2a7  jz      short loc_18000C2AB
0x18000c2a9  mov     eax, ebx
0x18000c2ab  add     rsp, 40h
0x18000c2af  pop     rbx
0x18000c2b0  retn
```
