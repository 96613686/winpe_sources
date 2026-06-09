# SAL2::CW32Sid::CopySids_(void * *,ulong)

- ea: `0x180026998`
- end: `0x180026b99`
- name: `?CopySids_@CW32Sid@SAL2@@AEAAKPEAPEAXK@Z`
- size: `513`
- prototype: `unsigned int __fastcall(SAL2::CW32Sid *__hidden this, void **, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180025aa4`
- `0x180085a2c`

## callees

- `0x1800017ec`
- `0x180001c00`
- `0x18000256c`
- `0x180026998`
- `0x180026fdc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026a7b`
- `KERNEL32!GetLastError` at `0x180026b3e`
- `KERNEL32!GetLastError` at `0x180026a7b`
- `KERNEL32!GetLastError` at `0x180026b3e`
- `ADVAPI32!GetLengthSid` at `0x180026a9c`
- `ADVAPI32!GetLengthSid` at `0x180026af6`
- `ADVAPI32!GetLengthSid` at `0x180026a9c`
- `ADVAPI32!GetLengthSid` at `0x180026af6`
- `ADVAPI32!FreeSid` at `0x180026b6a`
- `ADVAPI32!FreeSid` at `0x180026b6a`
- `ADVAPI32!IsValidSid` at `0x180026ae8`
- `ADVAPI32!IsValidSid` at `0x180026ae8`
- `ADVAPI32!CopySid` at `0x180026ac4`
- `ADVAPI32!CopySid` at `0x180026b29`
- `ADVAPI32!CopySid` at `0x180026ac4`
- `ADVAPI32!CopySid` at `0x180026b29`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180026a71`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180026a71`

## pseudocode

```c
__int64 __fastcall SAL2::CW32Sid::CopySids_(SAL2::CW32Sid *this, void **a2, unsigned int a3)
{
  unsigned __int64 v7; // rsi
  unsigned int v8; // ebx
  void *v9; // rax
  DWORD LastError; // eax
  DWORD LengthSid; // esi
  void *v12; // rdx
  unsigned int v13; // esi
  unsigned int i; // r12d
  void *v15; // rcx
  void *v16; // rdx
  PSID pSourceSid; // [rsp+60h] [rbp-20h] BYREF
  DWORD nDestinationSidLength; // [rsp+68h] [rbp-18h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+6Ch] [rbp-14h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 768;
  pSourceSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !a3 )
  {
    if ( !a2 )
      return 0;
    return 87;
  }
  if ( !a2 )
    return 87;
  v7 = a3 + 1;
  v8 = 8;
  v9 = operator new[](saturated_mul(v7, 8u));
  *((_QWORD *)this + 2) = v9;
  if ( v9 )
  {
    *((_DWORD *)this + 6) = v7;
    memset_0(v9, 0, 8 * v7);
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSourceSid) )
    {
LABEL_8:
      LastError = GetLastError();
LABEL_9:
      v8 = LastError;
      if ( !LastError )
        goto LABEL_23;
      goto LABEL_10;
    }
    LengthSid = GetLengthSid(pSourceSid);
    **((_QWORD **)this + 2) = operator new[](LengthSid);
    v12 = (void *)**((_QWORD **)this + 2);
    if ( v12 )
    {
      if ( !CopySid(LengthSid, v12, pSourceSid) )
        goto LABEL_8;
      v13 = 0;
      for ( i = 1; ; ++i )
      {
        if ( v13 >= a3 )
        {
          v8 = 0;
          goto LABEL_23;
        }
        v15 = a2[v13];
        if ( !v15 || !IsValidSid(v15) )
          break;
        nDestinationSidLength = GetLengthSid(a2[v13]);
        *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * i) = operator new[](nDestinationSidLength);
        v16 = *(void **)(*((_QWORD *)this + 2) + 8LL * i);
        if ( !v16 )
          goto LABEL_10;
        if ( !CopySid(nDestinationSidLength, v16, a2[v13]) )
          goto LABEL_8;
        ++v13;
      }
      LastError = GetLastError();
      if ( a2[v13] )
        goto LABEL_9;
      v8 = 87;
    }
LABEL_10:
    SBECoreUtil::CW32SID::DeleteSids_(this);
LABEL_23:
    if ( pSourceSid )
      FreeSid(pSourceSid);
  }
  return v8;
}

```

