# SmbCryptoReadCipherSuiteOrderPolicySetting

- ea: `0x14004b620`
- end: `0x14004b844`
- name: `SmbCryptoReadCipherSuiteOrderPolicySetting`
- size: `548`
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
- `0x14004b620`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14004b80e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004b80e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14004b6d8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004b6ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004b6ac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004b6bd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004b6bd`

## string_xrefs

- `0x14004b67e`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall SmbCryptoReadCipherSuiteOrderPolicySetting(__int64 a1, void *a2, unsigned __int16 *a3)
{
  PVOID SystemRoutineAddress; // rax
  int v7; // eax
  size_t i; // rdx
  unsigned int v9; // ebx
  STRSAFE_PCNZWCH v10; // rbx
  unsigned __int16 v11; // di
  int v12; // ecx
  __int64 v13; // rax
  size_t pcchLength; // [rsp+30h] [rbp-99h] BYREF
  STRSAFE_PCNZWCH psz[2]; // [rsp+38h] [rbp-91h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v18[14]; // [rsp+60h] [rbp-69h] BYREF
  __int128 Src; // [rsp+D0h] [rbp+7h] BYREF

  memset(v18, 0, sizeof(v18));
  LODWORD(v18[1]) = 304;
  LODWORD(v18[4]) = 117440512;
  v18[2] = L"CipherSuiteOrder";
  v18[3] = psz;
  pcchLength = 0;
  *(_OWORD *)psz = 0;
  Src = 0;
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
      goto LABEL_29;
    }
    v11 = 0;
    while ( 1 )
    {
      if ( !*v10 || v11 >= 4u )
      {
        if ( v11 )
        {
          memmove(a2, &Src, 4LL * v11);
          *a3 = v11;
          v9 = 0;
        }
        else
        {
          v9 = -1073741811;
        }
        goto LABEL_29;
      }
      if ( RtlStringCchLengthW(v10, i, &pcchLength) < 0 )
        goto LABEL_5;
      if ( wcsicmp_0(v10, L"AES_128_GCM") )
      {
        if ( wcsicmp_0(v10, L"AES_128_CCM") )
        {
          if ( wcsicmp_0(v10, L"AES_256_GCM") )
          {
            if ( wcsicmp_0(v10, L"AES_256_CCM") )
              goto LABEL_25;
            v12 = 3;
          }
          else
          {
            v12 = 4;
          }
        }
        else
        {
          v12 = 1;
        }
      }
      else
      {
        v12 = 2;
      }
      for ( i = 0; (unsigned __int16)i < v11; LOWORD(i) = i + 1 )
      {
        if ( *((_DWORD *)&Src + (unsigned __int16)i) == v12 )
          goto LABEL_5;
      }
      v13 = v11++;
      *((_DWORD *)&Src + v13) = v12;
LABEL_25:
      v10 += pcchLength + 1;
    }
  }
  if ( v7 == -1073741788 )
LABEL_5:
    v9 = -1073739509;
LABEL_29:
  RtlFreeUnicodeString((PUNICODE_STRING)psz);
  return v9;
}

```

## disassembly

