# HTTP_USER_REQUEST::_ParseTweener(int *)

- ea: `0x18002b200`
- end: `0x18002b424`
- name: `?_ParseTweener@HTTP_USER_REQUEST@@AEAAKPEAH@Z`
- size: `548`
- prototype: `__int64 __fastcall(HTTP_USER_REQUEST *this, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002af44`
- `0x18002b0e4`

## callees

- `0x18002b200`
- `0x18002b8a0`
- `0x18002c480`
- `0x1800a1d10`
- `0x1800a3da8`
- `0x1800a3db4`
- `0x1800cdd7c`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18002b2dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18002b2dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIA` at `0x18002b2f5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIA` at `0x18002b2f5`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002b3a2`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18002b3a2`
- `SspiCli!FreeContextBuffer` at `0x18002b3f8`
- `SspiCli!FreeContextBuffer` at `0x18002b3f8`
- `SspiCli!EnumerateSecurityPackagesA` at `0x18002b367`
- `SspiCli!EnumerateSecurityPackagesA` at `0x18002b367`

## pseudocode

```c
__int64 __fastcall HTTP_USER_REQUEST::_ParseTweener(HTTP_USER_REQUEST *this, int *a2)
{
  void *v2; // rdi
  unsigned int Header; // ebx
  unsigned int v5; // ecx
  CHAR *lpString2; // r14
  __int64 v7; // r12
  PSTR v8; // rax
  _BYTE *v9; // r15
  _BYTE *i; // rsi
  unsigned int v11; // esi
  CHAR *v12; // rax
  unsigned int j; // esi
  unsigned int v15[2]; // [rsp+30h] [rbp-30h] BYREF
  int *v16; // [rsp+38h] [rbp-28h]
  PSecPkgInfoA ppPackageInfo; // [rsp+40h] [rbp-20h] BYREF
  unsigned int pcPackages; // [rsp+48h] [rbp-18h] BYREF

  v2 = 0;
  v16 = a2;
  *a2 = 0;
  v15[0] = 0;
  pcPackages = 0;
  ppPackageInfo = 0;
  Header = CWebIOResponseHeadersShim::FindHeader((HTTP_USER_REQUEST *)((char *)this + 120), 0x28u, 0, 0, 0, v15);
  if ( Header == 122 )
  {
    v2 = operator new[](v15[0]);
    if ( !v2 )
    {
      Header = 8;
      goto LABEL_27;
    }
    Header = CWebIOResponseHeadersShim::FindHeader((HTTP_USER_REQUEST *)((char *)this + 120), 0x28u, 0, 0, v2, v15);
  }
  if ( Header )
  {
    lpString2 = 0;
    if ( !v2 )
      goto LABEL_27;
    goto LABEL_25;
  }
  if ( !v2 )
    goto LABEL_27;
  v5 = v15[0];
  lpString2 = 0;
  if ( v15[0] )
  {
    v7 = v15[0] - 1;
    *((_BYTE *)v2 + v7) = 0;
    if ( v5 >= 0xB && !StrCmpNICA((LPCSTR)v2, "Passport1.4", 11) )
    {
      v8 = StrStrIA((PCSTR)v2, "Negotiate2SupportedIf");
      if ( !v8 || v8[21] != 61 )
        goto LABEL_23;
      v9 = v8 + 22;
      for ( i = v8 + 22; *i != 44; ++i )
      {
        if ( !*i )
          break;
      }
      if ( i == v9 )
      {
LABEL_23:
        CUnicodeString::SetStringA((HTTP_USER_REQUEST *)((char *)this + 8712), (const char *)v2, v7, 0);
        *v16 = 1;
        goto LABEL_25;
      }
      v11 = (_DWORD)i - (_DWORD)v9;
      v12 = (CHAR *)operator new[](v11 + 1);
      lpString2 = v12;
      if ( !v12 )
      {
        Header = 8;
        goto LABEL_25;
      }
      memcpy_0(v12, v9, v11);
      lpString2[v11] = 0;
      Header = EnumerateSecurityPackagesA(&pcPackages, &ppPackageInfo);
      if ( !Header )
      {
        for ( j = 0; j < pcPackages; ++j )
        {
          if ( CompareStringA(0x7Fu, 1u, ppPackageInfo[j].Name, -1, lpString2, -1) == 2 )
            goto LABEL_25;
        }
        goto LABEL_23;
      }
    }
  }
LABEL_25:
  operator delete(v2);
  if ( lpString2 )
    operator delete(lpString2);
LABEL_27:
  if ( ppPackageInfo )
    FreeContextBuffer(ppPackageInfo);
  return Header;
}

