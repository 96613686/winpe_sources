# SXWriter::get_omitXMLDeclaration(short *)

- ea: `0x1004084f0`
- end: `0x100408510`
- name: `?get_omitXMLDeclaration@SXWriter@@UEAAJPEAF@Z`
- size: `32`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1004084f0`

## pseudocode

```c
__int64 __fastcall SXWriter::get_omitXMLDeclaration(SXWriter *this, __int16 *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = -(*((_BYTE *)this + 234) != 0);
  return 0;
}

```

## disassembly

```asm
0x1004084f0  mov     rax, rdx
0x1004084f3  test    rdx, rdx
0x1004084f6  jnz     short loc_1004084FE
0x1004084f8  mov     eax, 80004003h
0x1004084fd  retn
0x1004084fe  movzx   ecx, byte ptr [rcx+0EAh]
0x100408505  neg     cl
0x100408507  sbb     dx, dx
0x10040850a  mov     [rax], dx
0x10040850d  xor     eax, eax
0x10040850f  retn
```
