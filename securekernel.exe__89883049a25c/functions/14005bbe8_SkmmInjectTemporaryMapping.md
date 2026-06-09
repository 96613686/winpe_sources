# SkmmInjectTemporaryMapping

- ea: `0x14005bbe8`
- end: `0x14005bd0c`
- name: `SkmmInjectTemporaryMapping`
- size: `292`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400aeeec`
- `0x1400af7f8`

## callees

- `0x140001320`
- `0x14001e518`
- `0x14002f3f8`
- `0x140034dec`
- `0x140037fe4`
- `0x14005bbe8`
- `0x1400809dc`

## pseudocode

```c
__int64 __fastcall SkmmInjectTemporaryMapping(unsigned __int64 a1, __int64 a2)
{
  _QWORD *StackBase; // rdi
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // esi
  int v10; // r10d
  __int64 v11; // [rsp+20h] [rbp-18h]
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  StackBase = KeGetPcr()->NtTib.StackBase;
  v12 = 0;
  if ( StackBase )
    StackBase = (_QWORD *)StackBase[10];
  if ( (int)SkmiCreateLockedVad(a1, a2, 0, 0x38u, &v12) < 0 )
    return 3221225626LL;
  v4 = v12;
  v5 = v12;
  *(_QWORD *)(v12 + 48) = *(_QWORD *)(v12 + 48) & 0xFFFD8FFFFFFFFFFFuLL | 0x2100000000000LL;
  if ( (unsigned int)SkmiTryInsertVad(StackBase, v5) )
  {
    v12 = 20482;
    *(_QWORD *)(v4 + 48) |= 0x1000000000000uLL;
    SKMI_SWIZZLE_INVALID_PTE(&v12, v6, v7, v8);
    v9 = SkmiCommitVirtualPageTables(
           (__int64)StackBase,
           ((unsigned __int64)(v10 & 0xFFF) << 32) | *(unsigned int *)(v4 + 24),
           *(unsigned int *)(v4 + 28) | ((unsigned __int64)(v10 & 0xFFF000) << 20),
           v12 & 0xFFFFFFFFFFFFFC1FuLL | 0x20,
           v11,
           0);
    if ( v9 < 0 )
      SkmiDeleteVad((__int64)StackBase, v4);
  }
  else
  {
    v9 = -1073741800;
  }
  SkmiUnlockAndDereferenceVad(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14005bbe8  mov     [rsp+arg_0], rbx
0x14005bbed  mov     [rsp+arg_8], rsi
0x14005bbf2  push    rdi
0x14005bbf3  sub     rsp, 30h
0x14005bbf7  mov     rdi, gs:8
0x14005bc00  mov     [rsp+38h+arg_10], 0
0x14005bc09  test    rdi, rdi
0x14005bc0c  jz      short loc_14005BC12
0x14005bc0e  mov     rdi, [rdi+50h]
0x14005bc12  lea     rax, [rsp+38h+arg_10]
0x14005bc17  mov     r9d, 38h ; '8'
0x14005bc1d  xor     r8d, r8d
0x14005bc20  mov     [rsp+38h+var_18], rax
0x14005bc25  call    SkmiCreateLockedVad
0x14005bc2a  test    eax, eax
0x14005bc2c  jns     short loc_14005BC38
0x14005bc2e  mov     eax, 0C000009Ah
0x14005bc33  jmp     loc_14005BCFB
0x14005bc38  mov     rbx, [rsp+38h+arg_10]
0x14005bc3d  mov     rcx, 0FFFF9FFFFFFFFFFFh
0x14005bc47  mov     rdx, rbx
0x14005bc4a  mov     rax, [rbx+30h]
0x14005bc4e  and     rax, rcx
0x14005bc51  mov     rcx, 2100000000000h
0x14005bc5b  or      rax, rcx
0x14005bc5e  mov     rcx, rdi
0x14005bc61  mov     [rbx+30h], rax
0x14005bc65  call    SkmiTryInsertVad
0x14005bc6a  test    eax, eax
0x14005bc6c  jnz     short loc_14005BC75
0x14005bc6e  mov     esi, 0C0000018h
0x14005bc73  jmp     short loc_14005BCF1
0x14005bc75  mov     rax, 1000000000000h
0x14005bc7f  mov     [rsp+38h+arg_10], 5002h
0x14005bc88  or      [rbx+30h], rax
0x14005bc8c  lea     rcx, [rsp+38h+arg_10]
0x14005bc91  mov     r10d, [rbx+20h]
0x14005bc95  call    SKMI_SWIZZLE_INVALID_PTE
0x14005bc9a  mov     eax, [rbx+1Ch]
0x14005bc9d  mov     r8d, r10d
0x14005bca0  mov     edx, [rbx+18h]
0x14005bca3  and     r8d, 0FFF000h
0x14005bcaa  mov     r9, [rsp+38h+arg_10]
0x14005bcaf  and     r10d, 0FFFh
0x14005bcb6  shl     r8, 14h
0x14005bcba  and     r9, 0FFFFFFFFFFFFFC3Fh
0x14005bcc1  shl     r10, 20h
0x14005bcc5  or      r8, rax
0x14005bcc8  or      r9, 20h
0x14005bccc  mov     [rsp+38h+var_10], 0
0x14005bcd5  or      rdx, r10
0x14005bcd8  mov     rcx, rdi
0x14005bcdb  call    SkmiCommitVirtualPageTables
0x14005bce0  mov     esi, eax
0x14005bce2  test    eax, eax
0x14005bce4  jns     short loc_14005BCF1
0x14005bce6  mov     rdx, rbx
0x14005bce9  mov     rcx, rdi
0x14005bcec  call    SkmiDeleteVad
0x14005bcf1  mov     rcx, rbx
0x14005bcf4  call    SkmiUnlockAndDereferenceVad
0x14005bcf9  mov     eax, esi
0x14005bcfb  mov     rbx, [rsp+38h+arg_0]
0x14005bd00  mov     rsi, [rsp+38h+arg_8]
0x14005bd05  add     rsp, 30h
0x14005bd09  pop     rdi
0x14005bd0a  retn
```
