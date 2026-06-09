# AcmGenerateConnectionId

- ea: `0x180007090`
- end: `0x180007151`
- name: `AcmGenerateConnectionId`
- size: `193`
- prototype: `__int64 __fastcall(PUCHAR pbInput)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007090`
- `0x180007320`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800070ea`
- `ntdll!RtlNtStatusToDosError` at `0x18000711f`
- `ntdll!RtlNtStatusToDosError` at `0x1800070ea`
- `ntdll!RtlNtStatusToDosError` at `0x18000711f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007117`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007117`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800070e2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800070e2`

## pseudocode

```c
__int64 __fastcall AcmGenerateConnectionId(PUCHAR pbInput, __int64 a2, _OWORD *a3)
{
  NTSTATUS v6; // eax
  unsigned int ConnectionHashId; // ebp
  NTSTATUS v8; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+30h] [rbp+8h] BYREF

  phAlgorithm = 0;
  if ( !pbInput || !a2 || !a3 )
    return 87;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 8u);
  ConnectionHashId = RtlNtStatusToDosError(v6);
  if ( !ConnectionHashId )
    ConnectionHashId = AcmGenerateConnectionHashId(phAlgorithm, pbInput, a2, a3);
  if ( phAlgorithm )
  {
    v8 = BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    RtlNtStatusToDosError(v8);
  }
  return ConnectionHashId;
}

```

## disassembly

```asm
0x180007090  mov     [rsp+arg_10], rbx
0x180007095  mov     [rsp+arg_18], rsi
0x18000709a  push    rdi
0x18000709b  sub     rsp, 20h
0x18000709f  mov     [rsp+28h+phAlgorithm], 0
0x1800070a8  mov     rdi, r8
0x1800070ab  mov     rsi, rdx
0x1800070ae  mov     rbx, rcx
0x1800070b1  test    rcx, rcx
0x1800070b4  jz      loc_18000713C
0x1800070ba  test    rdx, rdx
0x1800070bd  jz      short loc_18000713C
0x1800070bf  test    r8, r8
0x1800070c2  jz      short loc_18000713C
0x1800070c4  mov     r9d, 8; dwFlags
0x1800070ca  mov     [rsp+28h+arg_8], rbp
0x1800070cf  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800070d6  lea     rdx, pszAlgId; "SHA256"
0x1800070dd  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x1800070e2  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800070e8  mov     ecx, eax; Status
0x1800070ea  call    cs:__imp_RtlNtStatusToDosError
0x1800070f0  mov     ebp, eax
0x1800070f2  test    eax, eax
0x1800070f4  jnz     short loc_18000710B
0x1800070f6  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1800070fb  mov     r9, rdi
0x1800070fe  mov     r8, rsi
0x180007101  mov     rdx, rbx; pbInput
0x180007104  call    AcmGenerateConnectionHashId
0x180007109  mov     ebp, eax
0x18000710b  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x180007110  test    rcx, rcx
0x180007113  jz      short loc_180007125
0x180007115  xor     edx, edx; dwFlags
0x180007117  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000711d  mov     ecx, eax; Status
0x18000711f  call    cs:__imp_RtlNtStatusToDosError
0x180007125  mov     eax, ebp
0x180007127  mov     rbp, [rsp+28h+arg_8]
0x18000712c  mov     rbx, [rsp+28h+arg_10]
0x180007131  mov     rsi, [rsp+28h+arg_18]
0x180007136  add     rsp, 20h
0x18000713a  pop     rdi
0x18000713b  retn
0x18000713c  mov     rbx, [rsp+28h+arg_10]
0x180007141  mov     eax, 57h ; 'W'
0x180007146  mov     rsi, [rsp+28h+arg_18]
0x18000714b  add     rsp, 20h
0x18000714f  pop     rdi
0x180007150  retn
```
