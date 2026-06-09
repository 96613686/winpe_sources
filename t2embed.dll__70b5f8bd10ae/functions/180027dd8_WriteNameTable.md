# WriteNameTable

- ea: `0x180027dd8`
- end: `0x180027ea0`
- name: `WriteNameTable`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002049c`

## callees

- `0x180010b90`
- `0x1800134a0`
- `0x1800164a0`
- `0x180016770`
- `0x18002773c`
- `0x180027dd8`

## pseudocode

```c
__int64 __fastcall WriteNameTable(__int64 a1, _WORD *a2, unsigned __int16 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // edi
  __int64 v9; // rbx
  unsigned __int16 inserted; // di
  unsigned __int16 v11; // [rsp+20h] [rbp-68h]
  __int64 v12; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-50h]
  int v14; // [rsp+3Ch] [rbp-4Ch]
  __int64 v15; // [rsp+40h] [rbp-48h]
  unsigned int v16; // [rsp+A8h] [rbp+20h] BYREF

  v16 = 0;
  v6 = CalcMaxNameTableLength(a2, a3);
  v7 = v6;
  if ( !v6 )
    return 1060;
  v9 = Mem_Alloc(v6);
  if ( !v9 )
    return 1005;
  v12 = v9;
  v13 = v7;
  v14 = 0;
  v15 = 0;
  inserted = WriteNameRecords(&v12, a2, a3, 1, v11, &v16);
  if ( !inserted )
    inserted = InsertTable(a1, "name", v9, v16);
  Mem_Free(v9);
  return inserted;
}

```

## disassembly

```asm
0x180027dd8  mov     rax, rsp
0x180027ddb  mov     [rax+20h], r9d
0x180027ddf  push    rbx
0x180027de0  push    rbp
0x180027de1  push    rsi
0x180027de2  push    rdi
0x180027de3  push    r14
0x180027de5  push    r15
0x180027de7  sub     rsp, 58h
0x180027deb  mov     rbp, rdx
0x180027dee  mov     r14, rcx
0x180027df1  xor     r15d, r15d
0x180027df4  mov     rcx, rbp
0x180027df7  movzx   edx, r8w
0x180027dfb  mov     [rax+20h], r15d
0x180027dff  movzx   esi, r8w
0x180027e03  call    CalcMaxNameTableLength
0x180027e08  mov     edi, eax
0x180027e0a  test    eax, eax
0x180027e0c  jnz     short loc_180027E15
0x180027e0e  mov     eax, 424h
0x180027e13  jmp     short loc_180027E93
0x180027e15  mov     rcx, rdi; Size
0x180027e18  call    Mem_Alloc
0x180027e1d  mov     rbx, rax
0x180027e20  test    rax, rax
0x180027e23  jnz     short loc_180027E2C
0x180027e25  mov     eax, 3EDh
0x180027e2a  jmp     short loc_180027E93
0x180027e2c  lea     rax, [rsp+88h+arg_18]
0x180027e34  mov     [rsp+88h+var_58], rbx
0x180027e39  mov     r9d, 1
0x180027e3f  mov     [rsp+88h+var_60], rax
0x180027e44  movzx   r8d, si
0x180027e48  mov     [rsp+88h+var_50], edi
0x180027e4c  mov     rdx, rbp
0x180027e4f  mov     [rsp+88h+var_4C], r15d
0x180027e54  lea     rcx, [rsp+88h+var_58]
0x180027e59  mov     [rsp+88h+var_48], r15
0x180027e5e  call    WriteNameRecords
0x180027e63  movzx   edi, ax
0x180027e66  test    ax, ax
0x180027e69  jnz     short loc_180027E88
0x180027e6b  mov     r9d, [rsp+88h+arg_18]
0x180027e73  lea     rdx, aName; "name"
0x180027e7a  mov     r8, rbx
0x180027e7d  mov     rcx, r14
0x180027e80  call    InsertTable
0x180027e85  movzx   edi, ax
0x180027e88  mov     rcx, rbx
0x180027e8b  call    Mem_Free
0x180027e90  movzx   eax, di
0x180027e93  add     rsp, 58h
0x180027e97  pop     r15
0x180027e99  pop     r14
0x180027e9b  pop     rdi
0x180027e9c  pop     rsi
0x180027e9d  pop     rbp
0x180027e9e  pop     rbx
0x180027e9f  retn
```
