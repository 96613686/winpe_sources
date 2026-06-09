# ldap_result2error

- ea: `0x180016360`
- end: `0x180016499`
- name: `ldap_result2error`
- size: `313`
- prototype: `ULONG __cdecl(LDAP *ld, LDAPMessage *res, ULONG freeit)`
- caller_count: `20`
- callee_count: `6`
- tags: ``

## callers

- `0x1800153c0`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18002a4f0`
- `0x18003a9b0`
- `0x18003abb0`
- `0x18003ce30`
- `0x18003d0d0`
- `0x18003ea40`
- `0x18003ec30`
- `0x18003f760`
- `0x18003f970`
- `0x180040b10`
- `0x180040d10`
- `0x180047930`
- `0x180047a80`
- `0x180047f80`
- `0x180048210`
- `0x180048d40`
- `0x18004b28c`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000cda0`
- `0x1800147f0`
- `0x180016360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800163f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016425`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800163f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016425`

## pseudocode

```c
ULONG __cdecl ldap_result2error(LDAP *ld, LDAPMessage *res, ULONG freeit)
{
  __int64 ConnectionPointer; // rax
  __int64 v7; // r8
  __int64 v8; // rbx
  LDAPMessage *v9; // rsi
  unsigned int lm_returncode; // edi
  LDAPMessage *v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rcx

  ConnectionPointer = GetConnectionPointer(ld, res, freeit);
  v8 = ConnectionPointer;
  if ( ConnectionPointer || !ld )
  {
    v9 = 0;
    if ( res != (LDAPMessage *)-1LL )
      v9 = res;
    if ( v9 )
    {
      lm_returncode = v9->lm_returncode;
      v11 = v9;
      do
      {
        if ( v11->lm_msgtype != 115 && v11->lm_msgtype != 100 )
          break;
        v11 = v11->lm_chain;
      }
      while ( v11 );
      if ( v11 )
        lm_returncode = v11->lm_returncode;
      SetConnectionError(v8, lm_returncode, v7);
      if ( freeit )
        ldap_msgfree(v9);
      if ( !v8 )
        return lm_returncode;
    }
    else
    {
      if ( !ConnectionPointer )
        return 82;
      lm_returncode = *(_DWORD *)(ConnectionPointer + 1020);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 512));
    --*(_DWORD *)v8;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", v8, *(_DWORD *)v8);
    v12 = (struct _RTL_CRITICAL_SECTION *)(v8 + 512);
    if ( *(_DWORD *)v8 )
    {
      LeaveCriticalSection(v12);
    }
    else
    {
      LeaveCriticalSection(v12);
      DereferenceLdapConnection2(v8, 1);
    }
    return lm_returncode;
  }
  return 89;
}

```

## disassembly

```asm
0x180016360  push    rbx
0x180016362  push    rbp
0x180016363  push    rsi
0x180016364  push    rdi
0x180016365  push    r14
0x180016367  sub     rsp, 20h
0x18001636b  mov     r14d, r8d
0x18001636e  mov     rbp, rdx
0x180016371  mov     rdi, rcx
0x180016374  call    GetConnectionPointer
0x180016379  mov     rbx, rax
0x18001637c  test    rax, rax
0x18001637f  jz      loc_180016447
0x180016385  xor     esi, esi
0x180016387  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18001638b  cmovnz  rsi, rbp
0x18001638f  test    rsi, rsi
0x180016392  jz      loc_180016418
0x180016398  mov     edi, [rsi+38h]
0x18001639b  mov     rax, rsi
0x18001639e  cmp     dword ptr [rax+4], 73h ; 's'
0x1800163a2  jz      short loc_18001640D
0x1800163a4  cmp     dword ptr [rax+4], 64h ; 'd'
0x1800163a8  jz      short loc_18001640D
0x1800163aa  test    rax, rax
0x1800163ad  jz      short loc_1800163B2
0x1800163af  mov     edi, [rax+38h]
0x1800163b2  mov     edx, edi
0x1800163b4  mov     rcx, rbx
0x1800163b7  call    SetConnectionError
0x1800163bc  test    r14d, r14d
0x1800163bf  jnz     loc_180016457
0x1800163c5  test    rbx, rbx
0x1800163c8  jz      short loc_1800163FF
0x1800163ca  lea     rsi, [rbx+200h]
0x1800163d1  mov     rcx, rsi; lpCriticalSection
0x1800163d4  call    cs:__imp_EnterCriticalSection
0x1800163db  nop     dword ptr [rax+rax+00h]
0x1800163e0  dec     dword ptr [rbx]
0x1800163e2  cmp     cs:g_fTracingOn, 0
0x1800163e9  jnz     short loc_180016464
0x1800163eb  cmp     dword ptr [rbx], 0
0x1800163ee  mov     rcx, rsi; lpCriticalSection
0x1800163f1  jz      short loc_180016425
0x1800163f3  call    cs:__imp_LeaveCriticalSection
0x1800163fa  nop     dword ptr [rax+rax+00h]
0x1800163ff  mov     eax, edi
0x180016401  add     rsp, 20h
0x180016405  pop     r14
0x180016407  pop     rdi
0x180016408  pop     rsi
0x180016409  pop     rbp
0x18001640a  pop     rbx
0x18001640b  retn
0x18001640d  mov     rax, [rax+10h]
0x180016411  test    rax, rax
0x180016414  jnz     short loc_18001639E
0x180016416  jmp     short loc_1800163AA
0x180016418  test    rbx, rbx
0x18001641b  jz      short loc_180016440
0x18001641d  mov     edi, [rax+3FCh]
0x180016423  jmp     short loc_1800163CA
0x180016425  call    cs:__imp_LeaveCriticalSection
0x18001642c  nop     dword ptr [rax+rax+00h]
0x180016431  mov     edx, 1
0x180016436  mov     rcx, rbx
0x180016439  call    DereferenceLdapConnection2
0x18001643e  jmp     short loc_1800163FF
0x180016440  mov     edi, 52h ; 'R'
0x180016445  jmp     short loc_1800163FF
0x180016447  test    rdi, rdi
0x18001644a  jz      loc_180016385
0x180016450  mov     eax, 59h ; 'Y'
0x180016455  jmp     short loc_180016401
0x180016457  mov     rcx, rsi; res
0x18001645a  call    ldap_msgfree
0x18001645f  jmp     loc_1800163C5
0x180016464  cmp     cs:g_fProviderEnabled, 0
0x18001646b  jz      loc_1800163EB
0x180016471  mov     ecx, 4
0x180016476  test    byte ptr cs:g_ulTraceFlags, cl
0x18001647c  jz      loc_1800163EB
0x180016482  mov     r9d, [rbx]
0x180016485  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x18001648c  mov     r8, rbx
0x18001648f  call    LDAPClientPrint
0x180016494  jmp     loc_1800163EB
```
