# _write_nolock

- ea: `0x100421878`
- end: `0x100421b7e`
- name: `_write_nolock`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x100421754`

## callees

- `0x10041b270`
- `0x10041bf74`
- `0x10041c158`
- `0x100420f38`
- `0x1004213b4`
- `0x1004214bc`
- `0x1004215dc`
- `0x100421878`
- `0x100421c84`
- `0x1004222dc`
- `0x1004222e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100421a1f`
- `KERNEL32!GetLastError` at `0x100421adf`
- `KERNEL32!GetLastError` at `0x100421a1f`
- `KERNEL32!GetLastError` at `0x100421adf`
- `KERNEL32!WriteFile` at `0x100421ad5`
- `KERNEL32!WriteFile` at `0x100421ad5`
- `KERNEL32!GetConsoleMode` at `0x100421994`
- `KERNEL32!GetConsoleMode` at `0x100421994`

## pseudocode

```c
__int64 __fastcall write_nolock(unsigned int a1, _BYTE *a2, unsigned int a3, __int64 a4)
{
  int v4; // edi
  __int64 v5; // r14
  __int64 v10; // rax
  __int64 v11; // r12
  __int64 v12; // r13
  __int64 v13; // rcx
  wchar_t *v14; // r12
  wchar_t *v15; // r15
  DWORD v16; // r14d
  __int64 v17; // rax
  __int64 v18; // xmm0_8
  __int64 v19; // rcx
  void *v20; // rcx
  char v21; // [rsp+30h] [rbp-48h]
  wchar_t v22; // [rsp+30h] [rbp-48h]
  DWORD NumberOfBytesWritten[2]; // [rsp+38h] [rbp-40h] BYREF
  int v24; // [rsp+40h] [rbp-38h]
  __int64 v25; // [rsp+48h] [rbp-30h]
  DWORD Mode; // [rsp+58h] [rbp-20h] BYREF
  __int64 v27; // [rsp+60h] [rbp-18h]

  v4 = 0;
  v5 = a3;
  if ( !a3 )
    return 0;
  if ( !a2
    || (v10 = a1 & 0x3F,
        v11 = (__int64)(int)a1 >> 6,
        v27 = v11,
        v12 = 9 * v10,
        v13 = _pioinfo[v11],
        v21 = *(_BYTE *)(v13 + 72 * v10 + 57),
        (unsigned __int8)(v21 - 1) <= 1u)
    && (a3 & 1) != 0 )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(v13 + 72 * v10 + 56) & 0x20) != 0 )
    lseeki64_nolock_internal(a1, 0, 2);
  v25 = 0;
  if ( !isatty(a1) || *(char *)(_pioinfo[v11] + 8 * v12 + 56) >= 0 )
    goto LABEL_30;
  if ( !*(_BYTE *)(a4 + 40) )
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)a4);
  if ( !*(_QWORD *)(*(_QWORD *)(a4 + 24) + 312LL) && !*(_BYTE *)(_pioinfo[v11] + 8 * v12 + 57)
    || !GetConsoleMode(*(HANDLE *)(_pioinfo[v11] + 8 * v12 + 40), &Mode) )
  {
LABEL_30:
    v19 = _pioinfo[v11];
    if ( *(char *)(v19 + 8 * v12 + 56) >= 0 )
    {
      v20 = *(void **)(v19 + 8 * v12 + 40);
      *(_QWORD *)NumberOfBytesWritten = 0;
      v24 = 0;
      if ( !WriteFile(v20, a2, v5, &NumberOfBytesWritten[1], 0) )
        NumberOfBytesWritten[0] = GetLastError();
      v4 = v24;
LABEL_40:
      v18 = *(_QWORD *)NumberOfBytesWritten;
      goto LABEL_41;
    }
    if ( v21 )
    {
      if ( v21 == 1 )
      {
        v17 = write_text_utf8_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v5);
      }
      else
      {
        if ( v21 != 2 )
          goto LABEL_42;
        v17 = write_text_utf16le_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v5);
      }
    }
    else
    {
      v17 = write_text_ansi_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v5);
    }
LABEL_29:
    v18 = *(_QWORD *)v17;
    v4 = *(_DWORD *)(v17 + 8);
