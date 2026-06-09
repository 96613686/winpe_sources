# WaitForExclusivetCallAccess

- ea: `0x18001f620`
- end: `0x18001f6bd`
- name: `WaitForExclusivetCallAccess`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x180003498`
- `0x180003f58`
- `0x18000469c`
- `0x1800064f8`
- `0x180007570`
- `0x180007aa0`
- `0x180007df0`
- `0x180008910`
- `0x18000c5a0`
- `0x18000fe60`
- `0x180011090`
- `0x1800112a0`
- `0x180011430`
- `0x180011600`
- `0x180015300`
- `0x180016d20`
- `0x180017be0`
- `0x18001c24c`
- `0x18001ea6c`
- `0x180034604`

## callees

- `0x18001f620`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001f6a5`
- `KERNEL32!LeaveCriticalSection` at `0x18001f6a5`
- `KERNEL32!EnterCriticalSection` at `0x18001f662`
- `KERNEL32!EnterCriticalSection` at `0x18001f662`

## pseudocode

```c
__int64 __fastcall WaitForExclusivetCallAccess(unsigned __int64 a1, int a2)
{
  __int64 result; // rax
  int v5; // esi

  LODWORD(result) = 0;
  if ( *(_DWORD *)a1 != a2
    || (v5 = *(_DWORD *)(a1 + 48),
        EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4))),
        result = 1,
        *(_DWORD *)a1 != a2)
    || *(_DWORD *)(a1 + 48) != v5 )
  {
    if ( (_DWORD)result )
      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001f620  mov     [rsp+arg_8], rbx
0x18001f625  mov     [rsp+arg_10], rsi
0x18001f62a  mov     [rsp+arg_0], rcx
0x18001f62f  push    rdi
0x18001f630  sub     rsp, 30h
0x18001f634  mov     edi, edx
0x18001f636  mov     rbx, rcx
0x18001f639  xor     eax, eax
0x18001f63b  mov     [rsp+38h+var_18], eax
0x18001f63f  cmp     [rcx], edx
0x18001f641  jnz     short loc_18001F67A
0x18001f643  mov     esi, [rcx+30h]
0x18001f646  shr     rcx, 4
0x18001f64a  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001f650  and     rcx, rax
0x18001f653  lea     rcx, [rcx+rcx*4]
0x18001f657  mov     rax, cs:gLockTable
0x18001f65e  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001f662  call    cs:__imp_EnterCriticalSection
0x18001f668  mov     eax, 1
0x18001f66d  mov     [rsp+38h+var_18], eax
0x18001f671  cmp     [rbx], edi
0x18001f673  jnz     short loc_18001F67A
0x18001f675  cmp     [rbx+30h], esi
0x18001f678  jz      short loc_18001F6AD
0x18001f67a  jmp     short loc_18001F685
0x18001f67c  mov     rbx, [rsp+38h+arg_0]
0x18001f681  mov     eax, [rsp+38h+var_18]
0x18001f685  test    eax, eax
0x18001f687  jz      short loc_18001F6AB
0x18001f689  shr     rbx, 4
0x18001f68d  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001f693  and     rbx, rax
0x18001f696  lea     rcx, [rbx+rbx*4]
0x18001f69a  mov     rax, cs:gLockTable
0x18001f6a1  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001f6a5  call    cs:__imp_LeaveCriticalSection
0x18001f6ab  xor     eax, eax
0x18001f6ad  mov     rbx, [rsp+38h+arg_8]
0x18001f6b2  mov     rsi, [rsp+38h+arg_10]
0x18001f6b7  add     rsp, 30h
0x18001f6bb  pop     rdi
0x18001f6bc  retn
```
