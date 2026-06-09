# LRPC_SCONTEXT::LookupUser(_SID *,ushort * *)

- ea: `0x180085754`
- end: `0x18008596d`
- name: `?LookupUser@LRPC_SCONTEXT@@CAJPEAU_SID@@PEAPEAG@Z`
- size: `537`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180085374`

## callees

- `0x180021e70`
- `0x180022870`
- `0x1800283bc`
- `0x180085754`
- `0x180085974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085911`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800857f9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800857f9`

## pseudocode

```c
__int64 __fastcall LRPC_SCONTEXT::LookupUser(PSID Sid, unsigned __int16 **a2)
{
  void *v4; // rdi
  DWORD v5; // r15d
  void *v6; // rsi
  DWORD v7; // ebx
  DWORD v8; // r14d
  int v9; // ebx
  DWORD v11; // eax
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-20h] BYREF
  _DWORD v13[6]; // [rsp+38h] [rbp-18h] BYREF
  DWORD cchName; // [rsp+A0h] [rbp+50h] BYREF
  DWORD cchReferencedDomainName; // [rsp+A8h] [rbp+58h] BYREF

  cchReferencedDomainName = 128;
  cchName = 256;
  peUse = 0;
  v4 = AllocWrapper(0x202u);
  if ( !v4 )
    return 14;
  v5 = cchName + 1 + cchReferencedDomainName;
  v6 = AllocWrapper(saturated_mul(v5 + 1, 2u));
  if ( !v6 )
  {
    v9 = 14;
    goto LABEL_21;
  }
  v7 = cchReferencedDomainName;
  v8 = cchName;
  while ( !LookupAccountSidLocalW(Sid, (LPWSTR)v4, &cchName, (LPWSTR)v6, &cchReferencedDomainName, &peUse) )
  {
    if ( cchName <= v8 )
    {
      v11 = cchReferencedDomainName;
      if ( cchReferencedDomainName <= v7 )
      {
        v13[0] = 3;
        v13[2] = GetLastError();
        v9 = 1332;
        RpcpErrorAddRecord(2u, 1332, 0x4ECu, 1, (struct tagParam *)v13);
        goto LABEL_21;
      }
    }
    else
    {
      v8 = cchName;
      FreeWrapper(v4);
      v4 = AllocWrapper(saturated_mul(cchName, 2u));
      if ( !v4 )
      {
        v9 = 14;
        goto LABEL_22;
      }
      v11 = cchReferencedDomainName;
    }
    if ( v11 > v7 )
    {
      v7 = v11;
      FreeWrapper(v6);
      v5 = cchName + 1 + cchReferencedDomainName;
      v6 = AllocWrapper(saturated_mul(v5, 2u));
      if ( !v6 )
      {
        v9 = 14;
        goto LABEL_21;
      }
    }
  }
  if ( (int)RtlStringCchCatW((unsigned __int16 *)v6, v5, L"\\") < 0
    || (v9 = RtlStringCchCatW((unsigned __int16 *)v6, v5, (const unsigned __int16 *)v4), v9 < 0) )
  {
    v9 = 87;
LABEL_21:
    FreeWrapper(v4);
LABEL_22:
    if ( v6 )
      FreeWrapper(v6);
    return (unsigned int)v9;
  }
  FreeWrapper(v4);
  *a2 = (unsigned __int16 *)v6;
  if ( v9 )
    goto LABEL_21;
  return 0;
}

```

## disassembly

