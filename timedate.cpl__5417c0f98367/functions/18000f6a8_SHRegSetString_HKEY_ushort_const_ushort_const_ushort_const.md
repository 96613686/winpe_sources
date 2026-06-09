# SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000f6a8`
- end: `0x18000f704`
- name: `?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `92`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000f70c`

## callees

- `0x18000f6a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f6e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f6e5`

## pseudocode

```c
LSTATUS __fastcall SHRegSetString(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, const BYTE *lpData)
{
  unsigned __int64 v4; // rax
  LSTATUS result; // eax

  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&lpData[2 * v4] );
  if ( v4 >= 0x7FFFFFFF )
  {
    LOWORD(result) = 534;
  }
  else
  {
    result = RegSetValueExW(a1, a3, 0, 1u, lpData, 2 * v4 + 2);
    if ( result <= 0 )
      return result;
  }
  return (unsigned __int16)result | 0x80070000;
}

```

## disassembly

```asm
0x18000f6a8  push    rbx
0x18000f6aa  sub     rsp, 30h
0x18000f6ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f6b2  mov     r10, r8
0x18000f6b5  xor     ebx, ebx
0x18000f6b7  inc     rax
0x18000f6ba  cmp     [r9+rax*2], bx
0x18000f6bf  jnz     short loc_18000F6B7
0x18000f6c1  cmp     rax, 7FFFFFFFh
0x18000f6c7  jnb     short loc_18000F6F1
0x18000f6c9  lea     eax, ds:2[rax*2]
0x18000f6d0  xor     r8d, r8d; Reserved
0x18000f6d3  mov     [rsp+38h+cbData], eax; cbData
0x18000f6d7  mov     rdx, r10; lpValueName
0x18000f6da  mov     [rsp+38h+lpData], r9; lpData
0x18000f6df  mov     r9d, 1; dwType
0x18000f6e5  call    cs:__imp_RegSetValueExW
0x18000f6eb  test    eax, eax
0x18000f6ed  jle     short loc_18000F6FE
0x18000f6ef  jmp     short loc_18000F6F6
0x18000f6f1  mov     eax, 216h
0x18000f6f6  movzx   eax, ax
0x18000f6f9  or      eax, 80070000h
0x18000f6fe  add     rsp, 30h
0x18000f702  pop     rbx
0x18000f703  retn
```
