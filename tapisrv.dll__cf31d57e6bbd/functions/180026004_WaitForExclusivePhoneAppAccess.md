# WaitForExclusivePhoneAppAccess

- ea: `0x180026004`
- end: `0x180026093`
- name: `WaitForExclusivePhoneAppAccess`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800234a0`
- `0x180023910`

## callees

- `0x180026004`
- `0x18003e15c`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180026072`
- `KERNEL32!LeaveCriticalSection` at `0x180026072`
- `KERNEL32!EnterCriticalSection` at `0x180026046`
- `KERNEL32!EnterCriticalSection` at `0x180026046`

## pseudocode

```c
unsigned __int64 __fastcall WaitForExclusivePhoneAppAccess(__int64 a1, __int64 a2)
{
  unsigned int v3; // esi
  unsigned __int64 result; // rax
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // rcx

  v3 = a1;
  result = ReferenceObject(a1, (unsigned int)a1, 1347436880);
  v5 = result;
  if ( result )
  {
    v6 = result >> 4;
    EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((result >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
    if ( *(_DWORD *)v5 != 1347436880 || *(_QWORD *)(v5 + 8) != a2 )
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
0x180026004  push    rbx
0x180026006  push    rbp
0x180026007  push    rsi
0x180026008  push    rdi
0x180026009  sub     rsp, 28h
0x18002600d  mov     rbp, rdx
0x180026010  mov     r8d, 50504150h
0x180026016  mov     edx, ecx
0x180026018  mov     esi, ecx
0x18002601a  call    ReferenceObject
0x18002601f  mov     rbx, rax
0x180026022  test    rax, rax
0x180026025  jz      short loc_18002608A
0x180026027  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002602d  mov     rdi, rbx
0x180026030  shr     rdi, 4
0x180026034  and     rax, rdi
0x180026037  lea     rcx, [rax+rax*4]
0x18002603b  mov     rax, cs:gLockTable
0x180026042  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180026046  call    cs:__imp_EnterCriticalSection
0x18002604c  cmp     dword ptr [rbx], 50504150h
0x180026052  jnz     short loc_18002605A
0x180026054  cmp     [rbx+8], rbp
0x180026058  jz      short loc_18002607A
0x18002605a  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180026060  and     rax, rdi
0x180026063  lea     rcx, [rax+rax*4]
0x180026067  mov     rax, cs:gLockTable
0x18002606e  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180026072  call    cs:__imp_LeaveCriticalSection
0x180026078  xor     ebx, ebx
0x18002607a  mov     r8d, 1
0x180026080  mov     edx, esi
0x180026082  call    DereferenceObject
0x180026087  mov     rax, rbx
0x18002608a  add     rsp, 28h
0x18002608e  pop     rdi
0x18002608f  pop     rsi
0x180026090  pop     rbp
0x180026091  pop     rbx
0x180026092  retn
```
