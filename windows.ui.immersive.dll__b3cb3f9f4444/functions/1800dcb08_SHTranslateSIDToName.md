# SHTranslateSIDToName

- ea: `0x1800dcb08`
- end: `0x1800dcd51`
- name: `SHTranslateSIDToName`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800cc550`

## callees

- `0x1800dc9a8`
- `0x1800dca00`
- `0x1800dcb08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dcbf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dcbf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dccfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dccfa`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800dcb57`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800dcb57`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800dcd15`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800dcd25`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800dcd15`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800dcd25`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800dcd35`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800dcd35`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x1800dcb9a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x1800dcb9a`

## pseudocode

```c
__int64 __fastcall SHTranslateSIDToName(void *a1, wchar_t **a2)
{
  HRESULT v3; // ebx
  int v4; // eax
  int v5; // eax
  unsigned int v6; // r8d
  unsigned __int64 v7; // rdi
  size_t *v8; // r8
  size_t v9; // r9
  wchar_t *v10; // r11
  size_t v11; // rdi
  size_t *v12; // r8
  size_t pcchDestLength; // [rsp+30h] [rbp-48h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
  PSID Sids; // [rsp+A0h] [rbp+28h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+A8h] [rbp+30h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+B0h] [rbp+38h] BYREF
  PVOID PolicyHandle; // [rsp+B8h] [rbp+40h] BYREF

  Sids = a1;
  *a2 = 0;
  v3 = -2147024809;
  if ( a1 )
  {
    PolicyHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle) | 0x10000000;
    if ( v4 < 0 )
      return (unsigned int)v4;
    ReferencedDomains = 0;
    Names = 0;
    v5 = LsaLookupSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &Names) | 0x10000000;
    if ( v5 < 0 )
    {
      v3 = v5;
      goto LABEL_24;
    }
    if ( (unsigned int)(Names->Use - 7) <= 1 )
    {
      v3 = -2147467259;
      goto LABEL_24;
    }
    v6 = Names->Name.Length + 2;
    if ( Names->DomainIndex >= 0 )
      v6 = ReferencedDomains->Domains[Names->DomainIndex].Name.Length + Names->Name.Length + 4;
    v7 = v6;
    v10 = (wchar_t *)CoTaskMemAlloc(v6);
    if ( v10 )
    {
      v11 = v7 >> 1;
      if ( Names->DomainIndex < 0 )
      {
        *v10 = 0;
      }
      else
      {
        if ( v11 )
        {
          v3 = StringCopyWorkerW(
                 v10,
                 v11,
                 v8,
                 ReferencedDomains->Domains[Names->DomainIndex].Name.Buffer,
                 (unsigned __int64)ReferencedDomains->Domains[Names->DomainIndex].Name.Length >> 1);
          if ( v3 >= 0 )
          {
            pcchDestLength = 0;
            v3 = StringValidateDestAndLengthW(v10, v11, &pcchDestLength, v9);
            if ( v3 >= 0 )
              v3 = StringCopyWorkerW(&v10[pcchDestLength], v11 - pcchDestLength, v12, L"\\", 0x7FFFFFFEu);
          }
        }
        if ( v3 < 0 )
          goto LABEL_21;
      }
      pcchDestLength = 0;
      v3 = StringValidateDestAndLengthW(v10, v11, &pcchDestLength, v9);
      if ( v3 >= 0 )
        v3 = StringCopyWorkerW(
               &v10[pcchDestLength],
               v11 - pcchDestLength,
               (size_t *)((unsigned __int64)Names->Name.Length >> 1),
               Names->Name.Buffer,
               (unsigned __int64)Names->Name.Length >> 1);
      if ( v3 >= 0 )
      {
        *a2 = v10;
        v10 = 0;
      }
    }
    else
    {
      v3 = -2147024882;
    }
LABEL_21:
    CoTaskMemFree(v10);
LABEL_24:
    LsaFreeMemory(ReferencedDomains);
    LsaFreeMemory(Names);
    LsaClose(PolicyHandle);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800dcb08  mov     [rsp-20h+Sids], rcx
0x1800dcb0d  push    rbp
0x1800dcb0e  push    rbx
0x1800dcb0f  push    rsi
0x1800dcb10  push    rdi
0x1800dcb11  mov     rbp, rsp
0x1800dcb14  sub     rsp, 78h
0x1800dcb18  mov     qword ptr [rdx], 0
0x1800dcb1f  mov     rsi, rdx
0x1800dcb22  mov     ebx, 80070057h
0x1800dcb27  test    rcx, rcx
0x1800dcb2a  jz      loc_1800DCD45
0x1800dcb30  xorps   xmm0, xmm0
0x1800dcb33  mov     [rbp+PolicyHandle], 0
0x1800dcb3b  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800dcb3f  mov     r8d, 800h; DesiredAccess
0x1800dcb45  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800dcb49  xor     ecx, ecx; SystemName
0x1800dcb4b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800dcb4f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800dcb53  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800dcb57  call    cs:__imp_LsaOpenPolicy
0x1800dcb5e  nop     dword ptr [rax+rax+00h]
0x1800dcb63  mov     edi, 10000000h
0x1800dcb68  or      eax, edi
0x1800dcb6a  jl      loc_1800DCD43
0x1800dcb70  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800dcb74  lea     rax, [rbp+arg_8]
0x1800dcb78  lea     r9, [rbp+ReferencedDomains]; ReferencedDomains
0x1800dcb7c  mov     [rsp+78h+Names], rax; Names
0x1800dcb81  lea     r8, [rbp+Sids]; Sids
0x1800dcb85  mov     [rbp+ReferencedDomains], 0
0x1800dcb8d  mov     edx, 1; Count
0x1800dcb92  mov     [rbp+arg_8], 0
0x1800dcb9a  call    cs:__imp_LsaLookupSids
0x1800dcba1  nop     dword ptr [rax+rax+00h]
0x1800dcba6  or      eax, edi
0x1800dcba8  jl      loc_1800DCD0F
0x1800dcbae  mov     rcx, [rbp+arg_8]
0x1800dcbb2  mov     eax, [rcx]
0x1800dcbb4  sub     eax, 7
0x1800dcbb7  cmp     eax, 1
0x1800dcbba  jbe     loc_1800DCD08
0x1800dcbc0  movzx   r8d, word ptr [rcx+8]
0x1800dcbc5  add     r8d, 2
0x1800dcbc9  cmp     dword ptr [rcx+18h], 0
0x1800dcbcd  jl      short loc_1800DCBEA
0x1800dcbcf  movsxd  rax, dword ptr [rcx+18h]
0x1800dcbd3  add     r8d, 2
0x1800dcbd7  lea     rdx, [rax+rax*2]
0x1800dcbdb  mov     rax, [rbp+ReferencedDomains]
0x1800dcbdf  mov     rcx, [rax+8]
0x1800dcbe3  movzx   eax, word ptr [rcx+rdx*8]
0x1800dcbe7  add     r8d, eax
0x1800dcbea  mov     ecx, r8d; cb
0x1800dcbed  mov     edi, r8d
0x1800dcbf0  call    cs:__imp_CoTaskMemAlloc
0x1800dcbf7  nop     dword ptr [rax+rax+00h]
0x1800dcbfc  mov     r11, rax
0x1800dcbff  test    rax, rax
0x1800dcc02  jz      loc_1800DCCF2
0x1800dcc08  mov     rax, [rbp+arg_8]
0x1800dcc0c  shr     rdi, 1
0x1800dcc0f  cmp     dword ptr [rax+18h], 0
0x1800dcc13  jl      loc_1800DCC99
0x1800dcc19  test    rdi, rdi
0x1800dcc1c  jz      short loc_1800DCC93
0x1800dcc1e  movsxd  rax, dword ptr [rax+18h]
0x1800dcc22  mov     rdx, rdi; cchDest
0x1800dcc25  lea     rcx, [rax+rax*2]
0x1800dcc29  mov     rax, [rbp+ReferencedDomains]
0x1800dcc2d  mov     r9, [rax+8]
0x1800dcc31  movzx   eax, word ptr [r9+rcx*8]
0x1800dcc36  mov     r9, [r9+rcx*8+8]; pszSrc
0x1800dcc3b  mov     rcx, r11; pszDest
0x1800dcc3e  shr     rax, 1
0x1800dcc41  mov     [rsp+78h+Names], rax; cchToCopy
0x1800dcc46  call    StringCopyWorkerW
0x1800dcc4b  mov     ebx, eax
0x1800dcc4d  test    eax, eax
0x1800dcc4f  js      short loc_1800DCC93
0x1800dcc51  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x1800dcc55  mov     [rbp+pcchDestLength], 0
0x1800dcc5d  mov     rdx, rdi; cchDest
0x1800dcc60  mov     rcx, r11; pszDest
0x1800dcc63  call    StringValidateDestAndLengthW
0x1800dcc68  mov     ebx, eax
0x1800dcc6a  test    eax, eax
0x1800dcc6c  js      short loc_1800DCC93
0x1800dcc6e  mov     rax, [rbp+pcchDestLength]
0x1800dcc72  lea     r9, pszSrc; "\\"
0x1800dcc79  mov     rdx, rdi
0x1800dcc7c  mov     [rsp+78h+Names], 7FFFFFFEh; cchToCopy
0x1800dcc85  sub     rdx, rax; cchDest
0x1800dcc88  lea     rcx, [r11+rax*2]; pszDest
0x1800dcc8c  call    StringCopyWorkerW
0x1800dcc91  mov     ebx, eax
0x1800dcc93  test    ebx, ebx
0x1800dcc95  jns     short loc_1800DCC9F
0x1800dcc97  jmp     short loc_1800DCCF7
0x1800dcc99  xor     eax, eax
0x1800dcc9b  mov     [r11], ax
0x1800dcc9f  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x1800dcca3  mov     [rbp+pcchDestLength], 0
0x1800dccab  mov     rdx, rdi; cchDest
0x1800dccae  mov     rcx, r11; pszDest
0x1800dccb1  call    StringValidateDestAndLengthW
0x1800dccb6  mov     ebx, eax
0x1800dccb8  test    eax, eax
0x1800dccba  js      short loc_1800DCCE6
0x1800dccbc  mov     r9, [rbp+arg_8]
0x1800dccc0  mov     rax, [rbp+pcchDestLength]
0x1800dccc4  sub     rdi, rax
0x1800dccc7  mov     rdx, rdi; cchDest
0x1800dccca  movzx   r8d, word ptr [r9+8]
0x1800dcccf  mov     r9, [r9+10h]; pszSrc
0x1800dccd3  lea     rcx, [r11+rax*2]; pszDest
0x1800dccd7  shr     r8, 1; pcchNewDestLength
0x1800dccda  mov     [rsp+78h+Names], r8; cchToCopy
0x1800dccdf  call    StringCopyWorkerW
0x1800dcce4  mov     ebx, eax
0x1800dcce6  test    ebx, ebx
0x1800dcce8  js      short loc_1800DCCF7
0x1800dccea  mov     [rsi], r11
0x1800dcced  xor     r11d, r11d
0x1800dccf0  jmp     short loc_1800DCCF7
0x1800dccf2  mov     ebx, 8007000Eh
0x1800dccf7  mov     rcx, r11; pv
0x1800dccfa  call    cs:__imp_CoTaskMemFree
0x1800dcd01  nop     dword ptr [rax+rax+00h]
0x1800dcd06  jmp     short loc_1800DCD11
0x1800dcd08  mov     ebx, 80004005h
0x1800dcd0d  jmp     short loc_1800DCD11
0x1800dcd0f  mov     ebx, eax
0x1800dcd11  mov     rcx, [rbp+ReferencedDomains]; Buffer
0x1800dcd15  call    cs:__imp_LsaFreeMemory
0x1800dcd1c  nop     dword ptr [rax+rax+00h]
0x1800dcd21  mov     rcx, [rbp+arg_8]; Buffer
0x1800dcd25  call    cs:__imp_LsaFreeMemory
0x1800dcd2c  nop     dword ptr [rax+rax+00h]
0x1800dcd31  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800dcd35  call    cs:__imp_LsaClose
0x1800dcd3c  nop     dword ptr [rax+rax+00h]
0x1800dcd41  jmp     short loc_1800DCD45
0x1800dcd43  mov     ebx, eax
0x1800dcd45  mov     eax, ebx
0x1800dcd47  add     rsp, 78h
0x1800dcd4b  pop     rdi
0x1800dcd4c  pop     rsi
0x1800dcd4d  pop     rbx
0x1800dcd4e  pop     rbp
0x1800dcd4f  retn
```
