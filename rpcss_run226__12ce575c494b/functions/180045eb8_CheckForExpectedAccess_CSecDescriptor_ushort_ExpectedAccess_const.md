# CheckForExpectedAccess(CSecDescriptor *,ushort,ExpectedAccess const *)

- ea: `0x180045eb8`
- end: `0x1800462b8`
- name: `?CheckForExpectedAccess@@YAJPEAVCSecDescriptor@@GPEBUExpectedAccess@@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(struct CSecDescriptor *, unsigned __int16, const struct ExpectedAccess *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800456f8`

## callees

- `0x18001ec28`
- `0x18001f828`
- `0x18002ba28`
- `0x180045eb8`
- `0x1800462c0`
- `0x180047874`
- `0x1800b27e0`
- `0x1800b2bb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004617d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800461ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800462aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004617d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800461ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800462aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045ef9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045fa8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045ef9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045fa8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004601e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004601e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800460e2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800460e2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800460fd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004624a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180046272`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800460fd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004624a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180046272`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800460ab`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800460ab`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180046056`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180046056`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180046227`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180046227`
- `KERNELBASE!LocalAlloc` at `0x1800460be`
- `KERNELBASE!LocalAlloc` at `0x1800460be`

## string_xrefs

- `0x180045f0b`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x180045fba`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x1800461cf`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x180046207`: `onecore\com\combase\rpcss\olescm\registry.cxx`

## pseudocode

```c
__int64 __fastcall CheckForExpectedAccess(void **a1, __int64 a2, const struct ExpectedAccess *a3)
{
  const struct ExpectedAccess *v3; // r13
  unsigned __int64 *v5; // rax
  unsigned __int64 *v6; // rbx
  unsigned int LastError; // edi
  char *v9; // rsi
  _DWORD *v10; // r14
  void *v11; // rcx
  PACL v12; // rax
  int v13; // ebx
  const char *v14; // r9
  unsigned __int16 j; // r12
  PSID *v16; // rdi
  __int64 v17; // rbx
  WELL_KNOWN_SID_TYPE v18; // ecx
  HLOCAL v19; // rax
  _DWORD *v20; // r13
  int v21; // eax
  unsigned __int16 i; // cx
  __int64 v23; // rdx
  __int64 v24; // rdx
  DWORD cbSid; // [rsp+20h] [rbp-69h] BYREF
  int v26; // [rsp+24h] [rbp-65h]
  LPVOID pAce; // [rsp+28h] [rbp-61h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+30h] [rbp-59h] BYREF
  WINBOOL bDaclPresent; // [rsp+34h] [rbp-55h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-51h] BYREF
  const struct ExpectedAccess *v31; // [rsp+40h] [rbp-49h]
  PACL v32; // [rsp+48h] [rbp-41h]
  _BYTE pSid[80]; // [rsp+50h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v31 = a3;
  v3 = a3;
  v5 = (unsigned __int64 *)HeapAlloc(g_hHeap, 0, 0x28u);
  v6 = v5;
  if ( !v5
    || (v5[1] = 0,
        v9 = (char *)(v5 + 1),
        v5[2] = 0,
        v5[3] = 0,
        v5[4] = 0,
        *v5 = 4,
        `vector constructor iterator'(
          v5 + 1,
          8u,
          4u,
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>),
        !v9) )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x354,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
      (const char *)0x8007000ELL,
      cbSid);
    return LastError;
  }
  v10 = HeapAlloc(g_hHeap, 0, 4u);
  if ( !v10 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x357,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
      (const char *)0x8007000ELL,
      cbSid);
