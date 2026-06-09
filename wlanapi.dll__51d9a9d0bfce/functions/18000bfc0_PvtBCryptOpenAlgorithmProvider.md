# PvtBCryptOpenAlgorithmProvider

- ea: `0x18000bfc0`
- end: `0x18000bfeb`
- name: `PvtBCryptOpenAlgorithmProvider`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d6b0`
- `0x18003d724`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000bfe4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000bfd8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000bfd8`

## pseudocode

```c
ULONG __fastcall PvtBCryptOpenAlgorithmProvider(BCRYPT_ALG_HANDLE *a1)
{
  NTSTATUS v1; // eax

  v1 = BCryptOpenAlgorithmProvider(a1, L"SHA256", L"Microsoft Primitive Provider", 8u);
  return RtlNtStatusToDosError(v1);
}

```

## disassembly

```asm
0x18000bfc0  sub     rsp, 28h
0x18000bfc4  mov     r9d, 8; dwFlags
0x18000bfca  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18000bfd1  lea     rdx, pszAlgId; "SHA256"
0x18000bfd8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000bfde  mov     ecx, eax
0x18000bfe0  add     rsp, 28h
0x18000bfe4  jmp     cs:__imp_RtlNtStatusToDosError
```
