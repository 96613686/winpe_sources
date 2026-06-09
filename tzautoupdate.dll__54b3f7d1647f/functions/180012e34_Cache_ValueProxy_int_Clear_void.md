# Cache::ValueProxy<int>::Clear(void)

- ea: `0x180012e34`
- end: `0x180012e4a`
- name: `?Clear@?$ValueProxy@H@Cache@@QEAAXXZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180012e80`
- `0x18001307c`
- `0x1800131dc`

## callees

- `0x180012e34`

## pseudocode

```c
__int64 __fastcall Cache::ValueProxy<int>::Clear(_QWORD *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( *(_BYTE *)(*a1 + 4LL) )
  {
    *(_BYTE *)(result + 4) = 0;
    result = a1[1];
    *(_BYTE *)(result + 120) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180012e34  mov     rax, [rcx]
0x180012e37  cmp     byte ptr [rax+4], 0
0x180012e3b  jz      short locret_180012E49
0x180012e3d  mov     byte ptr [rax+4], 0
0x180012e41  mov     rax, [rcx+8]
0x180012e45  mov     byte ptr [rax+78h], 1
0x180012e49  retn
```
