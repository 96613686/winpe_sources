# CacheRootDseResult(ldap_connection *,ldap_request *,ulong,CRequestListHolder,ldapmsg * *)

- ea: `0x180045b90`
- end: `0x180045d62`
- name: `?CacheRootDseResult@@YAKPEAUldap_connection@@PEAUldap_request@@KVCRequestListHolder@@PEAPEAUldapmsg@@@Z`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180019f88`

## callees

- `0x1800037a8`
- `0x1800057a0`
- `0x180008070`
- `0x18000a358`
- `0x18000e0d0`
- `0x1800112b0`
- `0x1800147f0`
- `0x18001a730`
- `0x1800235b0`
- `0x180045b90`

## string_xrefs

- `0x180045c2d`: `CacheRootDseResult:950`
- `0x180045c37`: `%s Cached the result for request: 0x%x FabricateLdapResult returned: 0x%x\n`
- `0x180045cb6`: `CacheRootDseResult:973`
- `0x180045cbd`: `%s Failed to cache the result for request: 0x%x Resending the request to the server\n`
- `0x180045d2d`: `CacheRootDseResult:993`
- `0x180045d34`: `%s Got the cached result for request: 0x%x\n`

## pseudocode

```c
__int64 __fastcall CacheRootDseResult(
        struct _RTL_CRITICAL_SECTION *a1,
        __int64 a2,
        unsigned int a3,
        struct CRequestListHolder *a4,
        struct ldapmsg **a5)
{
  unsigned __int8 v9; // al
  unsigned __int8 v10; // cl
  unsigned __int16 *v11; // r8
  unsigned __int16 **v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // r9d
  unsigned __int8 v17; // [rsp+20h] [rbp-78h]
  unsigned __int16 *v18; // [rsp+20h] [rbp-78h]
  unsigned int v19; // [rsp+30h] [rbp-68h]

  v9 = CopyResultToCache((const wchar_t **)a1, *a5);
  *(_BYTE *)(a2 + 273) = 0;
  v10 = *(_BYTE *)(a2 + 260);
  v11 = *(unsigned __int16 **)(a2 + 192);
  v12 = *(unsigned __int16 ***)(a2 + 248);
  if ( v9 == 1 )
  {
    v17 = *(_BYTE *)(a2 + 260);
    *(_BYTE *)(a2 + 274) = 1;
    v13 = FabricateLdapResult((struct ldap_request *)a2, (struct ldap_connection *)a1, v11, v12, v17);
    v14 = v13;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
      LDAPClientPrint(
        1024,
        "%s Cached the result for request: 0x%x FabricateLdapResult returned: 0x%x\n",
        "CacheRootDseResult:950",
        a2,
        v13);
  }
  else
  {
    v15 = *(_DWORD *)(a2 + 232);
    v19 = *(_DWORD *)(a2 + 256);
    v18 = *(unsigned __int16 **)(a2 + 240);
    *(_BYTE *)(a2 + 274) = 0;
    v14 = SendLdapSearch(
            (struct ldap_request *)a2,
            (struct ldap_connection *)a1,
            v11,
            v15,
            v18,
            v12,
            v19,
            v10,
            (struct CLdapBer **)(a2 + 160),
            0);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientPrint(
        0x10000000,
        "%s Failed to cache the result for request: 0x%x Resending the request to the server\n",
        "CacheRootDseResult:973",
        a2);
  }
  if ( !v14 )
  {
    ldap_msgfree(*a5);
    *a5 = 0;
    if ( *(_BYTE *)(a2 + 274) )
    {
      v14 = LdapBuffersToMessages(a1, a3, a4);
      CRequestListHolder::FreeAll(a4);
      LdapGetResponseFromServer((struct ldap_connection *)a1, (struct ldap_request *)a2, a3, a5);
      if ( *a5 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400) != 0 )
          LDAPClientPrint(1024, "%s Got the cached result for request: 0x%x\n", "CacheRootDseResult:993", a2);
        v14 = 0;
      }
    }
  }
  CRequestListHolder::~CRequestListHolder(a4);
  return v14;
}

