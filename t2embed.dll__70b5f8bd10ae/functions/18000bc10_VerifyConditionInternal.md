# VerifyConditionInternal

- ea: `0x18000bc10`
- end: `0x18000bc2d`
- name: `VerifyConditionInternal`
- size: `29`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800059a0`
- `0x180009d40`
- `0x18000a650`
- `0x18000b728`
- `0x18000b8f0`
- `0x18000bd00`

## callees

- `0x18000bc10`

## import_xrefs

- `msvcrt!longjmp` at `0x18000bc26`
- `msvcrt!longjmp` at `0x18000bc26`

## pseudocode

```c
void __fastcall VerifyConditionInternal(_JBTYPE *a1, int a2)
{
  if ( !a2 )
    longjmp(a1 + 3, 3362);
}

```

## disassembly

```asm
0x18000bc10  sub     rsp, 28h
0x18000bc14  test    edx, edx
0x18000bc16  jz      short loc_18000BC1D
0x18000bc18  add     rsp, 28h
0x18000bc1c  retn
0x18000bc1d  add     rcx, 30h ; '0'; Buf
0x18000bc21  mov     edx, 0D22h; Value
0x18000bc26  call    cs:__imp_longjmp
```
