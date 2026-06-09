# __GSHandlerCheckCommon

- ea: `0x14001550c`
- end: `0x14001557c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400154e8`

## callees

- `0x14001550c`
- `0x140015640`

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
0x14001550c  sub     rsp, 28h
0x140015510  mov     eax, [r8]
0x140015513  mov     r10, rcx
0x140015516  mov     ecx, eax
0x140015518  mov     r11, rdx
0x14001551b  and     ecx, 0FFFFFFF8h
0x14001551e  test    al, 4
0x140015520  jz      short loc_140015537
0x140015522  mov     eax, [r8+8]
0x140015526  movsxd  r9, dword ptr [r8+4]
0x14001552a  neg     eax
0x14001552c  movsxd  rdx, eax
0x14001552f  add     r9, r10
0x140015532  and     r9, rdx
0x140015535  jmp     short loc_14001553A
0x140015537  mov     r9, r10
0x14001553a  movsxd  rax, ecx
0x14001553d  mov     rdx, [rax+r9]
0x140015541  mov     rax, [r11+10h]
0x140015545  mov     ecx, [rax+8]
0x140015548  mov     rax, [r11+8]
0x14001554c  movzx   r8d, byte ptr [rcx+rax+3]
0x140015552  test    r8b, 0Fh
0x140015556  jz      short loc_140015568
0x140015558  mov     eax, r8d
0x14001555b  mov     ecx, 0FFFFFFF0h
0x140015560  and     rax, rcx
0x140015563  add     rax, r10
0x140015566  jmp     short loc_14001556B
0x140015568  mov     rax, r10
0x14001556b  xor     rdx, rax
0x14001556e  mov     rcx, rdx; StackCookie
0x140015571  call    __security_check_cookie
0x140015576  add     rsp, 28h
0x14001557a  retn
```
