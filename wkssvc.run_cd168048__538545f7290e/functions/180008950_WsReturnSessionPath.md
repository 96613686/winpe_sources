# WsReturnSessionPath

- ea: `0x180008950`
- end: `0x1800089a4`
- name: `WsReturnSessionPath`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x1800089ac`
- `0x180009370`

## callees

- `0x180008048`
- `0x180008950`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!DosPathToSessionPathW` at `0x180008984`
- `api-ms-win-core-kernel32-private-l1-1-0!DosPathToSessionPathW` at `0x180008984`

## pseudocode

```c
__int64 __fastcall WsReturnSessionPath(__int64 a1)
{
  unsigned int v3; // [rsp+38h] [rbp+10h] BYREF
  __int64 v4; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  v4 = 0;
  if ( (unsigned int)WsImpersonateAndGetSessionId(&v3) || !(unsigned int)DosPathToSessionPathW(v3, a1, &v4) )
    return 0;
  else
    return v4;
}

```

## disassembly

```asm
0x180008950  push    rbx
0x180008952  sub     rsp, 20h
0x180008956  mov     rbx, rcx
0x180008959  mov     [rsp+28h+arg_8], 0
0x180008961  lea     rcx, [rsp+28h+arg_8]
0x180008966  mov     [rsp+28h+arg_10], 0
0x18000896f  call    WsImpersonateAndGetSessionId
0x180008974  test    eax, eax
0x180008976  jnz     short loc_18000899B
0x180008978  mov     ecx, [rsp+28h+arg_8]
0x18000897c  lea     r8, [rsp+28h+arg_10]
0x180008981  mov     rdx, rbx
0x180008984  call    cs:__imp_DosPathToSessionPathW
0x18000898b  nop     dword ptr [rax+rax+00h]
0x180008990  test    eax, eax
0x180008992  jz      short loc_18000899B
0x180008994  mov     rax, [rsp+28h+arg_10]
0x180008999  jmp     short loc_18000899D
0x18000899b  xor     eax, eax
0x18000899d  add     rsp, 20h
0x1800089a1  pop     rbx
0x1800089a2  retn
```
