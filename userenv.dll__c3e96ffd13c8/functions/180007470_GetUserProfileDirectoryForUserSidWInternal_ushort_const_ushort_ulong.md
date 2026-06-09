# GetUserProfileDirectoryForUserSidWInternal(ushort const *,ushort *,ulong *)

- ea: `0x180007470`
- end: `0x1800075e7`
- name: `?GetUserProfileDirectoryForUserSidWInternal@@YAHPEBGPEAGPEAK@Z`
- size: `375`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180007460`

## callees

- `0x180007470`
- `0x18000d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000759d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800075cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000759d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800075cf`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800074d5`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180007590`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800074d5`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180007590`

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
0x180007470  mov     r11, rsp
0x180007473  push    rbx
0x180007474  push    r12
0x180007476  push    r14
0x180007478  sub     rsp, 260h
0x18000747f  mov     rax, cs:__security_cookie
0x180007486  xor     rax, rsp
0x180007489  mov     [rsp+278h+var_48], rax
0x180007491  mov     r14, r8
0x180007494  mov     rbx, rdx
0x180007497  mov     r12, rcx
0x18000749a  test    r8, r8
0x18000749d  jz      loc_1800075CA
0x1800074a3  mov     [r11-20h], rbp
0x1800074a7  mov     [r11-28h], rsi
0x1800074ab  mov     [r11-30h], rdi
0x1800074af  mov     [r11-38h], r15
0x1800074b3  test    rdx, rdx
0x1800074b6  jz      loc_180007568
0x1800074bc  mov     eax, [r8]
0x1800074bf  test    eax, eax
0x1800074c1  jz      loc_180007568
0x1800074c7  mov     r8, rdx
0x1800074ca  mov     r9d, eax
0x1800074cd  mov     rdx, rcx
0x1800074d0  mov     ecx, 5
0x1800074d5  call    cs:__imp_GetBasicProfileFolderPath
0x1800074db  xor     esi, esi
0x1800074dd  mov     ebp, 7FFFFFFFh
0x1800074e2  mov     edi, eax
0x1800074e4  mov     r15d, 80000000h
0x1800074ea  test    eax, eax
0x1800074ec  js      short loc_180007514
0x1800074ee  mov     ecx, ebp
0x1800074f0  cmp     [rbx], si
0x1800074f3  jz      short loc_1800074FF
0x1800074f5  add     rbx, 2
0x1800074f9  sub     rcx, 1
0x1800074fd  jnz     short loc_1800074F0
0x1800074ff  test    rcx, rcx
0x180007502  mov     edi, 80070057h
0x180007507  cmovnz  edi, esi
0x18000750a  jz      short loc_180007514
0x18000750c  mov     eax, r15d
0x18000750f  sub     eax, ecx
0x180007511  mov     [r14], eax
0x180007514  cmp     edi, 8007007Ah
0x18000751a  jz      loc_1800075DC
0x180007520  test    edi, edi
0x180007522  js      short loc_18000759A
0x180007524  mov     esi, 1
0x180007529  mov     r15, [rsp+278h+var_38]
0x180007531  mov     eax, esi
0x180007533  mov     rsi, [rsp+278h+var_28]
0x18000753b  mov     rdi, [rsp+278h+var_30]
0x180007543  mov     rbp, [rsp+278h+var_20]
0x18000754b  mov     rcx, [rsp+278h+var_48]
0x180007553  xor     rcx, rsp; StackCookie
0x180007556  call    __security_check_cookie
0x18000755b  add     rsp, 260h
0x180007562  pop     r14
0x180007564  pop     r12
0x180007566  pop     rbx
0x180007567  retn
0x180007568  xor     esi, esi
0x18000756a  mov     edi, 8007007Ah
0x18000756f  mov     [r8], esi
0x180007572  mov     ebp, 7FFFFFFFh
0x180007577  mov     r15d, 80000000h
0x18000757d  mov     r9d, 104h
0x180007583  lea     r8, [rsp+278h+var_258]
0x180007588  mov     rdx, r12
0x18000758b  mov     ecx, 5
0x180007590  call    cs:__imp_GetBasicProfileFolderPath
0x180007596  test    eax, eax
0x180007598  jns     short loc_1800075A5
0x18000759a  movzx   ecx, di; dwErrCode
0x18000759d  call    cs:__imp_SetLastError
0x1800075a3  jmp     short loc_180007529
0x1800075a5  lea     rax, [rsp+278h+var_258]
0x1800075aa  nop     word ptr [rax+rax+00h]
0x1800075b0  cmp     word ptr [rax], 0
0x1800075b4  jz      short loc_1800075C2
0x1800075b6  add     rax, 2
0x1800075ba  sub     rbp, 1
0x1800075be  jnz     short loc_1800075B0
0x1800075c0  jmp     short loc_18000759A
0x1800075c2  sub     r15d, ebp
0x1800075c5  mov     [r14], r15d
0x1800075c8  jmp     short loc_18000759A
0x1800075ca  mov     ecx, 57h ; 'W'; dwErrCode
0x1800075cf  call    cs:__imp_SetLastError
0x1800075d5  xor     eax, eax
0x1800075d7  jmp     loc_18000754B
0x1800075dc  cmp     dword ptr [r14], 104h
0x1800075e3  jnb     short loc_18000759A
0x1800075e5  jmp     short loc_18000757D
```
