# CPtrList<tagLOG_OUTPUT_STACK *>::Remove(tagLOG_OUTPUT_STACK *)

- ea: `0x18001fb9c`
- end: `0x18001fbca`
- name: `?Remove@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAHPEAUtagLOG_OUTPUT_STACK@@@Z`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001fda0`

## callees

- `0x18001fb9c`

## pseudocode

```c
__int64 __fastcall CPtrList<tagLOG_OUTPUT_STACK *>::Remove(__int64 a1, __int64 a2)
{
  __int64 i; // rax

  if ( a2 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 8); i = (unsigned int)(i + 1) )
    {
      if ( *(_QWORD *)(*(_QWORD *)a1 + 8 * i) == a2 )
      {
        *(_QWORD *)(*(_QWORD *)a1 + 8 * i) = 0;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001fb9c  mov     r8, rdx
0x18001fb9f  test    rdx, rdx
0x18001fba2  jz      short loc_18001FBC7
0x18001fba4  xor     eax, eax
0x18001fba6  cmp     eax, [rcx+8]
0x18001fba9  jnb     short loc_18001FBC7
0x18001fbab  mov     rdx, [rcx]
0x18001fbae  cmp     [rdx+rax*8], r8
0x18001fbb2  jz      short loc_18001FBB8
0x18001fbb4  inc     eax
0x18001fbb6  jmp     short loc_18001FBA6
0x18001fbb8  mov     qword ptr [rdx+rax*8], 0
0x18001fbc0  mov     eax, 1
0x18001fbc5  retn
0x18001fbc7  xor     eax, eax
0x18001fbc9  retn
```
