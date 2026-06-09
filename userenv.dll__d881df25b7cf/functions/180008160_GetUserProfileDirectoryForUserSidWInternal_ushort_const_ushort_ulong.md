# GetUserProfileDirectoryForUserSidWInternal(ushort const *,ushort *,ulong *)

- ea: `0x180008160`
- end: `0x1800082f1`
- name: `?GetUserProfileDirectoryForUserSidWInternal@@YAHPEBGPEAGPEAK@Z`
- size: `401`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180008150`

## callees

- `0x180008160`
- `0x18000e640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000829e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000829e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082d3`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800081c5`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000828b`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800081c5`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000828b`

## pseudocode

```c
__int64 __fastcall GetUserProfileDirectoryForUserSidWInternal(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  unsigned __int16 *v4; // rbx
  unsigned int v6; // esi
  __int64 v7; // rbp
  int BasicProfileFolderPath; // edi
  __int64 v9; // rcx
  _WORD *v11; // rax
  _BYTE v12[528]; // [rsp+20h] [rbp-258h] BYREF

  v4 = a2;
  if ( a3 )
  {
    if ( a2 && *a3 )
    {
      v6 = 0;
      v7 = 0x7FFFFFFF;
      BasicProfileFolderPath = GetBasicProfileFolderPath(5, a1, a2, *a3);
      if ( BasicProfileFolderPath >= 0 )
      {
        v9 = 0x7FFFFFFF;
        do
        {
          if ( !*v4 )
            break;
          ++v4;
          --v9;
        }
        while ( v9 );
        BasicProfileFolderPath = -2147024809;
        if ( v9 )
        {
          BasicProfileFolderPath = 0;
          *a3 = 0x80000000 - v9;
        }
      }
      if ( BasicProfileFolderPath != -2147024774 )
      {
        if ( BasicProfileFolderPath >= 0 )
          return 1;
LABEL_16:
        SetLastError((unsigned __int16)BasicProfileFolderPath);
        return v6;
      }
      if ( *a3 >= 0x104 )
        goto LABEL_16;
    }
    else
    {
      v6 = 0;
      LOWORD(BasicProfileFolderPath) = 122;
      *a3 = 0;
      v7 = 0x7FFFFFFF;
    }
    if ( (int)GetBasicProfileFolderPath(5, a1, v12, 260) >= 0 )
    {
      v11 = v12;
      while ( *v11 )
      {
        ++v11;
        if ( !--v7 )
          goto LABEL_16;
      }
      *a3 = 0x80000000 - v7;
    }
    goto LABEL_16;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180008160  mov     r11, rsp
0x180008163  push    rbx
0x180008164  push    r12
0x180008166  push    r14
0x180008168  sub     rsp, 260h
0x18000816f  mov     rax, cs:__security_cookie
0x180008176  xor     rax, rsp
0x180008179  mov     [rsp+278h+var_48], rax
0x180008181  mov     r14, r8
0x180008184  mov     rbx, rdx
0x180008187  mov     r12, rcx
0x18000818a  test    r8, r8
0x18000818d  jz      loc_1800082CE
0x180008193  mov     [r11-20h], rbp
0x180008197  mov     [r11-28h], rsi
0x18000819b  mov     [r11-30h], rdi
0x18000819f  mov     [r11-38h], r15
0x1800081a3  test    rdx, rdx
0x1800081a6  jz      loc_180008263
0x1800081ac  mov     eax, [r8]
0x1800081af  test    eax, eax
0x1800081b1  jz      loc_180008263
0x1800081b7  mov     r8, rdx
0x1800081ba  mov     r9d, eax
0x1800081bd  mov     rdx, rcx
0x1800081c0  mov     ecx, 5
0x1800081c5  call    cs:__imp_GetBasicProfileFolderPath
0x1800081cc  nop     dword ptr [rax+rax+00h]
0x1800081d1  xor     esi, esi
0x1800081d3  mov     ebp, 7FFFFFFFh
0x1800081d8  mov     edi, eax
0x1800081da  mov     r15d, 80000000h
0x1800081e0  test    eax, eax
0x1800081e2  js      short loc_18000820A
0x1800081e4  mov     ecx, ebp
0x1800081e6  cmp     [rbx], si
0x1800081e9  jz      short loc_1800081F5
0x1800081eb  add     rbx, 2
0x1800081ef  sub     rcx, 1
0x1800081f3  jnz     short loc_1800081E6
0x1800081f5  test    rcx, rcx
0x1800081f8  mov     edi, 80070057h
0x1800081fd  cmovnz  edi, esi
0x180008200  jz      short loc_18000820A
0x180008202  mov     eax, r15d
0x180008205  sub     eax, ecx
0x180008207  mov     [r14], eax
0x18000820a  cmp     edi, 8007007Ah
0x180008210  jz      loc_1800082E6
0x180008216  test    edi, edi
0x180008218  js      loc_18000829B
0x18000821e  mov     esi, 1
0x180008223  mov     r15, [rsp+278h+var_38]
0x18000822b  mov     eax, esi
0x18000822d  mov     rsi, [rsp+278h+var_28]
0x180008235  mov     rdi, [rsp+278h+var_30]
0x18000823d  mov     rbp, [rsp+278h+var_20]
0x180008245  mov     rcx, [rsp+278h+var_48]
0x18000824d  xor     rcx, rsp; StackCookie
0x180008250  call    __security_check_cookie
0x180008255  add     rsp, 260h
0x18000825c  pop     r14
0x18000825e  pop     r12
0x180008260  pop     rbx
0x180008261  retn
0x180008263  xor     esi, esi
0x180008265  mov     edi, 8007007Ah
0x18000826a  mov     [r8], esi
0x18000826d  mov     ebp, 7FFFFFFFh
0x180008272  mov     r15d, 80000000h
0x180008278  mov     r9d, 104h
0x18000827e  lea     r8, [rsp+278h+var_258]
0x180008283  mov     rdx, r12
0x180008286  mov     ecx, 5
0x18000828b  call    cs:__imp_GetBasicProfileFolderPath
0x180008292  nop     dword ptr [rax+rax+00h]
0x180008297  test    eax, eax
0x180008299  jns     short loc_1800082AF
0x18000829b  movzx   ecx, di; dwErrCode
0x18000829e  call    cs:__imp_SetLastError
0x1800082a5  nop     dword ptr [rax+rax+00h]
0x1800082aa  jmp     loc_180008223
0x1800082af  lea     rax, [rsp+278h+var_258]
0x1800082b4  cmp     word ptr [rax], 0
0x1800082b8  jz      short loc_1800082C6
0x1800082ba  add     rax, 2
0x1800082be  sub     rbp, 1
0x1800082c2  jnz     short loc_1800082B4
0x1800082c4  jmp     short loc_18000829B
0x1800082c6  sub     r15d, ebp
0x1800082c9  mov     [r14], r15d
0x1800082cc  jmp     short loc_18000829B
0x1800082ce  mov     ecx, 57h ; 'W'; dwErrCode
0x1800082d3  call    cs:__imp_SetLastError
0x1800082da  nop     dword ptr [rax+rax+00h]
0x1800082df  xor     eax, eax
0x1800082e1  jmp     loc_180008245
0x1800082e6  cmp     dword ptr [r14], 104h
0x1800082ed  jnb     short loc_18000829B
0x1800082ef  jmp     short loc_180008278
```
