# WinNatInitializeBindingState

- ea: `0x14001a558`
- end: `0x14001a64f`
- name: `WinNatInitializeBindingState`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018e4c`

## callees

- `0x14000d604`
- `0x14000d898`
- `0x14001a558`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14001a5ba`
- `ntoskrnl!RtlCreateHashTable` at `0x14001a5df`
- `ntoskrnl!RtlCreateHashTable` at `0x14001a5ba`
- `ntoskrnl!RtlCreateHashTable` at `0x14001a5df`
- `NETIO!RtlInitializeToeplitzHash` at `0x14001a625`
- `NETIO!RtlInitializeToeplitzHash` at `0x14001a625`
- `ksecdd!BCryptGenRandom` at `0x14001a605`
- `ksecdd!BCryptGenRandom` at `0x14001a605`

## pseudocode

```c
NTSTATUS __fastcall WinNatInitializeBindingState(__int64 a1, int a2, int a3, int a4)
{
  __int64 LookasideList; // rax
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rax
  NTSTATUS result; // eax
  int v12; // [rsp+20h] [rbp-38h]
  int v13; // [rsp+20h] [rbp-38h]
  int v14; // [rsp+38h] [rbp-20h]
  int v15; // [rsp+38h] [rbp-20h]

  LookasideList = PplCreateLookasideList(a1, a2, a3, a4, v12, 0x98u, 0x65624C57u, v14, 0x65624C57u);
  *(_QWORD *)a1 = LookasideList;
  if ( !LookasideList )
    return -1073741670;
  v10 = PplCreateLookasideList(v7, v6, v8, v9, v13, 0x8Cu, 0x65624C57u, v15, 0x65624C57u);
  *(_QWORD *)(a1 + 8) = v10;
  if ( !v10 )
    return -1073741670;
  if ( !RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)(a1 + 392), 0, 0) )
    return -1073741670;
  RtlInitializeScalableMrswLock(a1 + 64);
  if ( !RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), 0, 0) )
    return -1073741670;
  result = BCryptGenRandom(0, (PUCHAR)(a1 + 424), 0x28u, 2u);
  if ( result >= 0 )
    return (unsigned __int8)RtlInitializeToeplitzHash(a1 + 400, a1 + 424, 40) == 0 ? 0xC0000001 : 0;
  return result;
}

```

## disassembly

```asm
0x14001a558  mov     rax, rsp
0x14001a55b  mov     [rax+8], rbx
0x14001a55f  push    rdi
0x14001a560  sub     rsp, 50h
0x14001a564  mov     edi, 65624C57h
0x14001a569  mov     rbx, rcx
0x14001a56c  mov     [rax-18h], edi
0x14001a56f  mov     [rax-28h], edi
0x14001a572  mov     qword ptr [rax-30h], 98h
0x14001a57a  call    PplCreateLookasideList
0x14001a57f  mov     [rbx], rax
0x14001a582  test    rax, rax
0x14001a585  jz      loc_14001A63E
0x14001a58b  mov     [rsp+58h+var_18], edi; ULONG
0x14001a58f  mov     [rsp+58h+var_28], edi; ULONG
0x14001a593  mov     [rsp+58h+var_30], 8Ch; SIZE_T
0x14001a59c  call    PplCreateLookasideList
0x14001a5a1  mov     [rbx+8], rax
0x14001a5a5  test    rax, rax
0x14001a5a8  jz      loc_14001A63E
0x14001a5ae  lea     rcx, [rbx+188h]; HashTable
0x14001a5b5  xor     r8d, r8d; Flags
0x14001a5b8  xor     edx, edx; Shift
0x14001a5ba  call    cs:__imp_RtlCreateHashTable
0x14001a5c1  nop     dword ptr [rax+rax+00h]
0x14001a5c6  test    al, al
0x14001a5c8  jz      short loc_14001A63E
0x14001a5ca  lea     rcx, [rbx+40h]
0x14001a5ce  call    RtlInitializeScalableMrswLock
0x14001a5d3  lea     rcx, [rbx+180h]; HashTable
0x14001a5da  xor     r8d, r8d; Flags
0x14001a5dd  xor     edx, edx; Shift
0x14001a5df  call    cs:__imp_RtlCreateHashTable
0x14001a5e6  nop     dword ptr [rax+rax+00h]
0x14001a5eb  test    al, al
0x14001a5ed  jz      short loc_14001A63E
0x14001a5ef  mov     r9d, 2; dwFlags
0x14001a5f5  lea     rdi, [rbx+1A8h]
0x14001a5fc  mov     rdx, rdi; pbBuffer
0x14001a5ff  xor     ecx, ecx; hAlgorithm
0x14001a601  lea     r8d, [r9+26h]; cbBuffer
0x14001a605  call    cs:__imp_BCryptGenRandom
0x14001a60c  nop     dword ptr [rax+rax+00h]
0x14001a611  test    eax, eax
0x14001a613  js      short loc_14001A643
0x14001a615  lea     rcx, [rbx+190h]
0x14001a61c  mov     r8d, 28h ; '('
0x14001a622  mov     rdx, rdi
0x14001a625  call    cs:__imp_RtlInitializeToeplitzHash
0x14001a62c  nop     dword ptr [rax+rax+00h]
0x14001a631  neg     al
0x14001a633  sbb     eax, eax
0x14001a635  not     eax
0x14001a637  and     eax, 0C0000001h
0x14001a63c  jmp     short loc_14001A643
0x14001a63e  mov     eax, 0C000009Ah
0x14001a643  mov     rbx, [rsp+58h+arg_0]
0x14001a648  add     rsp, 50h
0x14001a64c  pop     rdi
0x14001a64d  retn
```