LABEL_7:
    `vector destructor iterator'(
      v9,
      8u,
      *v6,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>);
    operator delete(v6, 8 * *v6 + 8);
    return LastError;
  }
  *v10 = 0;
  v11 = *a1;
  bDaclPresent = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  GetSecurityDescriptorDacl(v11, &bDaclPresent, &pDacl, &bDaclDefaulted);
  v12 = pDacl;
  v32 = pDacl;
  if ( pDacl )
  {
    v13 = 0;
LABEL_10:
    v26 = v13;
    if ( (unsigned __int16)v13 >= v12->AceCount )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 4u )
        {
          HeapFree(g_hHeap, 0, v10);
          v6 = (unsigned __int64 *)(v9 - 8);
          goto LABEL_32;
        }
        if ( !*((_BYTE *)v10 + i) )
          break;
      }
      LastError = -2147024809;
      v23 = 936;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
        (const char *)LastError,
        cbSid);
    }
    else
    {
      pAce = 0;
      if ( GetAce(v12, (unsigned __int16)v13, &pAce) )
      {
        for ( j = 0; ; ++j )
        {
          if ( j >= 4u )
          {
            HIWORD(v13) = HIWORD(v26);
            v12 = v32;
            LOWORD(v13) = v26 + 1;
            goto LABEL_10;
          }
          v16 = (PSID *)&v9[8 * j];
          v17 = 24LL * j;
          if ( !*v16 )
          {
            if ( *(_QWORD *)((char *)v3 + v17 + 8) )
            {
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &v9[8 * j],
                0);
              if ( !ConvertStringSidToSidW(*(LPCWSTR *)((char *)v3 + v17 + 8), (PSID *)&v9[8 * j]) )
              {
                v24 = 882;
                goto LABEL_38;
              }
            }
            else
            {
              v18 = *(_DWORD *)((char *)v3 + v17);
              cbSid = 68;
              if ( !CreateWellKnownSid(v18, 0, pSid, &cbSid) )
              {
                v24 = 874;
                goto LABEL_38;
              }
              v19 = LocalAlloc(0, cbSid);
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &v9[8 * j],
                v19);
              if ( !*v16 )
              {
                LastError = -2147024882;
                v23 = 877;
                goto LABEL_35;
              }
              CopySid(cbSid, *v16, pSid);
            }
          }
          if ( *(_BYTE *)pAce )
          {
            if ( *(_BYTE *)pAce == 1 )
            {
              if ( EqualSid((char *)pAce + 8, *v16) )
              {
                LastError = -2147024809;
                v23 = 905;
                goto LABEL_35;
              }
            }
            else if ( *(_BYTE *)pAce == 2 && EqualSid((char *)pAce + 8, *v16) )
            {
              LastError = -2147024809;
              v23 = 915;
              goto LABEL_35;
            }
          }
          else
          {
            v20 = pAce;
            if ( EqualSid((char *)pAce + 8, *v16) )
            {
              v21 = v20[1];
              v3 = v31;
              if ( (*(_DWORD *)((_BYTE *)v31 + v17 + 16) & v21) == *(_DWORD *)((char *)v31 + v17 + 16) )
                *((_BYTE *)v10 + j) = 1;
            }
            else
            {
              v3 = v31;
            }
          }
        }
      }
      v24 = 863;
LABEL_38:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v24,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
                    v14);
    }
    HeapFree(g_hHeap, 0, v10);
    v6 = (unsigned __int64 *)(v9 - 8);
    goto LABEL_7;
  }
  HeapFree(g_hHeap, 0, v10);
LABEL_32:
  `vector destructor iterator'(
    v9,
    8u,
    *v6,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>);
  operator delete(v6, 8 * *v6 + 8);
  return 0;
}

