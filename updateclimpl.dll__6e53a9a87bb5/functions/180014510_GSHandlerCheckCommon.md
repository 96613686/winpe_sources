# __GSHandlerCheckCommon

- ea: `0x180014510`
- end: `0x180014570`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800144ec`
- `0x180014654`
- `0x1800147d8`

## callees

- `0x180010310`
- `0x180014510`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x180014510  push    rbx
0x180014512  mov     r11d, [r8]
0x180014515  mov     rbx, rdx
0x180014518  and     r11d, 0FFFFFFF8h
0x18001451c  mov     r9, rcx
0x18001451f  test    byte ptr [r8], 4
0x180014523  mov     r10, rcx
0x180014526  jz      short loc_18001453B
0x180014528  mov     eax, [r8+8]
0x18001452c  movsxd  r10, dword ptr [r8+4]
0x180014530  neg     eax
0x180014532  add     r10, rcx
0x180014535  movsxd  rcx, eax
0x180014538  and     r10, rcx
0x18001453b  movsxd  rax, r11d
0x18001453e  mov     rdx, [rax+r10]
0x180014542  mov     rax, [rbx+10h]
0x180014546  mov     ecx, [rax+8]
0x180014549  mov     rax, [rbx+8]
0x18001454d  test    byte ptr [rcx+rax+3], 0Fh
0x180014552  jz      short loc_180014564
0x180014554  movzx   eax, byte ptr [rcx+rax+3]
0x180014559  mov     ecx, 0FFFFFFF0h
0x18001455e  and     rax, rcx
0x180014561  add     r9, rax
0x180014564  xor     r9, rdx
0x180014567  mov     rcx, r9; StackCookie
0x18001456a  pop     rbx
0x18001456b  jmp     __security_check_cookie
```
