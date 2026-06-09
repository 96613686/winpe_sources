# UdfInsertPrefix

- ea: `0x140050a8c`
- end: `0x140050cd4`
- name: `UdfInsertPrefix`
- size: `584`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140033548`
- `0x140034450`
- `0x140050224`

## callees

- `0x14000c5c8`
- `0x1400147f8`
- `0x14001c080`
- `0x14002ead0`
- `0x140050a8c`
- `0x140057f9c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140050b35`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140050b35`
- `ntoskrnl!ExRaiseStatus` at `0x140050af0`
- `ntoskrnl!ExRaiseStatus` at `0x140050af0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140050b4d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140050b4d`

## pseudocode

```c
__int64 __fastcall UdfInsertPrefix(__int64 a1, __int64 a2, _WORD *a3, _WORD *a4, __int64 a5, __int64 a6, __int64 a7)
{
  int v7; // r12d
  _QWORD *i; // r10
  unsigned __int16 v12; // r14
  SIZE_T v13; // rdx
  int v14; // r13d
  _QWORD *PoolWithTag; // rax
  __int64 v16; // rbx
  int v17; // ecx
  __int64 inserted; // rdi
  __int64 v19; // r9
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  _QWORD *v25; // [rsp+88h] [rbp+10h] BYREF

  v7 = (int)a4;
  if ( *(_WORD *)a2 == 2355 )
  {
    for ( i = *(_QWORD **)(a2 + 160); i != (_QWORD *)(a2 + 160); i = (_QWORD *)*i )
    {
      v25 = i - 4;
      if ( *(i - 1) != a6 )
      {
        *(_DWORD *)(a1 + 24) = -1073741774;
        ExRaiseStatus(-1073741774);
      }
    }
  }
  v12 = 0;
  if ( a3 )
    v12 = *a4 + *a3 + 24;
  v13 = v12 + 240LL;
  if ( v13 <= 0x158 )
  {
    v14 = 0;
    PoolWithTag = ExAllocateFromPagedLookasideList(&UdfLcbLookasideList);
  }
  else
  {
    v14 = 1;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)17, v13, 0x6C666455u);
  }
  v16 = (__int64)PoolWithTag;
  v25 = PoolWithTag;
  memset(PoolWithTag, 0, 0xF0u);
  *(_WORD *)v16 = 2361;
  *(_WORD *)(v16 + 2) = v12 + 240;
  *(_QWORD *)(v16 + 224) = v16 + 240;
  *(_WORD *)(v16 + 232) = v12;
  *(_DWORD *)(v16 + 72) = 0;
  *(_QWORD *)(v16 + 56) = a7;
  *(_DWORD *)(v16 + 68) = v14;
  if ( a3 )
  {
    UdfUpdateNamesInLcb(v17, v16, (_DWORD)a3, v7, a5);
    inserted = UdfInsertNames(a1, a2, a6, v16);
  }
  else
  {
    inserted = v16;
  }
  if ( inserted == v16 )
  {
    v19 = a6;
    *(_QWORD *)(v16 + 24) = a6;
    *(_QWORD *)(v16 + 48) = a2;
    v20 = (_QWORD *)(v19 + 536);
    v21 = *(_QWORD *)(v19 + 536);
    if ( *(_QWORD *)(v21 + 8) != v19 + 536
      || (*(_QWORD *)(v16 + 8) = v21,
          *(_QWORD *)(v16 + 16) = v20,
          *(_QWORD *)(v21 + 8) = v16 + 8,
          *v20 = v16 + 8,
          v22 = (_QWORD *)(a2 + 160),
          v23 = *(_QWORD *)(a2 + 160),
          *(_QWORD *)(v23 + 8) != a2 + 160) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)(v16 + 32) = v23;
    *(_QWORD *)(v16 + 40) = v22;
    *(_QWORD *)(v23 + 8) = v16 + 32;
    *v22 = v16 + 32;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000) != 0 )
    {
      WPP_SF_qZqq(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 10, v16 + 128, v19, v16 + 128, v16, a2);
    }
    *(_DWORD *)(v16 + 64) = 0;
  }
  else
  {
    UdfFreeLcb(&v25);
    return inserted;
  }
  return v16;
}

```

