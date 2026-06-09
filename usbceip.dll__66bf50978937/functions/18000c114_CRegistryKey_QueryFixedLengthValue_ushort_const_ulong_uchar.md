# CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)

- ea: `0x18000c114`
- end: `0x18000c164`
- name: `?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z`
- size: `80`
- prototype: `unsigned __int8 __fastcall(HKEY *this, const unsigned __int16 *, DWORD, unsigned __int8 *)`
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800045d0`
- `0x1800053e4`
- `0x180005e94`
- `0x180006430`
- `0x1800066a8`
- `0x180006f18`
- `0x1800078e0`
- `0x180008904`
- `0x180008960`
- `0x180008a60`
- `0x180008f48`
- `0x1800090d4`
- `0x180009204`
- `0x180009424`
- `0x180009748`
- `0x18000ba28`
- `0x18000c0d0`

## callees

- `0x180008020`
- `0x18000c114`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c13d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c13d`

## pseudocode

```c
unsigned __int8 __fastcall CRegistryKey::QueryFixedLengthValue(
        HKEY *this,
        const unsigned __int16 *a2,
        DWORD a3,
        unsigned __int8 *a4)
{
  HKEY v4; // rcx
  unsigned int v5; // eax
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  DWORD v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = a3;
  v4 = *this;
  v7 = 0;
  v5 = RegQueryValueExW(v4, a2, 0, &v7, a4, &v8);
  if ( v5 == 2 )
    return 0;
  if ( v5 )
    CException::ThrowException(v5, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18000c114  mov     r11, rsp
0x18000c117  mov     [r11+18h], r8d
0x18000c11b  sub     rsp, 38h
0x18000c11f  mov     rcx, [rcx]; hKey
0x18000c122  lea     rax, [r11+18h]
0x18000c126  mov     [r11-10h], rax
0x18000c12a  xor     r8d, r8d; lpReserved
0x18000c12d  mov     [r11-18h], r9
0x18000c131  lea     r9, [r11+8]; lpType
0x18000c135  mov     [rsp+38h+arg_0], 0
0x18000c13d  call    cs:__imp_RegQueryValueExW
0x18000c143  cmp     eax, 2
0x18000c146  jnz     short loc_18000C14C
0x18000c148  xor     al, al
0x18000c14a  jmp     short loc_18000C15F
0x18000c14c  test    eax, eax
0x18000c14e  jz      short loc_18000C15D
0x18000c150  xor     r8d, r8d
0x18000c153  xor     edx, edx
0x18000c155  mov     ecx, eax
0x18000c157  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000c15d  mov     al, 1
0x18000c15f  add     rsp, 38h
0x18000c163  retn
```
