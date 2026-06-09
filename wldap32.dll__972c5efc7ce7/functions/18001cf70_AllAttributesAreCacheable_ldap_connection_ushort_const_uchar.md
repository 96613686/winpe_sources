# AllAttributesAreCacheable(ldap_connection *,ushort * * const,uchar)

- ea: `0x18001cf70`
- end: `0x18001d462`
- name: `?AllAttributesAreCacheable@@YAKPEAUldap_connection@@QEAPEAGE@Z`
- size: `1266`
- prototype: `unsigned int __fastcall(struct ldap_connection *, unsigned __int16 **const, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001af54`

## callees

- `0x1800037a8`
- `0x18001cf70`
- `0x18001e7b0`
- `0x18001ffa0`
- `0x180032bd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d0e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d0e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d1d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d278`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d1d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d278`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d0ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d0ce`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cff3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d159`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cff3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d159`

## string_xrefs

- `0x18001d2c2`: `Yes, '%S' is a cacheable attribute\n`
- `0x18001d050`: `Sorry, atleast one attribute is not cacheable\n`
- `0x18001d3b4`: `Comparing current server '%S' with cached server '%S'\n`
- `0x18001d3e8`: `AllAttributesAreCacheable: Returning CACHE HIT..\n`
- `0x18001d422`: `AllAttributesAreCacheable: Returning STALE CACHE..\n`
- `0x18001d44f`: `AllAttributesAreCacheable: Returning SERVER NOT CACHED!..\n`
- `0x18001d302`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
__int64 __fastcall AllAttributesAreCacheable(const wchar_t **a1, LPCCH *a2, char a3)
{
  LPCCH *v4; // rsi
  PCNZWCH *v6; // r14
  unsigned int v7; // ebp
  LPCCH v8; // r8
  __int64 result; // rax
  int i; // ebx
  __int64 v11; // rdi
  struct _CACHEHOLDER * near *v12; // r9
  const WCHAR *v13; // r8
  const WCHAR *lpString2; // rcx
  bool v15; // zf
  struct _CACHEHOLDER *v16; // rbx
  LPCCH v17; // r8

  v4 = a2;
  if ( !a2 )
    return 3;
  v6 = (PCNZWCH *)&off_180065000;
  v7 = 1;
  while ( *v4 )
  {
    if ( !a3 )
    {
      result = ToUnicodeWithAlloc(*v4, 1);
      if ( (_DWORD)result )
        return result;
    }
    while ( *v6 )
    {
      if ( a3 )
        v8 = *v4;
      else
        v8 = 0;
      if ( v8 && CompareStringW(0x400u, 1u, (PCNZWCH)v8, -1, *v6, -1) == 2 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
        {
          if ( a3 )
            v17 = *v4;
          else
            v17 = 0;
          LDAPClientPrint(16, "Yes, '%S' is a cacheable attribute\n", (const wchar_t *)v17);
        }
        v6 = (PCNZWCH *)&off_180065000;
        ++v4;
        break;
      }
      ++v6;
    }
    if ( !*v6 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
        LDAPClientTraceEvent(16, "Sorry, atleast one attribute is not cacheable\n");
      return 3;
    }
  }
  EnterCriticalSection(&CacheLock);
  for ( i = 0; i < 5; ++i )
  {
    v11 = i;
    v12 = (&CacheArray)[i];
    if ( !v12 )
      continue;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
      LDAPClientPrint(16, "Comparing current server '%S' with cached server '%S'\n", a1[52], (const wchar_t *)v12[1]);
    v13 = a1[52];
    lpString2 = (const WCHAR *)(&CacheArray)[i][1];
    if ( v13 )
    {
      if ( !lpString2 )
        continue;
      v15 = CompareStringW(0x400u, 1u, v13, -1, lpString2, -1) == 2;
    }
    else
    {
      v15 = lpString2 == 0;
    }
    if ( v15 && *((_WORD *)(&CacheArray)[i] + 8) == *((_WORD *)a1 + 253) )
    {
      _mm_lfence();
      v16 = (&CacheArray)[i][3];
      if ( (unsigned __int64)(LdapGetTickCount() - (_QWORD)v16) >= 0xDBBA0 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
          LDAPClientTraceEvent(16, "AllAttributesAreCacheable: Returning STALE CACHE..\n");
      }
      else
      {
        _mm_lfence();
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
          LDAPClientTraceEvent(16, "AllAttributesAreCacheable: Returning CACHE HIT..\n");
        ++*(_DWORD *)(&CacheArray)[v11];
        v7 = 0;
        (&CacheArray)[v11][4] = (struct _CACHEHOLDER *)LdapGetTickCount();
      }
      LeaveCriticalSection(&CacheLock);
      return v7;
    }
  }
  LeaveCriticalSection(&CacheLock);
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
    LDAPClientTraceEvent(16, "AllAttributesAreCacheable: Returning SERVER NOT CACHED!..\n");
  return 2;
}

