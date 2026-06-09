# LdrpAccessResourceDataNoMultipleLanguage

- ea: `0x1400ff518`
- end: `0x1400ff735`
- name: `LdrpAccessResourceDataNoMultipleLanguage`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400ff484`

## callees

- `0x1400d645c`
- `0x1400d64a4`
- `0x1400d6538`
- `0x1400d724c`
- `0x1400e3938`
- `0x1400ff518`

## pseudocode

```c
__int64 __fastcall LdrpAccessResourceDataNoMultipleLanguage(
        __int64 a1,
        unsigned int *a2,
        unsigned __int64 *a3,
        _DWORD *a4)
{
  __int64 v6; // rbx
  __int64 v7; // r13
  __int64 result; // rax
  unsigned __int64 v9; // rsi
  __int64 v10; // r14
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // r11
  __int16 v14; // ax
  int v15; // r8d
  __int64 v16; // rax
  unsigned int v17; // r8d
  __int64 v18; // r11
  __int64 v19; // r15
  __int64 v20; // rax
  __int64 v21; // r11
  __int64 v22; // rax
  unsigned int v23; // r8d
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  unsigned int v27[12]; // [rsp+28h] [rbp-30h] BYREF

  v6 = a1;
  v7 = RtlImageDirectoryEntryToData(a1, (int)a2, 2, (int)v27);
  if ( !v7 )
    return 3221225609LL;
  *(_QWORD *)v27 = 0;
  result = LdrpGetImageSize(v6, v27);
  if ( (int)result >= 0 )
  {
    v9 = v6 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (unsigned __int64)a2 < (v6 & 0xFFFFFFFFFFFFFFFCuLL) )
      return 3221225595LL;
    if ( a2 + 4 < a2 )
      return 3221225595LL;
    v10 = *(_QWORD *)v27;
    if ( *(_QWORD *)v27 && (unsigned __int64)(a2 + 4) > v9 + *(_QWORD *)v27 )
    {
      return 3221225595LL;
    }
    else
    {
      v11 = 0;
      if ( (v6 & 2) != 0 || (v6 & 1) != 0 )
      {
        if ( (v6 & 1) != 0 )
          v11 = 1;
        v6 &= 0xFFFFFFFFFFFFFFFCuLL;
      }
      if ( v11 == 1 )
      {
        v12 = RtlImageNtHeader(v6);
        v13 = v12;
        if ( !v12 )
          return 3221225609LL;
        v14 = *(_WORD *)(v12 + 24);
        if ( v14 == 267 )
        {
          v15 = *(_DWORD *)(v13 + 136);
        }
        else if ( v14 == 523 )
        {
          v15 = *(_DWORD *)(v13 + 152);
        }
        else
        {
          v15 = 0;
        }
        if ( !v15 )
          return 3221225609LL;
        v16 = RtlSectionTableFromVirtualAddress(v13);
        if ( !v16 )
          return 3221225609LL;
        v19 = v6 + v17 - v7;
        _mm_lfence();
        if ( *a2 <= *(_DWORD *)(v16 + 8) )
        {
          v24 = v6 + v17 - v7;
        }
        else
        {
          v27[0] = *(_DWORD *)(v16 + 12);
          v20 = RtlSectionTableFromVirtualAddress(v18);
          if ( !v20 )
            return 3221225609LL;
          v22 = RtlAddressInSectionTable(v21, v6, *(unsigned int *)(v20 + 12));
          v24 = v7 + v19 + v23 - (unsigned __int64)v27[0] - v22;
        }
      }
      else
      {
        v24 = 0;
      }
      if ( a3 )
      {
        v25 = v6 + *a2 - v24;
        if ( v25 < v9 )
          return 3221225595LL;
        v26 = v25 + a2[1];
        if ( v26 < v25 || v10 && v26 > v9 + v10 )
          return 3221225595LL;
        *a3 = v25;
      }
      if ( a4 )
        *a4 = a2[1];
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400ff518  mov     rax, rsp
0x1400ff51b  mov     [rax+8], rbx
0x1400ff51f  mov     [rax+10h], rsi
0x1400ff523  mov     [rax+18h], r8
0x1400ff527  push    rdi
0x1400ff528  push    r12
0x1400ff52a  push    r13
0x1400ff52c  push    r14
0x1400ff52e  push    r15
0x1400ff530  sub     rsp, 30h
0x1400ff534  mov     r12, r9
0x1400ff537  mov     rdi, rdx
0x1400ff53a  mov     rbx, rcx
0x1400ff53d  mov     r8d, 2
0x1400ff543  lea     r9, [rax-30h]
0x1400ff547  call    RtlImageDirectoryEntryToData
0x1400ff54c  mov     r13, rax
0x1400ff54f  test    rax, rax
0x1400ff552  jnz     short loc_1400FF55E
0x1400ff554  mov     eax, 0C0000089h
0x1400ff559  jmp     loc_1400FF71C
0x1400ff55e  mov     qword ptr [rsp+58h+var_30], 0
0x1400ff567  lea     rdx, [rsp+58h+var_30]
0x1400ff56c  mov     rcx, rbx
0x1400ff56f  call    LdrpGetImageSize
0x1400ff574  mov     [rsp+58h+var_38], eax
0x1400ff578  test    eax, eax
0x1400ff57a  js      loc_1400FF71C
0x1400ff580  mov     rsi, rbx
0x1400ff583  and     rsi, 0FFFFFFFFFFFFFFFCh
0x1400ff587  cmp     rdi, rsi
0x1400ff58a  jb      loc_1400FF70D
0x1400ff590  lea     rcx, [rdi+10h]
0x1400ff594  cmp     rcx, rdi
0x1400ff597  jb      loc_1400FF70D
0x1400ff59d  mov     r14, qword ptr [rsp+58h+var_30]
0x1400ff5a2  test    r14, r14
0x1400ff5a5  jz      short loc_1400FF5B4
0x1400ff5a7  lea     rax, [rsi+r14]
0x1400ff5ab  cmp     rcx, rax
0x1400ff5ae  ja      loc_1400FF70D
0x1400ff5b4  xor     eax, eax
0x1400ff5b6  mov     [rsp+58h+var_34], eax
0x1400ff5ba  mov     rcx, rbx
0x1400ff5bd  lea     edx, [rax+1]
0x1400ff5c0  and     rcx, rdx
0x1400ff5c3  test    bl, 2
0x1400ff5c6  jnz     short loc_1400FF5CD
0x1400ff5c8  test    rcx, rcx
0x1400ff5cb  jz      short loc_1400FF5DA
0x1400ff5cd  test    rcx, rcx
0x1400ff5d0  cmovnz  eax, edx
0x1400ff5d3  mov     [rsp+58h+var_34], eax
0x1400ff5d7  mov     rbx, rsi
0x1400ff5da  cmp     eax, edx
0x1400ff5dc  jnz     loc_1400FF6BB
0x1400ff5e2  mov     rcx, rbx
0x1400ff5e5  call    RtlImageNtHeader
0x1400ff5ea  mov     r11, rax
0x1400ff5ed  test    rax, rax
0x1400ff5f0  jnz     short loc_1400FF600
0x1400ff5f2  mov     eax, 0C0000089h
0x1400ff5f7  mov     [rsp+58h+var_38], eax
0x1400ff5fb  jmp     loc_1400FF71C
0x1400ff600  movzx   eax, word ptr [rax+18h]
0x1400ff604  mov     ecx, 10Bh
0x1400ff609  cmp     ax, cx
0x1400ff60c  jnz     short loc_1400FF617
0x1400ff60e  mov     r8d, [r11+88h]
0x1400ff615  jmp     short loc_1400FF62D
0x1400ff617  mov     ecx, 20Bh
0x1400ff61c  cmp     ax, cx
0x1400ff61f  jnz     short loc_1400FF62A
0x1400ff621  mov     r8d, [r11+98h]
0x1400ff628  jmp     short loc_1400FF62D
0x1400ff62a  xor     r8d, r8d
0x1400ff62d  test    r8d, r8d
0x1400ff630  jnz     short loc_1400FF640
0x1400ff632  mov     eax, 0C0000089h
0x1400ff637  mov     [rsp+58h+var_38], eax
0x1400ff63b  jmp     loc_1400FF71C
0x1400ff640  mov     rcx, r11
0x1400ff643  call    RtlSectionTableFromVirtualAddress
0x1400ff648  test    rax, rax
0x1400ff64b  jnz     short loc_1400FF65B
0x1400ff64d  mov     eax, 0C0000089h
0x1400ff652  mov     [rsp+58h+var_38], eax
0x1400ff656  jmp     loc_1400FF71C
0x1400ff65b  mov     r15d, r8d
0x1400ff65e  sub     r15, r13
0x1400ff661  add     r15, rbx
0x1400ff664  lfence
0x1400ff667  mov     r8d, [rdi]
0x1400ff66a  cmp     r8d, [rax+8]
0x1400ff66e  jbe     short loc_1400FF6B6
0x1400ff670  mov     eax, [rax+0Ch]
0x1400ff673  mov     [rsp+58h+var_30], eax
0x1400ff677  mov     rcx, r11
0x1400ff67a  call    RtlSectionTableFromVirtualAddress
0x1400ff67f  test    rax, rax
0x1400ff682  jnz     short loc_1400FF692
0x1400ff684  mov     eax, 0C0000089h
0x1400ff689  mov     [rsp+58h+var_38], eax
0x1400ff68d  jmp     loc_1400FF71C
0x1400ff692  mov     r8d, [rax+0Ch]
0x1400ff696  mov     rdx, rbx
0x1400ff699  mov     rcx, r11
0x1400ff69c  call    RtlAddressInSectionTable
0x1400ff6a1  mov     edx, r8d
0x1400ff6a4  mov     ecx, [rsp+58h+var_30]
0x1400ff6a8  sub     rdx, rcx
0x1400ff6ab  add     rdx, r15
0x1400ff6ae  add     rdx, r13
0x1400ff6b1  sub     rdx, rax
0x1400ff6b4  jmp     short loc_1400FF6BD
0x1400ff6b6  mov     rdx, r15
0x1400ff6b9  jmp     short loc_1400FF6BD
0x1400ff6bb  xor     edx, edx
0x1400ff6bd  mov     r8, [rsp+58h+arg_10]
0x1400ff6c2  test    r8, r8
0x1400ff6c5  jz      short loc_1400FF6FD
0x1400ff6c7  mov     ecx, [rdi]
0x1400ff6c9  sub     rcx, rdx
0x1400ff6cc  add     rcx, rbx
0x1400ff6cf  cmp     rcx, rsi
0x1400ff6d2  jb      short loc_1400FF6F2
0x1400ff6d4  mov     edx, [rdi+4]
0x1400ff6d7  add     rdx, rcx
0x1400ff6da  cmp     rdx, rcx
0x1400ff6dd  jb      short loc_1400FF6F2
0x1400ff6df  test    r14, r14
0x1400ff6e2  jz      short loc_1400FF6ED
0x1400ff6e4  lea     rax, [rsi+r14]
0x1400ff6e8  cmp     rdx, rax
0x1400ff6eb  ja      short loc_1400FF6F2
0x1400ff6ed  mov     [r8], rcx
0x1400ff6f0  jmp     short loc_1400FF6FD
0x1400ff6f2  mov     eax, 0C000007Bh
0x1400ff6f7  mov     [rsp+58h+var_38], eax
0x1400ff6fb  jmp     short loc_1400FF71C
0x1400ff6fd  test    r12, r12
0x1400ff700  jz      short loc_1400FF709
0x1400ff702  mov     eax, [rdi+4]
0x1400ff705  mov     [r12], eax
0x1400ff709  xor     eax, eax
0x1400ff70b  jmp     short loc_1400FF71C
0x1400ff70d  mov     eax, 0C000007Bh
0x1400ff712  mov     [rsp+58h+var_38], eax
0x1400ff716  jmp     short loc_1400FF71C
0x1400ff718  mov     [rsp+58h+var_38], eax
0x1400ff71c  mov     rbx, [rsp+58h+arg_0]
0x1400ff721  mov     rsi, [rsp+58h+arg_8]
0x1400ff726  add     rsp, 30h
0x1400ff72a  pop     r15
0x1400ff72c  pop     r14
0x1400ff72e  pop     r13
0x1400ff730  pop     r12
0x1400ff732  pop     rdi
0x1400ff733  retn
```
