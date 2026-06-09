# ldap_rename_ext_sA

- ea: `0x180047f80`
- end: `0x1800481fc`
- name: `ldap_rename_ext_sA`
- size: `636`
- prototype: `ULONG __cdecl(LDAP *ld, const PSTR dn, const PSTR NewRDN, const PSTR NewParent, INT DeleteOldRdn, PLDAPControlA *ServerControls, PLDAPControlA *ClientControls)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000b440`
- `0x18000bf40`
- `0x18000cda0`
- `0x18001611c`
- `0x180016360`
- `0x18001ffa0`
- `0x180046f48`
- `0x180047f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048179`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048179`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800481c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800481db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800481c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800481db`

## pseudocode

```c
ULONG __cdecl ldap_rename_ext_sA(
        LDAP *ld,
        const PSTR dn,
        const PSTR NewRDN,
        const PSTR NewParent,
        INT DeleteOldRdn,
        PLDAPControlA *ServerControls,
        PLDAPControlA *ClientControls)
{
  unsigned __int16 *v7; // r14
  _DWORD *ConnectionPointer; // rbx
  __int64 v12; // r8
  unsigned int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // edi
  unsigned int v17; // eax
  unsigned int v18; // r15d
  __int64 v19; // r8
  struct _RTL_CRITICAL_SECTION *v20; // rcx
  unsigned int v21; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v22; // [rsp+58h] [rbp-28h]
  unsigned __int16 *v23; // [rsp+60h] [rbp-20h]
  unsigned __int16 *v24; // [rsp+68h] [rbp-18h]
  LDAPMessage *res; // [rsp+70h] [rbp-10h] BYREF

  v23 = 0;
  v7 = 0;
  v22 = 0;
  v24 = 0;
  v21 = 0;
  res = 0;
  ConnectionPointer = (_DWORD *)GetConnectionPointer(ld, dn, NewRDN);
  if ( !ConnectionPointer )
  {
    SetConnectionError(0, 0x59u, v12);
    return 89;
  }
  v14 = ToUnicodeWithAlloc(dn, 1);
  v16 = v14;
  if ( v14 )
    goto LABEL_8;
  v14 = ToUnicodeWithAlloc(NewRDN, 1);
  v16 = v14;
  if ( v14 )
    goto LABEL_8;
  if ( !NewParent )
  {
LABEL_10:
    v17 = LdapRename(
            (struct ldap_connection *)ConnectionPointer,
            v23,
            v22,
            v7,
            DeleteOldRdn,
            0,
            1u,
            (struct ldapcontrolW **)ServerControls,
            (struct ldapcontrolW **)ClientControls,
            &v21);
    v18 = v21;
    v16 = v17;
    if ( v21 != -1 )
    {
      v16 = ldap_result_with_error((struct ldap_connection *)ConnectionPointer, v21, 1u, 0, &res, 0);
      if ( res )
      {
        v16 = ldap_result2error(*((LDAP **)ConnectionPointer + 56), res, 1u);
      }
      else
      {
        LdapAbandon((__int64)ConnectionPointer, v18, 1);
        SetConnectionError((__int64)ConnectionPointer, v16, v19);
      }
    }
    goto LABEL_14;
  }
  v14 = ToUnicodeWithAlloc(NewParent, 1);
  v16 = v14;
  if ( !v14 )
  {
    v7 = v24;
    goto LABEL_10;
  }
LABEL_8:
  SetConnectionError((__int64)ConnectionPointer, v14, v15);
LABEL_14:
  if ( v23 )
    ldapFree((__int64)v23, 1768838476);
  EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 128));
  --*ConnectionPointer;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)ConnectionPointer, *ConnectionPointer);
  v20 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 128);
  if ( *ConnectionPointer )
  {
    LeaveCriticalSection(v20);
  }
  else
  {
    LeaveCriticalSection(v20);
    DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
  }
  return v16;
}

```

## disassembly

