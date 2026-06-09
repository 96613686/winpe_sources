# LdapFreeMessageWaitStructure

- ea: `0x180027a30`
- end: `0x180027ce8`
- name: `LdapFreeMessageWaitStructure`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006d80`

## callees

- `0x1800037a8`
- `0x18000adb0`
- `0x180027a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027a48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027a99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027a48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027a99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027a6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027a6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b92`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027b81`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027b81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ad9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ad9`

## string_xrefs

- `0x180027c53`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
int __fastcall LdapFreeMessageWaitStructure(__int64 *a1)
{
  __int64 v1; // rbx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  int result; // eax
  int v7; // r9d
  int v8; // r8d
  int v9; // eax
  HANDLE v10; // rcx

  v1 = a1[2];
  EnterCriticalSection(&WaiterLock);
  v3 = (_QWORD *)a1[1];
  v4 = *a1;
  --GlobalWaiterCount;
  *v3 = v4;
  *(_QWORD *)(v4 + 8) = v3;
  LeaveCriticalSection(&WaiterLock);
  if ( GlobalLdapShuttingDown == 1 && !GlobalWaiterCount && GlobalLdapShutdownEvent )
    SetEvent(GlobalLdapShutdownEvent);
  if ( v1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 512));
    --*(_DWORD *)v1;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", v1, *(_DWORD *)v1);
    v5 = (struct _RTL_CRITICAL_SECTION *)(v1 + 512);
    if ( *(_DWORD *)v1 )
    {
      LeaveCriticalSection(v5);
    }
    else
    {
      LeaveCriticalSection(v5);
      DereferenceLdapConnection2(v1, 1);
    }
  }
  CloseHandle((HANDLE)a1[3]);
  result = *((_DWORD *)a1 - 2);
  if ( result != 1684095564 )
  {
    if ( result == 1701987916 )
    {
      if ( !g_fTracingOn )
      {
LABEL_9:
        v7 = *((_DWORD *)a1 - 2);
        if ( v7 != 1767987020 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1767987020, v7);
        v8 = *((_DWORD *)a1 - 1);
        v9 = LdapAllocatedHeap - v8;
        LdapAllocatedHeap -= v8;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(
            8,
            "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
            v8,
            (_DWORD)a1,
            1767987020,
            v9);
        v10 = LdapHeap;
        *((_DWORD *)a1 - 2) = 1701987916;
        return HeapFree(v10, 0, a1 - 1);
      }
      if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)a1);
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
        *((_DWORD *)a1 - 1),
        (_DWORD)a1 - 8,
        1767987020);
    goto LABEL_9;
  }
  return result;
}

```

## disassembly

