# Write_loca_Table

- ea: `0x180001ce4`
- end: `0x180001e42`
- name: `Write_loca_Table`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bde0`

## callees

- `0x180001ce4`
- `0x180001e48`
- `0x18001c9ec`

## pseudocode

```c
__int64 __fastcall Write_loca_Table(__int64 a1, __int64 a2, int a3, _QWORD *a4, int a5, __int64 a6)
{
  int v10; // r10d
  __int64 i; // r11
  int v12; // edx
  _BYTE *v13; // rbx
  __int64 v14; // r15
  _BYTE *j; // rbp
  int v16; // eax
  __int64 v17; // r12
  int v18; // edx

  v10 = *(_DWORD *)(a2 + 4LL * a3 - 4);
  for ( i = (unsigned int)(a3 - 2); (int)i >= 0; v10 = v12 )
  {
    v12 = *(_DWORD *)(a2 + 4 * i);
    if ( v12 <= v10 )
      v12 = v10;
    i = (unsigned int)(i - 1);
  }
  if ( v10 > 131070 )
  {
    AllocateTTFSpace(a1, (_DWORD)a4, a5, 4 * a3, a6);
    v17 = 0;
    v13 = (_BYTE *)(a5 + *a4);
    for ( j = v13; (int)v17 < a3; v13 += 4 )
    {
      if ( (*(_BYTE *)(a2 + 4 * v17) & 1) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v18 = *(_DWORD *)(a2 + 4 * v17);
      v13[1] = BYTE2(v18);
      *v13 = HIBYTE(v18);
      v13[2] = BYTE1(v18);
      v13[3] = v18;
      v17 = (unsigned int)(v17 + 1);
    }
    *(_WORD *)(a1 + 90) = 1;
    if ( v13 - j != 4 * a3 )
      goto LABEL_17;
  }
  else
  {
    AllocateTTFSpace(a1, (_DWORD)a4, a5, 2 * a3, a6);
    v13 = (_BYTE *)(a5 + *a4);
    v14 = 0;
    for ( j = v13; (int)v14 < a3; v13 += 2 )
    {
      if ( (*(_BYTE *)(a2 + 4 * v14) & 1) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v16 = *(_DWORD *)(a2 + 4 * v14);
      v14 = (unsigned int)(v14 + 1);
      v16 /= 2;
      *v13 = BYTE1(v16);
      v13[1] = v16;
    }
    *(_WORD *)(a1 + 90) = 0;
    if ( v13 - j != 2 * a3 )
LABEL_17:
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  return (unsigned int)((_DWORD)v13 - (_DWORD)j);
}

```

## disassembly

```asm
0x180001ce4  push    rbx
0x180001ce6  push    rbp
0x180001ce7  push    rsi
0x180001ce8  push    rdi
0x180001ce9  push    r12
0x180001ceb  push    r13
0x180001ced  push    r14
0x180001cef  push    r15
0x180001cf1  sub     rsp, 38h
0x180001cf5  movsxd  rsi, r8d
0x180001cf8  mov     rbx, r9
0x180001cfb  mov     rdi, rdx
0x180001cfe  mov     r14, rcx
0x180001d01  mov     r10d, [rdx+rsi*4-4]
0x180001d06  lea     r11d, [rsi-2]
0x180001d0a  test    r11d, r11d
0x180001d0d  js      short loc_180001D23
0x180001d0f  mov     edx, [rdi+r11*4]
0x180001d13  cmp     edx, r10d
0x180001d16  cmovle  edx, r10d
0x180001d1a  sub     r11d, 1
0x180001d1e  mov     r10d, edx
0x180001d21  jns     short loc_180001D0F
0x180001d23  movsxd  r8, [rsp+78h+arg_20]
0x180001d2b  mov     rdx, rbx
0x180001d2e  mov     rax, [rsp+78h+arg_28]
0x180001d36  mov     r15, r8
0x180001d39  mov     [rsp+78h+var_58], rax
0x180001d3e  cmp     r10d, 1FFFEh
0x180001d45  jg      short loc_180001DAE
0x180001d47  lea     r13d, [rsi+rsi]
0x180001d4b  mov     r9d, r13d
0x180001d4e  call    AllocateTTFSpace
0x180001d53  mov     rbx, [rbx]
0x180001d56  add     rbx, r15
0x180001d59  xor     r15d, r15d
0x180001d5c  mov     rbp, rbx
0x180001d5f  test    esi, esi
0x180001d61  jle     short loc_180001D92
0x180001d63  test    byte ptr [rdi+r15*4], 1
0x180001d68  jz      short loc_180001D6F
0x180001d6a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001d6f  mov     eax, [rdi+r15*4]
0x180001d73  mov     ecx, 2
0x180001d78  cdq
0x180001d79  inc     r15d
0x180001d7c  idiv    ecx
0x180001d7e  mov     ecx, eax
0x180001d80  shr     ax, 8
0x180001d84  mov     [rbx], al
0x180001d86  mov     [rbx+1], cl
0x180001d89  add     rbx, 2
0x180001d8d  cmp     r15d, esi
0x180001d90  jl      short loc_180001D63
0x180001d92  xor     eax, eax
0x180001d94  mov     rcx, rbx
0x180001d97  mov     [r14+5Ah], ax
0x180001d9c  sub     rcx, rbp
0x180001d9f  movsxd  rax, r13d
0x180001da2  cmp     rcx, rax
0x180001da5  jz      short loc_180001E1F
0x180001da7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001dac  jmp     short loc_180001E1F
0x180001dae  lea     r13d, ds:0[rsi*4]
0x180001db6  mov     r9d, r13d
0x180001db9  call    AllocateTTFSpace
0x180001dbe  mov     rbx, [rbx]
0x180001dc1  xor     r12d, r12d
0x180001dc4  add     rbx, r15
0x180001dc7  mov     rbp, rbx
0x180001dca  lea     eax, [r12+1]
0x180001dcf  test    esi, esi
0x180001dd1  jle     short loc_180001E0C
0x180001dd3  test    [rdi+r12*4], al
0x180001dd7  jnz     short loc_180001E34
0x180001dd9  mov     edx, [rdi+r12*4]
0x180001ddd  mov     ecx, edx
0x180001ddf  sar     ecx, 10h
0x180001de2  mov     [rbx+1], cl
0x180001de5  movzx   eax, cx
0x180001de8  shr     ax, 8
0x180001dec  mov     [rbx], al
0x180001dee  movzx   eax, dx
0x180001df1  shr     ax, 8
0x180001df5  mov     [rbx+2], al
0x180001df8  mov     eax, 1
0x180001dfd  mov     [rbx+3], dl
0x180001e00  add     r12d, eax
0x180001e03  add     rbx, 4
0x180001e07  cmp     r12d, esi
0x180001e0a  jl      short loc_180001DD3
0x180001e0c  mov     rdx, rbx
0x180001e0f  movsxd  rcx, r13d
0x180001e12  sub     rdx, rbp
0x180001e15  mov     [r14+5Ah], ax
0x180001e1a  cmp     rdx, rcx
0x180001e1d  jnz     short loc_180001E3B
0x180001e1f  sub     ebx, ebp
0x180001e21  mov     eax, ebx
0x180001e23  add     rsp, 38h
0x180001e27  pop     r15
0x180001e29  pop     r14
0x180001e2b  pop     r13
0x180001e2d  pop     r12
0x180001e2f  pop     rdi
0x180001e30  pop     rsi
0x180001e31  pop     rbp
0x180001e32  pop     rbx
0x180001e33  retn
0x180001e34  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001e39  jmp     short loc_180001DD9
0x180001e3b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001e40  jmp     short loc_180001E1F
```
