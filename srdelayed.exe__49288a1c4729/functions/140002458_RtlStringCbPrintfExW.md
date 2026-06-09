# RtlStringCbPrintfExW

- ea: `0x140002458`
- end: `0x140002686`
- name: `RtlStringCbPrintfExW`
- size: `558`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PWSTR *ppszDestEnd, size_t *pcbRemaining, ULONG dwFlags, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400020dc`
- `0x1400028a4`

## callees

- `0x140002458`
- `0x140003735`

## import_xrefs

- `ntdll!_vsnwprintf` at `0x1400025fa`
- `ntdll!_vsnwprintf` at `0x1400025fa`

## pseudocode

```c
NTSTATUS RtlStringCbPrintfExW(
        NTSTRSAFE_PWSTR pszDest,
        size_t cbDest,
        NTSTRSAFE_PWSTR *ppszDestEnd,
        size_t *pcbRemaining,
        ULONG dwFlags,
        NTSTRSAFE_PCWSTR pszFormat,
        ...)
{
  size_t v7; // rdi
  NTSTRSAFE_PCWSTR v9; // r8
  NTSTRSAFE_PWSTR v10; // r15
  size_t v11; // r14
  NTSTATUS v12; // ebp
  unsigned __int64 v14; // rbx
  int v15; // eax
  size_t v16; // r8
  size_t *v18; // [rsp+98h] [rbp+20h]
  va_list Args; // [rsp+B0h] [rbp+38h] BYREF

  va_start(Args, pszFormat);
  v18 = pcbRemaining;
  v7 = cbDest >> 1;
  if ( (dwFlags & 0x100) != 0 )
  {
    if ( (pszDest || !v7) && v7 <= 0x7FFFFFFF )
    {
      v9 = pszFormat;
      v10 = pszDest;
      v11 = cbDest >> 1;
      if ( !pszFormat )
        v9 = (NTSTRSAFE_PCWSTR)&qword_140004350;
LABEL_11:
      if ( (dwFlags & 0xFFFFE000) != 0 )
      {
        v12 = -1073741811;
        if ( v7 )
          *pszDest = 0;
        goto LABEL_14;
      }
      if ( !v7 )
      {
        v12 = 0;
        if ( !*v9 )
          goto LABEL_27;
        v10 = pszDest;
        v11 = cbDest >> 1;
        v12 = pszDest != 0 ? -2147483643 : -1073741811;
        goto LABEL_14;
      }
      v14 = v7 - 1;
      v15 = _vsnwprintf(pszDest, v7 - 1, v9, Args);
      if ( v15 < 0 || v15 > v14 )
      {
        v12 = -2147483643;
      }
      else
      {
        v12 = 0;
        if ( v15 != v14 )
        {
          v14 = v15;
          goto LABEL_41;
        }
      }
      pszDest[v14] = 0;
LABEL_41:
      v10 = &pszDest[v14];
      v11 = v7 - v14;
      if ( v12 >= 0 )
      {
        if ( (dwFlags & 0x200) != 0 )
        {
          v16 = (cbDest & 1) + 2 * v11;
          if ( v16 > 2 )
            memset_0(v10 + 1, (unsigned __int8)dwFlags, v16 - 2);
        }
LABEL_26:
        pcbRemaining = v18;
LABEL_27:
        if ( ppszDestEnd )
          *ppszDestEnd = v10;
        if ( pcbRemaining )
          *pcbRemaining = (cbDest & 1) + 2 * v11;
        return v12;
      }
LABEL_14:
      if ( (dwFlags & 0x1C00) == 0 || !cbDest )
        goto LABEL_25;
      if ( v7 && (dwFlags & 0x1000) != 0 )
      {
        v10 = pszDest;
        *pszDest = 0;
        v11 = v7;
      }
      if ( (dwFlags & 0x400) != 0 )
      {
        memset_0(pszDest, (unsigned __int8)dwFlags, cbDest);
        if ( (_BYTE)dwFlags )
        {
          if ( !v7 )
            goto LABEL_25;
          v11 = 1;
          v10 = &pszDest[v7 - 1];
          *v10 = 0;
          goto LABEL_23;
        }
        v10 = pszDest;
        v11 = v7;
      }
      if ( !v7 )
        goto LABEL_25;
LABEL_23:
      if ( (dwFlags & 0x800) != 0 )
      {
        v10 = pszDest;
        *pszDest = 0;
        v11 = v7;
      }
LABEL_25:
      if ( v12 != -2147483643 )
        return v12;
      goto LABEL_26;
    }
  }
  else if ( v7 - 1 <= 0x7FFFFFFE )
  {
    v9 = pszFormat;
    v10 = pszDest;
    v11 = cbDest >> 1;
    goto LABEL_11;
  }
  v12 = -1073741811;
  if ( v7 )
    *pszDest = 0;
  return v12;
}

