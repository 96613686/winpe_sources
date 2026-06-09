# SkmiClaimPhysicalPages

- ea: `0x140050ba4`
- end: `0x140050f6e`
- name: `SkmiClaimPhysicalPages`
- size: `970`
- prototype: `__int64 __fastcall(ULONG_PTR, __int64, unsigned int)`
- caller_count: `30`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140010c00`
- `0x140012750`
- `0x140014dd0`
- `0x140050fcc`
- `0x140055000`
- `0x140056878`
- `0x1400568ec`
- `0x140057534`
- `0x1400578dc`
- `0x14005d8f4`
- `0x14005fc00`
- `0x140061d60`
- `0x140062334`
- `0x140063ca8`
- `0x14006cd8c`
- `0x14006cfe0`
- `0x14006ffbc`
- `0x140070cd8`
- `0x140071704`
- `0x14007204c`
- `0x1400720b8`
- `0x140072594`
- `0x140072b1c`
- `0x140072fc4`
- `0x140074020`
- `0x140078b6c`
- `0x14007a358`
- `0x14007b0fc`
- `0x14008451c`
- `0x1400ee634`

## callees

- `0x140009890`
- `0x1400119c4`
- `0x140011d50`
- `0x14002b534`
- `0x14003afa4`
- `0x140050ba4`
- `0x14005443c`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiClaimPhysicalPages(ULONG_PTR a1, __int64 a2, unsigned int a3)
{
  __int64 v5; // rcx
  int v6; // edx
  unsigned __int64 v7; // rbx
  ULONG_PTR v8; // r8
  ULONG_PTR BugCheckParameter4; // r9
  __int64 v10; // r10
  unsigned int v11; // ecx
  ULONG_PTR v12; // rbp
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rdi
  signed __int64 v15; // rsi
  unsigned __int64 v16; // rdi
  int v17; // r12d
  unsigned __int64 v18; // r8
  __int64 v19; // rcx
  __int64 DataTraceEntry; // rax
  __int64 v21; // r8
  __int64 v22; // rdi
  _QWORD *v23; // rsi
  ULONG v24; // ecx
  USHORT v25; // ax
  __int64 v26; // rdx
  __int64 v27; // rcx
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-58h] BYREF
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v32; // [rsp+98h] [rbp+10h]
  unsigned int v33; // [rsp+A0h] [rbp+18h]

  v32 = a2;
  v5 = a3;
  LODWORD(v5) = a3 & 0xFFFF7FFF;
  v7 = SkmiPfnClassToContents(v5, a2, a1);
  if ( v7 >> 61 == 3 )
  {
    v7 &= 0xFFE3FFFFFFFFFFFFuLL;
  }
  else if ( v7 >> 61 == 5 )
  {
    v7 = v7 & 0xFFE3FFFFFFFFFFFFuLL | 0x4000000000000LL;
  }
  BugCheckParameter4 = 0;
  v10 = 1;
  v11 = 0;
  v33 = 0;
  if ( !v6 )
    return (unsigned int)v10;
  while ( 2 )
  {
    v12 = *(_QWORD *)(v8 + 8LL * v11);
    if ( v12 > 0xFFFFFFFFFFLL )
    {
      if ( (a3 & 0x8000) == 0 )
        SkeBugCheckEx(0x1Au, 0x56534Du, 0x901u, v12, BugCheckParameter4);
      return 0;
    }
    *(_QWORD *)BackTraceHash = 8 * v12;
    v13 = 8 * v12 - 0x180000000000LL;
    _m_prefetchw((const void *)v13);
LABEL_8:
    v14 = *(_QWORD *)v13;
    do
    {
      v15 = v14;
      if ( v14 >> 61 != v10 )
      {
LABEL_48:
        if ( (SkmiFlags & 2) != 0 && (a3 & 0x8000) == 0 )
          SkeBugCheckEx(0x1Au, 0x56534Du, 0x902u, v12, BugCheckParameter4);
        return 0;
      }
      if ( v7 >> 61 == 5
        && (v14 & 0xFFFFFFFFFFFLL) != 0
        && (v14 & 0x2000000000000LL) != 0
        && (v14 & 0xF00000000000LL) == 0 )
      {
        v16 = v14 & 0x1FC1FFFFFFFFFFFFLL | 0xA024000000000000uLL;
LABEL_14:
        v17 = v10;
        goto LABEL_24;
      }
      if ( v14 >> 61 != v10 )
        goto LABEL_48;
      v17 = BugCheckParameter4;
      if ( v7 >> 61 == v10 )
      {
        if ( ((v14 + 1) & 0xFFFFFFFFFFFLL) == 0 )
        {
          if ( (a3 & 0x8000) == 0 )
            SkeBugCheckEx(0x1Au, 0x56534Du, 0x903u, v12, BugCheckParameter4);
          return 0;
        }
        v16 = v14 & 0xFFFDF00000000000uLL ^ (v14 + 1) & 0xFFFFFFFFFFFLL;
      }
      else if ( (v14 & 0xFFFFFFFFFFFLL) != 0 || (v14 & 0xF00000000000LL) != 0 )
      {
        v16 = BugCheckParameter4;
      }
      else
      {
        v16 = v7;
        if ( (((v7 >> 61) - 3) & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
          goto LABEL_14;
      }
LABEL_24:
      if ( !v16 )
        goto LABEL_48;
      if ( (*(_BYTE *)(((v13 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL) & 2) == 0 )
      {
        SkmiPopulatePfnDatabasePage(v13);
        BugCheckParameter4 = 0;
        v10 = 1;
      }
      if ( (v15 & 0x1000000000000000LL) != 0 )
      {
        _mm_pause();
        goto LABEL_8;
      }
      v18 = v16;
      v14 = _InterlockedCompareExchange64((volatile signed __int64 *)v13, v16, v15);
    }
    while ( v15 != v14 );
    v19 = (unsigned int)BugCheckParameter4;
    if ( v18 >> 61 == 2 && (v18 & 0xFFF) == 0x40E )
      v19 = (unsigned int)v10;
    DataTraceEntry = SkmiAllocateDataTraceEntry(v19, 0, v18, BugCheckParameter4);
    v22 = DataTraceEntry;
    if ( DataTraceEntry )
    {
      *(_QWORD *)(DataTraceEntry + 16) = v15;
      *(_QWORD *)(DataTraceEntry + 24) = v21;
      v23 = (_QWORD *)(DataTraceEntry + 32);
      *(_QWORD *)DataTraceEntry = *(__int64 *)BackTraceHash >> 3;
      *(_BYTE *)(DataTraceEntry + 8) = 2;
      memset_0((void *)(DataTraceEntry + 32), 0, 0x40u);
      BugCheckParameter4 = 0;
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        if ( KeGetPcr()->NtTib.StackBase )
        {
          v25 = RtlCaptureStackBackTrace(v24, 8u, (PVOID *)(v22 + 32), BackTraceHash);
          BugCheckParameter4 = 0;
          if ( !v25 )
          {
            *(_QWORD *)(v22 + 40) = retaddr;
            *v23 = SkmiGetInstructionPointer(v27, v26);
          }
        }
      }
      v10 = 1;
    }
    v11 = v10 + v33;
    v33 = v11;
    if ( v11 < v32 )
    {
      v8 = a1;
      continue;
    }
    break;
  }
  if ( v17 )
  {
    if ( (a3 & 0x40000) == 0 )
    {
      SkmiProtectPhysicalPages(a1);
      LODWORD(v10) = 1;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140050ba4  mov     [rsp+arg_8], edx
0x140050ba8  mov     [rsp+BugCheckParameter3], rcx
0x140050bad  push    rbx
0x140050bae  push    rbp
0x140050baf  push    rsi
0x140050bb0  push    rdi
0x140050bb1  push    r12
0x140050bb3  push    r13
0x140050bb5  push    r14
0x140050bb7  push    r15
0x140050bb9  sub     rsp, 48h
0x140050bbd  mov     r14d, r8d
0x140050bc0  mov     r8, rcx
0x140050bc3  mov     ecx, r14d
0x140050bc6  btr     ecx, 0Fh
0x140050bca  call    SkmiPfnClassToContents
0x140050bcf  mov     rbx, rax
0x140050bd2  shr     rax, 3Dh
0x140050bd6  cmp     rax, 3
0x140050bda  jnz     short loc_140050BEB
0x140050bdc  mov     rax, 0FFE3FFFFFFFFFFFFh
0x140050be6  and     rbx, rax
0x140050be9  jmp     short loc_140050C0B
0x140050beb  cmp     rax, 5
0x140050bef  jnz     short loc_140050C0B
0x140050bf1  mov     rax, 0FFE7FFFFFFFFFFFFh
0x140050bfb  and     rbx, rax
0x140050bfe  mov     rax, 4000000000000h
0x140050c08  or      rbx, rax
0x140050c0b  xor     r9d, r9d
0x140050c0e  lea     rcx, SkmiVtlPageAccess
0x140050c15  mov     rax, rbx
0x140050c18  shr     rax, 32h
0x140050c1c  and     eax, 7
0x140050c1f  lea     r10d, [r9+1]
0x140050c23  mov     eax, [rcx+rax*4]
0x140050c26  mov     ecx, r9d
0x140050c29  mov     [rsp+88h+arg_10], ecx
0x140050c30  mov     [rsp+88h+arg_18], eax
0x140050c37  test    edx, edx
0x140050c39  jz      loc_140050EE1
0x140050c3f  mov     r13, 0FFFFEFFFFFFFFFFFh
0x140050c49  mov     rdx, 0FFFFE80000000000h
0x140050c53  mov     rax, rdx
0x140050c56  sub     r13, rax
0x140050c59  sar     r13, 3
0x140050c5d  mov     eax, ecx
0x140050c5f  mov     r12, 0F00000000000h
0x140050c69  mov     r11, 0FFFFFFFFFFFh
0x140050c73  mov     rbp, [r8+rax*8]
0x140050c77  cmp     rbp, r13
0x140050c7a  ja      loc_140050F09
0x140050c80  lea     rcx, ds:0[rbp*8]
0x140050c88  mov     qword ptr [rsp+88h+BackTraceHash], rcx
0x140050c8d  mov     rax, rdx
0x140050c90  lea     r15, [rcx+rax]
0x140050c94  prefetchw byte ptr [r15]
0x140050c98  mov     rdi, [r15]
0x140050c9b  mov     rdx, rdi
0x140050c9e  mov     rsi, rdi
0x140050ca1  shr     rdx, 3Dh
0x140050ca5  cmp     rdx, r10
0x140050ca8  jnz     loc_140050EF6
0x140050cae  mov     rax, rbx
0x140050cb1  shr     rax, 3Dh
0x140050cb5  cmp     al, 5
0x140050cb7  jnz     short loc_140050CEF
0x140050cb9  test    r11, rdi
0x140050cbc  setnz   cl
0x140050cbf  bt      rdi, 31h ; '1'
0x140050cc4  setb    al
0x140050cc7  test    al, cl
0x140050cc9  jz      short loc_140050CEF
0x140050ccb  test    r12, rdi
0x140050cce  jnz     short loc_140050CEF
0x140050cd0  mov     rax, 1FC1FFFFFFFFFFFFh
0x140050cda  and     rdi, rax
0x140050cdd  mov     rax, 0A024000000000000h
0x140050ce7  or      rdi, rax
0x140050cea  mov     r12d, r10d
0x140050ced  jmp     short loc_140050D57
0x140050cef  cmp     rdx, r10
0x140050cf2  jnz     loc_140050EF6
0x140050cf8  mov     rax, rbx
0x140050cfb  mov     r12d, r9d
0x140050cfe  shr     rax, 3Dh
0x140050d02  cmp     rax, r10
0x140050d05  jnz     short loc_140050D2F
0x140050d07  lea     rcx, [rdi+1]
0x140050d0b  test    r11, rcx
0x140050d0e  jz      loc_140050EB1
0x140050d14  mov     rax, rdi
0x140050d17  and     rcx, r11
0x140050d1a  mov     rdx, 0FFFDF00000000000h
0x140050d24  mov     rdi, rcx
0x140050d27  and     rax, rdx
0x140050d2a  xor     rdi, rax
0x140050d2d  jmp     short loc_140050D57
0x140050d2f  test    r11, rdi
0x140050d32  jnz     short loc_140050D54
0x140050d34  mov     rcx, 0F00000000000h
0x140050d3e  test    rcx, rdi
0x140050d41  jnz     short loc_140050D54
0x140050d43  add     rax, 0FFFFFFFFFFFFFFFDh
0x140050d47  mov     rdi, rbx
0x140050d4a  test    rax, 0FFFFFFFFFFFFFFFDh
0x140050d50  jnz     short loc_140050D57
0x140050d52  jmp     short loc_140050CEA
0x140050d54  mov     rdi, r9
0x140050d57  test    rdi, rdi
0x140050d5a  jz      loc_140050EF6
0x140050d60  mov     rax, r15
0x140050d63  mov     rcx, 7FFFFFFFF8h
0x140050d6d  shr     rax, 9
0x140050d71  and     rax, rcx
0x140050d74  mov     rcx, 0FFFFF68000000000h
0x140050d7e  test    byte ptr [rax+rcx], 2
0x140050d82  jnz     short loc_140050D9D
0x140050d84  mov     rcx, r15
0x140050d87  call    SkmiPopulatePfnDatabasePage
0x140050d8c  xor     r9d, r9d
0x140050d8f  mov     r11, 0FFFFFFFFFFFh
0x140050d99  lea     r10d, [r9+1]
0x140050d9d  bt      rsi, 3Ch ; '<'
0x140050da2  jb      short loc_140050DC3
0x140050da4  mov     r8, rdi
0x140050da7  mov     rax, rsi
0x140050daa  lock cmpxchg [r15], rdi
0x140050daf  mov     rdi, rax
0x140050db2  jz      short loc_140050DD4
0x140050db4  mov     r12, 0F00000000000h
0x140050dbe  jmp     loc_140050C9B
0x140050dc3  pause
0x140050dc5  mov     r12, 0F00000000000h
0x140050dcf  jmp     loc_140050C98
0x140050dd4  mov     rax, r8
0x140050dd7  mov     ecx, r9d
0x140050dda  shr     rax, 3Dh
0x140050dde  cmp     al, 2
0x140050de0  jnz     short loc_140050DF4
0x140050de2  mov     rax, r8
0x140050de5  and     eax, 0FFFh
0x140050dea  cmp     rax, 40Eh
0x140050df0  cmovz   ecx, r10d
0x140050df4  xor     edx, edx
0x140050df6  call    SkmiAllocateDataTraceEntry
0x140050dfb  mov     rdi, rax
0x140050dfe  test    rax, rax
0x140050e01  jz      short loc_140050E7E
0x140050e03  mov     [rax+10h], rsi
0x140050e07  xor     edx, edx; Val
0x140050e09  mov     [rax+18h], r8
0x140050e0d  lea     rsi, [rdi+20h]
0x140050e11  mov     rax, qword ptr [rsp+88h+BackTraceHash]
0x140050e16  mov     rcx, rsi; void *
0x140050e19  sar     rax, 3
0x140050e1d  lea     r8d, [rdx+40h]; Size
0x140050e21  mov     [rdi], rax
0x140050e24  mov     byte ptr [rdi+8], 2
0x140050e28  call    memset_0
0x140050e2d  xor     r9d, r9d
0x140050e30  test    cs:SkmiFlags, 400000h
0x140050e3a  jz      short loc_140050E78
0x140050e3c  mov     rax, gs:8
0x140050e45  test    rax, rax
0x140050e48  jz      short loc_140050E78
0x140050e4a  lea     r9, [rsp+88h+BackTraceHash]; BackTraceHash
0x140050e4f  mov     r8, rsi; BackTrace
0x140050e52  mov     edx, 8; FramesToCapture
0x140050e57  call    RtlCaptureStackBackTrace
0x140050e5c  xor     r9d, r9d
0x140050e5f  test    ax, ax
0x140050e62  jnz     short loc_140050E78
0x140050e64  mov     rax, [rsp+88h]
0x140050e6c  mov     [rdi+28h], rax
0x140050e70  call    SkmiGetInstructionPointer
0x140050e75  mov     [rsi], rax
0x140050e78  mov     r10d, 1
0x140050e7e  mov     ecx, [rsp+88h+arg_10]
0x140050e85  mov     edx, [rsp+88h+arg_8]
0x140050e8c  add     ecx, r10d
0x140050e8f  mov     [rsp+88h+arg_10], ecx
0x140050e96  cmp     ecx, edx
0x140050e98  jnb     short loc_140050EBA
0x140050e9a  mov     r8, [rsp+88h+BugCheckParameter3]
0x140050ea2  mov     rdx, 0FFFFE80000000000h
0x140050eac  jmp     loc_140050C5D
0x140050eb1  bt      r14d, 0Fh
0x140050eb6  jnb     short loc_140050F14
0x140050eb8  jmp     short loc_140050F10
0x140050eba  test    r12d, r12d
0x140050ebd  jz      short loc_140050EE1
0x140050ebf  bt      r14d, 12h
0x140050ec4  jb      short loc_140050EE1
0x140050ec6  mov     r8d, [rsp+88h+arg_18]
0x140050ece  mov     rcx, [rsp+88h+BugCheckParameter3]; BugCheckParameter3
0x140050ed6  call    SkmiProtectPhysicalPages
0x140050edb  mov     r10d, 1
0x140050ee1  mov     eax, r10d
0x140050ee4  add     rsp, 48h
0x140050ee8  pop     r15
0x140050eea  pop     r14
0x140050eec  pop     r13
0x140050eee  pop     r12
0x140050ef0  pop     rdi
0x140050ef1  pop     rsi
0x140050ef2  pop     rbp
0x140050ef3  pop     rbx
0x140050ef4  retn
0x140050ef6  mov     eax, cs:SkmiFlags
0x140050efc  test    al, 2
0x140050efe  jz      short loc_140050F10
0x140050f00  bt      r14d, 0Fh
0x140050f05  jnb     short loc_140050F32
0x140050f07  jmp     short loc_140050F10
0x140050f09  bt      r14d, 0Fh
0x140050f0e  jnb     short loc_140050F50
0x140050f10  xor     eax, eax
0x140050f12  jmp     short loc_140050EE4
0x140050f14  mov     [rsp+88h+BugCheckParameter4], r9; BugCheckParameter4
0x140050f19  mov     edx, 56534Dh; BugCheckParameter1
0x140050f1e  mov     r9, rbp; BugCheckParameter3
0x140050f21  mov     ecx, 1Ah; BugCheckCode
0x140050f26  mov     r8d, 903h; BugCheckParameter2
0x140050f2c  call    SkeBugCheckEx
0x140050f32  mov     [rsp+88h+BugCheckParameter4], r9; BugCheckParameter4
0x140050f37  mov     edx, 56534Dh; BugCheckParameter1
0x140050f3c  mov     r9, rbp; BugCheckParameter3
0x140050f3f  mov     ecx, 1Ah; BugCheckCode
0x140050f44  mov     r8d, 902h; BugCheckParameter2
0x140050f4a  call    SkeBugCheckEx
0x140050f50  mov     [rsp+88h+BugCheckParameter4], r9; BugCheckParameter4
0x140050f55  mov     edx, 56534Dh; BugCheckParameter1
0x140050f5a  mov     r9, rbp; BugCheckParameter3
0x140050f5d  mov     ecx, 1Ah; BugCheckCode
0x140050f62  mov     r8d, 901h; BugCheckParameter2
0x140050f68  call    SkeBugCheckEx
```
