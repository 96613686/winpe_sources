# CUserManager::IsDuplicateName(ushort const *,bool)

- ea: `0x18000bbe0`
- end: `0x18000be16`
- name: `?IsDuplicateName@CUserManager@@QEAA_NPEBG_N@Z`
- size: `566`
- prototype: `bool(CUserManager *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ce90`
- `0x18000d560`
- `0x18000fa50`

## callees

- `0x18000bbe0`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000bc8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bcfb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bcfb`
- `OLEAUT32!__imp_VariantInit` at `0x18000bd2c`
- `OLEAUT32!__imp_VariantInit` at `0x18000bd36`
- `OLEAUT32!__imp_VariantInit` at `0x18000bd2c`
- `OLEAUT32!__imp_VariantInit` at `0x18000bd36`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd9e`
- `OLEAUT32!__imp_VariantClear` at `0x18000bda8`
- `OLEAUT32!__imp_VariantClear` at `0x18000bd9e`
- `OLEAUT32!__imp_VariantClear` at `0x18000bda8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bc7c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bce7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bd8e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bde4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bc7c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bce7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bd8e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000bde4`

## pseudocode

```c
char __fastcall CUserManager::IsDuplicateName(CUserManager *this, const unsigned __int16 *a2, char a3)
{
  bool v3; // bl
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  const wchar_t *v10; // rdx
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rcx
  const wchar_t *v14; // rdx
  __int64 v15; // rdi
  __int64 *v16; // rcx
  __int64 v17; // rax
  unsigned int v18; // edi
  VARIANTARG v20; // [rsp+30h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v22; // [rsp+60h] [rbp-20h] BYREF
  int v23; // [rsp+C0h] [rbp+40h]
  LPCWCH lpString2; // [rsp+D8h] [rbp+58h] BYREF

  v3 = 0;
  lpString2 = 0;
  if ( *((_BYTE *)this + 896) )
  {
    v7 = (*(__int64 (__fastcall **)(CUserManager *, const unsigned __int16 *, const wchar_t *))(*(_QWORD *)this + 152LL))(
           this,
           a2,
           L"loginname");
    if ( v7 )
    {
      v8 = v7 + 16;
      v9 = *(_QWORD *)(v7 + 16);
      v10 = L"username";
      if ( !a3 )
        v10 = L"loginname";
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, LPCWCH *, _QWORD))(v9 + 8))(v8, v10, &lpString2, 0) >= 0 )
      {
        v3 = CompareStringOrdinal(a2, -1, lpString2, -1, 1) == 2;
        SysFreeString((BSTR)lpString2);
      }
    }
  }
  v11 = 0;
  while ( !v3 )
  {
    if ( (unsigned int)v11 >= *((_DWORD *)this + 10) )
    {
      v3 = 0;
      v23 = 32834036;
      v15 = 0;
      do
      {
        if ( (unsigned int)v15 >= 2 )
          break;
        VariantInit(&pvarg);
        VariantInit(&v20);
        v20.iVal = *((_WORD *)&v23 + v15);
        v16 = (__int64 *)*((_QWORD *)this + 9);
        v20.vt = 3;
        v17 = *v16;
        v22 = v20;
        if ( (*(int (__fastcall **)(__int64 *, VARIANTARG *, VARIANTARG *))(v17 + 88))(v16, &v22, &pvarg) >= 0 )
          v3 = CompareStringOrdinal(a2, -1, pvarg.bstrVal, -1, 1) == 2;
        VariantClear(&v20);
        VariantClear(&pvarg);
        v15 = (unsigned int)(v15 + 1);
      }
      while ( !v3 );
      v18 = 0;
      if ( !v3 )
      {
        while ( v18 < 4 )
        {
          if ( CompareStringOrdinal(a2, -1, (LPCWCH)qword_1800A1248[4 * v18], -1, 1) == 2 )
            return 1;
          v3 = 0;
          ++v18;
        }
      }
      return v3;
    }
    v12 = *((_QWORD *)this + v11 + 10);
    if ( v12 )
    {
      v13 = v12 + 16;
      v14 = L"username";
      if ( !a3 )
        v14 = L"loginname";
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, LPCWCH *, _QWORD))(*(_QWORD *)v13 + 8LL))(
             v13,
             v14,
             &lpString2,
             0) >= 0 )
      {
        v3 = CompareStringOrdinal(a2, -1, lpString2, -1, 1) == 2;
        SysFreeString((BSTR)lpString2);
      }
    }
    v11 = (unsigned int)(v11 + 1);
  }
  return v3;
}

```

