# I_MinCryptGetHashAlgorithmFromSignature

- ea: `0x180014d74`
- end: `0x180014ebe`
- name: `I_MinCryptGetHashAlgorithmFromSignature`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180015e90`

## callees

- `0x180014d74`
- `0x180015f14`
- `0x18001618c`

## pseudocode

```c
__int64 __fastcall I_MinCryptGetHashAlgorithmFromSignature(
        __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        _OWORD *a6,
        _DWORD *a7)
{
  _DWORD *v10; // rdi
  _DWORD *v11; // r8
  __int64 v12; // rsi
  int NextSignature; // ecx
  unsigned int v14; // ebx
  unsigned int *v15; // r12
  __int128 v16; // [rsp+38h] [rbp-40h] BYREF
  int v17; // [rsp+90h] [rbp+18h] BYREF
  unsigned int v18; // [rsp+98h] [rbp+20h] BYREF

  v18 = 0;
  v17 = 0;
  v16 = 0;
  if ( a3 < a4 )
    return 3221225485LL;
  v10 = a7;
  v11 = (_DWORD *)((unsigned __int64)&v17 & -(__int64)(a7 != 0));
  v12 = (__int64)a6;
  *a6 = 0;
  *(_OWORD *)(v12 + 16) = 0;
  *(_QWORD *)(v12 + 32) = 0;
  *((_QWORD *)&v16 + 1) = a1;
  LODWORD(v16) = a2;
  NextSignature = MinCryptQueryHashAlgorithmFromSignature((unsigned int *)&v16, &v18, v11, (_OWORD *)(v12 + 16));
  if ( NextSignature >= 0 )
  {
    v14 = v18;
    if ( v18 && v18 >= a3 )
    {
      *a5 = v18;
      *(_QWORD *)v12 = *((_QWORD *)&v16 + 1);
      *(_DWORD *)(v12 + 8) = v16;
      if ( v10 )
        *v10 = v17;
    }
    else
    {
      v15 = a5;
      NextSignature = MinCryptGetNextSignature(v12, a3, a4, (_DWORD)a5, (__int64)v10);
      if ( NextSignature < 0 && v14 && v14 >= a4 )
      {
        *v15 = v14;
        *(_QWORD *)v12 = *((_QWORD *)&v16 + 1);
        *(_DWORD *)(v12 + 8) = v16;
        if ( v10 )
          *v10 = v17;
        return 0;
      }
    }
  }
  else
  {
    return (unsigned int)-1073740760;
  }
  return (unsigned int)NextSignature;
}

