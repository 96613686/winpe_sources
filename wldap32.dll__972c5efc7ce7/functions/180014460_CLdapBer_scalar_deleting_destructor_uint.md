# CLdapBer::`scalar deleting destructor'(uint)

- ea: `0x180014460`
- end: `0x1800145f4`
- name: `??_GCLdapBer@@QEAAPEAXI@Z`
- size: `404`
- prototype: `void *__fastcall(CLdapBer *__hidden this, unsigned int)`
- caller_count: `28`
- callee_count: `3`
- tags: ``

## callers

- `0x180008710`
- `0x18000a358`
- `0x18000adb0`
- `0x18000bf40`
- `0x18000e0d0`
- `0x1800112b0`
- `0x1800147f0`
- `0x18001ba9c`
- `0x18001f96c`
- `0x1800230a0`
- `0x18002a9f8`
- `0x18002d1a8`
- `0x18002df40`
- `0x180038678`
- `0x18003a274`
- `0x18003ae3c`
- `0x18003b448`
- `0x18003c5bc`
- `0x18003e508`
- `0x18003f138`
- `0x180041cd0`
- `0x18004404c`
- `0x1800442b0`
- `0x18004459c`
- `0x180047254`
- `0x18004a6c4`
- `0x18004a984`
- `0x18004af90`

## callees

- `0x1800037a8`
- `0x180014460`
- `0x180014600`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800144e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800144e5`

## string_xrefs

- `0x18001455f`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
CLdapBer *__fastcall CLdapBer::`scalar deleting destructor'(CLdapBer *this)
{
  int v3; // eax
  int v4; // r9d
  int v5; // r8d
  int v6; // eax
  HANDLE v7; // rcx

  CLdapBer::~CLdapBer(this);
  if ( !this )
    return 0;
  v3 = *((_DWORD *)this - 2);
  if ( v3 != 1684095564 )
  {
    if ( v3 == 1701987916 )
    {
      if ( !g_fTracingOn )
      {
LABEL_6:
        v4 = *((_DWORD *)this - 2);
        if ( v4 != 1816347212 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1816347212, v4);
        v5 = *((_DWORD *)this - 1);
        v6 = LdapAllocatedHeap - v5;
        LdapAllocatedHeap -= v5;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(
            8,
            "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
            v5,
            (_DWORD)this,
            1816347212,
            v6);
        v7 = LdapHeap;
        *((_DWORD *)this - 2) = 1701987916;
        HeapFree(v7, 0, (char *)this - 8);
        return this;
      }
      if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)this);
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
        *((_DWORD *)this - 1),
        (_DWORD)this - 8,
        1816347212);
    goto LABEL_6;
  }
  return this;
}

```

## disassembly

```asm
0x180014460  push    rbx
0x180014462  sub     rsp, 30h
0x180014466  mov     rbx, rcx
0x180014469  call    ??1CLdapBer@@QEAA@XZ; CLdapBer::~CLdapBer(void)
0x18001446e  test    rbx, rbx
0x180014471  jnz     short loc_18001447D
0x180014473  mov     rax, rbx
0x180014476  add     rsp, 30h
0x18001447a  pop     rbx
0x18001447b  retn
0x18001447d  mov     eax, [rbx-8]
0x180014480  mov     [rsp+38h+arg_0], rdi
0x180014485  cmp     eax, 6461424Ch
0x18001448a  jz      short loc_1800144F1
0x18001448c  cmp     eax, 6572464Ch
0x180014491  jz      loc_180014535
0x180014497  cmp     cs:g_fTracingOn, 0
0x18001449e  jnz     loc_180014575
0x1800144a4  mov     r9d, [rbx-8]
0x1800144a8  cmp     r9d, 6C43424Ch
0x1800144af  jnz     short loc_1800144FE
0x1800144b1  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x1800144b7  mov     r8d, [rbx-4]
0x1800144bb  sub     eax, r8d
0x1800144be  cmp     cs:g_fTracingOn, 0
0x1800144c5  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x1800144cb  jnz     loc_1800145B5
0x1800144d1  mov     rcx, cs:LdapHeap; hHeap
0x1800144d8  lea     r8, [rbx-8]; lpMem
0x1800144dc  xor     edx, edx; dwFlags
0x1800144de  mov     dword ptr [rbx-8], 6572464Ch
0x1800144e5  call    cs:__imp_HeapFree
0x1800144ec  nop     dword ptr [rax+rax+00h]
0x1800144f1  mov     rdi, [rsp+38h+arg_0]
0x1800144f6  mov     rax, rbx
0x1800144f9  jmp     loc_180014476
0x1800144fe  cmp     cs:g_fTracingOn, 0
0x180014505  jz      short loc_1800144B1
0x180014507  cmp     cs:g_fProviderEnabled, 0
0x18001450e  jz      short loc_1800144B1
0x180014510  test    byte ptr cs:g_ulTraceFlags, 8
0x180014517  jz      short loc_1800144B1
0x180014519  mov     r8d, 6C43424Ch
0x18001451f  lea     rdx, aExpectedTag0xX; "Expected tag 0x%x but found tag 0x%x\n"
0x180014526  mov     ecx, 8
0x18001452b  call    LDAPClientPrint
0x180014530  jmp     loc_1800144B1
0x180014535  cmp     cs:g_fTracingOn, 0
0x18001453c  jz      loc_1800144A4
0x180014542  cmp     cs:g_fProviderEnabled, 0
0x180014549  jz      loc_180014497
0x18001454f  test    byte ptr cs:g_ulTraceFlags, 8
0x180014556  jz      loc_180014497
0x18001455c  mov     r8, rbx
0x18001455f  lea     rdx, aFreeingMemoryA; "Freeing memory at 0x%x which is already"...
0x180014566  mov     ecx, 8
0x18001456b  call    LDAPClientPrint
0x180014570  jmp     loc_180014497
0x180014575  cmp     cs:g_fProviderEnabled, 0
0x18001457c  jz      loc_1800144A4
0x180014582  test    byte ptr cs:g_ulTraceFlags, 8
0x180014589  jz      loc_1800144A4
0x18001458f  mov     r8d, [rbx-4]
0x180014593  lea     r9, [rbx-8]
0x180014597  lea     rdx, aLdapfreeFreed0; "ldapfree freed       0x%x bytes at addr"...
0x18001459e  mov     [rsp+38h+var_18], 6C43424Ch
0x1800145a6  mov     ecx, 8
0x1800145ab  call    LDAPClientPrint
0x1800145b0  jmp     loc_1800144A4
0x1800145b5  cmp     cs:g_fProviderEnabled, 0
0x1800145bc  jz      loc_1800144D1
0x1800145c2  test    byte ptr cs:g_ulTraceFlags, 8
0x1800145c9  jz      loc_1800144D1
0x1800145cf  mov     [rsp+38h+var_10], eax
0x1800145d3  lea     rdx, aLdapfree0x08xB; "ldapFree   0x%08x bytes at address 0x%x"...
0x1800145da  mov     r9, rbx
0x1800145dd  mov     [rsp+38h+var_18], 6C43424Ch
0x1800145e5  mov     ecx, 8
0x1800145ea  call    LDAPClientPrint
0x1800145ef  jmp     loc_1800144D1
```
