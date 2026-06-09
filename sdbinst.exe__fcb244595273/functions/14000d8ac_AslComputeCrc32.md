# AslComputeCrc32

- ea: `0x14000d8ac`
- end: `0x14000d8e0`
- name: `AslComputeCrc32`
- size: `52`
- prototype: `__int64 __fastcall(int, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001c290`
- `0x1400242ac`
- `0x14002b138`

## callees

- `0x14000d8ac`

## pseudocode

```c
__int64 __fastcall AslComputeCrc32(int a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // r9
  unsigned int i; // ecx
  __int64 v5; // rax

  v3 = 0;
  for ( i = ~a1; (unsigned int)v3 < a3; i = *((_DWORD *)AslpCrc32Table + v5) ^ (i >> 8) )
  {
    v5 = (unsigned __int8)(i ^ *(_BYTE *)(v3 + a2));
    v3 = (unsigned int)(v3 + 1);
  }
  return ~i;
}

```

## disassembly

```asm
0x14000d8ac  xor     r9d, r9d
0x14000d8af  mov     r10, rdx
0x14000d8b2  not     ecx
0x14000d8b4  test    r8d, r8d
0x14000d8b7  jz      short loc_14000D8DB
0x14000d8b9  movzx   edx, byte ptr [r9+r10]
0x14000d8be  mov     eax, ecx
0x14000d8c0  xor     rdx, rax
0x14000d8c3  shr     ecx, 8
0x14000d8c6  movzx   eax, dl
0x14000d8c9  inc     r9d
0x14000d8cc  lea     rdx, AslpCrc32Table
0x14000d8d3  xor     ecx, [rdx+rax*4]
0x14000d8d6  cmp     r9d, r8d
0x14000d8d9  jb      short loc_14000D8B9
0x14000d8db  not     ecx
0x14000d8dd  mov     eax, ecx
0x14000d8df  retn
```
