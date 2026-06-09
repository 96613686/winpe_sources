# SampValidateNewAliasMember(_SAMP_OBJECT *,void *,_DSNAME *)

- ea: `0x180035610`
- end: `0x180035911`
- name: `?SampValidateNewAliasMember@@YAJPEAU_SAMP_OBJECT@@PEAXPEAU_DSNAME@@@Z`
- size: `769`
- prototype: `int(struct _SAMP_OBJECT *, void *, struct _DSNAME *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180034520`

## callees

- `0x1800022a0`
- `0x180005a80`
- `0x180011810`
- `0x180012a28`
- `0x180021460`
- `0x180021bec`
- `0x180027e24`
- `0x180035610`
- `0x180062e58`
- `0x1800af690`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18003564e`
- `ntdll!RtlValidSid` at `0x18003564e`
- `ntdll!RtlEqualSid` at `0x1800356a8`
- `ntdll!RtlEqualSid` at `0x18003576e`
- `ntdll!RtlEqualSid` at `0x1800356a8`
- `ntdll!RtlEqualSid` at `0x18003576e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035873`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035873`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtEnforceCrossDomainGroupMembershipChecks` at `0x180035727`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtEnforceCrossDomainGroupMembershipChecks` at `0x180035727`

## pseudocode

```c
__int64 __fastcall SampValidateNewAliasMember(struct _SAMP_OBJECT *a1, void *a2, struct _DSNAME *a3)
{
  void *v6; // r12
  int v7; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int8 v10; // al
  unsigned int v11; // r15d
  unsigned __int8 v12; // si
  PUNICODE_STRING v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  char v17; // [rsp+40h] [rbp-20h] BYREF
  __int64 v18; // [rsp+41h] [rbp-1Fh] BYREF
  ULONG v19; // [rsp+48h] [rbp-18h] BYREF
  PSID Sid2; // [rsp+50h] [rbp-10h] BYREF
  __int64 v21; // [rsp+A8h] [rbp+48h] BYREF

  Sid2 = 0;
  v19 = 0;
  *(_DWORD *)((char *)&v18 + 3) = 0;
  if ( !a2 || !RtlValidSid(a2) )
  {
    v13 = WPP_GLOBAL_Control;
    v7 = -1073741704;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)v7;
    v14 = 55;
    v15 = 3221225592LL;
LABEL_46:
    WPP_SF_Dd(v13[3].Buffer, v14, &WPP_799c13f926ef3db95a69a5604490dfde_Traceguids, v15, v7);
    return (unsigned int)v7;
  }
  if ( (unsigned int)(*((_DWORD *)a1 + 64) - 4) > 1 )
  {
    v6 = (void *)*((_QWORD *)SampDefinedDomains + 170 * *((unsigned int *)a1 + 50) + 1);
    v7 = SampSplitSid(a2, &Sid2, &v19);
    if ( v7 < 0 )
      goto LABEL_37;
    if ( !RtlEqualSid(v6, Sid2) )
    {
      LOBYTE(v21) = 0;
      v17 = 0;
      v7 = SampExamineSid(a2, (__int64)&v21, (__int64)&v18, (__int64)&v17);
      if ( v7 >= 0 )
      {
        if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
        {
          v8 = SampShouldCallNtdsaApiSet();
          v7 = v8;
          if ( v8 != -1073741637 )
          {
            if ( v8 >= 0 )
              v7 = NtdsaExtEnforceCrossDomainGroupMembershipChecks(a1, a2, a3);
            goto LABEL_37;
          }
          goto LABEL_12;
        }
        if ( !(_BYTE)v21 )
        {
LABEL_12:
          v7 = 0;
          goto LABEL_37;
        }
        v9 = 0;
        if ( SampDefinedDomainsCount )
        {
          do
          {
            if ( RtlEqualSid(*((PSID *)SampDefinedDomains + 170 * v9 + 1), Sid2) )
              break;
            ++v9;
          }
          while ( v9 < SampDefinedDomainsCount );
          if ( v9 < SampDefinedDomainsCount )
          {
            v10 = SampTransactionWithinDomainFn();
            v11 = SampTransactionDomainIndexGlobal;
            v12 = v10;
            SampSetTransactionWithinDomain(0);
            SampSetTransactionDomain(v9);
            v7 = SampLookupAccountName(v9, v19, 0, (enum _SAMP_OBJECT_TYPE *)((char *)&v18 + 3));
            if ( v7 >= 0 )
            {
              if ( *(_DWORD *)((char *)&v18 + 3) == 2
                || *(_DWORD *)((char *)&v18 + 3) == 3
                || *(_DWORD *)((char *)&v18 + 3) == 4 )
              {
                v7 = 0;
              }
              else if ( *(_DWORD *)((char *)&v18 + 3) == 5 )
              {
                v7 = -1073741446;
              }
              else
              {
                v7 = -1073741445;
              }
            }
            goto LABEL_35;
          }
        }
LABEL_25:
        v7 = -1073741446;
      }
LABEL_37:
      if ( Sid2 )
        LocalFree(Sid2);
      v13 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)v7;
      v14 = 57;
      v15 = (unsigned int)v7;
      goto LABEL_46;
    }
    v7 = SampLookupAccountName(*((_DWORD *)a1 + 50), v19, 0, (enum _SAMP_OBJECT_TYPE *)((char *)&v18 + 3));
    if ( v7 < 0 )
      goto LABEL_37;
    if ( *(_DWORD *)((char *)&v18 + 3) != 2 )
    {
      if ( *(_DWORD *)((char *)&v18 + 3) != 3 )
      {
        if ( *(_DWORD *)((char *)&v18 + 3) == 4 )
          goto LABEL_12;
        if ( *(_DWORD *)((char *)&v18 + 3) == 5 )
          goto LABEL_25;
LABEL_31:
        v7 = -1073741445;
        goto LABEL_37;
      }
      if ( (*((_BYTE *)a1 + 192) & 2) == 0 )
        goto LABEL_31;
    }
    v7 = 0;
    if ( (*((_BYTE *)a1 + 192) & 2) == 0 )
      goto LABEL_37;
    v11 = 0;
    v12 = 0;
    v7 = SampEnforceSameDomainGroupMembershipChecks(a1, v19);
LABEL_35:
    if ( v12 )
    {
      SampSetTransactionWithinDomain(0);
      SampSetTransactionDomain(v11);
    }
    goto LABEL_37;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 56, &WPP_799c13f926ef3db95a69a5604490dfde_Traceguids, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180035610  mov     [rsp-28h+arg_0], rbx
0x180035615  push    rbp
0x180035616  push    rsi
0x180035617  push    rdi
0x180035618  push    r12
0x18003561a  push    r15
0x18003561c  mov     rbp, rsp
0x18003561f  sub     rsp, 60h
0x180035623  mov     [rbp+Sid2], 0
0x18003562b  mov     r15, r8
0x18003562e  mov     [rbp+var_18], 0
0x180035635  mov     rsi, rdx
0x180035638  mov     dword ptr [rbp+var_20+4], 0
0x18003563f  mov     rdi, rcx
0x180035642  test    rdx, rdx
0x180035645  jz      loc_1800358C7
0x18003564b  mov     rcx, rdx; Sid
0x18003564e  call    cs:__imp_RtlValidSid
0x180035654  test    al, al
0x180035656  jz      loc_1800358C7
0x18003565c  mov     eax, [rdi+100h]
0x180035662  sub     eax, 4
0x180035665  cmp     eax, 1
0x180035668  jbe     loc_180035893
0x18003566e  mov     eax, [rdi+0C8h]
0x180035674  lea     r8, [rbp+var_18]
0x180035678  imul    rcx, rax, 550h
0x18003567f  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180035686  lea     rdx, [rbp+Sid2]
0x18003568a  mov     r12, [rcx+rax+8]
0x18003568f  mov     rcx, rsi; Src
0x180035692  call    SampSplitSid
0x180035697  mov     ebx, eax
0x180035699  test    eax, eax
0x18003569b  js      loc_180035868
0x1800356a1  mov     rdx, [rbp+Sid2]; Sid2
0x1800356a5  mov     rcx, r12; Sid1
0x1800356a8  call    cs:__imp_RtlEqualSid
0x1800356ae  test    al, al
0x1800356b0  jnz     loc_1800357F0
0x1800356b6  mov     edx, [rdi+0C0h]
0x1800356bc  lea     r9, [rbp+arg_8]
0x1800356c0  mov     byte ptr [rbp+arg_18], al
0x1800356c3  lea     r8, [rbp+var_20+2]
0x1800356c7  mov     byte ptr [rbp+var_20], al
0x1800356ca  mov     rcx, rsi; Src
0x1800356cd  mov     [rbp+arg_8], al
0x1800356d0  lea     rax, [rbp+var_20]
0x1800356d4  mov     [rsp+60h+var_30], rax; __int64
0x1800356d9  lea     rax, [rbp+var_20+1]
0x1800356dd  mov     [rsp+60h+var_38], rax; __int64
0x1800356e2  lea     rax, [rbp+arg_18]
0x1800356e6  shr     edx, 1
0x1800356e8  and     dl, 1
0x1800356eb  mov     [rsp+60h+var_40], rax; __int64
0x1800356f0  call    SampExamineSid
0x1800356f5  mov     ebx, eax
0x1800356f7  test    eax, eax
0x1800356f9  js      loc_180035868
0x1800356ff  test    byte ptr [rdi+0C0h], 2
0x180035706  jz      short loc_180035734
0x180035708  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18003570d  mov     ebx, eax
0x18003570f  cmp     eax, 0C00000BBh
0x180035714  jz      short loc_180035740
0x180035716  test    eax, eax
0x180035718  js      loc_180035868
0x18003571e  mov     r8, r15
0x180035721  mov     rdx, rsi
0x180035724  mov     rcx, rdi
0x180035727  call    cs:__imp_NtdsaExtEnforceCrossDomainGroupMembershipChecks
0x18003572d  mov     ebx, eax
0x18003572f  jmp     loc_180035868
0x180035734  cmp     [rbp+arg_8], 0
0x180035738  jnz     short loc_180035747
0x18003573a  cmp     byte ptr [rbp+arg_18], 0
0x18003573e  jnz     short loc_180035747
0x180035740  xor     ebx, ebx
0x180035742  jmp     loc_180035868
0x180035747  xor     ebx, ebx
0x180035749  cmp     cs:?SampDefinedDomainsCount@@3KA, ebx; ulong SampDefinedDomainsCount
0x18003574f  jbe     loc_1800357E9
0x180035755  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18003575c  mov     rdx, [rbp+Sid2]; Sid2
0x180035760  mov     eax, ebx
0x180035762  imul    r8, rax, 550h
0x180035769  mov     rcx, [r8+rcx+8]; Sid1
0x18003576e  call    cs:__imp_RtlEqualSid
0x180035774  mov     ecx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x18003577a  test    al, al
0x18003577c  jnz     short loc_180035784
0x18003577e  inc     ebx
0x180035780  cmp     ebx, ecx
0x180035782  jb      short loc_180035755
0x180035784  cmp     ebx, ecx
0x180035786  jnb     short loc_1800357E9
0x180035788  call    ?SampTransactionWithinDomainFn@@YAEXZ; SampTransactionWithinDomainFn(void)
0x18003578d  mov     r15d, cs:?SampTransactionDomainIndexGlobal@@3KA; ulong SampTransactionDomainIndexGlobal
0x180035794  xor     ecx, ecx
0x180035796  mov     sil, al
0x180035799  call    SampSetTransactionWithinDomain
0x18003579e  mov     ecx, ebx
0x1800357a0  call    SampSetTransactionDomain
0x1800357a5  mov     edx, [rbp+var_18]; unsigned int
0x1800357a8  lea     r9, [rbp+var_20+4]; enum _SAMP_OBJECT_TYPE *
0x1800357ac  xor     r8d, r8d; struct _UNICODE_STRING *
0x1800357af  mov     ecx, ebx; unsigned int
0x1800357b1  call    ?SampLookupAccountName@@YAJKKPEAU_UNICODE_STRING@@PEAW4_SAMP_OBJECT_TYPE@@@Z; SampLookupAccountName(ulong,ulong,_UNICODE_STRING *,_SAMP_OBJECT_TYPE *)
0x1800357b6  mov     ebx, eax
0x1800357b8  test    eax, eax
0x1800357ba  js      loc_180035854
0x1800357c0  mov     ecx, dword ptr [rbp+var_20+4]
0x1800357c3  sub     ecx, 2
0x1800357c6  jz      short loc_1800357E5
0x1800357c8  sub     ecx, 1
0x1800357cb  jz      short loc_1800357E5
0x1800357cd  sub     ecx, 1
0x1800357d0  jz      short loc_1800357E5
0x1800357d2  cmp     ecx, 1
0x1800357d5  jz      short loc_1800357DE
0x1800357d7  mov     ebx, 0C000017Bh
0x1800357dc  jmp     short loc_180035854
0x1800357de  mov     ebx, 0C000017Ah
0x1800357e3  jmp     short loc_180035854
0x1800357e5  xor     ebx, ebx
0x1800357e7  jmp     short loc_180035854
0x1800357e9  mov     ebx, 0C000017Ah
0x1800357ee  jmp     short loc_180035868
0x1800357f0  mov     edx, [rbp+var_18]; unsigned int
0x1800357f3  lea     r9, [rbp+var_20+4]; enum _SAMP_OBJECT_TYPE *
0x1800357f7  mov     ecx, [rdi+0C8h]; unsigned int
0x1800357fd  xor     r8d, r8d; struct _UNICODE_STRING *
0x180035800  call    ?SampLookupAccountName@@YAJKKPEAU_UNICODE_STRING@@PEAW4_SAMP_OBJECT_TYPE@@@Z; SampLookupAccountName(ulong,ulong,_UNICODE_STRING *,_SAMP_OBJECT_TYPE *)
0x180035805  mov     ebx, eax
0x180035807  test    eax, eax
0x180035809  js      short loc_180035868
0x18003580b  mov     ecx, dword ptr [rbp+var_20+4]
0x18003580e  sub     ecx, 2
0x180035811  jz      short loc_180035836
0x180035813  sub     ecx, 1
0x180035816  jz      short loc_18003582D
0x180035818  sub     ecx, 1
0x18003581b  jz      loc_180035740
0x180035821  cmp     ecx, 1
0x180035824  jz      short loc_1800357E9
0x180035826  mov     ebx, 0C000017Bh
0x18003582b  jmp     short loc_180035868
0x18003582d  test    byte ptr [rdi+0C0h], 2
0x180035834  jz      short loc_180035826
0x180035836  xor     ebx, ebx
0x180035838  test    byte ptr [rdi+0C0h], 2
0x18003583f  jz      short loc_180035868
0x180035841  mov     edx, [rbp+var_18]; unsigned int
0x180035844  xor     r15d, r15d
0x180035847  xor     sil, sil
0x18003584a  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18003584d  call    ?SampEnforceSameDomainGroupMembershipChecks@@YAJPEAU_SAMP_OBJECT@@K@Z; SampEnforceSameDomainGroupMembershipChecks(_SAMP_OBJECT *,ulong)
0x180035852  mov     ebx, eax
0x180035854  test    sil, sil
0x180035857  jz      short loc_180035868
0x180035859  xor     ecx, ecx
0x18003585b  call    SampSetTransactionWithinDomain
0x180035860  mov     ecx, r15d
0x180035863  call    SampSetTransactionDomain
0x180035868  cmp     [rbp+Sid2], 0
0x18003586d  jz      short loc_180035879
0x18003586f  mov     rcx, [rbp+Sid2]; hMem
0x180035873  call    cs:__imp_LocalFree
0x180035879  mov     rcx, cs:WPP_GLOBAL_Control
0x180035880  test    dword ptr [rcx+44h], 20000h
0x180035887  jz      short loc_1800358FB
0x180035889  mov     edx, 39h ; '9'
0x18003588e  mov     r9d, ebx
0x180035891  jmp     short loc_1800358E7
0x180035893  mov     rcx, cs:WPP_GLOBAL_Control
0x18003589a  test    dword ptr [rcx+44h], 20000h
0x1800358a1  jz      short loc_1800358C3
0x1800358a3  mov     rcx, [rcx+38h]
0x1800358a7  lea     r8, WPP_799c13f926ef3db95a69a5604490dfde_Traceguids
0x1800358ae  mov     edx, 38h ; '8'
0x1800358b3  mov     dword ptr [rsp+60h+var_40], 0
0x1800358bb  xor     r9d, r9d
0x1800358be  call    WPP_SF_Dd
0x1800358c3  xor     eax, eax
0x1800358c5  jmp     short loc_1800358FD
0x1800358c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358ce  mov     ebx, 0C0000078h
0x1800358d3  test    dword ptr [rcx+44h], 20000h
0x1800358da  jz      short loc_1800358FB
0x1800358dc  mov     edx, 37h ; '7'
0x1800358e1  mov     r9d, 0C0000078h
0x1800358e7  mov     rcx, [rcx+38h]
0x1800358eb  lea     r8, WPP_799c13f926ef3db95a69a5604490dfde_Traceguids
0x1800358f2  mov     dword ptr [rsp+60h+var_40], ebx
0x1800358f6  call    WPP_SF_Dd
0x1800358fb  mov     eax, ebx
0x1800358fd  mov     rbx, [rsp+60h+arg_0]
0x180035905  add     rsp, 60h
0x180035909  pop     r15
0x18003590b  pop     r12
0x18003590d  pop     rdi
0x18003590e  pop     rsi
0x18003590f  pop     rbp
0x180035910  retn
```