## disassembly

```asm
0x180026998  mov     [rsp-38h+arg_18], rbx
0x18002699d  push    rbp
0x18002699e  push    rsi
0x18002699f  push    rdi
0x1800269a0  push    r12
0x1800269a2  push    r13
0x1800269a4  push    r14
0x1800269a6  push    r15
0x1800269a8  mov     rbp, rsp
0x1800269ab  sub     rsp, 80h
0x1800269b2  mov     rax, cs:__security_cookie
0x1800269b9  xor     rax, rsp
0x1800269bc  mov     [rbp+var_8], rax
0x1800269c0  xor     r12d, r12d
0x1800269c3  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 300h
0x1800269c9  mov     [rbp+pSourceSid], r12
0x1800269cd  mov     r13d, r8d
0x1800269d0  mov     dword ptr [rbp+pIdentifierAuthority.Value], r12d
0x1800269d4  mov     rdi, rdx
0x1800269d7  mov     r14, rcx
0x1800269da  test    r8d, r8d
0x1800269dd  jnz     short loc_1800269EB
0x1800269df  test    rdx, rdx
0x1800269e2  jnz     short loc_1800269F0
0x1800269e4  xor     eax, eax
0x1800269e6  jmp     loc_180026B72
0x1800269eb  test    rdi, rdi
0x1800269ee  jnz     short loc_1800269FA
0x1800269f0  mov     eax, 57h ; 'W'
0x1800269f5  jmp     loc_180026B72
0x1800269fa  lea     esi, [r8+1]
0x1800269fe  mov     ebx, 8
0x180026a03  mov     r15d, esi
0x180026a06  mov     eax, ebx
0x180026a08  mul     r15
0x180026a0b  lea     rcx, [rbx-9]
0x180026a0f  cmovb   rax, rcx
0x180026a13  mov     rcx, rax; unsigned __int64
0x180026a16  call    ??_U@YAPEAX_K@Z
0x180026a1b  mov     [r14+10h], rax
0x180026a1f  test    rax, rax
0x180026a22  jz      loc_180026B70
0x180026a28  lea     r8, ds:0[rsi*8]; Size
0x180026a30  mov     [r14+18h], esi
0x180026a34  xor     edx, edx; Val
0x180026a36  mov     rcx, rax; void *
0x180026a39  call    memset_0
0x180026a3e  lea     rax, [rbp+pSourceSid]
0x180026a42  xor     r9d, r9d; nSubAuthority1
0x180026a45  mov     [rsp+80h+pSid], rax; pSid
0x180026a4a  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180026a4e  mov     [rsp+80h+nSubAuthority7], r12d; nSubAuthority7
0x180026a53  xor     r8d, r8d; nSubAuthority0
0x180026a56  mov     [rsp+80h+nSubAuthority6], r12d; nSubAuthority6
0x180026a5b  mov     dl, 1; nSubAuthorityCount
0x180026a5d  mov     [rsp+80h+nSubAuthority5], r12d; nSubAuthority5
0x180026a62  mov     [rsp+80h+nSubAuthority4], r12d; nSubAuthority4
0x180026a67  mov     [rsp+80h+nSubAuthority3], r12d; nSubAuthority3
0x180026a6c  mov     [rsp+80h+nSubAuthority2], r12d; nSubAuthority2
0x180026a71  call    cs:__imp_AllocateAndInitializeSid
0x180026a77  test    eax, eax
0x180026a79  jnz     short loc_180026A98
0x180026a7b  call    cs:__imp_GetLastError
0x180026a81  mov     ebx, eax
0x180026a83  test    eax, eax
0x180026a85  jz      loc_180026B61
0x180026a8b  mov     rcx, r14; this
0x180026a8e  call    ?DeleteSids_@CW32SID@SBECoreUtil@@AEAAXXZ
0x180026a93  jmp     loc_180026B61
0x180026a98  mov     rcx, [rbp+pSourceSid]; pSid
0x180026a9c  call    cs:__imp_GetLengthSid
0x180026aa2  mov     ecx, eax; unsigned __int64
0x180026aa4  mov     esi, eax
0x180026aa6  call    ??_U@YAPEAX_K@Z
0x180026aab  mov     rcx, [r14+10h]
0x180026aaf  mov     [rcx], rax
0x180026ab2  mov     rcx, [r14+10h]
0x180026ab6  mov     rdx, [rcx]; pDestinationSid
0x180026ab9  test    rdx, rdx
0x180026abc  jz      short loc_180026A8B
0x180026abe  mov     r8, [rbp+pSourceSid]; pSourceSid
0x180026ac2  mov     ecx, esi; nDestinationSidLength
0x180026ac4  call    cs:__imp_CopySid
0x180026aca  test    eax, eax
0x180026acc  jz      short loc_180026A7B
0x180026ace  mov     esi, r12d
0x180026ad1  mov     r12d, 1
0x180026ad7  cmp     esi, r13d
0x180026ada  jnb     short loc_180026B5B
0x180026adc  mov     r15d, esi
0x180026adf  mov     rcx, [rdi+r15*8]; pSid
0x180026ae3  test    rcx, rcx
0x180026ae6  jz      short loc_180026B3E
0x180026ae8  call    cs:__imp_IsValidSid
0x180026aee  test    eax, eax
0x180026af0  jz      short loc_180026B3E
0x180026af2  mov     rcx, [rdi+r15*8]; pSid
0x180026af6  call    cs:__imp_GetLengthSid
0x180026afc  mov     ecx, eax; unsigned __int64
0x180026afe  mov     [rbp+nDestinationSidLength], eax
0x180026b01  call    ??_U@YAPEAX_K@Z
0x180026b06  mov     rcx, [r14+10h]
0x180026b0a  mov     edx, r12d
0x180026b0d  mov     [rcx+rdx*8], rax
0x180026b11  mov     rcx, [r14+10h]
0x180026b15  mov     rdx, [rcx+rdx*8]; pDestinationSid
0x180026b19  test    rdx, rdx
0x180026b1c  jz      loc_180026A8B
0x180026b22  mov     r8, [rdi+r15*8]; pSourceSid
0x180026b26  mov     ecx, [rbp+nDestinationSidLength]; nDestinationSidLength
0x180026b29  call    cs:__imp_CopySid
0x180026b2f  test    eax, eax
0x180026b31  jz      loc_180026A7B
0x180026b37  inc     esi
0x180026b39  inc     r12d
0x180026b3c  jmp     short loc_180026AD7
0x180026b3e  call    cs:__imp_GetLastError
0x180026b44  xor     r12d, r12d
0x180026b47  cmp     [rdi+r15*8], r12
0x180026b4b  jnz     loc_180026A81
0x180026b51  lea     ebx, [r12+57h]
0x180026b56  jmp     loc_180026A8B
0x180026b5b  xor     r12d, r12d
0x180026b5e  mov     ebx, r12d
0x180026b61  mov     rcx, [rbp+pSourceSid]; pSid
0x180026b65  test    rcx, rcx
0x180026b68  jz      short loc_180026B70
0x180026b6a  call    cs:__imp_FreeSid
0x180026b70  mov     eax, ebx
0x180026b72  mov     rcx, [rbp+var_8]
0x180026b76  xor     rcx, rsp; StackCookie
0x180026b79  call    __security_check_cookie
0x180026b7e  mov     rbx, [rsp+80h+arg_18]
0x180026b86  add     rsp, 80h
0x180026b8d  pop     r15
0x180026b8f  pop     r14
0x180026b91  pop     r13
0x180026b93  pop     r12
0x180026b95  pop     rdi
0x180026b96  pop     rsi
0x180026b97  pop     rbp
0x180026b98  retn
```
