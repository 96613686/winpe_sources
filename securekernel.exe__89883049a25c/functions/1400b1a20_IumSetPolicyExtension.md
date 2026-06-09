# IumSetPolicyExtension

- ea: `0x1400b1a20`
- end: `0x1400b1bfd`
- name: `IumSetPolicyExtension`
- size: `477`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x14002985c`
- `0x14002ba08`
- `0x14002c64c`
- `0x140037e68`
- `0x1400634b0`
- `0x1400b1a20`
- `0x1400b23c0`
- `0x1400b25c4`

## string_xrefs

- `0x1400b1b2c`: `IumSetPolicyExtension`

## pseudocode

```c
__int64 __fastcall IumSetPolicyExtension(__int64 a1)
{
  _QWORD *StackBase; // rbx
  _QWORD *v2; // rax
  __int64 v4; // r12
  int v5; // r13d
  char v6; // r15
  int ImagePolicy; // eax
  __int64 v8; // rsi
  int SvnAndOverriddenCapabilities; // edi
  int Policy; // eax
  char v11; // r14
  const char *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+38h] [rbp-8h] BYREF
  char v16; // [rsp+88h] [rbp+48h] BYREF
  int v17; // [rsp+90h] [rbp+50h] BYREF
  __int64 v18; // [rsp+98h] [rbp+58h] BYREF

  StackBase = KeGetPcr()->NtTib.StackBase;
  v14 = 0;
  v17 = 0;
  v18 = 0;
  v15 = 1;
  if ( StackBase )
    StackBase = (_QWORD *)StackBase[10];
  v2 = KeGetPcr()->NtTib.StackBase;
  v16 = 0;
  if ( v2 )
  {
    v2 = (_QWORD *)v2[10];
    if ( v2 == (_QWORD *)1 )
      return 3221225659LL;
  }
  if ( (*(_DWORD *)v2 & 0x1600) != 0 )
    return 3221225659LL;
  v4 = StackBase[54];
  v5 = *((_DWORD *)StackBase + 104);
  v6 = 0;
  ImagePolicy = SkmmGetImagePolicy(StackBase, a1, &v18);
  v8 = v18;
  SvnAndOverriddenCapabilities = ImagePolicy;
  if ( ImagePolicy >= 0 )
  {
    SkpspLockProcessExclusive(StackBase);
    if ( StackBase[62] )
    {
      SvnAndOverriddenCapabilities = 255;
LABEL_17:
      SkpspUnlockProcessExclusive(StackBase);
      goto LABEL_18;
    }
    v6 = 1;
    Policy = SkpspFindPolicy((_DWORD)StackBase, 13, 1, (unsigned int)&v16, (__int64)&v15);
    SvnAndOverriddenCapabilities = Policy;
    if ( Policy >= 0 )
    {
      v11 = v16;
      if ( v16 )
        StackBase[54] = *(_QWORD *)(*(_QWORD *)v8 + 8LL);
    }
    else
    {
      if ( Policy != -1073741275 )
      {
        v12 = "True";
        if ( !v16 )
          v12 = "False";
        DbgPrint(
          "%hs: SkpspFindPolicy returned 0x%x and TrustletIdOverridable is %s.\n",
          "IumSetPolicyExtension",
          Policy,
          v12);
        goto LABEL_16;
      }
      v11 = 0;
    }
    SvnAndOverriddenCapabilities = SkpspGetSvnAndOverriddenCapabilities(v8, StackBase[50], &v17, &v14);
    if ( SvnAndOverriddenCapabilities >= 0 )
    {
      v13 = v14;
      if ( (~StackBase[51] & v14) == 0 )
      {
        if ( v11 )
          *((_DWORD *)StackBase + 104) = v17;
        StackBase[50] |= v13;
        StackBase[62] = v8;
        v8 = 0;
        SvnAndOverriddenCapabilities = 0;
        goto LABEL_17;
      }
      SvnAndOverriddenCapabilities = -1073741790;
    }
  }
LABEL_16:
  StackBase[54] = v4;
  *((_DWORD *)StackBase + 104) = v5;
  if ( v6 )
    goto LABEL_17;
LABEL_18:
  if ( v8 )
    SkFreePool(1, v8);
  return (unsigned int)SvnAndOverriddenCapabilities;
}

