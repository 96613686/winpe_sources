# add_connection

- ea: `0x180008ef4`
- end: `0x18000934b`
- name: `add_connection`
- size: `1111`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007b90`
- `0x180008570`

## callees

- `0x180003f3c`
- `0x180005730`
- `0x180008ef4`
- `0x180009c40`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180009091`
- `OLEAUT32!__imp_SysFreeString` at `0x18000909a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009091`
- `OLEAUT32!__imp_SysFreeString` at `0x18000909a`
- `OLEAUT32!__imp_SysStringLen` at `0x180009198`
- `OLEAUT32!__imp_SysStringLen` at `0x180009237`
- `OLEAUT32!__imp_SysStringLen` at `0x180009198`
- `OLEAUT32!__imp_SysStringLen` at `0x180009237`
- `KERNEL32!GetLastError` at `0x180009079`
- `KERNEL32!GetLastError` at `0x180009079`
- `KERNEL32!WideCharToMultiByte` at `0x18000906c`
- `KERNEL32!WideCharToMultiByte` at `0x1800090fe`
- `KERNEL32!WideCharToMultiByte` at `0x180009129`
- `KERNEL32!WideCharToMultiByte` at `0x180009187`
- `KERNEL32!WideCharToMultiByte` at `0x1800091c3`
- `KERNEL32!WideCharToMultiByte` at `0x180009222`
- `KERNEL32!WideCharToMultiByte` at `0x180009263`
- `KERNEL32!WideCharToMultiByte` at `0x1800092c5`
- `KERNEL32!WideCharToMultiByte` at `0x18000906c`
- `KERNEL32!WideCharToMultiByte` at `0x1800090fe`
- `KERNEL32!WideCharToMultiByte` at `0x180009129`
- `KERNEL32!WideCharToMultiByte` at `0x180009187`
- `KERNEL32!WideCharToMultiByte` at `0x1800091c3`
- `KERNEL32!WideCharToMultiByte` at `0x180009222`
- `KERNEL32!WideCharToMultiByte` at `0x180009263`
- `KERNEL32!WideCharToMultiByte` at `0x1800092c5`
- `MPR!WNetAddConnection2W` at `0x180009041`
- `MPR!WNetAddConnection2W` at `0x180009041`
- `MPR!WNetAddConnection2A` at `0x18000930e`
- `MPR!WNetAddConnection2A` at `0x18000930e`

## pseudocode

