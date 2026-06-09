# GetExternalSignatureAlgorithms

- ea: `0x180087038`
- end: `0x180087308`
- name: `GetExternalSignatureAlgorithms`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c970`

## callees

- `0x18003ccdc`
- `0x180047ef8`
- `0x1800487bc`
- `0x1800597b0`
- `0x18005a100`
- `0x18005a148`
- `0x18005a160`
- `0x18005f160`
- `0x180086fc0`
- `0x180087038`
- `0x180087d00`
- `0x180087df0`
- `0x180087e10`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x180087117`
- `ntdll!NtEnumerateKey` at `0x180087117`

## string_xrefs

- `0x1800870c1`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`
- `0x180087162`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`

## pseudocode

```c
__int64 GetExternalSignatureAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // r9
  __int64 v3; // rbx
  wchar_t *v4; // rax
  int v5; // ecx
  __int64 v6; // rax
  HANDLE v7; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+38h] [rbp-C8h]
  ULONG ResultLength; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  int KeyInformation; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v12[12]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 v13[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v15[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Source[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v7 = 0;
  memset_0(v15, 0, sizeof(v15));
  memset_0(Source, 0, sizeof(Source));
  memset_0(String1, 0, sizeof(String1));
  v8 = 0;
  result = FreeExternalSignatureAlgorithms();
  if ( (unsigned int)g_dwSignatureInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\Signature",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      for ( i = 0; (unsigned int)g_dwSignatureInfoTotalCount < 0x10; ++i )
      {
        KeyInformation = 0;
        memset_0(v12, 0, 0x214u);
        ResultLength = 0;
        if ( NtEnumerateKey(KeyHandle[0], i, KeyBasicInformation, &KeyInformation, 0x218u, &ResultLength) < 0 )
          break;
        v2 = -1;
        do
          ++v2;
        while ( v13[v2] );
        if ( (int)RtlStringCchCopyNW(v15, 0x40u, v13, v2) < 0 )
          break;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Signature",
                    v15,
                    &v7) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v7, L"CngAlgorithm", Source) < 0
            || (int)GetSslDWordFromRegistry(v7) < 0
            || (int)GetSslStringFromRegistry(v7, L"SignatureStyle", String1) < 0 )
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
                v5 = g_dwSignatureInfoTotalCount;
                *(_DWORD *)(v3 + 12) = g_dwSignatureInfoTotalCount + 12281;
                *(_DWORD *)(v3 + 8) = v5 - 536870918;
                *(_DWORD *)(v3 + 16) = v8;
                if ( wcsicmp(String1, L"RSA") )
                {
                  if ( wcsicmp(String1, L"DSA") )
                    *(_DWORD *)(v3 + 20) = wcsicmp(String1, L"ECDSA") == 0 ? 4 : 0;
                  else
                    *(_DWORD *)(v3 + 20) = 3;
                }
                else
                {
                  *(_DWORD *)(v3 + 20) = 2;
                }
                v6 = (unsigned int)g_dwSignatureInfoTotalCount++;
                g_pSignatureInfo[v6] = v3;
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
0x180087038  push    rbp
0x18008703a  push    rbx
0x18008703b  push    rsi
0x18008703c  push    rdi
0x18008703d  push    r14
0x18008703f  lea     rbp, [rsp-300h]
0x180087047  sub     rsp, 400h
0x18008704e  mov     rax, cs:__security_cookie
0x180087055  xor     rax, rsp
0x180087058  mov     [rbp+320h+var_30], rax
0x18008705f  xor     esi, esi
0x180087061  lea     rcx, [rbp+320h+var_130]; void *
0x180087068  mov     r14d, 80h
0x18008706e  mov     [rsp+420h+KeyHandle], rsi
0x180087073  mov     r8d, r14d; Size
0x180087076  mov     [rsp+420h+var_3F0], rsi
0x18008707b  xor     edx, edx; Val
0x18008707d  call    memset_0
0x180087082  mov     r8d, r14d; Size
0x180087085  lea     rcx, [rbp+320h+Source]; void *
0x18008708c  xor     edx, edx; Val
0x18008708e  call    memset_0
0x180087093  mov     r8d, r14d; Size
0x180087096  lea     rcx, [rbp+320h+String1]; void *
0x18008709d  xor     edx, edx; Val
0x18008709f  call    memset_0
0x1800870a4  mov     [rsp+420h+var_3E8], esi
0x1800870a8  call    FreeExternalSignatureAlgorithms
0x1800870ad  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x1800870b4  jnb     loc_1800872EB
0x1800870ba  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x1800870bf  xor     edx, edx; PCWSTR
0x1800870c1  lea     rcx, aRegistryMachin_1; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800870c8  call    TlsOpenRegKey
0x1800870cd  test    eax, eax
0x1800870cf  js      loc_1800872EB
0x1800870d5  mov     edi, esi
0x1800870d7  jmp     loc_1800872D4
0x1800870dc  xor     edx, edx; Val
0x1800870de  mov     [rsp+420h+KeyInformation], esi
0x1800870e2  mov     r8d, 214h; Size
0x1800870e8  lea     rcx, [rsp+420h+var_3CC]; void *
0x1800870ed  call    memset_0
0x1800870f2  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x1800870f7  lea     rax, [rsp+420h+var_3E4]
0x1800870fc  mov     [rsp+420h+ResultLength], rax; ResultLength
0x180087101  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x180087106  xor     r8d, r8d; KeyInformationClass
0x180087109  mov     [rsp+420h+Length], 218h; Length
0x180087111  mov     edx, edi; Index
0x180087113  mov     [rsp+420h+var_3E4], esi
0x180087117  call    cs:__imp_NtEnumerateKey
0x18008711d  test    eax, eax
0x18008711f  js      loc_1800872E1
0x180087125  lea     rax, [rsp+420h+var_3C0]
0x18008712a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008712e  inc     r9; unsigned __int64
0x180087131  cmp     [rax+r9*2], si
0x180087136  jnz     short loc_18008712E
0x180087138  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x18008713d  mov     edx, 40h ; '@'; unsigned __int64
0x180087142  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x180087149  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18008714e  test    eax, eax
0x180087150  js      loc_1800872E1
0x180087156  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x18008715b  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x180087162  lea     rcx, aRegistryMachin_1; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180087169  call    TlsOpenRegKey
0x18008716e  test    eax, eax
0x180087170  js      loc_1800872D2
0x180087176  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x18008717b  lea     r8, [rbp+320h+Source]; unsigned __int16 *
0x180087182  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180087189  call    GetSslStringFromRegistry
0x18008718e  test    eax, eax
0x180087190  js      loc_1800872C8
0x180087196  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x18008719b  lea     r8, [rsp+420h+var_3E8]
0x1800871a0  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x1800871a7  call    GetSslDWordFromRegistry
0x1800871ac  test    eax, eax
0x1800871ae  js      loc_1800872C8
0x1800871b4  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x1800871b9  lea     r8, [rbp+320h+String1]; unsigned __int16 *
0x1800871c0  lea     rdx, aSignaturestyle; "SignatureStyle"
0x1800871c7  call    GetSslStringFromRegistry
0x1800871cc  test    eax, eax
0x1800871ce  js      loc_1800872C8
0x1800871d4  lea     rcx, [rsp+420h+var_3F0]
0x1800871d9  call    TlsCloseRegKey
0x1800871de  mov     ecx, 18h
0x1800871e3  call    SafeAllocaAllocateFromHeap
0x1800871e8  mov     rbx, rax
0x1800871eb  test    rax, rax
0x1800871ee  jz      loc_1800872D2
0x1800871f4  xorps   xmm0, xmm0
0x1800871f7  xor     eax, eax
0x1800871f9  movups  xmmword ptr [rbx], xmm0
0x1800871fc  mov     rcx, r14
0x1800871ff  mov     [rbx+10h], rax
0x180087203  call    SafeAllocaAllocateFromHeap
0x180087208  mov     [rbx], rax
0x18008720b  test    rax, rax
0x18008720e  jnz     short loc_18008721D
0x180087210  mov     rcx, rbx
0x180087213  call    SchannelFree
0x180087218  jmp     loc_1800872D2
0x18008721d  lea     r8, [rbp+320h+Source]; Source
0x180087224  mov     edx, 40h ; '@'; SizeInWords
0x180087229  mov     rcx, rax; Destination
0x18008722c  call    wcscpy_s
0x180087231  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x180087237  lea     rdx, aRsa; "RSA"
0x18008723e  lea     eax, [rcx+2FF9h]
0x180087244  mov     [rbx+0Ch], eax
0x180087247  lea     eax, [rcx-20000006h]
0x18008724d  mov     [rbx+8], eax
0x180087250  lea     rcx, [rbp+320h+String1]; String1
0x180087257  mov     eax, [rsp+420h+var_3E8]
0x18008725b  mov     [rbx+10h], eax
0x18008725e  call    _wcsicmp
0x180087263  test    eax, eax
0x180087265  jnz     short loc_180087270
0x180087267  mov     dword ptr [rbx+14h], 2
0x18008726e  jmp     short loc_1800872AF
0x180087270  lea     rdx, aDsa; "DSA"
0x180087277  lea     rcx, [rbp+320h+String1]; String1
0x18008727e  call    _wcsicmp
0x180087283  test    eax, eax
0x180087285  jnz     short loc_180087290
0x180087287  mov     dword ptr [rbx+14h], 3
0x18008728e  jmp     short loc_1800872AF
0x180087290  lea     rdx, aEcdsa; "ECDSA"
0x180087297  lea     rcx, [rbp+320h+String1]; String1
0x18008729e  call    _wcsicmp
0x1800872a3  neg     eax
0x1800872a5  sbb     ecx, ecx
0x1800872a7  not     ecx
0x1800872a9  and     ecx, 4
0x1800872ac  mov     [rbx+14h], ecx
0x1800872af  mov     eax, cs:g_dwSignatureInfoTotalCount
0x1800872b5  lea     rcx, g_pSignatureInfo
0x1800872bc  inc     cs:g_dwSignatureInfoTotalCount
0x1800872c2  mov     [rcx+rax*8], rbx
0x1800872c6  jmp     short loc_1800872D2
0x1800872c8  lea     rcx, [rsp+420h+var_3F0]
0x1800872cd  call    TlsCloseRegKey
0x1800872d2  inc     edi
0x1800872d4  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x1800872db  jb      loc_1800870DC
0x1800872e1  lea     rcx, [rsp+420h+KeyHandle]
0x1800872e6  call    TlsCloseRegKey
0x1800872eb  mov     rcx, [rbp+320h+var_30]
0x1800872f2  xor     rcx, rsp; StackCookie
0x1800872f5  call    __security_check_cookie
0x1800872fa  add     rsp, 400h
0x180087301  pop     r14
0x180087303  pop     rdi
0x180087304  pop     rsi
0x180087305  pop     rbx
0x180087306  pop     rbp
0x180087307  retn
```
