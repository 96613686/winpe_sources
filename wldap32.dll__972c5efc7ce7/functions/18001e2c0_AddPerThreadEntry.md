# AddPerThreadEntry

- ea: `0x18001e2c0`
- end: `0x18001e663`
- name: `AddPerThreadEntry`
- size: `931`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180004740`
- `0x180004e60`
- `0x180005170`
- `0x18001ba9c`
- `0x180024df0`
- `0x18002abe0`

## callees

- `0x1800037a8`
- `0x18001e2c0`
- `0x18001e66c`
- `0x18001e6c4`
- `0x18001e7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e36b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e3e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e36b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e3e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e3ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e405`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e3ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e405`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e301`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e436`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e301`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e436`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e492`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001e492`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e2d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e2d7`

## string_xrefs

- `0x18001e5f8`: `Added thread data entry for thread 0x%0lx\n`
- `0x18001e637`: `Failed to allocate thread data entry for thread 0x%0lx\n`

## pseudocode

```c
__int64 __fastcall AddPerThreadEntry(int a1)
{
  _QWORD *Value; // rbx
  LPVOID v3; // rax
  int v4; // ecx
  __int64 v5; // rdi
  unsigned int v6; // eax
  __int64 v7; // rax
  bool v8; // zf
  _QWORD *v10; // rax
  int v11; // ecx
  unsigned int v12; // eax

  Value = TlsGetValue(GlobalTlsLastErrorIndex);
  if ( !Value )
  {
    v10 = HeapAlloc(LdapHeap, 8u, 0x18u);
    v11 = g_fTracingOn;
    Value = v10;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    {
      LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", 24, (_DWORD)v10, 1817471076);
      v11 = g_fTracingOn;
    }
    v12 = LdapAllocatedHeap;
    if ( Value )
    {
      *(_DWORD *)Value = 1817471076;
      *((_DWORD *)Value++ + 1) = 16;
      v12 += 16;
      LdapAllocatedHeap = v12;
    }
    if ( v11 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
        16,
        (_DWORD)Value,
        1817471076,
        v12);
    if ( !Value )
      goto LABEL_11;
    TlsSetValue(GlobalTlsLastErrorIndex, Value);
  }
  v3 = HeapAlloc(LdapHeap, 8u, 0x38u);
  v4 = g_fTracingOn;
  v5 = (__int64)v3;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
  {
    LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", 56, (_DWORD)v3, 1817471076);
    v4 = g_fTracingOn;
  }
  v6 = LdapAllocatedHeap;
  if ( v5 )
  {
    *(_DWORD *)v5 = 1817471076;
    *(_DWORD *)(v5 + 4) = 48;
    v5 += 8;
    v6 += 48;
    LdapAllocatedHeap = v6;
  }
  if ( v4 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
  {
    LDAPClientPrint(8, "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", 48, v5, 1817471076, v6);
    v4 = g_fTracingOn;
  }
  if ( v5 )
  {
    *(_DWORD *)(v5 + 16) = a1;
    *(_QWORD *)(v5 + 24) = 0;
    *(_QWORD *)(v5 + 32) = 0;
    *(_BYTE *)(v5 + 40) = 0;
    EnterCriticalSection(&PerThreadListLock);
    if ( (unsigned int)ShouldRemoveDeletedThreadEntries() )
    {
      RemovePerThreadEntries();
      LastPerThreadDataCleanup = LdapGetTickCount();
    }
    v7 = GlobalPerThreadList;
    *(_QWORD *)(v5 + 8) = &GlobalPerThreadList;
    *(_QWORD *)v5 = v7;
    *(_QWORD *)(v7 + 8) = v5;
    GlobalPerThreadList = v5;
    LeaveCriticalSection(&PerThreadListLock);
    v8 = g_fTracingOn == 0;
    Value[1] = v5;
    if ( !v8 && g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
      LDAPClientPrint(0x200000, "Added thread data entry for thread 0x%0lx\n", a1);
    return 1;
  }
  if ( v4 && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
    LDAPClientPrint(0x4000, "Failed to allocate thread data entry for thread 0x%0lx\n", a1);
LABEL_11:
  EnterCriticalSection(&PerThreadListLock);
  if ( (unsigned int)ShouldRemoveDeletedThreadEntries() )
  {
    RemovePerThreadEntries();
    LastPerThreadDataCleanup = LdapGetTickCount();
  }
  LeaveCriticalSection(&PerThreadListLock);
  return 0;
}

```

## disassembly

```asm
0x18001e2c0  mov     [rsp+arg_0], rbx
0x18001e2c5  mov     [rsp+arg_8], rsi
0x18001e2ca  push    rdi
0x18001e2cb  sub     rsp, 30h
0x18001e2cf  mov     esi, ecx
0x18001e2d1  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x18001e2d7  call    cs:__imp_TlsGetValue
0x18001e2de  nop     dword ptr [rax+rax+00h]
0x18001e2e3  mov     rbx, rax
0x18001e2e6  test    rax, rax
0x18001e2e9  jz      loc_18001E424
0x18001e2ef  mov     rcx, cs:LdapHeap; hHeap
0x18001e2f6  mov     edx, 8; dwFlags
0x18001e2fb  mov     r8d, 38h ; '8'; dwBytes
0x18001e301  call    cs:__imp_HeapAlloc
0x18001e308  nop     dword ptr [rax+rax+00h]
0x18001e30d  mov     ecx, cs:g_fTracingOn
0x18001e313  mov     rdi, rax
0x18001e316  test    ecx, ecx
0x18001e318  jnz     loc_18001E4B9
0x18001e31e  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001e324  test    rdi, rdi
0x18001e327  jz      short loc_18001E343
0x18001e329  mov     dword ptr [rdi], 6C546864h
0x18001e32f  mov     dword ptr [rdi+4], 30h ; '0'
0x18001e336  add     rdi, 8
0x18001e33a  add     eax, 30h ; '0'
0x18001e33d  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001e343  test    ecx, ecx
0x18001e345  jnz     loc_18001E58C
0x18001e34b  test    rdi, rdi
0x18001e34e  jz      loc_18001E60E
0x18001e354  xor     eax, eax
0x18001e356  mov     [rdi+10h], esi
0x18001e359  lea     rcx, PerThreadListLock; lpCriticalSection
0x18001e360  mov     [rdi+18h], rax
0x18001e364  mov     [rdi+20h], rax
0x18001e368  mov     [rdi+28h], al
0x18001e36b  call    cs:__imp_EnterCriticalSection
0x18001e372  nop     dword ptr [rax+rax+00h]
0x18001e377  call    ?ShouldRemoveDeletedThreadEntries@@YAHXZ; ShouldRemoveDeletedThreadEntries(void)
0x18001e37c  test    eax, eax
0x18001e37e  jnz     loc_18001E4A3
0x18001e384  mov     rax, cs:GlobalPerThreadList
0x18001e38b  lea     rcx, GlobalPerThreadList
0x18001e392  mov     [rdi+8], rcx
0x18001e396  lea     rcx, PerThreadListLock; lpCriticalSection
0x18001e39d  mov     [rdi], rax
0x18001e3a0  mov     [rax+8], rdi
0x18001e3a4  mov     cs:GlobalPerThreadList, rdi
0x18001e3ab  call    cs:__imp_LeaveCriticalSection
0x18001e3b2  nop     dword ptr [rax+rax+00h]
0x18001e3b7  cmp     cs:g_fTracingOn, 0
0x18001e3be  mov     [rbx+8], rdi
0x18001e3c2  jnz     loc_18001E5D7
0x18001e3c8  mov     eax, 1
0x18001e3cd  mov     rbx, [rsp+38h+arg_0]
0x18001e3d2  mov     rsi, [rsp+38h+arg_8]
0x18001e3d7  add     rsp, 30h
0x18001e3db  pop     rdi
0x18001e3dc  retn
0x18001e3de  lea     rcx, PerThreadListLock; lpCriticalSection
0x18001e3e5  call    cs:__imp_EnterCriticalSection
0x18001e3ec  nop     dword ptr [rax+rax+00h]
0x18001e3f1  call    ?ShouldRemoveDeletedThreadEntries@@YAHXZ; ShouldRemoveDeletedThreadEntries(void)
0x18001e3f6  test    eax, eax
0x18001e3f8  jnz     loc_18001E64D
0x18001e3fe  lea     rcx, PerThreadListLock; lpCriticalSection
0x18001e405  call    cs:__imp_LeaveCriticalSection
0x18001e40c  nop     dword ptr [rax+rax+00h]
0x18001e411  mov     rbx, [rsp+38h+arg_0]
0x18001e416  xor     eax, eax
0x18001e418  mov     rsi, [rsp+38h+arg_8]
0x18001e41d  add     rsp, 30h
0x18001e421  pop     rdi
0x18001e422  retn
0x18001e424  mov     rcx, cs:LdapHeap; hHeap
0x18001e42b  mov     edx, 8; dwFlags
0x18001e430  mov     r8d, 18h; dwBytes
0x18001e436  call    cs:__imp_HeapAlloc
0x18001e43d  nop     dword ptr [rax+rax+00h]
0x18001e442  mov     ecx, cs:g_fTracingOn
0x18001e448  mov     rbx, rax
0x18001e44b  test    ecx, ecx
0x18001e44d  jnz     loc_18001E500
0x18001e453  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001e459  test    rbx, rbx
0x18001e45c  jz      short loc_18001E478
0x18001e45e  mov     dword ptr [rbx], 6C546864h
0x18001e464  mov     dword ptr [rbx+4], 10h
0x18001e46b  add     rbx, 8
0x18001e46f  add     eax, 10h
0x18001e472  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001e478  test    ecx, ecx
0x18001e47a  jnz     loc_18001E547
0x18001e480  test    rbx, rbx
0x18001e483  jz      loc_18001E3DE
0x18001e489  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x18001e48f  mov     rdx, rbx; lpTlsValue
0x18001e492  call    cs:__imp_TlsSetValue
0x18001e499  nop     dword ptr [rax+rax+00h]
0x18001e49e  jmp     loc_18001E2EF
0x18001e4a3  call    RemovePerThreadEntries
0x18001e4a8  call    LdapGetTickCount
0x18001e4ad  mov     cs:?LastPerThreadDataCleanup@@3_KA, rax; unsigned __int64 LastPerThreadDataCleanup
0x18001e4b4  jmp     loc_18001E384
0x18001e4b9  cmp     cs:g_fProviderEnabled, 0
0x18001e4c0  jz      loc_18001E31E
0x18001e4c6  test    byte ptr cs:g_ulTraceFlags, 8
0x18001e4cd  jz      loc_18001E31E
0x18001e4d3  mov     r9, rdi
0x18001e4d6  mov     [rsp+38h+var_18], 6C546864h
0x18001e4de  mov     r8d, 38h ; '8'
0x18001e4e4  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x18001e4eb  mov     ecx, 8
0x18001e4f0  call    LDAPClientPrint
0x18001e4f5  mov     ecx, cs:g_fTracingOn
0x18001e4fb  jmp     loc_18001E31E
0x18001e500  cmp     cs:g_fProviderEnabled, 0
0x18001e507  jz      loc_18001E453
0x18001e50d  test    byte ptr cs:g_ulTraceFlags, 8
0x18001e514  jz      loc_18001E453
0x18001e51a  mov     r9, rbx
0x18001e51d  mov     [rsp+38h+var_18], 6C546864h
0x18001e525  mov     r8d, 18h
0x18001e52b  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x18001e532  mov     ecx, 8
0x18001e537  call    LDAPClientPrint
0x18001e53c  mov     ecx, cs:g_fTracingOn
0x18001e542  jmp     loc_18001E453
0x18001e547  cmp     cs:g_fProviderEnabled, 0
0x18001e54e  jz      loc_18001E480
0x18001e554  test    byte ptr cs:g_ulTraceFlags, 8
0x18001e55b  jz      loc_18001E480
0x18001e561  mov     [rsp+38h+var_10], eax
0x18001e565  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x18001e56c  mov     r9, rbx
0x18001e56f  mov     [rsp+38h+var_18], 6C546864h
0x18001e577  mov     r8d, 10h
0x18001e57d  mov     ecx, 8
0x18001e582  call    LDAPClientPrint
0x18001e587  jmp     loc_18001E480
0x18001e58c  cmp     cs:g_fProviderEnabled, 0
0x18001e593  jz      loc_18001E34B
0x18001e599  test    byte ptr cs:g_ulTraceFlags, 8
0x18001e5a0  jz      loc_18001E34B
0x18001e5a6  mov     [rsp+38h+var_10], eax
0x18001e5aa  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x18001e5b1  mov     r9, rdi
0x18001e5b4  mov     [rsp+38h+var_18], 6C546864h
0x18001e5bc  mov     r8d, 30h ; '0'
0x18001e5c2  mov     ecx, 8
0x18001e5c7  call    LDAPClientPrint
0x18001e5cc  mov     ecx, cs:g_fTracingOn
0x18001e5d2  jmp     loc_18001E34B
0x18001e5d7  cmp     cs:g_fProviderEnabled, 0
0x18001e5de  jz      loc_18001E3C8
0x18001e5e4  test    cs:g_ulTraceFlags, 200000h
0x18001e5ef  jz      loc_18001E3C8
0x18001e5f5  mov     r8d, esi
0x18001e5f8  lea     rdx, aAddedThreadDat; "Added thread data entry for thread 0x%0"...
0x18001e5ff  mov     ecx, 200000h
0x18001e604  call    LDAPClientPrint
0x18001e609  jmp     loc_18001E3C8
0x18001e60e  test    ecx, ecx
0x18001e610  jz      loc_18001E3DE
0x18001e616  cmp     cs:g_fProviderEnabled, 0
0x18001e61d  jz      loc_18001E3DE
0x18001e623  test    cs:g_ulTraceFlags, 4000h
0x18001e62e  jz      loc_18001E3DE
0x18001e634  mov     r8d, esi
0x18001e637  lea     rdx, aFailedToAlloca_0; "Failed to allocate thread data entry fo"...
0x18001e63e  mov     ecx, 4000h
0x18001e643  call    LDAPClientPrint
0x18001e648  jmp     loc_18001E3DE
0x18001e64d  call    RemovePerThreadEntries
0x18001e652  call    LdapGetTickCount
0x18001e657  mov     cs:?LastPerThreadDataCleanup@@3_KA, rax; unsigned __int64 LastPerThreadDataCleanup
0x18001e65e  jmp     loc_18001E3FE
```
