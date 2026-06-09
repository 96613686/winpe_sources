# GenerateHash(void *,CSsl3TlsContext *,uchar *,ulong,uchar *,ulong)

- ea: `0x18001d960`
- end: `0x18001db56`
- name: `?GenerateHash@@YAKPEAXPEAVCSsl3TlsContext@@PEAEK2K@Z`
- size: `502`
- prototype: `unsigned int __usercall@<eax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, struct CSsl3TlsContext *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18001bba0`
- `0x180020450`
- `0x180040280`
- `0x180085a68`
- `0x180085bc8`

## callees

- `0x18001d960`
- `0x18001db60`
- `0x1800597b0`
- `0x1800889d0`
- `0x180091010`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x18001d9be`
- `bcrypt!BCryptGetProperty` at `0x18001d9be`
- `bcrypt!BCryptCreateHash` at `0x18001da6d`
- `bcrypt!BCryptCreateHash` at `0x18001da6d`
- `bcrypt!BCryptHashData` at `0x18001da8d`
- `bcrypt!BCryptHashData` at `0x18001daa6`
- `bcrypt!BCryptHashData` at `0x18001da8d`
- `bcrypt!BCryptHashData` at `0x18001daa6`
- `bcrypt!BCryptFinishHash` at `0x18001dac7`
- `bcrypt!BCryptFinishHash` at `0x18001dac7`
- `bcrypt!BCryptDestroyHash` at `0x18001dad8`
- `bcrypt!BCryptDestroyHash` at `0x18001dad8`

## pseudocode

```c
NTSTATUS __fastcall GenerateHash(
        BCRYPT_ALG_HANDLE hAlgorithm,
        UCHAR *a2,
        unsigned __int8 *a3,
        ULONG a4,
        unsigned __int8 *a5,
        ULONG cbOutput)
{
  NTSTATUS result; // eax
  unsigned __int64 v11; // rdi
  UCHAR *p_phHash; // rbx
  unsigned __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  NTSTATUS v18; // edi
  _DWORD *v19; // rax
  __int64 v20; // [rsp+0h] [rbp-40h] BYREF
  UCHAR pbOutput[4]; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp+8h] BYREF
  ULONG pcbResult[4]; // [rsp+50h] [rbp+10h] BYREF

  *(_DWORD *)pbOutput = 0;
  pcbResult[0] = 0;
  phHash = 0;
  result = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, pcbResult, 0);
  if ( result )
    return result;
  v11 = *(unsigned int *)pbOutput;
  p_phHash = 0;
  if ( !*(_DWORD *)pbOutput )
    goto LABEL_23;
  if ( *(unsigned int *)pbOutput > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_23;
  v13 = *(unsigned int *)pbOutput + g_ulAdditionalProbeSize + 8;
  if ( v13 < *(unsigned int *)pbOutput || !(unsigned int)VerifyStackAvailable(v13) )
    goto LABEL_23;
  v14 = v11 + 23;
  if ( v11 + 23 <= v11 + 8 )
    v14 = 0xFFFFFFFFFFFFFF0LL;
  v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
  v16 = alloca(v15);
  v17 = alloca(v15);
  p_phHash = pbOutput;
  if ( &v20 == (__int64 *)-64LL || (*(_DWORD *)pbOutput = 1801679955, (p_phHash = (UCHAR *)&phHash) == 0) )
  {
LABEL_23:
    if ( v11 + 8 >= v11 )
    {
      v19 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v19 )
        return 14;
      *v19 = 1885431112;
      p_phHash = (UCHAR *)(v19 + 2);
    }
    if ( p_phHash )
      goto LABEL_10;
    return 14;
  }
LABEL_10:
  v18 = BCryptCreateHash(hAlgorithm, &phHash, p_phHash, *(ULONG *)pbOutput, 0, 0, 0);
  if ( !v18 )
  {
    v18 = BCryptHashData(phHash, a2 + 1992, 0x40u, 0);
    if ( !v18 )
    {
      v18 = BCryptHashData(phHash, a3, a4, 0);
      if ( !v18 )
        v18 = BCryptFinishHash(phHash, a5, cbOutput, 0);
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash )
  {
    if ( *((_DWORD *)p_phHash - 2) == 1885431112 )
      ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_phHash - 8);
  }
  return v18;
}

