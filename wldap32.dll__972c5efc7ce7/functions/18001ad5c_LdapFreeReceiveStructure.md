# LdapFreeReceiveStructure

- ea: `0x18001ad5c`
- end: `0x18001af4b`
- name: `LdapFreeReceiveStructure`
- size: `495`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800094a0`
- `0x18000a358`
- `0x18000adb0`
- `0x1800190b0`
- `0x1800191d0`
- `0x18001a758`
- `0x18001c2d0`
- `0x18002b4d0`

## callees

- `0x1800037a8`
- `0x18001ad5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001adf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001adf9`

## string_xrefs

- `0x18001aec0`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
void __fastcall LdapFreeReceiveStructure(__int64 a1, char a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rax
  _DWORD *v5; // rdi
  int v6; // r8d
  int v7; // eax
  HANDLE v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  _QWORD *v10; // rax
  __int64 v11; // rdx

  v3 = (struct _RTL_CRITICAL_SECTION *)_InterlockedExchange64((volatile __int64 *)a1, 0);
  if ( v3 )
  {
    v9 = v3 + 20;
    if ( !a2 )
      EnterCriticalSection(v3 + 20);
    v10 = *(_QWORD **)(a1 + 16);
    v11 = *(_QWORD *)(a1 + 8);
    *v10 = v11;
    *(_QWORD *)(v11 + 8) = v10;
    if ( !a2 )
      LeaveCriticalSection(v9);
  }
  if ( a1 )
  {
    v5 = (_DWORD *)(a1 - 8);
    if ( *(_DWORD *)(a1 - 8) != 1684095564 )
    {
      if ( *v5 == 1701987916 )
      {
        if ( !g_fTracingOn )
        {
LABEL_7:
          if ( *v5 != 1667584588 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1667584588, *v5);
          v6 = v5[1];
          v7 = LdapAllocatedHeap - v6;
          LdapAllocatedHeap -= v6;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(8, "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", v6, a1, 1667584588, v7);
          v8 = LdapHeap;
          *v5 = 1701987916;
          HeapFree(v8, 0, (LPVOID)(a1 - 8));
          return;
        }
        if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", a1);
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(8, "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n", v5[1], a1 - 8, 1667584588);
      goto LABEL_7;
    }
  }
}

```

## disassembly

