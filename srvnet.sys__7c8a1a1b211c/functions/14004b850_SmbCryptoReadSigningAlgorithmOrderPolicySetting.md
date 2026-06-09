# SmbCryptoReadSigningAlgorithmOrderPolicySetting

- ea: `0x14004b850`
- end: `0x14004ba4d`
- name: `SmbCryptoReadSigningAlgorithmOrderPolicySetting`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1400147f1`
- `0x14001fa24`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x14002a540`
- `0x14002a840`
- `0x14004b850`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14004ba20`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004ba20`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14004b905`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004b8d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004b8d9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004b8ea`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004b8ea`

## string_xrefs

- `0x14004b89a`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall SmbCryptoReadSigningAlgorithmOrderPolicySetting(__int64 a1, void *a2, unsigned __int16 *a3)
{
  PVOID SystemRoutineAddress; // rax
  int v7; // eax
  size_t v8; // rdx
  unsigned int v9; // ebx
  const wchar_t *v10; // rbx
  unsigned __int16 i; // di
  unsigned __int16 j; // cx
  __int64 v13; // rax
  size_t pcchLength; // [rsp+30h] [rbp-99h] BYREF
  STRSAFE_PCNZWCH psz[2]; // [rsp+38h] [rbp-91h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v18[14]; // [rsp+60h] [rbp-69h] BYREF
  __int64 Src; // [rsp+D0h] [rbp+7h] BYREF
  int v20; // [rsp+D8h] [rbp+Fh]

  memset(v18, 0, sizeof(v18));
  LODWORD(v18[1]) = 304;
  Src = 0;
  v20 = 0;
  LODWORD(v18[4]) = 117440512;
  v18[2] = L"SigningAlgorithmOrder";
  v18[3] = psz;
  *(_OWORD *)psz = 0;
  pcchLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v7 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(0, a1, v18, 0, 0);
  v9 = v7;
  if ( v7 >= 0 )
  {
    v10 = psz[1];
    if ( !psz[1] )
    {
      v9 = -1073741772;
      goto LABEL_25;
    }
    for ( i = 0; *v10 && i < 3u; ++i )
    {
      if ( RtlStringCchLengthW(v10, v8, &pcchLength) < 0 )
        goto LABEL_5;
      if ( wcsicmp_0(v10, L"AES_GMAC") )
      {
        if ( wcsicmp_0(v10, L"AES_CMAC") )
        {
          if ( wcsicmp_0(v10, L"HMAC_SHA_256") )
            goto LABEL_5;
          v8 = 0;
        }
        else
        {
          v8 = 1;
        }
      }
      else
      {
        v8 = 2;
      }
      for ( j = 0; j < i; ++j )
      {
        if ( *((_DWORD *)&Src + j) == (_DWORD)v8 )
          goto LABEL_5;
      }
      v13 = i;
      *((_DWORD *)&Src + v13) = v8;
      v10 += pcchLength + 1;
    }
    if ( i )
    {
      memmove(a2, &Src, 4LL * i);
      *a3 = i;
      v9 = 0;
      goto LABEL_25;
    }
    goto LABEL_5;
  }
  if ( v7 == -1073741788 )
LABEL_5:
    v9 = -1073739509;
LABEL_25:
  RtlFreeUnicodeString((PUNICODE_STRING)psz);
  return v9;
}

```

## disassembly

