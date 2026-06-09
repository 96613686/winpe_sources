# SXWriter::get_standalone(short *)

- ea: `0x100408690`
- end: `0x1004086b0`
- name: `?get_standalone@SXWriter@@UEAAJPEAF@Z`
- size: `32`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100408690`

## pseudocode

```c
__int64 __fastcall SXWriter::get_standalone(SXWriter *this, __int16 *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = (*((_DWORD *)this + 28) != 1) - 1;
  return 0;
}

```

## disassembly

```asm
0x100408690  mov     rax, rcx
0x100408693  test    rdx, rdx
0x100408696  jnz     short loc_10040869E
0x100408698  mov     eax, 80004003h
0x10040869d  retn
0x10040869e  xor     ecx, ecx
0x1004086a0  cmp     dword ptr [rax+70h], 1
0x1004086a4  setnz   cl
0x1004086a7  dec     cx
0x1004086aa  mov     [rdx], cx
0x1004086ad  xor     eax, eax
0x1004086af  retn
```
