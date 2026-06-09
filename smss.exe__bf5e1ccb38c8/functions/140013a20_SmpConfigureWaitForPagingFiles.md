# SmpConfigureWaitForPagingFiles

- ea: `0x140013a20`
- end: `0x140013a36`
- name: `SmpConfigureWaitForPagingFiles`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013a20`

## pseudocode

```c
__int64 __fastcall SmpConfigureWaitForPagingFiles(__int64 a1, __int64 a2, int *a3, int a4)
{
  int v4; // eax

  if ( a4 == 4 )
    v4 = *a3;
  else
    v4 = 0;
  SmpWaitForPagingFiles = v4;
  return 0;
}

```

## disassembly

```asm
0x140013a20  cmp     r9d, 4
0x140013a24  jz      short loc_140013A2A
0x140013a26  xor     eax, eax
0x140013a28  jmp     short loc_140013A2D
0x140013a2a  mov     eax, [r8]
0x140013a2d  mov     cs:SmpWaitForPagingFiles, eax
0x140013a33  xor     eax, eax
0x140013a35  retn
```
