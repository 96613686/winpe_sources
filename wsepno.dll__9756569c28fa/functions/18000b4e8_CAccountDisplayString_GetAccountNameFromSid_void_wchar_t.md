# CAccountDisplayString::_GetAccountNameFromSid(void *,wchar_t * *)

- ea: `0x18000b4e8`
- end: `0x18000b6fe`
- name: `?_GetAccountNameFromSid@CAccountDisplayString@@AEAAJPEAXPEAPEA_W@Z`
- size: `534`
- prototype: `int(CAccountDisplayString *__hidden this, void *, wchar_t **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007768`

## callees

- `0x180003714`
- `0x180003b7c`
- `0x180003be0`
- `0x18000b4e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b60d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b60d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000b53e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000b603`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000b53e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000b603`

## pseudocode

```c
__int64 __fastcall CAccountDisplayString::_GetAccountNameFromSid(CAccountDisplayString *this, void *a2, wchar_t **a3)
{
  wchar_t *v3; // rsi
  signed int v5; // ebx
  LPWSTR v6; // r15
  LPWSTR v7; // r12
  signed int LastError; // eax
  void *v9; // r9
  int v10; // edi
  void *v11; // r9
  unsigned __int128 v12; // rax
  LPWSTR v13; // rsi
  LPWSTR v14; // r14
  void *v15; // rdx
  signed int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned __int64 v19; // rbx
  unsigned __int128 v20; // rax
  unsigned __int64 v21; // rdx
  wchar_t *v22; // rbx
  void *v23; // rdx
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR Name; // [rsp+48h] [rbp-18h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+50h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+A0h] [rbp+40h] BYREF
  int v29; // [rsp+A4h] [rbp+44h]
  wchar_t *v30; // [rsp+B0h] [rbp+50h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+58h] BYREF

  v30 = (wchar_t *)a3;
  v29 = HIDWORD(this);
  *a3 = 0;
  v3 = (wchar_t *)a3;
  peUse = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  if ( LookupAccountSidW(0, a2, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
    return (unsigned int)-2147467259;
  v6 = 0;
  v7 = 0;
  LastError = GetLastError();
  v5 = LastError;
  v10 = -2147024362;
  if ( LastError == 122 )
  {
    Name = 0;
    ReferencedDomainName = 0;
    if ( !is_mul_ok(cchName, 2u) )
      return (unsigned int)-2147024362;
    v5 = ProfNotif_HeapAlloc(2LL * cchName, (cchName * (unsigned __int128)2uLL) >> 64, (void **)&Name, v9);
    if ( v5 < 0 )
      return (unsigned int)v5;
    v12 = cchReferencedDomainName * (unsigned __int128)2uLL;
    ReferencedDomainName = 0;
    if ( is_mul_ok(cchReferencedDomainName, 2u) )
    {
      v5 = ProfNotif_HeapAlloc(2LL * cchReferencedDomainName, SDWORD2(v12), (void **)&ReferencedDomainName, v11);
      if ( v5 >= 0 )
      {
        v13 = Name;
        v14 = ReferencedDomainName;
        if ( LookupAccountSidW(0, a2, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        {
          v6 = v13;
          v7 = v14;
          v13 = 0;
          v14 = 0;
          v5 = 0;
        }
        else
        {
          v16 = GetLastError();
          v5 = v16;
          if ( v16 > 0 )
            v5 = (unsigned __int16)v16 | 0x80070000;
        }
        ProfNotif_HeapFree(v14, v15);
        goto LABEL_17;
      }
    }
    else
    {
      v5 = -2147024362;
    }
    v13 = Name;
LABEL_17:
    ProfNotif_HeapFree(v13, *((void **)&v12 + 1));
    v3 = v30;
    goto LABEL_18;
  }
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
  if ( v5 < 0 )
    return (unsigned int)v5;
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( v7[v18] );
  do
    ++v17;
  while ( v6[v17] );
  v30 = 0;
  v19 = v17 + v18 + 2;
  v20 = v19 * (unsigned __int128)2uLL;
  if ( is_mul_ok(v19, 2u) )
  {
    v10 = ProfNotif_HeapAlloc(2 * v19, SDWORD2(v20), (void **)&v30, v9);
    if ( v10 >= 0 )
    {
      v21 = v19;
      v22 = v30;
      v10 = StringCchPrintfW(v30, v21, L"%s\\%s", v7, v6);
      if ( v10 < 0 )
        ProfNotif_HeapFree(v22, *((void **)&v20 + 1));
      else
        *(_QWORD *)v3 = v22;
    }
  }
  ProfNotif_HeapFree(v6, *((void **)&v20 + 1));
  ProfNotif_HeapFree(v7, v23);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000b4e8  mov     r11, rsp
0x18000b4eb  mov     [r11+10h], rbx
0x18000b4ef  mov     [r11+18h], r8
0x18000b4f3  mov     [r11+8], rcx
0x18000b4f7  push    rbp
0x18000b4f8  push    rsi
0x18000b4f9  push    rdi
0x18000b4fa  push    r12
0x18000b4fc  push    r13
0x18000b4fe  push    r14
0x18000b500  push    r15
0x18000b502  mov     rbp, rsp
0x18000b505  sub     rsp, 60h
0x18000b509  xor     r14d, r14d
0x18000b50c  lea     rax, [rbp+var_20]
0x18000b510  mov     [r11-68h], rax
0x18000b514  lea     r9, [rbp+cchName]; cchName
0x18000b518  lea     rax, [rbp+arg_0]
0x18000b51c  mov     [r8], r14
0x18000b51f  mov     rsi, r8
0x18000b522  mov     [r11-70h], rax
0x18000b526  xor     r8d, r8d; Name
0x18000b529  mov     [r11-78h], r14
0x18000b52d  xor     ecx, ecx; lpSystemName
0x18000b52f  mov     [rbp+var_20], r14d
0x18000b533  mov     r13, rdx
0x18000b536  mov     [rbp+cchName], r14d
0x18000b53a  mov     [rbp+arg_0], r14d
0x18000b53e  call    cs:__imp_LookupAccountSidW
0x18000b544  test    eax, eax
0x18000b546  jz      short loc_18000B552
0x18000b548  mov     ebx, 80004005h
0x18000b54d  jmp     loc_18000B6E2
0x18000b552  mov     r15, r14
0x18000b555  mov     r12, r14
0x18000b558  call    cs:__imp_GetLastError
0x18000b55e  mov     ebx, eax
0x18000b560  mov     edi, 80070216h
0x18000b565  cmp     eax, 7Ah ; 'z'
0x18000b568  jz      short loc_18000B580
0x18000b56a  test    eax, eax
0x18000b56c  jle     loc_18000B650
0x18000b572  movzx   ebx, ax
0x18000b575  or      ebx, 80070000h
0x18000b57b  jmp     loc_18000B650
0x18000b580  mov     ecx, [rbp+cchName]
0x18000b583  mov     eax, 2
0x18000b588  mul     rcx
0x18000b58b  mov     [rbp+Name], r14
0x18000b58f  mov     [rbp+var_10], r14
0x18000b593  test    rdx, rdx
0x18000b596  jnz     loc_18000B6E0
0x18000b59c  lea     r8, [rbp+Name]; void **
0x18000b5a0  mov     rcx, rax; dwBytes
0x18000b5a3  call    ?ProfNotif_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; ProfNotif_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18000b5a8  mov     ebx, eax
0x18000b5aa  test    eax, eax
0x18000b5ac  js      loc_18000B6E2
0x18000b5b2  mov     ecx, [rbp+arg_0]
0x18000b5b5  mov     eax, 2
0x18000b5ba  mul     rcx
0x18000b5bd  mov     [rbp+var_10], r14
0x18000b5c1  test    rdx, rdx
0x18000b5c4  jnz     short loc_18000B63E
0x18000b5c6  lea     r8, [rbp+var_10]; void **
0x18000b5ca  mov     rcx, rax; dwBytes
0x18000b5cd  call    ?ProfNotif_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; ProfNotif_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18000b5d2  mov     ebx, eax
0x18000b5d4  test    eax, eax
0x18000b5d6  js      short loc_18000B640
0x18000b5d8  mov     rsi, [rbp+Name]
0x18000b5dc  lea     rax, [rbp+var_20]
0x18000b5e0  mov     r14, [rbp+var_10]
0x18000b5e4  lea     r9, [rbp+cchName]; cchName
0x18000b5e8  mov     [rsp+60h+peUse], rax; peUse
0x18000b5ed  mov     r8, rsi; Name
0x18000b5f0  lea     rax, [rbp+arg_0]
0x18000b5f4  mov     rdx, r13; Sid
0x18000b5f7  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000b5fc  xor     ecx, ecx; lpSystemName
0x18000b5fe  mov     [rsp+60h+ReferencedDomainName], r14; ReferencedDomainName
0x18000b603  call    cs:__imp_LookupAccountSidW
0x18000b609  test    eax, eax
0x18000b60b  jnz     short loc_18000B624
0x18000b60d  call    cs:__imp_GetLastError
0x18000b613  mov     ebx, eax
0x18000b615  test    eax, eax
0x18000b617  jle     short loc_18000B631
0x18000b619  movzx   ebx, ax
0x18000b61c  or      ebx, 80070000h
0x18000b622  jmp     short loc_18000B631
0x18000b624  mov     r15, rsi
0x18000b627  mov     r12, r14
0x18000b62a  xor     esi, esi
0x18000b62c  xor     r14d, r14d
0x18000b62f  xor     ebx, ebx
0x18000b631  mov     rcx, r14; lpMem
0x18000b634  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000b639  xor     r14d, r14d
0x18000b63c  jmp     short loc_18000B644
0x18000b63e  mov     ebx, edi
0x18000b640  mov     rsi, [rbp+Name]
0x18000b644  mov     rcx, rsi; lpMem
0x18000b647  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000b64c  mov     rsi, [rbp+arg_10]
0x18000b650  test    ebx, ebx
0x18000b652  js      loc_18000B6E2
0x18000b658  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b65c  mov     rdx, rcx
0x18000b65f  inc     rdx; int
0x18000b662  cmp     [r12+rdx*2], r14w
0x18000b667  jnz     short loc_18000B65F
0x18000b669  inc     rcx
0x18000b66c  cmp     [r15+rcx*2], r14w
0x18000b671  jnz     short loc_18000B669
0x18000b673  lea     rbx, [rdx+2]
0x18000b677  mov     [rbp+arg_10], r14
0x18000b67b  add     rbx, rcx
0x18000b67e  mov     eax, 2
0x18000b683  mul     rbx
0x18000b686  test    rdx, rdx
0x18000b689  jnz     short loc_18000B6CE
0x18000b68b  lea     r8, [rbp+arg_10]; void **
0x18000b68f  mov     rcx, rax; dwBytes
0x18000b692  call    ?ProfNotif_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; ProfNotif_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18000b697  mov     edi, eax
0x18000b699  test    eax, eax
0x18000b69b  js      short loc_18000B6CE
0x18000b69d  mov     rdx, rbx; unsigned __int64
0x18000b6a0  mov     [rsp+60h+ReferencedDomainName], r15
0x18000b6a5  mov     rbx, [rbp+arg_10]
0x18000b6a9  lea     r8, aSS; "%s\\%s"
0x18000b6b0  mov     rcx, rbx; wchar_t *
0x18000b6b3  mov     r9, r12
0x18000b6b6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000b6bb  mov     edi, eax
0x18000b6bd  test    eax, eax
0x18000b6bf  js      short loc_18000B6C6
0x18000b6c1  mov     [rsi], rbx
0x18000b6c4  jmp     short loc_18000B6CE
0x18000b6c6  mov     rcx, rbx; lpMem
0x18000b6c9  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000b6ce  mov     rcx, r15; lpMem
0x18000b6d1  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000b6d6  mov     rcx, r12; lpMem
0x18000b6d9  call    ?ProfNotif_HeapFree@@YAJPEAX0@Z; ProfNotif_HeapFree(void *,void *)
0x18000b6de  jmp     short loc_18000B6E4
0x18000b6e0  mov     ebx, edi
0x18000b6e2  mov     edi, ebx
0x18000b6e4  mov     rbx, [rsp+60h+arg_8]
0x18000b6ec  mov     eax, edi
0x18000b6ee  add     rsp, 60h
0x18000b6f2  pop     r15
0x18000b6f4  pop     r14
0x18000b6f6  pop     r13
0x18000b6f8  pop     r12
0x18000b6fa  pop     rdi
0x18000b6fb  pop     rsi
0x18000b6fc  pop     rbp
0x18000b6fd  retn
```
