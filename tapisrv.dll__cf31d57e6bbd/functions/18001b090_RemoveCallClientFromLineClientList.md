# RemoveCallClientFromLineClientList

- ea: `0x18001b090`
- end: `0x18001b123`
- name: `RemoveCallClientFromLineClientList`
- size: `147`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a94`
- `0x180008910`
- `0x180011090`
- `0x180016d20`

## callees

- `0x18001b090`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001b10b`
- `KERNEL32!LeaveCriticalSection` at `0x18001b10b`
- `KERNEL32!EnterCriticalSection` at `0x18001b0c5`
- `KERNEL32!EnterCriticalSection` at `0x18001b0c5`

## pseudocode

```c
__int64 __fastcall RemoveCallClientFromLineClientList(_QWORD *a1)
{
  unsigned __int64 v1; // rsi
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rax

  v1 = a1[2];
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v1 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  v3 = a1[9];
  if ( v3 )
    *(_QWORD *)(v3 + 64) = a1[8];
  v4 = a1[8];
  v5 = a1[9];
  if ( v4 )
    *(_QWORD *)(v4 + 72) = v5;
  else
    *(_QWORD *)(v1 + 48) = v5;
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((v1 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  return 0;
}

```

## disassembly

```asm
0x18001b090  mov     [rsp+arg_0], rbx
0x18001b095  mov     [rsp+arg_8], rsi
0x18001b09a  push    rdi
0x18001b09b  sub     rsp, 20h
0x18001b09f  mov     rsi, [rcx+10h]
0x18001b0a3  mov     rbx, rcx
0x18001b0a6  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001b0ac  mov     rdi, rsi
0x18001b0af  shr     rdi, 4
0x18001b0b3  and     rax, rdi
0x18001b0b6  lea     rdx, [rax+rax*4]
0x18001b0ba  mov     rax, cs:gLockTable
0x18001b0c1  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x18001b0c5  call    cs:__imp_EnterCriticalSection
0x18001b0cb  mov     rdx, [rbx+48h]
0x18001b0cf  test    rdx, rdx
0x18001b0d2  jz      short loc_18001B0DC
0x18001b0d4  mov     rax, [rbx+40h]
0x18001b0d8  mov     [rdx+40h], rax
0x18001b0dc  mov     rdx, [rbx+40h]
0x18001b0e0  mov     rax, [rbx+48h]
0x18001b0e4  test    rdx, rdx
0x18001b0e7  jz      short loc_18001B0EF
0x18001b0e9  mov     [rdx+48h], rax
0x18001b0ed  jmp     short loc_18001B0F3
0x18001b0ef  mov     [rsi+30h], rax
0x18001b0f3  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18001b0f9  and     rax, rdi
0x18001b0fc  lea     rcx, [rax+rax*4]
0x18001b100  mov     rax, cs:gLockTable
0x18001b107  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001b10b  call    cs:__imp_LeaveCriticalSection
0x18001b111  mov     rbx, [rsp+28h+arg_0]
0x18001b116  xor     eax, eax
0x18001b118  mov     rsi, [rsp+28h+arg_8]
0x18001b11d  add     rsp, 20h
0x18001b121  pop     rdi
0x18001b122  retn
```
