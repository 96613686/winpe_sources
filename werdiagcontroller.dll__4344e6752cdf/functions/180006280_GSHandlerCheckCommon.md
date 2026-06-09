# __GSHandlerCheckCommon

- ea: `0x180006280`
- end: `0x1800062e3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000625c`
- `0x1800062ec`

## callees

- `0x180001400`
- `0x180006280`

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
0x180006280  mov     r10, rcx
0x180006283  mov     r11, rdx
0x180006286  mov     ecx, [r8]
0x180006289  and     ecx, 0FFFFFFF8h
0x18000628c  test    byte ptr [r8], 4
0x180006290  jz      short loc_1800062A7
0x180006292  mov     eax, [r8+8]
0x180006296  movsxd  r9, dword ptr [r8+4]
0x18000629a  neg     eax
0x18000629c  movsxd  rdx, eax
0x18000629f  add     r9, r10
0x1800062a2  and     r9, rdx
0x1800062a5  jmp     short loc_1800062AA
0x1800062a7  mov     r9, r10
0x1800062aa  movsxd  rax, ecx
0x1800062ad  mov     rdx, [rax+r9]
0x1800062b1  mov     rax, [r11+10h]
0x1800062b5  mov     ecx, [rax+8]
0x1800062b8  mov     rax, [r11+8]
0x1800062bc  test    byte ptr [rcx+rax+3], 0Fh
0x1800062c1  jz      short loc_1800062D5
0x1800062c3  movzx   eax, byte ptr [rcx+rax+3]
0x1800062c8  mov     ecx, 0FFFFFFF0h
0x1800062cd  and     rax, rcx
0x1800062d0  add     rax, r10
0x1800062d3  jmp     short loc_1800062D8
0x1800062d5  mov     rax, r10
0x1800062d8  xor     rdx, rax
0x1800062db  mov     rcx, rdx; StackCookie
0x1800062de  jmp     __security_check_cookie
```