LABEL_41:
    v25 = v18;
    goto LABEL_42;
  }
  if ( !v21 )
  {
    v17 = write_double_translated_ansi_nolock((__int64)NumberOfBytesWritten, a1, a2, v5, a4);
    goto LABEL_29;
  }
  if ( (unsigned int)(v21 - 1) <= 1 )
  {
    v14 = (wchar_t *)&a2[v5];
    *(_QWORD *)NumberOfBytesWritten = 0;
    v15 = (wchar_t *)a2;
    if ( a2 < &a2[v5] )
    {
      v16 = NumberOfBytesWritten[1];
      while ( 1 )
      {
        v22 = *v15;
        if ( putwch_nolock(*v15) != v22 )
          break;
        v16 += 2;
        NumberOfBytesWritten[1] = v16;
        if ( v22 == 10 )
        {
          if ( putwch_nolock(0xDu) != 13 )
            break;
          NumberOfBytesWritten[1] = ++v16;
          ++v4;
        }
        if ( ++v15 >= v14 )
          goto LABEL_27;
      }
      NumberOfBytesWritten[0] = GetLastError();
    }
LABEL_27:
    v11 = v27;
    goto LABEL_40;
  }
LABEL_42:
  if ( HIDWORD(v25) )
    return (unsigned int)(HIDWORD(v25) - v4);
  if ( (_DWORD)v25 )
  {
    if ( (_DWORD)v25 == 5 )
    {
      *(_BYTE *)(a4 + 48) = 1;
      *(_DWORD *)(a4 + 44) = 9;
      *(_BYTE *)(a4 + 56) = 1;
      *(_DWORD *)(a4 + 52) = 5;
    }
    else
    {
      _acrt_errno_map_os_error_ptd((unsigned int)v25, a4);
    }
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(_pioinfo[v11] + 8 * v12 + 56) & 0x40) == 0 || *a2 != 26 )
  {
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 28;
    *(_BYTE *)(a4 + 56) = 1;
    return 0xFFFFFFFFLL;
  }
  return 0;
}

