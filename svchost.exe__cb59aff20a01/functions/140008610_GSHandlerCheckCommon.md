# __GSHandlerCheckCommon

- ea: `0x140008610`
- end: `0x140008673`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400085ec`

## callees

- `0x140004bd0`
- `0x140008610`

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
0x140008610  mov     r10, rcx
0x140008613  mov     r11, rdx
0x140008616  mov     ecx, [r8]
0x140008619  and     ecx, 0FFFFFFF8h
0x14000861c  test    byte ptr [r8], 4
0x140008620  jz      short loc_140008637
0x140008622  mov     eax, [r8+8]
0x140008626  movsxd  r9, dword ptr [r8+4]
0x14000862a  neg     eax
0x14000862c  movsxd  rdx, eax
0x14000862f  add     r9, r10
0x140008632  and     r9, rdx
0x140008635  jmp     short loc_14000863A
0x140008637  mov     r9, r10
0x14000863a  movsxd  rax, ecx
0x14000863d  mov     rdx, [rax+r9]
0x140008641  mov     rax, [r11+10h]
0x140008645  mov     ecx, [rax+8]
0x140008648  mov     rax, [r11+8]
0x14000864c  test    byte ptr [rcx+rax+3], 0Fh
0x140008651  jz      short loc_140008665
0x140008653  movzx   eax, byte ptr [rcx+rax+3]
0x140008658  mov     ecx, 0FFFFFFF0h
0x14000865d  and     rax, rcx
0x140008660  add     rax, r10
0x140008663  jmp     short loc_140008668
0x140008665  mov     rax, r10
0x140008668  xor     rdx, rax
0x14000866b  mov     rcx, rdx; StackCookie
0x14000866e  jmp     __security_check_cookie
```