```asm
0x18001ad5c  mov     [rsp+arg_0], rbx
0x18001ad61  mov     [rsp+arg_8], rsi
0x18001ad66  push    rdi
0x18001ad67  sub     rsp, 30h
0x18001ad6b  xor     eax, eax
0x18001ad6d  mov     sil, dl
0x18001ad70  xchg    rax, [rcx]
0x18001ad73  mov     rbx, rcx
0x18001ad76  test    rax, rax
0x18001ad79  jnz     loc_18001AE0A
0x18001ad7f  test    rbx, rbx
0x18001ad82  jnz     short loc_18001AD95
0x18001ad84  mov     rbx, [rsp+38h+arg_0]
0x18001ad89  mov     rsi, [rsp+38h+arg_8]
0x18001ad8e  add     rsp, 30h
0x18001ad92  pop     rdi
0x18001ad93  retn
0x18001ad95  lea     rdi, [rbx-8]
0x18001ad99  cmp     dword ptr [rdi], 6461424Ch
0x18001ad9f  jz      short loc_18001AD84
0x18001ada1  cmp     dword ptr [rdi], 6572464Ch
0x18001ada7  mov     esi, 8
0x18001adac  jz      loc_18001AE96
0x18001adb2  cmp     cs:g_fTracingOn, 0
0x18001adb9  jnz     loc_18001AED3
0x18001adbf  cmp     dword ptr [rdi], 6365524Ch
0x18001adc5  jnz     short loc_18001AE42
0x18001adc7  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001adcd  mov     r8d, [rdi+4]
0x18001add1  sub     eax, r8d
0x18001add4  cmp     cs:g_fTracingOn, 0
0x18001addb  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001ade1  jnz     loc_18001AF0F
0x18001ade7  mov     rcx, cs:LdapHeap; hHeap
0x18001adee  mov     r8, rdi; lpMem
0x18001adf1  xor     edx, edx; dwFlags
0x18001adf3  mov     dword ptr [rdi], 6572464Ch
0x18001adf9  call    cs:__imp_HeapFree
0x18001ae00  nop     dword ptr [rax+rax+00h]
0x18001ae05  jmp     loc_18001AD84
0x18001ae0a  lea     rdi, [rax+320h]
0x18001ae11  test    sil, sil
0x18001ae14  jz      short loc_18001AE85
0x18001ae16  mov     rax, [rbx+10h]
0x18001ae1a  mov     rdx, [rbx+8]
0x18001ae1e  mov     [rax], rdx
0x18001ae21  mov     [rdx+8], rax
0x18001ae25  test    sil, sil
0x18001ae28  jnz     loc_18001AD7F
0x18001ae2e  mov     rcx, rdi; lpCriticalSection
0x18001ae31  call    cs:__imp_LeaveCriticalSection
0x18001ae38  nop     dword ptr [rax+rax+00h]
0x18001ae3d  jmp     loc_18001AD7F
0x18001ae42  cmp     cs:g_fTracingOn, 0
0x18001ae49  jz      loc_18001ADC7
0x18001ae4f  cmp     cs:g_fProviderEnabled, 0
0x18001ae56  jz      loc_18001ADC7
0x18001ae5c  test    byte ptr cs:g_ulTraceFlags, sil
0x18001ae63  jz      loc_18001ADC7
0x18001ae69  mov     r9d, [rdi]
0x18001ae6c  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x18001ae73  mov     r8d, 6365524Ch
0x18001ae79  mov     ecx, esi
0x18001ae7b  call    LDAPClientPrint
0x18001ae80  jmp     loc_18001ADC7
0x18001ae85  mov     rcx, rdi; lpCriticalSection
0x18001ae88  call    cs:__imp_EnterCriticalSection
0x18001ae8f  nop     dword ptr [rax+rax+00h]
0x18001ae94  jmp     short loc_18001AE16
0x18001ae96  cmp     cs:g_fTracingOn, 0
0x18001ae9d  jz      loc_18001ADBF
0x18001aea3  cmp     cs:g_fProviderEnabled, 0
0x18001aeaa  jz      loc_18001ADB2
0x18001aeb0  test    byte ptr cs:g_ulTraceFlags, sil
0x18001aeb7  jz      loc_18001ADB2
0x18001aebd  mov     r8, rbx
0x18001aec0  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x18001aec7  mov     ecx, esi
0x18001aec9  call    LDAPClientPrint
0x18001aece  jmp     loc_18001ADB2
0x18001aed3  cmp     cs:g_fProviderEnabled, 0
0x18001aeda  jz      loc_18001ADBF
0x18001aee0  test    byte ptr cs:g_ulTraceFlags, sil
0x18001aee7  jz      loc_18001ADBF
0x18001aeed  mov     r8d, [rdi+4]
0x18001aef1  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x18001aef8  mov     r9, rdi
0x18001aefb  mov     [rsp+38h+var_18], 6365524Ch
0x18001af03  mov     ecx, esi
0x18001af05  call    LDAPClientPrint
0x18001af0a  jmp     loc_18001ADBF
0x18001af0f  cmp     cs:g_fProviderEnabled, 0
0x18001af16  jz      loc_18001ADE7
0x18001af1c  test    byte ptr cs:g_ulTraceFlags, sil
0x18001af23  jz      loc_18001ADE7
0x18001af29  mov     [rsp+38h+var_10], eax
0x18001af2d  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x18001af34  mov     r9, rbx
0x18001af37  mov     [rsp+38h+var_18], 6365524Ch
0x18001af3f  mov     ecx, esi
0x18001af41  call    LDAPClientPrint
0x18001af46  jmp     loc_18001ADE7
```
