# SmbCryptoHashCreate

- ea: `0x140054b30`
- end: `0x140054c17`
- name: `SmbCryptoHashCreate`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140054b30`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140054b8a`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140054b8a`
- `ntoskrnl!ExAllocatePool2` at `0x140054b56`
- `ntoskrnl!ExAllocatePool2` at `0x140054b56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054bea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054bea`
- `ksecdd!BCryptCreateHash` at `0x140054bc9`
- `ksecdd!BCryptCreateHash` at `0x140054bc9`

## pseudocode

```c
__int64 __fastcall SmbCryptoHashCreate(BCRYPT_HASH_HANDLE **a1, int a2, char a3)
{
  __int64 Pool2; // rax
  BCRYPT_HASH_HANDLE *v6; // rdi
  NTSTATUS Hash; // ebx

  if ( a2 == 1 )
  {
    Pool2 = ExAllocatePool2(66, 16, 590500684);
    v6 = (BCRYPT_HASH_HANDLE *)Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)(Pool2 + 8) = &SmbCryptoHashAlgorithms;
      Hash = RtlRunOnceExecuteOnce(&RunOnce, SmbCryptoHashAlgorithmInitialize, &SmbCryptoHashAlgorithms, 0);
      if ( Hash >= 0 )
      {
        Hash = BCryptCreateHash(SmbCryptoHashAlgorithms, v6, 0, 0, 0, 0, a3 != 0 ? 0x20 : 0);
        if ( Hash >= 0 )
        {
          *a1 = v6;
          return 0;
        }
      }
      ExFreePoolWithTag(v6, 0x2332534Cu);
    }
    else
    {
      Hash = -1073741670;
    }
  }
  else
  {
    Hash = -1073741811;
  }
  *a1 = 0;
  return (unsigned int)Hash;
}

```

## disassembly

```asm
0x140054b30  push    rbx
0x140054b32  push    rbp
0x140054b33  push    rsi
0x140054b34  push    rdi
0x140054b35  sub     rsp, 48h
0x140054b39  mov     bpl, r8b
0x140054b3c  mov     rsi, rcx
0x140054b3f  cmp     edx, 1
0x140054b42  jnz     loc_140054C10
0x140054b48  mov     edx, 10h
0x140054b4d  mov     r8d, 2332534Ch
0x140054b53  lea     ecx, [rdx+32h]
0x140054b56  call    cs:__imp_ExAllocatePool2
0x140054b5d  nop     dword ptr [rax+rax+00h]
0x140054b62  mov     rdi, rax
0x140054b65  test    rax, rax
0x140054b68  jz      loc_140054C09
0x140054b6e  lea     r8, SmbCryptoHashAlgorithms; Parameter
0x140054b75  xor     r9d, r9d; Context
0x140054b78  lea     rdx, SmbCryptoHashAlgorithmInitialize; InitFn
0x140054b7f  mov     [rax+8], r8
0x140054b83  lea     rcx, RunOnce; RunOnce
0x140054b8a  call    cs:__imp_RtlRunOnceExecuteOnce
0x140054b91  nop     dword ptr [rax+rax+00h]
0x140054b96  mov     ebx, eax
0x140054b98  test    eax, eax
0x140054b9a  js      short loc_140054BE2
0x140054b9c  mov     rcx, cs:SmbCryptoHashAlgorithms; hAlgorithm
0x140054ba3  neg     bpl
0x140054ba6  mov     rdx, rdi; phHash
0x140054ba9  sbb     eax, eax
0x140054bab  xor     r9d, r9d; cbHashObject
0x140054bae  and     eax, 20h
0x140054bb1  xor     r8d, r8d; pbHashObject
0x140054bb4  mov     [rsp+68h+dwFlags], eax; dwFlags
0x140054bb8  mov     [rsp+68h+cbSecret], 0; cbSecret
0x140054bc0  mov     [rsp+68h+pbSecret], 0; pbSecret
0x140054bc9  call    cs:__imp_BCryptCreateHash
0x140054bd0  nop     dword ptr [rax+rax+00h]
0x140054bd5  mov     ebx, eax
0x140054bd7  test    eax, eax
0x140054bd9  js      short loc_140054BE2
0x140054bdb  mov     [rsi], rdi
0x140054bde  xor     eax, eax
0x140054be0  jmp     short loc_140054BFF
0x140054be2  mov     edx, 2332534Ch; Tag
0x140054be7  mov     rcx, rdi; P
0x140054bea  call    cs:__imp_ExFreePoolWithTag
0x140054bf1  nop     dword ptr [rax+rax+00h]
0x140054bf6  mov     qword ptr [rsi], 0
0x140054bfd  mov     eax, ebx
0x140054bff  add     rsp, 48h
0x140054c03  pop     rdi
0x140054c04  pop     rsi
0x140054c05  pop     rbp
0x140054c06  pop     rbx
0x140054c07  retn
0x140054c09  mov     ebx, 0C000009Ah
0x140054c0e  jmp     short loc_140054BF6
0x140054c10  mov     ebx, 0C000000Dh
0x140054c15  jmp     short loc_140054BF6
```
