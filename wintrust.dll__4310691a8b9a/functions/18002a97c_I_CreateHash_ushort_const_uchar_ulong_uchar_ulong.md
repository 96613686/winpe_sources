# I_CreateHash(ushort const *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18002a97c`
- end: `0x18002ac36`
- name: `?I_CreateHash@@YAJPEBGPEAEKPEAPEAEPEAK@Z`
- size: `698`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszAlgId@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18003813c`

## callees

- `0x18002a97c`
- `0x18002c3b8`
- `0x18002d904`
- `0x18002e5d0`
- `0x180030224`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002a9d3`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002a9d3`
- `bcrypt!BCryptHashData` at `0x18002ab37`
- `bcrypt!BCryptHashData` at `0x18002ab37`
- `bcrypt!BCryptCreateHash` at `0x18002aade`
- `bcrypt!BCryptCreateHash` at `0x18002aade`
- `bcrypt!BCryptFinishHash` at `0x18002ab7a`
- `bcrypt!BCryptFinishHash` at `0x18002ab7a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002ab03`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002ab03`
- `bcrypt!BCryptGetProperty` at `0x18002aa3f`
- `bcrypt!BCryptGetProperty` at `0x18002aa6a`
- `bcrypt!BCryptGetProperty` at `0x18002aa3f`
- `bcrypt!BCryptGetProperty` at `0x18002aa6a`

## pseudocode

```c
__int64 __fastcall I_CreateHash(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, unsigned __int8 **a4, UCHAR *a5)
{
  UCHAR *v8; // rsi
  NTSTATUS Property; // ebx
  void *v11; // rax
  void *v12; // rcx
  void *v13; // rbx
  UCHAR *v14; // rdi
  NTSTATUS Hash; // eax
  unsigned int v16; // r14d
  NTSTATUS v17; // r14d
  NTSTATUS v18; // esi
  ULONG pcbResult; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_HASH_HANDLE *v20; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE *p_phAlgorithm; // [rsp+50h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash[3]; // [rsp+60h] [rbp-18h] BYREF
  ULONG pbOutput; // [rsp+D8h] [rbp+60h] BYREF

  phAlgorithm = 0;
  p_phAlgorithm = 0;
  phHash[0] = 0;
  v20 = 0;
  if ( !a4 || (v8 = a5) == 0 )
  {
    operator delete(0);
    std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(&v20);
    std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(&p_phAlgorithm);
    operator delete(0);
    return 2147942487LL;
  }
  *(_DWORD *)a5 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0x20u);
  if ( Property < 0
    || (p_phAlgorithm = &phAlgorithm,
        pbOutput = 0,
        pcbResult = 0,
        Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0),
        Property < 0)
    || (Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v8, 4u, &pcbResult, 0), Property < 0) )
  {
    operator delete(0);
    std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(&v20);
    std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(&p_phAlgorithm);
    operator delete(0);
    return Property | 0x10000000u;
  }
  v11 = operator new[](*(unsigned int *)v8, (const struct std::nothrow_t *)std::nothrow);
  v12 = 0;
  v13 = v11;
  if ( !v11 )
  {
LABEL_20:
    operator delete(v12);
    std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(&v20);
    std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(&p_phAlgorithm);
    operator delete(0);
    return 2147942414LL;
  }
  operator delete(0);
  v14 = (UCHAR *)operator new[](pbOutput, (const struct std::nothrow_t *)std::nothrow);
  if ( !v14 )
  {
    v12 = v13;
    goto LABEL_20;
  }
  operator delete(0);
  Hash = BCryptCreateHash(phAlgorithm, phHash, v14, pbOutput, 0, 0, 0x20u);
  if ( Hash < 0 )
  {
    v16 = Hash | 0x10000000;
    operator delete(v13);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    operator delete(v14);
    return v16;
  }
  std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(&v20);
  v20 = phHash;
  v17 = BCryptHashData(phHash[0], pbInput, cbInput, 0);
  if ( v17 < 0 )
  {
    operator delete(v13);
    std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(&v20);
    std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(&p_phAlgorithm);
    operator delete(v14);
    return v17 | 0x10000000u;
  }
  v18 = BCryptFinishHash(phHash[0], (PUCHAR)v13, *(_DWORD *)v8, 0);
  if ( v18 >= 0 )
  {
    *a4 = (unsigned __int8 *)v13;
    operator delete(0);
    std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(&v20);
    std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(&p_phAlgorithm);
    operator delete(v14);
    return 0;
  }
  else
  {
    operator delete(v13);
    std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(&v20);
    std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(&p_phAlgorithm);
    operator delete(v14);
    return v18 | 0x10000000u;
  }
}

```

## disassembly