```asm
0x180027a30  mov     [rsp+arg_8], rbx
0x180027a35  push    rdi
0x180027a36  sub     rsp, 30h
0x180027a3a  mov     rbx, [rcx+10h]
0x180027a3e  mov     rdi, rcx
0x180027a41  lea     rcx, WaiterLock; lpCriticalSection
0x180027a48  call    cs:__imp_EnterCriticalSection
0x180027a4f  nop     dword ptr [rax+rax+00h]
0x180027a54  mov     rax, [rdi+8]
0x180027a58  lea     rcx, WaiterLock; lpCriticalSection
0x180027a5f  mov     rdx, [rdi]
0x180027a62  dec     cs:GlobalWaiterCount
0x180027a68  mov     [rax], rdx
0x180027a6b  mov     [rdx+8], rax
0x180027a6f  call    cs:__imp_LeaveCriticalSection
0x180027a76  nop     dword ptr [rax+rax+00h]
0x180027a7b  cmp     cs:GlobalLdapShuttingDown, 1
0x180027a82  jz      loc_180027B64
0x180027a88  test    rbx, rbx
0x180027a8b  jz      short loc_180027AD5
0x180027a8d  lea     rcx, [rbx+200h]; lpCriticalSection
0x180027a94  mov     [rsp+38h+arg_0], rsi
0x180027a99  call    cs:__imp_EnterCriticalSection
0x180027aa0  nop     dword ptr [rax+rax+00h]
0x180027aa5  dec     dword ptr [rbx]
0x180027aa7  cmp     cs:g_fTracingOn, 0
0x180027aae  jnz     loc_180027BF3
0x180027ab4  cmp     dword ptr [rbx], 0
0x180027ab7  lea     rcx, [rbx+200h]; lpCriticalSection
0x180027abe  jz      loc_180027B92
0x180027ac4  call    cs:__imp_LeaveCriticalSection
0x180027acb  nop     dword ptr [rax+rax+00h]
0x180027ad0  mov     rsi, [rsp+38h+arg_0]
0x180027ad5  mov     rcx, [rdi+18h]; hObject
0x180027ad9  call    cs:__imp_CloseHandle
0x180027ae0  nop     dword ptr [rax+rax+00h]
0x180027ae5  mov     eax, [rdi-8]
0x180027ae8  cmp     eax, 6461424Ch
0x180027aed  jz      short loc_180027B58
0x180027aef  cmp     eax, 6572464Ch
0x180027af4  jz      loc_180027C29
0x180027afa  cmp     cs:g_fTracingOn, 0
0x180027b01  jnz     loc_180027C69
0x180027b07  mov     r9d, [rdi-8]
0x180027b0b  cmp     r9d, 6961574Ch
0x180027b12  jnz     loc_180027BB0
0x180027b18  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180027b1e  mov     r8d, [rdi-4]
0x180027b22  sub     eax, r8d
0x180027b25  cmp     cs:g_fTracingOn, 0
0x180027b2c  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180027b32  jnz     loc_180027CA9
0x180027b38  mov     rcx, cs:LdapHeap; hHeap
0x180027b3f  lea     r8, [rdi-8]; lpMem
0x180027b43  xor     edx, edx; dwFlags
0x180027b45  mov     dword ptr [rdi-8], 6572464Ch
0x180027b4c  call    cs:__imp_HeapFree
0x180027b53  nop     dword ptr [rax+rax+00h]
0x180027b58  mov     rbx, [rsp+38h+arg_8]
0x180027b5d  add     rsp, 30h
0x180027b61  pop     rdi
0x180027b62  retn
0x180027b64  cmp     cs:GlobalWaiterCount, 0
0x180027b6b  jnz     loc_180027A88
0x180027b71  mov     rcx, cs:GlobalLdapShutdownEvent; hEvent
0x180027b78  test    rcx, rcx
0x180027b7b  jz      loc_180027A88
0x180027b81  call    cs:__imp_SetEvent
0x180027b88  nop     dword ptr [rax+rax+00h]
0x180027b8d  jmp     loc_180027A88
0x180027b92  call    cs:__imp_LeaveCriticalSection
0x180027b99  nop     dword ptr [rax+rax+00h]
0x180027b9e  mov     edx, 1
0x180027ba3  mov     rcx, rbx
0x180027ba6  call    DereferenceLdapConnection2
0x180027bab  jmp     loc_180027AD0
0x180027bb0  cmp     cs:g_fTracingOn, 0
0x180027bb7  jz      loc_180027B18
0x180027bbd  cmp     cs:g_fProviderEnabled, 0
0x180027bc4  jz      loc_180027B18
0x180027bca  test    byte ptr cs:g_ulTraceFlags, 8
0x180027bd1  jz      loc_180027B18
0x180027bd7  mov     r8d, 6961574Ch
0x180027bdd  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x180027be4  mov     ecx, 8
0x180027be9  call    LDAPClientPrint
0x180027bee  jmp     loc_180027B18
0x180027bf3  cmp     cs:g_fProviderEnabled, 0
0x180027bfa  jz      loc_180027AB4
0x180027c00  test    byte ptr cs:g_ulTraceFlags, 4
0x180027c07  jz      loc_180027AB4
0x180027c0d  mov     r9d, [rbx]
0x180027c10  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180027c17  mov     r8, rbx
0x180027c1a  mov     ecx, 4
0x180027c1f  call    LDAPClientPrint
0x180027c24  jmp     loc_180027AB4
0x180027c29  cmp     cs:g_fTracingOn, 0
0x180027c30  jz      loc_180027B07
0x180027c36  cmp     cs:g_fProviderEnabled, 0
0x180027c3d  jz      loc_180027AFA
0x180027c43  test    byte ptr cs:g_ulTraceFlags, 8
0x180027c4a  jz      loc_180027AFA
0x180027c50  mov     r8, rdi
0x180027c53  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x180027c5a  mov     ecx, 8
0x180027c5f  call    LDAPClientPrint
0x180027c64  jmp     loc_180027AFA
0x180027c69  cmp     cs:g_fProviderEnabled, 0
0x180027c70  jz      loc_180027B07
0x180027c76  test    byte ptr cs:g_ulTraceFlags, 8
0x180027c7d  jz      loc_180027B07
0x180027c83  mov     r8d, [rdi-4]
0x180027c87  lea     r9, [rdi-8]
0x180027c8b  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x180027c92  mov     [rsp+38h+var_18], 6961574Ch
0x180027c9a  mov     ecx, 8
0x180027c9f  call    LDAPClientPrint
0x180027ca4  jmp     loc_180027B07
0x180027ca9  cmp     cs:g_fProviderEnabled, 0
0x180027cb0  jz      loc_180027B38
0x180027cb6  test    byte ptr cs:g_ulTraceFlags, 8
0x180027cbd  jz      loc_180027B38
0x180027cc3  mov     [rsp+38h+var_10], eax
0x180027cc7  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x180027cce  mov     r9, rdi
0x180027cd1  mov     [rsp+38h+var_18], 6961574Ch
0x180027cd9  mov     ecx, 8
0x180027cde  call    LDAPClientPrint
0x180027ce3  jmp     loc_180027B38
```
