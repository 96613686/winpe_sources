# CheckForExpectedAccess(CSecDescriptor *,ushort,ExpectedAccess const *)

- ea: `0x18003a84c`
- end: `0x18003ac80`
- name: `?CheckForExpectedAccess@@YAJPEAVCSecDescriptor@@GPEBUExpectedAccess@@@Z`
- size: `1076`
- prototype: `__int64 __fastcall(struct CSecDescriptor *this, unsigned __int16, const struct ExpectedAccess *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003afb8`

## callees

- `0x18000ce5c`
- `0x18000ce7c`
- `0x1800210f8`
- `0x180039c04`
- `0x18003a84c`
- `0x18003ac88`
- `0x18003af38`
- `0x1800b7ac0`
- `0x1800b7e90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ab21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ab94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ac6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ab21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ab94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ac6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a88d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a943`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a88d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a943`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003aa7a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003aa7a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003aa9b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003ac00`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003ac2e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003aa9b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003ac00`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003ac2e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003aa37`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003aa37`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003a9dc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003a9dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003abd7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003abd7`
- `KERNELBASE!LocalAlloc` at `0x18003aa50`
- `KERNELBASE!LocalAlloc` at `0x18003aa50`

## string_xrefs

- `0x18003a8a5`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18003a95b`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18003ab79`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18003abb7`: `onecore\com\combase\rpcss\olescm\registry.cxx`

## pseudocode

```c
__int64 __fastcall CheckForExpectedAccess(struct CSecDescriptor *this, __int64 a2, const struct ExpectedAccess *a3)
{
  const struct ExpectedAccess *v3; // r13
  unsigned __int64 *v5; // rax
  unsigned __int64 *v6; // rbx
  unsigned int LastError; // edi
  char *v9; // rsi
  bool *v10; // rdx
  bool *v11; // r8
  _DWORD *v12; // r14
  struct _ACL *Dacl; // rax
  int v14; // ebx
  const char *v15; // r9
  unsigned __int16 j; // r12
  PSID *v17; // rdi
  __int64 v18; // rbx
  WELL_KNOWN_SID_TYPE v19; // ecx
  HLOCAL v20; // rax
  _DWORD *v21; // r13
  int v22; // eax
  unsigned __int16 i; // cx
  __int64 v24; // rdx
  __int64 v25; // rdx
  DWORD cbSid; // [rsp+20h] [rbp-59h] BYREF
  int v27; // [rsp+24h] [rbp-55h]
  LPVOID pAce; // [rsp+28h] [rbp-51h] BYREF
  const struct ExpectedAccess *v29; // [rsp+30h] [rbp-49h]
  struct _ACL *v30; // [rsp+38h] [rbp-41h]
  _BYTE pSid[80]; // [rsp+40h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v29 = a3;
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
  v12 = HeapAlloc(g_hHeap, 0, 4u);
  if ( !v12 )
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
  *v12 = 0;
  Dacl = CSecDescriptor::GetDacl(this, v10, v11);
  v30 = Dacl;
  if ( Dacl )
  {
    v14 = 0;
LABEL_10:
    v27 = v14;
    if ( (unsigned __int16)v14 >= Dacl->AceCount )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 4u )
        {
          HeapFree(g_hHeap, 0, v12);
          v6 = (unsigned __int64 *)(v9 - 8);
          goto LABEL_32;
        }
        if ( !*((_BYTE *)v12 + i) )
          break;
      }
      LastError = -2147024809;
      v24 = 936;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
        (const char *)LastError,
        cbSid);
    }
    else
    {
      pAce = 0;
      if ( GetAce(Dacl, (unsigned __int16)v14, &pAce) )
      {
        for ( j = 0; ; ++j )
        {
          if ( j >= 4u )
          {
            HIWORD(v14) = HIWORD(v27);
            Dacl = v30;
            LOWORD(v14) = v27 + 1;
            goto LABEL_10;
          }
          v17 = (PSID *)&v9[8 * j];
          v18 = 24LL * j;
          if ( !*v17 )
          {
            if ( *(_QWORD *)((char *)v3 + v18 + 8) )
            {
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &v9[8 * j],
                0);
              if ( !ConvertStringSidToSidW(*(LPCWSTR *)((char *)v3 + v18 + 8), (PSID *)&v9[8 * j]) )
              {
                v25 = 882;
                goto LABEL_38;
              }
            }
            else
            {
              v19 = *(_DWORD *)((char *)v3 + v18);
              cbSid = 68;
              if ( !CreateWellKnownSid(v19, 0, pSid, &cbSid) )
              {
                v25 = 874;
                goto LABEL_38;
              }
              v20 = LocalAlloc(0, cbSid);
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &v9[8 * j],
                v20);
              if ( !*v17 )
              {
                LastError = -2147024882;
                v24 = 877;
                goto LABEL_35;
              }
              CopySid(cbSid, *v17, pSid);
            }
          }
          if ( *(_BYTE *)pAce )
          {
            if ( *(_BYTE *)pAce == 1 )
            {
              if ( EqualSid((char *)pAce + 8, *v17) )
              {
                LastError = -2147024809;
                v24 = 905;
                goto LABEL_35;
              }
            }
            else if ( *(_BYTE *)pAce == 2 && EqualSid((char *)pAce + 8, *v17) )
            {
              LastError = -2147024809;
              v24 = 915;
              goto LABEL_35;
            }
          }
          else
          {
            v21 = pAce;
            if ( EqualSid((char *)pAce + 8, *v17) )
            {
              v22 = v21[1];
              v3 = v29;
              if ( (*(_DWORD *)((_BYTE *)v29 + v18 + 16) & v22) == *(_DWORD *)((char *)v29 + v18 + 16) )
                *((_BYTE *)v12 + j) = 1;
            }
            else
            {
              v3 = v29;
            }
          }
        }
      }
      v25 = 863;