```

## disassembly

```asm
0x18001d960  push    rbp
0x18001d962  push    rbx
0x18001d963  push    rsi
0x18001d964  push    rdi
0x18001d965  push    r12
0x18001d967  push    r13
0x18001d969  push    r14
0x18001d96b  push    r15
0x18001d96d  sub     rsp, 78h
0x18001d971  lea     rbp, [rsp+40h]
0x18001d976  mov     rax, cs:__security_cookie
0x18001d97d  xor     rax, rbp
0x18001d980  mov     [rbp+70h+var_50], rax
0x18001d984  xor     r12d, r12d
0x18001d987  lea     rax, [rbp+70h+var_60]
0x18001d98b  mov     r14d, r9d
0x18001d98e  mov     [rsp+0B0h+dwFlags], r12d; dwFlags
0x18001d993  mov     r15, r8
0x18001d996  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18001d99b  mov     r13, rdx
0x18001d99e  mov     dword ptr [rbp+70h+pbOutput], r12d
0x18001d9a2  mov     r9d, 4; cbOutput
0x18001d9a8  mov     [rbp+70h+var_60], r12d
0x18001d9ac  lea     r8, [rbp+70h+pbOutput]; pbOutput
0x18001d9b0  mov     [rbp+70h+phHash], r12
0x18001d9b4  lea     rdx, pszProperty; "ObjectLength"
0x18001d9bb  mov     rsi, rcx
0x18001d9be  call    cs:__imp_BCryptGetProperty
0x18001d9c4  test    eax, eax
0x18001d9c6  jnz     loc_18001DAF2
0x18001d9cc  mov     edi, dword ptr [rbp+70h+pbOutput]
0x18001d9cf  mov     ebx, r12d
0x18001d9d2  test    rdi, rdi
0x18001d9d5  jz      loc_18001DB1F
0x18001d9db  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001d9e2  ja      loc_18001DB1F
0x18001d9e8  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001d9ef  add     rcx, 8
0x18001d9f3  add     rcx, rdi
0x18001d9f6  cmp     rcx, rdi
0x18001d9f9  jb      loc_18001DB1F
0x18001d9ff  call    VerifyStackAvailable
0x18001da04  test    eax, eax
0x18001da06  jz      loc_18001DB1F
0x18001da0c  lea     rax, [rdi+8]
0x18001da10  lea     rcx, [rax+0Fh]
0x18001da14  cmp     rcx, rax
0x18001da17  ja      short loc_18001DA23
0x18001da19  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001da23  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001da27  mov     rax, rcx
0x18001da2a  call    _alloca_probe
0x18001da2f  sub     rsp, rcx
0x18001da32  lea     rbx, [rsp+0B0h+pbOutput]
0x18001da37  test    rbx, rbx
0x18001da3a  jz      loc_18001DB1F
0x18001da40  mov     dword ptr [rbx], 6B637453h
0x18001da46  add     rbx, 8
0x18001da4a  jz      loc_18001DB1F
0x18001da50  mov     r9d, dword ptr [rbp+70h+pbOutput]; cbHashObject
0x18001da54  lea     rdx, [rbp+70h+phHash]; phHash
0x18001da58  mov     [rsp+0B0h+var_80], r12d; dwFlags
0x18001da5d  mov     r8, rbx; pbHashObject
0x18001da60  mov     [rsp+0B0h+dwFlags], r12d; cbSecret
0x18001da65  mov     rcx, rsi; hAlgorithm
0x18001da68  mov     [rsp+0B0h+pcbResult], r12; pbSecret
0x18001da6d  call    cs:__imp_BCryptCreateHash
0x18001da73  mov     edi, eax
0x18001da75  test    eax, eax
0x18001da77  jnz     short loc_18001DACF
0x18001da79  mov     rcx, [rbp+70h+phHash]; hHash
0x18001da7d  lea     rdx, [r13+7C8h]; pbInput
0x18001da84  xor     r9d, r9d; dwFlags
0x18001da87  mov     r8d, 40h ; '@'; cbInput
0x18001da8d  call    cs:__imp_BCryptHashData
0x18001da93  mov     edi, eax
0x18001da95  test    eax, eax
0x18001da97  jnz     short loc_18001DACF
0x18001da99  mov     rcx, [rbp+70h+phHash]; hHash
0x18001da9d  xor     r9d, r9d; dwFlags
0x18001daa0  mov     r8d, r14d; cbInput
0x18001daa3  mov     rdx, r15; pbInput
0x18001daa6  call    cs:__imp_BCryptHashData
0x18001daac  mov     edi, eax
0x18001daae  test    eax, eax
0x18001dab0  jnz     short loc_18001DACF
0x18001dab2  mov     r8d, [rbp+70h+cbOutput]; cbOutput
0x18001dab9  xor     r9d, r9d; dwFlags
0x18001dabc  mov     rdx, [rbp+70h+arg_20]; pbOutput
0x18001dac3  mov     rcx, [rbp+70h+phHash]; hHash
0x18001dac7  call    cs:__imp_BCryptFinishHash
0x18001dacd  mov     edi, eax
0x18001dacf  mov     rcx, [rbp+70h+phHash]; hHash
0x18001dad3  test    rcx, rcx
0x18001dad6  jz      short loc_18001DADE
0x18001dad8  call    cs:__imp_BCryptDestroyHash
0x18001dade  test    rbx, rbx
0x18001dae1  jz      short loc_18001DAF0
0x18001dae3  cmp     dword ptr [rbx-8], 70616548h
0x18001daea  lea     rcx, [rbx-8]
0x18001daee  jz      short loc_18001DB48
0x18001daf0  mov     eax, edi
0x18001daf2  mov     rcx, [rbp+70h+var_50]
0x18001daf6  xor     rcx, rbp; StackCookie
0x18001daf9  call    __security_check_cookie
0x18001dafe  lea     rsp, [rbp+38h]
0x18001db02  pop     r15
0x18001db04  pop     r14
0x18001db06  pop     r13
0x18001db08  pop     r12
0x18001db0a  pop     rdi
0x18001db0b  pop     rsi
0x18001db0c  pop     rbx
0x18001db0d  pop     rbp
0x18001db0e  retn
0x18001db0f  test    rbx, rbx
0x18001db12  jnz     loc_18001DA50
0x18001db18  mov     eax, 0Eh
0x18001db1d  jmp     short loc_18001DAF2
0x18001db1f  lea     rcx, [rdi+8]
0x18001db23  cmp     rcx, rdi
0x18001db26  jb      short loc_18001DB0F
0x18001db28  mov     rax, cs:g_pfnAllocate
0x18001db2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db34  mov     rbx, rax
0x18001db37  test    rax, rax
0x18001db3a  jz      short loc_18001DB18
0x18001db3c  mov     dword ptr [rax], 70616548h
0x18001db42  add     rbx, 8
0x18001db46  jmp     short loc_18001DB0F
0x18001db48  mov     rax, cs:g_pfnFree
0x18001db4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db54  jmp     short loc_18001DAF0
```
