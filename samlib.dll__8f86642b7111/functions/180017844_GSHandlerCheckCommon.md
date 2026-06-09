# __GSHandlerCheckCommon

- ea: `0x180017844`
- end: `0x1800178a7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017820`
- `0x1800178b0`

## callees

- `0x180006620`
- `0x180017844`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x180017844  mov     r10, rcx
0x180017847  mov     r11, rdx
0x18001784a  mov     ecx, [r8]
0x18001784d  and     ecx, 0FFFFFFF8h
0x180017850  test    byte ptr [r8], 4
0x180017854  jz      short loc_18001786B
0x180017856  mov     eax, [r8+8]
0x18001785a  movsxd  r9, dword ptr [r8+4]
0x18001785e  neg     eax
0x180017860  movsxd  rdx, eax
0x180017863  add     r9, r10
0x180017866  and     r9, rdx
0x180017869  jmp     short loc_18001786E
0x18001786b  mov     r9, r10
0x18001786e  movsxd  rax, ecx
0x180017871  mov     rdx, [rax+r9]
0x180017875  mov     rax, [r11+10h]
0x180017879  mov     ecx, [rax+8]
0x18001787c  mov     rax, [r11+8]
0x180017880  test    byte ptr [rcx+rax+3], 0Fh
0x180017885  jz      short loc_180017899
0x180017887  movzx   eax, byte ptr [rcx+rax+3]
0x18001788c  mov     ecx, 0FFFFFFF0h
0x180017891  and     rax, rcx
0x180017894  add     rax, r10
0x180017897  jmp     short loc_18001789C
0x180017899  mov     rax, r10
0x18001789c  xor     rdx, rax
0x18001789f  mov     rcx, rdx; StackCookie
0x1800178a2  jmp     __security_check_cookie
```
