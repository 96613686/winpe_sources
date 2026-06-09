# SkpCngPrepareHashObj

- ea: `0x1400c1eec`
- end: `0x1400c201a`
- name: `SkpCngPrepareHashObj`
- size: `302`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, BCRYPT_ALG_HANDLE *phAlgorithm)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14006a19c`
- `0x14006b310`
- `0x1400c1e60`
- `0x1400c592c`

## callees

- `0x14000f0f0`
- `0x140037e68`
- `0x1400c1eec`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x1400c1f1f`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400c1f1f`
- `cng!BCryptCreateHash` at `0x1400c1fb7`
- `cng!BCryptCreateHash` at `0x1400c1fb7`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c1ffb`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c1ffb`
- `cng!BCryptDestroyHash` at `0x1400c1fd2`
- `cng!BCryptDestroyHash` at `0x1400c1fd2`
- `cng!BCryptGetProperty` at `0x1400c1f5d`
- `cng!BCryptGetProperty` at `0x1400c1f5d`

## pseudocode

```c
__int64 __fastcall SkpCngPrepareHashObj(LPCWSTR pszAlgId, BCRYPT_ALG_HANDLE *phAlgorithm)
{
  NTSTATUS Property; // edi
  ULONG *v4; // rsi
  void *Pool; // rax
  BCRYPT_ALG_HANDLE v6; // rcx
  BCRYPT_ALG_HANDLE v7; // rdx
  ULONG cbOutput; // [rsp+58h] [rbp+10h] BYREF

  cbOutput = 4;
  *(_OWORD *)phAlgorithm = 0;
  *((_OWORD *)phAlgorithm + 1) = 0;
  Property = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, 0, 1u);
  if ( Property >= 0 )
  {
    v4 = (ULONG *)(phAlgorithm + 3);
    Property = BCryptGetProperty(*phAlgorithm, L"ObjectLength", (PUCHAR)phAlgorithm + 24, cbOutput, &cbOutput, 0);
    if ( Property >= 0 )
    {
      Pool = (void *)SkAllocatePool(512, *v4);
      phAlgorithm[2] = Pool;
      if ( Pool )
      {
        Property = BCryptCreateHash(*phAlgorithm, phAlgorithm + 1, (PUCHAR)Pool, *v4, 0, 0, 0);
        if ( Property >= 0 )
          return (unsigned int)Property;
      }
      else
      {
        Property = -1073741670;
      }
    }
  }
  v6 = phAlgorithm[1];
  if ( v6 )
    BCryptDestroyHash(v6);
  v7 = phAlgorithm[2];
  if ( v7 )
    SkFreePool(512, v7);
  if ( *phAlgorithm )
    BCryptCloseAlgorithmProvider(*phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1400c1eec  mov     [rsp+arg_0], rbx
0x1400c1ef1  mov     [rsp+arg_10], rsi
0x1400c1ef6  push    rdi
0x1400c1ef7  sub     rsp, 40h
0x1400c1efb  xorps   xmm0, xmm0
0x1400c1efe  mov     [rsp+48h+cbOutput], 4
0x1400c1f06  movups  xmmword ptr [rdx], xmm0
0x1400c1f09  mov     rbx, rdx
0x1400c1f0c  mov     r9d, 1; dwFlags
0x1400c1f12  movups  xmmword ptr [rdx+10h], xmm0
0x1400c1f16  mov     rdx, rcx; pszAlgId
0x1400c1f19  xor     r8d, r8d; pszImplementation
0x1400c1f1c  mov     rcx, rbx; phAlgorithm
0x1400c1f1f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400c1f26  nop     dword ptr [rax+rax+00h]
0x1400c1f2b  mov     edi, eax
0x1400c1f2d  test    eax, eax
0x1400c1f2f  js      loc_1400C1FC9
0x1400c1f35  mov     r9d, [rsp+48h+cbOutput]; cbOutput
0x1400c1f3a  lea     rax, [rsp+48h+cbOutput]
0x1400c1f3f  mov     rcx, [rbx]; hObject
0x1400c1f42  lea     rsi, [rbx+18h]
0x1400c1f46  mov     r8, rsi; pbOutput
0x1400c1f49  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1400c1f51  lea     rdx, pszProperty; "ObjectLength"
0x1400c1f58  mov     [rsp+48h+pcbResult], rax; pcbResult
0x1400c1f5d  call    cs:__imp_BCryptGetProperty
0x1400c1f64  nop     dword ptr [rax+rax+00h]
0x1400c1f69  mov     edi, eax
0x1400c1f6b  test    eax, eax
0x1400c1f6d  js      short loc_1400C1FC9
0x1400c1f6f  mov     edx, [rsi]
0x1400c1f71  mov     ecx, 200h
0x1400c1f76  mov     r8d, 57474E43h
0x1400c1f7c  call    SkAllocatePool
0x1400c1f81  mov     [rbx+10h], rax
0x1400c1f85  test    rax, rax
0x1400c1f88  jnz     short loc_1400C1F91
0x1400c1f8a  mov     edi, 0C000009Ah
0x1400c1f8f  jmp     short loc_1400C1FC9
0x1400c1f91  mov     r9d, [rsi]; cbHashObject
0x1400c1f94  lea     rdx, [rbx+8]; phHash
0x1400c1f98  mov     rcx, [rbx]; hAlgorithm
0x1400c1f9b  mov     r8, rax; pbHashObject
0x1400c1f9e  mov     [rsp+48h+var_18], 0; dwFlags
0x1400c1fa6  mov     [rsp+48h+dwFlags], 0; cbSecret
0x1400c1fae  mov     [rsp+48h+pcbResult], 0; pbSecret
0x1400c1fb7  call    cs:__imp_BCryptCreateHash
0x1400c1fbe  nop     dword ptr [rax+rax+00h]
0x1400c1fc3  mov     edi, eax
0x1400c1fc5  test    eax, eax
0x1400c1fc7  jns     short loc_1400C2007
0x1400c1fc9  mov     rcx, [rbx+8]; hHash
0x1400c1fcd  test    rcx, rcx
0x1400c1fd0  jz      short loc_1400C1FDE
0x1400c1fd2  call    cs:__imp_BCryptDestroyHash
0x1400c1fd9  nop     dword ptr [rax+rax+00h]
0x1400c1fde  mov     rdx, [rbx+10h]
0x1400c1fe2  test    rdx, rdx
0x1400c1fe5  jz      short loc_1400C1FF1
0x1400c1fe7  mov     ecx, 200h
0x1400c1fec  call    SkFreePool
0x1400c1ff1  mov     rcx, [rbx]; hAlgorithm
0x1400c1ff4  test    rcx, rcx
0x1400c1ff7  jz      short loc_1400C2007
0x1400c1ff9  xor     edx, edx; dwFlags
0x1400c1ffb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400c2002  nop     dword ptr [rax+rax+00h]
0x1400c2007  mov     rbx, [rsp+48h+arg_0]
0x1400c200c  mov     eax, edi
0x1400c200e  mov     rsi, [rsp+48h+arg_10]
0x1400c2013  add     rsp, 40h
0x1400c2017  pop     rdi
0x1400c2018  retn
```