```

## disassembly

```asm
0x180045eb8  mov     [rsp-8+arg_8], rbx
0x180045ebd  push    rbp
0x180045ebe  push    rsi
0x180045ebf  push    rdi
0x180045ec0  push    r12
0x180045ec2  push    r13
0x180045ec4  push    r14
0x180045ec6  push    r15
0x180045ec8  lea     rbp, [rsp-27h]
0x180045ecd  sub     rsp, 0B0h
0x180045ed4  mov     rax, cs:__security_cookie
0x180045edb  xor     rax, rsp
0x180045ede  mov     [rbp+57h+var_40], rax
0x180045ee2  xor     edx, edx; dwFlags
0x180045ee4  mov     [rbp+57h+var_A0], r8
0x180045ee8  mov     r13, r8
0x180045eeb  mov     rdi, rcx
0x180045eee  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180045ef5  lea     r8d, [rdx+28h]; dwBytes
0x180045ef9  call    cs:__imp_HeapAlloc
0x180045eff  mov     rbx, rax
0x180045f02  test    rax, rax
0x180045f05  jnz     short loc_180045F4D
0x180045f07  mov     rcx, [rbp+5Fh]; this
0x180045f0b  lea     r8, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x180045f12  mov     edi, 8007000Eh
0x180045f17  mov     edx, 354h; void *
0x180045f1c  mov     r9d, edi; char *
0x180045f1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045f24  mov     eax, edi
0x180045f26  mov     rcx, [rbp+57h+var_40]
0x180045f2a  xor     rcx, rsp; StackCookie
0x180045f2d  call    __security_check_cookie
0x180045f32  mov     rbx, [rsp+0E0h+arg_8]
0x180045f3a  add     rsp, 0B0h
0x180045f41  pop     r15
0x180045f43  pop     r14
0x180045f45  pop     r13
0x180045f47  pop     r12
0x180045f49  pop     rdi
0x180045f4a  pop     rsi
0x180045f4b  pop     rbp
0x180045f4c  retn
0x180045f4d  mov     qword ptr [rax+8], 0
0x180045f55  lea     rsi, [rax+8]
0x180045f59  mov     qword ptr [rax+10h], 0
0x180045f61  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void *(*)(void *)
0x180045f68  mov     r15d, 4
0x180045f6e  mov     qword ptr [rax+18h], 0
0x180045f76  mov     qword ptr [rax+20h], 0
0x180045f7e  mov     r8d, r15d; unsigned __int64
0x180045f81  mov     rcx, rsi; void *
0x180045f84  mov     [rax], r15
0x180045f87  lea     r12d, [r15+4]
0x180045f8b  mov     edx, r12d; unsigned __int64
0x180045f8e  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180045f93  test    rsi, rsi
0x180045f96  jz      loc_180045F07
0x180045f9c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180045fa3  mov     r8d, r15d; dwBytes
0x180045fa6  xor     edx, edx; dwFlags
0x180045fa8  call    cs:__imp_HeapAlloc
0x180045fae  mov     r14, rax
0x180045fb1  test    rax, rax
0x180045fb4  jnz     short loc_180046000
0x180045fb6  mov     rcx, [rbp+5Fh]; this
0x180045fba  lea     r8, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x180045fc1  mov     edi, 8007000Eh
0x180045fc6  mov     edx, 357h; void *
0x180045fcb  mov     r9d, edi; char *
0x180045fce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045fd3  mov     edx, r12d; unsigned __int64
0x180045fd6  mov     r8, [rbx]; unsigned __int64
0x180045fd9  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180045fe0  mov     rcx, rsi; void *
0x180045fe3  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180045fe8  mov     rdx, [rbx]
0x180045feb  mov     rcx, rbx; void *
0x180045fee  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x180045ff6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180045ffb  jmp     loc_180045F24
0x180046000  xor     eax, eax
0x180046002  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180046006  mov     [r14], eax
0x180046009  lea     r8, [rbp+57h+pDacl]; pDacl
0x18004600d  mov     rcx, [rdi]; pSecurityDescriptor
0x180046010  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180046014  mov     [rbp+57h+bDaclPresent], eax
0x180046017  mov     [rbp+57h+pDacl], rax
0x18004601b  mov     [rbp+57h+bDaclDefaulted], eax
0x18004601e  call    cs:__imp_GetSecurityDescriptorDacl
0x180046024  mov     rax, [rbp+57h+pDacl]
0x180046028  mov     [rbp+57h+var_98], rax
0x18004602c  test    rax, rax
0x18004602f  jz      loc_18004629E
0x180046035  xor     ebx, ebx
0x180046037  mov     [rbp+57h+var_BC], ebx
0x18004603a  cmp     bx, [rax+4]
0x18004603e  jnb     loc_180046156
0x180046044  movzx   edx, bx; dwAceIndex
0x180046047  lea     r8, [rbp+57h+pAce]; pAce
0x18004604b  mov     rcx, rax; pAcl
0x18004604e  mov     [rbp+57h+pAce], 0
0x180046056  call    cs:__imp_GetAce
0x18004605c  test    eax, eax
0x18004605e  jz      loc_18004623C
0x180046064  xor     r12d, r12d
0x180046067  cmp     r12w, r15w
0x18004606b  jnb     loc_180046147
0x180046071  movzx   r15d, r12w
0x180046075  lea     rdi, [rsi+r15*8]
0x180046079  cmp     qword ptr [rdi], 0
0x18004607d  lea     rax, [r15+r15*2]
0x180046081  lea     rbx, ds:0[rax*8]
0x180046089  jnz     short loc_1800460E8
0x18004608b  xor     edx, edx; DomainSid
0x18004608d  cmp     [rbx+r13+8], rdx
0x180046092  jnz     loc_180046217
0x180046098  mov     ecx, [rbx+r13]; WellKnownSidType
0x18004609c  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800460a0  lea     r8, [rbp+57h+pSid]; pSid
0x1800460a4  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800460ab  call    cs:__imp_CreateWellKnownSid
0x1800460b1  test    eax, eax
0x1800460b3  jz      loc_1800461FE
0x1800460b9  mov     edx, [rbp+57h+cbSid]; uBytes
0x1800460bc  xor     ecx, ecx; uFlags
0x1800460be  call    cs:__imp_LocalAlloc
0x1800460c4  mov     rdx, rax
0x1800460c7  mov     rcx, rdi
0x1800460ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800460cf  mov     rdx, [rdi]; pDestinationSid
0x1800460d2  test    rdx, rdx
0x1800460d5  jz      loc_1800461C1
0x1800460db  mov     ecx, [rbp+57h+cbSid]; nDestinationSidLength
0x1800460de  lea     r8, [rbp+57h+pSid]; pSourceSid
0x1800460e2  call    cs:__imp_CopySid
0x1800460e8  mov     rdx, [rbp+57h+pAce]
0x1800460ec  movzx   ecx, byte ptr [rdx]
0x1800460ef  test    ecx, ecx
0x1800460f1  jnz     short loc_180046126
0x1800460f3  mov     r13, rdx
0x1800460f6  lea     rcx, [rdx+8]; pSid1
0x1800460fa  mov     rdx, [rdi]; pSid2
0x1800460fd  call    cs:__imp_EqualSid
0x180046103  test    eax, eax
0x180046105  jz      loc_1800461B8
0x18004610b  mov     eax, [r13+4]
0x18004610f  mov     r13, [rbp+57h+var_A0]
0x180046113  and     eax, [rbx+r13+10h]
0x180046118  cmp     eax, [rbx+r13+10h]
0x18004611d  jnz     short loc_180046138
0x18004611f  mov     byte ptr [r15+r14], 1
0x180046124  jmp     short loc_180046138
0x180046126  sub     ecx, 1
0x180046129  jz      loc_180046267
0x18004612f  cmp     ecx, 1
0x180046132  jz      loc_180046243
0x180046138  inc     r12w
0x18004613c  mov     r15d, 4
0x180046142  jmp     loc_180046067
0x180046147  mov     ebx, [rbp+57h+var_BC]
0x18004614a  mov     rax, [rbp+57h+var_98]
0x18004614e  inc     bx
0x180046151  jmp     loc_180046037
0x180046156  xor     ecx, ecx
0x180046158  cmp     cx, r15w
0x18004615c  jnb     short loc_180046171
0x18004615e  movzx   eax, cx
0x180046161  cmp     byte ptr [rax+r14], 0
0x180046166  jz      loc_18004628F
0x18004616c  inc     cx
0x18004616f  jmp     short loc_180046158
0x180046171  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180046178  mov     r8, r14; lpMem
0x18004617b  xor     edx, edx; dwFlags
0x18004617d  call    cs:__imp_HeapFree
0x180046183  mov     edx, 8; unsigned __int64
0x180046188  lea     rbx, [rsi-8]
0x18004618c  mov     r8, [rbx]; unsigned __int64
0x18004618f  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180046196  mov     rcx, rsi; void *
0x180046199  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18004619e  mov     rdx, [rbx]
0x1800461a1  mov     rcx, rbx; void *
0x1800461a4  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x1800461ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800461b1  xor     eax, eax
0x1800461b3  jmp     loc_180045F26
0x1800461b8  mov     r13, [rbp+57h+var_A0]
0x1800461bc  jmp     loc_180046138
0x1800461c1  mov     edi, 8007000Eh
0x1800461c6  mov     edx, 36Dh; void *
0x1800461cb  mov     rcx, [rbp+5Fh]; this
0x1800461cf  lea     r8, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x1800461d6  mov     r9d, edi; char *
0x1800461d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800461de  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800461e5  mov     r8, r14; lpMem
0x1800461e8  xor     edx, edx; dwFlags
0x1800461ea  call    cs:__imp_HeapFree
0x1800461f0  mov     edx, 8
0x1800461f5  lea     rbx, [rsi-8]
0x1800461f9  jmp     loc_180045FD6
0x1800461fe  mov     edx, 36Ah; void *
0x180046203  mov     rcx, [rbp+5Fh]; this
0x180046207  lea     r8, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x18004620e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046213  mov     edi, eax
0x180046215  jmp     short loc_1800461DE
0x180046217  mov     rcx, rdi
0x18004621a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18004621f  mov     rcx, [rbx+r13+8]; StringSid
0x180046224  mov     rdx, rdi; Sid
0x180046227  call    cs:__imp_ConvertStringSidToSidW
0x18004622d  test    eax, eax
0x18004622f  jnz     loc_1800460E8
0x180046235  mov     edx, 372h
0x18004623a  jmp     short loc_180046203
0x18004623c  mov     edx, 35Fh
0x180046241  jmp     short loc_180046203
0x180046243  lea     rcx, [rdx+8]; pSid1
0x180046247  mov     rdx, [rdi]; pSid2
0x18004624a  call    cs:__imp_EqualSid
0x180046250  test    eax, eax
0x180046252  jz      loc_180046138
0x180046258  mov     edi, 80070057h
0x18004625d  mov     edx, 393h
0x180046262  jmp     loc_1800461CB
0x180046267  mov     rcx, [rbp+57h+pAce]
0x18004626b  mov     rdx, [rdi]; pSid2
0x18004626e  add     rcx, 8; pSid1
0x180046272  call    cs:__imp_EqualSid
0x180046278  test    eax, eax
0x18004627a  jz      loc_180046138
0x180046280  mov     edi, 80070057h
0x180046285  mov     edx, 389h
0x18004628a  jmp     loc_1800461CB
0x18004628f  mov     edi, 80070057h
0x180046294  mov     edx, 3A8h
0x180046299  jmp     loc_1800461CB
0x18004629e  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800462a5  mov     r8, r14; lpMem
0x1800462a8  xor     edx, edx; dwFlags
0x1800462aa  call    cs:__imp_HeapFree
0x1800462b0  mov     rdx, r12
0x1800462b3  jmp     loc_18004618C
```
