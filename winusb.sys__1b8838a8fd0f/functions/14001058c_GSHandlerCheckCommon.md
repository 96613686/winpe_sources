# __GSHandlerCheckCommon

- ea: `0x14001058c`
- end: `0x1400105fc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010568`

## callees

- `0x14001058c`
- `0x1400106c0`

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
0x14001058c  sub     rsp, 28h
0x140010590  mov     eax, [r8]
0x140010593  mov     r10, rcx
0x140010596  mov     ecx, eax
0x140010598  mov     r11, rdx
0x14001059b  and     ecx, 0FFFFFFF8h
0x14001059e  test    al, 4
0x1400105a0  jz      short loc_1400105B7
0x1400105a2  mov     eax, [r8+8]
0x1400105a6  movsxd  r9, dword ptr [r8+4]
0x1400105aa  neg     eax
0x1400105ac  movsxd  rdx, eax
0x1400105af  add     r9, r10
0x1400105b2  and     r9, rdx
0x1400105b5  jmp     short loc_1400105BA
0x1400105b7  mov     r9, r10
0x1400105ba  movsxd  rax, ecx
0x1400105bd  mov     rdx, [rax+r9]
0x1400105c1  mov     rax, [r11+10h]
0x1400105c5  mov     ecx, [rax+8]
0x1400105c8  mov     rax, [r11+8]
0x1400105cc  movzx   r8d, byte ptr [rcx+rax+3]
0x1400105d2  test    r8b, 0Fh
0x1400105d6  jz      short loc_1400105E8
0x1400105d8  mov     eax, r8d
0x1400105db  mov     ecx, 0FFFFFFF0h
0x1400105e0  and     rax, rcx
0x1400105e3  add     rax, r10
0x1400105e6  jmp     short loc_1400105EB
0x1400105e8  mov     rax, r10
0x1400105eb  xor     rdx, rax
0x1400105ee  mov     rcx, rdx; StackCookie
0x1400105f1  call    __security_check_cookie
0x1400105f6  add     rsp, 28h
0x1400105fa  retn
```
