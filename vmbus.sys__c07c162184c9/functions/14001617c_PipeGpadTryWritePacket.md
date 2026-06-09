# PipeGpadTryWritePacket

- ea: `0x14001617c`
- end: `0x140016253`
- name: `PipeGpadTryWritePacket`
- size: `215`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140002f04`
- `0x1400030fc`
- `0x14001661c`

## callees

- `0x14001617c`
- `0x140016994`
- `0x140017000`
- `0x140017240`

## pseudocode

```c
__int64 __fastcall PipeGpadTryWritePacket(int a1, int *a2, __int64 a3)
{
  int v3; // eax
  int v5; // eax
  int v6; // edx
  unsigned int v7; // edi
  size_t v9; // [rsp+40h] [rbp-40h] BYREF
  void *v10; // [rsp+48h] [rbp-38h] BYREF
  __int128 Src; // [rsp+50h] [rbp-30h] BYREF
  void *v12[2]; // [rsp+60h] [rbp-20h]
  size_t Size; // [rsp+70h] [rbp-10h]

  LODWORD(v9) = 0;
  Size = 0;
  v3 = *a2;
  v10 = 0;
  Src = 0;
  *(_OWORD *)v12 = 0;
  if ( v3 == 2 )
  {
    v5 = a2[8];
    v6 = 3;
    LODWORD(v9) = v5;
  }
  else
  {
    v6 = 0;
    if ( v3 == 3 )
    {
      v6 = 4;
      LODWORD(v9) = 4;
    }
  }
  v7 = PipeTryWriteDeferred(a1, v6, (unsigned int)&v9, 0, a3, (__int64)&v10, (__int64)&Src);
  if ( !v7 )
  {
    memmove(v12[1], &Src, (unsigned int)Size);
    if ( *a2 == 2 )
      memmove(v10, a2 + 9, (unsigned int)v9);
    else
      *(_DWORD *)v10 = a2[9];
  }
  return v7;
}

```

## disassembly

```asm
0x14001617c  push    rbp
0x14001617e  push    rbx
0x14001617f  push    rdi
0x140016180  mov     rbp, rsp
0x140016183  sub     rsp, 80h
0x14001618a  mov     rax, cs:__security_cookie
0x140016191  xor     rax, rsp
0x140016194  mov     [rbp+var_8], rax
0x140016198  xor     eax, eax
0x14001619a  mov     dword ptr [rbp+var_40], 0
0x1400161a1  xorps   xmm0, xmm0
0x1400161a4  mov     [rbp+Size], rax
0x1400161a8  mov     eax, [rdx]
0x1400161aa  mov     rbx, rdx
0x1400161ad  mov     [rbp+var_38], 0
0x1400161b5  movups  [rbp+Src], xmm0
0x1400161b9  movups  xmmword ptr [rbp+var_20], xmm0
0x1400161bd  cmp     eax, 2
0x1400161c0  jnz     short loc_1400161CF
0x1400161c2  mov     eax, [rdx+20h]
0x1400161c5  mov     edx, 3
0x1400161ca  mov     dword ptr [rbp+var_40], eax
0x1400161cd  jmp     short loc_1400161DC
0x1400161cf  xor     edx, edx
0x1400161d1  cmp     eax, 3
0x1400161d4  jnz     short loc_1400161DC
0x1400161d6  lea     edx, [rax+1]
0x1400161d9  mov     dword ptr [rbp+var_40], edx
0x1400161dc  lea     rax, [rbp+Src]
0x1400161e0  xor     r9d, r9d
0x1400161e3  mov     [rsp+80h+var_50], rax
0x1400161e8  lea     rax, [rbp+var_38]
0x1400161ec  mov     [rsp+80h+var_58], rax
0x1400161f1  mov     [rsp+80h+var_60], r8
0x1400161f6  lea     r8, [rbp+var_40]
0x1400161fa  call    PipeTryWriteDeferred
0x1400161ff  mov     edi, eax
0x140016201  test    eax, eax
0x140016203  jnz     short loc_140016239
0x140016205  mov     r8d, dword ptr [rbp+Size]; Size
0x140016209  lea     rdx, [rbp+Src]; Src
0x14001620d  mov     rcx, [rbp+var_20+8]; void *
0x140016211  nop
0x140016212  call    memmove
0x140016217  cmp     dword ptr [rbx], 2
0x14001621a  jnz     short loc_14001622F
0x14001621c  mov     r8d, dword ptr [rbp+var_40]; Size
0x140016220  lea     rdx, [rbx+24h]; Src
0x140016224  mov     rcx, [rbp+var_38]; void *
0x140016228  call    memmove
0x14001622d  jmp     short loc_140016238
0x14001622f  mov     rax, [rbp+var_38]
0x140016233  mov     ecx, [rbx+24h]
0x140016236  mov     [rax], ecx
0x140016238  nop
0x140016239  mov     eax, edi
0x14001623b  mov     rcx, [rbp+var_8]
0x14001623f  xor     rcx, rsp; StackCookie
0x140016242  call    __security_check_cookie
0x140016247  add     rsp, 80h
0x14001624e  pop     rdi
0x14001624f  pop     rbx
0x140016250  pop     rbp
0x140016251  retn
```