```

## disassembly

```asm
0x180014d74  mov     rax, rsp
0x180014d77  mov     [rax+8], rbx
0x180014d7b  push    rsi
0x180014d7c  push    rdi
0x180014d7d  push    r12
0x180014d7f  push    r14
0x180014d81  push    r15
0x180014d83  sub     rsp, 50h
0x180014d87  mov     r15d, r9d
0x180014d8a  mov     r14d, r8d
0x180014d8d  mov     dword ptr [rax+20h], 0
0x180014d94  mov     dword ptr [rax+18h], 0
0x180014d9b  xorps   xmm0, xmm0
0x180014d9e  movups  xmmword ptr [rax-40h], xmm0
0x180014da2  cmp     r8d, r9d
0x180014da5  jnb     short loc_180014DC2
0x180014da7  mov     eax, 0C000000Dh
0x180014dac  mov     rbx, [rsp+78h+arg_0]
0x180014db4  add     rsp, 50h
0x180014db8  pop     r15
0x180014dba  pop     r14
0x180014dbc  pop     r12
0x180014dbe  pop     rdi
0x180014dbf  pop     rsi
0x180014dc0  retn
0x180014dc2  mov     rdi, [rsp+78h+arg_30]
0x180014dca  mov     rax, rdi
0x180014dcd  neg     rax
0x180014dd0  sbb     r8, r8
0x180014dd3  lea     rax, [rsp+78h+arg_10]
0x180014ddb  and     r8, rax
0x180014dde  xor     eax, eax
0x180014de0  mov     rsi, [rsp+78h+arg_28]
0x180014de8  movups  xmmword ptr [rsi], xmm0
0x180014deb  movups  xmmword ptr [rsi+10h], xmm0
0x180014def  mov     [rsi+20h], rax
0x180014df3  mov     [rsp+78h+var_38], rcx
0x180014df8  mov     [rsp+78h+var_40], edx
0x180014dfc  lea     r9, [rsi+10h]
0x180014e00  lea     rdx, [rsp+78h+arg_18]
0x180014e08  lea     rcx, [rsp+78h+var_40]
0x180014e0d  call    MinCryptQueryHashAlgorithmFromSignature
0x180014e12  mov     ecx, eax
0x180014e14  mov     [rsp+78h+var_48], eax
0x180014e18  test    eax, eax
0x180014e1a  jns     short loc_180014E26
0x180014e1c  mov     ecx, 0C0000428h
0x180014e21  jmp     loc_180014EB3
0x180014e26  mov     ebx, [rsp+78h+arg_18]
0x180014e2d  test    ebx, ebx
0x180014e2f  jz      short loc_180014E5F
0x180014e31  cmp     ebx, r14d
0x180014e34  jb      short loc_180014E5F
0x180014e36  mov     rax, [rsp+78h+arg_20]
0x180014e3e  mov     [rax], ebx
0x180014e40  mov     rax, [rsp+78h+var_38]
0x180014e45  mov     [rsi], rax
0x180014e48  mov     eax, [rsp+78h+var_40]
0x180014e4c  mov     [rsi+8], eax
0x180014e4f  test    rdi, rdi
0x180014e52  jz      short loc_180014EB7
0x180014e54  mov     eax, [rsp+78h+arg_10]
0x180014e5b  mov     [rdi], eax
0x180014e5d  jmp     short loc_180014EB7
0x180014e5f  mov     [rsp+78h+var_58], rdi
0x180014e64  mov     r12, [rsp+78h+arg_20]
0x180014e6c  mov     r9, r12
0x180014e6f  mov     r8d, r15d
0x180014e72  mov     edx, r14d
0x180014e75  mov     rcx, rsi
0x180014e78  call    MinCryptGetNextSignature
0x180014e7d  mov     ecx, eax
0x180014e7f  mov     [rsp+78h+var_48], eax
0x180014e83  test    eax, eax
0x180014e85  jns     short loc_180014EB7
0x180014e87  test    ebx, ebx
0x180014e89  jz      short loc_180014EB7
0x180014e8b  cmp     ebx, r15d
0x180014e8e  jb      short loc_180014EB7
0x180014e90  mov     [r12], ebx
0x180014e94  mov     rax, [rsp+78h+var_38]
0x180014e99  mov     [rsi], rax
0x180014e9c  mov     eax, [rsp+78h+var_40]
0x180014ea0  mov     [rsi+8], eax
0x180014ea3  test    rdi, rdi
0x180014ea6  jz      short loc_180014EB1
0x180014ea8  mov     eax, [rsp+78h+arg_10]
0x180014eaf  mov     [rdi], eax
0x180014eb1  xor     ecx, ecx
0x180014eb3  mov     [rsp+78h+var_48], ecx
0x180014eb7  mov     eax, ecx
0x180014eb9  jmp     loc_180014DAC
0x180033a2c  push    rbp
0x180033a2e  sub     rsp, 30h
0x180033a32  mov     rbp, rdx
0x180033a35  movzx   eax, cl
0x180033a38  mov     ecx, [rbp+30h]
0x180033a3b  mov     edx, 0C00000E8h
0x180033a40  test    eax, eax
0x180033a42  cmovnz  ecx, edx
0x180033a45  mov     [rbp+30h], ecx
0x180033a48  add     rsp, 30h
0x180033a4c  pop     rbp
0x180033a4d  retn
```