```c
__int64 __fastcall add_connection(
        DWORD a1,
        WCHAR *a2,
        WCHAR *a3,
        const struct tagVARIANT *a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6)
{
  signed int v8; // ebx
  WCHAR *v9; // r12
  unsigned __int16 *v10; // r15
  VARIANTARG *v11; // rcx
  VARIANTARG *v12; // rcx
  int v13; // eax
  DWORD *v14; // rdi
  VARIANTARG *v15; // rcx
  int v16; // eax
  signed int LastError; // eax
  int cbMultiByte; // eax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  int v24; // eax
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  void *v27; // rsp
  void *v28; // rsp
  int v29; // eax
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  void *v32; // rsp
  void *v33; // rsp
  DWORD *v34; // rsi
  int v35; // eax
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  void *v38; // rsp
  void *v39; // rsp
  _BYTE v40[32]; // [rsp+0h] [rbp-40h] BYREF
  DWORD dwFlags; // [rsp+40h] [rbp+0h] BYREF
  int v42; // [rsp+44h] [rbp+4h] BYREF
  DWORD v43; // [rsp+48h] [rbp+8h]
  unsigned __int16 *p_dwFlags; // [rsp+50h] [rbp+10h] BYREF
  LPCWSTR lpUserName; // [rsp+58h] [rbp+18h] BYREF
  _NETRESOURCEW NetResource; // [rsp+60h] [rbp+20h] BYREF

  v43 = a1;
  if ( a3 && a2 && a4 && a5 && a6 )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
    dwFlags = 0;
    lpUserName = 0;
    p_dwFlags = 0;
    if ( fOptionalArgSupplied(a4) )
    {
      v42 = 0;
      v8 = Variant_BOOL(v11, &v42);
      if ( v8 < 0 )
        goto LABEL_24;
      dwFlags = v42 != 0;
    }
    if ( fOptionalArgSupplied(a5) && a5->vt && a5->vt != 1 )
    {
      v13 = Variant_BSTR(v12, (unsigned __int16 **)&lpUserName);
      v9 = (WCHAR *)lpUserName;
      v14 = 0;
      v8 = v13;
      if ( v13 < 0 )
        goto LABEL_24;
    }
    else
    {
      v14 = 0;
    }
    if ( fOptionalArgSupplied(a6) )
    {
      if ( a6->vt )
      {
        if ( a6->vt != 1 )
        {
          v16 = Variant_BSTR(v15, &p_dwFlags);
          v10 = p_dwFlags;
          v8 = v16;
          if ( v16 < 0 )
            goto LABEL_24;
        }
      }
    }
    if ( Global::g_fWindowsNT )
    {
      NetResource.dwScope = 0;
      NetResource.dwType = v43;
      *(_OWORD *)&NetResource.lpComment = 0;
      *(_QWORD *)&NetResource.dwDisplayType = 0;
      NetResource.lpLocalName = a2;
      NetResource.lpRemoteName = a3;
      LastError = WNetAddConnection2W(&NetResource, v10, v9, dwFlags);
LABEL_52:
      if ( !LastError )
        goto LABEL_24;
      if ( LastError <= 0 )
      {
        v8 = LastError;
        goto LABEL_24;
      }
      goto LABEL_23;
    }
    cbMultiByte = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
    if ( !cbMultiByte )
    {
LABEL_22:
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
LABEL_23:
        v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_24:
      SysFreeString(v9);
      SysFreeString(v10);
      return (unsigned int)v8;
    }
    v20 = cbMultiByte + 15LL;
    if ( v20 < cbMultiByte )
      v20 = 0xFFFFFFFFFFFFFF0LL;
    v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
    v22 = alloca(v21);
    v23 = alloca(v21);
    p_dwFlags = (unsigned __int16 *)&dwFlags;
    if ( &dwFlags )
    {
      if ( !WideCharToMultiByte(0, 0, a2, -1, (LPSTR)&dwFlags, cbMultiByte, 0, 0) )
        goto LABEL_22;
      v24 = WideCharToMultiByte(0, 0, a3, -1, 0, 0, 0, 0);
      if ( !v24 )
        goto LABEL_22;
      v25 = v24 + 15LL;
      if ( v25 < v24 )
        v25 = 0xFFFFFFFFFFFFFF0LL;
      v26 = v25 & 0xFFFFFFFFFFFFFFF0uLL;
      v27 = alloca(v26);
      v28 = alloca(v26);
      if ( v40 != (_BYTE *)-64LL )
      {
        if ( !WideCharToMultiByte(0, 0, a3, -1, (LPSTR)&dwFlags, v24, 0, 0) )
          goto LABEL_22;
        if ( SysStringLen(v9) )
        {
          v29 = WideCharToMultiByte(0, 0, v9, -1, 0, 0, 0, 0);
          if ( !v29 )
            goto LABEL_22;
          v30 = v29 + 15LL;
          if ( v30 < v29 )
            v30 = 0xFFFFFFFFFFFFFF0LL;
          v31 = v30 & 0xFFFFFFFFFFFFFFF0uLL;
          v32 = alloca(v31);
          v33 = alloca(v31);
          v34 = &dwFlags;
          if ( v40 == (_BYTE *)-64LL )
            goto LABEL_28;
          if ( !WideCharToMultiByte(0, 0, v9, -1, (LPSTR)&dwFlags, v29, 0, 0) )
            goto LABEL_22;
        }
        else
        {
          v34 = 0;
        }
        if ( !SysStringLen(v10) )
        {
          v34 = 0;
          goto LABEL_51;
        }
        v35 = WideCharToMultiByte(0, 0, v10, -1, 0, 0, 0, 0);
        if ( !v35 )
          goto LABEL_22;
        v36 = v35 + 15LL;
        if ( v36 < v35 )
          v36 = 0xFFFFFFFFFFFFFF0LL;
        v37 = v36 & 0xFFFFFFFFFFFFFFF0uLL;
        v38 = alloca(v37);
        v39 = alloca(v37);
        v14 = &dwFlags;
        if ( v40 != (_BYTE *)-64LL )
        {
          if ( !WideCharToMultiByte(0, 0, v10, -1, (LPSTR)&dwFlags, v35, 0, 0) )
            goto LABEL_22;
LABEL_51:
          NetResource.dwType = v43;
          NetResource.lpLocalName = p_dwFlags;
          NetResource.dwScope = 0;
          *(_QWORD *)&NetResource.dwDisplayType = 0;
          NetResource.lpRemoteName = (LPWSTR)&dwFlags;
          *(_OWORD *)&NetResource.lpComment = 0;
          LastError = WNetAddConnection2A((LPNETRESOURCEA)&NetResource, (LPCSTR)v14, (LPCSTR)v34, dwFlags);
          goto LABEL_52;
        }
      }
    }
LABEL_28:
    v8 = -2147024882;
    goto LABEL_24;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180008ef4  push    rbp
0x180008ef6  push    rbx
0x180008ef7  push    rsi
0x180008ef8  push    rdi
0x180008ef9  push    r12
0x180008efb  push    r13
0x180008efd  push    r14
0x180008eff  push    r15
0x180008f01  sub     rsp, 0A8h
0x180008f08  lea     rbp, [rsp+40h]
0x180008f0d  mov     rax, cs:__security_cookie
0x180008f14  xor     rax, rbp
0x180008f17  mov     [rbp+0A0h+var_50], rax
0x180008f1b  mov     [rbp+0A0h+var_98], ecx
0x180008f1e  mov     r13, r8
0x180008f21  mov     r14, rdx
0x180008f24  test    r8, r8
0x180008f27  jz      loc_180009329
0x180008f2d  test    rdx, rdx
0x180008f30  jz      loc_180009329
0x180008f36  test    r9, r9
0x180008f39  jz      loc_180009329
0x180008f3f  mov     rdi, [rbp+0A0h+arg_20]
0x180008f46  test    rdi, rdi
0x180008f49  jz      loc_180009329
0x180008f4f  mov     rsi, [rbp+0A0h+arg_28]
0x180008f56  test    rsi, rsi
0x180008f59  jz      loc_180009329
0x180008f5f  xor     ebx, ebx
0x180008f61  xor     r12d, r12d
0x180008f64  xor     r15d, r15d
0x180008f67  mov     [rbp+0A0h+dwFlags], ebx
0x180008f6a  mov     rcx, r9; struct tagVARIANT *
0x180008f6d  mov     [rbp+0A0h+lpUserName], r12
0x180008f71  mov     [rbp+0A0h+var_90], r15
0x180008f75  call    ?fOptionalArgSupplied@@YA_NPEBUtagVARIANT@@@Z; fOptionalArgSupplied(tagVARIANT const *)
0x180008f7a  test    al, al
0x180008f7c  jz      short loc_180008FA6
0x180008f7e  lea     rdx, [rbp+0A0h+var_9C]; int *
0x180008f82  mov     [rbp+0A0h+var_9C], ebx
0x180008f85  call    ?Variant_BOOL@@YAJPEAUtagVARIANT@@PEAH@Z; Variant_BOOL(tagVARIANT *,int *)
0x180008f8a  mov     ebx, eax
0x180008f8c  test    eax, eax
0x180008f8e  js      loc_18000908E
0x180008f94  cmp     [rbp+0A0h+var_9C], r12d
0x180008f98  lea     eax, [r12+1]
0x180008f9d  mov     edx, r12d
0x180008fa0  cmovnz  edx, eax
0x180008fa3  mov     [rbp+0A0h+dwFlags], edx
0x180008fa6  mov     rcx, rdi; struct tagVARIANT *
0x180008fa9  call    ?fOptionalArgSupplied@@YA_NPEBUtagVARIANT@@@Z; fOptionalArgSupplied(tagVARIANT const *)
0x180008fae  test    al, al
0x180008fb0  jz      short loc_180008FD8
0x180008fb2  movzx   edx, word ptr [rdi]
0x180008fb5  test    edx, edx
0x180008fb7  jz      short loc_180008FD8
0x180008fb9  cmp     edx, 1
0x180008fbc  jz      short loc_180008FD8
0x180008fbe  lea     rdx, [rbp+0A0h+lpUserName]; unsigned __int16 **
0x180008fc2  call    ?Variant_BSTR@@YAJPEAUtagVARIANT@@PEAPEAG@Z; Variant_BSTR(tagVARIANT *,ushort * *)
0x180008fc7  mov     r12, [rbp+0A0h+lpUserName]
0x180008fcb  xor     edi, edi
0x180008fcd  mov     ebx, eax
0x180008fcf  test    eax, eax
0x180008fd1  jns     short loc_180008FDA
0x180008fd3  jmp     loc_18000908E
0x180008fd8  xor     edi, edi
0x180008fda  mov     rcx, rsi; struct tagVARIANT *
0x180008fdd  call    ?fOptionalArgSupplied@@YA_NPEBUtagVARIANT@@@Z; fOptionalArgSupplied(tagVARIANT const *)
0x180008fe2  test    al, al
0x180008fe4  jz      short loc_180009009
0x180008fe6  movzx   edx, word ptr [rsi]
0x180008fe9  test    edx, edx
0x180008feb  jz      short loc_180009009
0x180008fed  cmp     edx, 1
0x180008ff0  jz      short loc_180009009
0x180008ff2  lea     rdx, [rbp+0A0h+var_90]; unsigned __int16 **
0x180008ff6  call    ?Variant_BSTR@@YAJPEAUtagVARIANT@@PEAPEAG@Z; Variant_BSTR(tagVARIANT *,ushort * *)
0x180008ffb  mov     r15, [rbp+0A0h+var_90]
0x180008fff  mov     ebx, eax
0x180009001  test    eax, eax
0x180009003  js      loc_18000908E
0x180009009  cmp     cs:?g_fWindowsNT@Global@@2_NA, dil; bool Global::g_fWindowsNT
0x180009010  jz      short loc_18000904C
0x180009012  mov     eax, [rbp+0A0h+var_98]
0x180009015  lea     rcx, [rbp+0A0h+NetResource]; lpNetResource
0x180009019  mov     r9d, [rbp+0A0h+dwFlags]; dwFlags
0x18000901d  xorps   xmm0, xmm0
0x180009020  mov     r8, r12; lpUserName
0x180009023  mov     [rbp+0A0h+NetResource.dwScope], edi
0x180009026  mov     rdx, r15; lpPassword
0x180009029  mov     [rbp+0A0h+NetResource.dwType], eax
0x18000902c  movdqu  xmmword ptr [rbp+0A0h+NetResource.lpComment], xmm0
0x180009031  mov     qword ptr [rbp+0A0h+NetResource.dwDisplayType], 0
0x180009039  mov     [rbp+0A0h+NetResource.lpLocalName], r14
0x18000903d  mov     [rbp+0A0h+NetResource.lpRemoteName], r13
0x180009041  call    cs:__imp_WNetAddConnection2W
0x180009047  jmp     loc_180009314
0x18000904c  mov     [rsp+0E0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180009051  or      esi, 0FFFFFFFFh
0x180009054  mov     [rsp+0E0h+lpDefaultChar], rdi; lpDefaultChar
0x180009059  mov     r9d, esi; cchWideChar
0x18000905c  mov     [rsp+0E0h+cbMultiByte], edi; cbMultiByte
0x180009060  mov     r8, r14; lpWideCharStr
0x180009063  xor     edx, edx; dwFlags
0x180009065  mov     [rsp+0E0h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000906a  xor     ecx, ecx; CodePage
0x18000906c  call    cs:__imp_WideCharToMultiByte
0x180009072  movsxd  rdx, eax
0x180009075  test    eax, eax
0x180009077  jnz     short loc_1800090A7
0x180009079  call    cs:__imp_GetLastError
0x18000907f  mov     ebx, eax
0x180009081  test    eax, eax
0x180009083  jle     short loc_18000908E
0x180009085  movzx   ebx, ax
0x180009088  or      ebx, 80070000h
0x18000908e  mov     rcx, r12; bstrString
0x180009091  call    cs:__imp_SysFreeString
0x180009097  mov     rcx, r15; bstrString
0x18000909a  call    cs:__imp_SysFreeString
0x1800090a0  mov     eax, ebx
0x1800090a2  jmp     loc_18000932E
0x1800090a7  lea     rcx, [rdx+0Fh]
0x1800090ab  mov     r8, 0FFFFFFFFFFFFFF0h
0x1800090b5  cmp     rcx, rdx
0x1800090b8  ja      short loc_1800090BD
0x1800090ba  mov     rcx, r8
0x1800090bd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800090c1  mov     rax, rcx
0x1800090c4  call    _alloca_probe
0x1800090c9  sub     rsp, rcx
0x1800090cc  lea     rax, [rsp+0E0h+dwFlags]
0x1800090d1  mov     [rbp+0A0h+var_90], rax
0x1800090d5  test    rax, rax
0x1800090d8  jnz     short loc_1800090E1
0x1800090da  mov     ebx, 8007000Eh
0x1800090df  jmp     short loc_18000908E
0x1800090e1  mov     [rsp+0E0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800090e6  mov     r9d, esi; cchWideChar
0x1800090e9  mov     [rsp+0E0h+lpDefaultChar], rdi; lpDefaultChar
0x1800090ee  mov     r8, r14; lpWideCharStr
0x1800090f1  mov     [rsp+0E0h+cbMultiByte], edx; cbMultiByte
0x1800090f5  xor     ecx, ecx; CodePage
0x1800090f7  xor     edx, edx; dwFlags
0x1800090f9  mov     [rsp+0E0h+lpMultiByteStr], rax; lpMultiByteStr
0x1800090fe  call    cs:__imp_WideCharToMultiByte
0x180009104  test    eax, eax
0x180009106  jz      loc_180009079
0x18000910c  mov     [rsp+0E0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180009111  mov     r9d, esi; cchWideChar
0x180009114  mov     [rsp+0E0h+lpDefaultChar], rdi; lpDefaultChar
0x180009119  mov     r8, r13; lpWideCharStr
0x18000911c  mov     [rsp+0E0h+cbMultiByte], edi; cbMultiByte
0x180009120  xor     edx, edx; dwFlags
0x180009122  xor     ecx, ecx; CodePage
0x180009124  mov     [rsp+0E0h+lpMultiByteStr], rdi; lpMultiByteStr
0x180009129  call    cs:__imp_WideCharToMultiByte
0x18000912f  movsxd  rdx, eax
0x180009132  test    eax, eax
0x180009134  jz      loc_180009079
0x18000913a  lea     rcx, [rdx+0Fh]
0x18000913e  cmp     rcx, rdx
0x180009141  ja      short loc_18000914D
0x180009143  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000914d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180009151  mov     rax, rcx
0x180009154  call    _alloca_probe
0x180009159  sub     rsp, rcx
0x18000915c  lea     r14, [rsp+0E0h+dwFlags]
0x180009161  test    r14, r14
0x180009164  jz      loc_1800090DA
0x18000916a  mov     [rsp+0E0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18000916f  mov     r9d, esi; cchWideChar
0x180009172  mov     [rsp+0E0h+lpDefaultChar], rdi; lpDefaultChar
0x180009177  mov     r8, r13; lpWideCharStr
0x18000917a  mov     [rsp+0E0h+cbMultiByte], edx; cbMultiByte
0x18000917e  xor     ecx, ecx; CodePage
0x180009180  xor     edx, edx; dwFlags
0x180009182  mov     [rsp+0E0h+lpMultiByteStr], r14; lpMultiByteStr
0x180009187  call    cs:__imp_WideCharToMultiByte
0x18000918d  test    eax, eax
0x18000918f  jz      loc_180009079
0x180009195  mov     rcx, r12; pbstr
0x180009198  call    cs:__imp_SysStringLen
0x18000919e  test    eax, eax
0x1800091a0  jz      loc_180009231
0x1800091a6  mov     [rsp+0E0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800091ab  mov     r9d, esi; cchWideChar
0x1800091ae  mov     [rsp+0E0h+lpDefaultChar], rdi; lpDefaultChar
0x1800091b3  mov     r8, r12; lpWideCharStr
0x1800091b6  mov     [rsp+0E0h+cbMultiByte], edi; cbMultiByte
0x1800091ba  xor     edx, edx; dwFlags
0x1800091bc  xor     ecx, ecx; CodePage
0x1800091be  mov     [rsp+0E0h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800091c3  call    cs:__imp_WideCharToMultiByte
0x1800091c9  movsxd  rdx, eax
0x1800091cc  test    eax, eax
0x1800091ce  jz      loc_180009079
0x1800091d4  lea     rcx, [rdx+0Fh]
0x1800091d8  cmp     rcx, rdx
0x1800091db  ja      short loc_1800091E7
0x1800091dd  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800091e7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800091eb  mov     rax, rcx
0x1800091ee  call    _alloca_probe
0x1800091f3  sub     rsp, rcx
0x1800091f6  lea     rsi, [rsp+0E0h+dwFlags]
0x1800091fb  test    rsi, rsi
0x1800091fe  jz      loc_1800090DA
0x180009204  mov     [rsp+0E0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180009209  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000920d  mov     [rsp+0E0h+lpDefaultChar], rdi; lpDefaultChar
0x180009212  mov     r8, r12; lpWideCharStr
0x180009215  mov     [rsp+0E0h+cbMultiByte], edx; cbMultiByte
0x180009219  xor     ecx, ecx; CodePage
0x18000921b  xor     edx, edx; dwFlags
0x18000921d  mov     [rsp+0E0h+lpMultiByteStr], rsi; lpMultiByteStr
0x180009222  call    cs:__imp_WideCharToMultiByte
0x180009228  test    eax, eax
0x18000922a  jnz     short loc_180009234
0x18000922c  jmp     loc_180009079
0x180009231  mov     rsi, rdi
0x180009234  mov     rcx, r15; pbstr
0x180009237  call    cs:__imp_SysStringLen
0x18000923d  test    eax, eax
0x18000923f  jz      loc_1800092D4
0x180009245  mov     [rsp+0E0h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18000924a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000924e  mov     [rsp+0E0h+lpDefaultChar], rdi; lpDefaultChar
0x180009253  mov     r8, r15; lpWideCharStr
0x180009256  mov     [rsp+0E0h+cbMultiByte], edi; cbMultiByte
0x18000925a  xor     edx, edx; dwFlags
0x18000925c  xor     ecx, ecx; CodePage
0x18000925e  mov     [rsp+0E0h+lpMultiByteStr], rdi; lpMultiByteStr
0x180009263  call    cs:__imp_WideCharToMultiByte
0x180009269  movsxd  rdx, eax
0x18000926c  test    eax, eax
0x18000926e  jz      loc_180009079
0x180009274  lea     rcx, [rdx+0Fh]
0x180009278  cmp     rcx, rdx
0x18000927b  ja      short loc_180009287
0x18000927d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180009287  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000928b  mov     rax, rcx
0x18000928e  call    _alloca_probe
0x180009293  sub     rsp, rcx
0x180009296  xor     r13d, r13d
0x180009299  lea     rdi, [rsp+0E0h+dwFlags]
0x18000929e  test    rdi, rdi
0x1800092a1  jz      loc_1800090DA
0x1800092a7  mov     [rsp+0E0h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800092ac  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800092b0  mov     [rsp+0E0h+lpDefaultChar], r13; lpDefaultChar
0x1800092b5  mov     r8, r15; lpWideCharStr
0x1800092b8  mov     [rsp+0E0h+cbMultiByte], edx; cbMultiByte
0x1800092bc  xor     ecx, ecx; CodePage
0x1800092be  xor     edx, edx; dwFlags
0x1800092c0  mov     [rsp+0E0h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800092c5  call    cs:__imp_WideCharToMultiByte
0x1800092cb  test    eax, eax
0x1800092cd  jnz     short loc_1800092DA
0x1800092cf  jmp     loc_180009079
0x1800092d4  xor     r13d, r13d
0x1800092d7  mov     esi, r13d
0x1800092da  mov     eax, [rbp+0A0h+var_98]
0x1800092dd  lea     rcx, [rbp+0A0h+NetResource]; lpNetResource
0x1800092e1  mov     r9d, [rbp+0A0h+dwFlags]; dwFlags
0x1800092e5  xorps   xmm0, xmm0
0x1800092e8  mov     [rbp+0A0h+NetResource.dwType], eax
0x1800092eb  mov     r8, rsi; lpUserName
0x1800092ee  mov     rax, [rbp+0A0h+var_90]
0x1800092f2  mov     rdx, rdi; lpPassword
0x1800092f5  mov     [rbp+0A0h+NetResource.lpLocalName], rax
0x1800092f9  mov     [rbp+0A0h+NetResource.dwScope], r13d
0x1800092fd  mov     qword ptr [rbp+0A0h+NetResource.dwDisplayType], 0
0x180009305  mov     [rbp+0A0h+NetResource.lpRemoteName], r14
0x180009309  movdqu  xmmword ptr [rbp+0A0h+NetResource.lpComment], xmm0
0x18000930e  call    cs:__imp_WNetAddConnection2A
0x180009314  test    eax, eax
0x180009316  jz      loc_18000908E
0x18000931c  jg      loc_180009085
0x180009322  mov     ebx, eax
0x180009324  jmp     loc_18000908E
0x180009329  mov     eax, 80004003h
0x18000932e  mov     rcx, [rbp+0A0h+var_50]
0x180009332  xor     rcx, rbp; StackCookie
0x180009335  call    __security_check_cookie
0x18000933a  lea     rsp, [rbp+68h]
0x18000933e  pop     r15
0x180009340  pop     r14
0x180009342  pop     r13
0x180009344  pop     r12
0x180009346  pop     rdi
0x180009347  pop     rsi
0x180009348  pop     rbx
0x180009349  pop     rbp
0x18000934a  retn
```