```asm
0x180085754  mov     [rsp-38h+arg_0], rbx
0x180085759  push    rbp
0x18008575a  push    rsi
0x18008575b  push    rdi
0x18008575c  push    r12
0x18008575e  push    r13
0x180085760  push    r14
0x180085762  push    r15
0x180085764  mov     rbp, rsp
0x180085767  sub     rsp, 50h
0x18008576b  mov     r13, rcx
0x18008576e  mov     [rbp+arg_18], 80h
0x180085775  mov     ecx, 202h; dwBytes
0x18008577a  mov     [rbp+cchName], 100h
0x180085781  mov     r12, rdx
0x180085784  mov     [rbp+var_20], 0
0x18008578b  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180085790  mov     rdi, rax
0x180085793  test    rax, rax
0x180085796  jz      loc_1800858F5
0x18008579c  mov     eax, [rbp+cchName]
0x18008579f  mov     r15d, [rbp+arg_18]
0x1800857a3  inc     eax
0x1800857a5  add     r15d, eax
0x1800857a8  mov     eax, 2
0x1800857ad  lea     ecx, [r15+1]
0x1800857b1  mul     rcx
0x1800857b4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800857bb  cmovb   rax, rcx
0x1800857bf  mov     rcx, rax; dwBytes
0x1800857c2  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800857c7  mov     rsi, rax
0x1800857ca  test    rax, rax
0x1800857cd  jz      loc_1800858FC
0x1800857d3  mov     ebx, [rbp+arg_18]
0x1800857d6  mov     r14d, [rbp+cchName]
0x1800857da  lea     rax, [rbp+var_20]
0x1800857de  mov     r9, rsi; ReferencedDomainName
0x1800857e1  mov     [rsp+50h+peUse], rax; peUse
0x1800857e6  lea     r8, [rbp+cchName]; cchName
0x1800857ea  lea     rax, [rbp+arg_18]
0x1800857ee  mov     rdx, rdi; Name
0x1800857f1  mov     rcx, r13; Sid
0x1800857f4  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800857f9  call    cs:__imp_LookupAccountSidLocalW
0x1800857ff  test    eax, eax
0x180085801  jz      short loc_180085865
0x180085803  lea     r8, asc_1800E2D40; "\\"
0x18008580a  mov     edx, r15d; unsigned __int64
0x18008580d  mov     rcx, rsi; unsigned __int16 *
0x180085810  mov     ebx, r15d
0x180085813  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180085818  test    eax, eax
0x18008581a  js      loc_180085947
0x180085820  mov     r8, rdi; unsigned __int16 *
0x180085823  mov     edx, ebx; unsigned __int64
0x180085825  mov     rcx, rsi; unsigned __int16 *
0x180085828  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008582d  mov     ebx, eax
0x18008582f  test    eax, eax
0x180085831  js      loc_180085947
0x180085837  mov     rcx, rdi; lpMem
0x18008583a  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18008583f  mov     [r12], rsi
0x180085843  test    ebx, ebx
0x180085845  jnz     loc_18008594C
0x18008584b  xor     eax, eax
0x18008584d  mov     rbx, [rsp+50h+arg_0]
0x180085855  add     rsp, 50h
0x180085859  pop     r15
0x18008585b  pop     r14
0x18008585d  pop     r13
0x18008585f  pop     r12
0x180085861  pop     rdi
0x180085862  pop     rsi
0x180085863  pop     rbp
0x180085864  retn
0x180085865  cmp     [rbp+cchName], r14d
0x180085869  jbe     loc_180085903
0x18008586f  mov     r14d, [rbp+cchName]
0x180085873  mov     rcx, rdi; lpMem
0x180085876  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18008587b  mov     ecx, [rbp+cchName]
0x18008587e  mov     eax, 2
0x180085883  mul     rcx
0x180085886  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008588d  cmovb   rax, rcx
0x180085891  mov     rcx, rax; dwBytes
0x180085894  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180085899  mov     rdi, rax
0x18008589c  test    rax, rax
0x18008589f  jz      loc_180085940
0x1800858a5  mov     eax, [rbp+arg_18]
0x1800858a8  cmp     eax, ebx
0x1800858aa  jbe     loc_1800857DA
0x1800858b0  mov     rcx, rsi; lpMem
0x1800858b3  mov     ebx, eax
0x1800858b5  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800858ba  mov     eax, [rbp+cchName]
0x1800858bd  mov     r15d, [rbp+arg_18]
0x1800858c1  inc     eax
0x1800858c3  add     r15d, eax
0x1800858c6  mov     eax, 2
0x1800858cb  mov     ecx, r15d
0x1800858ce  mul     rcx
0x1800858d1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800858d8  cmovb   rax, rcx
0x1800858dc  mov     rcx, rax; dwBytes
0x1800858df  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800858e4  mov     rsi, rax
0x1800858e7  test    rax, rax
0x1800858ea  jnz     loc_1800857DA
0x1800858f0  lea     ebx, [rax+0Eh]
0x1800858f3  jmp     short loc_18008594C
0x1800858f5  mov     ebx, 0Eh
0x1800858fa  jmp     short loc_180085966
0x1800858fc  mov     ebx, 0Eh
0x180085901  jmp     short loc_180085951
0x180085903  mov     eax, [rbp+arg_18]
0x180085906  cmp     eax, ebx
0x180085908  ja      short loc_1800858A8
0x18008590a  mov     [rbp+var_18], 3
0x180085911  call    cs:__imp_GetLastError
0x180085917  mov     r8d, 4ECh; unsigned __int16
0x18008591d  mov     r9d, 1; int
0x180085923  mov     [rbp+var_10], eax
0x180085926  lea     rax, [rbp+var_18]
0x18008592a  mov     [rsp+50h+cchReferencedDomainName], rax; struct tagParam *
0x18008592f  lea     ebx, [r8+48h]
0x180085933  mov     edx, ebx; int
0x180085935  lea     ecx, [r9+1]; unsigned int
0x180085939  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18008593e  jmp     short loc_18008594C
0x180085940  mov     ebx, 0Eh
0x180085945  jmp     short loc_180085959
0x180085947  mov     ebx, 57h ; 'W'
0x18008594c  test    rdi, rdi
0x18008594f  jz      short loc_180085959
0x180085951  mov     rcx, rdi; lpMem
0x180085954  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180085959  test    rsi, rsi
0x18008595c  jz      short loc_180085966
0x18008595e  mov     rcx, rsi; lpMem
0x180085961  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180085966  mov     eax, ebx
0x180085968  jmp     loc_18008584D
```
