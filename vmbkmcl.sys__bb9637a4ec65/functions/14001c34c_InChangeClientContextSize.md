# InChangeClientContextSize

- ea: `0x14001c34c`
- end: `0x14001c5ba`
- name: `InChangeClientContextSize`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400101a0`

## callees

- `0x140005ae0`
- `0x140008878`
- `0x140008b48`
- `0x140011e90`
- `0x140011f80`
- `0x14001c34c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001c44a`
- `ntoskrnl!ExAllocatePool2` at `0x14001c44a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c52e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c52e`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14001c3b7`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14001c3b7`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001c3d5`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001c3d5`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001c586`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001c586`

## pseudocode

```c
__int64 __fastcall InChangeClientContextSize(__int64 *a1, int a2)
{
  bool v2; // zf
  __int64 v6; // rcx
  __int64 v7; // rdi
  int v8; // r12d
  unsigned int v9; // r14d
  __int64 Pool2; // rsi
  __int64 *v11; // r14
  char v12; // al
  unsigned int v13; // r8d
  __int64 **v14; // rax
  __int64 v15; // rax
  int v16; // edi
  unsigned int v17; // esi
  int v18; // [rsp+20h] [rbp-68h]
  struct _GROUP_AFFINITY Affinity; // [rsp+28h] [rbp-60h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+38h] [rbp-50h] BYREF

  v2 = *((_DWORD *)a1 + 274) == 0;
  Affinity = 0;
  if ( !v2 )
    return 3221225860LL;
  if ( a2 == *((_DWORD *)a1 + 348) )
    return 0;
  v6 = *a1;
  PreviousAffinity = 0;
  KeQueryNodeActiveAffinity(*(_WORD *)(v6 + 3272), &Affinity, 0);
  if ( Affinity.Mask )
    KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
  v7 = a1[160];
  v8 = *((_DWORD *)a1 + 362);
  v18 = *((_DWORD *)a1 + 348);
  while ( (__int64 *)v7 != a1 + 160 )
  {
    if ( !*(_DWORD *)(v7 + 16) )
    {
      v9 = a2 + *(_DWORD *)(v7 - 12) - *(_DWORD *)(v7 + 60);
      if ( *(_DWORD *)(v7 - 16) < v9 )
      {
        Pool2 = ExAllocatePool2(64, v9, 1852402518);
        if ( !Pool2 )
        {
          v16 = -1073741670;
          goto LABEL_26;
        }
        *(_DWORD *)(Pool2 + 8) = v9;
        *(_DWORD *)(Pool2 + 12) = v9;
        *(_BYTE *)(Pool2 + 16) = 64;
        v11 = (__int64 *)(Pool2 + 24);
        *(_QWORD *)(Pool2 + 32) = Pool2 + 24;
        *(_QWORD *)(Pool2 + 24) = Pool2 + 24;
        *(_DWORD *)(Pool2 + 40) = 0;
        *(_QWORD *)(Pool2 + 48) = 0;
        *(_QWORD *)(Pool2 + 72) = 0;
        *(_BYTE *)(Pool2 + 17) = 0;
        v12 = *(_BYTE *)(v7 - 8);
        *(_DWORD *)(v7 + 60) = a2;
        *(_QWORD *)Pool2 = a1;
        *(_BYTE *)(Pool2 + 16) = v12 & 0xBE | 0x40;
        *(_DWORD *)(Pool2 + 56) = *(_DWORD *)(v7 + 32);
        *(_DWORD *)(Pool2 + 60) = *(_DWORD *)(v7 + 36);
        *(_DWORD *)(Pool2 + 64) = *(_DWORD *)(v7 + 40);
        memmove((void *)(Pool2 + 160), (const void *)(v7 + 136), *(unsigned int *)(v7 + 32));
        v13 = *(_DWORD *)(v7 + 52);
        if ( v13 && !InpParseGpaDirectPacket((_DWORD *)Pool2, 8 * *(unsigned __int16 *)(Pool2 + 162), v13) )
        {
          ExFreePoolWithTag((PVOID)Pool2, *((_DWORD *)a1 + 411));
          v16 = -1073741566;
          goto LABEL_26;
        }
        v14 = *(__int64 ***)(v7 + 8);
        if ( *v14 != (__int64 *)v7
          || (*v11 = v7,
              *(_QWORD *)(Pool2 + 32) = v14,
              *v14 = v11,
              *(_QWORD *)(v7 + 8) = v11,
              v15 = *(_QWORD *)v7,
              *(_QWORD *)(*(_QWORD *)v7 + 8LL) != v7)
          || *v11 != v7 )
        {
          __fastfail(3u);
        }
        *v11 = v15;
        *(_QWORD *)(v15 + 8) = v11;
        InpFreePacket(a1, v7 - 24);
        v7 = Pool2 + 24;
      }
      else
      {
        a1[173] += (unsigned int)(*(_DWORD *)(v7 + 60) - a2);
        *(_DWORD *)(v7 - 12) = v9;
        *(_DWORD *)(v7 + 60) = a2;
      }
    }
    v7 = *(_QWORD *)v7;
  }
  v17 = v8 - v18 + a2;
  if ( !a1[182] || (v16 = InpReacquirePacketAllocationResources(a1, v17), v16 >= 0) )
  {
    *((_DWORD *)a1 + 362) = v17;
    v16 = 0;
    *((_DWORD *)a1 + 348) = a2;
  }
LABEL_26:
  KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14001c34c  mov     [rsp+arg_10], rbx
0x14001c351  push    rbp
0x14001c352  push    rsi
0x14001c353  push    rdi
0x14001c354  push    r12
0x14001c356  push    r13
0x14001c358  push    r14
0x14001c35a  push    r15
0x14001c35c  sub     rsp, 50h
0x14001c360  mov     rax, cs:__security_cookie
0x14001c367  xor     rax, rsp
0x14001c36a  mov     [rsp+88h+var_40], rax
0x14001c36f  cmp     dword ptr [rcx+448h], 0
0x14001c376  xorps   xmm0, xmm0
0x14001c379  movups  xmmword ptr [rsp+88h+Affinity.Mask], xmm0
0x14001c37e  mov     r15d, edx
0x14001c381  mov     rbx, rcx
0x14001c384  jz      short loc_14001C390
0x14001c386  mov     eax, 0C0000184h
0x14001c38b  jmp     loc_14001C594
0x14001c390  cmp     r15d, [rcx+570h]
0x14001c397  jnz     short loc_14001C3A0
0x14001c399  xor     eax, eax
0x14001c39b  jmp     loc_14001C594
0x14001c3a0  mov     rcx, [rcx]
0x14001c3a3  lea     rdx, [rsp+88h+Affinity]; Affinity
0x14001c3a8  movups  xmmword ptr [rsp+88h+PreviousAffinity.Mask], xmm0
0x14001c3ad  xor     r8d, r8d; Count
0x14001c3b0  movzx   ecx, word ptr [rcx+0CC8h]; NodeNumber
0x14001c3b7  call    cs:__imp_KeQueryNodeActiveAffinity
0x14001c3be  nop     dword ptr [rax+rax+00h]
0x14001c3c3  cmp     [rsp+88h+Affinity.Mask], 0
0x14001c3c9  jz      short loc_14001C3E1
0x14001c3cb  lea     rdx, [rsp+88h+PreviousAffinity]; PreviousAffinity
0x14001c3d0  lea     rcx, [rsp+88h+Affinity]; Affinity
0x14001c3d5  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14001c3dc  nop     dword ptr [rax+rax+00h]
0x14001c3e1  mov     eax, [rbx+570h]
0x14001c3e7  lea     r13, [rbx+500h]
0x14001c3ee  mov     rdi, [r13+0]
0x14001c3f2  mov     r12d, [rbx+5A8h]
0x14001c3f9  mov     [rsp+88h+var_68], eax
0x14001c3fd  cmp     rdi, r13
0x14001c400  jz      loc_14001C54F
0x14001c406  cmp     dword ptr [rdi+10h], 0
0x14001c40a  jnz     loc_14001C51D
0x14001c410  mov     ecx, [rdi-0Ch]
0x14001c413  mov     r14d, ecx
0x14001c416  sub     r14d, [rdi+3Ch]
0x14001c41a  add     r14d, r15d
0x14001c41d  cmp     [rdi-10h], r14d
0x14001c421  jb      short loc_14001C43C
0x14001c423  sub     ecx, r14d
0x14001c426  mov     eax, ecx
0x14001c428  add     [rbx+568h], rax
0x14001c42f  mov     [rdi-0Ch], r14d
0x14001c433  mov     [rdi+3Ch], r15d
0x14001c437  jmp     loc_14001C51D
0x14001c43c  mov     edx, r14d
0x14001c43f  mov     ecx, 40h ; '@'
0x14001c444  mov     r8d, 6E696B56h
0x14001c44a  call    cs:__imp_ExAllocatePool2
0x14001c451  nop     dword ptr [rax+rax+00h]
0x14001c456  mov     rsi, rax
0x14001c459  xor     eax, eax
0x14001c45b  test    rsi, rsi
0x14001c45e  jz      loc_14001C548
0x14001c464  mov     [rsi+8], r14d
0x14001c468  lea     rdx, [rdi+88h]; Src
0x14001c46f  mov     [rsi+0Ch], r14d
0x14001c473  lea     rcx, [rsi+0A0h]; void *
0x14001c47a  mov     byte ptr [rsi+10h], 40h ; '@'
0x14001c47e  lea     r14, [rsi+18h]
0x14001c482  mov     [rsi+20h], r14
0x14001c486  mov     [r14], r14
0x14001c489  mov     [rsi+28h], eax
0x14001c48c  mov     [rsi+30h], rax
0x14001c490  mov     [rsi+48h], rax
0x14001c494  mov     [rsi+11h], al
0x14001c497  mov     al, [rdi-8]
0x14001c49a  mov     [rdi+3Ch], r15d
0x14001c49e  and     al, 0FEh
0x14001c4a0  or      al, 40h
0x14001c4a2  mov     [rsi], rbx
0x14001c4a5  mov     [rsi+10h], al
0x14001c4a8  mov     eax, [rdi+20h]
0x14001c4ab  mov     [rsi+38h], eax
0x14001c4ae  mov     eax, [rdi+24h]
0x14001c4b1  mov     [rsi+3Ch], eax
0x14001c4b4  mov     eax, [rdi+28h]
0x14001c4b7  mov     [rsi+40h], eax
0x14001c4ba  mov     r8d, [rdi+20h]; Size
0x14001c4be  call    memmove
0x14001c4c3  mov     r8d, [rdi+34h]
0x14001c4c7  test    r8d, r8d
0x14001c4ca  jz      short loc_14001C4E2
0x14001c4cc  movzx   edx, word ptr [rsi+0A2h]
0x14001c4d3  mov     rcx, rsi
0x14001c4d6  shl     edx, 3
0x14001c4d9  call    InpParseGpaDirectPacket
0x14001c4de  test    al, al
0x14001c4e0  jz      short loc_14001C525
0x14001c4e2  mov     rax, [rdi+8]
0x14001c4e6  cmp     [rax], rdi
0x14001c4e9  jnz     short loc_14001C541
0x14001c4eb  mov     [r14], rdi
0x14001c4ee  mov     [r14+8], rax
0x14001c4f2  mov     [rax], r14
0x14001c4f5  mov     [rdi+8], r14
0x14001c4f9  mov     rax, [rdi]
0x14001c4fc  cmp     [rax+8], rdi
0x14001c500  jnz     short loc_14001C541
0x14001c502  cmp     [r14], rdi
0x14001c505  jnz     short loc_14001C541
0x14001c507  mov     [r14], rax
0x14001c50a  lea     rdx, [rdi-18h]
0x14001c50e  mov     rcx, rbx
0x14001c511  mov     [rax+8], r14
0x14001c515  call    InpFreePacket
0x14001c51a  mov     rdi, r14
0x14001c51d  mov     rdi, [rdi]
0x14001c520  jmp     loc_14001C3FD
0x14001c525  mov     edx, [rbx+66Ch]; Tag
0x14001c52b  mov     rcx, rsi; P
0x14001c52e  call    cs:__imp_ExFreePoolWithTag
0x14001c535  nop     dword ptr [rax+rax+00h]
0x14001c53a  mov     edi, 0C0000102h
0x14001c53f  jmp     short loc_14001C581
0x14001c541  mov     ecx, 3
0x14001c546  int     29h; Win8: RtlFailFast(ecx)
0x14001c548  mov     edi, 0C000009Ah
0x14001c54d  jmp     short loc_14001C581
0x14001c54f  sub     r12d, [rsp+88h+var_68]
0x14001c554  cmp     qword ptr [rbx+5B0h], 0
0x14001c55c  lea     esi, [r12+r15]
0x14001c560  jz      short loc_14001C572
0x14001c562  mov     edx, esi
0x14001c564  mov     rcx, rbx
0x14001c567  call    InpReacquirePacketAllocationResources
0x14001c56c  mov     edi, eax
0x14001c56e  test    eax, eax
0x14001c570  js      short loc_14001C581
0x14001c572  mov     [rbx+5A8h], esi
0x14001c578  xor     edi, edi
0x14001c57a  mov     [rbx+570h], r15d
0x14001c581  lea     rcx, [rsp+88h+PreviousAffinity]; PreviousAffinity
0x14001c586  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14001c58d  nop     dword ptr [rax+rax+00h]
0x14001c592  mov     eax, edi
0x14001c594  mov     rcx, [rsp+88h+var_40]
0x14001c599  xor     rcx, rsp; StackCookie
0x14001c59c  call    __security_check_cookie
0x14001c5a1  mov     rbx, [rsp+88h+arg_10]
0x14001c5a9  add     rsp, 50h
0x14001c5ad  pop     r15
0x14001c5af  pop     r14
0x14001c5b1  pop     r13
0x14001c5b3  pop     r12
0x14001c5b5  pop     rdi
0x14001c5b6  pop     rsi
0x14001c5b7  pop     rbp
0x14001c5b8  retn
```
