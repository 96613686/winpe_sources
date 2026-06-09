# CSmartSession::GetUserNameFromSessionInformation(ushort * *,ushort * *)

- ea: `0x1800053f0`
- end: `0x18000582e`
- name: `?GetUserNameFromSessionInformation@CSmartSession@@AEAAJPEAPEAG0@Z`
- size: `1086`
- prototype: `__int64 __fastcall(CSmartSession *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006f3c`

## callees

- `0x1800053f0`
- `0x180007890`
- `0x18000bf20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000549b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005576`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000549b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005576`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000570e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005816`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000570e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005816`

## string_xrefs

- `0x1800056ff`: `StringCchCopy failed: 0x%x in %s`
- `0x1800057a6`: `StringCchCopy failed: 0x%x in %s`
- `0x1800056af`: `CSmartSession::SafeCopyString`
- `0x1800056f6`: `CSmartSession::SafeCopyString`
- `0x180005723`: `CSmartSession::SafeCopyString`
- `0x180005750`: `CSmartSession::SafeCopyString`
- `0x18000579d`: `CSmartSession::SafeCopyString`
- `0x1800057cd`: `CSmartSession::SafeCopyString`
- `0x18000564d`: `SafeCopyString on user name failed: 0x%x in %s`
- `0x18000573b`: `SafeCopyString on user name failed: 0x%x in %s`
- `0x1800057e8`: `SafeCopyString on domainname failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSmartSession::GetUserNameFromSessionInformation(
        CSmartSession *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  _WORD *v3; // rsi
  unsigned __int16 *v4; // r13
  bool v6; // zf
  unsigned __int16 **v7; // rdi
  _WORD *v9; // rbx
  __int64 v10; // rbp
  unsigned int v11; // r12d
  int v12; // r15d
  __int64 v13; // rcx
  _WORD *v14; // rax
  __int64 v15; // rdi
  unsigned __int64 v16; // rdx
  __int64 v17; // rax
  _WORD *v18; // r8
  _WORD *v19; // rcx
  int v20; // r8d
  _WORD *v21; // rbx
  __int64 v22; // rdx
  _WORD *v23; // rax
  unsigned int v24; // edi
  __int64 v25; // rdi
  _WORD *v26; // rax
  void *v27; // rsi
  unsigned __int64 v28; // rdx
  _WORD *v29; // rcx
  int v31; // eax
  CSmartSession *v32; // rcx
  int v33; // eax
  unsigned __int16 *v34; // [rsp+20h] [rbp-58h] BYREF
  _WORD *v35; // [rsp+80h] [rbp+8h]
  HLOCAL hMem; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  v35 = 0;
  v6 = *((_DWORD *)this + 71) == 1;
  v7 = a2;
  hMem = 0;
  v34 = 0;
  if ( v6 )
  {
    if ( *((_DWORD *)this + 18) == 1 )
    {
      v31 = CSmartSession::SafeCopyString(this, (const unsigned __int16 *)this + 95, (unsigned __int16 **)&hMem);
      v11 = v31;
      if ( v31 >= 0 )
      {
        v33 = CSmartSession::SafeCopyString(v32, (const unsigned __int16 *)this + 77, &v34);
        v11 = v33;
        if ( v33 >= 0 )
        {
          *v7 = (unsigned __int16 *)hMem;
          *a3 = v34;
          return v11;
        }
        v3 = hMem;
        v4 = v34;
        v24 = v33;
        goto LABEL_61;
      }
      v3 = hMem;
      _DbgPrintMessage(
        8,
        "SafeCopyString on user name failed: 0x%x in %s",
        (unsigned int)v31,
        "CSmartSession::GetUserNameFromSessionInformation");
LABEL_62:
      if ( v3 )
        LocalFree(v3);
      if ( v4 )
        LocalFree(v4);
      return v11;
    }
  }
  else if ( *((_DWORD *)this + 70) == 1 )
  {
    v9 = (_WORD *)*((_QWORD *)this + 2);
    v10 = 2147483646;
    v11 = -2147024809;
    v12 = -2147024774;
    if ( !v9 )
      goto LABEL_22;
    v13 = 0x7FFFFFFF;
    v14 = v9;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    if ( !v13 )
    {
      v11 = -2147024809;
      _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", -2147024809, "CSmartSession::SafeCopyString");
      goto LABEL_53;
    }
    v15 = 0x7FFFFFFF - v13;
    v3 = LocalAlloc(0x40u, 2 * (0x7FFFFFFF - v13) + 2);
    if ( !v3 )
    {
      v11 = -2147024882;
      _DbgPrintMessage(8, "MIDL_user_allocate failed: 0x%x in %s", -2147024882, "CSmartSession::SafeCopyString");
      v3 = 0;
LABEL_53:
      _DbgPrintMessage(
        8,
        "SafeCopyString on user name failed: 0x%x in %s",
        v11,
        "CSmartSession::GetUserNameFromSessionInformation");
      goto LABEL_62;
    }
    v16 = v15 + 1;
    if ( v15 == -1 )
    {
      v20 = -2147024809;
    }
    else
    {
      if ( v16 > 0x7FFFFFFF )
      {
        v20 = -2147024809;
        *v3 = 0;
LABEL_51:
        _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v20, "CSmartSession::SafeCopyString");
        LocalFree(v3);
        v3 = 0;
        goto LABEL_53;
      }
      v17 = 2147483646;
      v18 = v3;
      do
      {
        if ( !v17 )
          break;
        if ( !*v9 )
          break;
        *v18++ = *v9++;
        --v17;
        --v16;
      }
      while ( v16 );
      v19 = v18 - 1;
      if ( v16 )
        v19 = v18;
      v20 = -2147024774;
      if ( v16 )
        v20 = 0;
      *v19 = 0;
    }
    if ( v20 >= 0 )
    {
      v7 = a2;
      v35 = v3;
LABEL_22:
      v21 = (_WORD *)*((_QWORD *)this + 3);
      if ( !v21 )
      {
        v12 = 0;
        goto LABEL_38;
      }
      v22 = 0x7FFFFFFF;
      v23 = (_WORD *)*((_QWORD *)this + 3);
      do
      {
        if ( !*v23 )
          break;
        ++v23;
        --v22;
      }
      while ( v22 );
      v24 = -2147024809;
      if ( !v22 )
      {
        _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", -2147024809, "CSmartSession::SafeCopyString");
        v11 = -2147024809;
        goto LABEL_61;
      }
      v25 = 0x7FFFFFFF - v22;
      v26 = LocalAlloc(0x40u, 2 * (0x7FFFFFFF - v22) + 2);
      v27 = v26;
      if ( !v26 )
      {
        v11 = -2147024882;
        v24 = -2147024882;
        _DbgPrintMessage(8, "MIDL_user_allocate failed: 0x%x in %s", -2147024882, "CSmartSession::SafeCopyString");
        v3 = v35;
LABEL_61:
        _DbgPrintMessage(
          8,
          "SafeCopyString on domainname failed: 0x%x in %s",
          v24,
          "CSmartSession::GetUserNameFromSessionInformation");
        goto LABEL_62;
      }
      v28 = v25 + 1;
      if ( v25 == -1 )
      {
        v12 = -2147024809;
      }
      else
      {
        if ( v28 > 0x7FFFFFFF )
        {
          v12 = -2147024809;
          v24 = -2147024809;
          *v26 = 0;
LABEL_59:
          _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v12, "CSmartSession::SafeCopyString");
          LocalFree(v27);
          v3 = v35;
          goto LABEL_61;
        }
        do
        {
          if ( !v10 )
            break;
          if ( !*v21 )
            break;
          *v26++ = *v21++;
          --v10;
          --v28;
        }
        while ( v28 );
        v29 = v26 - 1;
        if ( v28 )
        {
          v29 = v26;
          v12 = 0;
        }
        *v29 = 0;
      }
      v11 = v12;
      if ( v12 >= 0 )
      {
        v7 = a2;
        v4 = (unsigned __int16 *)v27;
        v3 = v35;
LABEL_38:
        *v7 = v3;
        *a3 = v4;
        return (unsigned int)v12;
      }
      v24 = v12;
      goto LABEL_59;
    }
    v11 = v20;
    goto LABEL_51;
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800053f0  mov     rax, rsp
0x1800053f3  mov     [rax+18h], r8
0x1800053f7  mov     [rax+10h], rdx
0x1800053fb  push    rbx
0x1800053fc  push    rbp
0x1800053fd  push    rsi
0x1800053fe  push    rdi
0x1800053ff  push    r12
0x180005401  push    r13
0x180005403  push    r14
0x180005405  push    r15
0x180005407  sub     rsp, 38h
0x18000540b  xor     esi, esi
0x18000540d  xor     r13d, r13d
0x180005410  mov     [rax+8], rsi
0x180005414  mov     rbx, r8
0x180005417  cmp     dword ptr [rcx+11Ch], 1
0x18000541e  mov     rdi, rdx
0x180005421  mov     r14, rcx
0x180005424  mov     [rax+20h], rsi
0x180005428  mov     [rax-58h], r13
0x18000542c  jz      loc_180005620
0x180005432  cmp     dword ptr [rcx+118h], 1
0x180005439  jnz     loc_180005824
0x18000543f  mov     rbx, [rcx+10h]
0x180005443  mov     ebp, 7FFFFFFEh
0x180005448  mov     r12d, 80070057h
0x18000544e  mov     r15d, 8007007Ah
0x180005454  test    rbx, rbx
0x180005457  jz      loc_180005525
0x18000545d  mov     ecx, 7FFFFFFFh
0x180005462  mov     rax, rbx
0x180005465  cmp     [rax], si
0x180005468  jz      short loc_180005474
0x18000546a  add     rax, 2
0x18000546e  sub     rcx, 1
0x180005472  jnz     short loc_180005465
0x180005474  xor     eax, eax
0x180005476  mov     r8d, r12d
0x180005479  test    rcx, rcx
0x18000547c  cmovnz  r8d, eax
0x180005480  jz      loc_18000571E
0x180005486  mov     edi, 7FFFFFFFh
0x18000548b  sub     rdi, rcx
0x18000548e  mov     ecx, 40h ; '@'; uFlags
0x180005493  lea     rdx, ds:2[rdi*2]; uBytes
0x18000549b  call    cs:__imp_LocalAlloc
0x1800054a1  mov     rsi, rax
0x1800054a4  test    rax, rax
0x1800054a7  jz      loc_1800056A9
0x1800054ad  lea     rdx, [rdi+1]
0x1800054b1  test    rdx, rdx
0x1800054b4  jz      loc_1800056DB
0x1800054ba  cmp     rdx, 7FFFFFFFh
0x1800054c1  ja      loc_1800056D6
0x1800054c7  mov     rax, rbp
0x1800054ca  mov     r8, rsi
0x1800054cd  nop     dword ptr [rax]
0x1800054d0  test    rax, rax
0x1800054d3  jz      short loc_1800054F2
0x1800054d5  movzx   ecx, word ptr [rbx]
0x1800054d8  test    cx, cx
0x1800054db  jz      short loc_1800054F2
0x1800054dd  mov     [r8], cx
0x1800054e1  add     rbx, 2
0x1800054e5  add     r8, 2
0x1800054e9  dec     rax
0x1800054ec  sub     rdx, 1
0x1800054f0  jnz     short loc_1800054D0
0x1800054f2  lea     rcx, [r8-2]
0x1800054f6  test    rdx, rdx
0x1800054f9  cmovnz  rcx, r8
0x1800054fd  xor     eax, eax
0x1800054ff  test    rdx, rdx
0x180005502  mov     r8d, r15d
0x180005505  cmovnz  r8d, eax
0x180005509  mov     [rcx], ax
0x18000550c  test    r8d, r8d
0x18000550f  js      loc_1800056EE
0x180005515  mov     rdi, [rsp+78h+arg_8]
0x18000551d  mov     [rsp+78h+arg_0], rsi
0x180005525  mov     rbx, [r14+18h]
0x180005529  test    rbx, rbx
0x18000552c  jz      loc_18000561B
0x180005532  mov     edx, 7FFFFFFFh
0x180005537  mov     rax, rbx
0x18000553a  nop     word ptr [rax+rax+00h]
0x180005540  cmp     [rax], r13w
0x180005544  jz      short loc_180005550
0x180005546  add     rax, 2
0x18000554a  sub     rdx, 1
0x18000554e  jnz     short loc_180005540
0x180005550  xor     eax, eax
0x180005552  mov     edi, r12d
0x180005555  test    rdx, rdx
0x180005558  cmovnz  edi, eax
0x18000555b  jz      loc_1800057C8
0x180005561  mov     edi, 7FFFFFFFh
0x180005566  mov     ecx, 40h ; '@'; uFlags
0x18000556b  sub     rdi, rdx
0x18000556e  lea     rdx, ds:2[rdi*2]; uBytes
0x180005576  call    cs:__imp_LocalAlloc
0x18000557c  mov     rsi, rax
0x18000557f  test    rax, rax
0x180005582  jz      loc_18000574A
0x180005588  lea     rdx, [rdi+1]
0x18000558c  test    rdx, rdx
0x18000558f  jz      loc_18000577F
0x180005595  cmp     rdx, 7FFFFFFFh
0x18000559c  ja      loc_18000577A
0x1800055a2  test    rbp, rbp
0x1800055a5  jz      short loc_1800055C3
0x1800055a7  movzx   ecx, word ptr [rbx]
0x1800055aa  test    cx, cx
0x1800055ad  jz      short loc_1800055C3
0x1800055af  mov     [rax], cx
0x1800055b2  add     rbx, 2
0x1800055b6  add     rax, 2
0x1800055ba  dec     rbp
0x1800055bd  sub     rdx, 1
0x1800055c1  jnz     short loc_1800055A2
0x1800055c3  test    rdx, rdx
0x1800055c6  lea     rcx, [rax-2]
0x1800055ca  cmovnz  rcx, rax; this
0x1800055ce  xor     eax, eax
0x1800055d0  test    rdx, rdx
0x1800055d3  cmovnz  r15d, eax
0x1800055d7  mov     [rcx], ax
0x1800055da  mov     r12d, r15d
0x1800055dd  test    r15d, r15d
0x1800055e0  js      loc_180005795
0x1800055e6  mov     rdi, [rsp+78h+arg_8]
0x1800055ee  mov     r13, rsi
0x1800055f1  mov     rsi, [rsp+78h+arg_0]
0x1800055f9  mov     rax, [rsp+78h+arg_10]
0x180005601  mov     [rdi], rsi
0x180005604  mov     [rax], r13
0x180005607  mov     eax, r15d
0x18000560a  add     rsp, 38h
0x18000560e  pop     r15
0x180005610  pop     r14
0x180005612  pop     r13
0x180005614  pop     r12
0x180005616  pop     rdi
0x180005617  pop     rsi
0x180005618  pop     rbp
0x180005619  pop     rbx
0x18000561a  retn
0x18000561b  xor     r15d, r15d
0x18000561e  jmp     short loc_1800055F9
0x180005620  cmp     dword ptr [rcx+48h], 1
0x180005624  jnz     loc_180005824
0x18000562a  lea     rdx, [rcx+0BEh]; unsigned __int16 *
0x180005631  lea     r8, [rsp+78h+hMem]; unsigned __int16 **
0x180005639  call    ?SafeCopyString@CSmartSession@@AEAAJPEBGPEAPEAG@Z; CSmartSession::SafeCopyString(ushort const *,ushort * *)
0x18000563e  mov     r12d, eax
0x180005641  test    eax, eax
0x180005643  jns     short loc_180005660
0x180005645  mov     rsi, [rsp+78h+hMem]
0x18000564d  lea     rdx, aSafecopystring_0; "SafeCopyString on user name failed: 0x%"...
0x180005654  mov     ebx, 8
0x180005659  mov     edi, eax
0x18000565b  jmp     loc_1800057EF
0x180005660  lea     rdx, [r14+9Ah]; unsigned __int16 *
0x180005667  lea     r8, [rsp+78h+var_58]; unsigned __int16 **
0x18000566c  call    ?SafeCopyString@CSmartSession@@AEAAJPEBGPEAPEAG@Z; CSmartSession::SafeCopyString(ushort const *,ushort * *)
0x180005671  mov     r12d, eax
0x180005674  test    eax, eax
0x180005676  jns     short loc_180005691
0x180005678  mov     rsi, [rsp+78h+hMem]
0x180005680  mov     ebx, 8
0x180005685  mov     r13, [rsp+78h+var_58]
0x18000568a  mov     edi, eax
0x18000568c  jmp     loc_1800057E8
0x180005691  mov     rax, [rsp+78h+hMem]
0x180005699  mov     [rdi], rax
0x18000569c  mov     rax, [rsp+78h+var_58]
0x1800056a1  mov     [rbx], rax
0x1800056a4  jmp     loc_18000581C
0x1800056a9  mov     r12d, 8007000Eh
0x1800056af  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x1800056b6  mov     ebx, 8
0x1800056bb  lea     rdx, aMidlUserAlloca; "MIDL_user_allocate failed: 0x%x in %s"
0x1800056c2  mov     r8d, r12d
0x1800056c5  mov     ecx, ebx; int
0x1800056c7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800056cc  mov     rsi, [rsp+78h+arg_0]
0x1800056d4  jmp     short loc_18000573B
0x1800056d6  mov     r8d, r12d
0x1800056d9  jmp     short loc_1800056E7
0x1800056db  mov     r8d, r12d
0x1800056de  test    rdx, rdx
0x1800056e1  jz      loc_18000550C
0x1800056e7  xor     eax, eax
0x1800056e9  mov     [rsi], ax
0x1800056ec  jmp     short loc_1800056F1
0x1800056ee  mov     r12d, r8d
0x1800056f1  mov     ebx, 8
0x1800056f6  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x1800056fd  mov     ecx, ebx; int
0x1800056ff  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x180005706  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000570b  mov     rcx, rsi; hMem
0x18000570e  call    cs:__imp_LocalFree
0x180005714  mov     rsi, [rsp+78h+arg_0]
0x18000571c  jmp     short loc_18000573B
0x18000571e  mov     ebx, 8
0x180005723  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x18000572a  mov     ecx, ebx; int
0x18000572c  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x180005733  mov     r12d, r8d
0x180005736  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000573b  lea     rdx, aSafecopystring_0; "SafeCopyString on user name failed: 0x%"...
0x180005742  mov     edi, r12d
0x180005745  jmp     loc_1800057EF
0x18000574a  mov     r12d, 8007000Eh
0x180005750  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180005757  mov     ebx, 8
0x18000575c  lea     rdx, aMidlUserAlloca; "MIDL_user_allocate failed: 0x%x in %s"
0x180005763  mov     r8d, r12d
0x180005766  mov     ecx, ebx; int
0x180005768  mov     edi, r12d
0x18000576b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005770  mov     rsi, [rsp+78h+arg_0]
0x180005778  jmp     short loc_1800057E8
0x18000577a  mov     r15d, r12d
0x18000577d  jmp     short loc_18000578B
0x18000577f  mov     r15d, r12d
0x180005782  test    rdx, rdx
0x180005785  jz      loc_1800055DA
0x18000578b  xor     eax, eax
0x18000578d  mov     edi, r12d
0x180005790  mov     [rsi], ax
0x180005793  jmp     short loc_180005798
0x180005795  mov     edi, r15d
0x180005798  mov     ebx, 8
0x18000579d  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x1800057a4  mov     ecx, ebx; int
0x1800057a6  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x1800057ad  mov     r8d, r15d
0x1800057b0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800057b5  mov     rcx, rsi; hMem
0x1800057b8  call    cs:__imp_LocalFree
0x1800057be  mov     rsi, [rsp+78h+arg_0]
0x1800057c6  jmp     short loc_1800057E8
0x1800057c8  mov     ebx, 8
0x1800057cd  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x1800057d4  mov     ecx, ebx; int
0x1800057d6  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x1800057dd  mov     r8d, edi
0x1800057e0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800057e5  mov     r12d, edi
0x1800057e8  lea     rdx, aSafecopystring; "SafeCopyString on domainname failed: 0x"...
0x1800057ef  lea     r9, aCsmartsessionG_0; "CSmartSession::GetUserNameFromSessionIn"...
0x1800057f6  mov     r8d, edi
0x1800057f9  mov     ecx, ebx; int
0x1800057fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005800  test    rsi, rsi
0x180005803  jz      short loc_18000580E
0x180005805  mov     rcx, rsi; hMem
0x180005808  call    cs:__imp_LocalFree
0x18000580e  test    r13, r13
0x180005811  jz      short loc_18000581C
0x180005813  mov     rcx, r13; hMem
0x180005816  call    cs:__imp_LocalFree
0x18000581c  mov     eax, r12d
0x18000581f  jmp     loc_18000560A
0x180005824  mov     eax, 80004001h
0x180005829  jmp     loc_18000560A
```
