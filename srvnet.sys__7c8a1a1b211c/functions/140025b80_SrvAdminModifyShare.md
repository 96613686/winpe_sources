# SrvAdminModifyShare

- ea: `0x140025b80`
- end: `0x14002605c`
- name: `SrvAdminModifyShare`
- size: `1244`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, __int64, PSECURITY_DESCRIPTOR SecurityDescriptor, int, int, int, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140023c20`

## callees

- `0x140007160`
- `0x140007360`
- `0x1400073d0`
- `0x140007c60`
- `0x14000bc90`
- `0x1400227cc`
- `0x140025b80`
- `0x1400286b0`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025c1e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025c38`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025c1e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025c38`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140025d99`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140025d99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025f2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025f53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025f84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025fae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025fd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026000`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025f2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025f53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025f84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025fae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025fd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026000`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025ea9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002601d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140026032`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025ea9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002601d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140026032`

## pseudocode

```c
__int64 __fastcall SrvAdminModifyShare(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const void **a4,
        unsigned __int16 *a5,
        int a6,
        int a7,
        __int64 a8,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        int a10,
        int a11,
        int a12,
        _OWORD *a13,
        __int16 a14)
{
  unsigned __int16 *v16; // rdi
  unsigned int *v18; // r12
  unsigned int *v19; // r13
  char v20; // r14
  __int64 v21; // rax
  __int64 v22; // rsi
  unsigned int v23; // edi
  unsigned int *v24; // r15
  __int64 v25; // rax
  __int16 v26; // ax
  unsigned int *PoolWithTag; // rax
  _DWORD *v28; // rbx
  __int16 v29; // ax
  unsigned int *v30; // rax
  _OWORD *v31; // r15
  unsigned int v32; // eax
  int v33; // r12d
  int v34; // ebx
  __int64 v35; // rbx
  void *v36; // rbx
  unsigned int *v38; // [rsp+68h] [rbp-69h]
  unsigned int *v39; // [rsp+70h] [rbp-61h] BYREF
  __int128 v40; // [rsp+78h] [rbp-59h]
  __int128 v41; // [rsp+88h] [rbp-49h]
  __int128 v42; // [rsp+98h] [rbp-39h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-29h]
  PERESOURCE Resource; // [rsp+B0h] [rbp-21h]
  _QWORD v45[2]; // [rsp+B8h] [rbp-19h] BYREF
  PERESOURCE v46; // [rsp+C8h] [rbp-9h]
  unsigned __int16 *v48; // [rsp+128h] [rbp+57h]
  __int64 v49; // [rsp+150h] [rbp+7Fh]

  v48 = a3;
  v45[0] = 131074;
  v45[1] = L"*";
  v40 = 0u;
  v16 = a3;
  v38 = 0;
  v18 = 0;
  v42 = 0u;
  v19 = 0;
  v41 = 0u;
  v49 = 0;
  v43 = 0;
  v39 = 0;
  if ( !a3 || !*a3 )
  {
    v16 = (unsigned __int16 *)v45;
    v48 = (unsigned __int16 *)v45;
  }
  v20 = 1;
  v46 = (PERESOURCE)(a1 + 200);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 200), 1u);
  Resource = (PERESOURCE)(a1 + 96);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 96), 1u);
  v21 = SrvAdminLookupShareByName(a1, a2, v16);
  v22 = v21;
  if ( !v21 )
  {
    v23 = -1073741772;
LABEL_6:
    v24 = 0;
    goto LABEL_58;
  }
  if ( a5 )
  {
    if ( (a14 & 0x80u) != 0 )
    {
      if ( (*(_DWORD *)(v21 + 124) & 0x100000) == 0
        || *a5 < 0xAu
        || (v25 = *((_QWORD *)a5 + 1), *(_DWORD *)v25 != 6029404)
        || *(_WORD *)(v25 + 4) == 92 )
      {
        v23 = -1073741811;
LABEL_11:
        v20 = 1;
        goto LABEL_6;
      }
    }
  }
  if ( (a14 & 1) != 0 )
  {
    if ( a4 )
    {
      v26 = *(_WORD *)a4;
      if ( *(_WORD *)a4 )
      {
        WORD1(v40) = *(_WORD *)a4;
        LOWORD(v40) = v26;
        PoolWithTag = (unsigned int *)SrvNetAllocatePoolWithTag(258, WORD1(v40), 1684095315);
        v38 = PoolWithTag;
        *((_QWORD *)&v40 + 1) = PoolWithTag;
        v18 = PoolWithTag;
        if ( !PoolWithTag )
        {
          v23 = -1073741670;
          goto LABEL_11;
        }
        memmove(PoolWithTag, a4[1], *(unsigned __int16 *)a4);
      }
    }
  }
  v28 = (_DWORD *)(v22 + 124);
  if ( (a14 & 0x80) == 0 || (*v28 & 0x100000) == 0 || !a5 || (v29 = *a5) == 0 )
  {
LABEL_28:
    v31 = 0;
    v23 = 0;
    if ( (a14 & 0x10) != 0 )
    {
      if ( SecurityDescriptor )
      {
        if ( RtlLengthSecurityDescriptor(SecurityDescriptor) )
        {
          v32 = SrvAdminDuplicateSecurityDescriptor(SecurityDescriptor, (void **)&v39, 0, 1);
          v19 = v39;
          v23 = v32;
          if ( v32 )
          {
            v23 = -1073741670;
            v20 = 1;
            goto LABEL_54;
          }
        }
      }
      v31 = *(_OWORD **)(v22 + 192);
      *(_QWORD *)(v22 + 192) = v19;
      v19 = 0;
    }
    if ( (a14 & 1) != 0 )
    {
      v38 = 0;
      v42 = *(_OWORD *)(v22 + 88);
      *(_OWORD *)(v22 + 88) = v40;
    }
    if ( (a14 & 0x80) != 0 && (*v28 & 0x100000) != 0 )
    {
      v43 = *(_QWORD *)(v22 + 208);
      v49 = 0;
      *(_OWORD *)(v22 + 200) = v41;
    }
    v33 = *(_DWORD *)(v22 + 104);
    if ( (a14 & 2) != 0 )
      *(_DWORD *)(v22 + 104) = a6;
    v34 = *(_DWORD *)(v22 + 128);
    if ( (a14 & 4) != 0 )
      *(_DWORD *)(v22 + 128) = a7;
    if ( (a14 & 0x20) != 0 )
      *(_DWORD *)(v22 + 140) = a10;
    if ( (a14 & 0x40) != 0 )
      *(_DWORD *)(v22 + 144) = a11;
    if ( (a14 & 0x100) != 0 )
      *(_DWORD *)(v22 + 216) = a12;
    if ( a13 && (a14 & 0x200) != 0 )
      *(_OWORD *)(v22 + 220) = *a13;
    ExReleaseResourceLite(Resource);
    v20 = 0;
    SrvAdminUpdateProvidersOfShare(v22, 2261011);
    SrvLibAuditShareModification(
      a2,
      v48,
      (_QWORD *)(v22 + 72),
      v31,
      *(_OWORD **)(v22 + 192),
      v33,
      *(_DWORD *)(v22 + 104),
      &v42,
      v22 + 88,
      v34,
      *(_DWORD *)(v22 + 128));
    if ( !v31 )
      goto LABEL_56;
    SrvNetUpdateMemStatistics(*((unsigned int *)v31 - 3), *((unsigned int *)v31 - 4), 0);
    ExFreePoolWithTag(v31 - 1, 0);
LABEL_54:
    if ( v19 )
    {
      SrvNetUpdateMemStatistics(*(v19 - 3), *(v19 - 4), 0);
      ExFreePoolWithTag(v19 - 4, 0);
    }
LABEL_56:
    v24 = (unsigned int *)v49;
    goto LABEL_57;
  }
  WORD1(v41) = *a5;
  LOWORD(v41) = v29;
  v30 = (unsigned int *)SrvNetAllocatePoolWithTag(258, WORD1(v41), 1684095315);
  v49 = (__int64)v30;
  v24 = v30;
  *((_QWORD *)&v41 + 1) = v30;
  if ( v30 )
  {
    memmove(v30, *((const void **)a5 + 1), *a5);
    goto LABEL_28;
  }
  v23 = -1073741670;
  v20 = 1;
LABEL_57:
  v18 = v38;
LABEL_58:
  v35 = *((_QWORD *)&v42 + 1);
  if ( *((_QWORD *)&v42 + 1) )
  {
    SrvNetUpdateMemStatistics(
      *(unsigned int *)(*((_QWORD *)&v42 + 1) - 12LL),
      *(unsigned int *)(*((_QWORD *)&v42 + 1) - 16LL),
      0);
    ExFreePoolWithTag((PVOID)(v35 - 16), 0);
  }
  if ( v18 )
  {
    SrvNetUpdateMemStatistics(*(v18 - 3), *(v18 - 4), 0);
    ExFreePoolWithTag(v18 - 4, 0);
  }
  if ( v43 )
  {
    v36 = (void *)(v43 - 16);
    SrvNetUpdateMemStatistics(*(unsigned int *)(v43 - 16 + 4), *(unsigned int *)(v43 - 16), 0);
    ExFreePoolWithTag(v36, 0);
  }
  if ( v24 )
  {
    SrvNetUpdateMemStatistics(*(v24 - 3), *(v24 - 4), 0);
    ExFreePoolWithTag(v24 - 4, 0);
  }
  if ( v22 )
    SrvAdminDereferenceShare(v22);
  ExReleaseResourceLite(v46);
  if ( v20 )
    ExReleaseResourceLite(Resource);
  return v23;
}

```

