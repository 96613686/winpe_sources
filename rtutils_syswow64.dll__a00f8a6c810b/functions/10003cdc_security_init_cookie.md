# ___security_init_cookie

- ea: `0x10003cdc`
- end: `0x10003d27`
- name: `___security_init_cookie`
- size: `75`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10003bf0`

## callees

- `0x10003c87`
- `0x10003cdc`

## pseudocode

```c
void __cdecl __security_init_cookie()
{
  uintptr_t v0; // ecx
  unsigned int entropy; // eax

  v0 = __security_cookie;
  if ( __security_cookie == -1153374642 || (__security_cookie & 0xFFFF0000) == 0 )
  {
    entropy = _get_entropy();
    v0 = entropy;
    if ( entropy == -1153374642 )
    {
      v0 = -1153374641;
    }
    else if ( (entropy & 0xFFFF0000) == 0 )
    {
      v0 = ((entropy | 0x4711) << 16) | entropy;
    }
    __security_cookie = v0;
  }
  __security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x10003cdc  mov     ecx, ___security_cookie
0x10003ce2  push    esi
0x10003ce3  push    edi
0x10003ce4  mov     edi, 0BB40E64Eh
0x10003ce9  mov     esi, 0FFFF0000h
0x10003cee  cmp     ecx, edi
0x10003cf0  jz      short loc_10003CF6
0x10003cf2  test    esi, ecx
0x10003cf4  jnz     short loc_10003D1C
0x10003cf6  call    __get_entropy
0x10003cfb  mov     ecx, eax
0x10003cfd  cmp     ecx, edi
0x10003cff  jnz     short loc_10003D08
0x10003d01  mov     ecx, 0BB40E64Fh
0x10003d06  jmp     short loc_10003D16
0x10003d08  test    esi, ecx
0x10003d0a  jnz     short loc_10003D16
0x10003d0c  or      eax, 4711h
0x10003d11  shl     eax, 10h
0x10003d14  or      ecx, eax
0x10003d16  mov     ___security_cookie, ecx
0x10003d1c  not     ecx
0x10003d1e  pop     edi
0x10003d1f  mov     ___security_cookie_complement, ecx
0x10003d25  pop     esi
0x10003d26  retn
```
