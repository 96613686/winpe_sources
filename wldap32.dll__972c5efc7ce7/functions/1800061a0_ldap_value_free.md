# ldap_value_free

- ea: `0x1800061a0`
- end: `0x180006502`
- name: `ldap_value_free`
- size: `866`
- prototype: `ULONG __cdecl(PCHAR *vals)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018d0`
- `0x180005790`
- `0x1800057a0`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18001ba9c`
- `0x18002c04c`
- `0x1800412d0`
- `0x180041390`
- `0x180045de8`

## callees

- `0x1800037a8`
- `0x1800061a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000626f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000626f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062f0`

## string_xrefs

- `0x1800063ae`: `Freeing memory at 0x%x which is already freed\n`
- `0x18000646d`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
ULONG __cdecl ldap_value_free(PCHAR *vals)
{
  __int64 v2; // rbx
  PCHAR v3; // rbp
  PCHAR *v4; // rsi
  int v5; // eax
  int v6; // r9d
  int v7; // r8d
  int v8; // eax
  HANDLE v9; // rcx
  int v11; // eax
  int v12; // r9d
  int v13; // r8d
  int v14; // eax
  HANDLE v15; // rcx

  if ( vals )
  {
    LODWORD(v2) = 0;
    if ( *vals )
    {
      while ( 1 )
      {
        v3 = vals[(unsigned int)v2];
        v4 = &vals[(unsigned int)v2];
        if ( v3 )
        {
          v11 = *((_DWORD *)v3 - 2);
          if ( v11 != 1684095564 )
            break;
        }
LABEL_4:
        v2 = (unsigned int)(v2 + 1);
        *v4 = 0;
        if ( !vals[v2] )
          goto LABEL_5;
      }
      if ( v11 == 1701987916 )
      {
        if ( !g_fTracingOn )
        {
LABEL_15:
          v12 = *((_DWORD *)v3 - 2);
          if ( v12 != 1818318412 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1818318412, v12);
          v13 = *((_DWORD *)v3 - 1);
          v14 = LdapAllocatedHeap - v13;
          LdapAllocatedHeap -= v13;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(
              8,
              "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
              v13,
              (_DWORD)v3,
              1818318412,
              v14);
          v15 = LdapHeap;
          *((_DWORD *)v3 - 2) = 1701987916;
          HeapFree(v15, 0, v3 - 8);
          goto LABEL_4;
        }
        if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (unsigned int)vals[(unsigned int)v2]);
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
          *((_DWORD *)v3 - 1),
          (_DWORD)v3 - 8,
          1818318412);
      goto LABEL_15;
    }
LABEL_5:
    v5 = *((_DWORD *)vals - 2);
    if ( v5 == 1684095564 )
      return 0;
    if ( v5 == 1701987916 )
    {
      if ( !g_fTracingOn )
      {
LABEL_8:
        v6 = *((_DWORD *)vals - 2);
        if ( v6 != 1819039308 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1819039308, v6);
        v7 = *((_DWORD *)vals - 1);
        v8 = LdapAllocatedHeap - v7;
        LdapAllocatedHeap -= v7;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(
            8,
            "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
            v7,
            (_DWORD)vals,
            1819039308,
            v8);
        v9 = LdapHeap;
        *((_DWORD *)vals - 2) = 1701987916;
        HeapFree(v9, 0, vals - 1);
        return 0;
      }
      if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)vals);
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
        *((_DWORD *)vals - 1),
        (_DWORD)vals - 8,
        1819039308);
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x1800061a0  push    rdi; ldap_value_free
0x1800061a2  sub     rsp, 40h
0x1800061a6  mov     rdi, rcx
0x1800061a9  test    rcx, rcx
0x1800061ac  jz      loc_180006301
0x1800061b2  mov     [rsp+48h+arg_0], rbx
0x1800061b7  mov     [rsp+48h+var_18], r15
0x1800061bc  xor     r15d, r15d
0x1800061bf  mov     ebx, r15d
0x1800061c2  cmp     [rcx], rbx
0x1800061c5  jz      short loc_180006203
0x1800061c7  mov     [rsp+48h+arg_8], rbp
0x1800061cc  mov     [rsp+48h+arg_10], rsi
0x1800061d1  mov     [rsp+48h+var_10], r14
0x1800061d6  mov     eax, ebx
0x1800061d8  mov     rbp, [rdi+rax*8]
0x1800061dc  lea     rsi, [rdi+rax*8]
0x1800061e0  test    rbp, rbp
0x1800061e3  jnz     loc_180006289
0x1800061e9  inc     ebx
0x1800061eb  mov     [rsi], r15
0x1800061ee  cmp     [rdi+rbx*8], r15
0x1800061f2  jnz     short loc_1800061D6
0x1800061f4  mov     r14, [rsp+48h+var_10]
0x1800061f9  mov     rsi, [rsp+48h+arg_10]
0x1800061fe  mov     rbp, [rsp+48h+arg_8]
0x180006203  mov     eax, [rdi-8]
0x180006206  mov     r15, [rsp+48h+var_18]
0x18000620b  cmp     eax, 6461424Ch
0x180006210  jz      short loc_18000627B
0x180006212  cmp     eax, 6572464Ch
0x180006217  jz      loc_180006443
0x18000621d  cmp     cs:g_fTracingOn, 0
0x180006224  jnz     loc_180006483
0x18000622a  mov     r9d, [rdi-8]
0x18000622e  cmp     r9d, 6C6C564Ch
0x180006235  jnz     loc_180006341
0x18000623b  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180006241  mov     r8d, [rdi-4]
0x180006245  sub     eax, r8d
0x180006248  cmp     cs:g_fTracingOn, 0
0x18000624f  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180006255  jnz     loc_1800064C3
0x18000625b  mov     rcx, cs:LdapHeap; hHeap
0x180006262  lea     r8, [rdi-8]; lpMem
0x180006266  xor     edx, edx; dwFlags
0x180006268  mov     dword ptr [rdi-8], 6572464Ch
0x18000626f  call    cs:__imp_HeapFree
0x180006276  nop     dword ptr [rax+rax+00h]
0x18000627b  mov     rbx, [rsp+48h+arg_0]
0x180006280  xor     eax, eax
0x180006282  add     rsp, 40h
0x180006286  pop     rdi
0x180006287  retn
0x180006289  mov     eax, [rbp-8]
0x18000628c  cmp     eax, 6461424Ch
0x180006291  jz      loc_1800061E9
0x180006297  cmp     eax, 6572464Ch
0x18000629c  jz      loc_180006384
0x1800062a2  cmp     cs:g_fTracingOn, r15d
0x1800062a9  jnz     loc_1800063C4
0x1800062af  mov     r9d, [rbp-8]
0x1800062b3  cmp     r9d, 6C61564Ch
0x1800062ba  jnz     short loc_18000630A
0x1800062bc  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x1800062c2  mov     r8d, [rbp-4]
0x1800062c6  sub     eax, r8d
0x1800062c9  cmp     cs:g_fTracingOn, r15d
0x1800062d0  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x1800062d6  jnz     loc_180006404
0x1800062dc  mov     rcx, cs:LdapHeap; hHeap
0x1800062e3  lea     r8, [rbp-8]; lpMem
0x1800062e7  xor     edx, edx; dwFlags
0x1800062e9  mov     dword ptr [rbp-8], 6572464Ch
0x1800062f0  call    cs:__imp_HeapFree
0x1800062f7  nop     dword ptr [rax+rax+00h]
0x1800062fc  jmp     loc_1800061E9
0x180006301  xor     eax, eax
0x180006303  add     rsp, 40h
0x180006307  pop     rdi
0x180006308  retn
0x18000630a  cmp     cs:g_fTracingOn, r15d
0x180006311  jz      short loc_1800062BC
0x180006313  cmp     cs:g_fProviderEnabled, r15d
0x18000631a  jz      short loc_1800062BC
0x18000631c  test    byte ptr cs:g_ulTraceFlags, 8
0x180006323  jz      short loc_1800062BC
0x180006325  mov     r8d, 6C61564Ch
0x18000632b  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x180006332  mov     ecx, 8
0x180006337  call    LDAPClientPrint
0x18000633c  jmp     loc_1800062BC
0x180006341  cmp     cs:g_fTracingOn, 0
0x180006348  jz      loc_18000623B
0x18000634e  cmp     cs:g_fProviderEnabled, 0
0x180006355  jz      loc_18000623B
0x18000635b  test    byte ptr cs:g_ulTraceFlags, 8
0x180006362  jz      loc_18000623B
0x180006368  mov     r8d, 6C6C564Ch
0x18000636e  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x180006375  mov     ecx, 8
0x18000637a  call    LDAPClientPrint
0x18000637f  jmp     loc_18000623B
0x180006384  cmp     cs:g_fTracingOn, r15d
0x18000638b  jz      loc_1800062AF
0x180006391  cmp     cs:g_fProviderEnabled, r15d
0x180006398  jz      loc_1800062A2
0x18000639e  test    byte ptr cs:g_ulTraceFlags, 8
0x1800063a5  jz      loc_1800062A2
0x1800063ab  mov     r8, rbp
0x1800063ae  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x1800063b5  mov     ecx, 8
0x1800063ba  call    LDAPClientPrint
0x1800063bf  jmp     loc_1800062A2
0x1800063c4  cmp     cs:g_fProviderEnabled, r15d
0x1800063cb  jz      loc_1800062AF
0x1800063d1  test    byte ptr cs:g_ulTraceFlags, 8
0x1800063d8  jz      loc_1800062AF
0x1800063de  mov     r8d, [rbp-4]
0x1800063e2  lea     r9, [rbp-8]
0x1800063e6  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x1800063ed  mov     [rsp+48h+var_28], 6C61564Ch
0x1800063f5  mov     ecx, 8
0x1800063fa  call    LDAPClientPrint
0x1800063ff  jmp     loc_1800062AF
0x180006404  cmp     cs:g_fProviderEnabled, r15d
0x18000640b  jz      loc_1800062DC
0x180006411  test    byte ptr cs:g_ulTraceFlags, 8
0x180006418  jz      loc_1800062DC
0x18000641e  mov     [rsp+48h+var_20], eax
0x180006422  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x180006429  mov     r9, rbp
0x18000642c  mov     [rsp+48h+var_28], 6C61564Ch
0x180006434  mov     ecx, 8
0x180006439  call    LDAPClientPrint
0x18000643e  jmp     loc_1800062DC
0x180006443  cmp     cs:g_fTracingOn, 0
0x18000644a  jz      loc_18000622A
0x180006450  cmp     cs:g_fProviderEnabled, 0
0x180006457  jz      loc_18000621D
0x18000645d  test    byte ptr cs:g_ulTraceFlags, 8
0x180006464  jz      loc_18000621D
0x18000646a  mov     r8, rdi
0x18000646d  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x180006474  mov     ecx, 8
0x180006479  call    LDAPClientPrint
0x18000647e  jmp     loc_18000621D
0x180006483  cmp     cs:g_fProviderEnabled, 0
0x18000648a  jz      loc_18000622A
0x180006490  test    byte ptr cs:g_ulTraceFlags, 8
0x180006497  jz      loc_18000622A
0x18000649d  mov     r8d, [rdi-4]
0x1800064a1  lea     r9, [rdi-8]
0x1800064a5  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x1800064ac  mov     [rsp+48h+var_28], 6C6C564Ch
0x1800064b4  mov     ecx, 8
0x1800064b9  call    LDAPClientPrint
0x1800064be  jmp     loc_18000622A
0x1800064c3  cmp     cs:g_fProviderEnabled, 0
0x1800064ca  jz      loc_18000625B
0x1800064d0  test    byte ptr cs:g_ulTraceFlags, 8
0x1800064d7  jz      loc_18000625B
0x1800064dd  mov     [rsp+48h+var_20], eax
0x1800064e1  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x1800064e8  mov     r9, rdi
0x1800064eb  mov     [rsp+48h+var_28], 6C6C564Ch
0x1800064f3  mov     ecx, 8
0x1800064f8  call    LDAPClientPrint
0x1800064fd  jmp     loc_18000625B
```
