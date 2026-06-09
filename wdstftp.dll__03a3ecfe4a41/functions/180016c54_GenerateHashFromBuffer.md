# GenerateHashFromBuffer

- ea: `0x180016c54`
- end: `0x180016e34`
- name: `GenerateHashFromBuffer`
- size: `480`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001dfe0`

## callees

- `0x180016c54`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180016dd4`
- `KERNEL32!HeapFree` at `0x180016dd4`
- `KERNEL32!HeapAlloc` at `0x180016d1f`
- `KERNEL32!HeapAlloc` at `0x180016d1f`
- `KERNEL32!SetLastError` at `0x180016e0d`
- `KERNEL32!SetLastError` at `0x180016e0d`
- `KERNEL32!GetProcessHeap` at `0x180016d08`
- `KERNEL32!GetProcessHeap` at `0x180016dc0`
- `KERNEL32!GetProcessHeap` at `0x180016d08`
- `KERNEL32!GetProcessHeap` at `0x180016dc0`
- `bcrypt!BCryptDestroyHash` at `0x180016db4`
- `bcrypt!BCryptDestroyHash` at `0x180016db4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016de6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016de6`
- `bcrypt!BCryptFinishHash` at `0x180016da2`
- `bcrypt!BCryptFinishHash` at `0x180016da2`
- `bcrypt!BCryptHashData` at `0x180016d82`
- `bcrypt!BCryptHashData` at `0x180016d82`
- `bcrypt!BCryptCreateHash` at `0x180016d63`
- `bcrypt!BCryptCreateHash` at `0x180016d63`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180016cb6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180016cb6`
- `bcrypt!BCryptGetProperty` at `0x180016cef`
- `bcrypt!BCryptGetProperty` at `0x180016cef`
- `ntdll!RtlNtStatusToDosError` at `0x180016dff`
- `ntdll!RtlNtStatusToDosError` at `0x180016dff`

## pseudocode

```c
_BOOL8 __fastcall GenerateHashFromBuffer(PUCHAR pbInput, ULONG cbInput, _QWORD *pbOutput)
{
  signed int Property; // ebx
  ULONG v7; // ebx
  HANDLE ProcessHeap; // rax
  UCHAR *v9; // rsi
  HANDLE v10; // rax
  DWORD v11; // eax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-8h] BYREF
  ULONG pbOutputa; // [rsp+80h] [rbp+30h] BYREF
  ULONG pcbResult; // [rsp+98h] [rbp+48h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pbOutputa = 0;
  if ( !pbInput || !cbInput || !pbOutput )
  {
    Property = -1073741811;
LABEL_15:
    v11 = RtlNtStatusToDosError(Property);
    SetLastError(v11);
    return Property >= 0;
  }
  *pbOutput = 0;
  pbOutput[1] = 0;
  *((_DWORD *)pbOutput + 4) = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 0);
  if ( Property < 0 )
    goto LABEL_15;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutputa, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    v7 = pbOutputa;
    ProcessHeap = GetProcessHeap();
    v9 = (UCHAR *)HeapAlloc(ProcessHeap, 8u, v7);
    Property = v9 == 0 ? 0xC0000017 : 0;
    if ( v9 )
    {
      Property = BCryptCreateHash(phAlgorithm, &phHash, v9, pbOutputa, 0, 0, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( Property >= 0 )
          Property = BCryptFinishHash(phHash, (PUCHAR)pbOutput, 0x14u, 0);
        BCryptDestroyHash(phHash);
      }
      v10 = GetProcessHeap();
      HeapFree(v10, 0, v9);
    }
  }
  BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( Property < 0 )
    goto LABEL_15;
  return Property >= 0;
}

