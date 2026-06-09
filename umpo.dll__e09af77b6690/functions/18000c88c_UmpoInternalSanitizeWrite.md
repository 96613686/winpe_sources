# UmpoInternalSanitizeWrite

- ea: `0x18000c88c`
- end: `0x18000c8ca`
- name: `UmpoInternalSanitizeWrite`
- size: `62`
- prototype: `__int64 __fastcall(__int64, unsigned int, _WORD *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c780`
- `0x180015150`

## callees

- `0x18000c88c`
- `0x180014b38`

## pseudocode

```c
__int64 __fastcall UmpoInternalSanitizeWrite(__int64 a1, unsigned int a2, _WORD *a3, unsigned int a4)
{
  unsigned int v4; // ebx
  int v5; // eax

  v4 = 0;
  if ( a2 <= 0xD )
  {
    v5 = 12396;
    if ( _bittest(&v5, a2) )
    {
      if ( a3 && a4 >= 2 && *a3 == 64 && (unsigned int)UmpoRpcIsAdministrator() )
        return 5;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000c88c  push    rbx
0x18000c88e  sub     rsp, 20h
0x18000c892  xor     ebx, ebx
0x18000c894  cmp     edx, 0Dh
0x18000c897  ja      short loc_18000C8C2
0x18000c899  mov     eax, 306Ch
0x18000c89e  bt      eax, edx
0x18000c8a1  jnb     short loc_18000C8C2
0x18000c8a3  test    r8, r8
0x18000c8a6  jz      short loc_18000C8C2
0x18000c8a8  cmp     r9d, 2
0x18000c8ac  jb      short loc_18000C8C2
0x18000c8ae  cmp     word ptr [r8], 40h ; '@'
0x18000c8b3  jnz     short loc_18000C8C2
0x18000c8b5  call    UmpoRpcIsAdministrator
0x18000c8ba  test    eax, eax
0x18000c8bc  lea     ecx, [rbx+5]
0x18000c8bf  cmovnz  ebx, ecx
0x18000c8c2  mov     eax, ebx
0x18000c8c4  add     rsp, 20h
0x18000c8c8  pop     rbx
0x18000c8c9  retn
```
