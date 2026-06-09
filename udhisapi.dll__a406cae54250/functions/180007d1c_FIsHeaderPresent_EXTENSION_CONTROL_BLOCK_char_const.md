# FIsHeaderPresent(_EXTENSION_CONTROL_BLOCK *,char const *)

- ea: `0x180007d1c`
- end: `0x180007d53`
- name: `?FIsHeaderPresent@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD@Z`
- size: `55`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006f64`
- `0x1800071bc`
- `0x180007734`

## callees

- `0x1800025e8`
- `0x180007d1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007d40`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007d40`

## pseudocode

```c
__int64 __fastcall FIsHeaderPresent(struct _EXTENSION_CONTROL_BLOCK *a1, const char *a2)
{
  unsigned int v2; // ebx
  void *Block; // [rsp+40h] [rbp+18h] BYREF

  Block = 0;
  v2 = 0;
  if ( !(unsigned int)DwQueryHeader(a1, a2, (char **)&Block) )
  {
    free(Block);
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x180007d1c  push    rbx
0x180007d1e  sub     rsp, 20h
0x180007d22  lea     r8, [rsp+28h+Block]; char **
0x180007d27  mov     [rsp+28h+Block], 0
0x180007d30  xor     ebx, ebx
0x180007d32  call    ?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z; DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)
0x180007d37  test    eax, eax
0x180007d39  jnz     short loc_180007D4B
0x180007d3b  mov     rcx, [rsp+28h+Block]; Block
0x180007d40  call    cs:__imp_free
0x180007d46  mov     ebx, 1
0x180007d4b  mov     eax, ebx
0x180007d4d  add     rsp, 20h
0x180007d51  pop     rbx
0x180007d52  retn
```
