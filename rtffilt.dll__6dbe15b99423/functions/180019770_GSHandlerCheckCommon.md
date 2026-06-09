# __GSHandlerCheckCommon

- ea: `0x180019770`
- end: `0x1800197d3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001974c`
- `0x1800197dc`

## callees

- `0x180001e40`
- `0x180019770`

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
0x180019770  mov     r10, rcx
0x180019773  mov     r11, rdx
0x180019776  mov     ecx, [r8]
0x180019779  and     ecx, 0FFFFFFF8h
0x18001977c  test    byte ptr [r8], 4
0x180019780  jz      short loc_180019797
0x180019782  mov     eax, [r8+8]
0x180019786  movsxd  r9, dword ptr [r8+4]
0x18001978a  neg     eax
0x18001978c  movsxd  rdx, eax
0x18001978f  add     r9, r10
0x180019792  and     r9, rdx
0x180019795  jmp     short loc_18001979A
0x180019797  mov     r9, r10
0x18001979a  movsxd  rax, ecx
0x18001979d  mov     rdx, [rax+r9]
0x1800197a1  mov     rax, [r11+10h]
0x1800197a5  mov     ecx, [rax+8]
0x1800197a8  mov     rax, [r11+8]
0x1800197ac  test    byte ptr [rcx+rax+3], 0Fh
0x1800197b1  jz      short loc_1800197C5
0x1800197b3  movzx   eax, byte ptr [rcx+rax+3]
0x1800197b8  mov     ecx, 0FFFFFFF0h
0x1800197bd  and     rax, rcx
0x1800197c0  add     rax, r10
0x1800197c3  jmp     short loc_1800197C8
0x1800197c5  mov     rax, r10
0x1800197c8  xor     rdx, rax
0x1800197cb  mov     rcx, rdx; StackCookie
0x1800197ce  jmp     __security_check_cookie
```
