# ldap_msgfree

- ea: `0x1800147f0`
- end: `0x180014b50`
- name: `ldap_msgfree`
- size: `864`
- prototype: `ULONG __cdecl(LDAPMessage *res)`
- caller_count: `17`
- callee_count: `5`
- tags: ``

## callers

- `0x1800018d0`
- `0x180006d80`
- `0x180008710`
- `0x18000adb0`
- `0x18000bf40`
- `0x180012ab0`
- `0x180016360`
- `0x1800164a0`
- `0x180017854`
- `0x1800188d0`
- `0x18001b0d4`
- `0x180029f50`
- `0x18003ada4`
- `0x180045448`
- `0x180045b90`
- `0x180046aa8`
- `0x1800491d4`

## callees

- `0x1800037a8`
- `0x18000adb0`
- `0x180014460`
- `0x1800147f0`
- `0x18002c7e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001495e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001495e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001488f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001488f`

## string_xrefs

- `0x180014abb`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
ULONG __cdecl ldap_msgfree(LDAPMessage *res)
{
  LDAPMessage *v1; // rbx
  CLdapBer *lm_ber; // rcx
  LDAPMessage *lm_chain; // rsi
  int v4; // eax
  int v5; // r9d
  int v6; // r8d
  int v7; // eax
  HANDLE v8; // rcx
  _DWORD *ConnectionPointer2; // rax
  _DWORD *v11; // rdi
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  struct _RTL_CRITICAL_SECTION *v13; // rcx

  v1 = res;
  if ( res )
  {
    while ( 1 )
    {
      lm_ber = (CLdapBer *)v1->lm_ber;
      lm_chain = v1->lm_chain;
      if ( lm_ber )
        CLdapBer::`scalar deleting destructor'(lm_ber);
      if ( v1->ConnectionReferenced && v1->Connection )
      {
        ConnectionPointer2 = (_DWORD *)GetConnectionPointer2();
        v11 = ConnectionPointer2;
        if ( ConnectionPointer2 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
            LDAPClientPrint(
              4,
              "Dereferencing Connection 0x%x with reference count 0x%x\n",
              (_DWORD)ConnectionPointer2,
              *ConnectionPointer2);
          EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 128));
          --*v11;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
            LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v11, *v11);
          v12 = (struct _RTL_CRITICAL_SECTION *)(v11 + 128);
          if ( *v11 )
          {
            LeaveCriticalSection(v12);
          }
          else
          {
            LeaveCriticalSection(v12);
            DereferenceLdapConnection2((__int64)v11, 1);
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 128));
          --*v11;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
            LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v11, *v11);
          v13 = (struct _RTL_CRITICAL_SECTION *)(v11 + 128);
          if ( *v11 )
          {
            LeaveCriticalSection(v13);
          }
          else
          {
            LeaveCriticalSection(v13);
            DereferenceLdapConnection2((__int64)v11, 1);
          }
          v1->Connection = 0;
        }
        else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        {
          LDAPClientPrint(0x10000000, "Referencing Connection 0x%x failed.\n", v1->Connection);
        }
      }
      v4 = *(_DWORD *)&v1[-1].ConnectionReferenced;
      if ( v4 == 1684095564 )
        goto LABEL_11;
      if ( v4 != 1701987916 )
        goto LABEL_7;
      if ( g_fTracingOn )
        break;
LABEL_8:
      v5 = *(_DWORD *)&v1[-1].ConnectionReferenced;
      if ( v5 != 1735609676 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1735609676, v5);
      v6 = *((_DWORD *)&v1[-1].ConnectionReferenced + 1);
      v7 = LdapAllocatedHeap - v6;
      LdapAllocatedHeap -= v6;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
          v6,
          (_DWORD)v1,
          1735609676,
          v7);
      v8 = LdapHeap;
      *(_DWORD *)&v1[-1].ConnectionReferenced = 1701987916;
      HeapFree(v8, 0, &v1[-1].ConnectionReferenced);
LABEL_11:
      v1 = lm_chain;
      if ( !lm_chain )
        return 0;
    }
    if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)v1);
LABEL_7:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
        *((_DWORD *)&v1[-1].ConnectionReferenced + 1),
        (_DWORD)v1 - 8,
        1735609676);
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x1800147f0  push    rbx
0x1800147f2  sub     rsp, 30h
0x1800147f6  mov     rbx, rcx
0x1800147f9  test    rcx, rcx
0x1800147fc  jz      loc_1800148B6
0x180014802  mov     [rsp+38h+arg_8], rsi
0x180014807  mov     [rsp+38h+arg_10], rdi
0x18001480c  mov     [rsp+38h+arg_0], rbp
0x180014811  mov     rcx, [rbx+8]; this
0x180014815  mov     rsi, [rbx+10h]
0x180014819  test    rcx, rcx
0x18001481c  jnz     loc_1800148BF
0x180014822  cmp     byte ptr [rbx+40h], 0
0x180014826  jnz     loc_180014904
0x18001482c  mov     eax, [rbx-8]
0x18001482f  cmp     eax, 6461424Ch
0x180014834  jz      short loc_18001489B
0x180014836  cmp     eax, 6572464Ch
0x18001483b  jz      loc_180014A91
0x180014841  cmp     cs:g_fTracingOn, 0
0x180014848  jnz     loc_180014AD1
0x18001484e  mov     r9d, [rbx-8]
0x180014852  cmp     r9d, 67734D4Ch
0x180014859  jnz     short loc_1800148C9
0x18001485b  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180014861  mov     r8d, [rbx-4]
0x180014865  sub     eax, r8d
0x180014868  cmp     cs:g_fTracingOn, 0
0x18001486f  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180014875  jnz     loc_180014B11
0x18001487b  mov     rcx, cs:LdapHeap; hHeap
0x180014882  lea     r8, [rbx-8]; lpMem
0x180014886  xor     edx, edx; dwFlags
0x180014888  mov     dword ptr [rbx-8], 6572464Ch
0x18001488f  call    cs:__imp_HeapFree
0x180014896  nop     dword ptr [rax+rax+00h]
0x18001489b  mov     rbx, rsi
0x18001489e  test    rsi, rsi
0x1800148a1  jnz     loc_180014811
0x1800148a7  mov     rdi, [rsp+38h+arg_10]
0x1800148ac  mov     rsi, [rsp+38h+arg_8]
0x1800148b1  mov     rbp, [rsp+38h+arg_0]
0x1800148b6  xor     eax, eax
0x1800148b8  add     rsp, 30h
0x1800148bc  pop     rbx
0x1800148bd  retn
0x1800148bf  call    ??_GCLdapBer@@QEAAPEAXI@Z; CLdapBer::`scalar deleting destructor'(uint)
0x1800148c4  jmp     loc_180014822
0x1800148c9  cmp     cs:g_fTracingOn, 0
0x1800148d0  jz      short loc_18001485B
0x1800148d2  cmp     cs:g_fProviderEnabled, 0
0x1800148d9  jz      short loc_18001485B
0x1800148db  test    byte ptr cs:g_ulTraceFlags, 8
0x1800148e2  jz      loc_18001485B
0x1800148e8  mov     r8d, 67734D4Ch
0x1800148ee  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x1800148f5  mov     ecx, 8
0x1800148fa  call    LDAPClientPrint
0x1800148ff  jmp     loc_18001485B
0x180014904  mov     rcx, [rbx+28h]
0x180014908  test    rcx, rcx
0x18001490b  jz      loc_18001482C
0x180014911  call    GetConnectionPointer2
0x180014916  mov     rdi, rax
0x180014919  test    rax, rax
0x18001491c  jz      loc_180014A4C
0x180014922  cmp     cs:g_fTracingOn, 0
0x180014929  jz      short loc_180014954
0x18001492b  cmp     cs:g_fProviderEnabled, 0
0x180014932  jz      short loc_180014954
0x180014934  test    byte ptr cs:g_ulTraceFlags, 4
0x18001493b  jz      short loc_180014954
0x18001493d  mov     r9d, [rax]
0x180014940  lea     rdx, aDereferencingC; "Dereferencing Connection 0x%x with refe"...
0x180014947  mov     r8, rax
0x18001494a  mov     ecx, 4
0x18001494f  call    LDAPClientPrint
0x180014954  lea     rbp, [rdi+200h]
0x18001495b  mov     rcx, rbp; lpCriticalSection
0x18001495e  call    cs:__imp_EnterCriticalSection
0x180014965  nop     dword ptr [rax+rax+00h]
0x18001496a  dec     dword ptr [rdi]
0x18001496c  cmp     cs:g_fTracingOn, 0
0x180014973  jz      short loc_18001499E
0x180014975  cmp     cs:g_fProviderEnabled, 0
0x18001497c  jz      short loc_18001499E
0x18001497e  test    byte ptr cs:g_ulTraceFlags, 4
0x180014985  jz      short loc_18001499E
0x180014987  mov     r9d, [rdi]
0x18001498a  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180014991  mov     r8, rdi
0x180014994  mov     ecx, 4
0x180014999  call    LDAPClientPrint
0x18001499e  cmp     dword ptr [rdi], 0
0x1800149a1  mov     rcx, rbp; lpCriticalSection
0x1800149a4  jnz     short loc_1800149C1
0x1800149a6  call    cs:__imp_LeaveCriticalSection
0x1800149ad  nop     dword ptr [rax+rax+00h]
0x1800149b2  mov     edx, 1
0x1800149b7  mov     rcx, rdi
0x1800149ba  call    DereferenceLdapConnection2
0x1800149bf  jmp     short loc_1800149CD
0x1800149c1  call    cs:__imp_LeaveCriticalSection
0x1800149c8  nop     dword ptr [rax+rax+00h]
0x1800149cd  mov     rcx, rbp; lpCriticalSection
0x1800149d0  call    cs:__imp_EnterCriticalSection
0x1800149d7  nop     dword ptr [rax+rax+00h]
0x1800149dc  dec     dword ptr [rdi]
0x1800149de  cmp     cs:g_fTracingOn, 0
0x1800149e5  jz      short loc_180014A10
0x1800149e7  cmp     cs:g_fProviderEnabled, 0
0x1800149ee  jz      short loc_180014A10
0x1800149f0  test    byte ptr cs:g_ulTraceFlags, 4
0x1800149f7  jz      short loc_180014A10
0x1800149f9  mov     r9d, [rdi]
0x1800149fc  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180014a03  mov     r8, rdi
0x180014a06  mov     ecx, 4
0x180014a0b  call    LDAPClientPrint
0x180014a10  cmp     dword ptr [rdi], 0
0x180014a13  mov     rcx, rbp; lpCriticalSection
0x180014a16  jnz     short loc_180014A33
0x180014a18  call    cs:__imp_LeaveCriticalSection
0x180014a1f  nop     dword ptr [rax+rax+00h]
0x180014a24  mov     edx, 1
0x180014a29  mov     rcx, rdi
0x180014a2c  call    DereferenceLdapConnection2
0x180014a31  jmp     short loc_180014A3F
0x180014a33  call    cs:__imp_LeaveCriticalSection
0x180014a3a  nop     dword ptr [rax+rax+00h]
0x180014a3f  mov     qword ptr [rbx+28h], 0
0x180014a47  jmp     loc_18001482C
0x180014a4c  cmp     cs:g_fTracingOn, 0
0x180014a53  jz      loc_18001482C
0x180014a59  cmp     cs:g_fProviderEnabled, 0
0x180014a60  jz      loc_18001482C
0x180014a66  test    cs:g_ulTraceFlags, 10000000h
0x180014a71  jz      loc_18001482C
0x180014a77  mov     r8, [rbx+28h]
0x180014a7b  lea     rdx, aReferencingCon; "Referencing Connection 0x%x failed.\n"
0x180014a82  mov     ecx, 10000000h
0x180014a87  call    LDAPClientPrint
0x180014a8c  jmp     loc_18001482C
0x180014a91  cmp     cs:g_fTracingOn, 0
0x180014a98  jz      loc_18001484E
0x180014a9e  cmp     cs:g_fProviderEnabled, 0
0x180014aa5  jz      loc_180014841
0x180014aab  test    byte ptr cs:g_ulTraceFlags, 8
0x180014ab2  jz      loc_180014841
0x180014ab8  mov     r8, rbx
0x180014abb  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x180014ac2  mov     ecx, 8
0x180014ac7  call    LDAPClientPrint
0x180014acc  jmp     loc_180014841
0x180014ad1  cmp     cs:g_fProviderEnabled, 0
0x180014ad8  jz      loc_18001484E
0x180014ade  test    byte ptr cs:g_ulTraceFlags, 8
0x180014ae5  jz      loc_18001484E
0x180014aeb  mov     r8d, [rbx-4]
0x180014aef  lea     r9, [rbx-8]
0x180014af3  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x180014afa  mov     [rsp+38h+var_18], 67734D4Ch
0x180014b02  mov     ecx, 8
0x180014b07  call    LDAPClientPrint
0x180014b0c  jmp     loc_18001484E
0x180014b11  cmp     cs:g_fProviderEnabled, 0
0x180014b18  jz      loc_18001487B
0x180014b1e  test    byte ptr cs:g_ulTraceFlags, 8
0x180014b25  jz      loc_18001487B
0x180014b2b  mov     [rsp+38h+var_10], eax
0x180014b2f  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x180014b36  mov     r9, rbx
0x180014b39  mov     [rsp+38h+var_18], 67734D4Ch
0x180014b41  mov     ecx, 8
0x180014b46  call    LDAPClientPrint
0x180014b4b  jmp     loc_18001487B
```
