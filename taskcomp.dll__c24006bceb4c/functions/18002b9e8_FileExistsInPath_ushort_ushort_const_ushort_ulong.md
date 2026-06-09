# FileExistsInPath(ushort *,ushort const *,ushort *,ulong)

- ea: `0x18002b9e8`
- end: `0x18002ba3a`
- name: `?FileExistsInPath@@YAHPEAGPEBG0K@Z`
- size: `82`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR lpPath, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002bd00`

## callees

- `0x18002b8c4`
- `0x18002b9e8`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002ba19`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002ba19`

## pseudocode

```c
__int64 __fastcall FileExistsInPath(LPCWSTR lpFileName, LPCWSTR lpPath, unsigned __int16 *a3)
{
  LPWSTR v5; // [rsp+30h] [rbp-18h] BYREF

  v5 = 0;
  if ( SearchPathW(lpPath, lpFileName, 0, 0x105u, a3, &v5) - 1 > 0x104 )
    return 0;
  else
    return FileExists(a3);
}

```

## disassembly

```asm
0x18002b9e8  mov     r11, rsp
0x18002b9eb  push    rbx
0x18002b9ec  sub     rsp, 40h
0x18002b9f0  mov     rax, rdx
0x18002b9f3  mov     qword ptr [r11-18h], 0
0x18002b9fb  lea     rdx, [r11-18h]
0x18002b9ff  mov     rbx, r8
0x18002ba02  mov     [r11-20h], rdx
0x18002ba06  mov     r9d, 105h; nBufferLength
0x18002ba0c  mov     rdx, rcx; lpFileName
0x18002ba0f  mov     [r11-28h], rbx
0x18002ba13  mov     rcx, rax; lpPath
0x18002ba16  xor     r8d, r8d; lpExtension
0x18002ba19  call    cs:__imp_SearchPathW
0x18002ba1f  dec     eax
0x18002ba21  cmp     eax, 104h
0x18002ba26  ja      short loc_18002BA32
0x18002ba28  mov     rcx, rbx; unsigned __int16 *
0x18002ba2b  call    ?FileExists@@YAHPEAG_K@Z; FileExists(ushort *,unsigned __int64)
0x18002ba30  jmp     short loc_18002BA34
0x18002ba32  xor     eax, eax
0x18002ba34  add     rsp, 40h
0x18002ba38  pop     rbx
0x18002ba39  retn
```
