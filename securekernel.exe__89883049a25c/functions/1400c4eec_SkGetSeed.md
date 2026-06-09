# SkGetSeed

- ea: `0x1400c4eec`
- end: `0x1400c4f33`
- name: `SkGetSeed`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140021428`
- `0x1400b17a4`
- `0x1400c2df8`
- `0x1400c30f0`

## callees

- `0x1400c4eec`

## import_xrefs

- `cng!SystemPrng` at `0x1400c4f06`
- `cng!SystemPrng` at `0x1400c4f06`

## pseudocode

```c
__int64 __fastcall SkGetSeed(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rdi

  v4 = MEMORY[0xFFFFF78000000250];
  if ( !(unsigned int)SystemPrng() )
    return 3221225701LL;
  if ( a3 )
    *a3 = v4;
  return 0;
}

```

## disassembly

```asm
0x1400c4eec  mov     [rsp+arg_0], rbx
0x1400c4ef1  push    rdi
0x1400c4ef2  sub     rsp, 20h
0x1400c4ef6  mov     rbx, r8
0x1400c4ef9  mov     rdi, 0FFFFF78000000250h
0x1400c4f03  mov     rdi, [rdi]
0x1400c4f06  call    cs:__imp_SystemPrng
0x1400c4f0d  nop     dword ptr [rax+rax+00h]
0x1400c4f12  test    eax, eax
0x1400c4f14  jz      short loc_1400C4F22
0x1400c4f16  test    rbx, rbx
0x1400c4f19  jz      short loc_1400C4F1E
0x1400c4f1b  mov     [rbx], rdi
0x1400c4f1e  xor     eax, eax
0x1400c4f20  jmp     short loc_1400C4F27
0x1400c4f22  mov     eax, 0C00000E5h
0x1400c4f27  mov     rbx, [rsp+28h+arg_0]
0x1400c4f2c  add     rsp, 20h
0x1400c4f30  pop     rdi
0x1400c4f31  retn
```
