# WinNatInitializeBindingState

- ea: `0x14001a078`
- end: `0x14001a16f`
- name: `WinNatInitializeBindingState`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001896c`

## callees

- `0x14000d634`
- `0x14000d8c8`
- `0x14001a078`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14001a0da`
- `ntoskrnl!RtlCreateHashTable` at `0x14001a0ff`
- `ntoskrnl!RtlCreateHashTable` at `0x14001a0da`
- `ntoskrnl!RtlCreateHashTable` at `0x14001a0ff`
- `NETIO!RtlInitializeToeplitzHash` at `0x14001a145`
- `NETIO!RtlInitializeToeplitzHash` at `0x14001a145`
- `ksecdd!BCryptGenRandom` at `0x14001a125`
- `ksecdd!BCryptGenRandom` at `0x14001a125`

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
0x14001a078  mov     rax, rsp
0x14001a07b  mov     [rax+8], rbx
0x14001a07f  push    rdi
0x14001a080  sub     rsp, 50h
0x14001a084  mov     edi, 65624C57h
0x14001a089  mov     rbx, rcx
0x14001a08c  mov     [rax-18h], edi
0x14001a08f  mov     [rax-28h], edi
0x14001a092  mov     qword ptr [rax-30h], 98h
0x14001a09a  call    PplCreateLookasideList
0x14001a09f  mov     [rbx], rax
0x14001a0a2  test    rax, rax
0x14001a0a5  jz      loc_14001A15E
0x14001a0ab  mov     [rsp+58h+var_18], edi; ULONG
0x14001a0af  mov     [rsp+58h+var_28], edi; ULONG
0x14001a0b3  mov     [rsp+58h+var_30], 8Ch; SIZE_T
0x14001a0bc  call    PplCreateLookasideList
0x14001a0c1  mov     [rbx+8], rax
0x14001a0c5  test    rax, rax
0x14001a0c8  jz      loc_14001A15E
0x14001a0ce  lea     rcx, [rbx+188h]; HashTable
0x14001a0d5  xor     r8d, r8d; Flags
0x14001a0d8  xor     edx, edx; Shift
0x14001a0da  call    cs:__imp_RtlCreateHashTable
0x14001a0e1  nop     dword ptr [rax+rax+00h]
0x14001a0e6  test    al, al
0x14001a0e8  jz      short loc_14001A15E
0x14001a0ea  lea     rcx, [rbx+40h]
0x14001a0ee  call    RtlInitializeScalableMrswLock
0x14001a0f3  lea     rcx, [rbx+180h]; HashTable
0x14001a0fa  xor     r8d, r8d; Flags
0x14001a0fd  xor     edx, edx; Shift
0x14001a0ff  call    cs:__imp_RtlCreateHashTable
0x14001a106  nop     dword ptr [rax+rax+00h]
0x14001a10b  test    al, al
0x14001a10d  jz      short loc_14001A15E
0x14001a10f  mov     r9d, 2; dwFlags
0x14001a115  lea     rdi, [rbx+1A8h]
0x14001a11c  mov     rdx, rdi; pbBuffer
0x14001a11f  xor     ecx, ecx; hAlgorithm
0x14001a121  lea     r8d, [r9+26h]; cbBuffer
0x14001a125  call    cs:__imp_BCryptGenRandom
0x14001a12c  nop     dword ptr [rax+rax+00h]
0x14001a131  test    eax, eax
0x14001a133  js      short loc_14001A163
0x14001a135  lea     rcx, [rbx+190h]
0x14001a13c  mov     r8d, 28h ; '('
0x14001a142  mov     rdx, rdi
0x14001a145  call    cs:__imp_RtlInitializeToeplitzHash
0x14001a14c  nop     dword ptr [rax+rax+00h]
0x14001a151  neg     al
0x14001a153  sbb     eax, eax
0x14001a155  not     eax
0x14001a157  and     eax, 0C0000001h
0x14001a15c  jmp     short loc_14001A163
0x14001a15e  mov     eax, 0C000009Ah
0x14001a163  mov     rbx, [rsp+58h+arg_0]
0x14001a168  add     rsp, 50h
0x14001a16c  pop     rdi
0x14001a16d  retn
```