```

## disassembly

```asm
0x18001cf70  push    rbx
0x18001cf72  push    rbp
0x18001cf73  push    rsi
0x18001cf74  push    rdi
0x18001cf75  push    r12
0x18001cf77  push    r13
0x18001cf79  push    r14
0x18001cf7b  push    r15
0x18001cf7d  sub     rsp, 38h
0x18001cf81  xor     r12d, r12d
0x18001cf84  mov     r15b, r8b
0x18001cf87  mov     rsi, rdx
0x18001cf8a  mov     r13, rcx
0x18001cf8d  test    rdx, rdx
0x18001cf90  jz      loc_18001D061
0x18001cf96  lea     r14, off_180065000; "subschemaSubentry"
0x18001cf9d  lea     ebp, [r12+1]
0x18001cfa2  mov     rcx, [rsi]; lpMultiByteStr
0x18001cfa5  test    rcx, rcx
0x18001cfa8  jz      loc_18001D0DF
0x18001cfae  mov     [rsp+78h+arg_8], r12
0x18001cfb6  mov     rdi, r12
0x18001cfb9  test    r15b, r15b
0x18001cfbc  jz      loc_18001D246
0x18001cfc2  mov     rax, [r14]
0x18001cfc5  test    rax, rax
0x18001cfc8  jz      short loc_18001D027
0x18001cfca  test    r15b, r15b
0x18001cfcd  jz      loc_18001D1F0
0x18001cfd3  mov     r8, [rsi]; lpString1
0x18001cfd6  test    r8, r8
0x18001cfd9  jz      short loc_18001D009
0x18001cfdb  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001cfe3  or      r9d, 0FFFFFFFFh; cchCount1
0x18001cfe7  mov     edx, ebp; dwCmpFlags
0x18001cfe9  mov     [rsp+78h+lpString2], rax; lpString2
0x18001cfee  mov     ecx, 400h; Locale
0x18001cff3  call    cs:__imp_CompareStringW
0x18001cffa  nop     dword ptr [rax+rax+00h]
0x18001cfff  cmp     eax, 2
0x18001d002  setz    al
0x18001d005  test    al, al
0x18001d007  jnz     short loc_18001D00F
0x18001d009  add     r14, 8
0x18001d00d  jmp     short loc_18001CFC2
0x18001d00f  cmp     cs:g_fTracingOn, r12d
0x18001d016  jnz     loc_18001D29B
0x18001d01c  lea     r14, off_180065000; "subschemaSubentry"
0x18001d023  add     rsi, 8
0x18001d027  test    rdi, rdi
0x18001d02a  jnz     short loc_18001D06B
0x18001d02c  cmp     [r14], r12
0x18001d02f  jnz     loc_18001CFA2
0x18001d035  cmp     cs:g_fTracingOn, r12d
0x18001d03c  jz      short loc_18001D061
0x18001d03e  cmp     cs:g_fProviderEnabled, r12d
0x18001d045  jz      short loc_18001D061
0x18001d047  test    byte ptr cs:g_ulTraceFlags, 10h
0x18001d04e  jz      short loc_18001D061
0x18001d050  lea     rdx, aSorryAtleastOn; "Sorry, atleast one attribute is not cac"...
0x18001d057  mov     ecx, 10h
0x18001d05c  call    LDAPClientTraceEvent
0x18001d061  mov     eax, 3
0x18001d066  jmp     loc_18001D1DE
0x18001d06b  lea     rbx, [rdi-8]
0x18001d06f  cmp     dword ptr [rbx], 6461424Ch
0x18001d075  jz      short loc_18001D02C
0x18001d077  cmp     dword ptr [rbx], 6572464Ch
0x18001d07d  jz      loc_18001D2D8
0x18001d083  cmp     cs:g_fTracingOn, r12d
0x18001d08a  jnz     loc_18001D318
0x18001d090  cmp     dword ptr [rbx], 696E554Ch
0x18001d096  jnz     loc_18001D200
0x18001d09c  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001d0a2  mov     r8d, [rbx+4]
0x18001d0a6  sub     eax, r8d
0x18001d0a9  cmp     cs:g_fTracingOn, r12d
0x18001d0b0  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001d0b6  jnz     loc_18001D357
0x18001d0bc  mov     rcx, cs:LdapHeap; hHeap
0x18001d0c3  mov     r8, rbx; lpMem
0x18001d0c6  xor     edx, edx; dwFlags
0x18001d0c8  mov     dword ptr [rbx], 6572464Ch
0x18001d0ce  call    cs:__imp_HeapFree
0x18001d0d5  nop     dword ptr [rax+rax+00h]
0x18001d0da  jmp     loc_18001D02C
0x18001d0df  lea     r15, CacheLock
0x18001d0e6  mov     rcx, r15; lpCriticalSection
0x18001d0e9  call    cs:__imp_EnterCriticalSection
0x18001d0f0  nop     dword ptr [rax+rax+00h]
0x18001d0f5  mov     ebx, r12d
0x18001d0f8  mov     esi, 10h
0x18001d0fd  cmp     ebx, 5
0x18001d100  jge     loc_18001D275
0x18001d106  movsxd  rdi, ebx
0x18001d109  lea     r14, ?CacheArray@@3PAPEAU_CACHEHOLDER@@A; _CACHEHOLDER * near * CacheArray
0x18001d110  mov     r9, [r14+rdi*8]
0x18001d114  test    r9, r9
0x18001d117  jz      short loc_18001D16F
0x18001d119  cmp     cs:g_fTracingOn, r12d
0x18001d120  jnz     loc_18001D396
0x18001d126  mov     rax, [r14+rdi*8]
0x18001d12a  mov     r8, [r13+1A0h]; lpString1
0x18001d131  mov     rcx, [rax+8]
0x18001d135  test    r8, r8
0x18001d138  jz      loc_18001D1F8
0x18001d13e  test    rcx, rcx
0x18001d141  jz      short loc_18001D16F
0x18001d143  or      eax, 0FFFFFFFFh
0x18001d146  mov     edx, ebp; dwCmpFlags
0x18001d148  mov     [rsp+78h+cchCount2], eax; cchCount2
0x18001d14c  mov     r9d, eax; cchCount1
0x18001d14f  mov     [rsp+78h+lpString2], rcx; lpString2
0x18001d154  mov     ecx, 400h; Locale
0x18001d159  call    cs:__imp_CompareStringW
0x18001d160  nop     dword ptr [rax+rax+00h]
0x18001d165  cmp     eax, 2
0x18001d168  setz    al
0x18001d16b  test    al, al
0x18001d16d  jnz     short loc_18001D173
0x18001d16f  add     ebx, ebp
0x18001d171  jmp     short loc_18001D0FD
0x18001d173  mov     rcx, [r14+rdi*8]
0x18001d177  movzx   eax, word ptr [r13+1FAh]
0x18001d17f  cmp     [rcx+10h], ax
0x18001d183  jnz     short loc_18001D16F
0x18001d185  lfence
0x18001d188  mov     rax, [r14+rdi*8]
0x18001d18c  mov     rbx, [rax+18h]
0x18001d190  call    LdapGetTickCount
0x18001d195  sub     rax, rbx
0x18001d198  cmp     rax, 0DBBA0h
0x18001d19e  jnb     loc_18001D3FB
0x18001d1a4  lfence
0x18001d1a7  cmp     cs:g_fTracingOn, r12d
0x18001d1ae  jnz     loc_18001D3CE
0x18001d1b4  mov     rax, [r14+rdi*8]
0x18001d1b8  add     [rax], ebp
0x18001d1ba  call    LdapGetTickCount
0x18001d1bf  mov     rcx, rax
0x18001d1c2  mov     ebp, r12d
0x18001d1c5  mov     rax, [r14+rdi*8]
0x18001d1c9  mov     [rax+20h], rcx
0x18001d1cd  mov     rcx, r15; lpCriticalSection
0x18001d1d0  call    cs:__imp_LeaveCriticalSection
0x18001d1d7  nop     dword ptr [rax+rax+00h]
0x18001d1dc  mov     eax, ebp
0x18001d1de  add     rsp, 38h
0x18001d1e2  pop     r15
0x18001d1e4  pop     r14
0x18001d1e6  pop     r13
0x18001d1e8  pop     r12
0x18001d1ea  pop     rdi
0x18001d1eb  pop     rsi
0x18001d1ec  pop     rbp
0x18001d1ed  pop     rbx
0x18001d1ee  retn
0x18001d1f0  mov     r8, rdi
0x18001d1f3  jmp     loc_18001CFD6
0x18001d1f8  test    rcx, rcx
0x18001d1fb  jmp     loc_18001D168
0x18001d200  cmp     cs:g_fTracingOn, r12d
0x18001d207  jz      loc_18001D09C
0x18001d20d  cmp     cs:g_fProviderEnabled, r12d
0x18001d214  jz      loc_18001D09C
0x18001d21a  test    byte ptr cs:g_ulTraceFlags, 8
0x18001d221  jz      loc_18001D09C
0x18001d227  mov     r9d, [rbx]
0x18001d22a  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x18001d231  mov     r8d, 696E554Ch
0x18001d237  mov     ecx, 8
0x18001d23c  call    LDAPClientPrint
0x18001d241  jmp     loc_18001D09C
0x18001d246  mov     r9d, 696E554Ch
0x18001d24c  mov     dword ptr [rsp+78h+lpString2], ebp; int
0x18001d250  lea     r8, [rsp+78h+arg_8]
0x18001d258  or      edx, 0FFFFFFFFh
0x18001d25b  call    ToUnicodeWithAlloc
0x18001d260  test    eax, eax
0x18001d262  jnz     loc_18001D1DE
0x18001d268  mov     rdi, [rsp+78h+arg_8]
0x18001d270  jmp     loc_18001CFC2
0x18001d275  mov     rcx, r15; lpCriticalSection
0x18001d278  call    cs:__imp_LeaveCriticalSection
0x18001d27f  nop     dword ptr [rax+rax+00h]
0x18001d284  cmp     cs:g_fTracingOn, r12d
0x18001d28b  jnz     loc_18001D435
0x18001d291  mov     eax, 2
0x18001d296  jmp     loc_18001D1DE
0x18001d29b  cmp     cs:g_fProviderEnabled, r12d
0x18001d2a2  jz      loc_18001D01C
0x18001d2a8  test    byte ptr cs:g_ulTraceFlags, 10h
0x18001d2af  jz      loc_18001D01C
0x18001d2b5  test    r15b, r15b
0x18001d2b8  jz      short loc_18001D2BF
0x18001d2ba  mov     r8, [rsi]
0x18001d2bd  jmp     short loc_18001D2C2
0x18001d2bf  mov     r8, rdi
0x18001d2c2  lea     rdx, aYesSIsACacheab; "Yes, '%S' is a cacheable attribute\n"
0x18001d2c9  mov     ecx, 10h
0x18001d2ce  call    LDAPClientPrint
0x18001d2d3  jmp     loc_18001D01C
0x18001d2d8  cmp     cs:g_fTracingOn, r12d
0x18001d2df  jz      loc_18001D090
0x18001d2e5  cmp     cs:g_fProviderEnabled, r12d
0x18001d2ec  jz      loc_18001D083
0x18001d2f2  test    byte ptr cs:g_ulTraceFlags, 8
0x18001d2f9  jz      loc_18001D083
0x18001d2ff  mov     r8, rdi
0x18001d302  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x18001d309  mov     ecx, 8
0x18001d30e  call    LDAPClientPrint
0x18001d313  jmp     loc_18001D083
0x18001d318  cmp     cs:g_fProviderEnabled, r12d
0x18001d31f  jz      loc_18001D090
0x18001d325  test    byte ptr cs:g_ulTraceFlags, 8
0x18001d32c  jz      loc_18001D090
0x18001d332  mov     r8d, [rbx+4]
0x18001d336  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x18001d33d  mov     r9, rbx
0x18001d340  mov     dword ptr [rsp+78h+lpString2], 696E554Ch
0x18001d348  mov     ecx, 8
0x18001d34d  call    LDAPClientPrint
0x18001d352  jmp     loc_18001D090
0x18001d357  cmp     cs:g_fProviderEnabled, r12d
0x18001d35e  jz      loc_18001D0BC
0x18001d364  test    byte ptr cs:g_ulTraceFlags, 8
0x18001d36b  jz      loc_18001D0BC
0x18001d371  mov     [rsp+78h+cchCount2], eax
0x18001d375  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x18001d37c  mov     r9, rdi
0x18001d37f  mov     dword ptr [rsp+78h+lpString2], 696E554Ch
0x18001d387  mov     ecx, 8
0x18001d38c  call    LDAPClientPrint
0x18001d391  jmp     loc_18001D0BC
0x18001d396  cmp     cs:g_fProviderEnabled, r12d
0x18001d39d  jz      loc_18001D126
0x18001d3a3  test    byte ptr cs:g_ulTraceFlags, sil
0x18001d3aa  jz      loc_18001D126
0x18001d3b0  mov     r9, [r9+8]
0x18001d3b4  lea     rdx, aComparingCurre; "Comparing current server '%S' with cach"...
0x18001d3bb  mov     r8, [r13+1A0h]
0x18001d3c2  mov     ecx, esi
0x18001d3c4  call    LDAPClientPrint
0x18001d3c9  jmp     loc_18001D126
0x18001d3ce  cmp     cs:g_fProviderEnabled, r12d
0x18001d3d5  jz      loc_18001D1B4
0x18001d3db  test    byte ptr cs:g_ulTraceFlags, sil
0x18001d3e2  jz      loc_18001D1B4
0x18001d3e8  lea     rdx, aAllattributesa_1; "AllAttributesAreCacheable: Returning CA"...
0x18001d3ef  mov     ecx, esi
0x18001d3f1  call    LDAPClientTraceEvent
0x18001d3f6  jmp     loc_18001D1B4
0x18001d3fb  cmp     cs:g_fTracingOn, r12d
0x18001d402  jz      loc_18001D1CD
0x18001d408  cmp     cs:g_fProviderEnabled, r12d
0x18001d40f  jz      loc_18001D1CD
0x18001d415  test    byte ptr cs:g_ulTraceFlags, sil
0x18001d41c  jz      loc_18001D1CD
0x18001d422  lea     rdx, aAllattributesa; "AllAttributesAreCacheable: Returning ST"...
0x18001d429  mov     ecx, esi
0x18001d42b  call    LDAPClientTraceEvent
0x18001d430  jmp     loc_18001D1CD
0x18001d435  cmp     cs:g_fProviderEnabled, r12d
0x18001d43c  jz      loc_18001D291
0x18001d442  test    byte ptr cs:g_ulTraceFlags, sil
0x18001d449  jz      loc_18001D291
0x18001d44f  lea     rdx, aAllattributesa_0; "AllAttributesAreCacheable: Returning SE"...
0x18001d456  mov     ecx, esi
0x18001d458  call    LDAPClientTraceEvent
0x18001d45d  jmp     loc_18001D291
```
