# DafClass5GuidFromBlob(_GUID const &,void *,ulong,_GUID *)

- ea: `0x18001643c`
- end: `0x1800166cc`
- name: `?DafClass5GuidFromBlob@@YAJAEBU_GUID@@PEAXKPEAU1@@Z`
- size: `656`
- prototype: `int(const struct _GUID *, void *, unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800166d4`

## callees

- `0x18000526c`
- `0x180005278`
- `0x180005680`
- `0x18001643c`
- `0x180016a3c`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18001665c`
- `bcrypt!BCryptDestroyHash` at `0x18001665c`
- `bcrypt!BCryptCreateHash` at `0x180016535`
- `bcrypt!BCryptCreateHash` at `0x180016535`
- `bcrypt!BCryptHashData` at `0x180016563`
- `bcrypt!BCryptHashData` at `0x180016582`
- `bcrypt!BCryptHashData` at `0x180016563`
- `bcrypt!BCryptHashData` at `0x180016582`
- `bcrypt!BCryptGetProperty` at `0x1800164ed`
- `bcrypt!BCryptGetProperty` at `0x1800165b4`
- `bcrypt!BCryptGetProperty` at `0x1800164ed`
- `bcrypt!BCryptGetProperty` at `0x1800165b4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800164b3`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800164b3`
- `bcrypt!BCryptFinishHash` at `0x1800165ef`
- `bcrypt!BCryptFinishHash` at `0x1800165ef`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016673`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180016673`

## pseudocode

```c
__int64 __fastcall DafClass5GuidFromBlob(const struct _GUID *a1, UCHAR *a2, ULONG a3, struct _GUID *a4)
{
  UCHAR *v4; // rsi
  UCHAR *v5; // rdi
  size_t v9; // r15
  unsigned __int64 v10; // rdx
  NTSTATUS Property; // ebx
  bool v12; // sf
  unsigned __int16 Data3; // ax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-30h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-2Ch] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-20h] BYREF
  UCHAR pbInput[4]; // [rsp+58h] [rbp-18h] BYREF
  int v21; // [rsp+5Ch] [rbp-14h]
  unsigned __int64 v22; // [rsp+60h] [rbp-10h]

  phAlgorithm = 0;
  phHash = 0;
  v4 = 0;
  *(_DWORD *)pbOutput = 0;
  v5 = 0;
  pcbResult = 0;
  *a4 = 0;
  *(_DWORD *)pbInput = 507857385;
  v21 = 1133792159;
  v22 = 0x973B90D6C14C80AAuLL;
  v9 = 16;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v4 = (UCHAR *)operator new[](*(unsigned int *)pbOutput);
      if ( !v4 )
      {
LABEL_10:
        Property = -1073741801;
        goto LABEL_17;
      }
      Property = BCryptCreateHash(phAlgorithm, &phHash, v4, *(ULONG *)pbOutput, 0, 0, 0);
      if ( Property >= 0 )
      {
        *(_DWORD *)pbInput = -381074146;
        v21 = -1807507637;
        Property = BCryptHashData(phHash, pbInput, 0x10u, 0);
        if ( Property >= 0 )
          Property = BCryptHashData(phHash, a2, a3, 0);
      }
    }
  }
  v12 = Property < 0;
  if ( Property )
  {
LABEL_12:
    if ( v12 )
      goto LABEL_17;
    goto LABEL_13;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property )
  {
    v12 = Property < 0;
    goto LABEL_12;
  }
  v5 = (UCHAR *)operator new[](*(unsigned int *)pbOutput);
  if ( !v5 )
    goto LABEL_10;
LABEL_13:
  Property = BCryptFinishHash(phHash, v5, *(ULONG *)pbOutput, 0);
  if ( Property >= 0 )
  {
    if ( *(_DWORD *)pbOutput < 0x10u )
      v9 = *(unsigned int *)pbOutput;
    memcpy_0(a4, v5, v9);
    a4->Data1 = _byteswap_ulong(a4->Data1);
    a4->Data2 = __ROR2__(a4->Data2, 8);
    Data3 = a4->Data3;
    a4->Data4[0] &= 0x3Fu;
    a4->Data4[0] |= 0x80u;
    a4->Data3 = __ROR2__(Data3, 8) & 0xFFF | 0x5000;
  }
LABEL_17:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v4 )
    operator delete(v4, v10);
  if ( v5 )
    operator delete(v5, v10);
  if ( Property < 0 )
    return (unsigned int)(Property | 0x10000000);
  else
    return 0;
}

```

