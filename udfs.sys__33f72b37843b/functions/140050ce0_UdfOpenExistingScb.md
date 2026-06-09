# UdfOpenExistingScb

- ea: `0x140050ce0`
- end: `0x140050ed3`
- name: `UdfOpenExistingScb`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140042c40`

## callees

- `0x140010c5c`
- `0x14004ce50`
- `0x140050ce0`
- `0x140050ee0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140050e80`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050e80`

## pseudocode

```c
__int64 __fastcall UdfOpenExistingScb(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        ULONG a6,
        char a7,
        char a8,
        char a9,
        __int64 a10,
        ULONG a11)
{
  __int64 v11; // rbp
  unsigned int v15; // ebx
  int v18; // ecx
  int v19; // ecx
  int v20; // r11d
  __int64 v22; // rbp
  int v23; // r11d

  v11 = a4;
  v15 = -1073741790;
  if ( (*(_BYTE *)(a2 + 2) & 4) != 0 && a9 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
    {
      WPP_SF_qq(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        15,
        WPP_962a5ab0fb873cc757a84452495a3943_Traceguids,
        *(_QWORD *)(a4 + 24),
        *a3);
    }
    UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 24) + 136LL) + 80LL) + 8LL, 0, 0);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*a3 + 136) + 80LL) + 8LL));
    v22 = *(_QWORD *)(v11 + 24);
    a6 = 3;
    *a3 = v22;
    if ( v22 == *(_QWORD *)(*(_QWORD *)(a1 + 16) + 288LL) )
      v11 = 0;
    else
      v11 = *(_QWORD *)(v22 + 160) - 32LL;
    a8 = 0;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 0x10) != 0 )
  {
    v18 = 278;
    if ( a6 == 2 )
      v18 = 0;
    if ( ((v18 | 0x50040) & *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL)) != 0 )
      return v15;
  }
  if ( *(_WORD *)*a3 != 2355 || (a11 & 0xFFFFFFFA) != 0 || a11 == 1 )
  {
    v19 = (a7 != 0 ? 4 : 0) | 0x80;
    if ( !a8 )
      v19 = a7 != 0 ? 4 : 0;
    v20 = v19;
    if ( a10 )
    {
      v23 = v19 | 2;
      if ( (*(_DWORD *)(a10 + 4) & 3) == 0 )
        v23 = v19;
      v20 = v23 | 0x800;
    }
    return (unsigned int)UdfCompleteScbOpen(
                           a1,
                           a2,
                           *(_QWORD *)(*(_QWORD *)(*a3 + 136) + 8LL),
                           a3,
                           v11,
                           a5,
                           a6,
                           v20,
                           a11,
                           a9);
  }
  return 3221225525LL;
}

```

## disassembly

