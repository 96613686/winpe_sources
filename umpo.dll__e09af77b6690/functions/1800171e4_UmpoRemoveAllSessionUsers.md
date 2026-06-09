# UmpoRemoveAllSessionUsers

- ea: `0x1800171e4`
- end: `0x180017207`
- name: `UmpoRemoveAllSessionUsers`
- size: `35`
- prototype: `_UNKNOWN **()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e490`

## callees

- `0x18000fb58`
- `0x1800171e4`

## pseudocode

```c
_UNKNOWN **UmpoRemoveAllSessionUsers()
{
  _UNKNOWN **result; // rax

  while ( 1 )
  {
    result = &UmpoUserContextList;
    if ( UmpoUserContextList == (_UNKNOWN *)&UmpoUserContextList )
      break;
    UmpoRemoveSessionUser();
  }
  return result;
}

```

## disassembly

```asm
0x1800171e4  sub     rsp, 28h
0x1800171e8  mov     rcx, cs:UmpoUserContextList
0x1800171ef  lea     rax, UmpoUserContextList
0x1800171f6  cmp     rcx, rax
0x1800171f9  jz      short loc_180017202
0x1800171fb  call    UmpoRemoveSessionUser
0x180017200  jmp     short loc_1800171E8
0x180017202  add     rsp, 28h
0x180017206  retn
```
