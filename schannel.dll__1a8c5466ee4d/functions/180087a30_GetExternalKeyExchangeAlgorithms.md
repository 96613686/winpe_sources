# GetExternalKeyExchangeAlgorithms

- ea: `0x180087a30`
- end: `0x180087cf7`
- name: `GetExternalKeyExchangeAlgorithms`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c970`

## callees

- `0x18003ccdc`
- `0x1800487bc`
- `0x1800597b0`
- `0x18005a100`
- `0x18005a148`
- `0x18005a160`
- `0x18005f160`
- `0x1800879b8`
- `0x180087a30`
- `0x180087d00`
- `0x180087df0`
- `0x180087e10`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x180087b0b`
- `ntdll!NtEnumerateKey` at `0x180087b0b`

## string_xrefs

- `0x180087ab5`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`
- `0x180087b56`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`

## pseudocode

```c
__int64 GetExternalKeyExchangeAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // r9
  __int64 v3; // rbx
  wchar_t *v4; // rax
  int v5; // ecx
  __int64 v6; // rax
  HANDLE v7; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  int KeyInformation; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v11[12]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 v12[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v14[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Source[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v7 = 0;
  memset_0(v14, 0, sizeof(v14));
  memset_0(Source, 0, sizeof(Source));
  memset_0(String1, 0, sizeof(String1));
  result = FreeExternalKeyExchangeAlgorithms();
  if ( (unsigned int)g_dwKeyExchangeInfoTotalCount < 0xC )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\KeyExchange",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      for ( i = 0; (unsigned int)g_dwKeyExchangeInfoTotalCount < 0xC; ++i )
      {
        KeyInformation = 0;
        memset_0(v11, 0, 0x214u);
        ResultLength = 0;
        if ( NtEnumerateKey(KeyHandle[0], i, KeyBasicInformation, &KeyInformation, 0x218u, &ResultLength) < 0 )
          break;
        v2 = -1;
        do
          ++v2;
        while ( v12[v2] );
        if ( (int)RtlStringCchCopyNW(v14, 0x40u, v12, v2) < 0 )
          break;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\KeyExchange",
                    v14,
                    &v7) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v7, L"CngAlgorithm", Source) < 0
            || (int)GetSslStringFromRegistry(v7, L"MessageFlow", String1) < 0 )
          {
            TlsCloseRegKey(&v7);
          }
          else
          {
            TlsCloseRegKey(&v7);
            v3 = SafeAllocaAllocateFromHeap(24);
            if ( v3 )
            {
              *(_OWORD *)v3 = 0;
              *(_QWORD *)(v3 + 16) = 0;
              v4 = (wchar_t *)SafeAllocaAllocateFromHeap(128);
              *(_QWORD *)v3 = v4;
              if ( v4 )
              {
                wcscpy_s(v4, 0x40u, Source);
                v5 = g_dwKeyExchangeInfoTotalCount;
                *(_DWORD *)(v3 + 12) = g_dwKeyExchangeInfoTotalCount + 45049;
                *(_DWORD *)(v3 + 8) = v5 - 805306374;
                if ( wcsicmp(String1, L"RSA") )
                {
                  if ( wcsicmp(String1, L"DH") )
                  {
                    if ( wcsicmp(String1, L"ECDH") )
                      *(_DWORD *)(v3 + 16) = wcsicmp(String1, L"PSK") == 0 ? 4 : 0;
                    else
                      *(_DWORD *)(v3 + 16) = 3;
                  }
                  else
                  {
                    *(_DWORD *)(v3 + 16) = 2;
                  }
                }
                else
                {
                  *(_DWORD *)(v3 + 16) = 1;
                }
                v6 = (unsigned int)g_dwKeyExchangeInfoTotalCount++;
                g_pKeyExchangeInfo[v6] = v3;
              }
              else
              {
                SchannelFree(v3);
              }
            }
          }
        }
      }
      return TlsCloseRegKey(KeyHandle);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180087a30  push    rbp
0x180087a32  push    rbx
0x180087a33  push    rsi
0x180087a34  push    rdi
0x180087a35  push    r14
0x180087a37  lea     rbp, [rsp-300h]
0x180087a3f  sub     rsp, 400h
0x180087a46  mov     rax, cs:__security_cookie
0x180087a4d  xor     rax, rsp
0x180087a50  mov     [rbp+320h+var_30], rax
0x180087a57  xor     esi, esi
0x180087a59  lea     rcx, [rbp+320h+var_130]; void *
0x180087a60  mov     r14d, 80h
0x180087a66  mov     [rsp+420h+KeyHandle], rsi
0x180087a6b  mov     r8d, r14d; Size
0x180087a6e  mov     [rsp+420h+var_3F0], rsi
0x180087a73  xor     edx, edx; Val
0x180087a75  call    memset_0
0x180087a7a  mov     r8d, r14d; Size
0x180087a7d  lea     rcx, [rbp+320h+Source]; void *
0x180087a84  xor     edx, edx; Val
0x180087a86  call    memset_0
0x180087a8b  mov     r8d, r14d; Size
0x180087a8e  lea     rcx, [rbp+320h+String1]; void *
0x180087a95  xor     edx, edx; Val
0x180087a97  call    memset_0
0x180087a9c  call    FreeExternalKeyExchangeAlgorithms
0x180087aa1  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x180087aa8  jnb     loc_180087CDA
0x180087aae  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x180087ab3  xor     edx, edx; PCWSTR
0x180087ab5  lea     rcx, aRegistryMachin_0; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180087abc  call    TlsOpenRegKey
0x180087ac1  test    eax, eax
0x180087ac3  js      loc_180087CDA
0x180087ac9  mov     edi, esi
0x180087acb  jmp     loc_180087CC3
0x180087ad0  xor     edx, edx; Val
0x180087ad2  mov     [rsp+420h+KeyInformation], esi
0x180087ad6  mov     r8d, 214h; Size
0x180087adc  lea     rcx, [rsp+420h+var_3CC]; void *
0x180087ae1  call    memset_0
0x180087ae6  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x180087aeb  lea     rax, [rsp+420h+var_3E8]
0x180087af0  mov     [rsp+420h+ResultLength], rax; ResultLength
0x180087af5  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x180087afa  xor     r8d, r8d; KeyInformationClass
0x180087afd  mov     [rsp+420h+Length], 218h; Length
0x180087b05  mov     edx, edi; Index
0x180087b07  mov     [rsp+420h+var_3E8], esi
0x180087b0b  call    cs:__imp_NtEnumerateKey
0x180087b11  test    eax, eax
0x180087b13  js      loc_180087CD0
0x180087b19  lea     rax, [rsp+420h+var_3C0]
0x180087b1e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180087b22  inc     r9; unsigned __int64
0x180087b25  cmp     [rax+r9*2], si
0x180087b2a  jnz     short loc_180087B22
0x180087b2c  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x180087b31  mov     edx, 40h ; '@'; unsigned __int64
0x180087b36  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x180087b3d  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180087b42  test    eax, eax
0x180087b44  js      loc_180087CD0
0x180087b4a  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x180087b4f  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x180087b56  lea     rcx, aRegistryMachin_0; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180087b5d  call    TlsOpenRegKey
0x180087b62  test    eax, eax
0x180087b64  js      loc_180087CC1
0x180087b6a  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x180087b6f  lea     r8, [rbp+320h+Source]; unsigned __int16 *
0x180087b76  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180087b7d  call    GetSslStringFromRegistry
0x180087b82  test    eax, eax
0x180087b84  js      loc_180087CB7
0x180087b8a  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x180087b8f  lea     r8, [rbp+320h+String1]; unsigned __int16 *
0x180087b96  lea     rdx, aMessageflow; "MessageFlow"
0x180087b9d  call    GetSslStringFromRegistry
0x180087ba2  test    eax, eax
0x180087ba4  js      loc_180087CB7
0x180087baa  lea     rcx, [rsp+420h+var_3F0]
0x180087baf  call    TlsCloseRegKey
0x180087bb4  mov     ecx, 18h
0x180087bb9  call    SafeAllocaAllocateFromHeap
0x180087bbe  mov     rbx, rax
0x180087bc1  test    rax, rax
0x180087bc4  jz      loc_180087CC1
0x180087bca  xorps   xmm0, xmm0
0x180087bcd  xor     eax, eax
0x180087bcf  movups  xmmword ptr [rbx], xmm0
0x180087bd2  mov     rcx, r14
0x180087bd5  mov     [rbx+10h], rax
0x180087bd9  call    SafeAllocaAllocateFromHeap
0x180087bde  mov     [rbx], rax
0x180087be1  test    rax, rax
0x180087be4  jnz     short loc_180087BF3
0x180087be6  mov     rcx, rbx
0x180087be9  call    SchannelFree
0x180087bee  jmp     loc_180087CC1
0x180087bf3  lea     r8, [rbp+320h+Source]; Source
0x180087bfa  mov     edx, 40h ; '@'; SizeInWords
0x180087bff  mov     rcx, rax; Destination
0x180087c02  call    wcscpy_s
0x180087c07  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x180087c0d  lea     rdx, aRsa; "RSA"
0x180087c14  lea     eax, [rcx+0AFF9h]
0x180087c1a  mov     [rbx+0Ch], eax
0x180087c1d  lea     eax, [rcx-30000006h]
0x180087c23  lea     rcx, [rbp+320h+String1]; String1
0x180087c2a  mov     [rbx+8], eax
0x180087c2d  call    _wcsicmp
0x180087c32  test    eax, eax
0x180087c34  jnz     short loc_180087C3F
0x180087c36  mov     dword ptr [rbx+10h], 1
0x180087c3d  jmp     short loc_180087C9E
0x180087c3f  lea     rdx, aDh; "DH"
0x180087c46  lea     rcx, [rbp+320h+String1]; String1
0x180087c4d  call    _wcsicmp
0x180087c52  test    eax, eax
0x180087c54  jnz     short loc_180087C5F
0x180087c56  mov     dword ptr [rbx+10h], 2
0x180087c5d  jmp     short loc_180087C9E
0x180087c5f  lea     rdx, aEcdh_0; "ECDH"
0x180087c66  lea     rcx, [rbp+320h+String1]; String1
0x180087c6d  call    _wcsicmp
0x180087c72  test    eax, eax
0x180087c74  jnz     short loc_180087C7F
0x180087c76  mov     dword ptr [rbx+10h], 3
0x180087c7d  jmp     short loc_180087C9E
0x180087c7f  lea     rdx, aPsk; "PSK"
0x180087c86  lea     rcx, [rbp+320h+String1]; String1
0x180087c8d  call    _wcsicmp
0x180087c92  neg     eax
0x180087c94  sbb     ecx, ecx
0x180087c96  not     ecx
0x180087c98  and     ecx, 4
0x180087c9b  mov     [rbx+10h], ecx
0x180087c9e  mov     eax, cs:g_dwKeyExchangeInfoTotalCount
0x180087ca4  lea     rcx, g_pKeyExchangeInfo
0x180087cab  inc     cs:g_dwKeyExchangeInfoTotalCount
0x180087cb1  mov     [rcx+rax*8], rbx
0x180087cb5  jmp     short loc_180087CC1
0x180087cb7  lea     rcx, [rsp+420h+var_3F0]
0x180087cbc  call    TlsCloseRegKey
0x180087cc1  inc     edi
0x180087cc3  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x180087cca  jb      loc_180087AD0
0x180087cd0  lea     rcx, [rsp+420h+KeyHandle]
0x180087cd5  call    TlsCloseRegKey
0x180087cda  mov     rcx, [rbp+320h+var_30]
0x180087ce1  xor     rcx, rsp; StackCookie
0x180087ce4  call    __security_check_cookie
0x180087ce9  add     rsp, 400h
0x180087cf0  pop     r14
0x180087cf2  pop     rdi
0x180087cf3  pop     rsi
0x180087cf4  pop     rbx
0x180087cf5  pop     rbp
0x180087cf6  retn
```
