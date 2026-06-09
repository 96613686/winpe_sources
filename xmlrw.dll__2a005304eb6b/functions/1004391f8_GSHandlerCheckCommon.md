# __GSHandlerCheckCommon

- ea: `0x1004391f8`
- end: `0x100439253`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1004391d4`
- `0x1004392d4`

## callees

- `0x100426580`
- `0x1004391f8`

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
0x1004391f8  push    rbx
0x1004391fa  mov     r11d, [r8]
0x1004391fd  mov     rbx, rdx
0x100439200  and     r11d, 0FFFFFFF8h
0x100439204  mov     r9, rcx
0x100439207  test    byte ptr [r8], 4
0x10043920b  mov     r10, rcx
0x10043920e  jz      short loc_100439223
0x100439210  mov     eax, [r8+8]
0x100439214  movsxd  r10, dword ptr [r8+4]
0x100439218  neg     eax
0x10043921a  add     r10, rcx
0x10043921d  movsxd  rcx, eax
0x100439220  and     r10, rcx
0x100439223  movsxd  rax, r11d
0x100439226  mov     rdx, [rax+r10]
0x10043922a  mov     rax, [rbx+10h]
0x10043922e  mov     ecx, [rax+8]
0x100439231  mov     rax, [rbx+8]
0x100439235  test    byte ptr [rcx+rax+3], 0Fh
0x10043923a  jz      short loc_100439247
0x10043923c  movzx   eax, byte ptr [rcx+rax+3]
0x100439241  and     eax, 0FFFFFFF0h
0x100439244  add     r9, rax
0x100439247  xor     r9, rdx
0x10043924a  mov     rcx, r9; StackCookie
0x10043924d  pop     rbx
0x10043924e  jmp     __security_check_cookie
```
