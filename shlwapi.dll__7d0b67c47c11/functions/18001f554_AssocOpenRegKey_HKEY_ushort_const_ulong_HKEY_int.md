# _AssocOpenRegKey(HKEY__ *,ushort const *,ulong,HKEY__ * *,int)

- ea: `0x18001f554`
- end: `0x18001f5c9`
- name: `?_AssocOpenRegKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@H@Z`
- size: `117`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, HKEY *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001f454`
- `0x18001fa90`
- `0x18001fd40`
- `0x18001ff80`
- `0x18002094c`

## callees

- `0x18001f554`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f5b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f5b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f580`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f580`

## pseudocode

```c
LSTATUS __fastcall _AssocOpenRegKey(HKEY a1, const unsigned __int16 *a2, REGSAM samDesired, HKEY *phkResult, int a5)
{
  LSTATUS result; // eax

  *phkResult = 0;
  if ( !a1 )
    return -2147023741;
  if ( a5 )
    result = RegCreateKeyExW(a1, a2, 0, 0, 0, samDesired, 0, phkResult, 0);
  else
    result = RegOpenKeyExW(a1, a2, 0, samDesired, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001f554  sub     rsp, 58h
0x18001f558  mov     qword ptr [r9], 0
0x18001f55f  test    rcx, rcx
0x18001f562  jnz     short loc_18001F56B
0x18001f564  mov     eax, 80070483h
0x18001f569  jmp     short loc_18001F5C4
0x18001f56b  cmp     [rsp+58h+arg_20], 0
0x18001f573  jnz     short loc_18001F588
0x18001f575  mov     [rsp+58h+phkResult], r9; phkResult
0x18001f57a  mov     r9d, r8d; samDesired
0x18001f57d  xor     r8d, r8d; ulOptions
0x18001f580  call    cs:__imp_RegOpenKeyExW
0x18001f586  jmp     short loc_18001F5B8
0x18001f588  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18001f591  mov     [rsp+58h+var_20], r9; phkResult
0x18001f596  xor     r9d, r9d; lpClass
0x18001f599  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001f5a2  mov     [rsp+58h+samDesired], r8d; samDesired
0x18001f5a7  xor     r8d, r8d; Reserved
0x18001f5aa  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x18001f5b2  call    cs:__imp_RegCreateKeyExW
0x18001f5b8  test    eax, eax
0x18001f5ba  jle     short loc_18001F5C4
0x18001f5bc  movzx   eax, ax
0x18001f5bf  or      eax, 80070000h
0x18001f5c4  add     rsp, 58h
0x18001f5c8  retn
```
