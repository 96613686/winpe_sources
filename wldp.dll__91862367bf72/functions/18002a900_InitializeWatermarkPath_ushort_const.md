# InitializeWatermarkPath(ushort const *)

- ea: `0x18002a900`
- end: `0x18002a932`
- name: `?InitializeWatermarkPath@@YAJPEBG@Z`
- size: `50`
- prototype: `signed int __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d220`
- `0x18002b390`

## callees

- `0x18002a900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a910`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a906`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a906`

## pseudocode

```c
signed int __fastcall InitializeWatermarkPath(const unsigned __int16 *a1)
{
  signed int result; // eax

  if ( CreateDirectoryW(a1, 0) )
    return 0;
  result = GetLastError();
  if ( result == 183 )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002a900  sub     rsp, 28h
0x18002a904  xor     edx, edx; lpSecurityAttributes
0x18002a906  call    cs:__imp_CreateDirectoryW
0x18002a90c  test    eax, eax
0x18002a90e  jnz     short loc_18002A92B
0x18002a910  call    cs:__imp_GetLastError
0x18002a916  cmp     eax, 0B7h
0x18002a91b  jz      short loc_18002A92B
0x18002a91d  test    eax, eax
0x18002a91f  jle     short loc_18002A92D
0x18002a921  movzx   eax, ax
0x18002a924  or      eax, 80070000h
0x18002a929  jmp     short loc_18002A92D
0x18002a92b  xor     eax, eax
0x18002a92d  add     rsp, 28h
0x18002a931  retn
```
