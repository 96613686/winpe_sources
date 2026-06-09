# FExMpRegistrationComplete

- ea: `0x14000c2f0`
- end: `0x14000c394`
- name: `FExMpRegistrationComplete`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006bc0`

## callees

- `0x14000c2f0`

## import_xrefs

- `NDIS!NdisFreeMemory` at `0x14000c30f`
- `NDIS!NdisFreeMemory` at `0x14000c344`
- `NDIS!NdisFreeMemory` at `0x14000c368`
- `NDIS!NdisFreeMemory` at `0x14000c386`
- `NDIS!NdisFreeMemory` at `0x14000c30f`
- `NDIS!NdisFreeMemory` at `0x14000c344`
- `NDIS!NdisFreeMemory` at `0x14000c368`
- `NDIS!NdisFreeMemory` at `0x14000c386`

## pseudocode

```c
__int64 __fastcall FExMpRegistrationComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4, PVOID VirtualAddress)
{
  void *v6; // rcx
  void *v7; // rcx

  if ( a4 )
  {
    v6 = *(void **)(a4 + 200);
    if ( v6 )
    {
      NdisFreeMemory(v6, 0, 0);
      *(_QWORD *)(a4 + 200) = 0;
    }
    v7 = *(void **)(a4 + 160);
    *(_DWORD *)(a4 + 208) = 0;
    if ( v7 )
    {
      NdisFreeMemory(v7, 0, 0);
      *(_QWORD *)(a4 + 160) = 0;
    }
    NdisFreeMemory((PVOID)a4, 0, 0);
  }
  if ( VirtualAddress )
    NdisFreeMemory(VirtualAddress, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x14000c2f0  push    rbx
0x14000c2f2  sub     rsp, 20h
0x14000c2f6  mov     rbx, r9
0x14000c2f9  test    r9, r9
0x14000c2fc  jz      short loc_14000C350
0x14000c2fe  mov     rcx, [r9+0C8h]; VirtualAddress
0x14000c305  test    rcx, rcx
0x14000c308  jz      short loc_14000C326
0x14000c30a  xor     r8d, r8d; MemoryFlags
0x14000c30d  xor     edx, edx; Length
0x14000c30f  call    cs:__imp_NdisFreeMemory
0x14000c316  nop     dword ptr [rax+rax+00h]
0x14000c31b  mov     qword ptr [rbx+0C8h], 0
0x14000c326  mov     rcx, [rbx+0A0h]; VirtualAddress
0x14000c32d  mov     dword ptr [rbx+0D0h], 0
0x14000c337  test    rcx, rcx
0x14000c33a  jnz     short loc_14000C363
0x14000c33c  xor     r8d, r8d; MemoryFlags
0x14000c33f  xor     edx, edx; Length
0x14000c341  mov     rcx, rbx; VirtualAddress
0x14000c344  call    cs:__imp_NdisFreeMemory
0x14000c34b  nop     dword ptr [rax+rax+00h]
0x14000c350  mov     rcx, [rsp+28h+VirtualAddress]; VirtualAddress
0x14000c355  test    rcx, rcx
0x14000c358  jnz     short loc_14000C381
0x14000c35a  xor     eax, eax
0x14000c35c  add     rsp, 20h
0x14000c360  pop     rbx
0x14000c361  retn
0x14000c363  xor     r8d, r8d; MemoryFlags
0x14000c366  xor     edx, edx; Length
0x14000c368  call    cs:__imp_NdisFreeMemory
0x14000c36f  nop     dword ptr [rax+rax+00h]
0x14000c374  mov     qword ptr [rbx+0A0h], 0
0x14000c37f  jmp     short loc_14000C33C
0x14000c381  xor     r8d, r8d; MemoryFlags
0x14000c384  xor     edx, edx; Length
0x14000c386  call    cs:__imp_NdisFreeMemory
0x14000c38d  nop     dword ptr [rax+rax+00h]
0x14000c392  jmp     short loc_14000C35A
```
