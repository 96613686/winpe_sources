# ParseReplacementString(ushort *,unsigned __int64,_LIST_ENTRY *,_STRING_TOKEN *,ulong,ulong *)

- ea: `0x140019b70`
- end: `0x140019e09`
- name: `?ParseReplacementString@@YAKPEAG_KPEAU_LIST_ENTRY@@PEAU_STRING_TOKEN@@KPEAK@Z`
- size: `665`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, struct _LIST_ENTRY *, struct _STRING_TOKEN *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140019960`

## callees

- `0x1400196f0`
- `0x140019adc`
- `0x140019b70`

## import_xrefs

- `msvcrt!wcstoul` at `0x140019c13`
- `msvcrt!wcstoul` at `0x140019c13`
- `msvcrt!iswspace` at `0x140019c40`
- `msvcrt!iswspace` at `0x140019cc9`
- `msvcrt!iswspace` at `0x140019c40`
- `msvcrt!iswspace` at `0x140019cc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140019dec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140019dec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019dde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019dde`

## pseudocode

```c
__int64 __fastcall ParseReplacementString(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        struct _LIST_ENTRY *a3,
        struct _STRING_TOKEN *a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned __int16 *v6; // r12
  struct _REPLACE_TOKEN *v9; // rdi
  int v11; // ebx
  unsigned int v12; // r15d
  __int64 v13; // r14
  wint_t v14; // bp
  const wchar_t *v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // r12
  wchar_t *v18; // rbp
  int v19; // ebx
  struct _LIST_ENTRY *v20; // rax
  int v21; // ebx
  struct _LIST_ENTRY *v22; // rax
  int v23; // ebx
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  unsigned int v26; // ebx
  struct _LIST_ENTRY *Blink; // rax
  HANDLE ProcessHeap; // rax
  wchar_t *EndPtr; // [rsp+20h] [rbp-48h] BYREF

  v6 = a1;
  EndPtr = 0;
  v9 = NewReplaceToken(0);
  if ( !v9 )
    return 8;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( !(_DWORD)a2 )
  {
LABEL_39:
    if ( *((_DWORD *)v9 + 7) )
    {
      Blink = a3->Blink;
      if ( Blink->Flink != a3 )
LABEL_41:
        __fastfail(3u);
      *(_QWORD *)v9 = a3;
      *((_QWORD *)v9 + 1) = Blink;
      Blink->Flink = (struct _LIST_ENTRY *)v9;
      a3->Blink = (struct _LIST_ENTRY *)v9;
      v12 += *((_DWORD *)v9 + 7);
      v9 = 0;
    }
    v26 = 0;
    *a6 = v12;
    goto LABEL_44;
  }
  do
  {
    v14 = v6[v13];
    if ( v14 == 92 )
    {
      if ( v11 )
        goto LABEL_36;
      ++*((_DWORD *)v9 + 7);
      v13 = (unsigned int)(v13 + 1);
      *((_DWORD *)v9 + 5) = 1;
      if ( (unsigned int)v13 >= a2 )
        goto LABEL_36;
      v24 = v6[v13];
      LOWORD(v24) = v24 - 92;
      if ( (unsigned __int16)v24 > 0x21u )
        goto LABEL_36;
      v25 = 0x280000001LL;
      if ( !_bittest64(&v25, v24) )
        goto LABEL_36;
      goto LABEL_33;
    }
    if ( v14 != 123 )
    {
      if ( v14 == 125 )
      {
        if ( !v11 )
          goto LABEL_36;
        if ( !*((_DWORD *)v9 + 7) )
          goto LABEL_36;
        v15 = &v6[*((unsigned int *)v9 + 6)];
        v16 = wcstoul(v15, &EndPtr, 10);
        v17 = v16;
        if ( v16 >= a5 )
          goto LABEL_36;
        v18 = EndPtr;
        v19 = *((_DWORD *)v9 + 7) - (EndPtr - v15) + 1;
        while ( *v18 != 125 )
        {
          if ( !iswspace(*v18) )
            goto LABEL_36;
          if ( !--v19 )
            goto LABEL_36;
          ++v18;
        }
        *((_DWORD *)v9 + 6) = v17;
        v20 = a3->Blink;
        if ( v20->Flink != a3 )
          goto LABEL_41;
        *(_QWORD *)v9 = a3;
        *((_QWORD *)v9 + 1) = v20;
        v20->Flink = (struct _LIST_ENTRY *)v9;
        a3->Blink = (struct _LIST_ENTRY *)v9;
        v21 = *((_DWORD *)a4 + 2 * v17 + 1);
        v9 = NewReplaceToken(0);
        if ( !v9 )
          goto LABEL_38;
        v6 = a1;
        v12 += v21;
        *((_DWORD *)v9 + 6) = v13 + 1;
        v11 = 0;
        goto LABEL_34;
      }
      if ( v11 && !iswspace(v14) && (unsigned __int16)(v14 - 48) > 9u )
        goto LABEL_36;
LABEL_33:
      ++*((_DWORD *)v9 + 7);
      goto LABEL_34;
    }
    if ( v11 )
      goto LABEL_36;
    if ( *((_DWORD *)v9 + 7) )
    {
      v22 = a3->Blink;
      if ( v22->Flink != a3 )
        goto LABEL_41;
      *(_QWORD *)v9 = a3;
      *((_QWORD *)v9 + 1) = v22;
      v22->Flink = (struct _LIST_ENTRY *)v9;
      a3->Blink = (struct _LIST_ENTRY *)v9;
      v23 = *((_DWORD *)v9 + 7);
      v9 = NewReplaceToken(1);
      if ( !v9 )
      {
LABEL_38:
        v26 = 8;
        goto LABEL_37;
      }
      v12 += v23;
    }
    else
    {
      *((_DWORD *)v9 + 4) = 1;
    }
    v11 = 1;
    *((_DWORD *)v9 + 6) = v13 + 1;
LABEL_34:
    v13 = (unsigned int)(v13 + 1);
  }
  while ( (unsigned int)v13 < (unsigned int)a2 );
  if ( !v11 )
    goto LABEL_39;
LABEL_36:
  v26 = 13;
LABEL_37:
  FreeReplaceTokenList(a3);
LABEL_44:
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
  return v26;
}