## disassembly

```asm
0x140025b80  mov     rax, rsp
0x140025b83  mov     [rax+20h], rbx
0x140025b87  mov     [rax+18h], r8
0x140025b8b  mov     [rax+10h], rdx
0x140025b8f  push    rbp
0x140025b90  push    rsi
0x140025b91  push    rdi
0x140025b92  push    r12
0x140025b94  push    r13
0x140025b96  push    r14
0x140025b98  push    r15
0x140025b9a  lea     rbp, [rax-3Fh]
0x140025b9e  sub     rsp, 0D0h
0x140025ba5  mov     rbx, rcx
0x140025ba8  mov     [rbp+37h+var_50], 20002h
0x140025bb0  xor     ecx, ecx
0x140025bb2  lea     rax, Buf2; "*"
0x140025bb9  mov     [rbp+37h+var_48], rax
0x140025bbd  mov     r15, r9
0x140025bc0  mov     qword ptr [rbp+37h+var_90], rcx
0x140025bc4  mov     rdi, r8
0x140025bc7  mov     [rbp+37h+var_A0], rcx
0x140025bcb  mov     rsi, rdx
0x140025bce  mov     qword ptr [rbp+37h+var_90+8], rcx
0x140025bd2  mov     r12d, ecx
0x140025bd5  mov     qword ptr [rbp+37h+var_70], rcx
0x140025bd9  mov     r13d, ecx
0x140025bdc  mov     qword ptr [rbp+37h+var_70+8], rcx
0x140025be0  mov     qword ptr [rbp+37h+var_80], rcx
0x140025be4  mov     [rbp+37h+arg_38], rcx
0x140025be8  mov     qword ptr [rbp+37h+var_80+8], rcx
0x140025bec  mov     [rbp+37h+var_60], rcx
0x140025bf0  mov     [rbp+37h+var_98], rcx
0x140025bf4  test    r8, r8
0x140025bf7  jz      short loc_140025BFF
0x140025bf9  cmp     [r8], cx
0x140025bfd  jnz     short loc_140025C07
0x140025bff  lea     rdi, [rbp+37h+var_50]
0x140025c03  mov     [rbp+37h+arg_10], rdi
0x140025c07  lea     rax, [rbx+0C8h]
0x140025c0e  mov     r14d, 1
0x140025c14  mov     dl, r14b; Wait
0x140025c17  mov     [rbp+37h+var_40], rax
0x140025c1b  mov     rcx, rax; Resource
0x140025c1e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140025c25  nop     dword ptr [rax+rax+00h]
0x140025c2a  lea     rax, [rbx+60h]
0x140025c2e  mov     dl, r14b; Wait
0x140025c31  mov     rcx, rax; Resource
0x140025c34  mov     [rbp+37h+Resource], rax
0x140025c38  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140025c3f  nop     dword ptr [rax+rax+00h]
0x140025c44  mov     r8, rdi
0x140025c47  mov     rdx, rsi
0x140025c4a  mov     rcx, rbx
0x140025c4d  call    SrvAdminLookupShareByName
0x140025c52  xor     ecx, ecx
0x140025c54  mov     rsi, rax
0x140025c57  test    rax, rax
0x140025c5a  jnz     short loc_140025C69
0x140025c5c  mov     edi, 0C0000034h
0x140025c61  mov     r15, rcx
0x140025c64  jmp     loc_140025F67
0x140025c69  mov     rdi, [rbp+37h+arg_20]
0x140025c6d  mov     r14d, [rbp+37h+arg_68]
0x140025c74  test    rdi, rdi
0x140025c77  jz      short loc_140025CB2
0x140025c79  test    r14b, r14b
0x140025c7c  jns     short loc_140025CB2
0x140025c7e  test    dword ptr [rax+7Ch], 100000h
0x140025c85  jnz     short loc_140025C94
0x140025c87  mov     edi, 0C000000Dh
0x140025c8c  mov     r14d, 1
0x140025c92  jmp     short loc_140025C61
0x140025c94  cmp     word ptr [rdi], 0Ah
0x140025c98  jb      short loc_140025C87
0x140025c9a  mov     rax, [rdi+8]
0x140025c9e  cmp     word ptr [rax], 5Ch ; '\'
0x140025ca2  jnz     short loc_140025C87
0x140025ca4  cmp     word ptr [rax+2], 5Ch ; '\'
0x140025ca9  jnz     short loc_140025C87
0x140025cab  cmp     word ptr [rax+4], 5Ch ; '\'
0x140025cb0  jz      short loc_140025C87
0x140025cb2  mov     eax, r14d
0x140025cb5  and     eax, 1
0x140025cb8  mov     [rbp+37h+arg_0], eax
0x140025cbb  jz      short loc_140025D10
0x140025cbd  test    r15, r15
0x140025cc0  jz      short loc_140025D10
0x140025cc2  movzx   eax, word ptr [r15]
0x140025cc6  test    ax, ax
0x140025cc9  jz      short loc_140025D10
0x140025ccb  mov     edx, eax
0x140025ccd  mov     word ptr [rbp+37h+var_90+2], ax
0x140025cd1  mov     ecx, 102h
0x140025cd6  mov     word ptr [rbp+37h+var_90], ax
0x140025cda  mov     r8d, 64614153h
0x140025ce0  call    SrvNetAllocatePoolWithTag
0x140025ce5  xor     ecx, ecx
0x140025ce7  mov     [rbp+37h+var_A0], rax
0x140025ceb  mov     qword ptr [rbp+37h+var_90+8], rax
0x140025cef  mov     r12, rax
0x140025cf2  test    rax, rax
0x140025cf5  jnz     short loc_140025CFE
0x140025cf7  mov     edi, 0C000009Ah
0x140025cfc  jmp     short loc_140025C8C
0x140025cfe  movzx   r8d, word ptr [r15]; Size
0x140025d02  mov     rcx, rax; void *
0x140025d05  mov     rdx, [r15+8]; Src
0x140025d09  call    memmove
0x140025d0e  xor     ecx, ecx
0x140025d10  mov     r12d, r14d
0x140025d13  lea     rbx, [rsi+7Ch]
0x140025d17  and     r12d, 80h
0x140025d1e  jz      short loc_140025D7F
0x140025d20  test    dword ptr [rbx], 100000h
0x140025d26  jz      short loc_140025D7F
0x140025d28  test    rdi, rdi
0x140025d2b  jz      short loc_140025D7F
0x140025d2d  movzx   eax, word ptr [rdi]
0x140025d30  test    ax, ax
0x140025d33  jz      short loc_140025D7F
0x140025d35  mov     edx, eax
0x140025d37  mov     word ptr [rbp+37h+var_80+2], ax
0x140025d3b  mov     ecx, 102h
0x140025d40  mov     word ptr [rbp+37h+var_80], ax
0x140025d44  mov     r8d, 64614153h
0x140025d4a  call    SrvNetAllocatePoolWithTag
0x140025d4f  mov     [rbp+37h+arg_38], rax
0x140025d53  mov     r15, rax
0x140025d56  mov     qword ptr [rbp+37h+var_80+8], rax
0x140025d5a  test    rax, rax
0x140025d5d  jnz     short loc_140025D6D
0x140025d5f  mov     edi, 0C000009Ah
0x140025d64  lea     r14d, [rax+1]
0x140025d68  jmp     loc_140025F63
0x140025d6d  movzx   r8d, word ptr [rdi]; Size
0x140025d71  mov     rcx, rax; void *
0x140025d74  mov     rdx, [rdi+8]; Src
0x140025d78  call    memmove
0x140025d7d  xor     ecx, ecx
0x140025d7f  mov     r15, rcx
0x140025d82  mov     edi, ecx
0x140025d84  test    r14b, 10h
0x140025d88  jz      short loc_140025DE8
0x140025d8a  mov     r15, [rbp+37h+SecurityDescriptor]
0x140025d91  test    r15, r15
0x140025d94  jz      short loc_140025DD7
0x140025d96  mov     rcx, r15; SecurityDescriptor
0x140025d99  call    cs:__imp_RtlLengthSecurityDescriptor
0x140025da0  nop     dword ptr [rax+rax+00h]
0x140025da5  xor     ecx, ecx
0x140025da7  test    eax, eax
0x140025da9  jz      short loc_140025DD7
0x140025dab  mov     r9b, 1
0x140025dae  lea     rdx, [rbp+37h+var_98]
0x140025db2  xor     r8d, r8d
0x140025db5  mov     rcx, r15; AbsoluteSecurityDescriptor
0x140025db8  call    SrvAdminDuplicateSecurityDescriptor
0x140025dbd  mov     r13, [rbp+37h+var_98]
0x140025dc1  xor     ecx, ecx
0x140025dc3  mov     edi, eax
0x140025dc5  test    eax, eax
0x140025dc7  jz      short loc_140025DD7
0x140025dc9  mov     edi, 0C000009Ah
0x140025dce  lea     r14d, [rcx+1]
0x140025dd2  jmp     loc_140025F38
0x140025dd7  mov     r15, [rsi+0C0h]
0x140025dde  mov     [rsi+0C0h], r13
0x140025de5  mov     r13, rcx
0x140025de8  cmp     [rbp+37h+arg_0], ecx
0x140025deb  jz      short loc_140025E03
0x140025ded  movups  xmm0, xmmword ptr [rsi+58h]
0x140025df1  mov     [rbp+37h+var_A0], rcx
0x140025df5  movups  xmm1, [rbp+37h+var_90]
0x140025df9  movdqu  [rbp+37h+var_70], xmm0
0x140025dfe  movdqu  xmmword ptr [rsi+58h], xmm1
0x140025e03  test    r12d, r12d
0x140025e06  jz      short loc_140025E2B
0x140025e08  test    dword ptr [rbx], 100000h
0x140025e0e  jz      short loc_140025E2B
0x140025e10  mov     rax, [rsi+0D0h]
0x140025e17  movups  xmm0, [rbp+37h+var_80]
0x140025e1b  mov     [rbp+37h+var_60], rax
0x140025e1f  mov     [rbp+37h+arg_38], rcx
0x140025e23  movdqu  xmmword ptr [rsi+0C8h], xmm0
0x140025e2b  mov     r12d, [rsi+68h]
0x140025e2f  test    r14b, 2
0x140025e33  jz      short loc_140025E3B
0x140025e35  mov     eax, [rbp+37h+arg_28]
0x140025e38  mov     [rsi+68h], eax
0x140025e3b  mov     ebx, [rsi+80h]
0x140025e41  test    r14b, 4
0x140025e45  jz      short loc_140025E50
0x140025e47  mov     eax, [rbp+37h+arg_30]
0x140025e4a  mov     [rsi+80h], eax
0x140025e50  test    r14b, 20h
0x140025e54  jz      short loc_140025E62
0x140025e56  mov     eax, [rbp+37h+arg_48]
0x140025e5c  mov     [rsi+8Ch], eax
0x140025e62  test    r14b, 40h
0x140025e66  jz      short loc_140025E74
0x140025e68  mov     eax, [rbp+37h+arg_50]
0x140025e6e  mov     [rsi+90h], eax
0x140025e74  bt      r14d, 8
0x140025e79  jnb     short loc_140025E87
0x140025e7b  mov     eax, [rbp+37h+arg_58]
0x140025e81  mov     [rsi+0D8h], eax
0x140025e87  mov     rax, [rbp+37h+arg_60]
0x140025e8e  test    rax, rax
0x140025e91  jz      short loc_140025EA5
0x140025e93  bt      r14d, 9
0x140025e98  jnb     short loc_140025EA5
0x140025e9a  movups  xmm0, xmmword ptr [rax]
0x140025e9d  movdqu  xmmword ptr [rsi+0DCh], xmm0
0x140025ea5  mov     rcx, [rbp+37h+Resource]; Resource
0x140025ea9  call    cs:__imp_ExReleaseResourceLite
0x140025eb0  nop     dword ptr [rax+rax+00h]
0x140025eb5  mov     edx, 228013h
0x140025eba  mov     rcx, rsi
0x140025ebd  xor     r14b, r14b
0x140025ec0  call    SrvAdminUpdateProvidersOfShare
0x140025ec5  mov     eax, [rsi+80h]
0x140025ecb  lea     rcx, [rsi+58h]
0x140025ecf  mov     rdx, [rbp+37h+arg_10]
0x140025ed3  lea     r8, [rsi+48h]
0x140025ed7  mov     [rsp+50h], eax
0x140025edb  mov     r9, r15
0x140025ede  mov     [rsp+100h+var_B8], ebx
0x140025ee2  lea     rax, [rbp+37h+var_70]
0x140025ee6  mov     qword ptr [rsp+100h+var_C0], rcx
0x140025eeb  mov     rcx, [rbp+37h+arg_8]
0x140025eef  mov     [rsp+100h+var_C8], rax
0x140025ef4  mov     eax, [rsi+68h]
0x140025ef7  mov     dword ptr [rsp+100h+var_D0], eax
0x140025efb  mov     rax, [rsi+0C0h]
0x140025f02  mov     [rsp+100h+var_D8], r12d
0x140025f07  mov     qword ptr [rsp+100h+var_E0], rax
0x140025f0c  call    SrvLibAuditShareModification
0x140025f11  test    r15, r15
0x140025f14  jz      short loc_140025F5F
0x140025f16  mov     ecx, [r15-0Ch]
0x140025f1a  xor     r8d, r8d
0x140025f1d  mov     edx, [r15-10h]
0x140025f21  call    SrvNetUpdateMemStatistics
0x140025f26  xor     edx, edx; Tag
0x140025f28  lea     rcx, [r15-10h]; P
0x140025f2c  call    cs:__imp_ExFreePoolWithTag
0x140025f33  nop     dword ptr [rax+rax+00h]
0x140025f38  test    r13, r13
0x140025f3b  jz      short loc_140025F5F
0x140025f3d  mov     ecx, [r13-0Ch]
0x140025f41  xor     r8d, r8d
0x140025f44  mov     edx, [r13-10h]
0x140025f48  call    SrvNetUpdateMemStatistics
0x140025f4d  xor     edx, edx; Tag
0x140025f4f  lea     rcx, [r13-10h]; P
0x140025f53  call    cs:__imp_ExFreePoolWithTag
0x140025f5a  nop     dword ptr [rax+rax+00h]
0x140025f5f  mov     r15, [rbp+37h+arg_38]
0x140025f63  mov     r12, [rbp+37h+var_A0]
0x140025f67  mov     rbx, qword ptr [rbp+37h+var_70+8]
0x140025f6b  test    rbx, rbx
0x140025f6e  jz      short loc_140025F90
0x140025f70  mov     ecx, [rbx-0Ch]
0x140025f73  xor     r8d, r8d
0x140025f76  mov     edx, [rbx-10h]
0x140025f79  call    SrvNetUpdateMemStatistics
0x140025f7e  xor     edx, edx; Tag
0x140025f80  lea     rcx, [rbx-10h]; P
0x140025f84  call    cs:__imp_ExFreePoolWithTag
0x140025f8b  nop     dword ptr [rax+rax+00h]
0x140025f90  test    r12, r12
0x140025f93  jz      short loc_140025FBA
0x140025f95  mov     ecx, [r12-0Ch]
0x140025f9a  xor     r8d, r8d
0x140025f9d  mov     edx, [r12-10h]
0x140025fa2  call    SrvNetUpdateMemStatistics
0x140025fa7  xor     edx, edx; Tag
0x140025fa9  lea     rcx, [r12-10h]; P
0x140025fae  call    cs:__imp_ExFreePoolWithTag
0x140025fb5  nop     dword ptr [rax+rax+00h]
0x140025fba  mov     rax, [rbp+37h+var_60]
0x140025fbe  test    rax, rax
0x140025fc1  jz      short loc_140025FE5
0x140025fc3  lea     rbx, [rax-10h]
0x140025fc7  xor     r8d, r8d
0x140025fca  mov     ecx, [rbx+4]
0x140025fcd  mov     edx, [rbx]
0x140025fcf  call    SrvNetUpdateMemStatistics
0x140025fd4  xor     edx, edx; Tag
0x140025fd6  mov     rcx, rbx; P
0x140025fd9  call    cs:__imp_ExFreePoolWithTag
0x140025fe0  nop     dword ptr [rax+rax+00h]
0x140025fe5  test    r15, r15
0x140025fe8  jz      short loc_14002600C
0x140025fea  mov     ecx, [r15-0Ch]
0x140025fee  xor     r8d, r8d
0x140025ff1  mov     edx, [r15-10h]
0x140025ff5  call    SrvNetUpdateMemStatistics
  ... truncated ...
```
