# CAudioMediaType::IsCompressedFormat(int *)

- ea: `0x180016320`
- end: `0x180016333`
- name: `?IsCompressedFormat@CAudioMediaType@@UEAAJPEAH@Z`
- size: `19`
- prototype: `__int64 __fastcall(CAudioMediaType *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016320`

## pseudocode

```c
__int64 __fastcall CAudioMediaType::IsCompressedFormat(CAudioMediaType *this, int *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147942487LL;
  result = 0;
  *a2 = *((_DWORD *)this + 3);
  return result;
}

```

## disassembly

```asm
0x180016320  test    rdx, rdx
0x180016323  jnz     short loc_18001632B
0x180016325  mov     eax, 80070057h
0x18001632a  retn
0x18001632b  mov     ecx, [rcx+0Ch]
0x18001632e  xor     eax, eax
0x180016330  mov     [rdx], ecx
0x180016332  retn
```