```

## disassembly

```asm
0x140019b70  mov     rax, rsp
0x140019b73  mov     [rax+10h], rbx
0x140019b77  mov     [rax+20h], r9
0x140019b7b  mov     [rax+8], rcx
0x140019b7f  push    rbp
0x140019b80  push    rsi
0x140019b81  push    rdi
0x140019b82  push    r12
0x140019b84  push    r13
0x140019b86  push    r14
0x140019b88  push    r15
0x140019b8a  sub     rsp, 30h
0x140019b8e  mov     r12, rcx
0x140019b91  mov     qword ptr [rax-48h], 0
0x140019b99  xor     ecx, ecx; int
0x140019b9b  mov     rsi, r8
0x140019b9e  mov     r13, rdx
0x140019ba1  call    ?NewReplaceToken@@YAPEAU_REPLACE_TOKEN@@H@Z; NewReplaceToken(int)
0x140019ba6  mov     rdi, rax
0x140019ba9  test    rax, rax
0x140019bac  jnz     short loc_140019BB6
0x140019bae  lea     eax, [rdi+8]
0x140019bb1  jmp     loc_140019DF4
0x140019bb6  xor     ebx, ebx
0x140019bb8  xor     r15d, r15d
0x140019bbb  xor     r14d, r14d
0x140019bbe  test    r13d, r13d
0x140019bc1  jz      loc_140019DA2
0x140019bc7  movzx   ebp, word ptr [r12+r14*2]
0x140019bcc  mov     ecx, 7Dh ; '}'
0x140019bd1  cmp     bp, 5Ch ; '\'
0x140019bd5  jz      loc_140019D41
0x140019bdb  cmp     bp, 7Bh ; '{'
0x140019bdf  jz      loc_140019CEA
0x140019be5  cmp     bp, cx
0x140019be8  jnz     loc_140019CBE
0x140019bee  test    ebx, ebx
0x140019bf0  jz      loc_140019D8C
0x140019bf6  cmp     dword ptr [rdi+1Ch], 0
0x140019bfa  jbe     loc_140019D8C
0x140019c00  mov     eax, [rdi+18h]
0x140019c03  lea     r8d, [rcx-73h]; Radix
0x140019c07  lea     rdx, [rsp+68h+EndPtr]; EndPtr
0x140019c0c  lea     rbx, [r12+rax*2]
0x140019c10  mov     rcx, rbx; String
0x140019c13  call    cs:__imp_wcstoul
0x140019c19  mov     r12d, eax
0x140019c1c  cmp     eax, [rsp+68h+arg_20]
0x140019c23  jnb     loc_140019D8C
0x140019c29  mov     rbp, [rsp+68h+EndPtr]
0x140019c2e  mov     rdx, rbp
0x140019c31  sub     rdx, rbx
0x140019c34  mov     ebx, [rdi+1Ch]
0x140019c37  sar     rdx, 1
0x140019c3a  sub     ebx, edx
0x140019c3c  inc     ebx
0x140019c3e  jmp     short loc_140019C5B
0x140019c40  call    cs:__imp_iswspace
0x140019c46  test    eax, eax
0x140019c48  jz      loc_140019D8C
0x140019c4e  add     ebx, 0FFFFFFFFh
0x140019c51  jz      loc_140019D8C
0x140019c57  add     rbp, 2
0x140019c5b  movzx   ecx, word ptr [rbp+0]; C
0x140019c5f  mov     eax, 7Dh ; '}'
0x140019c64  cmp     ax, cx
0x140019c67  jnz     short loc_140019C40
0x140019c69  mov     [rdi+18h], r12d
0x140019c6d  mov     rax, [rsi+8]
0x140019c71  cmp     [rax], rsi
0x140019c74  jnz     loc_140019DB1
0x140019c7a  mov     rcx, [rsp+68h+arg_18]
0x140019c82  mov     [rdi], rsi
0x140019c85  mov     [rdi+8], rax
0x140019c89  mov     [rax], rdi
0x140019c8c  mov     [rsi+8], rdi
0x140019c90  mov     ebx, [rcx+r12*8+4]
0x140019c95  xor     ecx, ecx; int
0x140019c97  call    ?NewReplaceToken@@YAPEAU_REPLACE_TOKEN@@H@Z; NewReplaceToken(int)
0x140019c9c  mov     rdi, rax
0x140019c9f  test    rax, rax
0x140019ca2  jz      loc_140019D9B
0x140019ca8  mov     r12, [rsp+68h+arg_0]
0x140019cad  lea     eax, [r14+1]
0x140019cb1  add     r15d, ebx
0x140019cb4  mov     [rdi+18h], eax
0x140019cb7  xor     ebx, ebx
0x140019cb9  jmp     loc_140019D7C
0x140019cbe  test    ebx, ebx
0x140019cc0  jz      loc_140019D79
0x140019cc6  movzx   ecx, bp; C
0x140019cc9  call    cs:__imp_iswspace
0x140019ccf  test    eax, eax
0x140019cd1  jnz     loc_140019D79
0x140019cd7  sub     bp, 30h ; '0'
0x140019cdb  cmp     bp, 9
0x140019cdf  ja      loc_140019D8C
0x140019ce5  jmp     loc_140019D79
0x140019cea  test    ebx, ebx
0x140019cec  jnz     loc_140019D8C
0x140019cf2  cmp     [rdi+1Ch], ebx
0x140019cf5  jbe     short loc_140019D2C
0x140019cf7  mov     rax, [rsi+8]
0x140019cfb  cmp     [rax], rsi
0x140019cfe  jnz     loc_140019DB1
0x140019d04  mov     [rdi], rsi
0x140019d07  mov     ecx, 1; int
0x140019d0c  mov     [rdi+8], rax
0x140019d10  mov     [rax], rdi
0x140019d13  mov     [rsi+8], rdi
0x140019d17  mov     ebx, [rdi+1Ch]
0x140019d1a  call    ?NewReplaceToken@@YAPEAU_REPLACE_TOKEN@@H@Z; NewReplaceToken(int)
0x140019d1f  mov     rdi, rax
0x140019d22  test    rax, rax
0x140019d25  jz      short loc_140019D9B
0x140019d27  add     r15d, ebx
0x140019d2a  jmp     short loc_140019D33
0x140019d2c  mov     dword ptr [rdi+10h], 1
0x140019d33  lea     eax, [r14+1]
0x140019d37  mov     ebx, 1
0x140019d3c  mov     [rdi+18h], eax
0x140019d3f  jmp     short loc_140019D7C
0x140019d41  test    ebx, ebx
0x140019d43  jnz     short loc_140019D8C
0x140019d45  inc     dword ptr [rdi+1Ch]
0x140019d48  inc     r14d
0x140019d4b  mov     eax, r14d
0x140019d4e  mov     dword ptr [rdi+14h], 1
0x140019d55  cmp     rax, r13
0x140019d58  jnb     short loc_140019D8C
0x140019d5a  movzx   eax, word ptr [r12+r14*2]
0x140019d5f  sub     ax, 5Ch ; '\'
0x140019d63  cmp     ax, 21h ; '!'
0x140019d67  ja      short loc_140019D8C
0x140019d69  mov     rcx, 280000001h
0x140019d73  bt      rcx, rax
0x140019d77  jnb     short loc_140019D8C
0x140019d79  inc     dword ptr [rdi+1Ch]
0x140019d7c  inc     r14d
0x140019d7f  cmp     r14d, r13d
0x140019d82  jb      loc_140019BC7
0x140019d88  test    ebx, ebx
0x140019d8a  jz      short loc_140019DA2
0x140019d8c  mov     ebx, 0Dh
0x140019d91  mov     rcx, rsi; struct _LIST_ENTRY *
0x140019d94  call    ?FreeReplaceTokenList@@YAXPEAU_LIST_ENTRY@@@Z; FreeReplaceTokenList(_LIST_ENTRY *)
0x140019d99  jmp     short loc_140019DD9
0x140019d9b  mov     ebx, 8
0x140019da0  jmp     short loc_140019D91
0x140019da2  cmp     dword ptr [rdi+1Ch], 0
0x140019da6  jbe     short loc_140019DCC
0x140019da8  mov     rax, [rsi+8]
0x140019dac  cmp     [rax], rsi
0x140019daf  jz      short loc_140019DB8
0x140019db1  mov     ecx, 3
0x140019db6  int     29h; Win8: RtlFailFast(ecx)
0x140019db8  mov     [rdi], rsi
0x140019dbb  mov     [rdi+8], rax
0x140019dbf  mov     [rax], rdi
0x140019dc2  mov     [rsi+8], rdi
0x140019dc6  add     r15d, [rdi+1Ch]
0x140019dca  xor     edi, edi
0x140019dcc  mov     rcx, [rsp+68h+arg_28]
0x140019dd4  xor     ebx, ebx
0x140019dd6  mov     [rcx], r15d
0x140019dd9  test    rdi, rdi
0x140019ddc  jz      short loc_140019DF2
0x140019dde  call    cs:__imp_GetProcessHeap
0x140019de4  mov     r8, rdi; lpMem
0x140019de7  xor     edx, edx; dwFlags
0x140019de9  mov     rcx, rax; hHeap
0x140019dec  call    cs:__imp_HeapFree
0x140019df2  mov     eax, ebx
0x140019df4  mov     rbx, [rsp+68h+arg_8]
0x140019df9  add     rsp, 30h
0x140019dfd  pop     r15
0x140019dff  pop     r14
0x140019e01  pop     r13
0x140019e03  pop     r12
0x140019e05  pop     rdi
0x140019e06  pop     rsi
0x140019e07  pop     rbp
0x140019e08  retn
```