## disassembly

```asm
0x18001643c  mov     [rsp-38h+arg_0], rbx
0x180016441  push    rbp
0x180016442  push    rsi
0x180016443  push    rdi
0x180016444  push    r12
0x180016446  push    r13
0x180016448  push    r14
0x18001644a  push    r15
0x18001644c  mov     rbp, rsp
0x18001644f  sub     rsp, 70h
0x180016453  mov     rax, cs:__security_cookie
0x18001645a  xor     rax, rsp
0x18001645d  mov     [rbp+var_8], rax
0x180016461  mov     rax, cs:qword_18001BF58
0x180016468  xor     ecx, ecx
0x18001646a  xorps   xmm0, xmm0
0x18001646d  mov     [rbp+phAlgorithm], rcx
0x180016471  mov     [rbp+phHash], rcx
0x180016475  mov     esi, ecx
0x180016477  mov     dword ptr [rbp+pbOutput], ecx
0x18001647a  mov     edi, ecx
0x18001647c  mov     [rbp+var_2C], ecx
0x18001647f  mov     r14, r9
0x180016482  movups  xmmword ptr [r9], xmm0
0x180016486  mov     r13d, r8d
0x180016489  mov     dword ptr [rbp+pbInput], 1E4549E9h
0x180016490  mov     r12, rdx
0x180016493  mov     [rbp+var_14], 43944B9Fh
0x18001649a  xor     r9d, r9d; dwFlags
0x18001649d  mov     [rbp+var_10], rax
0x1800164a1  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800164a5  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800164ac  lea     rdx, pszAlgId; "SHA1"
0x1800164b3  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800164ba  nop     dword ptr [rax+rax+00h]
0x1800164bf  lea     r15d, [rdi+10h]
0x1800164c3  mov     ebx, eax
0x1800164c5  test    eax, eax
0x1800164c7  js      loc_180016590
0x1800164cd  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800164d1  lea     rax, [rbp+var_2C]
0x1800164d5  mov     [rsp+70h+dwFlags], esi; dwFlags
0x1800164d9  lea     r9d, [rdi+4]; cbOutput
0x1800164dd  lea     r8, [rbp+pbOutput]; pbOutput
0x1800164e1  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1800164e6  lea     rdx, pszProperty; "ObjectLength"
0x1800164ed  call    cs:__imp_BCryptGetProperty
0x1800164f4  nop     dword ptr [rax+rax+00h]
0x1800164f9  mov     ebx, eax
0x1800164fb  test    eax, eax
0x1800164fd  js      loc_180016590
0x180016503  mov     ecx, dword ptr [rbp+pbOutput]; unsigned __int64
0x180016506  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001650b  mov     rsi, rax
0x18001650e  xor     eax, eax
0x180016510  test    rsi, rsi
0x180016513  jz      loc_1800165D6
0x180016519  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x18001651d  lea     rdx, [rbp+phHash]; phHash
0x180016521  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180016525  mov     r8, rsi; pbHashObject
0x180016528  mov     [rsp+70h+var_40], eax; dwFlags
0x18001652c  mov     [rsp+70h+dwFlags], eax; cbSecret
0x180016530  mov     [rsp+70h+pcbResult], rax; pbSecret
0x180016535  call    cs:__imp_BCryptCreateHash
0x18001653c  nop     dword ptr [rax+rax+00h]
0x180016541  mov     ebx, eax
0x180016543  test    eax, eax
0x180016545  js      short loc_180016590
0x180016547  mov     rcx, [rbp+phHash]; hHash
0x18001654b  lea     rdx, [rbp+pbInput]; pbInput
0x18001654f  xor     r9d, r9d; dwFlags
0x180016552  mov     dword ptr [rbp+pbInput], 0E949451Eh
0x180016559  mov     r8d, r15d; cbInput
0x18001655c  mov     [rbp+var_14], 94439F4Bh
0x180016563  call    cs:__imp_BCryptHashData
0x18001656a  nop     dword ptr [rax+rax+00h]
0x18001656f  mov     ebx, eax
0x180016571  test    eax, eax
0x180016573  js      short loc_180016590
0x180016575  mov     rcx, [rbp+phHash]; hHash
0x180016579  xor     r9d, r9d; dwFlags
0x18001657c  mov     r8d, r13d; cbInput
0x18001657f  mov     rdx, r12; pbInput
0x180016582  call    cs:__imp_BCryptHashData
0x180016589  nop     dword ptr [rax+rax+00h]
0x18001658e  mov     ebx, eax
0x180016590  test    ebx, ebx
0x180016592  jnz     short loc_1800165DF
0x180016594  mov     rcx, [rbp+phAlgorithm]; hObject
0x180016598  lea     rax, [rbp+var_2C]
0x18001659c  mov     [rsp+70h+dwFlags], edi; dwFlags
0x1800165a0  lea     r9d, [rbx+4]; cbOutput
0x1800165a4  lea     r8, [rbp+pbOutput]; pbOutput
0x1800165a8  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1800165ad  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800165b4  call    cs:__imp_BCryptGetProperty
0x1800165bb  nop     dword ptr [rax+rax+00h]
0x1800165c0  mov     ebx, eax
0x1800165c2  test    eax, eax
0x1800165c4  jnz     short loc_1800165DD
0x1800165c6  mov     ecx, dword ptr [rbp+pbOutput]; unsigned __int64
0x1800165c9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800165ce  mov     rdi, rax
0x1800165d1  test    rax, rax
0x1800165d4  jnz     short loc_1800165E1
0x1800165d6  mov     ebx, 0C0000017h
0x1800165db  jmp     short loc_180016653
0x1800165dd  test    ebx, ebx
0x1800165df  js      short loc_180016653
0x1800165e1  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x1800165e5  xor     r9d, r9d; dwFlags
0x1800165e8  mov     rcx, [rbp+phHash]; hHash
0x1800165ec  mov     rdx, rdi; pbOutput
0x1800165ef  call    cs:__imp_BCryptFinishHash
0x1800165f6  nop     dword ptr [rax+rax+00h]
0x1800165fb  mov     ebx, eax
0x1800165fd  test    eax, eax
0x1800165ff  js      short loc_180016653
0x180016601  cmp     dword ptr [rbp+pbOutput], r15d
0x180016605  jnb     short loc_18001660B
0x180016607  mov     r15d, dword ptr [rbp+pbOutput]
0x18001660b  mov     r8, r15; Size
0x18001660e  mov     rdx, rdi; Src
0x180016611  mov     rcx, r14; void *
0x180016614  call    memcpy_0
0x180016619  mov     eax, [r14]
0x18001661c  mov     ecx, 0FFFh
0x180016621  bswap   eax
0x180016623  mov     [r14], eax
0x180016626  movzx   eax, word ptr [r14+4]
0x18001662b  ror     ax, 8
0x18001662f  mov     [r14+4], ax
0x180016634  movzx   eax, word ptr [r14+6]
0x180016639  and     byte ptr [r14+8], 3Fh
0x18001663e  ror     ax, 8
0x180016642  and     ax, cx
0x180016645  or      ax, 5000h
0x180016649  or      byte ptr [r14+8], 80h
0x18001664e  mov     [r14+6], ax
0x180016653  mov     rcx, [rbp+phHash]; hHash
0x180016657  test    rcx, rcx
0x18001665a  jz      short loc_180016668
0x18001665c  call    cs:__imp_BCryptDestroyHash
0x180016663  nop     dword ptr [rax+rax+00h]
0x180016668  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001666c  test    rcx, rcx
0x18001666f  jz      short loc_18001667F
0x180016671  xor     edx, edx; dwFlags
0x180016673  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001667a  nop     dword ptr [rax+rax+00h]
0x18001667f  test    rsi, rsi
0x180016682  jz      short loc_18001668C
0x180016684  mov     rcx, rsi; void *
0x180016687  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001668c  test    rdi, rdi
0x18001668f  jz      short loc_180016699
0x180016691  mov     rcx, rdi; void *
0x180016694  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016699  test    ebx, ebx
0x18001669b  js      short loc_1800166A1
0x18001669d  xor     ebx, ebx
0x18001669f  jmp     short loc_1800166A5
0x1800166a1  bts     ebx, 1Ch
0x1800166a5  mov     eax, ebx
0x1800166a7  mov     rcx, [rbp+var_8]
0x1800166ab  xor     rcx, rsp; StackCookie
0x1800166ae  call    __security_check_cookie
0x1800166b3  mov     rbx, [rsp+70h+arg_0]
0x1800166bb  add     rsp, 70h
0x1800166bf  pop     r15
0x1800166c1  pop     r14
0x1800166c3  pop     r13
0x1800166c5  pop     r12
0x1800166c7  pop     rdi
0x1800166c8  pop     rsi
0x1800166c9  pop     rbp
0x1800166ca  retn
```