```

## disassembly

```asm
0x180016c54  mov     [rsp-28h+arg_8], rbx
0x180016c59  push    rbp
0x180016c5a  push    rsi
0x180016c5b  push    rdi
0x180016c5c  push    r14
0x180016c5e  push    r15
0x180016c60  mov     rbp, rsp
0x180016c63  sub     rsp, 50h
0x180016c67  and     [rbp+phAlgorithm], 0
0x180016c6c  mov     rdi, r8
0x180016c6f  and     [rbp+phHash], 0
0x180016c74  mov     r14d, edx
0x180016c77  and     [rbp+pbOutput], 0
0x180016c7b  mov     r15, rcx
0x180016c7e  test    rcx, rcx
0x180016c81  jz      loc_180016DF8
0x180016c87  test    edx, edx
0x180016c89  jz      loc_180016DF8
0x180016c8f  test    r8, r8
0x180016c92  jz      loc_180016DF8
0x180016c98  xor     eax, eax
0x180016c9a  lea     rdx, pszAlgId; "SHA1"
0x180016ca1  mov     [r8], rax
0x180016ca4  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180016ca8  mov     [r8+8], rax
0x180016cac  xor     r9d, r9d; dwFlags
0x180016caf  mov     [r8+10h], eax
0x180016cb3  xor     r8d, r8d; pszImplementation
0x180016cb6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180016cbd  nop     dword ptr [rax+rax+00h]
0x180016cc2  mov     ebx, eax
0x180016cc4  test    eax, eax
0x180016cc6  js      loc_180016DFD
0x180016ccc  and     [rsp+50h+var_28], 0
0x180016cd1  lea     rax, [rbp+arg_18]
0x180016cd5  mov     rcx, [rbp+phAlgorithm]; hObject
0x180016cd9  lea     r8, [rbp+pbOutput]; pbOutput
0x180016cdd  mov     r9d, 4; cbOutput
0x180016ce3  mov     [rsp+50h+pcbResult], rax; pbSecret
0x180016ce8  lea     rdx, pszProperty; "ObjectLength"
0x180016cef  call    cs:__imp_BCryptGetProperty
0x180016cf6  nop     dword ptr [rax+rax+00h]
0x180016cfb  mov     ebx, eax
0x180016cfd  test    eax, eax
0x180016cff  js      loc_180016DE0
0x180016d05  mov     ebx, [rbp+pbOutput]
0x180016d08  call    cs:__imp_GetProcessHeap
0x180016d0f  nop     dword ptr [rax+rax+00h]
0x180016d14  mov     r8d, ebx; dwBytes
0x180016d17  mov     edx, 8; dwFlags
0x180016d1c  mov     rcx, rax; hHeap
0x180016d1f  call    cs:__imp_HeapAlloc
0x180016d26  nop     dword ptr [rax+rax+00h]
0x180016d2b  mov     rsi, rax
0x180016d2e  neg     rax
0x180016d31  sbb     ebx, ebx
0x180016d33  not     ebx
0x180016d35  and     ebx, 0C0000017h
0x180016d3b  test    rsi, rsi
0x180016d3e  jz      loc_180016DE0
0x180016d44  and     [rsp+50h+var_20], 0
0x180016d49  lea     rdx, [rbp+phHash]; phHash
0x180016d4d  and     [rsp+50h+var_28], 0
0x180016d52  mov     r8, rsi; pbHashObject
0x180016d55  mov     r9d, [rbp+pbOutput]; cbHashObject
0x180016d59  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180016d5d  and     [rsp+50h+pcbResult], 0
0x180016d63  call    cs:__imp_BCryptCreateHash
0x180016d6a  nop     dword ptr [rax+rax+00h]
0x180016d6f  mov     ebx, eax
0x180016d71  test    eax, eax
0x180016d73  js      short loc_180016DC0
0x180016d75  mov     rcx, [rbp+phHash]; hHash
0x180016d79  xor     r9d, r9d; dwFlags
0x180016d7c  mov     r8d, r14d; cbInput
0x180016d7f  mov     rdx, r15; pbInput
0x180016d82  call    cs:__imp_BCryptHashData
0x180016d89  nop     dword ptr [rax+rax+00h]
0x180016d8e  mov     ebx, eax
0x180016d90  test    eax, eax
0x180016d92  js      short loc_180016DB0
0x180016d94  mov     rcx, [rbp+phHash]; hHash
0x180016d98  xor     r9d, r9d; dwFlags
0x180016d9b  mov     rdx, rdi; pbOutput
0x180016d9e  lea     r8d, [r9+14h]; cbOutput
0x180016da2  call    cs:__imp_BCryptFinishHash
0x180016da9  nop     dword ptr [rax+rax+00h]
0x180016dae  mov     ebx, eax
0x180016db0  mov     rcx, [rbp+phHash]; hHash
0x180016db4  call    cs:__imp_BCryptDestroyHash
0x180016dbb  nop     dword ptr [rax+rax+00h]
0x180016dc0  call    cs:__imp_GetProcessHeap
0x180016dc7  nop     dword ptr [rax+rax+00h]
0x180016dcc  mov     r8, rsi; lpMem
0x180016dcf  xor     edx, edx; dwFlags
0x180016dd1  mov     rcx, rax; hHeap
0x180016dd4  call    cs:__imp_HeapFree
0x180016ddb  nop     dword ptr [rax+rax+00h]
0x180016de0  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180016de4  xor     edx, edx; dwFlags
0x180016de6  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180016ded  nop     dword ptr [rax+rax+00h]
0x180016df2  test    ebx, ebx
0x180016df4  jns     short loc_180016E19
0x180016df6  jmp     short loc_180016DFD
0x180016df8  mov     ebx, 0C000000Dh
0x180016dfd  mov     ecx, ebx; Status
0x180016dff  call    cs:__imp_RtlNtStatusToDosError
0x180016e06  nop     dword ptr [rax+rax+00h]
0x180016e0b  mov     ecx, eax; dwErrCode
0x180016e0d  call    cs:__imp_SetLastError
0x180016e14  nop     dword ptr [rax+rax+00h]
0x180016e19  not     ebx
0x180016e1b  shr     ebx, 1Fh
0x180016e1e  mov     eax, ebx
0x180016e20  mov     rbx, [rsp+50h+arg_8]
0x180016e28  add     rsp, 50h
0x180016e2c  pop     r15
0x180016e2e  pop     r14
0x180016e30  pop     rdi
0x180016e31  pop     rsi
0x180016e32  pop     rbp
0x180016e33  retn
```
