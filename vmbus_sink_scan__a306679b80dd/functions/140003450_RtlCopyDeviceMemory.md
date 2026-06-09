# RtlCopyDeviceMemory

- ea: `0x140003450`
- end: `0x140003492`
- name: `RtlCopyDeviceMemory`
- size: `66`
- prototype: `char *__fastcall(char *, char *, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e880`

## callees

- `0x140003450`
- `0x140017140`

## pseudocode

```c
char *__fastcall RtlCopyDeviceMemory(char *a1, char *a2, size_t a3)
{
  char *v5; // rcx
  char *v6; // rax
  char *v7; // rcx

  if ( !a3 )
    return a1;
  v5 = a2;
  v6 = a2;
  if ( a1 < a2 )
    v5 = a1;
  v7 = &v5[a3];
  if ( a1 >= a2 )
    v6 = a1;
  if ( v7 > v6 )
    __fastfail(5u);
  return (char *)RtlCopyVolatileMemory(a1, a2, a3);
}

```

## disassembly

```asm
0x140003450  sub     rsp, 28h
0x140003454  mov     r9, rcx
0x140003457  test    r8, r8
0x14000345a  jnz     short loc_140003461
0x14000345c  mov     rax, rcx
0x14000345f  jmp     short loc_14000348C
0x140003461  cmp     r9, rdx
0x140003464  mov     rcx, rdx
0x140003467  mov     rax, rdx
0x14000346a  cmovb   rcx, r9
0x14000346e  add     rcx, r8
0x140003471  cmp     r9, rdx
0x140003474  cmovnb  rax, r9
0x140003478  cmp     rcx, rax
0x14000347b  jbe     short loc_140003484
0x14000347d  mov     ecx, 5
0x140003482  int     29h; Win8: RtlFailFast(ecx)
0x140003484  mov     rcx, r9; void *
0x140003487  call    RtlCopyVolatileMemory
0x14000348c  add     rsp, 28h
0x140003490  retn
```
