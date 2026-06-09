# ldapFree

- ea: `0x18000b440`
- end: `0x18000b5c2`
- name: `ldapFree`
- size: `386`
- prototype: ``
- caller_count: `120`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018d0`
- `0x1800022c0`
- `0x1800057a0`
- `0x180006b20`
- `0x180006d80`
- `0x180008710`
- `0x180009040`
- `0x1800094a0`
- `0x18000a358`
- `0x18000adb0`
- `0x18000c8c4`
- `0x18000ce40`
- `0x18000dee8`
- `0x18000e0d0`
- `0x180011020`
- `0x1800112b0`
- `0x180011c80`
- `0x180011f50`
- `0x180014060`
- `0x180014b60`
- `0x1800164a0`
- `0x180017854`
- `0x180019f88`
- `0x18001a730`
- `0x18001a94c`
- `0x18001b0d4`
- `0x18001ba9c`
- `0x18001c2d0`
- `0x18001d470`
- `0x18001de00`
- `0x18001e6c4`
- `0x18001e800`
- `0x18001e8e0`
- `0x18001ea90`
- `0x18001f13c`
- `0x18001fb78`
- `0x1800201e0`
- `0x180020990`
- `0x180021454`
- `0x18002227c`
- `0x180022a60`
- `0x180023054`
- `0x1800230a0`
- `0x18002376c`
- `0x180024580`
- `0x180025cc8`
- `0x180026b50`
- `0x180027cf0`
- `0x180028a60`
- `0x18002909c`

## callees

- `0x1800037a8`
- `0x18000b440`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4ba`

## string_xrefs

- `0x18000b535`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
void __fastcall ldapFree(__int64 a1, int a2)
{
  int v2; // eax
  int v5; // r9d
  int v6; // r8d
  int v7; // eax
  HANDLE v8; // rcx

  if ( !a1 )
    return;
  v2 = *(_DWORD *)(a1 - 8);
  if ( v2 == 1684095564 )
    return;
  if ( v2 != 1701987916 )
    goto LABEL_4;
  if ( g_fTracingOn )
  {
    if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", a1);
LABEL_4:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
        *(_DWORD *)(a1 - 4),
        a1 - 8,
        a2);
  }
  v5 = *(_DWORD *)(a1 - 8);
  if ( v5 != a2 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", a2, v5);
  v6 = *(_DWORD *)(a1 - 4);
  v7 = LdapAllocatedHeap - v6;
  LdapAllocatedHeap -= v6;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", v6, a1, a2, v7);
  v8 = LdapHeap;
  *(_DWORD *)(a1 - 8) = 1701987916;
  HeapFree(v8, 0, (LPVOID)(a1 - 8));
}

```

## disassembly

```asm
0x18000b440  test    rcx, rcx
0x18000b443  jnz     short loc_18000B447
0x18000b445  retn
0x18000b447  mov     [rsp+arg_8], rbx
0x18000b44c  push    rsi
0x18000b44d  sub     rsp, 30h
0x18000b451  mov     eax, [rcx-8]
0x18000b454  mov     esi, edx
0x18000b456  mov     [rsp+38h+arg_0], rdi
0x18000b45b  mov     rbx, rcx
0x18000b45e  cmp     eax, 6461424Ch
0x18000b463  jz      short loc_18000B4C6
0x18000b465  cmp     eax, 6572464Ch
0x18000b46a  jz      loc_18000B50B
0x18000b470  cmp     cs:g_fTracingOn, 0
0x18000b477  jnz     loc_18000B54B
0x18000b47d  mov     r9d, [rbx-8]
0x18000b481  cmp     r9d, esi
0x18000b484  jnz     short loc_18000B4D7
0x18000b486  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18000b48c  mov     r8d, [rbx-4]
0x18000b490  sub     eax, r8d
0x18000b493  cmp     cs:g_fTracingOn, 0
0x18000b49a  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18000b4a0  jnz     loc_18000B587
0x18000b4a6  mov     rcx, cs:LdapHeap; hHeap
0x18000b4ad  lea     r8, [rbx-8]; lpMem
0x18000b4b1  xor     edx, edx; dwFlags
0x18000b4b3  mov     dword ptr [rbx-8], 6572464Ch
0x18000b4ba  call    cs:__imp_HeapFree
0x18000b4c1  nop     dword ptr [rax+rax+00h]
0x18000b4c6  mov     rdi, [rsp+38h+arg_0]
0x18000b4cb  mov     rbx, [rsp+38h+arg_8]
0x18000b4d0  add     rsp, 30h
0x18000b4d4  pop     rsi
0x18000b4d5  retn
0x18000b4d7  cmp     cs:g_fTracingOn, 0
0x18000b4de  jz      short loc_18000B486
0x18000b4e0  cmp     cs:g_fProviderEnabled, 0
0x18000b4e7  jz      short loc_18000B486
0x18000b4e9  test    byte ptr cs:g_ulTraceFlags, 8
0x18000b4f0  jz      short loc_18000B486
0x18000b4f2  mov     r8d, esi
0x18000b4f5  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x18000b4fc  mov     ecx, 8
0x18000b501  call    LDAPClientPrint
0x18000b506  jmp     loc_18000B486
0x18000b50b  cmp     cs:g_fTracingOn, 0
0x18000b512  jz      loc_18000B47D
0x18000b518  cmp     cs:g_fProviderEnabled, 0
0x18000b51f  jz      loc_18000B470
0x18000b525  test    byte ptr cs:g_ulTraceFlags, 8
0x18000b52c  jz      loc_18000B470
0x18000b532  mov     r8, rbx
0x18000b535  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x18000b53c  mov     ecx, 8
0x18000b541  call    LDAPClientPrint
0x18000b546  jmp     loc_18000B470
0x18000b54b  cmp     cs:g_fProviderEnabled, 0
0x18000b552  jz      loc_18000B47D
0x18000b558  test    byte ptr cs:g_ulTraceFlags, 8
0x18000b55f  jz      loc_18000B47D
0x18000b565  mov     r8d, [rbx-4]
0x18000b569  lea     r9, [rbx-8]
0x18000b56d  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x18000b574  mov     [rsp+38h+var_18], esi
0x18000b578  mov     ecx, 8
0x18000b57d  call    LDAPClientPrint
0x18000b582  jmp     loc_18000B47D
0x18000b587  cmp     cs:g_fProviderEnabled, 0
0x18000b58e  jz      loc_18000B4A6
0x18000b594  test    byte ptr cs:g_ulTraceFlags, 8
0x18000b59b  jz      loc_18000B4A6
0x18000b5a1  mov     [rsp+38h+var_10], eax
0x18000b5a5  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x18000b5ac  mov     r9, rbx
0x18000b5af  mov     [rsp+38h+var_18], esi
0x18000b5b3  mov     ecx, 8
0x18000b5b8  call    LDAPClientPrint
0x18000b5bd  jmp     loc_18000B4A6
```