```asm
0x140050ce0  push    rbx
0x140050ce2  push    rbp
0x140050ce3  push    rsi
0x140050ce4  push    rdi
0x140050ce5  push    r14
0x140050ce7  push    r15
0x140050ce9  sub     rsp, 58h
0x140050ced  test    byte ptr [rdx+2], 4
0x140050cf1  mov     rbp, r9
0x140050cf4  movzx   r15d, [rsp+88h+arg_40]
0x140050cfd  mov     r14, r8
0x140050d00  mov     rdi, rdx
0x140050d03  mov     rsi, rcx
0x140050d06  mov     ebx, 0C0000022h
0x140050d0b  jnz     loc_140050E09
0x140050d11  mov     edx, [rsp+88h+arg_28]
0x140050d18  movzx   r8d, [rsp+88h+arg_38]
0x140050d21  mov     rax, [rsi+10h]
0x140050d25  mov     ecx, [rax+30h]
0x140050d28  test    cl, 10h
0x140050d2b  jz      short loc_140050D4D
0x140050d2d  xor     eax, eax
0x140050d2f  mov     ecx, 116h
0x140050d34  cmp     edx, 2
0x140050d37  cmovz   ecx, eax
0x140050d3a  mov     rax, [rdi+8]
0x140050d3e  or      ecx, 50040h
0x140050d44  test    [rax+10h], ecx
0x140050d47  jnz     loc_140050DCF
0x140050d4d  mov     r10, [r14]
0x140050d50  mov     eax, 933h
0x140050d55  mov     r9d, [rsp+88h+arg_50]
0x140050d5d  cmp     ax, [r10]
0x140050d61  jz      short loc_140050DDF
0x140050d63  neg     [rsp+88h+arg_30]
0x140050d6a  sbb     eax, eax
0x140050d6c  and     eax, 4
0x140050d6f  mov     ecx, eax
0x140050d71  bts     ecx, 7
0x140050d75  test    r8b, r8b
0x140050d78  cmovz   ecx, eax
0x140050d7b  mov     rax, [rsp+88h+arg_48]
0x140050d83  mov     r11d, ecx
0x140050d86  test    rax, rax
0x140050d89  jnz     loc_140050EBC
0x140050d8f  mov     r8, [r10+88h]
0x140050d96  mov     rcx, rsi; int
0x140050d99  mov     rax, [rsp+88h+arg_20]
0x140050da1  mov     [rsp+88h+var_40], r15b; char
0x140050da6  mov     [rsp+88h+var_48], r9d; ULONG
0x140050dab  mov     r9, r14; int
0x140050dae  mov     r8, [r8+8]; int
0x140050db2  mov     [rsp+88h+var_50], r11d; int
0x140050db7  mov     [rsp+88h+var_58], edx; ULONG
0x140050dbb  mov     rdx, rdi; int
0x140050dbe  mov     [rsp+88h+var_60], rax; __int64
0x140050dc3  mov     qword ptr [rsp+88h+var_68], rbp; int
0x140050dc8  call    UdfCompleteScbOpen
0x140050dcd  mov     ebx, eax
0x140050dcf  mov     eax, ebx
0x140050dd1  add     rsp, 58h
0x140050dd5  pop     r15
0x140050dd7  pop     r14
0x140050dd9  pop     rdi
0x140050dda  pop     rsi
0x140050ddb  pop     rbp
0x140050ddc  pop     rbx
0x140050ddd  retn
0x140050ddf  test    r9d, 0FFFFFFFAh
0x140050de6  jnz     loc_140050D63
0x140050dec  cmp     r9d, 1
0x140050df0  jz      loc_140050D63
0x140050df6  mov     eax, 0C0000035h
0x140050dfb  add     rsp, 58h
0x140050dff  pop     r15
0x140050e01  pop     r14
0x140050e03  pop     rdi
0x140050e04  pop     rsi
0x140050e05  pop     rbp
0x140050e06  pop     rbx
0x140050e07  retn
0x140050e09  test    r15b, r15b
0x140050e0c  jz      loc_140050D11
0x140050e12  mov     rcx, cs:WPP_GLOBAL_Control
0x140050e19  lea     rax, WPP_GLOBAL_Control
0x140050e20  cmp     rcx, rax
0x140050e23  jz      short loc_140050E4D
0x140050e25  mov     eax, [rcx+2Ch]
0x140050e28  test    al, 10h
0x140050e2a  jz      short loc_140050E4D
0x140050e2c  mov     rax, [r8]
0x140050e2f  mov     edx, 0Fh
0x140050e34  mov     r9, [r9+18h]
0x140050e38  lea     r8, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids
0x140050e3f  mov     rcx, [rcx+18h]
0x140050e43  mov     qword ptr [rsp+88h+var_68], rax
0x140050e48  call    WPP_SF_qq
0x140050e4d  mov     rax, [rbp+18h]
0x140050e51  xor     r9d, r9d
0x140050e54  xor     r8d, r8d
0x140050e57  mov     rcx, [rax+88h]
0x140050e5e  mov     rdx, [rcx+50h]
0x140050e62  mov     rcx, rsi
0x140050e65  add     rdx, 8
0x140050e69  call    UdfAcquireResource
0x140050e6e  mov     rax, [r14]
0x140050e71  mov     rcx, [rax+88h]
0x140050e78  mov     rcx, [rcx+50h]
0x140050e7c  add     rcx, 8; Resource
0x140050e80  call    cs:__imp_ExReleaseResourceLite
0x140050e87  nop     dword ptr [rax+rax+00h]
0x140050e8c  mov     rbp, [rbp+18h]
0x140050e90  mov     edx, 3
0x140050e95  mov     [r14], rbp
0x140050e98  mov     rax, [rsi+10h]
0x140050e9c  cmp     rbp, [rax+120h]
0x140050ea3  jz      short loc_140050EB2
0x140050ea5  mov     rbp, [rbp+0A0h]
0x140050eac  sub     rbp, 20h ; ' '
0x140050eb0  jmp     short loc_140050EB4
0x140050eb2  xor     ebp, ebp
0x140050eb4  xor     r8b, r8b
0x140050eb7  jmp     loc_140050D21
0x140050ebc  mov     eax, [rax+4]
0x140050ebf  or      r11d, 2
0x140050ec3  test    al, 3
0x140050ec5  cmovz   r11d, ecx
0x140050ec9  bts     r11d, 0Bh
0x140050ece  jmp     loc_140050D8F
```