```asm
0x14004b850  push    rbp
0x14004b852  push    rbx
0x14004b853  push    rsi
0x14004b854  push    rdi
0x14004b855  push    r12
0x14004b857  push    r14
0x14004b859  push    r15
0x14004b85b  lea     rbp, [rsp-27h]
0x14004b860  sub     rsp, 0F0h
0x14004b867  mov     rax, cs:__security_cookie
0x14004b86e  xor     rax, rsp
0x14004b871  mov     [rbp+57h+var_40], rax
0x14004b875  mov     rsi, rdx
0x14004b878  mov     r14, r8
0x14004b87b  xor     edx, edx; Val
0x14004b87d  mov     rbx, rcx
0x14004b880  lea     rcx, [rbp+57h+var_C0]; void *
0x14004b884  lea     r8d, [rdx+70h]; Size
0x14004b888  call    memset
0x14004b88d  xor     eax, eax
0x14004b88f  mov     [rbp+57h+var_B8], 130h
0x14004b896  mov     [rbp+57h+Src], rax
0x14004b89a  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14004b8a1  mov     [rbp+57h+var_48], eax
0x14004b8a4  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14004b8a9  xorps   xmm0, xmm0
0x14004b8ac  mov     [rbp+57h+var_A0], 7000000h
0x14004b8b3  lea     rax, aSigningalgorit; "SigningAlgorithmOrder"
0x14004b8ba  xor     r15d, r15d
0x14004b8bd  mov     [rbp+57h+var_B0], rax
0x14004b8c1  lea     rax, [rsp+120h+psz]
0x14004b8c6  mov     [rbp+57h+var_A8], rax
0x14004b8ca  movups  xmmword ptr [rsp+120h+psz], xmm0
0x14004b8cf  mov     [rsp+120h+pcchLength], r15
0x14004b8d4  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x14004b8d9  call    cs:__imp_RtlInitUnicodeString
0x14004b8e0  nop     dword ptr [rax+rax+00h]
0x14004b8e5  lea     rcx, [rsp+120h+DestinationString]; SystemRoutineName
0x14004b8ea  call    cs:__imp_MmGetSystemRoutineAddress
0x14004b8f1  nop     dword ptr [rax+rax+00h]
0x14004b8f6  lea     r8, [rbp+57h+var_C0]
0x14004b8fa  mov     [rsp+120h+var_100], r15
0x14004b8ff  test    rax, rax
0x14004b902  mov     rdx, rbx
0x14004b905  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14004b90d  xor     r9d, r9d
0x14004b910  xor     ecx, ecx
0x14004b912  call    _guard_dispatch_icall
0x14004b917  mov     ebx, eax
0x14004b919  test    eax, eax
0x14004b91b  jns     short loc_14004B932
0x14004b91d  cmp     eax, 0C0000024h
0x14004b922  jnz     loc_14004BA1B
0x14004b928  mov     ebx, 0C000090Bh
0x14004b92d  jmp     loc_14004BA1B
0x14004b932  mov     rbx, [rsp+120h+psz+8]
0x14004b937  test    rbx, rbx
0x14004b93a  jnz     short loc_14004B946
0x14004b93c  mov     ebx, 0C0000034h
0x14004b941  jmp     loc_14004BA1B
0x14004b946  mov     edi, r15d
0x14004b949  mov     r12d, 1
0x14004b94f  cmp     [rbx], r15w
0x14004b953  jz      loc_14004B9F6
0x14004b959  cmp     di, 3
0x14004b95d  jnb     loc_14004B9F6
0x14004b963  lea     r8, [rsp+120h+pcchLength]; pcchLength
0x14004b968  mov     rcx, rbx; psz
0x14004b96b  call    RtlStringCchLengthW
0x14004b970  test    eax, eax
0x14004b972  js      short loc_14004B928
0x14004b974  lea     rdx, aAesGmac; "AES_GMAC"
0x14004b97b  mov     rcx, rbx; Str1
0x14004b97e  call    _wcsicmp_0
0x14004b983  test    eax, eax
0x14004b985  jnz     short loc_14004B98C
0x14004b987  lea     edx, [rax+2]
0x14004b98a  jmp     short loc_14004B9BE
0x14004b98c  lea     rdx, aAesCmac; "AES_CMAC"
0x14004b993  mov     rcx, rbx; Str1
0x14004b996  call    _wcsicmp_0
0x14004b99b  test    eax, eax
0x14004b99d  jnz     short loc_14004B9A4
0x14004b99f  mov     edx, r12d
0x14004b9a2  jmp     short loc_14004B9BE
0x14004b9a4  lea     rdx, aHmacSha256; "HMAC_SHA_256"
0x14004b9ab  mov     rcx, rbx; Str1
0x14004b9ae  call    _wcsicmp_0
0x14004b9b3  test    eax, eax
0x14004b9b5  jnz     loc_14004B928
0x14004b9bb  mov     edx, r15d
0x14004b9be  mov     ecx, r15d
0x14004b9c1  cmp     cx, di
0x14004b9c4  jnb     short loc_14004B9D9
0x14004b9c6  movzx   eax, cx
0x14004b9c9  cmp     dword ptr [rbp+rax*4+57h+Src], edx
0x14004b9cd  jz      loc_14004B928
0x14004b9d3  add     cx, r12w
0x14004b9d7  jmp     short loc_14004B9C1
0x14004b9d9  movzx   eax, di
0x14004b9dc  add     di, r12w
0x14004b9e0  mov     dword ptr [rbp+rax*4+57h+Src], edx
0x14004b9e4  mov     rax, [rsp+120h+pcchLength]
0x14004b9e9  lea     rbx, [rbx+rax*2]
0x14004b9ed  add     rbx, 2
0x14004b9f1  jmp     loc_14004B94F
0x14004b9f6  cmp     r15w, di
0x14004b9fa  jz      loc_14004B928
0x14004ba00  movzx   r8d, di
0x14004ba04  lea     rdx, [rbp+57h+Src]; Src
0x14004ba08  shl     r8, 2; Size
0x14004ba0c  mov     rcx, rsi; void *
0x14004ba0f  call    memmove
0x14004ba14  mov     [r14], di
0x14004ba18  mov     ebx, r15d
0x14004ba1b  lea     rcx, [rsp+120h+psz]; UnicodeString
0x14004ba20  call    cs:__imp_RtlFreeUnicodeString
0x14004ba27  nop     dword ptr [rax+rax+00h]
0x14004ba2c  mov     eax, ebx
0x14004ba2e  mov     rcx, [rbp+57h+var_40]
0x14004ba32  xor     rcx, rsp; StackCookie
0x14004ba35  call    __security_check_cookie
0x14004ba3a  add     rsp, 0F0h
0x14004ba41  pop     r15
0x14004ba43  pop     r14
0x14004ba45  pop     r12
0x14004ba47  pop     rdi
0x14004ba48  pop     rsi
0x14004ba49  pop     rbx
0x14004ba4a  pop     rbp
0x14004ba4b  retn
```
