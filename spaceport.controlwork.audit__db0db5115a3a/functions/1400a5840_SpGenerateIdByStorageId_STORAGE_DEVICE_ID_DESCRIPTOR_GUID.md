# SpGenerateIdByStorageId(_STORAGE_DEVICE_ID_DESCRIPTOR *,_GUID *)

- ea: `0x1400a5840`
- end: `0x1400a595a`
- name: `?SpGenerateIdByStorageId@@YAJPEAU_STORAGE_DEVICE_ID_DESCRIPTOR@@PEAU_GUID@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct _STORAGE_DEVICE_ID_DESCRIPTOR *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400905a8`

## callees

- `0x140067fc0`
- `0x1400a577c`
- `0x1400a5840`

## import_xrefs

- `cng!BCryptDestroyHash` at `0x1400a591c`
- `cng!BCryptDestroyHash` at `0x1400a591c`
- `cng!BCryptHashData` at `0x1400a58dc`
- `cng!BCryptHashData` at `0x1400a58dc`
- `cng!BCryptCreateHash` at `0x1400a58b2`
- `cng!BCryptCreateHash` at `0x1400a58b2`
- `cng!BCryptFinishHash` at `0x1400a5902`
- `cng!BCryptFinishHash` at `0x1400a5902`

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
0x1400a5840  mov     [rsp+arg_10], rbx
0x1400a5845  push    rsi
0x1400a5846  push    rdi
0x1400a5847  push    r14
0x1400a5849  sub     rsp, 60h
0x1400a584d  mov     rax, cs:__security_cookie
0x1400a5854  xor     rax, rsp
0x1400a5857  mov     [rsp+78h+var_20], rax
0x1400a585c  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1400a5863  xor     eax, eax
0x1400a5865  mov     rsi, rdx
0x1400a5868  xorps   xmm0, xmm0
0x1400a586b  mov     [rsp+78h+var_28], rax
0x1400a5870  movdqu  xmmword ptr [rdx], xmm1
0x1400a5874  movups  xmmword ptr [rsp+78h+phHash], xmm0
0x1400a5879  test    rcx, rcx
0x1400a587c  jnz     short loc_1400A5888
0x1400a587e  mov     ebx, 0C0000225h
0x1400a5883  jmp     loc_1400A5939
0x1400a5888  call    ?SpFindStorageId@@YAPEAU_STORAGE_IDENTIFIER@@PEAU_STORAGE_DEVICE_ID_DESCRIPTOR@@@Z; SpFindStorageId(_STORAGE_DEVICE_ID_DESCRIPTOR *)
0x1400a588d  mov     rdi, rax
0x1400a5890  test    rax, rax
0x1400a5893  jz      short loc_1400A587E
0x1400a5895  xor     ebx, ebx
0x1400a5897  lea     rdx, [rsp+78h+phHash]; phHash
0x1400a589c  mov     [rsp+78h+dwFlags], ebx; dwFlags
0x1400a58a0  xor     r9d, r9d; cbHashObject
0x1400a58a3  mov     [rsp+78h+cbSecret], ebx; cbSecret
0x1400a58a7  xor     r8d, r8d; pbHashObject
0x1400a58aa  mov     [rsp+78h+pbSecret], rbx; pbSecret
0x1400a58af  lea     ecx, [rbx+21h]; hAlgorithm
0x1400a58b2  call    cs:__imp_BCryptCreateHash
0x1400a58b9  nop     dword ptr [rax+rax+00h]
0x1400a58be  lea     r14d, [rbx+7]
0x1400a58c2  test    eax, eax
0x1400a58c4  jns     short loc_1400A58CB
0x1400a58c6  mov     ecx, r14d
0x1400a58c9  int     29h; Win8: RtlFailFast(ecx)
0x1400a58cb  movzx   r8d, word ptr [rdi+8]; cbInput
0x1400a58d0  lea     rdx, [rdi+10h]; pbInput
0x1400a58d4  mov     rcx, [rsp+78h+phHash]; hHash
0x1400a58d9  xor     r9d, r9d; dwFlags
0x1400a58dc  call    cs:__imp_BCryptHashData
0x1400a58e3  nop     dword ptr [rax+rax+00h]
0x1400a58e8  test    eax, eax
0x1400a58ea  jns     short loc_1400A58F1
0x1400a58ec  mov     rcx, r14
0x1400a58ef  int     29h; Win8: RtlFailFast(ecx)
0x1400a58f1  mov     rcx, [rsp+78h+phHash]; hHash
0x1400a58f6  lea     rdx, [rsp+78h+phHash+8]; pbOutput
0x1400a58fb  xor     r9d, r9d; dwFlags
0x1400a58fe  lea     r8d, [r9+10h]; cbOutput
0x1400a5902  call    cs:__imp_BCryptFinishHash
0x1400a5909  nop     dword ptr [rax+rax+00h]
0x1400a590e  test    eax, eax
0x1400a5910  jns     short loc_1400A5917
0x1400a5912  mov     rcx, r14
0x1400a5915  int     29h; Win8: RtlFailFast(ecx)
0x1400a5917  mov     rcx, [rsp+78h+phHash]; hHash
0x1400a591c  call    cs:__imp_BCryptDestroyHash
0x1400a5923  nop     dword ptr [rax+rax+00h]
0x1400a5928  mov     rcx, [rsp+78h+phHash+8]
0x1400a592d  mov     [rsi], rcx
0x1400a5930  mov     rcx, [rsp+78h+var_28]
0x1400a5935  mov     [rsi+8], rcx
0x1400a5939  mov     eax, ebx
0x1400a593b  mov     rcx, [rsp+78h+var_20]
0x1400a5940  xor     rcx, rsp; StackCookie
0x1400a5943  call    __security_check_cookie
0x1400a5948  mov     rbx, [rsp+78h+arg_10]
0x1400a5950  add     rsp, 60h
0x1400a5954  pop     r14
0x1400a5956  pop     rdi
0x1400a5957  pop     rsi
0x1400a5958  retn
```