## disassembly

```asm
0x18000bbe0  mov     [rsp-38h+arg_8], rbx
0x18000bbe5  push    rbp
0x18000bbe6  push    rsi
0x18000bbe7  push    rdi
0x18000bbe8  push    r12
0x18000bbea  push    r13
0x18000bbec  push    r14
0x18000bbee  push    r15
0x18000bbf0  mov     rbp, rsp
0x18000bbf3  sub     rsp, 80h
0x18000bbfa  xor     bl, bl
0x18000bbfc  mov     [rbp+lpString2], 0
0x18000bc04  or      r13d, 0FFFFFFFFh
0x18000bc08  mov     r15b, r8b
0x18000bc0b  lea     r8, aLoginname; "loginname"
0x18000bc12  mov     r14, rdx
0x18000bc15  mov     rsi, rcx
0x18000bc18  mov     r12d, 1
0x18000bc1e  cmp     [rcx+380h], bl
0x18000bc24  jz      short loc_18000BC99
0x18000bc26  mov     rax, [rcx]
0x18000bc29  mov     rax, [rax+98h]
0x18000bc30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc35  lea     r8, aLoginname; "loginname"
0x18000bc3c  test    rax, rax
0x18000bc3f  jz      short loc_18000BC99
0x18000bc41  lea     rcx, [rax+10h]
0x18000bc45  test    r15b, r15b
0x18000bc48  mov     rax, [rcx]
0x18000bc4b  lea     rdx, pszStr2; "username"
0x18000bc52  cmovz   rdx, r8
0x18000bc56  xor     r9d, r9d
0x18000bc59  lea     r8, [rbp+lpString2]
0x18000bc5d  mov     rax, [rax+8]
0x18000bc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc66  test    eax, eax
0x18000bc68  js      short loc_18000BC92
0x18000bc6a  mov     r8, [rbp+lpString2]; lpString2
0x18000bc6e  mov     r9d, r13d; cchCount2
0x18000bc71  mov     edx, r13d; cchCount1
0x18000bc74  mov     [rsp+80h+bIgnoreCase], r12d; bIgnoreCase
0x18000bc79  mov     rcx, r14; lpString1
0x18000bc7c  call    cs:__imp_CompareStringOrdinal
0x18000bc82  mov     rcx, [rbp+lpString2]; bstrString
0x18000bc86  cmp     eax, 2
0x18000bc89  setz    bl
0x18000bc8c  call    cs:__imp_SysFreeString
0x18000bc92  lea     r8, aLoginname; "loginname"
0x18000bc99  xor     edi, edi
0x18000bc9b  jmp     short loc_18000BD0B
0x18000bc9d  cmp     edi, [rsi+28h]
0x18000bca0  jnb     short loc_18000BD14
0x18000bca2  mov     rcx, [rsi+rdi*8+50h]
0x18000bca7  test    rcx, rcx
0x18000bcaa  jz      short loc_18000BD01
0x18000bcac  add     rcx, 10h
0x18000bcb0  lea     rdx, pszStr2; "username"
0x18000bcb7  test    r15b, r15b
0x18000bcba  cmovz   rdx, r8
0x18000bcbe  xor     r9d, r9d
0x18000bcc1  mov     rax, [rcx]
0x18000bcc4  lea     r8, [rbp+lpString2]
0x18000bcc8  mov     rax, [rax+8]
0x18000bccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcd1  test    eax, eax
0x18000bcd3  js      short loc_18000BD01
0x18000bcd5  mov     r8, [rbp+lpString2]; lpString2
0x18000bcd9  mov     r9d, r13d; cchCount2
0x18000bcdc  mov     edx, r13d; cchCount1
0x18000bcdf  mov     [rsp+80h+bIgnoreCase], r12d; bIgnoreCase
0x18000bce4  mov     rcx, r14; lpString1
0x18000bce7  call    cs:__imp_CompareStringOrdinal
0x18000bced  mov     rcx, [rbp+lpString2]; bstrString
0x18000bcf1  cmp     eax, 2
0x18000bcf4  movzx   ebx, bl
0x18000bcf7  cmovz   ebx, r12d
0x18000bcfb  call    cs:__imp_SysFreeString
0x18000bd01  add     edi, r12d
0x18000bd04  lea     r8, aLoginname; "loginname"
0x18000bd0b  test    bl, bl
0x18000bd0d  jz      short loc_18000BC9D
0x18000bd0f  jmp     loc_18000BDF9
0x18000bd14  xor     bl, bl
0x18000bd16  mov     [rbp+arg_0], 1F501F4h
0x18000bd1d  xor     edi, edi
0x18000bd1f  cmp     edi, 2
0x18000bd22  jnb     loc_18000BDB9
0x18000bd28  lea     rcx, [rbp+pvarg]; pvarg
0x18000bd2c  call    cs:__imp_VariantInit
0x18000bd32  lea     rcx, [rbp+var_50]; pvarg
0x18000bd36  call    cs:__imp_VariantInit
0x18000bd3c  movzx   ecx, word ptr [rbp+rdi*2+arg_0]
0x18000bd41  lea     r8, [rbp+pvarg]
0x18000bd45  movsd   xmm1, qword ptr [rbp+var_50+10h]
0x18000bd4a  lea     rdx, [rbp+var_20]
0x18000bd4e  mov     word ptr [rbp+var_50+8], cx
0x18000bd52  mov     eax, 3
0x18000bd57  mov     rcx, [rsi+48h]
0x18000bd5b  mov     word ptr [rbp+var_50], ax
0x18000bd5f  movups  xmm0, xmmword ptr [rbp+var_50]
0x18000bd63  mov     rax, [rcx]
0x18000bd66  movaps  [rbp+var_20], xmm0
0x18000bd6a  movsd   [rbp+var_10], xmm1
0x18000bd6f  mov     rax, [rax+58h]
0x18000bd73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd78  test    eax, eax
0x18000bd7a  js      short loc_18000BD9A
0x18000bd7c  mov     r8, qword ptr [rbp+pvarg+8]; lpString2
0x18000bd80  mov     r9d, r13d; cchCount2
0x18000bd83  mov     edx, r13d; cchCount1
0x18000bd86  mov     [rsp+80h+bIgnoreCase], r12d; bIgnoreCase
0x18000bd8b  mov     rcx, r14; lpString1
0x18000bd8e  call    cs:__imp_CompareStringOrdinal
0x18000bd94  cmp     eax, 2
0x18000bd97  setz    bl
0x18000bd9a  lea     rcx, [rbp+var_50]; pvarg
0x18000bd9e  call    cs:__imp_VariantClear
0x18000bda4  lea     rcx, [rbp+pvarg]; pvarg
0x18000bda8  call    cs:__imp_VariantClear
0x18000bdae  add     edi, r12d
0x18000bdb1  test    bl, bl
0x18000bdb3  jz      loc_18000BD1F
0x18000bdb9  xor     edi, edi
0x18000bdbb  test    bl, bl
0x18000bdbd  jnz     short loc_18000BDF9
0x18000bdbf  cmp     edi, 4
0x18000bdc2  jnb     short loc_18000BDF9
0x18000bdc4  lea     rax, qword_1800A1248
0x18000bdcb  mov     r8d, edi
0x18000bdce  shl     r8, 5
0x18000bdd2  mov     r9d, r13d; cchCount2
0x18000bdd5  mov     edx, r13d; cchCount1
0x18000bdd8  mov     [rsp+80h+bIgnoreCase], r12d; bIgnoreCase
0x18000bddd  mov     rcx, r14; lpString1
0x18000bde0  mov     r8, [r8+rax]; lpString2
0x18000bde4  call    cs:__imp_CompareStringOrdinal
0x18000bdea  cmp     eax, 2
0x18000bded  jz      short loc_18000BDF6
0x18000bdef  xor     bl, bl
0x18000bdf1  add     edi, r12d
0x18000bdf4  jmp     short loc_18000BDBF
0x18000bdf6  mov     bl, r12b
0x18000bdf9  mov     al, bl
0x18000bdfb  mov     rbx, [rsp+80h+arg_8]
0x18000be03  add     rsp, 80h
0x18000be0a  pop     r15
0x18000be0c  pop     r14
0x18000be0e  pop     r13
0x18000be10  pop     r12
0x18000be12  pop     rdi
0x18000be13  pop     rsi
0x18000be14  pop     rbp
0x18000be15  retn
```