## disassembly

```asm
0x140050a8c  mov     [rsp+arg_0], rbx
0x140050a91  mov     [rsp+arg_10], rsi
0x140050a96  push    rdi
0x140050a97  push    r12
0x140050a99  push    r13
0x140050a9b  push    r14
0x140050a9d  push    r15
0x140050a9f  sub     rsp, 50h
0x140050aa3  mov     r12, r9
0x140050aa6  mov     rdi, r8
0x140050aa9  mov     rsi, rdx
0x140050aac  mov     r15, rcx
0x140050aaf  mov     eax, 933h
0x140050ab4  cmp     [rdx], ax
0x140050ab7  jnz     short loc_140050AFD
0x140050ab9  lea     r8, [rdx+0A0h]
0x140050ac0  mov     r10, [r8]
0x140050ac3  cmp     r10, r8
0x140050ac6  jz      short loc_140050AFD
0x140050ac8  lea     rdx, [r10-20h]
0x140050acc  mov     [rsp+78h+arg_8], rdx
0x140050ad4  mov     rax, [rsp+78h+arg_28]
0x140050adc  cmp     [rdx+18h], rax
0x140050ae0  jnz     short loc_140050AE7
0x140050ae2  mov     r10, [r10]
0x140050ae5  jmp     short loc_140050AC3
0x140050ae7  mov     ecx, 0C0000032h; Status
0x140050aec  mov     [r15+18h], ecx
0x140050af0  call    cs:__imp_ExRaiseStatus
0x140050afd  xor     r14d, r14d
0x140050b00  test    rdi, rdi
0x140050b03  jz      short loc_140050B12
0x140050b05  movzx   r14d, word ptr [rdi]
0x140050b09  add     r14w, 18h
0x140050b0e  add     r14w, [r9]
0x140050b12  movzx   edx, r14w
0x140050b16  add     rdx, 0F0h; NumberOfBytes
0x140050b1d  cmp     rdx, 158h
0x140050b24  jbe     short loc_140050B43
0x140050b26  mov     ecx, 11h; PoolType
0x140050b2b  lea     r13d, [rcx-10h]
0x140050b2f  mov     r8d, 6C666455h; Tag
0x140050b35  call    cs:__imp_ExAllocatePoolWithTag
0x140050b3c  nop     dword ptr [rax+rax+00h]
0x140050b41  jmp     short loc_140050B59
0x140050b43  xor     r13d, r13d
0x140050b46  lea     rcx, UdfLcbLookasideList; Lookaside
0x140050b4d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140050b54  nop     dword ptr [rax+rax+00h]
0x140050b59  mov     rbx, rax
0x140050b5c  mov     [rsp+78h+arg_8], rax
0x140050b64  xor     edx, edx; Val
0x140050b66  mov     r8d, 0F0h; Size
0x140050b6c  mov     rcx, rax; void *
0x140050b6f  call    memset
0x140050b74  mov     word ptr [rbx], 939h
0x140050b79  mov     eax, 0F0h
0x140050b7e  add     eax, r14d
0x140050b81  mov     [rbx+2], ax
0x140050b85  lea     rax, [rbx+0F0h]
0x140050b8c  mov     [rbx+0E0h], rax
0x140050b93  mov     [rbx+0E8h], r14w
0x140050b9b  mov     dword ptr [rbx+48h], 0
0x140050ba2  mov     rax, [rsp+78h+arg_30]
0x140050baa  mov     [rbx+38h], rax
0x140050bae  mov     [rbx+44h], r13d
0x140050bb2  test    rdi, rdi
0x140050bb5  jz      short loc_140050BF3
0x140050bb7  mov     rax, [rsp+78h+arg_20]
0x140050bbf  mov     [rsp+78h+var_58], rax
0x140050bc4  mov     r9, r12
0x140050bc7  mov     r8, rdi
0x140050bca  mov     rdx, rbx
0x140050bcd  call    UdfUpdateNamesInLcb
0x140050bd2  nop
0x140050bd3  mov     r9, rbx
0x140050bd6  mov     r8, [rsp+78h+arg_28]
0x140050bde  mov     rdx, rsi
0x140050be1  mov     rcx, r15
0x140050be4  call    UdfInsertNames
0x140050be9  mov     rdi, rax
0x140050bec  mov     [rsp+78h+var_38], rax
0x140050bf1  jmp     short loc_140050BF6
0x140050bf3  mov     rdi, rbx
0x140050bf6  cmp     rdi, rbx
0x140050bf9  jz      short loc_140050C10
0x140050bfb  lea     rcx, [rsp+78h+arg_8]
0x140050c03  call    UdfFreeLcb
0x140050c08  mov     rbx, rdi
0x140050c0b  jmp     loc_140050CAF
0x140050c10  mov     r9, [rsp+78h+arg_28]
0x140050c18  mov     [rbx+18h], r9
0x140050c1c  mov     [rbx+30h], rsi
0x140050c20  lea     rcx, [r9+218h]
0x140050c27  mov     rdx, [rcx]
0x140050c2a  cmp     [rdx+8], rcx
0x140050c2e  jnz     loc_140050CCD
0x140050c34  lea     rax, [rbx+8]
0x140050c38  mov     [rax], rdx
0x140050c3b  mov     [rax+8], rcx
0x140050c3f  mov     [rdx+8], rax
0x140050c43  mov     [rcx], rax
0x140050c46  lea     rcx, [rsi+0A0h]
0x140050c4d  mov     rdx, [rcx]
0x140050c50  cmp     [rdx+8], rcx
0x140050c54  jnz     short loc_140050CCD
0x140050c56  lea     rax, [rbx+20h]
0x140050c5a  mov     [rax], rdx
0x140050c5d  mov     [rax+8], rcx
0x140050c61  mov     [rdx+8], rax
0x140050c65  mov     [rcx], rax
0x140050c68  lea     rax, WPP_GLOBAL_Control
0x140050c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140050c76  cmp     rcx, rax
0x140050c79  jz      short loc_140050CA8
0x140050c7b  test    dword ptr [rcx+2Ch], 8000h
0x140050c82  jz      short loc_140050CA8
0x140050c84  lea     r8, [rbx+80h]
0x140050c8b  mov     edx, 0Ah
0x140050c90  mov     [rsp+78h+var_48], rsi
0x140050c95  mov     [rsp+78h+var_50], rbx
0x140050c9a  mov     [rsp+78h+var_58], r8
0x140050c9f  mov     rcx, [rcx+18h]
0x140050ca3  call    WPP_SF_qZqq
0x140050ca8  mov     dword ptr [rbx+40h], 0
0x140050caf  mov     rax, rbx
0x140050cb2  lea     r11, [rsp+78h+var_28]
0x140050cb7  mov     rbx, [r11+30h]
0x140050cbb  mov     rsi, [r11+40h]
0x140050cbf  mov     rsp, r11
0x140050cc2  pop     r15
0x140050cc4  pop     r14
0x140050cc6  pop     r13
0x140050cc8  pop     r12
0x140050cca  pop     rdi
0x140050ccb  retn
0x140050ccd  mov     ecx, 3
0x140050cd2  int     29h; Win8: RtlFailFast(ecx)
0x14005a993  push    rbp
0x14005a995  sub     rsp, 40h
0x14005a999  mov     rbp, rdx
0x14005a99c  movzx   eax, cl
0x14005a99f  test    cl, cl
0x14005a9a1  jz      short loc_14005A9B0
0x14005a9a3  lea     rcx, [rbp+88h]
0x14005a9aa  call    UdfFreeLcb
0x14005a9af  nop
0x14005a9b0  add     rsp, 40h
0x14005a9b4  pop     rbp
0x14005a9b5  retn
```
