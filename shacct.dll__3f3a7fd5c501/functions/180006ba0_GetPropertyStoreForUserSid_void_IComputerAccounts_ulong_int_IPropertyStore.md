# _GetPropertyStoreForUserSid(void *,IComputerAccounts * *,ulong,int,IPropertyStore * *)

- ea: `0x180006ba0`
- end: `0x180006f71`
- name: `?_GetPropertyStoreForUserSid@@YAJPEAXPEAPEAUIComputerAccounts@@KHPEAPEAUIPropertyStore@@@Z`
- size: `977`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct IComputerAccounts **@<rdx>, unsigned int@<r8d>, int@<r9d>, struct IPropertyStore **)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000de40`
- `0x18000dee0`
- `0x18000e4a0`

## callees

- `0x180006ba0`
- `0x180008270`
- `0x180008300`
- `0x180008c10`
- `0x18000bcc0`
- `0x18000d740`
- `0x18000d8fc`
- `0x18000ed10`
- `0x180016880`
- `0x180017010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180006d9c`
- `SHCORE!SHStrDupW` at `0x180006d9c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180006c37`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180006c37`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180006c45`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180006c45`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006e01`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006e01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006da8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006da8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006eb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006dbb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006dbb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006df0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180006df0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006ca1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006d8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006ca1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006d8a`

## pseudocode

