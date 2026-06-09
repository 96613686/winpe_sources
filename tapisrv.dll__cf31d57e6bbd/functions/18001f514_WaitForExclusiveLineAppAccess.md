# WaitForExclusiveLineAppAccess

- ea: `0x18001f514`
- end: `0x18001f5a3`
- name: `WaitForExclusiveLineAppAccess`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fb70`
- `0x180011820`
- `0x1800132a0`
- `0x18001fb28`

## callees

- `0x18001f514`
- `0x18003e15c`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001f582`
- `KERNEL32!LeaveCriticalSection` at `0x18001f582`
- `KERNEL32!EnterCriticalSection` at `0x18001f556`
- `KERNEL32!EnterCriticalSection` at `0x18001f556`

## pseudocode

```c
unsigned __int64 __fastcall WaitForExclusiveLineAppAccess(__int64 a1, __int64 a2)
{
  unsigned int v3; // esi
  unsigned __int64 result; // rax
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // rcx

  v3 = a1;
  result = ReferenceObject(a1, (unsigned int)a1, 1347436876);
  v5 = result;
  if ( result )
  {
    v6 = result >> 4;
    EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((result >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
    if ( *(_DWORD *)v5 != 1347436876 || *(_QWORD *)(v5 + 8) != a2 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v6 & gdwPointerToLockTableIndexBits));
      v5 = 0;
    }
    DereferenceObject(v7, v3, 1);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18001f514  push    rbx
0x18001f516  push    rbp
0x18001f517  push    rsi
0x18001f518  push    rdi
0x18001f519  sub     rsp, 28h
0x18001f51d  mov     rbp, rdx
0x18001f520  mov     r8d, 5050414Ch
0x18001f526  mov     edx, ecx
0x18001f528  mov     esi, ecx
0x18001f52a  call    ReferenceObject
0x18001f52f  mov     rbx, rax
0x18001f532  test    rax, rax
0x18001f535  jz      short loc_18001F59A
0x18001f537  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001f53d  mov     rdi, rbx
0x18001f540  shr     rdi, 4
0x18001f544  and     rax, rdi
0x18001f547  lea     rcx, [rax+rax*4]
0x18001f54b  mov     rax, cs:gLockTable
0x18001f552  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001f556  call    cs:__imp_EnterCriticalSection
0x18001f55c  cmp     dword ptr [rbx], 5050414Ch
0x18001f562  jnz     short loc_18001F56A
0x18001f564  cmp     [rbx+8], rbp
0x18001f568  jz      short loc_18001F58A
0x18001f56a  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001f570  and     rax, rdi
0x18001f573  lea     rcx, [rax+rax*4]
0x18001f577  mov     rax, cs:gLockTable
0x18001f57e  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001f582  call    cs:__imp_LeaveCriticalSection
0x18001f588  xor     ebx, ebx
0x18001f58a  mov     r8d, 1
0x18001f590  mov     edx, esi
0x18001f592  call    DereferenceObject
0x18001f597  mov     rax, rbx
0x18001f59a  add     rsp, 28h
0x18001f59e  pop     rdi
0x18001f59f  pop     rsi
0x18001f5a0  pop     rbp
0x18001f5a1  pop     rbx
0x18001f5a2  retn
```
