# _BasicApiWrapper(_PROFILE_FOLDER_ID,ushort const *,ushort *,ulong *)

- ea: `0x180007ca0`
- end: `0x180007deb`
- name: `?_BasicApiWrapper@@YAHW4_PROFILE_FOLDER_ID@@PEBGPEAGPEAK@Z`
- size: `331`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180007c40`
- `0x180007c60`
- `0x180007c80`
- `0x180015090`
- `0x1800151a0`
- `0x1800152b0`

## callees

- `0x180007ca0`
- `0x18000e640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007da7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007da7`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180007cf0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180007d94`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180007cf0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180007d94`

## pseudocode

```c
__int64 __fastcall _BasicApiWrapper(__int64 a1, __int64 a2, _WORD *a3, _DWORD *a4)
{
  _WORD *v5; // rbx
  unsigned int v7; // r15d
  __int64 v8; // rbp
  int BasicProfileFolderPath; // edi
  __int64 v10; // rcx
  _WORD *v12; // rax
  _BYTE v13[528]; // [rsp+20h] [rbp-258h] BYREF

  v5 = a3;
  v7 = a1;
  if ( !a4 )
  {
    LOWORD(BasicProfileFolderPath) = 87;
    goto LABEL_15;
  }
  if ( !a3 || !*a4 )
  {
    LOWORD(BasicProfileFolderPath) = 122;
    *a4 = 0;
    v8 = 0x7FFFFFFF;
    goto LABEL_14;
  }
  v8 = 0x7FFFFFFF;
  BasicProfileFolderPath = GetBasicProfileFolderPath(a1, a2, a3, (unsigned int)*a4);
  if ( BasicProfileFolderPath >= 0 )
  {
    v10 = 0x7FFFFFFF;
    do
    {
      if ( !*v5 )
        break;
      ++v5;
      --v10;
    }
    while ( v10 );
    BasicProfileFolderPath = -2147024809;
    if ( v10 )
    {
      BasicProfileFolderPath = 0;
      *a4 = 0x80000000 - v10;
    }
  }
  if ( BasicProfileFolderPath == -2147024774 )
  {
    if ( *a4 >= 0x104u )
      goto LABEL_15;
LABEL_14:
    if ( (int)GetBasicProfileFolderPath(v7, a2, v13, 260) >= 0 )
    {
      v12 = v13;
      while ( *v12 )
      {
        ++v12;
        if ( !--v8 )
          goto LABEL_15;
      }
      *a4 = 0x80000000 - v8;
    }
    goto LABEL_15;
  }
  if ( BasicProfileFolderPath >= 0 )
    return 1;
LABEL_15:
  SetLastError((unsigned __int16)BasicProfileFolderPath);
  return 0;
}

```

## disassembly

```asm
0x180007ca0  push    rbx
0x180007ca2  push    rbp
0x180007ca3  push    rsi
0x180007ca4  push    rdi
0x180007ca5  push    r12
0x180007ca7  push    r14
0x180007ca9  push    r15
0x180007cab  sub     rsp, 240h
0x180007cb2  mov     rax, cs:__security_cookie
0x180007cb9  xor     rax, rsp
0x180007cbc  mov     [rsp+278h+var_48], rax
0x180007cc4  mov     rsi, r9
0x180007cc7  mov     rbx, r8
0x180007cca  mov     r12, rdx
0x180007ccd  mov     r15d, ecx
0x180007cd0  test    r9, r9
0x180007cd3  jz      loc_180007DE4
0x180007cd9  test    rbx, rbx
0x180007cdc  jz      loc_180007D6E
0x180007ce2  mov     eax, [r9]
0x180007ce5  test    eax, eax
0x180007ce7  jz      loc_180007D6E
0x180007ced  mov     r9d, eax
0x180007cf0  call    cs:__imp_GetBasicProfileFolderPath
0x180007cf7  nop     dword ptr [rax+rax+00h]
0x180007cfc  mov     ebp, 7FFFFFFFh
0x180007d01  mov     r14d, 80000000h
0x180007d07  mov     edi, eax
0x180007d09  test    eax, eax
0x180007d0b  js      short loc_180007D36
0x180007d0d  mov     ecx, ebp
0x180007d0f  nop
0x180007d10  cmp     word ptr [rbx], 0
0x180007d14  jz      short loc_180007D20
0x180007d16  add     rbx, 2
0x180007d1a  sub     rcx, 1
0x180007d1e  jnz     short loc_180007D10
0x180007d20  xor     eax, eax
0x180007d22  mov     edi, 80070057h
0x180007d27  test    rcx, rcx
0x180007d2a  cmovnz  edi, eax
0x180007d2d  jz      short loc_180007D36
0x180007d2f  mov     eax, r14d
0x180007d32  sub     eax, ecx
0x180007d34  mov     [rsi], eax
0x180007d36  cmp     edi, 8007007Ah
0x180007d3c  jz      loc_180007DDA
0x180007d42  test    edi, edi
0x180007d44  js      short loc_180007DA4
0x180007d46  mov     eax, 1
0x180007d4b  mov     rcx, [rsp+278h+var_48]
0x180007d53  xor     rcx, rsp; StackCookie
0x180007d56  call    __security_check_cookie
0x180007d5b  add     rsp, 240h
0x180007d62  pop     r15
0x180007d64  pop     r14
0x180007d66  pop     r12
0x180007d68  pop     rdi
0x180007d69  pop     rsi
0x180007d6a  pop     rbp
0x180007d6b  pop     rbx
0x180007d6c  retn
0x180007d6e  xor     eax, eax
0x180007d70  mov     edi, 8007007Ah
0x180007d75  mov     [r9], eax
0x180007d78  mov     ebp, 7FFFFFFFh
0x180007d7d  mov     r14d, 80000000h
0x180007d83  mov     r9d, 104h
0x180007d89  lea     r8, [rsp+278h+var_258]
0x180007d8e  mov     rdx, r12
0x180007d91  mov     ecx, r15d
0x180007d94  call    cs:__imp_GetBasicProfileFolderPath
0x180007d9b  nop     dword ptr [rax+rax+00h]
0x180007da0  test    eax, eax
0x180007da2  jns     short loc_180007DB7
0x180007da4  movzx   ecx, di; dwErrCode
0x180007da7  call    cs:__imp_SetLastError
0x180007dae  nop     dword ptr [rax+rax+00h]
0x180007db3  xor     eax, eax
0x180007db5  jmp     short loc_180007D4B
0x180007db7  lea     rax, [rsp+278h+var_258]
0x180007dbc  nop     dword ptr [rax+00h]
0x180007dc0  cmp     word ptr [rax], 0
0x180007dc4  jz      short loc_180007DD2
0x180007dc6  add     rax, 2
0x180007dca  sub     rbp, 1
0x180007dce  jnz     short loc_180007DC0
0x180007dd0  jmp     short loc_180007DA4
0x180007dd2  sub     r14d, ebp
0x180007dd5  mov     [rsi], r14d
0x180007dd8  jmp     short loc_180007DA4
0x180007dda  cmp     dword ptr [rsi], 104h
0x180007de0  jnb     short loc_180007DA4
0x180007de2  jmp     short loc_180007D83
0x180007de4  mov     edi, 80070057h
0x180007de9  jmp     short loc_180007DA4
```