```c
__int64 __fastcall _GetPropertyStoreForUserSid(
        void *a1,
        struct IComputerAccounts **a2,
        __int64 a3,
        int a4,
        struct IPropertyStore **pv)
{
  void *v6; // r14
  CUserPropertyStore *v7; // rax
  CUserPropertyStore *v8; // rsi
  HDPA v9; // rax
  int String; // r15d
  PUCHAR SidSubAuthorityCount; // rax
  unsigned int i; // ebx
  void *v13; // rdi
  int v14; // r14d
  __int64 v15; // rax
  HRESULT Error; // edi
  bool v17; // di
  struct IPropertyStore **v18; // r13
  LPWSTR v19; // rbx
  void *p; // [rsp+20h] [rbp-50h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-48h] BYREF
  __int64 v23; // [rsp+30h] [rbp-40h] BYREF
  LPWSTR v24; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-30h] BYREF
  PSID Sid; // [rsp+50h] [rbp-20h]
  DWORD v28; // [rsp+B0h] [rbp+40h]

  v6 = a1;
  *pv = 0;
  v7 = (CUserPropertyStore *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
    return 2147942414LL;
  v8 = CUserPropertyStore::CUserPropertyStore(v7);
  if ( !v8 )
    return 2147942414LL;
  v9 = g_pfn_DPA_Create(2);
  *((_QWORD *)v8 + 3) = v9;
  if ( !v9 )
  {
    String = -2147024882;
    goto LABEL_43;
  }
  v28 = 0;
  String = -2147467259;
  if ( v6 )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(v6);
    v28 = *GetSidSubAuthority(v6, (unsigned int)*SidSubAuthorityCount - 1);
  }
  for ( i = 0; i < 4; ++i )
  {
    p = 0;
    v23 = 0;
    if ( (**(int (__fastcall ***)(struct IComputerAccounts *, GUID *, __int64 *))a2[i])(
           a2[i],
           &GUID_fde873d4_e2de_427c_89bd_c234b5f2dc43,
           &v23) < 0 )
    {
      if ( (*(int (__fastcall **)(struct IComputerAccounts *, _QWORD, void **))(*(_QWORD *)a2[i] + 80LL))(
             a2[i],
             v28,
             &p) >= 0 )
      {
        StringSid = 0;
        Sid = 0;
        v15 = *(_QWORD *)p;
        *(_OWORD *)pvar = 0;
        if ( (*(int (__fastcall **)(void *, __int128 *, PROPVARIANT *))(v15 + 40))(p, &PKEY_SAM_SecurityID, pvar) < 0 )
          goto LABEL_22;
        Error = -2147467259;
        if ( LOWORD(pvar[0]) == 65 )
        {
          v24 = 0;
          if ( ConvertSidToStringSidW(Sid, &v24) )
          {
            Error = SHStrDupW(v24, &StringSid);
            LocalFree(v24);
          }
          else
          {
            Error = ResultFromKnownLastError();
          }
        }
        PropVariantClear(pvar);
        if ( Error < 0 )
        {
LABEL_22:
          if ( (int)IPropertyStore_GetString(p, &PKEY_Identity_PrimarySid, &StringSid) < 0 )
            goto LABEL_26;
        }
        v17 = 0;
        v24 = 0;
        if ( ConvertStringSidToSidW(StringSid, (PSID *)&v24) )
        {
          v17 = EqualSid(v6, v24);
          LocalFree(v24);
        }
        CoTaskMemFree(StringSid);
        if ( !v17 )
        {
LABEL_26:
          (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
          continue;
        }
      }
    }
    else
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(v6, &StringSid) )
      {
        (*(void (__fastcall **)(__int64, LPWSTR, void **))(*(_QWORD *)v23 + 104LL))(v23, StringSid, &p);
        LocalFree(StringSid);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v13 = p;
    if ( p )
    {
      if ( DPA_InsertPtr(*((HDPA *)v8 + 3), 0x7FFFFFFF, p) == -1 )
      {
        v14 = -2147024882;
      }
      else
      {
        v14 = 0;
        if ( i == 3 )
        {
          *((_BYTE *)v8 + 33) = 1;
        }
        else if ( !i )
        {
          *((_BYTE *)v8 + 32) = 1;
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 8LL))(v13);
      }
      if ( String < 0 )
        String = v14;
      (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
      v6 = a1;
    }
  }
  v18 = pv;
  if ( String >= 0 )
  {
    pv = 0;
    String = IPropertyStore_GetString(v8, &PKEY_SAM_Name, &pv);
    if ( String >= 0 )
    {
      CoTaskMemFree(pv);
      goto LABEL_41;
    }
    if ( !a4 )
    {
      v24 = 0;
      String = _CreateReadOnlyPropStoreForSid(v6, (struct IPropertyStore **)&v24);
      if ( String >= 0 )
      {
        v19 = v24;
        String = CUserPropertyStore::AddPropertyStore(v8, v24, 0xFFFFFFFFLL);
        (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)v19 + 16LL))(v19);
        if ( String >= 0 )
        {
LABEL_41:
          *v18 = (struct IPropertyStore *)v8;
          (*(void (__fastcall **)(CUserPropertyStore *))(*(_QWORD *)v8 + 8LL))(v8);
        }
      }
    }
  }
LABEL_43:
  (*(void (__fastcall **)(CUserPropertyStore *))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180006ba0  mov     [rsp-28h+arg_18], r9d
0x180006ba5  mov     [rsp-28h+arg_10], r8d
0x180006baa  mov     [rsp-28h+arg_0], rcx
0x180006baf  push    rbp
0x180006bb0  push    rdi
0x180006bb1  push    r12
0x180006bb3  push    r13
0x180006bb5  push    r14
0x180006bb7  mov     rbp, rsp
0x180006bba  sub     rsp, 70h
0x180006bbe  mov     r13, [rbp+pv]
0x180006bc2  mov     r12, rdx
0x180006bc5  mov     r14, rcx
0x180006bc8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006bcf  xor     edi, edi
0x180006bd1  mov     ecx, 28h ; '('; unsigned __int64
0x180006bd6  mov     [r13+0], rdi
0x180006bda  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006bdf  test    rax, rax
0x180006be2  jz      loc_180006F5F
0x180006be8  mov     rcx, rax; this
0x180006beb  mov     [rsp+70h+var_8], rsi
0x180006bf0  call    ??0CUserPropertyStore@@QEAA@XZ; CUserPropertyStore::CUserPropertyStore(void)
0x180006bf5  mov     rsi, rax
0x180006bf8  test    rax, rax
0x180006bfb  jz      loc_180006F58
0x180006c01  mov     [rsp+70h+var_10], r15
0x180006c06  mov     ecx, 2; cItemGrow
0x180006c0b  mov     [rsp+70h+arg_8], rbx
0x180006c13  call    cs:g_pfn_DPA_Create
0x180006c19  mov     [rsi+18h], rax
0x180006c1d  test    rax, rax
0x180006c20  jz      loc_180006F21
0x180006c26  mov     [rbp+arg_10], edi
0x180006c29  mov     r15d, 80004005h
0x180006c2f  test    r14, r14
0x180006c32  jz      short loc_180006C50
0x180006c34  mov     rcx, r14; pSid
0x180006c37  call    cs:__imp_GetSidSubAuthorityCount
0x180006c3d  mov     rcx, r14; pSid
0x180006c40  movzx   edx, byte ptr [rax]
0x180006c43  dec     edx; nSubAuthority
0x180006c45  call    cs:__imp_GetSidSubAuthority
0x180006c4b  mov     eax, [rax]
0x180006c4d  mov     [rbp+arg_10], eax
0x180006c50  mov     r13d, [rbp+arg_10]
0x180006c54  mov     ebx, edi
0x180006c56  jmp     short loc_180006C62
0x180006c60  xor     edi, edi
0x180006c62  mov     [rbp+p], rdi
0x180006c66  lea     r8, [rbp+var_40]
0x180006c6a  mov     [rbp+var_40], rdi
0x180006c6e  lea     rdx, _GUID_fde873d4_e2de_427c_89bd_c234b5f2dc43
0x180006c75  mov     eax, ebx
0x180006c77  mov     rcx, [r12+rax*8]
0x180006c7b  lea     rdi, [r12+rax*8]
0x180006c7f  mov     rax, [rcx]
0x180006c82  mov     rax, [rax]
0x180006c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8a  test    eax, eax
0x180006c8c  js      loc_180006D20
0x180006c92  lea     rdx, [rbp+StringSid]; StringSid
0x180006c96  mov     [rbp+StringSid], 0
0x180006c9e  mov     rcx, r14; Sid
0x180006ca1  call    cs:__imp_ConvertSidToStringSidW
0x180006ca7  test    eax, eax
0x180006ca9  jz      short loc_180006CCD
0x180006cab  mov     rcx, [rbp+var_40]
0x180006caf  lea     r8, [rbp+p]
0x180006cb3  mov     rdx, [rbp+StringSid]
0x180006cb7  mov     rax, [rcx]
0x180006cba  mov     rax, [rax+68h]
0x180006cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc3  mov     rcx, [rbp+StringSid]; hMem
0x180006cc7  call    cs:__imp_LocalFree
0x180006ccd  mov     rcx, [rbp+var_40]
0x180006cd1  mov     rax, [rcx]
0x180006cd4  mov     rax, [rax+10h]
0x180006cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cdd  mov     rdi, [rbp+p]
0x180006ce1  test    rdi, rdi
0x180006ce4  jz      loc_180006E79
0x180006cea  mov     rcx, [rsi+18h]; hdpa
0x180006cee  mov     r8, rdi; p
0x180006cf1  mov     edx, 7FFFFFFFh; i
0x180006cf6  mov     r14d, 80070057h
0x180006cfc  call    cs:__imp_DPA_InsertPtr
0x180006d02  cmp     eax, 0FFFFFFFFh
0x180006d05  jz      loc_180006E55
0x180006d0b  xor     r14d, r14d
0x180006d0e  cmp     ebx, 3
0x180006d11  jnz     loc_180006E3C
0x180006d17  mov     byte ptr [rsi+21h], 1
0x180006d1b  jmp     loc_180006E44
0x180006d20  mov     rcx, [rdi]
0x180006d23  lea     r8, [rbp+p]
0x180006d27  mov     edx, r13d
0x180006d2a  mov     rax, [rcx]
0x180006d2d  mov     rax, [rax+50h]
0x180006d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d36  test    eax, eax
0x180006d38  js      short loc_180006CDD
0x180006d3a  mov     rcx, [rbp+p]
0x180006d3e  lea     r8, [rbp+pvar]
0x180006d42  xor     eax, eax
0x180006d44  mov     [rbp+StringSid], 0
0x180006d4c  mov     [rbp+Sid], rax
0x180006d50  lea     rdx, PKEY_SAM_SecurityID
0x180006d57  xorps   xmm0, xmm0
0x180006d5a  mov     rax, [rcx]
0x180006d5d  movups  xmmword ptr [rbp+pvar], xmm0
0x180006d61  mov     rax, [rax+28h]
0x180006d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d6a  test    eax, eax
0x180006d6c  js      short loc_180006DC5
0x180006d6e  cmp     word ptr [rbp+pvar], 41h ; 'A'
0x180006d73  mov     edi, 80004005h
0x180006d78  jnz     short loc_180006DB7
0x180006d7a  mov     rcx, [rbp+Sid]; Sid
0x180006d7e  lea     rdx, [rbp+var_38]; StringSid
0x180006d82  mov     [rbp+var_38], 0
0x180006d8a  call    cs:__imp_ConvertSidToStringSidW
0x180006d90  test    eax, eax
0x180006d92  jz      short loc_180006DB0
0x180006d94  mov     rcx, [rbp+var_38]; psz
0x180006d98  lea     rdx, [rbp+StringSid]; ppwsz
0x180006d9c  call    cs:__imp_SHStrDupW
0x180006da2  mov     rcx, [rbp+var_38]; hMem
0x180006da6  mov     edi, eax
0x180006da8  call    cs:__imp_LocalFree
0x180006dae  jmp     short loc_180006DB7
0x180006db0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006db5  mov     edi, eax
0x180006db7  lea     rcx, [rbp+pvar]; pvar
0x180006dbb  call    cs:__imp_PropVariantClear
0x180006dc1  test    edi, edi
0x180006dc3  jns     short loc_180006DDD
0x180006dc5  mov     rcx, [rbp+p]
0x180006dc9  lea     r8, [rbp+StringSid]
0x180006dcd  lea     rdx, PKEY_Identity_PrimarySid
0x180006dd4  call    IPropertyStore_GetString
0x180006dd9  test    eax, eax
0x180006ddb  js      short loc_180006E2A
0x180006ddd  mov     rcx, [rbp+StringSid]; StringSid
0x180006de1  lea     rdx, [rbp+var_38]; Sid
0x180006de5  xor     dil, dil
0x180006de8  mov     [rbp+var_38], 0
0x180006df0  call    cs:__imp_ConvertStringSidToSidW
0x180006df6  test    eax, eax
0x180006df8  jz      short loc_180006E17
0x180006dfa  mov     rdx, [rbp+var_38]; pSid2
0x180006dfe  mov     rcx, r14; pSid1
0x180006e01  call    cs:__imp_EqualSid
0x180006e07  mov     rcx, [rbp+var_38]; hMem
0x180006e0b  test    eax, eax
0x180006e0d  setnz   dil
0x180006e11  call    cs:__imp_LocalFree
0x180006e17  mov     rcx, [rbp+StringSid]; pv
0x180006e1b  call    cs:__imp_CoTaskMemFree
0x180006e21  test    dil, dil
0x180006e24  jnz     loc_180006CDD
0x180006e2a  mov     rcx, [rbp+p]
0x180006e2e  mov     rax, [rcx]
0x180006e31  mov     rax, [rax+10h]
0x180006e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3a  jmp     short loc_180006E79
0x180006e3c  test    ebx, ebx
0x180006e3e  jnz     short loc_180006E44
0x180006e40  mov     byte ptr [rsi+20h], 1
0x180006e44  mov     rax, [rdi]
0x180006e47  mov     rcx, rdi
0x180006e4a  mov     rax, [rax+8]
0x180006e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e53  jmp     short loc_180006E5B
0x180006e55  mov     r14d, 8007000Eh
0x180006e5b  mov     rdi, [rbp+p]
0x180006e5f  test    r15d, r15d
0x180006e62  mov     rcx, rdi
0x180006e65  cmovs   r15d, r14d
0x180006e69  mov     rax, [rdi]
0x180006e6c  mov     rax, [rax+10h]
0x180006e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e75  mov     r14, [rbp+arg_0]
0x180006e79  inc     ebx
0x180006e7b  cmp     ebx, 4
0x180006e7e  jb      loc_180006C60
0x180006e84  mov     r13, [rbp+pv]
0x180006e88  test    r15d, r15d
0x180006e8b  js      loc_180006F27
0x180006e91  lea     r8, [rbp+pv]
0x180006e95  mov     [rbp+pv], 0
0x180006e9d  lea     rdx, PKEY_SAM_Name
0x180006ea4  mov     rcx, rsi
0x180006ea7  call    IPropertyStore_GetString
0x180006eac  mov     r15d, eax
0x180006eaf  test    eax, eax
0x180006eb1  js      short loc_180006EBF
0x180006eb3  mov     rcx, [rbp+pv]; pv
0x180006eb7  call    cs:__imp_CoTaskMemFree
0x180006ebd  jmp     short loc_180006F0C
0x180006ebf  cmp     [rbp+arg_18], 0
0x180006ec3  jnz     short loc_180006F27
0x180006ec5  lea     rdx, [rbp+var_38]; struct IPropertyStore **
0x180006ec9  mov     [rbp+var_38], 0
0x180006ed1  mov     rcx, r14; void *
0x180006ed4  call    ?_CreateReadOnlyPropStoreForSid@@YAJPEAXPEAPEAUIPropertyStore@@@Z; _CreateReadOnlyPropStoreForSid(void *,IPropertyStore * *)
0x180006ed9  mov     r15d, eax
0x180006edc  test    eax, eax
0x180006ede  js      short loc_180006F27
0x180006ee0  mov     rbx, [rbp+var_38]
0x180006ee4  mov     r8d, 0FFFFFFFFh
0x180006eea  mov     rdx, rbx
0x180006eed  mov     rcx, rsi
0x180006ef0  call    ?AddPropertyStore@CUserPropertyStore@@QEAAJPEAUIPropertyStore@@W4PROPSTORE_INDEX@@@Z; CUserPropertyStore::AddPropertyStore(IPropertyStore *,PROPSTORE_INDEX)
0x180006ef5  mov     r15d, eax
0x180006ef8  mov     rcx, rbx
0x180006efb  mov     rax, [rbx]
0x180006efe  mov     rax, [rax+10h]
0x180006f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f07  test    r15d, r15d
0x180006f0a  js      short loc_180006F27
0x180006f0c  mov     [r13+0], rsi
0x180006f10  mov     rcx, rsi
0x180006f13  mov     rax, [rsi]
0x180006f16  mov     rax, [rax+8]
0x180006f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f1f  jmp     short loc_180006F27
0x180006f21  mov     r15d, 8007000Eh
0x180006f27  mov     rax, [rsi]
0x180006f2a  mov     rcx, rsi
0x180006f2d  mov     rax, [rax+10h]
0x180006f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f36  mov     rbx, [rsp+70h+arg_8]
0x180006f3e  mov     eax, r15d
0x180006f41  mov     r15, [rsp+70h+var_10]
0x180006f46  mov     rsi, [rsp+70h+var_8]
0x180006f4b  add     rsp, 70h
0x180006f4f  pop     r14
0x180006f51  pop     r13
0x180006f53  pop     r12
0x180006f55  pop     rdi
0x180006f56  pop     rbp
0x180006f57  retn
0x180006f58  mov     eax, 8007000Eh
0x180006f5d  jmp     short loc_180006F46
0x180006f5f  mov     eax, 8007000Eh
0x180006f64  add     rsp, 70h
0x180006f68  pop     r14
0x180006f6a  pop     r13
0x180006f6c  pop     r12
0x180006f6e  pop     rdi
0x180006f6f  pop     rbp
0x180006f70  retn
```
