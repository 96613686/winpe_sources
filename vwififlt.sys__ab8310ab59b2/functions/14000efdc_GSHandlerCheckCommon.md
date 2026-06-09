# __GSHandlerCheckCommon

- ea: `0x14000efdc`
- end: `0x14000f04c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000efb8`

## callees

- `0x14000efdc`
- `0x14000f110`

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
0x14000efdc  sub     rsp, 28h
0x14000efe0  mov     eax, [r8]
0x14000efe3  mov     r10, rcx
0x14000efe6  mov     ecx, eax
0x14000efe8  mov     r11, rdx
0x14000efeb  and     ecx, 0FFFFFFF8h
0x14000efee  test    al, 4
0x14000eff0  jz      short loc_14000F007
0x14000eff2  mov     eax, [r8+8]
0x14000eff6  movsxd  r9, dword ptr [r8+4]
0x14000effa  neg     eax
0x14000effc  movsxd  rdx, eax
0x14000efff  add     r9, r10
0x14000f002  and     r9, rdx
0x14000f005  jmp     short loc_14000F00A
0x14000f007  mov     r9, r10
0x14000f00a  movsxd  rax, ecx
0x14000f00d  mov     rdx, [rax+r9]
0x14000f011  mov     rax, [r11+10h]
0x14000f015  mov     ecx, [rax+8]
0x14000f018  mov     rax, [r11+8]
0x14000f01c  movzx   r8d, byte ptr [rcx+rax+3]
0x14000f022  test    r8b, 0Fh
0x14000f026  jz      short loc_14000F038
0x14000f028  mov     eax, r8d
0x14000f02b  mov     ecx, 0FFFFFFF0h
0x14000f030  and     rax, rcx
0x14000f033  add     rax, r10
0x14000f036  jmp     short loc_14000F03B
0x14000f038  mov     rax, r10
0x14000f03b  xor     rdx, rax
0x14000f03e  mov     rcx, rdx; StackCookie
0x14000f041  call    __security_check_cookie
0x14000f046  add     rsp, 28h
0x14000f04a  retn
```
