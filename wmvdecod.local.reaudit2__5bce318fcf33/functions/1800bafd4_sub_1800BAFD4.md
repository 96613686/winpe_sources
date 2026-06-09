# sub_1800BAFD4

- ea: `0x1800bafd4`
- end: `0x1800bb027`
- name: `sub_1800BAFD4`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800bbb70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bb00e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bb00e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800baff6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800baff6`

## pseudocode

```c
__int64 __fastcall sub_1800BAFD4(__int64 a1)
{
  *(_DWORD *)(a1 + 72) = 8;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  *(_QWORD *)a1 = CreateEventW(0, 1, 1, 0);
  return a1;
}

```

## disassembly

```asm
0x1800bafd4  push    rbx
0x1800bafd6  sub     rsp, 20h
0x1800bafda  xor     eax, eax
0x1800bafdc  mov     dword ptr [rcx+48h], 8
0x1800bafe3  mov     [rcx+8], rax
0x1800bafe7  mov     rbx, rcx
0x1800bafea  mov     [rcx+10h], rax
0x1800bafee  mov     [rcx+18h], rax
0x1800baff2  add     rcx, 20h ; ' '; lpCriticalSection
0x1800baff6  call    cs:InitializeCriticalSection
0x1800baffd  nop     dword ptr [rax+rax+00h]
0x1800bb002  xor     r9d, r9d; lpName
0x1800bb005  xor     ecx, ecx; lpEventAttributes
0x1800bb007  lea     edx, [r9+1]; bManualReset
0x1800bb00b  mov     r8d, edx; bInitialState
0x1800bb00e  call    cs:CreateEventW
0x1800bb015  nop     dword ptr [rax+rax+00h]
0x1800bb01a  mov     [rbx], rax
0x1800bb01d  mov     rax, rbx
0x1800bb020  add     rsp, 20h
0x1800bb024  pop     rbx
0x1800bb025  retn
```
