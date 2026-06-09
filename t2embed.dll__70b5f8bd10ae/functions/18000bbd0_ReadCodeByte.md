# ReadCodeByte

- ea: `0x18000bbd0`
- end: `0x18000bc03`
- name: `ReadCodeByte`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b8f0`

## callees

- `0x18000bbd0`

## import_xrefs

- `msvcrt!longjmp` at `0x18000bbfc`
- `msvcrt!longjmp` at `0x18000bbfc`

## pseudocode

```c
char __fastcall ReadCodeByte(__int64 a1, unsigned __int16 a2)
{
  if ( a2 >= *(_WORD *)(a1 + 70) )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  return *(_BYTE *)(a2 + *(_QWORD *)(a1 + 72));
}

```

## disassembly

```asm
0x18000bbd0  sub     rsp, 28h
0x18000bbd4  mov     rax, rcx
0x18000bbd7  cmp     dx, [rcx+46h]
0x18000bbdb  jnb     short loc_18000BBEC
0x18000bbdd  mov     rax, [rax+48h]
0x18000bbe1  movzx   ecx, dx
0x18000bbe4  mov     al, [rcx+rax]
0x18000bbe7  add     rsp, 28h
0x18000bbeb  retn
0x18000bbec  mov     rcx, [rcx+88h]
0x18000bbf3  mov     edx, 0D22h; Value
0x18000bbf8  add     rcx, 30h ; '0'; Buf
0x18000bbfc  call    cs:__imp_longjmp
```
