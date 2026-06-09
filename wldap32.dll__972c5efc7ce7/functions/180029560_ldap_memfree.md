# ldap_memfree

- ea: `0x180029560`
- end: `0x180029704`
- name: `ldap_memfree`
- size: `420`
- prototype: `void __cdecl(PCHAR Block)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e60`
- `0x18000adb0`
- `0x18001e6c4`
- `0x18002c04c`
- `0x180032660`
- `0x180045de8`

## callees

- `0x1800037a8`
- `0x180029560`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800295ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800295ec`

## string_xrefs

- `0x18002967e`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
void __cdecl ldap_memfree(PCHAR Block)
{
  PCHAR v1; // rdi
  int v2; // ebx
  int v3; // esi
  int v4; // r8d
  int v5; // eax
  HANDLE v6; // rcx

  if ( !Block )
    return;
  v1 = Block - 8;
  v2 = 1849968460;
  v3 = (int)Block;
  if ( *((_DWORD *)Block - 2) == 1849968460 )
    goto LABEL_6;
  v2 = 1818318412;
  if ( *(_DWORD *)v1 == 1818318412 )
    goto LABEL_6;
  v2 = 1920091468;
  if ( *(_DWORD *)v1 == 1920091468 )
    goto LABEL_6;
  v2 = 1953383244;
  if ( *(_DWORD *)v1 == 1953383244 )
    goto LABEL_6;
  if ( *(_DWORD *)v1 == 1684095564 )
    return;
  v2 = 1718960716;
  if ( *(_DWORD *)v1 != 1701987916 )
    goto LABEL_6;
  if ( g_fTracingOn )
  {
    if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)Block);
LABEL_6:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
        *((_DWORD *)v1 + 1),
        (_DWORD)v1,
        v2);
  }
  if ( *(_DWORD *)v1 != v2 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", v2, *(_DWORD *)v1);
  v4 = *((_DWORD *)v1 + 1);
  v5 = LdapAllocatedHeap - v4;
  LdapAllocatedHeap -= v4;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", v4, v3, v2, v5);
  v6 = LdapHeap;
  *(_DWORD *)v1 = 1701987916;
  HeapFree(v6, 0, v1);
}

```

## disassembly

```asm
0x180029560  test    rcx, rcx; ldap_memfreeA
0x180029563  jz      locret_180029603
0x180029569  push    rbx
0x18002956a  push    rsi
0x18002956b  push    rdi
0x18002956c  push    r14
0x18002956e  push    r15
0x180029570  sub     rsp, 30h
0x180029574  lea     rdi, [rcx-8]
0x180029578  mov     ebx, 6E44474Ch
0x18002957d  mov     rsi, rcx
0x180029580  mov     r15d, 8
0x180029586  cmp     [rdi], ebx
0x180029588  jz      short loc_1800295A9
0x18002958a  mov     ebx, 6C61564Ch
0x18002958f  cmp     [rdi], ebx
0x180029591  jz      short loc_1800295A9
0x180029593  mov     ebx, 7272454Ch
0x180029598  cmp     [rdi], ebx
0x18002959a  jz      short loc_1800295A9
0x18002959c  mov     ebx, 746E434Ch
0x1800295a1  cmp     [rdi], ebx
0x1800295a3  jnz     loc_180029637
0x1800295a9  cmp     cs:g_fTracingOn, 0
0x1800295b0  jnz     loc_180029692
0x1800295b6  cmp     [rdi], ebx
0x1800295b8  jnz     short loc_180029605
0x1800295ba  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x1800295c0  mov     r8d, [rdi+4]
0x1800295c4  sub     eax, r8d
0x1800295c7  cmp     cs:g_fTracingOn, 0
0x1800295ce  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x1800295d4  jnz     loc_1800296CB
0x1800295da  mov     rcx, cs:LdapHeap; hHeap
0x1800295e1  mov     r8, rdi; lpMem
0x1800295e4  xor     edx, edx; dwFlags
0x1800295e6  mov     dword ptr [rdi], 6572464Ch
0x1800295ec  call    cs:__imp_HeapFree
0x1800295f3  nop     dword ptr [rax+rax+00h]
0x1800295f8  add     rsp, 30h
0x1800295fc  pop     r15
0x1800295fe  pop     r14
0x180029600  pop     rdi
0x180029601  pop     rsi
0x180029602  pop     rbx
0x180029603  retn
0x180029605  cmp     cs:g_fTracingOn, 0
0x18002960c  jz      short loc_1800295BA
0x18002960e  cmp     cs:g_fProviderEnabled, 0
0x180029615  jz      short loc_1800295BA
0x180029617  test    byte ptr cs:g_ulTraceFlags, r15b
0x18002961e  jz      short loc_1800295BA
0x180029620  mov     r9d, [rdi]
0x180029623  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x18002962a  mov     r8d, ebx
0x18002962d  mov     ecx, r15d
0x180029630  call    LDAPClientPrint
0x180029635  jmp     short loc_1800295BA
0x180029637  cmp     dword ptr [rdi], 6461424Ch
0x18002963d  jz      short loc_1800295F8
0x18002963f  cmp     dword ptr [rdi], 6572464Ch
0x180029645  mov     r14d, 6675424Ch
0x18002964b  mov     ebx, r14d
0x18002964e  jnz     loc_1800295A9
0x180029654  cmp     cs:g_fTracingOn, 0
0x18002965b  jz      loc_1800295B6
0x180029661  cmp     cs:g_fProviderEnabled, 0
0x180029668  jz      loc_1800295A9
0x18002966e  test    byte ptr cs:g_ulTraceFlags, r15b
0x180029675  jz      loc_1800295A9
0x18002967b  mov     r8, rsi
0x18002967e  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x180029685  mov     ecx, r15d
0x180029688  call    LDAPClientPrint
0x18002968d  jmp     loc_1800295A9
0x180029692  cmp     cs:g_fProviderEnabled, 0
0x180029699  jz      loc_1800295B6
0x18002969f  test    byte ptr cs:g_ulTraceFlags, r15b
0x1800296a6  jz      loc_1800295B6
0x1800296ac  mov     r8d, [rdi+4]
0x1800296b0  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x1800296b7  mov     r9, rdi
0x1800296ba  mov     [rsp+58h+var_38], ebx
0x1800296be  mov     ecx, r15d
0x1800296c1  call    LDAPClientPrint
0x1800296c6  jmp     loc_1800295B6
0x1800296cb  cmp     cs:g_fProviderEnabled, 0
0x1800296d2  jz      loc_1800295DA
0x1800296d8  test    byte ptr cs:g_ulTraceFlags, r15b
0x1800296df  jz      loc_1800295DA
0x1800296e5  mov     [rsp+58h+var_30], eax
0x1800296e9  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x1800296f0  mov     r9, rsi
0x1800296f3  mov     [rsp+58h+var_38], ebx
0x1800296f7  mov     ecx, r15d
0x1800296fa  call    LDAPClientPrint
0x1800296ff  jmp     loc_1800295DA
```