```

## disassembly

```asm
0x1400b1a20  mov     [rsp-38h+arg_0], rbx
0x1400b1a25  push    rbp
0x1400b1a26  push    rsi
0x1400b1a27  push    rdi
0x1400b1a28  push    r12
0x1400b1a2a  push    r13
0x1400b1a2c  push    r14
0x1400b1a2e  push    r15
0x1400b1a30  mov     rbp, rsp
0x1400b1a33  sub     rsp, 40h
0x1400b1a37  mov     rbx, gs:8
0x1400b1a40  mov     r14d, 1
0x1400b1a46  mov     [rbp+var_10], 0
0x1400b1a4e  mov     [rbp+arg_10], 0
0x1400b1a55  mov     [rbp+arg_18], 0
0x1400b1a5d  mov     [rbp+var_8], r14
0x1400b1a61  test    rbx, rbx
0x1400b1a64  jz      short loc_1400B1A6A
0x1400b1a66  mov     rbx, [rbx+50h]
0x1400b1a6a  mov     rax, gs:8
0x1400b1a73  mov     [rbp+arg_8], 0
0x1400b1a77  test    rax, rax
0x1400b1a7a  jz      short loc_1400B1A85
0x1400b1a7c  mov     rax, [rax+50h]
0x1400b1a80  cmp     rax, r14
0x1400b1a83  jz      short loc_1400B1A8D
0x1400b1a85  test    dword ptr [rax], 1600h
0x1400b1a8b  jz      short loc_1400B1A97
0x1400b1a8d  mov     eax, 0C00000BBh
0x1400b1a92  jmp     loc_1400B1B6E
0x1400b1a97  mov     r12, [rbx+1B0h]
0x1400b1a9e  lea     r8, [rbp+arg_18]
0x1400b1aa2  mov     r13d, [rbx+1A0h]
0x1400b1aa9  mov     rdx, rcx
0x1400b1aac  mov     rcx, rbx
0x1400b1aaf  xor     r15b, r15b
0x1400b1ab2  call    SkmmGetImagePolicy
0x1400b1ab7  mov     rsi, [rbp+arg_18]
0x1400b1abb  mov     edi, eax
0x1400b1abd  test    eax, eax
0x1400b1abf  js      short loc_1400B1B3F
0x1400b1ac1  mov     rcx, rbx
0x1400b1ac4  call    SkpspLockProcessExclusive
0x1400b1ac9  cmp     qword ptr [rbx+1F0h], 0
0x1400b1ad1  jz      short loc_1400B1ADA
0x1400b1ad3  mov     edi, 0FFh
0x1400b1ad8  jmp     short loc_1400B1B52
0x1400b1ada  lea     rax, [rbp+var_8]
0x1400b1ade  mov     r8d, r14d
0x1400b1ae1  lea     r9, [rbp+arg_8]
0x1400b1ae5  mov     [rsp+40h+var_20], rax
0x1400b1aea  mov     edx, 0Dh
0x1400b1aef  mov     rcx, rbx
0x1400b1af2  mov     r15b, r14b
0x1400b1af5  call    SkpspFindPolicy
0x1400b1afa  mov     edi, eax
0x1400b1afc  test    eax, eax
0x1400b1afe  jns     loc_1400B1B87
0x1400b1b04  cmp     eax, 0C0000225h
0x1400b1b09  jnz     short loc_1400B1B13
0x1400b1b0b  xor     r14b, r14b
0x1400b1b0e  jmp     loc_1400B1B9E
0x1400b1b13  cmp     [rbp+arg_8], 0
0x1400b1b17  lea     rax, aFalse_0; "False"
0x1400b1b1e  lea     r9, aTrue_0; "True"
0x1400b1b25  mov     r8d, edi
0x1400b1b28  cmovz   r9, rax
0x1400b1b2c  lea     rdx, aIumsetpolicyex; "IumSetPolicyExtension"
0x1400b1b33  lea     rcx, aHsSkpspfindpol; "%hs: SkpspFindPolicy returned 0x%x and "...
0x1400b1b3a  call    DbgPrint
0x1400b1b3f  mov     [rbx+1B0h], r12
0x1400b1b46  mov     [rbx+1A0h], r13d
0x1400b1b4d  test    r15b, r15b
0x1400b1b50  jz      short loc_1400B1B5A
0x1400b1b52  mov     rcx, rbx
0x1400b1b55  call    SkpspUnlockProcessExclusive
0x1400b1b5a  test    rsi, rsi
0x1400b1b5d  jz      short loc_1400B1B6C
0x1400b1b5f  mov     rdx, rsi
0x1400b1b62  mov     ecx, 1
0x1400b1b67  call    SkFreePool
0x1400b1b6c  mov     eax, edi
0x1400b1b6e  mov     rbx, [rsp+40h+arg_0]
0x1400b1b76  add     rsp, 40h
0x1400b1b7a  pop     r15
0x1400b1b7c  pop     r14
0x1400b1b7e  pop     r13
0x1400b1b80  pop     r12
0x1400b1b82  pop     rdi
0x1400b1b83  pop     rsi
0x1400b1b84  pop     rbp
0x1400b1b85  retn
0x1400b1b87  mov     r14b, [rbp+arg_8]
0x1400b1b8b  test    r14b, r14b
0x1400b1b8e  jz      short loc_1400B1B9E
0x1400b1b90  mov     rax, [rsi]
0x1400b1b93  mov     rcx, [rax+8]
0x1400b1b97  mov     [rbx+1B0h], rcx
0x1400b1b9e  mov     rdx, [rbx+190h]
0x1400b1ba5  lea     r9, [rbp+var_10]
0x1400b1ba9  lea     r8, [rbp+arg_10]
0x1400b1bad  mov     rcx, rsi
0x1400b1bb0  call    SkpspGetSvnAndOverriddenCapabilities
0x1400b1bb5  mov     edi, eax
0x1400b1bb7  test    eax, eax
0x1400b1bb9  js      short loc_1400B1B3F
0x1400b1bbb  mov     rax, [rbx+198h]
0x1400b1bc2  mov     rcx, [rbp+var_10]
0x1400b1bc6  not     rax
0x1400b1bc9  test    rcx, rax
0x1400b1bcc  jz      short loc_1400B1BD8
0x1400b1bce  mov     edi, 0C0000022h
0x1400b1bd3  jmp     loc_1400B1B3F
0x1400b1bd8  test    r14b, r14b
0x1400b1bdb  jz      short loc_1400B1BE6
0x1400b1bdd  mov     eax, [rbp+arg_10]
0x1400b1be0  mov     [rbx+1A0h], eax
0x1400b1be6  or      [rbx+190h], rcx
0x1400b1bed  mov     [rbx+1F0h], rsi
0x1400b1bf4  xor     esi, esi
0x1400b1bf6  xor     edi, edi
0x1400b1bf8  jmp     loc_1400B1B52
```
