# XdrEncodeOpaqueUnsafe

- ea: `0x140005bac`
- end: `0x140005c22`
- name: `XdrEncodeOpaqueUnsafe`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140002514`
- `0x140004774`
- `0x140004844`
- `0x140004900`
- `0x140008988`

## callees

- `0x140005bac`
- `0x140005c28`
- `0x140015840`
- `0x140015b40`

## pseudocode

```c
void *__fastcall XdrEncodeOpaqueUnsafe(__int64 a1, unsigned int a2, const void *a3)
{
  __int64 v3; // rax
  void *v5; // rcx
  __int64 v6; // rbx
  void *result; // rax
  char *v8; // r9
  char *v9; // r8

  v3 = *(_QWORD *)(a1 + 72);
  if ( v3 )
    v5 = *(void **)(v3 + 64);
  else
    v5 = 0;
  v6 = a2;
  memmove(v5, a3, a2);
  *(_QWORD *)(*(_QWORD *)(a1 + 72) + 64LL) += v6;
  result = (void *)XdrNextMod4Boundary(a1);
  v9 = *(char **)(a1 + 72);
  if ( v9 )
    v9 = (char *)*((_QWORD *)v9 + 8);
  if ( v8 != v9 )
    return memset(v8, 0, v9 - v8);
  return result;
}

```

## disassembly

```asm
0x140005bac  mov     [rsp+arg_0], rbx
0x140005bb1  push    rdi
0x140005bb2  sub     rsp, 20h
0x140005bb6  mov     rax, [rcx+48h]
0x140005bba  mov     r9, r8
0x140005bbd  mov     rdi, rcx
0x140005bc0  test    rax, rax
0x140005bc3  jnz     short loc_140005BC9
0x140005bc5  xor     ecx, ecx
0x140005bc7  jmp     short loc_140005BCD
0x140005bc9  mov     rcx, [rax+40h]; void *
0x140005bcd  mov     ebx, edx
0x140005bcf  mov     r8d, edx; Size
0x140005bd2  mov     rdx, r9; Src
0x140005bd5  call    memmove
0x140005bda  mov     rax, [rdi+48h]
0x140005bde  add     [rax+40h], rbx
0x140005be2  mov     r9, [rdi+48h]
0x140005be6  test    r9, r9
0x140005be9  jz      short loc_140005BEF
0x140005beb  mov     r9, [r9+40h]
0x140005bef  mov     rcx, rdi
0x140005bf2  call    XdrNextMod4Boundary
0x140005bf7  mov     r8, [rdi+48h]
0x140005bfb  test    r8, r8
0x140005bfe  jz      short loc_140005C04
0x140005c00  mov     r8, [r8+40h]
0x140005c04  cmp     r9, r8
0x140005c07  jz      short loc_140005C16
0x140005c09  sub     r8, r9; Size
0x140005c0c  xor     edx, edx; Val
0x140005c0e  mov     rcx, r9; void *
0x140005c11  call    memset
0x140005c16  mov     rbx, [rsp+28h+arg_0]
0x140005c1b  add     rsp, 20h
0x140005c1f  pop     rdi
0x140005c20  retn
```
