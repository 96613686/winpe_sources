# WaitForExclusiveClientAccess

- ea: `0x18001f494`
- end: `0x18001f50b`
- name: `WaitForExclusiveClientAccess`
- size: `119`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180006cd4`
- `0x18000d980`
- `0x180010750`
- `0x180017be0`
- `0x18001b1dc`
- `0x18001b4c4`
- `0x180021424`
- `0x180023060`
- `0x180024fc8`
- `0x1800283d0`
- `0x180028b00`
- `0x180029920`
- `0x18002a8c0`
- `0x18002f1c0`
- `0x18002f778`
- `0x180032910`
- `0x1800329f0`
- `0x180032ad0`
- `0x1800330a8`
- `0x180034694`
- `0x180034a80`

## callees

- `0x18001f494`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001f4f8`
- `KERNEL32!LeaveCriticalSection` at `0x18001f4f8`
- `KERNEL32!EnterCriticalSection` at `0x18001f4c5`
- `KERNEL32!EnterCriticalSection` at `0x18001f4c5`

## pseudocode

```c
unsigned __int64 __fastcall WaitForExclusiveClientAccess(unsigned __int64 a1)
{
  unsigned __int64 v2; // rbx

  v2 = a1 >> 4;
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a1 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  if ( *(_DWORD *)a1 == 1414417475 )
    return a1;
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v2 & gdwPointerToLockTableIndexBits));
  return 0;
}

```

## disassembly

```asm
0x18001f494  mov     [rsp+arg_8], rbx
0x18001f499  push    rdi
0x18001f49a  sub     rsp, 20h
0x18001f49e  mov     rdi, rcx
0x18001f4a1  mov     rbx, rcx
0x18001f4a4  shr     rbx, 4
0x18001f4a8  mov     [rsp+28h+arg_0], rbx
0x18001f4ad  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001f4b3  and     rax, rbx
0x18001f4b6  lea     rdx, [rax+rax*4]
0x18001f4ba  mov     rax, cs:gLockTable
0x18001f4c1  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x18001f4c5  call    cs:__imp_EnterCriticalSection
0x18001f4cb  nop
0x18001f4cc  cmp     dword ptr [rdi], 544E4C43h
0x18001f4d2  jnz     short loc_18001F4D9
0x18001f4d4  mov     rax, rdi
0x18001f4d7  jmp     short loc_18001F500
0x18001f4d9  jmp     short loc_18001F4E0
0x18001f4db  mov     rbx, [rsp+28h+arg_0]
0x18001f4e0  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001f4e6  and     rax, rbx
0x18001f4e9  lea     rcx, [rax+rax*4]
0x18001f4ed  mov     rax, cs:gLockTable
0x18001f4f4  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001f4f8  call    cs:__imp_LeaveCriticalSection
0x18001f4fe  xor     eax, eax
0x18001f500  mov     rbx, [rsp+28h+arg_8]
0x18001f505  add     rsp, 20h
0x18001f509  pop     rdi
0x18001f50a  retn
```
