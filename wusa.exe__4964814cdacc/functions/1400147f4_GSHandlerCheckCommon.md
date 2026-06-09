# __GSHandlerCheckCommon

- ea: `0x1400147f4`
- end: `0x140014857`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400147d0`
- `0x140014860`

## callees

- `0x1400147f4`
- `0x140014910`

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
0x1400147f4  mov     r10, rcx
0x1400147f7  mov     r11, rdx
0x1400147fa  mov     ecx, [r8]
0x1400147fd  and     ecx, 0FFFFFFF8h
0x140014800  test    byte ptr [r8], 4
0x140014804  jz      short loc_14001481B
0x140014806  mov     eax, [r8+8]
0x14001480a  movsxd  r9, dword ptr [r8+4]
0x14001480e  neg     eax
0x140014810  movsxd  rdx, eax
0x140014813  add     r9, r10
0x140014816  and     r9, rdx
0x140014819  jmp     short loc_14001481E
0x14001481b  mov     r9, r10
0x14001481e  movsxd  rax, ecx
0x140014821  mov     rdx, [rax+r9]
0x140014825  mov     rax, [r11+10h]
0x140014829  mov     ecx, [rax+8]
0x14001482c  mov     rax, [r11+8]
0x140014830  test    byte ptr [rcx+rax+3], 0Fh
0x140014835  jz      short loc_140014849
0x140014837  movzx   eax, byte ptr [rcx+rax+3]
0x14001483c  mov     ecx, 0FFFFFFF0h
0x140014841  and     rax, rcx
0x140014844  add     rax, r10
0x140014847  jmp     short loc_14001484C
0x140014849  mov     rax, r10
0x14001484c  xor     rdx, rax
0x14001484f  mov     rcx, rdx; StackCookie
0x140014852  jmp     __security_check_cookie
```
