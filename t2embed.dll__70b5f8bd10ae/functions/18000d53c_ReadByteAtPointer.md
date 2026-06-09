# ReadByteAtPointer

- ea: `0x18000d53c`
- end: `0x18000d568`
- name: `ReadByteAtPointer`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b728`

## callees

- `0x18000d53c`

## import_xrefs

- `msvcrt!longjmp` at `0x18000d561`
- `msvcrt!longjmp` at `0x18000d561`

## pseudocode

```c
char __fastcall ReadByteAtPointer(_JBTYPE *a1, char **a2, unsigned __int64 a3)
{
  char *v4; // rcx
  char result; // al

  v4 = *a2;
  if ( (unsigned __int64)*a2 >= a3 )
    longjmp(a1 + 3, 3362);
  result = *v4;
  *a2 = v4 + 1;
  return result;
}

```

## disassembly

```asm
0x18000d53c  sub     rsp, 28h
0x18000d540  mov     rax, rcx
0x18000d543  mov     rcx, [rdx]
0x18000d546  cmp     rcx, r8
0x18000d549  jnb     short loc_18000D558
0x18000d54b  mov     al, [rcx]
0x18000d54d  inc     rcx
0x18000d550  mov     [rdx], rcx
0x18000d553  add     rsp, 28h
0x18000d557  retn
0x18000d558  lea     rcx, [rax+30h]; Buf
0x18000d55c  mov     edx, 0D22h; Value
0x18000d561  call    cs:__imp_longjmp
```
