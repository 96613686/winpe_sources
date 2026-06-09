# VolChar(long)

- ea: `0x18000c548`
- end: `0x18000c556`
- name: `?VolChar@@YAGJ@Z`
- size: `14`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b50`
- `0x180003798`
- `0x180005660`
- `0x180006a80`
- `0x18000756c`
- `0x18000f22c`

## callees

- `0x18000c548`

## pseudocode

```c
__int64 __fastcall VolChar(unsigned int a1)
{
  __int64 result; // rax

  result = a1 + 65;
  if ( a1 > 0x19 )
    return 63;
  return result;
}

```

## disassembly

```asm
0x18000c548  lea     eax, [rcx+41h]
0x18000c54b  cmp     ecx, 19h
0x18000c54e  jbe     short locret_18000C555
0x18000c550  mov     eax, 3Fh ; '?'
0x18000c555  retn
```