```

## disassembly

```asm
0x18002b200  mov     [rsp-38h+arg_10], rbx
0x18002b205  push    rbp
0x18002b206  push    rsi
0x18002b207  push    rdi
0x18002b208  push    r12
0x18002b20a  push    r13
0x18002b20c  push    r14
0x18002b20e  push    r15
0x18002b210  mov     rbp, rsp
0x18002b213  sub     rsp, 60h
0x18002b217  mov     rax, cs:__security_cookie
0x18002b21e  xor     rax, rsp
0x18002b221  mov     [rbp+var_10], rax
0x18002b225  xor     edi, edi
0x18002b227  mov     [rbp+var_28], rdx
0x18002b22b  lea     rax, [rbp+var_30]
0x18002b22f  mov     [rdx], edi
0x18002b231  mov     r13, rcx
0x18002b234  mov     qword ptr [rsp+60h+cchCount2], rax; unsigned int *
0x18002b239  xor     r9d, r9d; unsigned int
0x18002b23c  mov     [rbp+var_30], edi
0x18002b23f  lea     r14d, [rdi+28h]
0x18002b243  mov     [rbp+pcPackages], edi
0x18002b246  mov     edx, r14d; unsigned int
0x18002b249  mov     [rbp+ppPackageInfo], rdi
0x18002b24d  xor     r8d, r8d; unsigned int
0x18002b250  mov     [rsp+60h+lpString2], rdi; void *
0x18002b255  add     rcx, 78h ; 'x'; this
0x18002b259  call    ?FindHeader@CWebIOResponseHeadersShim@@QEAAKKKKPEAXPEAK@Z; CWebIOResponseHeadersShim::FindHeader(ulong,ulong,ulong,void *,ulong *)
0x18002b25e  mov     ebx, eax
0x18002b260  cmp     eax, 7Ah ; 'z'
0x18002b263  jnz     short loc_18002B29F
0x18002b265  mov     ecx, [rbp+var_30]; unsigned __int64
0x18002b268  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002b26d  mov     rdi, rax
0x18002b270  test    rax, rax
0x18002b273  jnz     short loc_18002B27D
0x18002b275  lea     ebx, [rax+8]
0x18002b278  jmp     loc_18002B3EF
0x18002b27d  lea     rax, [rbp+var_30]
0x18002b281  xor     r9d, r9d; unsigned int
0x18002b284  mov     qword ptr [rsp+60h+cchCount2], rax; unsigned int *
0x18002b289  lea     rcx, [r13+78h]; this
0x18002b28d  xor     r8d, r8d; unsigned int
0x18002b290  mov     [rsp+60h+lpString2], rdi; void *
0x18002b295  mov     edx, r14d; unsigned int
0x18002b298  call    ?FindHeader@CWebIOResponseHeadersShim@@QEAAKKKKPEAXPEAK@Z; CWebIOResponseHeadersShim::FindHeader(ulong,ulong,ulong,void *,ulong *)
0x18002b29d  mov     ebx, eax
0x18002b29f  test    ebx, ebx
0x18002b2a1  jnz     loc_18002B3D2
0x18002b2a7  test    rdi, rdi
0x18002b2aa  jz      loc_18002B3EF
0x18002b2b0  mov     ecx, [rbp+var_30]
0x18002b2b3  xor     r14d, r14d
0x18002b2b6  test    ecx, ecx
0x18002b2b8  jz      loc_18002B3DA
0x18002b2be  lea     r8d, [rbx+0Bh]; nChar
0x18002b2c2  lea     r12d, [rcx-1]
0x18002b2c6  mov     [r12+rdi], r14b
0x18002b2ca  cmp     ecx, r8d
0x18002b2cd  jb      loc_18002B3DA
0x18002b2d3  lea     rdx, pszStr2; "Passport1.4"
0x18002b2da  mov     rcx, rdi; pszStr1
0x18002b2dd  call    cs:__imp_StrCmpNICA
0x18002b2e3  test    eax, eax
0x18002b2e5  jnz     loc_18002B3DA
0x18002b2eb  lea     rdx, pszSrch; "Negotiate2SupportedIf"
0x18002b2f2  mov     rcx, rdi; pszFirst
0x18002b2f5  call    cs:__imp_StrStrIA
0x18002b2fb  test    rax, rax
0x18002b2fe  jz      loc_18002B3B1
0x18002b304  cmp     byte ptr [rax+15h], 3Dh ; '='
0x18002b308  jnz     loc_18002B3B1
0x18002b30e  lea     r15, [rax+16h]
0x18002b312  cmp     byte ptr [r15], 2Ch ; ','
0x18002b316  mov     rsi, r15
0x18002b319  jz      short loc_18002B328
0x18002b31b  cmp     [rsi], r14b
0x18002b31e  jz      short loc_18002B328
0x18002b320  inc     rsi
0x18002b323  cmp     byte ptr [rsi], 2Ch ; ','
0x18002b326  jnz     short loc_18002B31B
0x18002b328  cmp     rsi, r15
0x18002b32b  jz      loc_18002B3B1
0x18002b331  sub     esi, r15d
0x18002b334  lea     ecx, [rsi+1]; unsigned __int64
0x18002b337  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002b33c  mov     r14, rax
0x18002b33f  test    rax, rax
0x18002b342  jnz     short loc_18002B34C
0x18002b344  lea     ebx, [rax+8]
0x18002b347  jmp     loc_18002B3DA
0x18002b34c  mov     r8d, esi; Size
0x18002b34f  mov     rdx, r15; Src
0x18002b352  mov     rcx, r14; void *
0x18002b355  call    memcpy_0
0x18002b35a  lea     rdx, [rbp+ppPackageInfo]; ppPackageInfo
0x18002b35e  mov     byte ptr [rsi+r14], 0
0x18002b363  lea     rcx, [rbp+pcPackages]; pcPackages
0x18002b367  call    cs:__imp_EnumerateSecurityPackagesA
0x18002b36d  mov     ebx, eax
0x18002b36f  test    eax, eax
0x18002b371  jnz     short loc_18002B3DA
0x18002b373  xor     esi, esi
0x18002b375  or      r15d, 0FFFFFFFFh
0x18002b379  cmp     esi, [rbp+pcPackages]
0x18002b37c  jnb     short loc_18002B3B1
0x18002b37e  mov     r8, [rbp+ppPackageInfo]
0x18002b382  mov     edx, 1; dwCmpFlags
0x18002b387  mov     eax, esi
0x18002b389  mov     r9d, r15d; cchCount1
0x18002b38c  shl     rax, 5
0x18002b390  mov     [rsp+60h+cchCount2], r15d; cchCount2
0x18002b395  lea     ecx, [rdx+7Eh]; Locale
0x18002b398  mov     [rsp+60h+lpString2], r14; lpString2
0x18002b39d  mov     r8, [rax+r8+10h]; lpString1
0x18002b3a2  call    cs:__imp_CompareStringA
0x18002b3a8  cmp     eax, 2
0x18002b3ab  jz      short loc_18002B3DA
0x18002b3ad  inc     esi
0x18002b3af  jmp     short loc_18002B379
0x18002b3b1  lea     rcx, [r13+2208h]; this
0x18002b3b8  xor     r9d, r9d; unsigned int
0x18002b3bb  mov     r8d, r12d; unsigned int
0x18002b3be  mov     rdx, rdi; char *
0x18002b3c1  call    ?SetStringA@CUnicodeString@@QEAAKPEBDKI@Z; CUnicodeString::SetStringA(char const *,ulong,uint)
0x18002b3c6  mov     rax, [rbp+var_28]
0x18002b3ca  mov     dword ptr [rax], 1
0x18002b3d0  jmp     short loc_18002B3DA
0x18002b3d2  xor     r14d, r14d
0x18002b3d5  test    rdi, rdi
0x18002b3d8  jz      short loc_18002B3EF
0x18002b3da  mov     rcx, rdi; void *
0x18002b3dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b3e2  test    r14, r14
0x18002b3e5  jz      short loc_18002B3EF
0x18002b3e7  mov     rcx, r14; void *
0x18002b3ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b3ef  mov     rcx, [rbp+ppPackageInfo]; pvContextBuffer
0x18002b3f3  test    rcx, rcx
0x18002b3f6  jz      short loc_18002B3FE
0x18002b3f8  call    cs:__imp_FreeContextBuffer
0x18002b3fe  mov     eax, ebx
0x18002b400  mov     rcx, [rbp+var_10]
0x18002b404  xor     rcx, rsp; StackCookie
0x18002b407  call    __security_check_cookie
0x18002b40c  mov     rbx, [rsp+60h+arg_10]
0x18002b414  add     rsp, 60h
0x18002b418  pop     r15
0x18002b41a  pop     r14
0x18002b41c  pop     r13
0x18002b41e  pop     r12
0x18002b420  pop     rdi
0x18002b421  pop     rsi
0x18002b422  pop     rbp
0x18002b423  retn
```
