# pSetupAppendPath

- ea: `0x18000cba0`
- end: `0x18000cf21`
- name: `pSetupAppendPath`
- size: `897`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000cab0`
- `0x180017708`

## callees

- `0x18000cba0`
- `0x180010384`
- `0x1800162c0`
- `0x1800162dc`
- `0x1800180b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ce84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cee0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ce84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cee0`

## pseudocode

```c
__int64 __fastcall pSetupAppendPath(const wchar_t *a1, const wchar_t *a2, __int64 *a3)
{
  const wchar_t *v4; // rdi
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r13
  __int64 v9; // r12
  _WORD *v10; // r14
  __int64 v12; // rcx
  _WORD *v13; // rax
  __int64 v14; // rdx
  DWORD v15; // edi
  __int64 v16; // rcx
  int v17; // edx
  __int16 v18; // dx
  HRESULT v19; // eax
  _WORD *v20; // rax
  __int64 v21; // rax
  __int64 *v22; // [rsp+A0h] [rbp+18h]

  v22 = a3;
  v4 = a1;
  if ( !a1 && !a2 )
  {
    v20 = HeapAlloc(hHeap, 0, 2u);
    *v22 = (__int64)v20;
    if ( v20 )
    {
      *v20 = 0;
      return 1;
    }
    return 0;
  }
  if ( !a1 )
  {
    a1 = a2;
    goto LABEL_56;
  }
  if ( !a2 )
  {
LABEL_56:
    v21 = pSetupDuplicateString(a1);
    *v22 = v21;
    return v21 != 0;
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = -1;
  do
    ++v7;
  while ( v4[v7] );
  v8 = (unsigned int)(v7 + v6 + 2);
  v9 = v8;
  if ( (unsigned __int64)(2 * v8) <= 0xFFFFFFFF )
  {
    v10 = HeapAlloc(hHeap, 0, (unsigned int)(2 * v8));
    a3 = v22;
  }
  else
  {
    v10 = 0;
  }
  if ( !v10 )
  {
    *a3 = 0;
    return 0;
  }
  v12 = 2147483646;
  if ( (unsigned __int64)(v8 - 1) > 0x7FFFFFFE )
  {
    if ( (_DWORD)v8 )
      *v10 = 0;
  }
  else
  {
    v13 = v10;
    v14 = 0;
    while ( v9 )
    {
      if ( !v12 || !*v4 )
        goto LABEL_17;
      *v13++ = *v4++;
      --v9;
      --v12;
      ++v14;
    }
    --v13;
LABEL_17:
    *v13 = 0;
    a3 = v22;
  }
  v15 = 0;
  v16 = -1;
  do
    ++v16;
  while ( v10[v16] );
  do
    ++v5;
  while ( a2[v5] );
  if ( (_DWORD)v16 )
  {
    v18 = v10[(unsigned int)v16 - 1];
    if ( v18 == 92 || v18 == 47 )
      LODWORD(v16) = v16 - 1;
  }
  if ( *a2 == 92 || *a2 == 47 )
  {
    v17 = 1;
    LODWORD(v5) = v5 - 1;
  }
  else
  {
    v17 = 0;
  }
  if ( (int)v16 + (int)v5 + 2 <= (unsigned int)v8 )
  {
    if ( !v17 )
    {
      if ( (unsigned int)v16 >= (unsigned int)v8 )
        goto LABEL_46;
      v10[(unsigned int)v16] = 92;
      LODWORD(v16) = v16 + 1;
    }
    if ( (unsigned int)v16 < (unsigned int)v8 )
    {
      v19 = StringCchCopyW(&v10[(unsigned int)v16], (unsigned int)(v8 - v16), a2);
      a3 = v22;
      if ( v19 < 0 )
        v15 = (unsigned __int16)v19;
LABEL_47:
      if ( (_DWORD)v8 )
        v10[(unsigned int)(v8 - 1)] = 0;
      if ( !v15 )
        goto LABEL_49;
      goto LABEL_26;
    }
LABEL_46:
    v15 = 206;
    goto LABEL_47;
  }
  v15 = 206;
LABEL_26:
  SetLastError(v15);
  a3 = v22;
LABEL_49:
  if ( v15 )
  {
    HeapFree(hHeap, 0, v10);
    v10 = 0;
    a3 = v22;
  }
  *a3 = (__int64)v10;
  return v15 == 0;
}

```

## disassembly

```asm
0x18000cba0  mov     [rsp+arg_8], rbx
0x18000cba5  mov     [rsp+arg_18], rsi
0x18000cbaa  mov     [rsp+arg_10], r8
0x18000cbaf  push    rdi
0x18000cbb0  push    r12
0x18000cbb2  push    r13
0x18000cbb4  push    r14
0x18000cbb6  push    r15
0x18000cbb8  sub     rsp, 60h
0x18000cbbc  mov     rbx, rdx
0x18000cbbf  mov     rdi, rcx
0x18000cbc2  test    rcx, rcx
0x18000cbc5  jz      loc_18000CE6C
0x18000cbcb  test    rdi, rdi
0x18000cbce  jz      loc_18000CEAF
0x18000cbd4  test    rbx, rbx
0x18000cbd7  jz      loc_18000CEB2
0x18000cbdd  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000cbe4  mov     rax, rsi
0x18000cbe7  nop     word ptr [rax+rax+00000000h]
0x18000cbf0  lea     rax, [rax+1]
0x18000cbf4  cmp     word ptr [rdx+rax*2], 0
0x18000cbf9  jnz     short loc_18000CBF0
0x18000cbfb  mov     rcx, rsi
0x18000cbfe  xchg    ax, ax
0x18000cc00  inc     rcx
0x18000cc03  cmp     word ptr [rdi+rcx*2], 0
0x18000cc08  jnz     short loc_18000CC00
0x18000cc0a  lea     r13d, [rax+2]
0x18000cc0e  add     r13d, ecx
0x18000cc11  mov     r12d, r13d
0x18000cc14  lea     rax, ds:0[r13*2]
0x18000cc1c  mov     r9d, 0FFFFFFFFh
0x18000cc22  cmp     rax, r9
0x18000cc25  jbe     loc_18000CED4
0x18000cc2b  xor     r15d, r15d
0x18000cc2e  mov     r14d, r15d
0x18000cc31  mov     [rsp+88h+arg_0], r14
0x18000cc39  test    r14, r14
0x18000cc3c  jnz     short loc_18000CC5D
0x18000cc3e  mov     [r8], r15
0x18000cc41  xor     eax, eax
0x18000cc43  lea     r11, [rsp+88h+var_28]
0x18000cc48  mov     rbx, [r11+38h]
0x18000cc4c  mov     rsi, [r11+48h]
0x18000cc50  mov     rsp, r11
0x18000cc53  pop     r15
0x18000cc55  pop     r14
0x18000cc57  pop     r13
0x18000cc59  pop     r12
0x18000cc5b  pop     rdi
0x18000cc5c  retn
0x18000cc5d  lea     rax, [r13-1]
0x18000cc61  mov     ecx, 7FFFFFFEh
0x18000cc66  cmp     rax, rcx
0x18000cc69  ja      loc_18000CD84
0x18000cc6f  mov     [rsp+88h+var_38], rcx
0x18000cc74  mov     [rsp+88h+var_48], rdi
0x18000cc79  mov     [rsp+88h+var_40], r12
0x18000cc7e  mov     rax, r14
0x18000cc81  mov     [rsp+88h+var_58], rax
0x18000cc86  mov     rdx, r15
0x18000cc89  mov     [rsp+88h+var_50], rdx
0x18000cc8e  test    r12, r12
0x18000cc91  jnz     loc_18000CD42
0x18000cc97  sub     rax, 2
0x18000cc9b  mov     [rsp+88h+var_58], rax
0x18000cca0  dec     rdx
0x18000cca3  mov     [rsp+88h+var_50], rdx
0x18000cca8  mov     [rax], r15w
0x18000ccac  mov     r8, [rsp+88h+arg_10]
0x18000ccb4  mov     [rsp+88h+var_68], r15d
0x18000ccb9  mov     [rsp+88h+var_64], r15d
0x18000ccbe  mov     edi, r15d
0x18000ccc1  mov     rcx, rsi
0x18000ccc4  inc     rcx
0x18000ccc7  cmp     word ptr [r14+rcx*2], 0
0x18000cccd  jnz     short loc_18000CCC4
0x18000cccf  mov     [rsp+88h+var_68], ecx
0x18000ccd3  inc     rsi
0x18000ccd6  cmp     word ptr [rbx+rsi*2], 0
0x18000ccdb  jnz     short loc_18000CCD3
0x18000ccdd  mov     [rsp+88h+var_64], esi
0x18000cce1  test    ecx, ecx
0x18000cce3  jnz     loc_18000CD96
0x18000cce9  movzx   eax, word ptr [rbx]
0x18000ccec  cmp     ax, 5Ch ; '\'
0x18000ccf0  jnz     loc_18000CDBA
0x18000ccf6  mov     edx, 1
0x18000ccfb  add     esi, r9d
0x18000ccfe  mov     [rsp+88h+var_64], esi
0x18000cd02  lea     eax, [rsi+2]
0x18000cd05  add     eax, ecx
0x18000cd07  cmp     eax, r13d
0x18000cd0a  jbe     loc_18000CDCC
0x18000cd10  mov     edi, 0CEh
0x18000cd15  mov     ecx, edi; dwErrCode
0x18000cd17  call    cs:__imp_SetLastError
0x18000cd1d  mov     r8, [rsp+88h+arg_10]
0x18000cd25  jmp     loc_18000CE2C
0x18000cd2a  test    edi, edi
0x18000cd2c  jz      loc_18000CE2C
0x18000cd32  jmp     short loc_18000CD15
0x18000cd34  test    r12, r12
0x18000cd37  jnz     loc_18000CCA8
0x18000cd3d  jmp     loc_18000CC97
0x18000cd42  test    rcx, rcx
0x18000cd45  jz      short loc_18000CD34
0x18000cd47  movzx   r8d, word ptr [rdi]
0x18000cd4b  test    r8w, r8w
0x18000cd4f  jz      short loc_18000CD34
0x18000cd51  mov     [rax], r8w
0x18000cd55  add     rax, 2
0x18000cd59  mov     [rsp+88h+var_58], rax
0x18000cd5e  add     rdi, 2
0x18000cd62  mov     [rsp+88h+var_48], rdi
0x18000cd67  dec     r12
0x18000cd6a  mov     [rsp+88h+var_40], r12
0x18000cd6f  dec     rcx
0x18000cd72  mov     [rsp+88h+var_38], rcx
0x18000cd77  inc     rdx
0x18000cd7a  mov     [rsp+88h+var_50], rdx
0x18000cd7f  jmp     loc_18000CC8E
0x18000cd84  test    r13d, r13d
0x18000cd87  jz      loc_18000CCB4
0x18000cd8d  mov     [r14], r15w
0x18000cd91  jmp     loc_18000CCB4
0x18000cd96  mov     eax, ecx
0x18000cd98  movzx   edx, word ptr [r14+rax*2-2]
0x18000cd9e  cmp     dx, 5Ch ; '\'
0x18000cda2  jz      short loc_18000CDAE
0x18000cda4  cmp     dx, 2Fh ; '/'
0x18000cda8  jnz     loc_18000CCE9
0x18000cdae  add     ecx, r9d
0x18000cdb1  mov     [rsp+88h+var_68], ecx
0x18000cdb5  jmp     loc_18000CCE9
0x18000cdba  cmp     ax, 2Fh ; '/'
0x18000cdbe  jz      loc_18000CCF6
0x18000cdc4  mov     edx, r15d
0x18000cdc7  jmp     loc_18000CD02
0x18000cdcc  test    edx, edx
0x18000cdce  jnz     short loc_18000CDE7
0x18000cdd0  cmp     ecx, r13d
0x18000cdd3  jnb     short loc_18000CE10
0x18000cdd5  mov     eax, ecx
0x18000cdd7  mov     edx, 5Ch ; '\'
0x18000cddc  mov     [r14+rax*2], dx
0x18000cde1  inc     ecx
0x18000cde3  mov     [rsp+88h+var_68], ecx
0x18000cde7  cmp     ecx, r13d
0x18000cdea  jnb     short loc_18000CE10
0x18000cdec  mov     edx, r13d
0x18000cdef  sub     edx, ecx; cchDest
0x18000cdf1  mov     eax, ecx
0x18000cdf3  lea     rcx, [r14+rax*2]; pszDest
0x18000cdf7  mov     r8, rbx; pszSrc
0x18000cdfa  call    StringCchCopyW
0x18000cdff  mov     r8, [rsp+88h+arg_10]
0x18000ce07  test    eax, eax
0x18000ce09  jns     short loc_18000CE15
0x18000ce0b  movzx   edi, ax
0x18000ce0e  jmp     short loc_18000CE15
0x18000ce10  mov     edi, 0CEh
0x18000ce15  test    r13d, r13d
0x18000ce18  jz      loc_18000CD2A
0x18000ce1e  lea     eax, [r13-1]
0x18000ce22  mov     [r14+rax*2], r15w
0x18000ce27  jmp     loc_18000CD2A
0x18000ce2c  mov     ebx, r15d
0x18000ce2f  test    edi, edi
0x18000ce31  setz    bl
0x18000ce34  mov     [rsp+88h+var_60], ebx
0x18000ce38  jmp     short loc_18000CE5A
0x18000ce3a  mov     ecx, eax
0x18000ce3c  call    pSetupExceptionHandler
0x18000ce41  xor     ebx, ebx
0x18000ce43  mov     [rsp+88h+var_60], ebx
0x18000ce47  xor     r15d, r15d
0x18000ce4a  mov     r14, [rsp+88h+arg_0]
0x18000ce52  mov     r8, [rsp+88h+arg_10]
0x18000ce5a  test    ebx, ebx
0x18000ce5c  jz      loc_18000CEFF
0x18000ce62  mov     [r8], r14
0x18000ce65  mov     eax, ebx
0x18000ce67  jmp     loc_18000CC43
0x18000ce6c  test    rbx, rbx
0x18000ce6f  jnz     loc_18000CBCB
0x18000ce75  xor     edx, edx; dwFlags
0x18000ce77  mov     r8d, 2; dwBytes
0x18000ce7d  mov     rcx, cs:hHeap; hHeap
0x18000ce84  call    cs:__imp_HeapAlloc
0x18000ce8a  mov     rcx, [rsp+88h+arg_10]
0x18000ce92  mov     [rcx], rax
0x18000ce95  test    rax, rax
0x18000ce98  jz      loc_18000CC41
0x18000ce9e  xor     r15d, r15d
0x18000cea1  mov     [rax], r15w
0x18000cea5  mov     eax, 1
0x18000ceaa  jmp     loc_18000CC43
0x18000ceaf  mov     rcx, rbx; pszSrc
0x18000ceb2  call    pSetupDuplicateString
0x18000ceb7  mov     rcx, [rsp+88h+arg_10]
0x18000cebf  mov     [rcx], rax
0x18000cec2  xor     r15d, r15d
0x18000cec5  test    rax, rax
0x18000cec8  setnz   r15b
0x18000cecc  mov     eax, r15d
0x18000cecf  jmp     loc_18000CC43
0x18000ced4  mov     r8d, eax; dwBytes
0x18000ced7  xor     edx, edx; dwFlags
0x18000ced9  mov     rcx, cs:hHeap; hHeap
0x18000cee0  call    cs:__imp_HeapAlloc
0x18000cee6  mov     r14, rax
0x18000cee9  xor     r15d, r15d
0x18000ceec  mov     r8, [rsp+88h+arg_10]
0x18000cef4  mov     r9d, 0FFFFFFFFh
0x18000cefa  jmp     loc_18000CC31
0x18000ceff  mov     r8, r14; lpMem
0x18000cf02  xor     edx, edx; dwFlags
0x18000cf04  mov     rcx, cs:hHeap; hHeap
0x18000cf0b  call    cs:__imp_HeapFree
0x18000cf11  mov     r14, r15
0x18000cf14  mov     r8, [rsp+88h+arg_10]
0x18000cf1c  jmp     loc_18000CE62
0x180018e30  push    rbp
0x180018e32  sub     rsp, 20h
0x180018e36  mov     rbp, rdx
0x180018e39  mov     rcx, [rcx]
0x180018e3c  mov     ecx, [rcx]
0x180018e3e  call    pSetupExceptionFilter
0x180018e43  nop
0x180018e44  add     rsp, 20h
0x180018e48  pop     rbp
0x180018e49  retn
```