```

## disassembly

```asm
0x180045b90  push    rbx
0x180045b92  push    rbp
0x180045b93  push    rsi
0x180045b94  push    rdi
0x180045b95  push    r12
0x180045b97  push    r13
0x180045b99  push    r14
0x180045b9b  push    r15
0x180045b9d  sub     rsp, 58h
0x180045ba1  mov     rsi, [rsp+98h+arg_20]
0x180045ba9  mov     rbx, rdx
0x180045bac  mov     r14, r9
0x180045baf  mov     r15d, r8d
0x180045bb2  mov     rbp, rcx
0x180045bb5  mov     rdx, [rsi]; struct ldapmsg *
0x180045bb8  call    ?CopyResultToCache@@YAEPEAUldap_connection@@PEAUldapmsg@@@Z; CopyResultToCache(ldap_connection *,ldapmsg *)
0x180045bbd  xor     r12d, r12d
0x180045bc0  mov     r13d, 400h
0x180045bc6  mov     [rbx+111h], r12b
0x180045bcd  mov     cl, [rbx+104h]
0x180045bd3  mov     r8, [rbx+0C0h]; unsigned __int16 *
0x180045bda  mov     rdx, [rbx+0F8h]
0x180045be1  cmp     al, 1
0x180045be3  jnz     short loc_180045C48
0x180045be5  mov     byte ptr [rsp+98h+var_78], cl; unsigned __int8
0x180045be9  mov     r9, rdx; unsigned __int16 **
0x180045bec  mov     rdx, rbp; struct ldap_connection *
0x180045bef  mov     [rbx+112h], al
0x180045bf5  mov     rcx, rbx; struct ldap_request *
0x180045bf8  call    ?FabricateLdapResult@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGPEAPEAGE@Z; FabricateLdapResult(ldap_request *,ldap_connection *,ushort *,ushort * *,uchar)
0x180045bfd  cmp     cs:g_fTracingOn, r12d
0x180045c04  mov     edi, eax
0x180045c06  jz      loc_180045CC9
0x180045c0c  cmp     cs:g_fProviderEnabled, r12d
0x180045c13  jz      loc_180045CC9
0x180045c19  test    cs:g_ulTraceFlags, r13
0x180045c20  jz      loc_180045CC9
0x180045c26  mov     r9, rbx
0x180045c29  mov     dword ptr [rsp+98h+var_78], eax
0x180045c2d  lea     r8, aCacherootdsere_0; "CacheRootDseResult:950"
0x180045c34  mov     ecx, r13d
0x180045c37  lea     rdx, aSCachedTheResu; "%s Cached the result for request: 0x%x "...
0x180045c3e  call    LDAPClientPrint
0x180045c43  jmp     loc_180045CC9
0x180045c48  mov     r9d, [rbx+0E8h]; unsigned int
0x180045c4f  lea     rax, [rbx+0A0h]
0x180045c56  mov     [rsp+98h+var_50], r12d; int
0x180045c5b  mov     [rsp+98h+var_58], rax; struct CLdapBer **
0x180045c60  mov     eax, [rbx+100h]
0x180045c66  mov     [rsp+98h+var_60], cl; unsigned __int8
0x180045c6a  mov     rcx, rbx; struct ldap_request *
0x180045c6d  mov     [rsp+98h+var_68], eax; unsigned int
0x180045c71  mov     rax, [rbx+0F0h]
0x180045c78  mov     [rsp+98h+var_70], rdx; unsigned __int16 **
0x180045c7d  mov     rdx, rbp; struct ldap_connection *
0x180045c80  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x180045c85  mov     [rbx+112h], r12b
0x180045c8c  call    ?SendLdapSearch@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGK2PEAPEAGKEPEAPEAVCLdapBer@@J@Z; SendLdapSearch(ldap_request *,ldap_connection *,ushort *,ulong,ushort *,ushort * *,ulong,uchar,CLdapBer * *,long)
0x180045c91  cmp     cs:g_fTracingOn, r12d
0x180045c98  mov     edi, eax
0x180045c9a  jz      short loc_180045CC9
0x180045c9c  cmp     cs:g_fProviderEnabled, r12d
0x180045ca3  jz      short loc_180045CC9
0x180045ca5  mov     ecx, 10000000h
0x180045caa  test    cs:g_ulTraceFlags, rcx
0x180045cb1  jz      short loc_180045CC9
0x180045cb3  mov     r9, rbx
0x180045cb6  lea     r8, aCacherootdsere; "CacheRootDseResult:973"
0x180045cbd  lea     rdx, aSFailedToCache; "%s Failed to cache the result for reque"...
0x180045cc4  call    LDAPClientPrint
0x180045cc9  test    edi, edi
0x180045ccb  jnz     short loc_180045D46
0x180045ccd  mov     rcx, [rsi]; res
0x180045cd0  call    ldap_msgfree
0x180045cd5  mov     [rsi], r12
0x180045cd8  cmp     [rbx+112h], r12b
0x180045cdf  jz      short loc_180045D46
0x180045ce1  mov     r8, r14; struct CRequestListHolder *
0x180045ce4  mov     edx, r15d; unsigned int
0x180045ce7  mov     rcx, rbp; struct ldap_connection *
0x180045cea  call    ?LdapBuffersToMessages@@YAKPEAUldap_connection@@KPEAVCRequestListHolder@@@Z; LdapBuffersToMessages(ldap_connection *,ulong,CRequestListHolder *)
0x180045cef  mov     rcx, r14; this
0x180045cf2  mov     edi, eax
0x180045cf4  call    ?FreeAll@CRequestListHolder@@QEAAXXZ; CRequestListHolder::FreeAll(void)
0x180045cf9  mov     r9, rsi; struct ldapmsg **
0x180045cfc  mov     r8d, r15d; unsigned int
0x180045cff  mov     rdx, rbx; struct ldap_request *
0x180045d02  mov     rcx, rbp; struct ldap_connection *
0x180045d05  call    ?LdapGetResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KPEAPEAUldapmsg@@@Z; LdapGetResponseFromServer(ldap_connection *,ldap_request *,ulong,ldapmsg * *)
0x180045d0a  cmp     [rsi], r12
0x180045d0d  jz      short loc_180045D46
0x180045d0f  cmp     cs:g_fTracingOn, r12d
0x180045d16  jz      short loc_180045D43
0x180045d18  cmp     cs:g_fProviderEnabled, r12d
0x180045d1f  jz      short loc_180045D43
0x180045d21  test    cs:g_ulTraceFlags, r13
0x180045d28  jz      short loc_180045D43
0x180045d2a  mov     r9, rbx
0x180045d2d  lea     r8, aCacherootdsere_1; "CacheRootDseResult:993"
0x180045d34  lea     rdx, aSGotTheCachedR; "%s Got the cached result for request: 0"...
0x180045d3b  mov     ecx, r13d
0x180045d3e  call    LDAPClientPrint
0x180045d43  mov     edi, r12d
0x180045d46  mov     rcx, r14; this
0x180045d49  call    ??1CRequestListHolder@@QEAA@XZ; CRequestListHolder::~CRequestListHolder(void)
0x180045d4e  mov     eax, edi
0x180045d50  add     rsp, 58h
0x180045d54  pop     r15
0x180045d56  pop     r14
0x180045d58  pop     r13
0x180045d5a  pop     r12
0x180045d5c  pop     rdi
0x180045d5d  pop     rsi
0x180045d5e  pop     rbp
0x180045d5f  pop     rbx
0x180045d60  retn
```
