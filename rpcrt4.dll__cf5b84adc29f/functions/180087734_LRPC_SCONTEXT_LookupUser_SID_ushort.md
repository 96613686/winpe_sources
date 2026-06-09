# LRPC_SCONTEXT::LookupUser(_SID *,ushort * *)

- ea: `0x180087734`
- end: `0x18008795a`
- name: `?LookupUser@LRPC_SCONTEXT@@CAJPEAU_SID@@PEAPEAG@Z`
- size: `550`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180087334`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800295d8`
- `0x180087734`
- `0x180087960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800878f8`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800877d9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800877d9`

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
0x180087734  mov     [rsp-38h+arg_0], rbx
0x180087739  push    rbp
0x18008773a  push    rsi
0x18008773b  push    rdi
0x18008773c  push    r12
0x18008773e  push    r13
0x180087740  push    r14
0x180087742  push    r15
0x180087744  mov     rbp, rsp
0x180087747  sub     rsp, 50h
0x18008774b  mov     r13, rcx
0x18008774e  mov     [rbp+arg_18], 80h
0x180087755  mov     ecx, 202h; dwBytes
0x18008775a  mov     [rbp+cchName], 100h
0x180087761  mov     r12, rdx
0x180087764  mov     [rbp+var_20], 0
0x18008776b  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180087770  mov     rdi, rax
0x180087773  test    rax, rax
0x180087776  jz      loc_1800878DC
0x18008777c  mov     eax, [rbp+cchName]
0x18008777f  mov     r15d, [rbp+arg_18]
0x180087783  inc     eax
0x180087785  add     r15d, eax
0x180087788  mov     eax, 2
0x18008778d  lea     ecx, [r15+1]
0x180087791  mul     rcx
0x180087794  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008779b  cmovb   rax, rcx
0x18008779f  mov     rcx, rax; dwBytes
0x1800877a2  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800877a7  mov     rsi, rax
0x1800877aa  test    rax, rax
0x1800877ad  jz      loc_1800878E3
0x1800877b3  mov     ebx, [rbp+arg_18]
0x1800877b6  mov     r14d, [rbp+cchName]
0x1800877ba  lea     rax, [rbp+var_20]
0x1800877be  mov     r9, rsi; ReferencedDomainName
0x1800877c1  mov     [rsp+50h+peUse], rax; peUse
0x1800877c6  lea     r8, [rbp+cchName]; cchName
0x1800877ca  lea     rax, [rbp+arg_18]
0x1800877ce  mov     rdx, rdi; Name
0x1800877d1  mov     rcx, r13; Sid
0x1800877d4  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800877d9  call    cs:__imp_LookupAccountSidLocalW
0x1800877e0  nop     dword ptr [rax+rax+00h]
0x1800877e5  test    eax, eax
0x1800877e7  jz      short loc_18008784C
0x1800877e9  lea     r8, asc_1800E7D08; "\\"
0x1800877f0  mov     edx, r15d; unsigned __int64
0x1800877f3  mov     rcx, rsi; unsigned __int16 *
0x1800877f6  mov     ebx, r15d
0x1800877f9  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800877fe  test    eax, eax
0x180087800  js      loc_180087934
0x180087806  mov     r8, rdi; unsigned __int16 *
0x180087809  mov     edx, ebx; unsigned __int64
0x18008780b  mov     rcx, rsi; unsigned __int16 *
0x18008780e  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180087813  mov     ebx, eax
0x180087815  test    eax, eax
0x180087817  js      loc_180087934
0x18008781d  mov     rcx, rdi; lpMem
0x180087820  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180087825  mov     [r12], rsi
0x180087829  test    ebx, ebx
0x18008782b  jnz     loc_180087939
0x180087831  xor     eax, eax
0x180087833  mov     rbx, [rsp+50h+arg_0]
0x18008783b  add     rsp, 50h
0x18008783f  pop     r15
0x180087841  pop     r14
0x180087843  pop     r13
0x180087845  pop     r12
0x180087847  pop     rdi
0x180087848  pop     rsi
0x180087849  pop     rbp
0x18008784a  retn
0x18008784c  cmp     [rbp+cchName], r14d
0x180087850  jbe     loc_1800878EA
0x180087856  mov     r14d, [rbp+cchName]
0x18008785a  mov     rcx, rdi; lpMem
0x18008785d  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180087862  mov     ecx, [rbp+cchName]
0x180087865  mov     eax, 2
0x18008786a  mul     rcx
0x18008786d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180087874  cmovb   rax, rcx
0x180087878  mov     rcx, rax; dwBytes
0x18008787b  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180087880  mov     rdi, rax
0x180087883  test    rax, rax
0x180087886  jz      loc_18008792D
0x18008788c  mov     eax, [rbp+arg_18]
0x18008788f  cmp     eax, ebx
0x180087891  jbe     loc_1800877BA
0x180087897  mov     rcx, rsi; lpMem
0x18008789a  mov     ebx, eax
0x18008789c  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800878a1  mov     eax, [rbp+cchName]
0x1800878a4  mov     r15d, [rbp+arg_18]
0x1800878a8  inc     eax
0x1800878aa  add     r15d, eax
0x1800878ad  mov     eax, 2
0x1800878b2  mov     ecx, r15d
0x1800878b5  mul     rcx
0x1800878b8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800878bf  cmovb   rax, rcx
0x1800878c3  mov     rcx, rax; dwBytes
0x1800878c6  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800878cb  mov     rsi, rax
0x1800878ce  test    rax, rax
0x1800878d1  jnz     loc_1800877BA
0x1800878d7  lea     ebx, [rax+0Eh]
0x1800878da  jmp     short loc_180087939
0x1800878dc  mov     ebx, 0Eh
0x1800878e1  jmp     short loc_180087953
0x1800878e3  mov     ebx, 0Eh
0x1800878e8  jmp     short loc_18008793E
0x1800878ea  mov     eax, [rbp+arg_18]
0x1800878ed  cmp     eax, ebx
0x1800878ef  ja      short loc_18008788F
0x1800878f1  mov     [rbp+var_18], 3
0x1800878f8  call    cs:__imp_GetLastError
0x1800878ff  nop     dword ptr [rax+rax+00h]
0x180087904  mov     r8d, 4ECh; unsigned __int16
0x18008790a  mov     r9d, 1; int
0x180087910  mov     [rbp+var_10], eax
0x180087913  lea     rax, [rbp+var_18]
0x180087917  mov     [rsp+50h+cchReferencedDomainName], rax; struct tagParam *
0x18008791c  lea     ebx, [r8+48h]
0x180087920  mov     edx, ebx; int
0x180087922  lea     ecx, [r9+1]; unsigned int
0x180087926  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18008792b  jmp     short loc_180087939
0x18008792d  mov     ebx, 0Eh
0x180087932  jmp     short loc_180087946
0x180087934  mov     ebx, 57h ; 'W'
0x180087939  test    rdi, rdi
0x18008793c  jz      short loc_180087946
0x18008793e  mov     rcx, rdi; lpMem
0x180087941  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180087946  test    rsi, rsi
0x180087949  jz      short loc_180087953
0x18008794b  mov     rcx, rsi; lpMem
0x18008794e  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180087953  mov     eax, ebx
0x180087955  jmp     loc_180087833
```
