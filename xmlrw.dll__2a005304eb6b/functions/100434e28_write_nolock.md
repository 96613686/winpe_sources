# _write_nolock

- ea: `0x100434e28`
- end: `0x10043512e`
- name: `_write_nolock`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x100434d04`

## callees

- `0x10042d4f0`
- `0x10042e504`
- `0x10042e6e8`
- `0x1004344e8`
- `0x100434964`
- `0x100434a6c`
- `0x100434b8c`
- `0x100434e28`
- `0x100435234`
- `0x100437264`
- `0x100437270`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100434fcf`
- `KERNEL32!GetLastError` at `0x10043508f`
- `KERNEL32!GetLastError` at `0x100434fcf`
- `KERNEL32!GetLastError` at `0x10043508f`
- `KERNEL32!WriteFile` at `0x100435085`
- `KERNEL32!WriteFile` at `0x100435085`
- `KERNEL32!GetConsoleMode` at `0x100434f44`
- `KERNEL32!GetConsoleMode` at `0x100434f44`

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
0x100434e28  push    rbp
0x100434e2a  push    rbx
0x100434e2b  push    rsi
0x100434e2c  push    rdi
0x100434e2d  push    r12
0x100434e2f  push    r13
0x100434e31  push    r14
0x100434e33  push    r15
0x100434e35  mov     rbp, rsp
0x100434e38  sub     rsp, 78h
0x100434e3c  xor     edi, edi
0x100434e3e  mov     r14d, r8d
0x100434e41  movsxd  r15, ecx
0x100434e44  mov     rbx, r9
0x100434e47  mov     rsi, rdx
0x100434e4a  test    r8d, r8d
0x100434e4d  jz      loc_10043511B
0x100434e53  test    rdx, rdx
0x100434e56  jnz     short loc_100434E8F
0x100434e58  mov     byte ptr [r9+38h], 1
0x100434e5d  xor     r8d, r8d; FileName
0x100434e60  mov     [r9+34h], edi
0x100434e64  xor     edx, edx; FunctionName
0x100434e66  mov     byte ptr [r9+30h], 1
0x100434e6b  xor     ecx, ecx; Expression
0x100434e6d  mov     dword ptr [r9+2Ch], 16h
0x100434e75  xor     r9d, r9d; LineNo
0x100434e78  mov     [rsp+78h+var_50], rbx; __crt_cached_ptd_host *
0x100434e7d  mov     [rsp+78h+var_58], rdi; uintptr_t
0x100434e82  call    _invalid_parameter_internal
0x100434e87  or      eax, 0FFFFFFFFh
0x100434e8a  jmp     loc_10043511D
0x100434e8f  mov     rax, r15
0x100434e92  lea     rcx, __pioinfo
0x100434e99  and     eax, 3Fh
0x100434e9c  mov     r12, r15
0x100434e9f  sar     r12, 6
0x100434ea3  mov     [rbp+var_18], r12
0x100434ea7  lea     r13, [rax+rax*8]
0x100434eab  mov     rcx, [rcx+r12*8]
0x100434eaf  mov     al, [rcx+r13*8+39h]
0x100434eb4  mov     byte ptr [rbp+var_48], al
0x100434eb7  dec     al
0x100434eb9  cmp     al, 1
0x100434ebb  ja      short loc_100434EC6
0x100434ebd  mov     eax, r14d
0x100434ec0  not     eax
0x100434ec2  test    al, 1
0x100434ec4  jz      short loc_100434E58
0x100434ec6  test    byte ptr [rcx+r13*8+38h], 20h
0x100434ecc  jz      short loc_100434EDC
0x100434ece  xor     edx, edx
0x100434ed0  mov     ecx, r15d
0x100434ed3  lea     r8d, [rdx+2]
0x100434ed7  call    _lseeki64_nolock_internal
0x100434edc  mov     ecx, r15d; FileHandle
0x100434edf  mov     [rbp+var_30], rdi
0x100434ee3  call    _isatty
0x100434ee8  lea     rdx, __pioinfo
0x100434eef  test    eax, eax
0x100434ef1  jz      loc_10043500B
0x100434ef7  mov     rax, [rdx+r12*8]
0x100434efb  cmp     [rax+r13*8+38h], dil
0x100434f00  jge     loc_10043500B
0x100434f06  cmp     [rbx+28h], dil
0x100434f0a  jnz     short loc_100434F1B
0x100434f0c  mov     rcx, rbx; this
0x100434f0f  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x100434f14  lea     rdx, __pioinfo
0x100434f1b  mov     rax, [rbx+18h]
0x100434f1f  cmp     [rax+138h], rdi
0x100434f26  jnz     short loc_100434F37
0x100434f28  mov     rax, [rdx+r12*8]
0x100434f2c  cmp     [rax+r13*8+39h], dil
0x100434f31  jz      loc_10043500B
0x100434f37  mov     rcx, [rdx+r12*8]
0x100434f3b  lea     rdx, [rbp+Mode]; lpMode
0x100434f3f  mov     rcx, [rcx+r13*8+28h]; hConsoleHandle
0x100434f44  call    cs:__imp_GetConsoleMode
0x100434f4a  test    eax, eax
0x100434f4c  jz      loc_100435004
0x100434f52  movsx   ecx, byte ptr [rbp+var_48]
0x100434f56  test    ecx, ecx
0x100434f58  jz      loc_100434FE1
0x100434f5e  sub     ecx, 1
0x100434f61  jz      short loc_100434F6C
0x100434f63  cmp     ecx, 1
0x100434f66  jnz     loc_1004350A5
0x100434f6c  lea     r12, [rsi+r14]
0x100434f70  mov     qword ptr [rbp+NumberOfBytesWritten], rdi
0x100434f74  mov     r15, rsi
0x100434f77  cmp     rsi, r12
0x100434f7a  jnb     short loc_100434FD8
0x100434f7c  mov     r14d, [rbp+NumberOfBytesWritten+4]
0x100434f80  movzx   eax, word ptr [r15]
0x100434f84  movzx   ecx, ax; Character
0x100434f87  mov     [rbp+var_48], ax
0x100434f8b  call    _putwch_nolock
0x100434f90  movzx   ecx, [rbp+var_48]
0x100434f94  cmp     ax, cx
0x100434f97  jnz     short loc_100434FCF
0x100434f99  add     r14d, 2
0x100434f9d  mov     [rbp+NumberOfBytesWritten+4], r14d
0x100434fa1  cmp     cx, 0Ah
0x100434fa5  jnz     short loc_100434FC4
0x100434fa7  mov     ecx, 0Dh; Character
0x100434fac  call    _putwch_nolock
0x100434fb1  mov     ecx, 0Dh
0x100434fb6  cmp     ax, cx
0x100434fb9  jnz     short loc_100434FCF
0x100434fbb  inc     r14d
0x100434fbe  mov     [rbp+NumberOfBytesWritten+4], r14d
0x100434fc2  inc     edi
0x100434fc4  add     r15, 2
0x100434fc8  cmp     r15, r12
0x100434fcb  jnb     short loc_100434FD8
0x100434fcd  jmp     short loc_100434F80
0x100434fcf  call    cs:__imp_GetLastError
0x100434fd5  mov     [rbp+NumberOfBytesWritten], eax
0x100434fd8  mov     r12, [rbp+var_18]
0x100434fdc  jmp     loc_10043509B
0x100434fe1  mov     r9d, r14d
0x100434fe4  mov     [rsp+78h+var_58], rbx
0x100434fe9  mov     r8, rsi
0x100434fec  lea     rcx, [rbp+NumberOfBytesWritten]
0x100434ff0  mov     edx, r15d
0x100434ff3  call    write_double_translated_ansi_nolock
0x100434ff8  movsd   xmm0, qword ptr [rax]
0x100434ffc  mov     edi, [rax+8]
0x100434fff  jmp     loc_1004350A0
0x100435004  lea     rdx, __pioinfo
0x10043500b  mov     rcx, [rdx+r12*8]
0x10043500f  cmp     [rcx+r13*8+38h], dil
0x100435014  jge     short loc_100435068
0x100435016  movsx   ecx, byte ptr [rbp+var_48]
0x10043501a  test    ecx, ecx
0x10043501c  jz      short loc_100435054
0x10043501e  sub     ecx, 1
0x100435021  jz      short loc_100435040
0x100435023  cmp     ecx, 1
0x100435026  jnz     loc_1004350AC
0x10043502c  mov     r9d, r14d
0x10043502f  lea     rcx, [rbp+NumberOfBytesWritten]
0x100435033  mov     r8, rsi
0x100435036  mov     edx, r15d
0x100435039  call    write_text_utf16le_nolock
0x10043503e  jmp     short loc_100434FF8
0x100435040  mov     r9d, r14d
0x100435043  lea     rcx, [rbp+NumberOfBytesWritten]
0x100435047  mov     r8, rsi
0x10043504a  mov     edx, r15d
0x10043504d  call    write_text_utf8_nolock
0x100435052  jmp     short loc_100434FF8
0x100435054  mov     r9d, r14d
0x100435057  lea     rcx, [rbp+NumberOfBytesWritten]
0x10043505b  mov     r8, rsi
0x10043505e  mov     edx, r15d
0x100435061  call    write_text_ansi_nolock
0x100435066  jmp     short loc_100434FF8
0x100435068  mov     rcx, [rcx+r13*8+28h]; hFile
0x10043506d  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x100435071  xor     eax, eax
0x100435073  mov     r8d, r14d; nNumberOfBytesToWrite
0x100435076  and     [rsp+78h+var_58], rax
0x10043507b  mov     rdx, rsi; lpBuffer
0x10043507e  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x100435082  mov     [rbp+var_38], eax
0x100435085  call    cs:__imp_WriteFile
0x10043508b  test    eax, eax
0x10043508d  jnz     short loc_100435098
0x10043508f  call    cs:__imp_GetLastError
0x100435095  mov     [rbp+NumberOfBytesWritten], eax
0x100435098  mov     edi, [rbp+var_38]
0x10043509b  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x1004350a0  movsd   [rbp+var_30], xmm0
0x1004350a5  lea     rdx, __pioinfo
0x1004350ac  mov     rax, [rbp+var_30]
0x1004350b0  shr     rax, 20h
0x1004350b4  test    eax, eax
0x1004350b6  jnz     short loc_100435114
0x1004350b8  mov     eax, dword ptr [rbp+var_30]
0x1004350bb  test    eax, eax
0x1004350bd  jz      short loc_1004350EB
0x1004350bf  cmp     eax, 5
0x1004350c2  jnz     short loc_1004350DB
0x1004350c4  mov     byte ptr [rbx+30h], 1
0x1004350c8  mov     dword ptr [rbx+2Ch], 9
0x1004350cf  mov     byte ptr [rbx+38h], 1
0x1004350d3  mov     [rbx+34h], eax
0x1004350d6  jmp     loc_100434E87
0x1004350db  mov     ecx, dword ptr [rbp+var_30]
0x1004350de  mov     rdx, rbx
0x1004350e1  call    __acrt_errno_map_os_error_ptd
0x1004350e6  jmp     loc_100434E87
0x1004350eb  mov     rax, [rdx+r12*8]
0x1004350ef  test    byte ptr [rax+r13*8+38h], 40h
0x1004350f5  jz      short loc_1004350FC
0x1004350f7  cmp     byte ptr [rsi], 1Ah
0x1004350fa  jz      short loc_10043511B
0x1004350fc  and     dword ptr [rbx+34h], 0
0x100435100  mov     byte ptr [rbx+30h], 1
0x100435104  mov     dword ptr [rbx+2Ch], 1Ch
0x10043510b  mov     byte ptr [rbx+38h], 1
0x10043510f  jmp     loc_100434E87
0x100435114  mov     eax, dword ptr [rbp+var_30+4]
0x100435117  sub     eax, edi
0x100435119  jmp     short loc_10043511D
0x10043511b  xor     eax, eax
0x10043511d  add     rsp, 78h
0x100435121  pop     r15
0x100435123  pop     r14
0x100435125  pop     r13
0x100435127  pop     r12
0x100435129  pop     rdi
0x10043512a  pop     rsi
0x10043512b  pop     rbx
0x10043512c  pop     rbp
0x10043512d  retn
```
