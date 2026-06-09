# SpGenerateIdByStorageId(_STORAGE_DEVICE_ID_DESCRIPTOR *,_GUID *)

- ea: `0x1400a5970`
- end: `0x1400a5a8a`
- name: `?SpGenerateIdByStorageId@@YAJPEAU_STORAGE_DEVICE_ID_DESCRIPTOR@@PEAU_GUID@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct _STORAGE_DEVICE_ID_DESCRIPTOR *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400905a8`

## callees

- `0x140068110`
- `0x1400a58ac`
- `0x1400a5970`

## import_xrefs

- `cng!BCryptDestroyHash` at `0x1400a5a4c`
- `cng!BCryptDestroyHash` at `0x1400a5a4c`
- `cng!BCryptHashData` at `0x1400a5a0c`
- `cng!BCryptHashData` at `0x1400a5a0c`
- `cng!BCryptCreateHash` at `0x1400a59e2`
- `cng!BCryptCreateHash` at `0x1400a59e2`
- `cng!BCryptFinishHash` at `0x1400a5a32`
- `cng!BCryptFinishHash` at `0x1400a5a32`

## pseudocode

```c
__int64 __fastcall SpGenerateIdByStorageId(struct _STORAGE_DEVICE_ID_DESCRIPTOR *a1, struct _GUID *a2)
{
  unsigned int v3; // ebx
  struct _STORAGE_IDENTIFIER *StorageId; // rdi
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v7; // [rsp+50h] [rbp-28h]

  v7 = 0;
  *a2 = GUID_NULL;
  *(_OWORD *)phHash = 0;
  if ( a1 && (StorageId = SpFindStorageId(a1)) != 0 )
  {
    v3 = 0;
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash[0], StorageId->Identifier, StorageId->IdentifierSize, 0) < 0 )
      __fastfail(7u);
    if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
      __fastfail(7u);
    BCryptDestroyHash(phHash[0]);
    *(BCRYPT_HASH_HANDLE *)&a2->Data1 = phHash[1];
    *(_QWORD *)a2->Data4 = v7;
  }
  else
  {
    return (unsigned int)-1073741275;
  }
  return v3;
}

```

## disassembly

```asm
0x1400a5970  mov     [rsp+arg_10], rbx
0x1400a5975  push    rsi
0x1400a5976  push    rdi
0x1400a5977  push    r14
0x1400a5979  sub     rsp, 60h
0x1400a597d  mov     rax, cs:__security_cookie
0x1400a5984  xor     rax, rsp
0x1400a5987  mov     [rsp+78h+var_20], rax
0x1400a598c  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1400a5993  xor     eax, eax
0x1400a5995  mov     rsi, rdx
0x1400a5998  xorps   xmm0, xmm0
0x1400a599b  mov     [rsp+78h+var_28], rax
0x1400a59a0  movdqu  xmmword ptr [rdx], xmm1
0x1400a59a4  movups  xmmword ptr [rsp+78h+phHash], xmm0
0x1400a59a9  test    rcx, rcx
0x1400a59ac  jnz     short loc_1400A59B8
0x1400a59ae  mov     ebx, 0C0000225h
0x1400a59b3  jmp     loc_1400A5A69
0x1400a59b8  call    ?SpFindStorageId@@YAPEAU_STORAGE_IDENTIFIER@@PEAU_STORAGE_DEVICE_ID_DESCRIPTOR@@@Z; SpFindStorageId(_STORAGE_DEVICE_ID_DESCRIPTOR *)
0x1400a59bd  mov     rdi, rax
0x1400a59c0  test    rax, rax
0x1400a59c3  jz      short loc_1400A59AE
0x1400a59c5  xor     ebx, ebx
0x1400a59c7  lea     rdx, [rsp+78h+phHash]; phHash
0x1400a59cc  mov     [rsp+78h+dwFlags], ebx; dwFlags
0x1400a59d0  xor     r9d, r9d; cbHashObject
0x1400a59d3  mov     [rsp+78h+cbSecret], ebx; cbSecret
0x1400a59d7  xor     r8d, r8d; pbHashObject
0x1400a59da  mov     [rsp+78h+pbSecret], rbx; pbSecret
0x1400a59df  lea     ecx, [rbx+21h]; hAlgorithm
0x1400a59e2  call    cs:__imp_BCryptCreateHash
0x1400a59e9  nop     dword ptr [rax+rax+00h]
0x1400a59ee  lea     r14d, [rbx+7]
0x1400a59f2  test    eax, eax
0x1400a59f4  jns     short loc_1400A59FB
0x1400a59f6  mov     ecx, r14d
0x1400a59f9  int     29h; Win8: RtlFailFast(ecx)
0x1400a59fb  movzx   r8d, word ptr [rdi+8]; cbInput
0x1400a5a00  lea     rdx, [rdi+10h]; pbInput
0x1400a5a04  mov     rcx, [rsp+78h+phHash]; hHash
0x1400a5a09  xor     r9d, r9d; dwFlags
0x1400a5a0c  call    cs:__imp_BCryptHashData
0x1400a5a13  nop     dword ptr [rax+rax+00h]
0x1400a5a18  test    eax, eax
0x1400a5a1a  jns     short loc_1400A5A21
0x1400a5a1c  mov     rcx, r14
0x1400a5a1f  int     29h; Win8: RtlFailFast(ecx)
0x1400a5a21  mov     rcx, [rsp+78h+phHash]; hHash
0x1400a5a26  lea     rdx, [rsp+78h+phHash+8]; pbOutput
0x1400a5a2b  xor     r9d, r9d; dwFlags
0x1400a5a2e  lea     r8d, [r9+10h]; cbOutput
0x1400a5a32  call    cs:__imp_BCryptFinishHash
0x1400a5a39  nop     dword ptr [rax+rax+00h]
0x1400a5a3e  test    eax, eax
0x1400a5a40  jns     short loc_1400A5A47
0x1400a5a42  mov     rcx, r14
0x1400a5a45  int     29h; Win8: RtlFailFast(ecx)
0x1400a5a47  mov     rcx, [rsp+78h+phHash]; hHash
0x1400a5a4c  call    cs:__imp_BCryptDestroyHash
0x1400a5a53  nop     dword ptr [rax+rax+00h]
0x1400a5a58  mov     rcx, [rsp+78h+phHash+8]
0x1400a5a5d  mov     [rsi], rcx
0x1400a5a60  mov     rcx, [rsp+78h+var_28]
0x1400a5a65  mov     [rsi+8], rcx
0x1400a5a69  mov     eax, ebx
0x1400a5a6b  mov     rcx, [rsp+78h+var_20]
0x1400a5a70  xor     rcx, rsp; StackCookie
0x1400a5a73  call    __security_check_cookie
0x1400a5a78  mov     rbx, [rsp+78h+arg_10]
0x1400a5a80  add     rsp, 60h
0x1400a5a84  pop     r14
0x1400a5a86  pop     rdi
0x1400a5a87  pop     rsi
0x1400a5a88  retn
```