LABEL_38:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v25,
                    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
                    v15);
    }
    HeapFree(g_hHeap, 0, v12);
    v6 = (unsigned __int64 *)(v9 - 8);
    goto LABEL_7;
  }
  HeapFree(g_hHeap, 0, v12);
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
0x18003a84c  mov     [rsp-8+arg_8], rbx
0x18003a851  push    rbp
0x18003a852  push    rsi
0x18003a853  push    rdi
0x18003a854  push    r12
0x18003a856  push    r13
0x18003a858  push    r14
0x18003a85a  push    r15
0x18003a85c  lea     rbp, [rsp-27h]
0x18003a861  sub     rsp, 0A0h
0x18003a868  mov     rax, cs:__security_cookie
0x18003a86f  xor     rax, rsp
0x18003a872  mov     [rbp+57h+var_40], rax
0x18003a876  xor     edx, edx; dwFlags
0x18003a878  mov     [rbp+57h+var_A0], r8
0x18003a87c  mov     r13, r8
0x18003a87f  mov     rdi, rcx
0x18003a882  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003a889  lea     r8d, [rdx+28h]; dwBytes
0x18003a88d  call    cs:__imp_HeapAlloc
0x18003a894  nop     dword ptr [rax+rax+00h]
0x18003a899  mov     rbx, rax
0x18003a89c  test    rax, rax
0x18003a89f  jnz     short loc_18003A8E8
0x18003a8a1  mov     rcx, [rbp+5Fh]; this
0x18003a8a5  lea     r8, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x18003a8ac  mov     edi, 8007000Eh
0x18003a8b1  mov     edx, 354h; void *
0x18003a8b6  mov     r9d, edi; char *
0x18003a8b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a8be  mov     eax, edi
0x18003a8c0  mov     rcx, [rbp+57h+var_40]
0x18003a8c4  xor     rcx, rsp; StackCookie
0x18003a8c7  call    __security_check_cookie
0x18003a8cc  mov     rbx, [rsp+0D0h+arg_8]
0x18003a8d4  add     rsp, 0A0h
0x18003a8db  pop     r15
0x18003a8dd  pop     r14
0x18003a8df  pop     r13
0x18003a8e1  pop     r12
0x18003a8e3  pop     rdi
0x18003a8e4  pop     rsi
0x18003a8e5  pop     rbp
0x18003a8e6  retn
0x18003a8e8  mov     qword ptr [rax+8], 0
0x18003a8f0  lea     rsi, [rax+8]
0x18003a8f4  mov     qword ptr [rax+10h], 0
0x18003a8fc  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void *(*)(void *)
0x18003a903  mov     r15d, 4
0x18003a909  mov     qword ptr [rax+18h], 0
0x18003a911  mov     qword ptr [rax+20h], 0
0x18003a919  mov     r8d, r15d; unsigned __int64
0x18003a91c  mov     rcx, rsi; void *
0x18003a91f  mov     [rax], r15
0x18003a922  lea     r12d, [r15+4]
0x18003a926  mov     edx, r12d; unsigned __int64
0x18003a929  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18003a92e  test    rsi, rsi
0x18003a931  jz      loc_18003A8A1
0x18003a937  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003a93e  mov     r8d, r15d; dwBytes
0x18003a941  xor     edx, edx; dwFlags
0x18003a943  call    cs:__imp_HeapAlloc
0x18003a94a  nop     dword ptr [rax+rax+00h]
0x18003a94f  mov     r14, rax
0x18003a952  test    rax, rax
0x18003a955  jnz     short loc_18003A9A1
0x18003a957  mov     rcx, [rbp+5Fh]; this
0x18003a95b  lea     r8, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x18003a962  mov     edi, 8007000Eh
0x18003a967  mov     edx, 357h; void *
0x18003a96c  mov     r9d, edi; char *
0x18003a96f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a974  mov     edx, r12d; unsigned __int64
0x18003a977  mov     r8, [rbx]; unsigned __int64
0x18003a97a  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x18003a981  mov     rcx, rsi; void *
0x18003a984  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003a989  mov     rdx, [rbx]
0x18003a98c  mov     rcx, rbx; void *
0x18003a98f  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x18003a997  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003a99c  jmp     loc_18003A8BE
0x18003a9a1  xor     eax, eax
0x18003a9a3  mov     rcx, rdi; this
0x18003a9a6  mov     [r14], eax
0x18003a9a9  call    ?GetDacl@CSecDescriptor@@QEBAPEAU_ACL@@PEA_N0@Z; CSecDescriptor::GetDacl(bool *,bool *)
0x18003a9ae  mov     [rbp+57h+var_98], rax
0x18003a9b2  test    rax, rax
0x18003a9b5  jz      loc_18003AC60
0x18003a9bb  xor     ebx, ebx
0x18003a9bd  mov     [rbp+57h+var_AC], ebx
0x18003a9c0  cmp     bx, [rax+4]
0x18003a9c4  jnb     loc_18003AAFA
0x18003a9ca  movzx   edx, bx; dwAceIndex
0x18003a9cd  lea     r8, [rbp+57h+pAce]; pAce
0x18003a9d1  mov     rcx, rax; pAcl
0x18003a9d4  mov     [rbp+57h+pAce], 0
0x18003a9dc  call    cs:__imp_GetAce
0x18003a9e3  nop     dword ptr [rax+rax+00h]
0x18003a9e8  test    eax, eax
0x18003a9ea  jz      loc_18003ABF2
0x18003a9f0  xor     r12d, r12d
0x18003a9f3  cmp     r12w, r15w
0x18003a9f7  jnb     loc_18003AAEB
0x18003a9fd  movzx   r15d, r12w
0x18003aa01  lea     rdi, [rsi+r15*8]
0x18003aa05  cmp     qword ptr [rdi], 0
0x18003aa09  lea     rax, [r15+r15*2]
0x18003aa0d  lea     rbx, ds:0[rax*8]
0x18003aa15  jnz     short loc_18003AA86
0x18003aa17  xor     edx, edx; DomainSid
0x18003aa19  cmp     [rbx+r13+8], rdx
0x18003aa1e  jnz     loc_18003ABC7
0x18003aa24  mov     ecx, [rbx+r13]; WellKnownSidType
0x18003aa28  lea     r9, [rbp+57h+cbSid]; cbSid
0x18003aa2c  lea     r8, [rbp+57h+pSid]; pSid
0x18003aa30  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18003aa37  call    cs:__imp_CreateWellKnownSid
0x18003aa3e  nop     dword ptr [rax+rax+00h]
0x18003aa43  test    eax, eax
0x18003aa45  jz      loc_18003ABAE
0x18003aa4b  mov     edx, [rbp+57h+cbSid]; uBytes
0x18003aa4e  xor     ecx, ecx; uFlags
0x18003aa50  call    cs:__imp_LocalAlloc
0x18003aa57  nop     dword ptr [rax+rax+00h]
0x18003aa5c  mov     rdx, rax
0x18003aa5f  mov     rcx, rdi
0x18003aa62  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18003aa67  mov     rdx, [rdi]; pDestinationSid
0x18003aa6a  test    rdx, rdx
0x18003aa6d  jz      loc_18003AB6B
0x18003aa73  mov     ecx, [rbp+57h+cbSid]; nDestinationSidLength
0x18003aa76  lea     r8, [rbp+57h+pSid]; pSourceSid
0x18003aa7a  call    cs:__imp_CopySid
0x18003aa81  nop     dword ptr [rax+rax+00h]
0x18003aa86  mov     rdx, [rbp+57h+pAce]
0x18003aa8a  movzx   ecx, byte ptr [rdx]
0x18003aa8d  test    ecx, ecx
0x18003aa8f  jnz     short loc_18003AACA
0x18003aa91  mov     r13, rdx
0x18003aa94  lea     rcx, [rdx+8]; pSid1
0x18003aa98  mov     rdx, [rdi]; pSid2
0x18003aa9b  call    cs:__imp_EqualSid
0x18003aaa2  nop     dword ptr [rax+rax+00h]
0x18003aaa7  test    eax, eax
0x18003aaa9  jz      loc_18003AB62
0x18003aaaf  mov     eax, [r13+4]
0x18003aab3  mov     r13, [rbp+57h+var_A0]
0x18003aab7  and     eax, [rbx+r13+10h]
0x18003aabc  cmp     eax, [rbx+r13+10h]
0x18003aac1  jnz     short loc_18003AADC
0x18003aac3  mov     byte ptr [r14+r15], 1
0x18003aac8  jmp     short loc_18003AADC
0x18003aaca  sub     ecx, 1
0x18003aacd  jz      loc_18003AC23
0x18003aad3  cmp     ecx, 1
0x18003aad6  jz      loc_18003ABF9
0x18003aadc  inc     r12w
0x18003aae0  mov     r15d, 4
0x18003aae6  jmp     loc_18003A9F3
0x18003aaeb  mov     ebx, [rbp+57h+var_AC]
0x18003aaee  mov     rax, [rbp+57h+var_98]
0x18003aaf2  inc     bx
0x18003aaf5  jmp     loc_18003A9BD
0x18003aafa  xor     ecx, ecx
0x18003aafc  cmp     cx, r15w
0x18003ab00  jnb     short loc_18003AB15
0x18003ab02  movzx   eax, cx
0x18003ab05  cmp     byte ptr [rax+r14], 0
0x18003ab0a  jz      loc_18003AC51
0x18003ab10  inc     cx
0x18003ab13  jmp     short loc_18003AAFC
0x18003ab15  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003ab1c  mov     r8, r14; lpMem
0x18003ab1f  xor     edx, edx; dwFlags
0x18003ab21  call    cs:__imp_HeapFree
0x18003ab28  nop     dword ptr [rax+rax+00h]
0x18003ab2d  mov     edx, 8; unsigned __int64
0x18003ab32  lea     rbx, [rsi-8]
0x18003ab36  mov     r8, [rbx]; unsigned __int64
0x18003ab39  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x18003ab40  mov     rcx, rsi; void *
0x18003ab43  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003ab48  mov     rdx, [rbx]
0x18003ab4b  mov     rcx, rbx; void *
0x18003ab4e  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x18003ab56  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003ab5b  xor     eax, eax
0x18003ab5d  jmp     loc_18003A8C0
0x18003ab62  mov     r13, [rbp+57h+var_A0]
0x18003ab66  jmp     loc_18003AADC
0x18003ab6b  mov     edi, 8007000Eh
0x18003ab70  mov     edx, 36Dh; void *
0x18003ab75  mov     rcx, [rbp+5Fh]; this
0x18003ab79  lea     r8, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x18003ab80  mov     r9d, edi; char *
0x18003ab83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ab88  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003ab8f  mov     r8, r14; lpMem
0x18003ab92  xor     edx, edx; dwFlags
0x18003ab94  call    cs:__imp_HeapFree
0x18003ab9b  nop     dword ptr [rax+rax+00h]
0x18003aba0  mov     edx, 8
0x18003aba5  lea     rbx, [rsi-8]
0x18003aba9  jmp     loc_18003A977
0x18003abae  mov     edx, 36Ah; void *
0x18003abb3  mov     rcx, [rbp+5Fh]; this
0x18003abb7  lea     r8, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x18003abbe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003abc3  mov     edi, eax
0x18003abc5  jmp     short loc_18003AB88
0x18003abc7  mov     rcx, rdi
0x18003abca  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18003abcf  mov     rcx, [rbx+r13+8]; StringSid
0x18003abd4  mov     rdx, rdi; Sid
0x18003abd7  call    cs:__imp_ConvertStringSidToSidW
0x18003abde  nop     dword ptr [rax+rax+00h]
0x18003abe3  test    eax, eax
0x18003abe5  jnz     loc_18003AA86
0x18003abeb  mov     edx, 372h
0x18003abf0  jmp     short loc_18003ABB3
0x18003abf2  mov     edx, 35Fh
0x18003abf7  jmp     short loc_18003ABB3
0x18003abf9  lea     rcx, [rdx+8]; pSid1
0x18003abfd  mov     rdx, [rdi]; pSid2
0x18003ac00  call    cs:__imp_EqualSid
0x18003ac07  nop     dword ptr [rax+rax+00h]
0x18003ac0c  test    eax, eax
0x18003ac0e  jz      loc_18003AADC
0x18003ac14  mov     edi, 80070057h
0x18003ac19  mov     edx, 393h
0x18003ac1e  jmp     loc_18003AB75
0x18003ac23  mov     rcx, [rbp+57h+pAce]
0x18003ac27  mov     rdx, [rdi]; pSid2
0x18003ac2a  add     rcx, 8; pSid1
0x18003ac2e  call    cs:__imp_EqualSid
0x18003ac35  nop     dword ptr [rax+rax+00h]
0x18003ac3a  test    eax, eax
0x18003ac3c  jz      loc_18003AADC
0x18003ac42  mov     edi, 80070057h
0x18003ac47  mov     edx, 389h
0x18003ac4c  jmp     loc_18003AB75
0x18003ac51  mov     edi, 80070057h
0x18003ac56  mov     edx, 3A8h
0x18003ac5b  jmp     loc_18003AB75
0x18003ac60  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003ac67  mov     r8, r14; lpMem
0x18003ac6a  xor     edx, edx; dwFlags
0x18003ac6c  call    cs:__imp_HeapFree
0x18003ac73  nop     dword ptr [rax+rax+00h]
0x18003ac78  mov     rdx, r12
0x18003ac7b  jmp     loc_18003AB36
```
