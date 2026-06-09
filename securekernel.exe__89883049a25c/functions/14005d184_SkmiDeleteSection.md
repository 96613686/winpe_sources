# SkmiDeleteSection

- ea: `0x14005d184`
- end: `0x14005d36c`
- name: `SkmiDeleteSection`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x14006004c`

## callees

- `0x140002900`
- `0x140002ef0`
- `0x14000b084`
- `0x14000b980`
- `0x14000f8b0`
- `0x14001df2c`
- `0x140024724`
- `0x1400518a4`
- `0x14005d184`
- `0x14005d374`
- `0x14005e660`
- `0x140087b9c`
- `0x140095cd8`

## pseudocode

```c
void __fastcall SkmiDeleteSection(int *a1)
{
  _QWORD *StackBase; // rcx
  char v3; // r12
  __int64 v4; // rcx
  __int64 *v5; // rbp
  int v6; // r14d
  ULONG_PTR *i; // rsi
  ULONG_PTR v8; // rdi
  int v9; // eax
  ULONG_PTR v10; // rcx
  char v11; // r15
  __int64 v12; // r8
  __int64 v13; // r9
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v17; // rcx
  __int64 v18; // [rsp+70h] [rbp+8h] BYREF

  if ( *((_QWORD *)a1 + 1) )
  {
    StackBase = KeGetPcr()->NtTib.StackBase;
    v3 = 0;
    v18 = 0;
    if ( StackBase )
    {
      v4 = StackBase[18];
      if ( v4 )
        --*(_WORD *)(v4 + xmmword_140167150);
    }
    if ( (*a1 & 0x2000) != 0 )
      SkAcquirePushLockExclusive(&SkmiVtl0SectionsLock);
    if ( (*a1 & 0x200000) != 0 )
    {
      v5 = &v18;
      RtlAcquireSRWLockShared(&SkmiTrustedFirmwareRangeLock);
    }
    else
    {
      v5 = 0;
    }
    v6 = a1[1];
    for ( i = (ULONG_PTR *)*((_QWORD *)a1 + 1); v6; --v6 )
    {
      if ( (*i & 1) != 0 )
      {
        v8 = (*i >> 12) & 0xFFFFFFFFFFLL;
        v9 = *a1;
        if ( (*a1 & 0x2000) != 0 )
        {
          v10 = (*i >> 12) & 0xFFFFFFFFFFLL;
          if ( (v9 & 0x208000) == 0x8000 )
          {
            v11 = SkmiDecrementInsecurePageSectionsCount(v10);
            SkmiDecrementPageReferenceCount(v8);
          }
          else
          {
            SkmiReleaseTrustedPage(v10);
            v11 = 1;
          }
          v3 |= v11;
          *i = (v8 << 12) | v11 & 1;
        }
        else
        {
          if ( (v9 & 0x20000) != 0 )
            SkmiReleaseTrustedPage((*i >> 12) & 0xFFFFFFFFFFLL);
          SkmiFreePhysicalPage(0, v8);
        }
      }
      ++i;
    }
    if ( v5 )
      RtlReleaseSRWLockShared(&SkmiTrustedFirmwareRangeLock);
    if ( (*a1 & 0x2000) != 0 )
    {
      if ( v3 )
        SkmiUnmarkSpecifyPagesSectionPages(a1);
      RtlReleaseSRWLockExclusive(&SkmiVtl0SectionsLock);
    }
    SkmiFreeSectionProtoPtes(a1);
    v14 = KeGetPcr()->NtTib.StackBase;
    if ( v14 )
    {
      v15 = v14[18];
      if ( v15 )
      {
        if ( (*(_WORD *)(v15 + xmmword_140167150))++ == 0xFFFF
          && *(_QWORD *)(v15 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v14[17]
          && !*(_WORD *)(v15 + *((_QWORD *)&xmmword_140167150 + 1)) )
        {
          SkiCheckForKernelApcDelivery(xmmword_140167160, v15, v12, v13);
        }
      }
    }
  }
  v17 = *((_QWORD *)a1 + 3);
  if ( v17 )
    SkobDereferenceObject(v17);
}

```

## disassembly

```asm
0x14005d184  push    rbx
0x14005d186  push    rbp
0x14005d187  push    rsi
0x14005d188  push    rdi
0x14005d189  push    r12
0x14005d18b  push    r13
0x14005d18d  push    r14
0x14005d18f  push    r15
0x14005d191  sub     rsp, 28h
0x14005d195  xor     r13d, r13d
0x14005d198  mov     rbx, rcx
0x14005d19b  cmp     [rcx+8], r13
0x14005d19f  jz      loc_14005D34C
0x14005d1a5  mov     rcx, gs:8
0x14005d1ae  mov     r12b, r13b
0x14005d1b1  mov     [rsp+68h+arg_0], r13
0x14005d1b6  test    rcx, rcx
0x14005d1b9  jz      short loc_14005D1D3
0x14005d1bb  mov     rcx, [rcx+90h]
0x14005d1c2  test    rcx, rcx
0x14005d1c5  jz      short loc_14005D1D3
0x14005d1c7  mov     rax, qword ptr cs:xmmword_140167150
0x14005d1ce  dec     word ptr [rcx+rax]
0x14005d1d2  nop
0x14005d1d3  mov     r15d, 2000h
0x14005d1d9  test    [rbx], r15d
0x14005d1dc  jz      short loc_14005D1EA
0x14005d1de  lea     rcx, SkmiVtl0SectionsLock
0x14005d1e5  call    SkAcquirePushLockExclusive
0x14005d1ea  test    dword ptr [rbx], 200000h
0x14005d1f0  jz      short loc_14005D205
0x14005d1f2  lea     rcx, SkmiTrustedFirmwareRangeLock
0x14005d1f9  lea     rbp, [rsp+68h+arg_0]
0x14005d1fe  call    RtlAcquireSRWLockShared
0x14005d203  jmp     short loc_14005D208
0x14005d205  mov     rbp, r13
0x14005d208  mov     r14d, [rbx+4]
0x14005d20c  mov     edi, 1
0x14005d211  mov     rsi, [rbx+8]
0x14005d215  test    r14d, r14d
0x14005d218  jz      loc_14005D2C2
0x14005d21e  mov     r13d, edi
0x14005d221  mov     rdi, [rsi]
0x14005d224  test    r13b, dil
0x14005d227  jz      loc_14005D2AD
0x14005d22d  shr     rdi, 0Ch
0x14005d231  mov     rax, 0FFFFFFFFFFh
0x14005d23b  and     rdi, rax
0x14005d23e  mov     eax, [rbx]
0x14005d240  test    r15d, eax
0x14005d243  jnz     short loc_14005D265
0x14005d245  bt      eax, 11h
0x14005d249  jnb     short loc_14005D259
0x14005d24b  xor     edx, edx
0x14005d24d  mov     rcx, rdi; BugCheckParameter3
0x14005d250  lea     r8d, [rdx+2]
0x14005d254  call    SkmiReleaseTrustedPage
0x14005d259  mov     rdx, rdi
0x14005d25c  xor     ecx, ecx
0x14005d25e  call    SkmiFreePhysicalPage
0x14005d263  jmp     short loc_14005D2AD
0x14005d265  and     eax, 208000h
0x14005d26a  mov     rcx, rdi; BugCheckParameter3
0x14005d26d  cmp     eax, 8000h
0x14005d272  jnz     short loc_14005D286
0x14005d274  call    SkmiDecrementInsecurePageSectionsCount
0x14005d279  mov     rcx, rdi; BugCheckParameter3
0x14005d27c  mov     r15d, eax
0x14005d27f  call    SkmiDecrementPageReferenceCount
0x14005d284  jmp     short loc_14005D294
0x14005d286  xor     r8d, r8d
0x14005d289  mov     rdx, rbp
0x14005d28c  call    SkmiReleaseTrustedPage
0x14005d291  mov     r15d, r13d
0x14005d294  mov     eax, r15d
0x14005d297  shl     rdi, 0Ch
0x14005d29b  and     rax, r13
0x14005d29e  or      rax, rdi
0x14005d2a1  or      r12b, r15b
0x14005d2a4  mov     [rsi], rax
0x14005d2a7  mov     r15d, 2000h
0x14005d2ad  add     rsi, 8
0x14005d2b1  add     r14d, 0FFFFFFFFh
0x14005d2b5  jnz     loc_14005D221
0x14005d2bb  xor     r13d, r13d
0x14005d2be  lea     edi, [r14+1]
0x14005d2c2  test    rbp, rbp
0x14005d2c5  jz      short loc_14005D2D3
0x14005d2c7  lea     rcx, SkmiTrustedFirmwareRangeLock
0x14005d2ce  call    RtlReleaseSRWLockShared
0x14005d2d3  test    [rbx], r15d
0x14005d2d6  jz      short loc_14005D2F1
0x14005d2d8  test    r12b, r12b
0x14005d2db  jz      short loc_14005D2E5
0x14005d2dd  mov     rcx, rbx
0x14005d2e0  call    SkmiUnmarkSpecifyPagesSectionPages
0x14005d2e5  lea     rcx, SkmiVtl0SectionsLock
0x14005d2ec  call    RtlReleaseSRWLockExclusive
0x14005d2f1  mov     rcx, rbx
0x14005d2f4  call    SkmiFreeSectionProtoPtes
0x14005d2f9  mov     rcx, gs:8
0x14005d302  test    rcx, rcx
0x14005d305  jz      short loc_14005D34C
0x14005d307  mov     rdx, [rcx+90h]
0x14005d30e  test    rdx, rdx
0x14005d311  jz      short loc_14005D34C
0x14005d313  nop
0x14005d314  mov     rax, qword ptr cs:xmmword_140167150
0x14005d31b  add     [rdx+rax], di
0x14005d31f  jnz     short loc_14005D34C
0x14005d321  mov     rax, [rcx+88h]
0x14005d328  nop
0x14005d329  mov     rcx, qword ptr cs:xmmword_140167160
0x14005d330  add     rax, rcx
0x14005d333  cmp     [rdx+rcx], rax
0x14005d337  jz      short loc_14005D34C
0x14005d339  mov     rax, qword ptr cs:xmmword_140167150+8
0x14005d340  cmp     [rdx+rax], r13w
0x14005d345  jnz     short loc_14005D34C
0x14005d347  call    SkiCheckForKernelApcDelivery
0x14005d34c  mov     rcx, [rbx+18h]
0x14005d350  test    rcx, rcx
0x14005d353  jz      short loc_14005D35A
0x14005d355  call    SkobDereferenceObject
0x14005d35a  add     rsp, 28h
0x14005d35e  pop     r15
0x14005d360  pop     r14
0x14005d362  pop     r13
0x14005d364  pop     r12
0x14005d366  pop     rdi
0x14005d367  pop     rsi
0x14005d368  pop     rbp
0x14005d369  pop     rbx
0x14005d36a  retn
```
