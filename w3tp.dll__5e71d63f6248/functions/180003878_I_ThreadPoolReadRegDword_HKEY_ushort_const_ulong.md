# I_ThreadPoolReadRegDword(HKEY__ *,ushort const *,ulong)

- ea: `0x180003878`
- end: `0x1800038d3`
- name: `?I_ThreadPoolReadRegDword@@YAKPEAUHKEY__@@PEBGK@Z`
- size: `91`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003a80`
- `0x180003d80`

## callees

- `0x180003878`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038b7`

## pseudocode

```c
__int64 __fastcall I_ThreadPoolReadRegDword(HKEY a1, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v5; // [rsp+40h] [rbp+8h] BYREF
  DWORD v6; // [rsp+50h] [rbp+18h] BYREF
  DWORD v7; // [rsp+58h] [rbp+20h] BYREF

  v5 = 0;
  v7 = 4;
  v6 = 0;
  if ( a1 && !RegQueryValueExW(a1, a2, 0, &v6, (LPBYTE)&v5, &v7) && v6 == 4 )
    return v5;
  return a3;
}

```

## disassembly

```asm
0x180003878  mov     r11, rsp
0x18000387b  push    rbx
0x18000387c  sub     rsp, 30h
0x180003880  mov     [rsp+38h+arg_0], 0
0x180003888  mov     ebx, r8d
0x18000388b  mov     [rsp+38h+arg_18], 4
0x180003893  mov     [rsp+38h+arg_10], 0
0x18000389b  test    rcx, rcx
0x18000389e  jz      short loc_1800038CB
0x1800038a0  lea     rax, [r11+20h]
0x1800038a4  xor     r8d, r8d; lpReserved
0x1800038a7  mov     [r11-10h], rax
0x1800038ab  lea     r9, [r11+18h]; lpType
0x1800038af  lea     rax, [r11+8]
0x1800038b3  mov     [r11-18h], rax
0x1800038b7  call    cs:__imp_RegQueryValueExW
0x1800038bd  test    eax, eax
0x1800038bf  jnz     short loc_1800038CB
0x1800038c1  cmp     [rsp+38h+arg_10], 4
0x1800038c6  cmovz   ebx, [rsp+38h+arg_0]
0x1800038cb  mov     eax, ebx
0x1800038cd  add     rsp, 30h
0x1800038d1  pop     rbx
0x1800038d2  retn
```