```asm
0x18002a97c  push    rbp
0x18002a97e  push    rbx
0x18002a97f  push    rsi
0x18002a980  push    rdi
0x18002a981  push    r12
0x18002a983  push    r13
0x18002a985  push    r14
0x18002a987  push    r15
0x18002a989  mov     rbp, rsp
0x18002a98c  sub     rsp, 78h
0x18002a990  xor     r14d, r14d
0x18002a993  mov     r15, r9
0x18002a996  mov     [rbp+phAlgorithm], r14
0x18002a99a  mov     r12d, r8d
0x18002a99d  mov     [rbp+var_28], r14
0x18002a9a1  mov     r13, rdx
0x18002a9a4  mov     [rbp+phHash], r14
0x18002a9a8  mov     [rbp+var_30], r14
0x18002a9ac  test    r9, r9
0x18002a9af  jz      loc_18002AC00
0x18002a9b5  mov     rsi, [rbp+arg_20]
0x18002a9b9  test    rsi, rsi
0x18002a9bc  jz      loc_18002AC00
0x18002a9c2  mov     rdx, rcx; pszAlgId
0x18002a9c5  mov     [rsi], r14d
0x18002a9c8  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18002a9cc  xor     r8d, r8d; pszImplementation
0x18002a9cf  lea     r9d, [r14+20h]; dwFlags
0x18002a9d3  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002a9d9  mov     ebx, eax
0x18002a9db  test    eax, eax
0x18002a9dd  jns     short loc_18002AA0A
0x18002a9df  xor     ecx, ecx; Block
0x18002a9e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a9e6  lea     rcx, [rbp+var_30]
0x18002a9ea  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_hash_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(void)
0x18002a9ef  lea     rcx, [rbp+var_28]
0x18002a9f3  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_alg_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(void)
0x18002a9f8  xor     ecx, ecx; Block
0x18002a9fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a9ff  bts     ebx, 1Ch
0x18002aa03  mov     eax, ebx
0x18002aa05  jmp     loc_18002AC25
0x18002aa0a  mov     rcx, [rbp+phAlgorithm]; hObject
0x18002aa0e  lea     rax, [rbp+phAlgorithm]
0x18002aa12  mov     [rbp+var_28], rax
0x18002aa16  lea     r8, [rbp+pbOutput]; pbOutput
0x18002aa1a  lea     rax, [rbp+var_38]
0x18002aa1e  mov     [rsp+78h+dwFlags], r14d; dwFlags
0x18002aa23  mov     edi, 4
0x18002aa28  mov     [rsp+78h+pcbResult], rax; pcbResult
0x18002aa2d  mov     r9d, edi; cbOutput
0x18002aa30  mov     [rbp+pbOutput], r14d
0x18002aa34  lea     rdx, aObjectlength; "ObjectLength"
0x18002aa3b  mov     [rbp+var_38], r14d
0x18002aa3f  call    cs:__imp_BCryptGetProperty
0x18002aa45  mov     ebx, eax
0x18002aa47  test    eax, eax
0x18002aa49  js      short loc_18002A9DF
0x18002aa4b  mov     rcx, [rbp+phAlgorithm]; hObject
0x18002aa4f  lea     rax, [rbp+var_38]
0x18002aa53  mov     [rsp+78h+dwFlags], r14d; dwFlags
0x18002aa58  lea     rdx, pszProperty; "HashDigestLength"
0x18002aa5f  mov     r9d, edi; cbOutput
0x18002aa62  mov     [rsp+78h+pcbResult], rax; pcbResult
0x18002aa67  mov     r8, rsi; pbOutput
0x18002aa6a  call    cs:__imp_BCryptGetProperty
0x18002aa70  mov     ebx, eax
0x18002aa72  test    eax, eax
0x18002aa74  js      loc_18002A9DF
0x18002aa7a  mov     ecx, [rsi]; unsigned __int64
0x18002aa7c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002aa83  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002aa88  xor     ecx, ecx; Block
0x18002aa8a  mov     rbx, rax
0x18002aa8d  test    rax, rax
0x18002aa90  jz      loc_18002ABDB
0x18002aa96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002aa9b  mov     ecx, [rbp+pbOutput]; unsigned __int64
0x18002aa9e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002aaa5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002aaaa  mov     rdi, rax
0x18002aaad  test    rax, rax
0x18002aab0  jz      loc_18002ABD8
0x18002aab6  xor     ecx, ecx; Block
0x18002aab8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002aabd  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18002aac1  lea     rdx, [rbp+phHash]; phHash
0x18002aac5  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18002aac9  mov     r8, rdi; pbHashObject
0x18002aacc  mov     [rsp+78h+var_48], 20h ; ' '; dwFlags
0x18002aad4  mov     [rsp+78h+dwFlags], r14d; cbSecret
0x18002aad9  mov     [rsp+78h+pcbResult], r14; pbSecret
0x18002aade  call    cs:__imp_BCryptCreateHash
0x18002aae4  mov     r14d, eax
0x18002aae7  test    eax, eax
0x18002aae9  jns     short loc_18002AB19
0x18002aaeb  mov     rcx, rbx; Block
0x18002aaee  bts     r14d, 1Ch
0x18002aaf3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002aaf8  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18002aafc  test    rcx, rcx
0x18002aaff  jz      short loc_18002AB09
0x18002ab01  xor     edx, edx; dwFlags
0x18002ab03  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002ab09  mov     rcx, rdi; Block
0x18002ab0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ab11  mov     eax, r14d
0x18002ab14  jmp     loc_18002AC25
0x18002ab19  lea     rcx, [rbp+var_30]
0x18002ab1d  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_hash_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(void)
0x18002ab22  mov     rcx, [rbp+phHash]; hHash
0x18002ab26  lea     rax, [rbp+phHash]
0x18002ab2a  xor     r9d, r9d; dwFlags
0x18002ab2d  mov     [rbp+var_30], rax
0x18002ab31  mov     r8d, r12d; cbInput
0x18002ab34  mov     rdx, r13; pbInput
0x18002ab37  call    cs:__imp_BCryptHashData
0x18002ab3d  mov     r14d, eax
0x18002ab40  test    eax, eax
0x18002ab42  jns     short loc_18002AB6D
0x18002ab44  mov     rcx, rbx; Block
0x18002ab47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ab4c  lea     rcx, [rbp+var_30]
0x18002ab50  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_hash_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(void)
0x18002ab55  lea     rcx, [rbp+var_28]
0x18002ab59  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_alg_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(void)
0x18002ab5e  mov     rcx, rdi; Block
0x18002ab61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ab66  bts     r14d, 1Ch
0x18002ab6b  jmp     short loc_18002AB11
0x18002ab6d  mov     r8d, [rsi]; cbOutput
0x18002ab70  xor     r9d, r9d; dwFlags
0x18002ab73  mov     rcx, [rbp+phHash]; hHash
0x18002ab77  mov     rdx, rbx; pbOutput
0x18002ab7a  call    cs:__imp_BCryptFinishHash
0x18002ab80  mov     esi, eax
0x18002ab82  test    eax, eax
0x18002ab84  jns     short loc_18002ABB0
0x18002ab86  mov     rcx, rbx; Block
0x18002ab89  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ab8e  lea     rcx, [rbp+var_30]
0x18002ab92  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_hash_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(void)
0x18002ab97  lea     rcx, [rbp+var_28]
0x18002ab9b  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_alg_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(void)
0x18002aba0  mov     rcx, rdi; Block
0x18002aba3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002aba8  bts     esi, 1Ch
0x18002abac  mov     eax, esi
0x18002abae  jmp     short loc_18002AC25
0x18002abb0  xor     ecx, ecx; Block
0x18002abb2  mov     [r15], rbx
0x18002abb5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002abba  lea     rcx, [rbp+var_30]
0x18002abbe  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_hash_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(void)
0x18002abc3  lea     rcx, [rbp+var_28]
0x18002abc7  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_alg_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(void)
0x18002abcc  mov     rcx, rdi; Block
0x18002abcf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002abd4  xor     eax, eax
0x18002abd6  jmp     short loc_18002AC25
0x18002abd8  mov     rcx, rbx; Block
0x18002abdb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002abe0  lea     rcx, [rbp+var_30]
0x18002abe4  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_hash_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(void)
0x18002abe9  lea     rcx, [rbp+var_28]
0x18002abed  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_alg_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(void)
0x18002abf2  xor     ecx, ecx; Block
0x18002abf4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002abf9  mov     eax, 8007000Eh
0x18002abfe  jmp     short loc_18002AC25
0x18002ac00  xor     ecx, ecx; Block
0x18002ac02  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ac07  lea     rcx, [rbp+var_30]
0x18002ac0b  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_hash_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_hash_handle::tag>>::_Delete(void)
0x18002ac10  lea     rcx, [rbp+var_28]
0x18002ac14  call    ?_Delete@?$unique_ptr@PEAXU?$deleter@Utag@bcrypt_alg_handle@release@@@@@std@@AEAAXXZ; std::unique_ptr<void *,deleter<release::bcrypt_alg_handle::tag>>::_Delete(void)
0x18002ac19  xor     ecx, ecx; Block
0x18002ac1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ac20  mov     eax, 80070057h
0x18002ac25  add     rsp, 78h
0x18002ac29  pop     r15
0x18002ac2b  pop     r14
0x18002ac2d  pop     r13
0x18002ac2f  pop     r12
0x18002ac31  pop     rdi
0x18002ac32  pop     rsi
0x18002ac33  pop     rbx
0x18002ac34  pop     rbp
0x18002ac35  retn
```
