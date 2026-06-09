# CUserAccounts::_AddUsers(IComputerAccounts *)

- ea: `0x180007e40`
- end: `0x18000805c`
- name: `?_AddUsers@CUserAccounts@@AEAAJPEAUIComputerAccounts@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(CUserAccounts *__hidden this, struct IComputerAccounts *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009900`

## callees

- `0x180007e40`
- `0x180008d90`
- `0x1800092e0`
- `0x18000bcc0`
- `0x18000ef58`
- `0x180017010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180007f18`
- `SHCORE!SHStrDupW` at `0x180007f18`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180007f6b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180007f6b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180007f79`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180007f79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007fee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008037`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007fee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ff8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f37`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f37`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180007f51`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180007f51`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007f06`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007f06`

## pseudocode

```c
__int64 __fastcall CUserAccounts::_AddUsers(HDPA *this, struct IComputerAccounts *a2)
{
  __int64 v2; // rax
  __int64 result; // rax
  HRESULT Error; // edi
  unsigned int v7; // ebx
  PSID v8; // r12
  __int64 v9; // rax
  __int64 v10; // rax
  PSID v11; // rsi
  PUCHAR SidSubAuthorityCount; // rax
  PSID v13; // rcx
  unsigned int v14; // ebx
  LPWSTR StringSid; // [rsp+30h] [rbp-40h] BYREF
  LPWSTR ppwsz; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-30h] BYREF
  PSID Sid; // [rsp+50h] [rbp-20h]
  unsigned int v19; // [rsp+A8h] [rbp+38h] BYREF
  PSID pSid; // [rsp+B0h] [rbp+40h] BYREF
  __int64 *v21; // [rsp+B8h] [rbp+48h] BYREF

  v2 = *(_QWORD *)a2;
  v19 = 0;
  result = (*(__int64 (__fastcall **)(struct IComputerAccounts *, unsigned int *))(v2 + 32))(a2, &v19);
  Error = result;
  if ( (int)result >= 0 )
  {
    v7 = 0;
    v8 = 0;
    while ( 1 )
    {
      if ( v7 >= v19 )
      {
LABEL_27:
        if ( !v8 )
          return (unsigned int)Error;
        result = CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(this + 3, v8);
        v14 = result;
        if ( (int)result < 0 )
        {
          LocalFree(v8);
          return v14;
        }
        return result;
      }
      v9 = *(_QWORD *)a2;
      v21 = 0;
      Error = (*(__int64 (__fastcall **)(struct IComputerAccounts *, _QWORD, __int64 **))(v9 + 40))(a2, v7, &v21);
      if ( Error >= 0 )
        break;
LABEL_26:
      ++v7;
      if ( Error < 0 )
        goto LABEL_27;
    }
    ppwsz = 0;
    Sid = 0;
    v10 = *v21;
    *(_OWORD *)pvar = 0;
    Error = (*(__int64 (__fastcall **)(__int64 *, __int128 *, PROPVARIANT *))(v10 + 40))(
              v21,
              &PKEY_SAM_SecurityID,
              pvar);
    if ( Error >= 0 )
    {
      Error = -2147467259;
      if ( LOWORD(pvar[0]) == 65 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(Sid, &StringSid) )
        {
          Error = SHStrDupW(StringSid, &ppwsz);
          LocalFree(StringSid);
        }
        else
        {
          Error = ResultFromKnownLastError();
        }
      }
      PropVariantClear(pvar);
    }
    if ( Error < 0 )
    {
LABEL_25:
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
      goto LABEL_26;
    }
    pSid = 0;
    if ( !ConvertStringSidToSidW(ppwsz, &pSid) )
    {
LABEL_24:
      CoTaskMemFree(ppwsz);
      goto LABEL_25;
    }
    v11 = pSid;
    if ( pSid )
    {
      SidSubAuthorityCount = GetSidSubAuthorityCount(pSid);
      if ( *GetSidSubAuthority(v11, (unsigned int)*SidSubAuthorityCount - 1) - 18 <= 2 )
        goto LABEL_22;
      v11 = pSid;
    }
    if ( DPA_Search(this[3], v11, 0, _DPACompareSids, 0, 0) < 0 )
    {
      if ( (unsigned __int8)IsGuest(v21) )
      {
        v8 = pSid;
        Error = 0;
LABEL_21:
        v13 = 0;
        pSid = 0;
LABEL_23:
        LocalFree(v13);
        goto LABEL_24;
      }
      Error = CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(this + 3, pSid);
      if ( Error >= 0 )
        goto LABEL_21;
    }
LABEL_22:
    v13 = pSid;
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x180007e40  push    rbp
0x180007e42  push    rsi
0x180007e43  push    rdi
0x180007e44  push    r13
0x180007e46  push    r14
0x180007e48  mov     rbp, rsp
0x180007e4b  sub     rsp, 70h
0x180007e4f  mov     rax, [rdx]
0x180007e52  mov     r14, rdx
0x180007e55  mov     r13, rcx
0x180007e58  lea     rdx, [rbp+arg_8]
0x180007e5c  xor     esi, esi
0x180007e5e  mov     rcx, r14
0x180007e61  mov     [rbp+arg_8], esi
0x180007e64  mov     rax, [rax+20h]
0x180007e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e6d  mov     edi, eax
0x180007e6f  test    eax, eax
0x180007e71  js      loc_180008050
0x180007e77  mov     [rsp+70h+arg_0], rbx
0x180007e7f  mov     ebx, esi
0x180007e81  mov     [rsp+70h+var_8], r12
0x180007e86  mov     r12d, esi
0x180007e89  mov     [rsp+70h+var_10], r15
0x180007e8e  xchg    ax, ax
0x180007e90  cmp     ebx, [rbp+arg_8]
0x180007e93  jnb     loc_180008018
0x180007e99  mov     rax, [r14]
0x180007e9c  lea     r8, [rbp+arg_18]
0x180007ea0  mov     edx, ebx
0x180007ea2  mov     [rbp+arg_18], rsi
0x180007ea6  mov     rcx, r14
0x180007ea9  mov     rax, [rax+28h]
0x180007ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb2  mov     edi, eax
0x180007eb4  test    eax, eax
0x180007eb6  js      loc_18000800E
0x180007ebc  mov     rcx, [rbp+arg_18]
0x180007ec0  lea     r8, [rbp+pvar]
0x180007ec4  xor     eax, eax
0x180007ec6  mov     [rbp+ppwsz], rsi
0x180007eca  mov     [rbp+Sid], rax
0x180007ece  lea     rdx, PKEY_SAM_SecurityID
0x180007ed5  xorps   xmm0, xmm0
0x180007ed8  mov     rax, [rcx]
0x180007edb  movups  xmmword ptr [rbp+pvar], xmm0
0x180007edf  mov     rax, [rax+28h]
0x180007ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ee8  mov     edi, eax
0x180007eea  test    eax, eax
0x180007eec  js      short loc_180007F3D
0x180007eee  cmp     word ptr [rbp+pvar], 41h ; 'A'
0x180007ef3  mov     edi, 80004005h
0x180007ef8  jnz     short loc_180007F33
0x180007efa  mov     rcx, [rbp+Sid]; Sid
0x180007efe  lea     rdx, [rbp+StringSid]; StringSid
0x180007f02  mov     [rbp+StringSid], rsi
0x180007f06  call    cs:__imp_ConvertSidToStringSidW
0x180007f0c  test    eax, eax
0x180007f0e  jz      short loc_180007F2C
0x180007f10  mov     rcx, [rbp+StringSid]; psz
0x180007f14  lea     rdx, [rbp+ppwsz]; ppwsz
0x180007f18  call    cs:__imp_SHStrDupW
0x180007f1e  mov     rcx, [rbp+StringSid]; hMem
0x180007f22  mov     edi, eax
0x180007f24  call    cs:__imp_LocalFree
0x180007f2a  jmp     short loc_180007F33
0x180007f2c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180007f31  mov     edi, eax
0x180007f33  lea     rcx, [rbp+pvar]; pvar
0x180007f37  call    cs:__imp_PropVariantClear
0x180007f3d  test    edi, edi
0x180007f3f  js      loc_180007FFE
0x180007f45  mov     rcx, [rbp+ppwsz]; StringSid
0x180007f49  lea     rdx, [rbp+pSid]; Sid
0x180007f4d  mov     [rbp+pSid], rsi
0x180007f51  call    cs:__imp_ConvertStringSidToSidW
0x180007f57  test    eax, eax
0x180007f59  jz      loc_180007FF4
0x180007f5f  mov     rsi, [rbp+pSid]
0x180007f63  test    rsi, rsi
0x180007f66  jz      short loc_180007F8D
0x180007f68  mov     rcx, rsi; pSid
0x180007f6b  call    cs:__imp_GetSidSubAuthorityCount
0x180007f71  mov     rcx, rsi; pSid
0x180007f74  movzx   edx, byte ptr [rax]
0x180007f77  dec     edx; nSubAuthority
0x180007f79  call    cs:__imp_GetSidSubAuthority
0x180007f7f  mov     ecx, [rax]
0x180007f81  sub     ecx, 12h
0x180007f84  cmp     ecx, 2
0x180007f87  jbe     short loc_180007FE8
0x180007f89  mov     rsi, [rbp+pSid]
0x180007f8d  mov     rcx, [r13+18h]; hdpa
0x180007f91  lea     r9, ?_DPACompareSids@@YAHPEAU_SID@@0_J@Z; pfnCompare
0x180007f98  xor     eax, eax
0x180007f9a  xor     r8d, r8d; iStart
0x180007f9d  mov     [rsp+70h+options], eax; options
0x180007fa1  mov     rdx, rsi; pFind
0x180007fa4  mov     [rsp+70h+lParam], rax; lParam
0x180007fa9  call    cs:__imp_DPA_Search
0x180007faf  test    eax, eax
0x180007fb1  jns     short loc_180007FE8
0x180007fb3  mov     rcx, [rbp+arg_18]
0x180007fb7  call    _IsGuest
0x180007fbc  test    al, al
0x180007fbe  jnz     short loc_180007FD7
0x180007fc0  mov     rdx, [rbp+pSid]
0x180007fc4  lea     rcx, [r13+18h]
0x180007fc8  call    ?AppendPtr@?$CDPA_Base@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@QEAAJPEAU_SID@@PEAH@Z; CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(_SID *,int *)
0x180007fcd  mov     edi, eax
0x180007fcf  test    eax, eax
0x180007fd1  js      short loc_180007FE8
0x180007fd3  xor     esi, esi
0x180007fd5  jmp     short loc_180007FDF
0x180007fd7  mov     r12, [rbp+pSid]
0x180007fdb  xor     esi, esi
0x180007fdd  mov     edi, esi
0x180007fdf  mov     rcx, rsi
0x180007fe2  mov     [rbp+pSid], rcx
0x180007fe6  jmp     short loc_180007FEE
0x180007fe8  mov     rcx, [rbp+pSid]; hMem
0x180007fec  xor     esi, esi
0x180007fee  call    cs:__imp_LocalFree
0x180007ff4  mov     rcx, [rbp+ppwsz]; pv
0x180007ff8  call    cs:__imp_CoTaskMemFree
0x180007ffe  mov     rcx, [rbp+arg_18]
0x180008002  mov     rax, [rcx]
0x180008005  mov     rax, [rax+10h]
0x180008009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000800e  inc     ebx
0x180008010  test    edi, edi
0x180008012  jns     loc_180007E90
0x180008018  mov     r15, [rsp+70h+var_10]
0x18000801d  test    r12, r12
0x180008020  jz      short loc_180008041
0x180008022  lea     rcx, [r13+18h]
0x180008026  mov     rdx, r12
0x180008029  call    ?AppendPtr@?$CDPA_Base@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@QEAAJPEAU_SID@@PEAH@Z; CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(_SID *,int *)
0x18000802e  mov     ebx, eax
0x180008030  test    eax, eax
0x180008032  jns     short loc_180008043
0x180008034  mov     rcx, r12; hMem
0x180008037  call    cs:__imp_LocalFree
0x18000803d  mov     eax, ebx
0x18000803f  jmp     short loc_180008043
0x180008041  mov     eax, edi
0x180008043  mov     rbx, [rsp+70h+arg_0]
0x18000804b  mov     r12, [rsp+70h+var_8]
0x180008050  add     rsp, 70h
0x180008054  pop     r14
0x180008056  pop     r13
0x180008058  pop     rdi
0x180008059  pop     rsi
0x18000805a  pop     rbp
0x18000805b  retn
```
