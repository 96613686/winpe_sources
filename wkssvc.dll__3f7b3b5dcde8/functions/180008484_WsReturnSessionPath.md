# WsReturnSessionPath

- ea: `0x180008484`
- end: `0x1800084d1`
- name: `WsReturnSessionPath`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x1800084d8`
- `0x180008c90`

## callees

- `0x180007b2c`
- `0x180008484`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!DosPathToSessionPathW` at `0x1800084b8`
- `api-ms-win-core-kernel32-private-l1-1-0!DosPathToSessionPathW` at `0x1800084b8`

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
0x180008484  push    rbx
0x180008486  sub     rsp, 20h
0x18000848a  mov     rbx, rcx
0x18000848d  mov     [rsp+28h+arg_8], 0
0x180008495  lea     rcx, [rsp+28h+arg_8]
0x18000849a  mov     [rsp+28h+arg_10], 0
0x1800084a3  call    WsImpersonateAndGetSessionId
0x1800084a8  test    eax, eax
0x1800084aa  jnz     short loc_1800084C9
0x1800084ac  mov     ecx, [rsp+28h+arg_8]
0x1800084b0  lea     r8, [rsp+28h+arg_10]
0x1800084b5  mov     rdx, rbx
0x1800084b8  call    cs:__imp_DosPathToSessionPathW
0x1800084be  test    eax, eax
0x1800084c0  jz      short loc_1800084C9
0x1800084c2  mov     rax, [rsp+28h+arg_10]
0x1800084c7  jmp     short loc_1800084CB
0x1800084c9  xor     eax, eax
0x1800084cb  add     rsp, 20h
0x1800084cf  pop     rbx
0x1800084d0  retn
```