```

## disassembly

```asm
0x140002458  mov     [rsp+arg_18], r9
0x14000245d  mov     [rsp+arg_10], r8
0x140002462  push    rbx
0x140002463  push    rbp
0x140002464  push    rsi
0x140002465  push    rdi
0x140002466  push    r12
0x140002468  push    r13
0x14000246a  push    r14
0x14000246c  push    r15
0x14000246e  sub     rsp, 38h
0x140002472  mov     r12d, [rsp+78h+dwFlags]
0x14000247a  mov     rdi, rdx
0x14000247d  mov     rsi, rcx
0x140002480  shr     rdi, 1
0x140002483  xor     ecx, ecx
0x140002485  mov     r13, rdx
0x140002488  bt      r12d, 8
0x14000248d  jnb     short loc_1400024C6
0x14000248f  test    rsi, rsi
0x140002492  jnz     short loc_140002499
0x140002494  test    rdi, rdi
0x140002497  jnz     short loc_1400024D2
0x140002499  cmp     rdi, 7FFFFFFFh
0x1400024a0  ja      short loc_1400024D2
0x1400024a2  mov     r8, [rsp+78h+pszFormat]
0x1400024aa  mov     r15, rsi
0x1400024ad  mov     r14, rdi
0x1400024b0  test    r8, r8
0x1400024b3  jnz     short loc_1400024F6
0x1400024b5  lea     r8, qword_140004350
0x1400024bc  mov     [rsp+78h+pszFormat], r8
0x1400024c4  jmp     short loc_1400024F6
0x1400024c6  lea     rax, [rdi-1]
0x1400024ca  cmp     rax, 7FFFFFFEh
0x1400024d0  jbe     short loc_1400024E8
0x1400024d2  mov     ebp, 0C000000Dh
0x1400024d7  test    rdi, rdi
0x1400024da  jz      loc_1400025A6
0x1400024e0  mov     [rsi], cx
0x1400024e3  jmp     loc_1400025A6
0x1400024e8  mov     r8, [rsp+78h+pszFormat]; Format
0x1400024f0  mov     r15, rsi
0x1400024f3  mov     r14, rdi
0x1400024f6  test    r12d, 0FFFFE000h
0x1400024fd  jz      loc_1400025B9
0x140002503  mov     ebp, 0C000000Dh
0x140002508  test    rdi, rdi
0x14000250b  jz      short loc_140002510
0x14000250d  mov     [rsi], cx
0x140002510  test    r12d, 1C00h
0x140002517  jz      short loc_14000256F
0x140002519  test    r13, r13
0x14000251c  jz      short loc_14000256F
0x14000251e  test    rdi, rdi
0x140002521  jz      short loc_140002533
0x140002523  bt      r12d, 0Ch
0x140002528  jnb     short loc_140002533
0x14000252a  mov     r15, rsi
0x14000252d  mov     [rsi], cx
0x140002530  mov     r14, rdi
0x140002533  bt      r12d, 0Ah
0x140002538  jnb     short loc_14000255A
0x14000253a  movzx   edx, r12b; Val
0x14000253e  mov     r8, r13; Size
0x140002541  mov     rcx, rsi; void *
0x140002544  call    memset_0
0x140002549  xor     ecx, ecx
0x14000254b  test    r12b, r12b
0x14000254e  jnz     loc_140002666
0x140002554  mov     r15, rsi
0x140002557  mov     r14, rdi
0x14000255a  test    rdi, rdi
0x14000255d  jz      short loc_14000256F
0x14000255f  bt      r12d, 0Bh
0x140002564  jnb     short loc_14000256F
0x140002566  mov     r15, rsi
0x140002569  mov     [rsi], cx
0x14000256c  mov     r14, rdi
0x14000256f  cmp     ebp, 80000005h
0x140002575  jnz     short loc_1400025A6
0x140002577  mov     r9, [rsp+78h+arg_18]
0x14000257f  mov     rax, [rsp+78h+arg_10]
0x140002587  test    rax, rax
0x14000258a  jz      short loc_14000258F
0x14000258c  mov     [rax], r15
0x14000258f  test    r9, r9
0x140002592  jz      short loc_1400025A6
0x140002594  and     r13d, 1
0x140002598  lea     rcx, ds:0[r14*2]
0x1400025a0  add     rcx, r13
0x1400025a3  mov     [r9], rcx
0x1400025a6  mov     eax, ebp
0x1400025a8  add     rsp, 38h
0x1400025ac  pop     r15
0x1400025ae  pop     r14
0x1400025b0  pop     r13
0x1400025b2  pop     r12
0x1400025b4  pop     rdi
0x1400025b5  pop     rsi
0x1400025b6  pop     rbp
0x1400025b7  pop     rbx
0x1400025b8  retn
0x1400025b9  test    rdi, rdi
0x1400025bc  jnz     short loc_1400025E8
0x1400025be  mov     ebp, ecx
0x1400025c0  cmp     [r8], cx
0x1400025c4  jz      short loc_14000257F
0x1400025c6  mov     rax, rsi
0x1400025c9  mov     ebp, 0C000000Dh
0x1400025ce  neg     rax
0x1400025d1  mov     r15, rsi
0x1400025d4  mov     r14, rdi
0x1400025d7  sbb     ecx, ecx
0x1400025d9  and     ecx, 0BFFFFFF8h
0x1400025df  add     ebp, ecx
0x1400025e1  xor     ecx, ecx
0x1400025e3  jmp     loc_140002510
0x1400025e8  lea     rbx, [rdi-1]
0x1400025ec  mov     rcx, rsi; Dest
0x1400025ef  mov     rdx, rbx; Count
0x1400025f2  lea     r9, [rsp+78h+Args]; Args
0x1400025fa  call    cs:__imp__vsnwprintf
0x140002600  xor     ecx, ecx
0x140002602  test    eax, eax
0x140002604  js      short loc_140002616
0x140002606  cdqe
0x140002608  cmp     rax, rbx
0x14000260b  ja      short loc_140002616
0x14000260d  mov     ebp, ecx
0x14000260f  jz      short loc_14000261B
0x140002611  mov     rbx, rax
0x140002614  jmp     short loc_14000261F
0x140002616  mov     ebp, 80000005h
0x14000261b  mov     [rsi+rbx*2], cx
0x14000261f  mov     r14, rdi
0x140002622  lea     r15, [rsi+rbx*2]
0x140002626  sub     r14, rbx
0x140002629  test    ebp, ebp
0x14000262b  js      loc_140002510
0x140002631  bt      r12d, 9
0x140002636  jnb     loc_140002577
0x14000263c  mov     rax, r13
0x14000263f  and     eax, 1
0x140002642  lea     r8, [rax+r14*2]
0x140002646  cmp     r8, 2
0x14000264a  jbe     loc_140002577
0x140002650  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x140002654  movzx   edx, r12b; Val
0x140002658  lea     rcx, [r15+2]; void *
0x14000265c  call    memset_0
0x140002661  jmp     loc_140002577
0x140002666  test    rdi, rdi
0x140002669  jz      loc_14000256F
0x14000266f  lea     r15, [rsi-2]
0x140002673  mov     r14d, 1
0x140002679  lea     r15, [r15+rdi*2]
0x14000267d  mov     [r15], cx
0x140002681  jmp     loc_14000255F
```