```

## disassembly

```asm
0x100421878  push    rbp
0x10042187a  push    rbx
0x10042187b  push    rsi
0x10042187c  push    rdi
0x10042187d  push    r12
0x10042187f  push    r13
0x100421881  push    r14
0x100421883  push    r15
0x100421885  mov     rbp, rsp
0x100421888  sub     rsp, 78h
0x10042188c  xor     edi, edi
0x10042188e  mov     r14d, r8d
0x100421891  movsxd  r15, ecx
0x100421894  mov     rbx, r9
0x100421897  mov     rsi, rdx
0x10042189a  test    r8d, r8d
0x10042189d  jz      loc_100421B6B
0x1004218a3  test    rdx, rdx
0x1004218a6  jnz     short loc_1004218DF
0x1004218a8  mov     byte ptr [r9+38h], 1
0x1004218ad  xor     r8d, r8d; FileName
0x1004218b0  mov     [r9+34h], edi
0x1004218b4  xor     edx, edx; FunctionName
0x1004218b6  mov     byte ptr [r9+30h], 1
0x1004218bb  xor     ecx, ecx; Expression
0x1004218bd  mov     dword ptr [r9+2Ch], 16h
0x1004218c5  xor     r9d, r9d; LineNo
0x1004218c8  mov     [rsp+78h+var_50], rbx; __crt_cached_ptd_host *
0x1004218cd  mov     [rsp+78h+var_58], rdi; uintptr_t
0x1004218d2  call    _invalid_parameter_internal
0x1004218d7  or      eax, 0FFFFFFFFh
0x1004218da  jmp     loc_100421B6D
0x1004218df  mov     rax, r15
0x1004218e2  lea     rcx, __pioinfo
0x1004218e9  and     eax, 3Fh
0x1004218ec  mov     r12, r15
0x1004218ef  sar     r12, 6
0x1004218f3  mov     [rbp+var_18], r12
0x1004218f7  lea     r13, [rax+rax*8]
0x1004218fb  mov     rcx, [rcx+r12*8]
0x1004218ff  mov     al, [rcx+r13*8+39h]
0x100421904  mov     byte ptr [rbp+var_48], al
0x100421907  dec     al
0x100421909  cmp     al, 1
0x10042190b  ja      short loc_100421916
0x10042190d  mov     eax, r14d
0x100421910  not     eax
0x100421912  test    al, 1
0x100421914  jz      short loc_1004218A8
0x100421916  test    byte ptr [rcx+r13*8+38h], 20h
0x10042191c  jz      short loc_10042192C
0x10042191e  xor     edx, edx
0x100421920  mov     ecx, r15d
0x100421923  lea     r8d, [rdx+2]
0x100421927  call    _lseeki64_nolock_internal
0x10042192c  mov     ecx, r15d; FileHandle
0x10042192f  mov     [rbp+var_30], rdi
0x100421933  call    _isatty
0x100421938  lea     rdx, __pioinfo
0x10042193f  test    eax, eax
0x100421941  jz      loc_100421A5B
0x100421947  mov     rax, [rdx+r12*8]
0x10042194b  cmp     [rax+r13*8+38h], dil
0x100421950  jge     loc_100421A5B
0x100421956  cmp     [rbx+28h], dil
0x10042195a  jnz     short loc_10042196B
0x10042195c  mov     rcx, rbx; this
0x10042195f  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x100421964  lea     rdx, __pioinfo
0x10042196b  mov     rax, [rbx+18h]
0x10042196f  cmp     [rax+138h], rdi
0x100421976  jnz     short loc_100421987
0x100421978  mov     rax, [rdx+r12*8]
0x10042197c  cmp     [rax+r13*8+39h], dil
0x100421981  jz      loc_100421A5B
0x100421987  mov     rcx, [rdx+r12*8]
0x10042198b  lea     rdx, [rbp+Mode]; lpMode
0x10042198f  mov     rcx, [rcx+r13*8+28h]; hConsoleHandle
0x100421994  call    cs:__imp_GetConsoleMode
0x10042199a  test    eax, eax
0x10042199c  jz      loc_100421A54
0x1004219a2  movsx   ecx, byte ptr [rbp+var_48]
0x1004219a6  test    ecx, ecx
0x1004219a8  jz      loc_100421A31
0x1004219ae  sub     ecx, 1
0x1004219b1  jz      short loc_1004219BC
0x1004219b3  cmp     ecx, 1
0x1004219b6  jnz     loc_100421AF5
0x1004219bc  lea     r12, [rsi+r14]
0x1004219c0  mov     qword ptr [rbp+NumberOfBytesWritten], rdi
0x1004219c4  mov     r15, rsi
0x1004219c7  cmp     rsi, r12
0x1004219ca  jnb     short loc_100421A28
0x1004219cc  mov     r14d, [rbp+NumberOfBytesWritten+4]
0x1004219d0  movzx   eax, word ptr [r15]
0x1004219d4  movzx   ecx, ax; Character
0x1004219d7  mov     [rbp+var_48], ax
0x1004219db  call    _putwch_nolock
0x1004219e0  movzx   ecx, [rbp+var_48]
0x1004219e4  cmp     ax, cx
0x1004219e7  jnz     short loc_100421A1F
0x1004219e9  add     r14d, 2
0x1004219ed  mov     [rbp+NumberOfBytesWritten+4], r14d
0x1004219f1  cmp     cx, 0Ah
0x1004219f5  jnz     short loc_100421A14
0x1004219f7  mov     ecx, 0Dh; Character
0x1004219fc  call    _putwch_nolock
0x100421a01  mov     ecx, 0Dh
0x100421a06  cmp     ax, cx
0x100421a09  jnz     short loc_100421A1F
0x100421a0b  inc     r14d
0x100421a0e  mov     [rbp+NumberOfBytesWritten+4], r14d
0x100421a12  inc     edi
0x100421a14  add     r15, 2
0x100421a18  cmp     r15, r12
0x100421a1b  jnb     short loc_100421A28
0x100421a1d  jmp     short loc_1004219D0
0x100421a1f  call    cs:__imp_GetLastError
0x100421a25  mov     [rbp+NumberOfBytesWritten], eax
0x100421a28  mov     r12, [rbp+var_18]
0x100421a2c  jmp     loc_100421AEB
0x100421a31  mov     r9d, r14d
0x100421a34  mov     [rsp+78h+var_58], rbx
0x100421a39  mov     r8, rsi
0x100421a3c  lea     rcx, [rbp+NumberOfBytesWritten]
0x100421a40  mov     edx, r15d
0x100421a43  call    write_double_translated_ansi_nolock
0x100421a48  movsd   xmm0, qword ptr [rax]
0x100421a4c  mov     edi, [rax+8]
0x100421a4f  jmp     loc_100421AF0
0x100421a54  lea     rdx, __pioinfo
0x100421a5b  mov     rcx, [rdx+r12*8]
0x100421a5f  cmp     [rcx+r13*8+38h], dil
0x100421a64  jge     short loc_100421AB8
0x100421a66  movsx   ecx, byte ptr [rbp+var_48]
0x100421a6a  test    ecx, ecx
0x100421a6c  jz      short loc_100421AA4
0x100421a6e  sub     ecx, 1
0x100421a71  jz      short loc_100421A90
0x100421a73  cmp     ecx, 1
0x100421a76  jnz     loc_100421AFC
0x100421a7c  mov     r9d, r14d
0x100421a7f  lea     rcx, [rbp+NumberOfBytesWritten]
0x100421a83  mov     r8, rsi
0x100421a86  mov     edx, r15d
0x100421a89  call    write_text_utf16le_nolock
0x100421a8e  jmp     short loc_100421A48
0x100421a90  mov     r9d, r14d
0x100421a93  lea     rcx, [rbp+NumberOfBytesWritten]
0x100421a97  mov     r8, rsi
0x100421a9a  mov     edx, r15d
0x100421a9d  call    write_text_utf8_nolock
0x100421aa2  jmp     short loc_100421A48
0x100421aa4  mov     r9d, r14d
0x100421aa7  lea     rcx, [rbp+NumberOfBytesWritten]
0x100421aab  mov     r8, rsi
0x100421aae  mov     edx, r15d
0x100421ab1  call    write_text_ansi_nolock
0x100421ab6  jmp     short loc_100421A48
0x100421ab8  mov     rcx, [rcx+r13*8+28h]; hFile
0x100421abd  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x100421ac1  xor     eax, eax
0x100421ac3  mov     r8d, r14d; nNumberOfBytesToWrite
0x100421ac6  and     [rsp+78h+var_58], rax
0x100421acb  mov     rdx, rsi; lpBuffer
0x100421ace  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x100421ad2  mov     [rbp+var_38], eax
0x100421ad5  call    cs:__imp_WriteFile
0x100421adb  test    eax, eax
0x100421add  jnz     short loc_100421AE8
0x100421adf  call    cs:__imp_GetLastError
0x100421ae5  mov     [rbp+NumberOfBytesWritten], eax
0x100421ae8  mov     edi, [rbp+var_38]
0x100421aeb  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x100421af0  movsd   [rbp+var_30], xmm0
0x100421af5  lea     rdx, __pioinfo
0x100421afc  mov     rax, [rbp+var_30]
0x100421b00  shr     rax, 20h
0x100421b04  test    eax, eax
0x100421b06  jnz     short loc_100421B64
0x100421b08  mov     eax, dword ptr [rbp+var_30]
0x100421b0b  test    eax, eax
0x100421b0d  jz      short loc_100421B3B
0x100421b0f  cmp     eax, 5
0x100421b12  jnz     short loc_100421B2B
0x100421b14  mov     byte ptr [rbx+30h], 1
0x100421b18  mov     dword ptr [rbx+2Ch], 9
0x100421b1f  mov     byte ptr [rbx+38h], 1
0x100421b23  mov     [rbx+34h], eax
0x100421b26  jmp     loc_1004218D7
0x100421b2b  mov     ecx, dword ptr [rbp+var_30]
0x100421b2e  mov     rdx, rbx
0x100421b31  call    __acrt_errno_map_os_error_ptd
0x100421b36  jmp     loc_1004218D7
0x100421b3b  mov     rax, [rdx+r12*8]
0x100421b3f  test    byte ptr [rax+r13*8+38h], 40h
0x100421b45  jz      short loc_100421B4C
0x100421b47  cmp     byte ptr [rsi], 1Ah
0x100421b4a  jz      short loc_100421B6B
0x100421b4c  and     dword ptr [rbx+34h], 0
0x100421b50  mov     byte ptr [rbx+30h], 1
0x100421b54  mov     dword ptr [rbx+2Ch], 1Ch
0x100421b5b  mov     byte ptr [rbx+38h], 1
0x100421b5f  jmp     loc_1004218D7
0x100421b64  mov     eax, dword ptr [rbp+var_30+4]
0x100421b67  sub     eax, edi
0x100421b69  jmp     short loc_100421B6D
0x100421b6b  xor     eax, eax
0x100421b6d  add     rsp, 78h
0x100421b71  pop     r15
0x100421b73  pop     r14
0x100421b75  pop     r13
0x100421b77  pop     r12
0x100421b79  pop     rdi
0x100421b7a  pop     rsi
0x100421b7b  pop     rbx
0x100421b7c  pop     rbp
0x100421b7d  retn
```
