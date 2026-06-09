# ldap_modrdn2W

- ea: `0x180047770`
- end: `0x180047923`
- name: `ldap_modrdn2W`
- size: `435`
- prototype: `ULONG __cdecl(LDAP *ExternalHandle, const PWSTR DistinguishedName, const PWSTR NewDistinguishedName, INT DeleteOldRdn)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x1800475f0`
- `0x180047a80`
- `0x180047bd0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000adb0`
- `0x18000b440`
- `0x18000cda0`
- `0x180040f04`
- `0x1800416d0`
- `0x180046f48`
- `0x180047770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004789f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004789f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800478e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800478e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047901`

## pseudocode

```c
ULONG __cdecl ldap_modrdn2W(
        LDAP *ExternalHandle,
        const PWSTR DistinguishedName,
        const PWSTR NewDistinguishedName,
        INT DeleteOldRdn)
{
  PWSTR v4; // rdi
  ULONG v5; // r14d
  _DWORD *ConnectionPointer; // rbx
  __int64 v10; // r8
  ULONG v11; // eax
  __int64 v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // edx
  unsigned __int64 v15; // r9
  unsigned int v16; // eax
  __int64 v17; // r8
  struct _RTL_CRITICAL_SECTION *v18; // rcx
  unsigned int v20; // [rsp+50h] [rbp-30h] BYREF
  PWSTR pDn; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int16 *v22; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v23; // [rsp+68h] [rbp-18h] BYREF
  _BYTE v24[16]; // [rsp+70h] [rbp-10h] BYREF

  v4 = 0;
  v5 = -1;
  v20 = -1;
  pDn = 0;
  v23 = 0;
  v22 = 0;
  ConnectionPointer = (_DWORD *)GetConnectionPointer(ExternalHandle, DistinguishedName, NewDistinguishedName);
  if ( !ConnectionPointer || !NewDistinguishedName )
  {
    v14 = 89;
    goto LABEL_13;
  }
  v11 = ldap_ufn2dnW(NewDistinguishedName, &pDn);
  if ( v11 )
  {
    SetConnectionError((__int64)ConnectionPointer, v11, v12);
    v4 = pDn;
    goto LABEL_14;
  }
  v4 = pDn;
  v13 = ParseLdapToken(pDn, &v23, v24, &v22);
  if ( v13 )
  {
    v14 = v13;
LABEL_13:
    SetConnectionError((__int64)ConnectionPointer, v14, v10);
    goto LABEL_14;
  }
  v15 = (unsigned __int64)v22;
  if ( v22 )
  {
    if ( *v22 == 44 )
    {
      *v22 = 0;
      v15 += 2LL;
    }
    v15 &= -(__int64)(*(_WORD *)v15 != 0);
  }
  v16 = LdapRename(
          (struct ldap_connection *)ConnectionPointer,
          DistinguishedName,
          v23,
          (unsigned __int16 *)v15,
          DeleteOldRdn,
          1u,
          0,
          0,
          0,
          &v20);
  SetConnectionError((__int64)ConnectionPointer, v16, v17);
  v5 = v20;
LABEL_14:
  if ( v4 )
    ldapFree((__int64)v4, 1849968460);
  if ( ConnectionPointer )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(ConnectionPointer + 128));
    --*ConnectionPointer;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)ConnectionPointer, *ConnectionPointer);
    v18 = (struct _RTL_CRITICAL_SECTION *)(ConnectionPointer + 128);
    if ( *ConnectionPointer )
    {
      LeaveCriticalSection(v18);
    }
    else
    {
      LeaveCriticalSection(v18);
      DereferenceLdapConnection2((__int64)ConnectionPointer, 1);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180047770  push    rbp
0x180047772  push    rbx
0x180047773  push    rsi
0x180047774  push    rdi
0x180047775  push    r12
0x180047777  push    r14
0x180047779  push    r15
0x18004777b  mov     rbp, rsp
0x18004777e  sub     rsp, 80h
0x180047785  xor     edi, edi
0x180047787  or      r14d, 0FFFFFFFFh
0x18004778b  mov     [rbp+var_30], r14d
0x18004778f  mov     r15d, r9d
0x180047792  mov     [rbp+pDn], rdi
0x180047796  mov     rsi, r8
0x180047799  mov     [rbp+var_18], rdi
0x18004779d  mov     r12, rdx
0x1800477a0  mov     [rbp+var_20], rdi
0x1800477a4  call    GetConnectionPointer
0x1800477a9  mov     rbx, rax
0x1800477ac  test    rax, rax
0x1800477af  jz      loc_180047871
0x1800477b5  test    rsi, rsi
0x1800477b8  jz      loc_180047871
0x1800477be  lea     rdx, [rbp+pDn]; pDn
0x1800477c2  mov     rcx, rsi; ufn
0x1800477c5  call    ldap_ufn2dnW
0x1800477ca  test    eax, eax
0x1800477cc  jz      short loc_1800477E1
0x1800477ce  mov     edx, eax
0x1800477d0  mov     rcx, rbx
0x1800477d3  call    SetConnectionError
0x1800477d8  mov     rdi, [rbp+pDn]
0x1800477dc  jmp     loc_18004787E
0x1800477e1  mov     rdi, [rbp+pDn]
0x1800477e5  lea     r9, [rbp+var_20]
0x1800477e9  mov     rcx, rdi
0x1800477ec  lea     r8, [rbp+var_10]
0x1800477f0  lea     rdx, [rbp+var_18]
0x1800477f4  call    ParseLdapToken
0x1800477f9  test    eax, eax
0x1800477fb  jz      short loc_180047801
0x1800477fd  mov     edx, eax
0x1800477ff  jmp     short loc_180047876
0x180047801  mov     r9, [rbp+var_20]
0x180047805  test    r9, r9
0x180047808  jz      short loc_180047828
0x18004780a  cmp     word ptr [r9], 2Ch ; ','
0x18004780f  jnz     short loc_18004781B
0x180047811  xor     eax, eax
0x180047813  mov     [r9], ax
0x180047817  add     r9, 2
0x18004781b  movzx   eax, word ptr [r9]
0x18004781f  neg     ax
0x180047822  sbb     rcx, rcx
0x180047825  and     r9, rcx; unsigned __int16 *
0x180047828  mov     r8, [rbp+var_18]; unsigned __int16 *
0x18004782c  lea     rax, [rbp+var_30]
0x180047830  mov     [rsp+80h+var_38], rax; unsigned int *
0x180047835  mov     rdx, r12; unsigned __int16 *
0x180047838  mov     [rsp+80h+var_40], 0; struct ldapcontrolW **
0x180047841  mov     rcx, rbx; struct ldap_connection *
0x180047844  mov     [rsp+80h+var_48], 0; struct ldapcontrolW **
0x18004784d  mov     [rsp+80h+var_50], 0; unsigned __int8
0x180047852  mov     [rsp+80h+var_58], 1; unsigned __int8
0x180047857  mov     [rsp+80h+var_60], r15d; int
0x18004785c  call    ?LdapRename@@YAKPEAUldap_connection@@PEAG11HEEPEAPEAUldapcontrolW@@2PEAK@Z; LdapRename(ldap_connection *,ushort *,ushort *,ushort *,int,uchar,uchar,ldapcontrolW * *,ldapcontrolW * *,ulong *)
0x180047861  mov     edx, eax
0x180047863  mov     rcx, rbx
0x180047866  call    SetConnectionError
0x18004786b  mov     r14d, [rbp+var_30]
0x18004786f  jmp     short loc_18004787E
0x180047871  mov     edx, 59h ; 'Y'
0x180047876  mov     rcx, rbx
0x180047879  call    SetConnectionError
0x18004787e  test    rdi, rdi
0x180047881  jz      short loc_180047890
0x180047883  mov     edx, 6E44474Ch
0x180047888  mov     rcx, rdi
0x18004788b  call    ldapFree
0x180047890  test    rbx, rbx
0x180047893  jz      short loc_18004790D
0x180047895  lea     rdi, [rbx+200h]
0x18004789c  mov     rcx, rdi; lpCriticalSection
0x18004789f  call    cs:__imp_EnterCriticalSection
0x1800478a6  nop     dword ptr [rax+rax+00h]
0x1800478ab  dec     dword ptr [rbx]
0x1800478ad  cmp     cs:g_fTracingOn, 0
0x1800478b4  jz      short loc_1800478DE
0x1800478b6  cmp     cs:g_fProviderEnabled, 0
0x1800478bd  jz      short loc_1800478DE
0x1800478bf  mov     ecx, 4
0x1800478c4  test    byte ptr cs:g_ulTraceFlags, cl
0x1800478ca  jz      short loc_1800478DE
0x1800478cc  mov     r9d, [rbx]
0x1800478cf  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x1800478d6  mov     r8, rbx
0x1800478d9  call    LDAPClientPrint
0x1800478de  cmp     dword ptr [rbx], 0
0x1800478e1  mov     rcx, rdi; lpCriticalSection
0x1800478e4  jnz     short loc_180047901
0x1800478e6  call    cs:__imp_LeaveCriticalSection
0x1800478ed  nop     dword ptr [rax+rax+00h]
0x1800478f2  mov     edx, 1
0x1800478f7  mov     rcx, rbx
0x1800478fa  call    DereferenceLdapConnection2
0x1800478ff  jmp     short loc_18004790D
0x180047901  call    cs:__imp_LeaveCriticalSection
0x180047908  nop     dword ptr [rax+rax+00h]
0x18004790d  mov     eax, r14d
0x180047910  add     rsp, 80h
0x180047917  pop     r15
0x180047919  pop     r14
0x18004791b  pop     r12
0x18004791d  pop     rdi
0x18004791e  pop     rsi
0x18004791f  pop     rbx
0x180047920  pop     rbp
0x180047921  retn
```
