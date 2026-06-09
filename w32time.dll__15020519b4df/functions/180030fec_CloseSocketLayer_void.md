# CloseSocketLayer(void)

- ea: `0x180030fec`
- end: `0x180031023`
- name: `?CloseSocketLayer@@YAJXZ`
- size: `55`
- prototype: `signed int(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180009a80`
- `0x180029bbc`

## callees

- `0x180030fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031001`
- `WS2_32!__imp_WSACleanup` at `0x180030ff0`
- `WS2_32!__imp_WSACleanup` at `0x180030ff0`

## pseudocode

```c
signed int CloseSocketLayer(void)
{
  signed int result; // eax

  if ( WSACleanup() != -1 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180030fec  sub     rsp, 28h
0x180030ff0  call    cs:__imp_WSACleanup
0x180030ff7  nop     dword ptr [rax+rax+00h]
0x180030ffc  cmp     eax, 0FFFFFFFFh
0x180030fff  jnz     short loc_18003101B
0x180031001  call    cs:__imp_GetLastError
0x180031008  nop     dword ptr [rax+rax+00h]
0x18003100d  test    eax, eax
0x18003100f  jle     short loc_18003101D
0x180031011  movzx   eax, ax
0x180031014  or      eax, 80070000h
0x180031019  jmp     short loc_18003101D
0x18003101b  xor     eax, eax
0x18003101d  add     rsp, 28h
0x180031021  retn
```
