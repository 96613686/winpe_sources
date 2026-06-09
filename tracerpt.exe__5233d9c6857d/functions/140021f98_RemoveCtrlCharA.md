# RemoveCtrlCharA

- ea: `0x140021f98`
- end: `0x140021fed`
- name: `RemoveCtrlCharA`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140022480`

## callees

- `0x140021f98`

## import_xrefs

- `msvcrt!isprint` at `0x140021fb2`
- `msvcrt!isprint` at `0x140021fb2`

## pseudocode

```c
__int64 __fastcall RemoveCtrlCharA(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx

  v4 = 0;
  do
  {
    if ( !*(_BYTE *)(v4 + a1) )
      break;
    if ( isprint(*(unsigned __int8 *)(v4 + a1)) )
    {
      if ( *(_BYTE *)(v4 + a1) > 0x27u )
        continue;
      v5 = 0x8400000700LL;
      if ( !_bittest64(&v5, *(char *)(v4 + a1)) )
        continue;
    }
    *(_BYTE *)(v4 + a1) = 63;
    v4 = (unsigned int)(v4 + 1);
  }
  while ( (unsigned int)v4 <= a2 );
  return a1;
}

```

## disassembly

```asm
0x140021f98  push    rbx
0x140021f9a  push    rbp
0x140021f9b  push    rsi
0x140021f9c  push    rdi
0x140021f9d  sub     rsp, 28h
0x140021fa1  mov     ebp, edx
0x140021fa3  mov     rbx, rcx
0x140021fa6  xor     edi, edi
0x140021fa8  movzx   eax, byte ptr [rdi+rbx]
0x140021fac  test    al, al
0x140021fae  jz      short loc_140021FE1
0x140021fb0  mov     ecx, eax; C
0x140021fb2  call    cs:__imp_isprint
0x140021fb8  test    eax, eax
0x140021fba  jz      short loc_140021FD7
0x140021fbc  cmp     byte ptr [rdi+rbx], 27h ; '''
0x140021fc0  ja      short loc_140021FDB
0x140021fc2  movsx   rax, byte ptr [rdi+rbx]
0x140021fc7  mov     rcx, 8400000700h
0x140021fd1  bt      rcx, rax
0x140021fd5  jnb     short loc_140021FDB
0x140021fd7  mov     byte ptr [rdi+rbx], 3Fh ; '?'
0x140021fdb  inc     edi
0x140021fdd  cmp     edi, ebp
0x140021fdf  jbe     short loc_140021FA8
0x140021fe1  mov     rax, rbx
0x140021fe4  add     rsp, 28h
0x140021fe8  pop     rdi
0x140021fe9  pop     rsi
0x140021fea  pop     rbp
0x140021feb  pop     rbx
0x140021fec  retn
```
