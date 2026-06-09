# ldap_compare_ext_sA

- ea: `0x18003ce30`
- end: `0x18003d0c9`
- name: `ldap_compare_ext_sA`
- size: `665`
- prototype: `ULONG __cdecl(LDAP *ld, const PSTR dn, const PSTR Attr, const PSTR Value, struct berval *Data, PLDAPControlA *ServerControls, PLDAPControlA *ClientControls)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003d260`

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
- `0x18003c254`
- `0x18003ce30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d03c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d03c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d083`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d09e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d083`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d09e`

## pseudocode

```c
ULONG __cdecl ldap_compare_ext_sA(
        LDAP *ld,
        const PSTR dn,
        const PSTR Attr,
        const PSTR Value,
        struct berval *Data,
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
  ConnectionPointer = (_DWORD *)GetConnectionPointer(ld, dn, Attr);
  if ( !ConnectionPointer )
  {
    SetConnectionError(0, 0x59u, v12);
    return 89;
  }
  v14 = ToUnicodeWithAlloc(dn, 1);
  v16 = v14;
  if ( v14 )
    goto LABEL_9;
  v14 = ToUnicodeWithAlloc(Attr, 1);
  v16 = v14;
  if ( v14 )
    goto LABEL_9;
  if ( !Value || Data )
  {
LABEL_11:
    v17 = LdapCompare(
            (struct ldap_connection *)ConnectionPointer,
            v23,
            v22,
            v7,
            Data,
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
        v16 = ldap_result2error(ld, res, 1u);
      }
      else
      {
        LdapAbandon((__int64)ConnectionPointer, v18, 1);
        SetConnectionError((__int64)ConnectionPointer, v16, v19);
      }
    }
    goto LABEL_15;
  }
  v14 = ToUnicodeWithAlloc(Value, 1);
  v16 = v14;
  if ( !v14 )
  {
    v7 = v24;
    goto LABEL_11;
  }
LABEL_9:
  SetConnectionError((__int64)ConnectionPointer, v14, v15);
LABEL_15:
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
0x18003ce30  mov     [rsp-28h+arg_8], rbx; ldap_compare_ext_s
0x18003ce35  mov     [rsp-28h+arg_10], rsi
0x18003ce3a  mov     [rsp-28h+ld], rcx
0x18003ce3f  push    rbp
0x18003ce40  push    rdi
0x18003ce41  push    r13
0x18003ce43  push    r14
0x18003ce45  push    r15
0x18003ce47  mov     rbp, rsp
0x18003ce4a  sub     rsp, 80h
0x18003ce51  xor     esi, esi
0x18003ce53  mov     [rbp+var_20], 0
0x18003ce5b  xor     r14d, r14d
0x18003ce5e  mov     [rbp+var_28], rsi
0x18003ce62  mov     [rbp+var_18], r14
0x18003ce66  mov     r15, r9
0x18003ce69  mov     r13, r8
0x18003ce6c  mov     [rbp+var_30], 0
0x18003ce73  mov     rdi, rdx
0x18003ce76  mov     [rbp+res], 0
0x18003ce7e  call    GetConnectionPointer
0x18003ce83  mov     rbx, rax
0x18003ce86  test    rax, rax
0x18003ce89  jnz     short loc_18003CE9E
0x18003ce8b  lea     ebx, [rsi+59h]
0x18003ce8e  xor     ecx, ecx
0x18003ce90  mov     edx, ebx
0x18003ce92  call    SetConnectionError
0x18003ce97  mov     eax, ebx
0x18003ce99  jmp     loc_18003D0AC
0x18003ce9e  mov     r9d, 696E554Ch
0x18003cea4  mov     dword ptr [rsp+80h+var_60], 1; int
0x18003ceac  lea     r8, [rbp+var_20]
0x18003ceb0  or      edx, 0FFFFFFFFh
0x18003ceb3  mov     rcx, rdi; lpMultiByteStr
0x18003ceb6  call    ToUnicodeWithAlloc
0x18003cebb  mov     edi, eax
0x18003cebd  test    eax, eax
0x18003cebf  jz      short loc_18003CED3
0x18003cec1  mov     edx, eax
0x18003cec3  mov     rcx, rbx
0x18003cec6  call    SetConnectionError
0x18003cecb  xor     r13d, r13d
0x18003cece  jmp     loc_18003CFFA
0x18003ced3  mov     r9d, 696E554Ch
0x18003ced9  mov     dword ptr [rsp+80h+var_60], 1; int
0x18003cee1  lea     r8, [rbp+var_28]
0x18003cee5  or      edx, 0FFFFFFFFh
0x18003cee8  mov     rcx, r13; lpMultiByteStr
0x18003ceeb  call    ToUnicodeWithAlloc
0x18003cef0  xor     r13d, r13d
0x18003cef3  mov     edi, eax
0x18003cef5  test    eax, eax
0x18003cef7  jz      short loc_18003CF0C
0x18003cef9  mov     edx, eax
0x18003cefb  mov     rcx, rbx
0x18003cefe  call    SetConnectionError
0x18003cf03  mov     rsi, [rbp+var_28]
0x18003cf07  jmp     loc_18003CFFA
0x18003cf0c  mov     rsi, [rbp+Data]
0x18003cf10  test    r15, r15
0x18003cf13  jz      short loc_18003CF58
0x18003cf15  test    rsi, rsi
0x18003cf18  jnz     short loc_18003CF58
0x18003cf1a  mov     r9d, 696E554Ch
0x18003cf20  mov     dword ptr [rsp+80h+var_60], 1; int
0x18003cf28  lea     r8, [rbp+var_18]
0x18003cf2c  or      edx, 0FFFFFFFFh
0x18003cf2f  mov     rcx, r15; lpMultiByteStr
0x18003cf32  call    ToUnicodeWithAlloc
0x18003cf37  mov     edi, eax
0x18003cf39  test    eax, eax
0x18003cf3b  jz      short loc_18003CF54
0x18003cf3d  mov     edx, eax
0x18003cf3f  mov     rcx, rbx
0x18003cf42  call    SetConnectionError
0x18003cf47  mov     rsi, [rbp+var_28]
0x18003cf4b  mov     r14, [rbp+var_18]
0x18003cf4f  jmp     loc_18003CFFA
0x18003cf54  mov     r14, [rbp+var_18]
0x18003cf58  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18003cf5c  lea     rax, [rbp+var_30]
0x18003cf60  mov     [rsp+80h+var_38], rax; unsigned int *
0x18003cf65  mov     r9, r14; unsigned __int16 *
0x18003cf68  mov     rax, [rbp+ClientControls]
0x18003cf6c  mov     rcx, rbx; struct ldap_connection *
0x18003cf6f  mov     [rsp+80h+var_40], rax; struct ldapcontrolW **
0x18003cf74  mov     rax, [rbp+ServerControls]
0x18003cf78  mov     [rsp+80h+var_48], rax; struct ldapcontrolW **
0x18003cf7d  mov     [rsp+80h+var_50], 1; unsigned __int8
0x18003cf82  mov     [rsp+80h+var_58], r13b; unsigned __int8
0x18003cf87  mov     [rsp+80h+var_60], rsi; struct berval *
0x18003cf8c  mov     rsi, [rbp+var_28]
0x18003cf90  mov     r8, rsi; unsigned __int16 *
0x18003cf93  call    ?LdapCompare@@YAKPEAUldap_connection@@PEAG11PEAUberval@@EEPEAPEAUldapcontrolW@@3PEAK@Z; LdapCompare(ldap_connection *,ushort *,ushort *,ushort *,berval *,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x18003cf98  mov     r15d, [rbp+var_30]
0x18003cf9c  mov     edi, eax
0x18003cf9e  cmp     r15d, 0FFFFFFFFh
0x18003cfa2  jz      short loc_18003CFFA
0x18003cfa4  xor     r9d, r9d
0x18003cfa7  mov     qword ptr [rsp+80h+var_58], r13
0x18003cfac  lea     rax, [rbp+res]
0x18003cfb0  mov     edx, r15d
0x18003cfb3  mov     rcx, rbx
0x18003cfb6  mov     [rsp+80h+var_60], rax
0x18003cfbb  lea     r8d, [r9+1]
0x18003cfbf  call    ldap_result_with_error
0x18003cfc4  mov     rdx, [rbp+res]; res
0x18003cfc8  mov     edi, eax
0x18003cfca  test    rdx, rdx
0x18003cfcd  jnz     short loc_18003CFE9
0x18003cfcf  mov     r8b, 1
0x18003cfd2  mov     edx, r15d
0x18003cfd5  mov     rcx, rbx
0x18003cfd8  call    LdapAbandon
0x18003cfdd  mov     edx, edi
0x18003cfdf  mov     rcx, rbx
0x18003cfe2  call    SetConnectionError
0x18003cfe7  jmp     short loc_18003CFFA
0x18003cfe9  mov     rcx, [rbp+ld]; ld
0x18003cfed  mov     r8d, 1; freeit
0x18003cff3  call    ldap_result2error
0x18003cff8  mov     edi, eax
0x18003cffa  cmp     [rbp+var_20], r13
0x18003cffe  jz      short loc_18003D00E
0x18003d000  mov     rcx, [rbp+var_20]
0x18003d004  mov     edx, 696E554Ch
0x18003d009  call    ldapFree
0x18003d00e  test    rsi, rsi
0x18003d011  jz      short loc_18003D020
0x18003d013  mov     edx, 696E554Ch
0x18003d018  mov     rcx, rsi
0x18003d01b  call    ldapFree
0x18003d020  test    r14, r14
0x18003d023  jz      short loc_18003D032
0x18003d025  mov     edx, 696E554Ch
0x18003d02a  mov     rcx, r14
0x18003d02d  call    ldapFree
0x18003d032  lea     rsi, [rbx+200h]
0x18003d039  mov     rcx, rsi; lpCriticalSection
0x18003d03c  call    cs:__imp_EnterCriticalSection
0x18003d043  nop     dword ptr [rax+rax+00h]
0x18003d048  dec     dword ptr [rbx]
0x18003d04a  cmp     cs:g_fTracingOn, r13d
0x18003d051  jz      short loc_18003D07B
0x18003d053  cmp     cs:g_fProviderEnabled, r13d
0x18003d05a  jz      short loc_18003D07B
0x18003d05c  mov     ecx, 4
0x18003d061  test    byte ptr cs:g_ulTraceFlags, cl
0x18003d067  jz      short loc_18003D07B
0x18003d069  mov     r9d, [rbx]
0x18003d06c  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18003d073  mov     r8, rbx
0x18003d076  call    LDAPClientPrint
0x18003d07b  mov     rcx, rsi; lpCriticalSection
0x18003d07e  cmp     [rbx], r13d
0x18003d081  jnz     short loc_18003D09E
0x18003d083  call    cs:__imp_LeaveCriticalSection
0x18003d08a  nop     dword ptr [rax+rax+00h]
0x18003d08f  mov     edx, 1
0x18003d094  mov     rcx, rbx
0x18003d097  call    DereferenceLdapConnection2
0x18003d09c  jmp     short loc_18003D0AA
0x18003d09e  call    cs:__imp_LeaveCriticalSection
0x18003d0a5  nop     dword ptr [rax+rax+00h]
0x18003d0aa  mov     eax, edi
0x18003d0ac  lea     r11, [rsp+80h+var_s0]
0x18003d0b4  mov     rbx, [r11+38h]
0x18003d0b8  mov     rsi, [r11+40h]
0x18003d0bc  mov     rsp, r11
0x18003d0bf  pop     r15
0x18003d0c1  pop     r14
0x18003d0c3  pop     r13
0x18003d0c5  pop     rdi
0x18003d0c6  pop     rbp
0x18003d0c7  retn
```