```asm
0x180047f80  push    rbp; ldap_rename_ext_s
0x180047f82  push    rbx
0x180047f83  push    rsi
0x180047f84  push    rdi
0x180047f85  push    r13
0x180047f87  push    r14
0x180047f89  push    r15
0x180047f8b  mov     rbp, rsp
0x180047f8e  sub     rsp, 80h
0x180047f95  xor     esi, esi
0x180047f97  mov     [rbp+var_20], 0
0x180047f9f  xor     r14d, r14d
0x180047fa2  mov     [rbp+var_28], rsi
0x180047fa6  mov     [rbp+var_18], r14
0x180047faa  mov     r15, r9
0x180047fad  mov     r13, r8
0x180047fb0  mov     [rbp+var_30], 0
0x180047fb7  mov     rdi, rdx
0x180047fba  mov     [rbp+res], 0
0x180047fc2  call    GetConnectionPointer
0x180047fc7  mov     rbx, rax
0x180047fca  test    rax, rax
0x180047fcd  jnz     short loc_180047FE2
0x180047fcf  lea     ebx, [rsi+59h]
0x180047fd2  xor     ecx, ecx
0x180047fd4  mov     edx, ebx
0x180047fd6  call    SetConnectionError
0x180047fdb  mov     eax, ebx
0x180047fdd  jmp     loc_1800481E9
0x180047fe2  mov     r9d, 696E554Ch
0x180047fe8  mov     [rsp+80h+var_60], 1; int
0x180047ff0  lea     r8, [rbp+var_20]
0x180047ff4  or      edx, 0FFFFFFFFh
0x180047ff7  mov     rcx, rdi; lpMultiByteStr
0x180047ffa  call    ToUnicodeWithAlloc
0x180047fff  mov     edi, eax
0x180048001  test    eax, eax
0x180048003  jz      short loc_180048017
0x180048005  mov     edx, eax
0x180048007  mov     rcx, rbx
0x18004800a  call    SetConnectionError
0x18004800f  xor     r13d, r13d
0x180048012  jmp     loc_180048137
0x180048017  mov     esi, 1
0x18004801c  lea     r8, [rbp+var_28]
0x180048020  mov     r9d, 696E554Ch
0x180048026  mov     [rsp+80h+var_60], esi; int
0x18004802a  or      edx, 0FFFFFFFFh
0x18004802d  mov     rcx, r13; lpMultiByteStr
0x180048030  call    ToUnicodeWithAlloc
0x180048035  xor     r13d, r13d
0x180048038  mov     edi, eax
0x18004803a  test    eax, eax
0x18004803c  jz      short loc_180048051
0x18004803e  mov     edx, eax
0x180048040  mov     rcx, rbx
0x180048043  call    SetConnectionError
0x180048048  mov     rsi, [rbp+var_28]
0x18004804c  jmp     loc_180048137
0x180048051  test    r15, r15
0x180048054  jz      short loc_180048090
0x180048056  mov     r9d, 696E554Ch
0x18004805c  mov     [rsp+80h+var_60], esi; int
0x180048060  lea     r8, [rbp+var_18]
0x180048064  or      edx, 0FFFFFFFFh
0x180048067  mov     rcx, r15; lpMultiByteStr
0x18004806a  call    ToUnicodeWithAlloc
0x18004806f  mov     edi, eax
0x180048071  test    eax, eax
0x180048073  jz      short loc_18004808C
0x180048075  mov     edx, eax
0x180048077  mov     rcx, rbx
0x18004807a  call    SetConnectionError
0x18004807f  mov     rsi, [rbp+var_28]
0x180048083  mov     r14, [rbp+var_18]
0x180048087  jmp     loc_180048137
0x18004808c  mov     r14, [rbp+var_18]
0x180048090  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x180048094  lea     rax, [rbp+var_30]
0x180048098  mov     [rsp+80h+var_38], rax; unsigned int *
0x18004809d  mov     r9, r14; unsigned __int16 *
0x1800480a0  mov     rax, [rbp+ClientControls]
0x1800480a4  mov     rcx, rbx; struct ldap_connection *
0x1800480a7  mov     [rsp+80h+var_40], rax; struct ldapcontrolW **
0x1800480ac  mov     rax, [rbp+ServerControls]
0x1800480b0  mov     [rsp+80h+var_48], rax; struct ldapcontrolW **
0x1800480b5  mov     eax, [rbp+DeleteOldRdn]
0x1800480b8  mov     [rsp+80h+var_50], sil; unsigned __int8
0x1800480bd  mov     rsi, [rbp+var_28]
0x1800480c1  mov     r8, rsi; unsigned __int16 *
0x1800480c4  mov     [rsp+80h+var_58], r13b; unsigned __int8
0x1800480c9  mov     [rsp+80h+var_60], eax; int
0x1800480cd  call    ?LdapRename@@YAKPEAUldap_connection@@PEAG11HEEPEAPEAUldapcontrolW@@2PEAK@Z; LdapRename(ldap_connection *,ushort *,ushort *,ushort *,int,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x1800480d2  mov     r15d, [rbp+var_30]
0x1800480d6  mov     edi, eax
0x1800480d8  cmp     r15d, 0FFFFFFFFh
0x1800480dc  jz      short loc_180048137
0x1800480de  xor     r9d, r9d
0x1800480e1  mov     qword ptr [rsp+80h+var_58], r13
0x1800480e6  lea     rax, [rbp+res]
0x1800480ea  mov     edx, r15d
0x1800480ed  mov     rcx, rbx
0x1800480f0  mov     qword ptr [rsp+80h+var_60], rax
0x1800480f5  lea     r8d, [r9+1]
0x1800480f9  call    ldap_result_with_error
0x1800480fe  mov     rdx, [rbp+res]; res
0x180048102  mov     edi, eax
0x180048104  test    rdx, rdx
0x180048107  jnz     short loc_180048123
0x180048109  mov     r8b, 1
0x18004810c  mov     edx, r15d
0x18004810f  mov     rcx, rbx
0x180048112  call    LdapAbandon
0x180048117  mov     edx, edi
0x180048119  mov     rcx, rbx
0x18004811c  call    SetConnectionError
0x180048121  jmp     short loc_180048137
0x180048123  mov     rcx, [rbx+1C0h]; ld
0x18004812a  mov     r8d, 1; freeit
0x180048130  call    ldap_result2error
0x180048135  mov     edi, eax
0x180048137  cmp     [rbp+var_20], r13
0x18004813b  jz      short loc_18004814B
0x18004813d  mov     rcx, [rbp+var_20]
0x180048141  mov     edx, 696E554Ch
0x180048146  call    ldapFree
0x18004814b  test    rsi, rsi
0x18004814e  jz      short loc_18004815D
0x180048150  mov     edx, 696E554Ch
0x180048155  mov     rcx, rsi
0x180048158  call    ldapFree
0x18004815d  test    r14, r14
0x180048160  jz      short loc_18004816F
0x180048162  mov     edx, 696E554Ch
0x180048167  mov     rcx, r14
0x18004816a  call    ldapFree
0x18004816f  lea     rsi, [rbx+200h]
0x180048176  mov     rcx, rsi; lpCriticalSection
0x180048179  call    cs:__imp_EnterCriticalSection
0x180048180  nop     dword ptr [rax+rax+00h]
0x180048185  dec     dword ptr [rbx]
0x180048187  cmp     cs:g_fTracingOn, r13d
0x18004818e  jz      short loc_1800481B8
0x180048190  cmp     cs:g_fProviderEnabled, r13d
0x180048197  jz      short loc_1800481B8
0x180048199  mov     ecx, 4
0x18004819e  test    byte ptr cs:g_ulTraceFlags, cl
0x1800481a4  jz      short loc_1800481B8
0x1800481a6  mov     r9d, [rbx]
0x1800481a9  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x1800481b0  mov     r8, rbx
0x1800481b3  call    LDAPClientPrint
0x1800481b8  mov     rcx, rsi; lpCriticalSection
0x1800481bb  cmp     [rbx], r13d
0x1800481be  jnz     short loc_1800481DB
0x1800481c0  call    cs:__imp_LeaveCriticalSection
0x1800481c7  nop     dword ptr [rax+rax+00h]
0x1800481cc  mov     edx, 1
0x1800481d1  mov     rcx, rbx
0x1800481d4  call    DereferenceLdapConnection2
0x1800481d9  jmp     short loc_1800481E7
0x1800481db  call    cs:__imp_LeaveCriticalSection
0x1800481e2  nop     dword ptr [rax+rax+00h]
0x1800481e7  mov     eax, edi
0x1800481e9  add     rsp, 80h
0x1800481f0  pop     r15
0x1800481f2  pop     r14
0x1800481f4  pop     r13
0x1800481f6  pop     rdi
0x1800481f7  pop     rsi
0x1800481f8  pop     rbx
0x1800481f9  pop     rbp
0x1800481fa  retn
```
