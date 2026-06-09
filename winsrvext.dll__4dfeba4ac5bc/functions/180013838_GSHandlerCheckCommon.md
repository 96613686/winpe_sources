# __GSHandlerCheckCommon

- ea: `0x180013838`
- end: `0x18001389b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013814`

## callees

- `0x180013838`
- `0x1800138f0`

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
0x180013838  mov     r10, rcx
0x18001383b  mov     r11, rdx
0x18001383e  mov     ecx, [r8]
0x180013841  and     ecx, 0FFFFFFF8h
0x180013844  test    byte ptr [r8], 4
0x180013848  jz      short loc_18001385F
0x18001384a  mov     eax, [r8+8]
0x18001384e  movsxd  r9, dword ptr [r8+4]
0x180013852  neg     eax
0x180013854  movsxd  rdx, eax
0x180013857  add     r9, r10
0x18001385a  and     r9, rdx
0x18001385d  jmp     short loc_180013862
0x18001385f  mov     r9, r10
0x180013862  movsxd  rax, ecx
0x180013865  mov     rdx, [rax+r9]
0x180013869  mov     rax, [r11+10h]
0x18001386d  mov     ecx, [rax+8]
0x180013870  mov     rax, [r11+8]
0x180013874  test    byte ptr [rcx+rax+3], 0Fh
0x180013879  jz      short loc_18001388D
0x18001387b  movzx   eax, byte ptr [rcx+rax+3]
0x180013880  mov     ecx, 0FFFFFFF0h
0x180013885  and     rax, rcx
0x180013888  add     rax, r10
0x18001388b  jmp     short loc_180013890
0x18001388d  mov     rax, r10
0x180013890  xor     rdx, rax
0x180013893  mov     rcx, rdx; StackCookie
0x180013896  jmp     __security_check_cookie
```
