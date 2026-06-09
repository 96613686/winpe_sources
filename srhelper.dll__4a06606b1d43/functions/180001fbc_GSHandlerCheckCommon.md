# __GSHandlerCheckCommon

- ea: `0x180001fbc`
- end: `0x18000201f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f98`

## callees

- `0x180001fbc`
- `0x1800157f0`

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
0x180001fbc  mov     r10, rcx
0x180001fbf  mov     r11, rdx
0x180001fc2  mov     ecx, [r8]
0x180001fc5  and     ecx, 0FFFFFFF8h
0x180001fc8  test    byte ptr [r8], 4
0x180001fcc  jz      short loc_180001FE3
0x180001fce  mov     eax, [r8+8]
0x180001fd2  movsxd  r9, dword ptr [r8+4]
0x180001fd6  neg     eax
0x180001fd8  movsxd  rdx, eax
0x180001fdb  add     r9, r10
0x180001fde  and     r9, rdx
0x180001fe1  jmp     short loc_180001FE6
0x180001fe3  mov     r9, r10
0x180001fe6  movsxd  rax, ecx
0x180001fe9  mov     rdx, [rax+r9]
0x180001fed  mov     rax, [r11+10h]
0x180001ff1  mov     ecx, [rax+8]
0x180001ff4  mov     rax, [r11+8]
0x180001ff8  test    byte ptr [rcx+rax+3], 0Fh
0x180001ffd  jz      short loc_180002011
0x180001fff  movzx   eax, byte ptr [rcx+rax+3]
0x180002004  mov     ecx, 0FFFFFFF0h
0x180002009  and     rax, rcx
0x18000200c  add     rax, r10
0x18000200f  jmp     short loc_180002014
0x180002011  mov     rax, r10
0x180002014  xor     rdx, rax
0x180002017  mov     rcx, rdx; StackCookie
0x18000201a  jmp     __security_check_cookie
```
