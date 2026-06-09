# __GSHandlerCheckCommon

- ea: `0x180003064`
- end: `0x1800030c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003040`
- `0x1800030d0`

## callees

- `0x180002570`
- `0x180003064`

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
0x180003064  mov     r10, rcx
0x180003067  mov     r11, rdx
0x18000306a  mov     ecx, [r8]
0x18000306d  and     ecx, 0FFFFFFF8h
0x180003070  test    byte ptr [r8], 4
0x180003074  jz      short loc_18000308B
0x180003076  mov     eax, [r8+8]
0x18000307a  movsxd  r9, dword ptr [r8+4]
0x18000307e  neg     eax
0x180003080  movsxd  rdx, eax
0x180003083  add     r9, r10
0x180003086  and     r9, rdx
0x180003089  jmp     short loc_18000308E
0x18000308b  mov     r9, r10
0x18000308e  movsxd  rax, ecx
0x180003091  mov     rdx, [rax+r9]
0x180003095  mov     rax, [r11+10h]
0x180003099  mov     ecx, [rax+8]
0x18000309c  mov     rax, [r11+8]
0x1800030a0  test    byte ptr [rcx+rax+3], 0Fh
0x1800030a5  jz      short loc_1800030B9
0x1800030a7  movzx   eax, byte ptr [rcx+rax+3]
0x1800030ac  mov     ecx, 0FFFFFFF0h
0x1800030b1  and     rax, rcx
0x1800030b4  add     rax, r10
0x1800030b7  jmp     short loc_1800030BC
0x1800030b9  mov     rax, r10
0x1800030bc  xor     rdx, rax
0x1800030bf  mov     rcx, rdx; StackCookie
0x1800030c2  jmp     __security_check_cookie
```
