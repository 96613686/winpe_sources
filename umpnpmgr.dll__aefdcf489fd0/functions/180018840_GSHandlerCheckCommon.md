# __GSHandlerCheckCommon

- ea: `0x180018840`
- end: `0x1800188a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001881c`
- `0x1800188ac`

## callees

- `0x180018840`
- `0x180018970`

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
0x180018840  mov     r10, rcx
0x180018843  mov     r11, rdx
0x180018846  mov     ecx, [r8]
0x180018849  and     ecx, 0FFFFFFF8h
0x18001884c  test    byte ptr [r8], 4
0x180018850  jz      short loc_180018867
0x180018852  mov     eax, [r8+8]
0x180018856  movsxd  r9, dword ptr [r8+4]
0x18001885a  neg     eax
0x18001885c  movsxd  rdx, eax
0x18001885f  add     r9, r10
0x180018862  and     r9, rdx
0x180018865  jmp     short loc_18001886A
0x180018867  mov     r9, r10
0x18001886a  movsxd  rax, ecx
0x18001886d  mov     rdx, [rax+r9]
0x180018871  mov     rax, [r11+10h]
0x180018875  mov     ecx, [rax+8]
0x180018878  mov     rax, [r11+8]
0x18001887c  test    byte ptr [rcx+rax+3], 0Fh
0x180018881  jz      short loc_180018895
0x180018883  movzx   eax, byte ptr [rcx+rax+3]
0x180018888  mov     ecx, 0FFFFFFF0h
0x18001888d  and     rax, rcx
0x180018890  add     rax, r10
0x180018893  jmp     short loc_180018898
0x180018895  mov     rax, r10
0x180018898  xor     rdx, rax
0x18001889b  mov     rcx, rdx; StackCookie
0x18001889e  jmp     __security_check_cookie
```
