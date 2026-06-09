# CSmartSession::GetUserNameFromSessionInformation(ushort * *,ushort * *)

- ea: `0x1800038c0`
- end: `0x180003d1d`
- name: `?GetUserNameFromSessionInformation@CSmartSession@@AEAAJPEAPEAG0@Z`
- size: `1117`
- prototype: `__int64 __fastcall(CSmartSession *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005180`

## callees

- `0x1800038c0`
- `0x180005b40`
- `0x18000daa0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000396b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000396b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003be5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ceb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003cff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003be5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ceb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003cff`

## string_xrefs

- `0x180003bd6`: `StringCchCopy failed: 0x%x in %s`
- `0x180003c83`: `StringCchCopy failed: 0x%x in %s`
- `0x180003b86`: `CSmartSession::SafeCopyString`
- `0x180003bcd`: `CSmartSession::SafeCopyString`
- `0x180003c00`: `CSmartSession::SafeCopyString`
- `0x180003c2d`: `CSmartSession::SafeCopyString`
- `0x180003c7a`: `CSmartSession::SafeCopyString`
- `0x180003cb0`: `CSmartSession::SafeCopyString`
- `0x180003b24`: `SafeCopyString on user name failed: 0x%x in %s`
- `0x180003c18`: `SafeCopyString on user name failed: 0x%x in %s`
- `0x180003ccb`: `SafeCopyString on domainname failed: 0x%x in %s`

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
0x1800038c0  mov     rax, rsp
0x1800038c3  mov     [rax+18h], r8
0x1800038c7  mov     [rax+10h], rdx
0x1800038cb  push    rbx
0x1800038cc  push    rbp
0x1800038cd  push    rsi
0x1800038ce  push    rdi
0x1800038cf  push    r12
0x1800038d1  push    r13
0x1800038d3  push    r14
0x1800038d5  push    r15
0x1800038d7  sub     rsp, 38h
0x1800038db  xor     esi, esi
0x1800038dd  xor     r13d, r13d
0x1800038e0  mov     [rax+8], rsi
0x1800038e4  mov     rbx, r8
0x1800038e7  cmp     dword ptr [rcx+11Ch], 1
0x1800038ee  mov     rdi, rdx
0x1800038f1  mov     r14, rcx
0x1800038f4  mov     [rax+20h], rsi
0x1800038f8  mov     [rax-58h], r13
0x1800038fc  jz      loc_180003AF7
0x180003902  cmp     dword ptr [rcx+118h], 1
0x180003909  jnz     loc_180003D13
0x18000390f  mov     rbx, [rcx+10h]
0x180003913  mov     ebp, 7FFFFFFEh
0x180003918  mov     r12d, 80070057h
0x18000391e  mov     r15d, 8007007Ah
0x180003924  test    rbx, rbx
0x180003927  jz      loc_1800039F8
0x18000392d  mov     ecx, 7FFFFFFFh
0x180003932  mov     rax, rbx
0x180003935  cmp     [rax], si
0x180003938  jz      short loc_180003944
0x18000393a  add     rax, 2
0x18000393e  sub     rcx, 1
0x180003942  jnz     short loc_180003935
0x180003944  xor     eax, eax
0x180003946  mov     r8d, r12d
0x180003949  test    rcx, rcx
0x18000394c  cmovnz  r8d, eax
0x180003950  jz      loc_180003BFB
0x180003956  mov     edi, 7FFFFFFFh
0x18000395b  sub     rdi, rcx
0x18000395e  mov     ecx, 40h ; '@'; uFlags
0x180003963  lea     rdx, ds:2[rdi*2]; uBytes
0x18000396b  call    cs:__imp_LocalAlloc
0x180003972  nop     dword ptr [rax+rax+00h]
0x180003977  mov     rsi, rax
0x18000397a  test    rax, rax
0x18000397d  jz      loc_180003B80
0x180003983  lea     rdx, [rdi+1]
0x180003987  test    rdx, rdx
0x18000398a  jz      loc_180003BB2
0x180003990  cmp     rdx, 7FFFFFFFh
0x180003997  ja      loc_180003BAD
0x18000399d  mov     rax, rbp
0x1800039a0  mov     r8, rsi
0x1800039a3  test    rax, rax
0x1800039a6  jz      short loc_1800039C5
0x1800039a8  movzx   ecx, word ptr [rbx]
0x1800039ab  test    cx, cx
0x1800039ae  jz      short loc_1800039C5
0x1800039b0  mov     [r8], cx
0x1800039b4  add     rbx, 2
0x1800039b8  add     r8, 2
0x1800039bc  dec     rax
0x1800039bf  sub     rdx, 1
0x1800039c3  jnz     short loc_1800039A3
0x1800039c5  lea     rcx, [r8-2]
0x1800039c9  test    rdx, rdx
0x1800039cc  cmovnz  rcx, r8
0x1800039d0  xor     eax, eax
0x1800039d2  test    rdx, rdx
0x1800039d5  mov     r8d, r15d
0x1800039d8  cmovnz  r8d, eax
0x1800039dc  mov     [rcx], ax
0x1800039df  test    r8d, r8d
0x1800039e2  js      loc_180003BC5
0x1800039e8  mov     rdi, [rsp+78h+arg_8]
0x1800039f0  mov     [rsp+78h+arg_0], rsi
0x1800039f8  mov     rbx, [r14+18h]
0x1800039fc  test    rbx, rbx
0x1800039ff  jz      loc_180003AF2
0x180003a05  mov     edx, 7FFFFFFFh
0x180003a0a  mov     rax, rbx
0x180003a0d  nop     dword ptr [rax]
0x180003a10  cmp     [rax], r13w
0x180003a14  jz      short loc_180003A20
0x180003a16  add     rax, 2
0x180003a1a  sub     rdx, 1
0x180003a1e  jnz     short loc_180003A10
0x180003a20  xor     eax, eax
0x180003a22  mov     edi, r12d
0x180003a25  test    rdx, rdx
0x180003a28  cmovnz  edi, eax
0x180003a2b  jz      loc_180003CAB
0x180003a31  mov     edi, 7FFFFFFFh
0x180003a36  mov     ecx, 40h ; '@'; uFlags
0x180003a3b  sub     rdi, rdx
0x180003a3e  lea     rdx, ds:2[rdi*2]; uBytes
0x180003a46  call    cs:__imp_LocalAlloc
0x180003a4d  nop     dword ptr [rax+rax+00h]
0x180003a52  mov     rsi, rax
0x180003a55  test    rax, rax
0x180003a58  jz      loc_180003C27
0x180003a5e  lea     rdx, [rdi+1]
0x180003a62  test    rdx, rdx
0x180003a65  jz      loc_180003C5C
0x180003a6b  cmp     rdx, 7FFFFFFFh
0x180003a72  ja      loc_180003C57
0x180003a78  test    rbp, rbp
0x180003a7b  jz      short loc_180003A99
0x180003a7d  movzx   ecx, word ptr [rbx]
0x180003a80  test    cx, cx
0x180003a83  jz      short loc_180003A99
0x180003a85  mov     [rax], cx
0x180003a88  add     rbx, 2
0x180003a8c  add     rax, 2
0x180003a90  dec     rbp
0x180003a93  sub     rdx, 1
0x180003a97  jnz     short loc_180003A78
0x180003a99  test    rdx, rdx
0x180003a9c  lea     rcx, [rax-2]
0x180003aa0  cmovnz  rcx, rax; this
0x180003aa4  xor     eax, eax
0x180003aa6  test    rdx, rdx
0x180003aa9  cmovnz  r15d, eax
0x180003aad  mov     [rcx], ax
0x180003ab0  mov     r12d, r15d
0x180003ab3  test    r15d, r15d
0x180003ab6  js      loc_180003C72
0x180003abc  mov     rdi, [rsp+78h+arg_8]
0x180003ac4  mov     r13, rsi
0x180003ac7  mov     rsi, [rsp+78h+arg_0]
0x180003acf  mov     rax, [rsp+78h+arg_10]
0x180003ad7  mov     [rdi], rsi
0x180003ada  mov     [rax], r13
0x180003add  mov     eax, r15d
0x180003ae0  add     rsp, 38h
0x180003ae4  pop     r15
0x180003ae6  pop     r14
0x180003ae8  pop     r13
0x180003aea  pop     r12
0x180003aec  pop     rdi
0x180003aed  pop     rsi
0x180003aee  pop     rbp
0x180003aef  pop     rbx
0x180003af0  retn
0x180003af2  xor     r15d, r15d
0x180003af5  jmp     short loc_180003ACF
0x180003af7  cmp     dword ptr [rcx+48h], 1
0x180003afb  jnz     loc_180003D13
0x180003b01  lea     rdx, [rcx+0BEh]; unsigned __int16 *
0x180003b08  lea     r8, [rsp+78h+hMem]; unsigned __int16 **
0x180003b10  call    ?SafeCopyString@CSmartSession@@AEAAJPEBGPEAPEAG@Z; CSmartSession::SafeCopyString(ushort const *,ushort * *)
0x180003b15  mov     r12d, eax
0x180003b18  test    eax, eax
0x180003b1a  jns     short loc_180003B37
0x180003b1c  mov     rsi, [rsp+78h+hMem]
0x180003b24  lea     rdx, aSafecopystring_0; "SafeCopyString on user name failed: 0x%"...
0x180003b2b  mov     ebx, 8
0x180003b30  mov     edi, eax
0x180003b32  jmp     loc_180003CD2
0x180003b37  lea     rdx, [r14+9Ah]; unsigned __int16 *
0x180003b3e  lea     r8, [rsp+78h+var_58]; unsigned __int16 **
0x180003b43  call    ?SafeCopyString@CSmartSession@@AEAAJPEBGPEAPEAG@Z; CSmartSession::SafeCopyString(ushort const *,ushort * *)
0x180003b48  mov     r12d, eax
0x180003b4b  test    eax, eax
0x180003b4d  jns     short loc_180003B68
0x180003b4f  mov     rsi, [rsp+78h+hMem]
0x180003b57  mov     ebx, 8
0x180003b5c  mov     r13, [rsp+78h+var_58]
0x180003b61  mov     edi, eax
0x180003b63  jmp     loc_180003CCB
0x180003b68  mov     rax, [rsp+78h+hMem]
0x180003b70  mov     [rdi], rax
0x180003b73  mov     rax, [rsp+78h+var_58]
0x180003b78  mov     [rbx], rax
0x180003b7b  jmp     loc_180003D0B
0x180003b80  mov     r12d, 8007000Eh
0x180003b86  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180003b8d  mov     ebx, 8
0x180003b92  lea     rdx, aMidlUserAlloca; "MIDL_user_allocate failed: 0x%x in %s"
0x180003b99  mov     r8d, r12d
0x180003b9c  mov     ecx, ebx; int
0x180003b9e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003ba3  mov     rsi, [rsp+78h+arg_0]
0x180003bab  jmp     short loc_180003C18
0x180003bad  mov     r8d, r12d
0x180003bb0  jmp     short loc_180003BBE
0x180003bb2  mov     r8d, r12d
0x180003bb5  test    rdx, rdx
0x180003bb8  jz      loc_1800039DF
0x180003bbe  xor     eax, eax
0x180003bc0  mov     [rsi], ax
0x180003bc3  jmp     short loc_180003BC8
0x180003bc5  mov     r12d, r8d
0x180003bc8  mov     ebx, 8
0x180003bcd  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180003bd4  mov     ecx, ebx; int
0x180003bd6  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x180003bdd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003be2  mov     rcx, rsi; hMem
0x180003be5  call    cs:__imp_LocalFree
0x180003bec  nop     dword ptr [rax+rax+00h]
0x180003bf1  mov     rsi, [rsp+78h+arg_0]
0x180003bf9  jmp     short loc_180003C18
0x180003bfb  mov     ebx, 8
0x180003c00  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180003c07  mov     ecx, ebx; int
0x180003c09  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x180003c10  mov     r12d, r8d
0x180003c13  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003c18  lea     rdx, aSafecopystring_0; "SafeCopyString on user name failed: 0x%"...
0x180003c1f  mov     edi, r12d
0x180003c22  jmp     loc_180003CD2
0x180003c27  mov     r12d, 8007000Eh
0x180003c2d  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180003c34  mov     ebx, 8
0x180003c39  lea     rdx, aMidlUserAlloca; "MIDL_user_allocate failed: 0x%x in %s"
0x180003c40  mov     r8d, r12d
0x180003c43  mov     ecx, ebx; int
0x180003c45  mov     edi, r12d
0x180003c48  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003c4d  mov     rsi, [rsp+78h+arg_0]
0x180003c55  jmp     short loc_180003CCB
0x180003c57  mov     r15d, r12d
0x180003c5a  jmp     short loc_180003C68
0x180003c5c  mov     r15d, r12d
0x180003c5f  test    rdx, rdx
0x180003c62  jz      loc_180003AB0
0x180003c68  xor     eax, eax
0x180003c6a  mov     edi, r12d
0x180003c6d  mov     [rsi], ax
0x180003c70  jmp     short loc_180003C75
0x180003c72  mov     edi, r15d
0x180003c75  mov     ebx, 8
0x180003c7a  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180003c81  mov     ecx, ebx; int
0x180003c83  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x180003c8a  mov     r8d, r15d
0x180003c8d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003c92  mov     rcx, rsi; hMem
0x180003c95  call    cs:__imp_LocalFree
0x180003c9c  nop     dword ptr [rax+rax+00h]
0x180003ca1  mov     rsi, [rsp+78h+arg_0]
0x180003ca9  jmp     short loc_180003CCB
0x180003cab  mov     ebx, 8
0x180003cb0  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180003cb7  mov     ecx, ebx; int
0x180003cb9  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x180003cc0  mov     r8d, edi
0x180003cc3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003cc8  mov     r12d, edi
0x180003ccb  lea     rdx, aSafecopystring; "SafeCopyString on domainname failed: 0x"...
0x180003cd2  lea     r9, aCsmartsessionG_0; "CSmartSession::GetUserNameFromSessionIn"...
0x180003cd9  mov     r8d, edi
0x180003cdc  mov     ecx, ebx; int
0x180003cde  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003ce3  test    rsi, rsi
0x180003ce6  jz      short loc_180003CF7
0x180003ce8  mov     rcx, rsi; hMem
0x180003ceb  call    cs:__imp_LocalFree
0x180003cf2  nop     dword ptr [rax+rax+00h]
0x180003cf7  test    r13, r13
0x180003cfa  jz      short loc_180003D0B
0x180003cfc  mov     rcx, r13; hMem
0x180003cff  call    cs:__imp_LocalFree
0x180003d06  nop     dword ptr [rax+rax+00h]
0x180003d0b  mov     eax, r12d
0x180003d0e  jmp     loc_180003AE0
0x180003d13  mov     eax, 80004001h
0x180003d18  jmp     loc_180003AE0
```
