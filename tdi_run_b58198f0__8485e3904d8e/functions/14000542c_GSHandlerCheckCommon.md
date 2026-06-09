# __GSHandlerCheckCommon

- ea: `0x14000542c`
- end: `0x14000549c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005408`

## callees

- `0x14000542c`
- `0x1400054b0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x14000542c  sub     rsp, 28h
0x140005430  mov     eax, [r8]
0x140005433  mov     r10, rcx
0x140005436  mov     ecx, eax
0x140005438  mov     r11, rdx
0x14000543b  and     ecx, 0FFFFFFF8h
0x14000543e  test    al, 4
0x140005440  jz      short loc_140005457
0x140005442  mov     eax, [r8+8]
0x140005446  movsxd  r9, dword ptr [r8+4]
0x14000544a  neg     eax
0x14000544c  movsxd  rdx, eax
0x14000544f  add     r9, r10
0x140005452  and     r9, rdx
0x140005455  jmp     short loc_14000545A
0x140005457  mov     r9, r10
0x14000545a  movsxd  rax, ecx
0x14000545d  mov     rdx, [rax+r9]
0x140005461  mov     rax, [r11+10h]
0x140005465  mov     ecx, [rax+8]
0x140005468  mov     rax, [r11+8]
0x14000546c  movzx   r8d, byte ptr [rcx+rax+3]
0x140005472  test    r8b, 0Fh
0x140005476  jz      short loc_140005488
0x140005478  mov     eax, r8d
0x14000547b  mov     ecx, 0FFFFFFF0h
0x140005480  and     rax, rcx
0x140005483  add     rax, r10
0x140005486  jmp     short loc_14000548B
0x140005488  mov     rax, r10
0x14000548b  xor     rdx, rax
0x14000548e  mov     rcx, rdx; StackCookie
0x140005491  call    __security_check_cookie
0x140005496  add     rsp, 28h
0x14000549a  retn
```
