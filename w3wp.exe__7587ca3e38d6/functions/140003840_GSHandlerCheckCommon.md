# __GSHandlerCheckCommon

- ea: `0x140003840`
- end: `0x1400038a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000381c`

## callees

- `0x140003840`
- `0x1400038e0`

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
0x140003840  mov     r10, rcx
0x140003843  mov     r11, rdx
0x140003846  mov     ecx, [r8]
0x140003849  and     ecx, 0FFFFFFF8h
0x14000384c  test    byte ptr [r8], 4
0x140003850  jz      short loc_140003867
0x140003852  mov     eax, [r8+8]
0x140003856  movsxd  r9, dword ptr [r8+4]
0x14000385a  neg     eax
0x14000385c  movsxd  rdx, eax
0x14000385f  add     r9, r10
0x140003862  and     r9, rdx
0x140003865  jmp     short loc_14000386A
0x140003867  mov     r9, r10
0x14000386a  movsxd  rax, ecx
0x14000386d  mov     rdx, [rax+r9]
0x140003871  mov     rax, [r11+10h]
0x140003875  mov     ecx, [rax+8]
0x140003878  mov     rax, [r11+8]
0x14000387c  test    byte ptr [rcx+rax+3], 0Fh
0x140003881  jz      short loc_140003895
0x140003883  movzx   eax, byte ptr [rcx+rax+3]
0x140003888  mov     ecx, 0FFFFFFF0h
0x14000388d  and     rax, rcx
0x140003890  add     rax, r10
0x140003893  jmp     short loc_140003898
0x140003895  mov     rax, r10
0x140003898  xor     rdx, rax
0x14000389b  mov     rcx, rdx; StackCookie
0x14000389e  jmp     __security_check_cookie
```