```asm
0x14004b620  mov     [rsp-8+arg_18], rbx
0x14004b625  push    rbp
0x14004b626  push    rsi
0x14004b627  push    rdi
0x14004b628  push    r12
0x14004b62a  push    r13
0x14004b62c  push    r14
0x14004b62e  push    r15
0x14004b630  lea     rbp, [rsp-27h]
0x14004b635  sub     rsp, 0F0h
0x14004b63c  mov     rax, cs:__security_cookie
0x14004b643  xor     rax, rsp
0x14004b646  mov     [rbp+57h+var_40], rax
0x14004b64a  mov     rsi, rdx
0x14004b64d  mov     r14, r8
0x14004b650  xor     edx, edx; Val
0x14004b652  mov     rbx, rcx
0x14004b655  lea     rcx, [rbp+57h+var_C0]; void *
0x14004b659  lea     r8d, [rdx+70h]; Size
0x14004b65d  call    memset
0x14004b662  xorps   xmm0, xmm0
0x14004b665  mov     [rbp+57h+var_B8], 130h
0x14004b66c  lea     rax, aCiphersuiteord; "CipherSuiteOrder"
0x14004b673  mov     [rbp+57h+var_A0], 7000000h
0x14004b67a  mov     [rbp+57h+var_B0], rax
0x14004b67e  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14004b685  lea     rax, [rsp+120h+psz]
0x14004b68a  xorps   xmm1, xmm1
0x14004b68d  xor     r15d, r15d
0x14004b690  mov     [rbp+57h+var_A8], rax
0x14004b694  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14004b699  mov     [rsp+120h+pcchLength], r15
0x14004b69e  movups  xmmword ptr [rsp+120h+psz], xmm0
0x14004b6a3  movups  [rbp+57h+Src], xmm1
0x14004b6a7  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x14004b6ac  call    cs:__imp_RtlInitUnicodeString
0x14004b6b3  nop     dword ptr [rax+rax+00h]
0x14004b6b8  lea     rcx, [rsp+120h+DestinationString]; SystemRoutineName
0x14004b6bd  call    cs:__imp_MmGetSystemRoutineAddress
0x14004b6c4  nop     dword ptr [rax+rax+00h]
0x14004b6c9  lea     r8, [rbp+57h+var_C0]
0x14004b6cd  mov     [rsp+120h+var_100], r15
0x14004b6d2  test    rax, rax
0x14004b6d5  mov     rdx, rbx
0x14004b6d8  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14004b6e0  xor     r9d, r9d
0x14004b6e3  xor     ecx, ecx
0x14004b6e5  call    _guard_dispatch_icall
0x14004b6ea  mov     ebx, eax
0x14004b6ec  test    eax, eax
0x14004b6ee  jns     short loc_14004B705
0x14004b6f0  cmp     eax, 0C0000024h
0x14004b6f5  jnz     loc_14004B809
0x14004b6fb  mov     ebx, 0C000090Bh
0x14004b700  jmp     loc_14004B809
0x14004b705  mov     rbx, [rsp+120h+psz+8]
0x14004b70a  test    rbx, rbx
0x14004b70d  jnz     short loc_14004B719
0x14004b70f  mov     ebx, 0C0000034h
0x14004b714  jmp     loc_14004B809
0x14004b719  mov     r13d, 4
0x14004b71f  mov     edi, r15d
0x14004b722  lea     r12d, [r13-3]
0x14004b726  cmp     [rbx], r15w
0x14004b72a  jz      loc_14004B7E1
0x14004b730  cmp     di, r13w
0x14004b734  jnb     loc_14004B7E1
0x14004b73a  lea     r8, [rsp+120h+pcchLength]; pcchLength
0x14004b73f  mov     rcx, rbx; psz
0x14004b742  call    RtlStringCchLengthW
0x14004b747  test    eax, eax
0x14004b749  js      short loc_14004B6FB
0x14004b74b  lea     rdx, aAes128Gcm; "AES_128_GCM"
0x14004b752  mov     rcx, rbx; Str1
0x14004b755  call    _wcsicmp_0
0x14004b75a  test    eax, eax
0x14004b75c  jnz     short loc_14004B763
0x14004b75e  lea     ecx, [rax+2]
0x14004b761  jmp     short loc_14004B7A9
0x14004b763  lea     rdx, aAes128Ccm; "AES_128_CCM"
0x14004b76a  mov     rcx, rbx; Str1
0x14004b76d  call    _wcsicmp_0
0x14004b772  test    eax, eax
0x14004b774  jnz     short loc_14004B77B
0x14004b776  mov     ecx, r12d
0x14004b779  jmp     short loc_14004B7A9
0x14004b77b  lea     rdx, aAes256Gcm; "AES_256_GCM"
0x14004b782  mov     rcx, rbx; Str1
0x14004b785  call    _wcsicmp_0
0x14004b78a  test    eax, eax
0x14004b78c  jnz     short loc_14004B793
0x14004b78e  mov     ecx, r13d
0x14004b791  jmp     short loc_14004B7A9
0x14004b793  lea     rdx, aAes256Ccm; "AES_256_CCM"
0x14004b79a  mov     rcx, rbx; Str1
0x14004b79d  call    _wcsicmp_0
0x14004b7a2  test    eax, eax
0x14004b7a4  jnz     short loc_14004B7CF
0x14004b7a6  lea     ecx, [rax+3]
0x14004b7a9  mov     edx, r15d
0x14004b7ac  cmp     dx, di
0x14004b7af  jnb     short loc_14004B7C4
0x14004b7b1  movzx   eax, dx
0x14004b7b4  cmp     dword ptr [rbp+rax*4+57h+Src], ecx
0x14004b7b8  jz      loc_14004B6FB
0x14004b7be  add     dx, r12w
0x14004b7c2  jmp     short loc_14004B7AC
0x14004b7c4  movzx   eax, di
0x14004b7c7  add     di, r12w
0x14004b7cb  mov     dword ptr [rbp+rax*4+57h+Src], ecx
0x14004b7cf  mov     rax, [rsp+120h+pcchLength]
0x14004b7d4  lea     rbx, [rbx+rax*2]
0x14004b7d8  add     rbx, 2
0x14004b7dc  jmp     loc_14004B726
0x14004b7e1  cmp     r15w, di
0x14004b7e5  jnz     short loc_14004B7EE
0x14004b7e7  mov     ebx, 0C000000Dh
0x14004b7ec  jmp     short loc_14004B809
0x14004b7ee  movzx   r8d, di
0x14004b7f2  lea     rdx, [rbp+57h+Src]; Src
0x14004b7f6  shl     r8, 2; Size
0x14004b7fa  mov     rcx, rsi; void *
0x14004b7fd  call    memmove
0x14004b802  mov     [r14], di
0x14004b806  mov     ebx, r15d
0x14004b809  lea     rcx, [rsp+120h+psz]; UnicodeString
0x14004b80e  call    cs:__imp_RtlFreeUnicodeString
0x14004b815  nop     dword ptr [rax+rax+00h]
0x14004b81a  mov     eax, ebx
0x14004b81c  mov     rcx, [rbp+57h+var_40]
0x14004b820  xor     rcx, rsp; StackCookie
0x14004b823  call    __security_check_cookie
0x14004b828  mov     rbx, [rsp+120h+arg_18]
0x14004b830  add     rsp, 0F0h
0x14004b837  pop     r15
0x14004b839  pop     r14
0x14004b83b  pop     r13
0x14004b83d  pop     r12
0x14004b83f  pop     rdi
0x14004b840  pop     rsi
0x14004b841  pop     rbp
0x14004b842  retn
```
