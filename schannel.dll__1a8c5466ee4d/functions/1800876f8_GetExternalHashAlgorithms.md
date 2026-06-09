# GetExternalHashAlgorithms

- ea: `0x1800876f8`
- end: `0x1800879b2`
- name: `GetExternalHashAlgorithms`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c970`

## callees

- `0x18003ccdc`
- `0x180047ef8`
- `0x1800487bc`
- `0x1800597b0`
- `0x18005a148`
- `0x18005a160`
- `0x18005f160`
- `0x180087680`
- `0x1800876f8`
- `0x180087d00`
- `0x180087df0`
- `0x180087e10`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x1800877db`
- `ntdll!NtEnumerateKey` at `0x1800877db`
- `bcrypt!BCryptGetProperty` at `0x1800878c7`
- `bcrypt!BCryptGetProperty` at `0x1800878c7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800878d8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800878e3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800878d8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800878e3`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180087894`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180087894`

## string_xrefs

- `0x18008777d`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`
- `0x180087826`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`

## pseudocode

```c
__int64 GetExternalHashAlgorithms()
{
  __int64 result; // rax
  ULONG v1; // edi
  unsigned __int64 v2; // r9
  __int64 v3; // rbx
  wchar_t *v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // ecx
  UCHAR pbOutput[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+34h] [rbp-CCh]
  HANDLE v9; // [rsp+38h] [rbp-C8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  int KeyInformation; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[12]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 v16[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszAlgId[64]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v18[64]; // [rsp+300h] [rbp+200h] BYREF

  KeyHandle[0] = 0;
  v9 = 0;
  memset_0(v18, 0, sizeof(v18));
  memset_0(pszAlgId, 0, sizeof(pszAlgId));
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  pcbResult = 0;
  v8 = 0;
  result = FreeExternalHashAlgorithms();
  if ( (unsigned int)g_dwHashInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol Provider\\Hash",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      v1 = 0;
      if ( (unsigned int)g_dwHashInfoTotalCount < 0x10 )
      {
        while ( 1 )
        {
          KeyInformation = 0;
          memset_0(v15, 0, 0x214u);
          ResultLength = 0;
          if ( NtEnumerateKey(KeyHandle[0], v1, KeyBasicInformation, &KeyInformation, 0x218u, &ResultLength) < 0 )
            return TlsCloseRegKey(KeyHandle);
          v2 = -1;
          do
            ++v2;
          while ( v16[v2] );
          if ( (int)RtlStringCchCopyNW(v18, 0x40u, v16, v2) < 0
            || (int)TlsOpenRegKey(
                      L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Pr"
                       "otocol Provider\\Hash",
                      v18,
                      &v9) < 0 )
          {
            goto LABEL_19;
          }
          if ( (int)GetSslStringFromRegistry(v9, L"CngAlgorithm", pszAlgId) < 0 || (int)GetSslDWordFromRegistry(v9) < 0 )
          {
            TlsCloseRegKey(&v9);
            goto LABEL_19;
          }
          TlsCloseRegKey(&v9);
          if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) < 0 )
            goto LABEL_19;
          if ( BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0) < 0 )
            break;
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
          v3 = SafeAllocaAllocateFromHeap(24);
          if ( !v3 )
            goto LABEL_19;
          *(_OWORD *)v3 = 0;
          *(_QWORD *)(v3 + 16) = 0;
          v4 = (wchar_t *)SafeAllocaAllocateFromHeap(128);
          *(_QWORD *)v3 = v4;
          if ( !v4 )
          {
            SchannelFree(v3);
            goto LABEL_19;
          }
          wcscpy_s(v4, 0x40u, pszAlgId);
          v5 = (unsigned int)g_dwHashInfoTotalCount;
          *(_DWORD *)(v3 + 8) = *(_DWORD *)pbOutput;
          g_pHashInfo[v5] = v3;
          *(_DWORD *)(v3 + 16) = v5 + 36857;
          *(_DWORD *)(v3 + 12) = v5 - 268435462;
          v6 = v5 + 1;
          *(_DWORD *)(v3 + 20) = v8;
          g_dwHashInfoTotalCount = v6;
LABEL_20:
          ++v1;
          if ( v6 >= 0x10 )
            return TlsCloseRegKey(KeyHandle);
        }
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
LABEL_19:
        v6 = g_dwHashInfoTotalCount;
        goto LABEL_20;
      }
      return TlsCloseRegKey(KeyHandle);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800876f8  push    rbp
0x1800876fa  push    rbx
0x1800876fb  push    rsi
0x1800876fc  push    rdi
0x1800876fd  push    r14
0x1800876ff  lea     rbp, [rsp-290h]
0x180087707  sub     rsp, 390h
0x18008770e  mov     rax, cs:__security_cookie
0x180087715  xor     rax, rsp
0x180087718  mov     [rbp+2B0h+var_30], rax
0x18008771f  xor     esi, esi
0x180087721  lea     rcx, [rbp+2B0h+var_B0]; void *
0x180087728  mov     r14d, 80h
0x18008772e  mov     [rsp+3B0h+KeyHandle], rsi
0x180087733  mov     r8d, r14d; Size
0x180087736  mov     [rsp+3B0h+var_378], rsi
0x18008773b  xor     edx, edx; Val
0x18008773d  call    memset_0
0x180087742  mov     r8d, r14d; Size
0x180087745  lea     rcx, [rbp+2B0h+pszAlgId]; void *
0x18008774c  xor     edx, edx; Val
0x18008774e  call    memset_0
0x180087753  mov     dword ptr [rsp+3B0h+pbOutput], esi
0x180087757  mov     [rsp+3B0h+phAlgorithm], rsi
0x18008775c  mov     [rsp+3B0h+pcbResult], esi
0x180087760  mov     [rsp+3B0h+var_37C], esi
0x180087764  call    FreeExternalHashAlgorithms
0x180087769  cmp     cs:g_dwHashInfoTotalCount, 10h
0x180087770  jnb     loc_180087995
0x180087776  lea     r8, [rsp+3B0h+KeyHandle]; KeyHandle
0x18008777b  xor     edx, edx; PCWSTR
0x18008777d  lea     rcx, aRegistryMachin; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180087784  call    TlsOpenRegKey
0x180087789  test    eax, eax
0x18008778b  js      loc_180087995
0x180087791  cmp     cs:g_dwHashInfoTotalCount, 10h
0x180087798  mov     edi, esi
0x18008779a  jnb     loc_18008798B
0x1800877a0  xor     edx, edx; Val
0x1800877a2  mov     [rsp+3B0h+KeyInformation], esi
0x1800877a6  mov     r8d, 214h; Size
0x1800877ac  lea     rcx, [rsp+3B0h+var_34C]; void *
0x1800877b1  call    memset_0
0x1800877b6  mov     rcx, [rsp+3B0h+KeyHandle]; KeyHandle
0x1800877bb  lea     rax, [rsp+3B0h+var_368]
0x1800877c0  mov     [rsp+3B0h+ResultLength], rax; ResultLength
0x1800877c5  lea     r9, [rsp+3B0h+KeyInformation]; KeyInformation
0x1800877ca  xor     r8d, r8d; KeyInformationClass
0x1800877cd  mov     [rsp+3B0h+Length], 218h; Length
0x1800877d5  mov     edx, edi; Index
0x1800877d7  mov     [rsp+3B0h+var_368], esi
0x1800877db  call    cs:__imp_NtEnumerateKey
0x1800877e1  test    eax, eax
0x1800877e3  js      loc_18008798B
0x1800877e9  lea     rax, [rsp+3B0h+var_340]
0x1800877ee  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800877f2  inc     r9; unsigned __int64
0x1800877f5  cmp     [rax+r9*2], si
0x1800877fa  jnz     short loc_1800877F2
0x1800877fc  lea     r8, [rsp+3B0h+var_340]; unsigned __int16 *
0x180087801  mov     edx, 40h ; '@'; unsigned __int64
0x180087806  lea     rcx, [rbp+2B0h+var_B0]; unsigned __int16 *
0x18008780d  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180087812  test    eax, eax
0x180087814  js      loc_18008797A
0x18008781a  lea     r8, [rsp+3B0h+var_378]; KeyHandle
0x18008781f  lea     rdx, [rbp+2B0h+var_B0]; PCWSTR
0x180087826  lea     rcx, aRegistryMachin; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008782d  call    TlsOpenRegKey
0x180087832  test    eax, eax
0x180087834  js      loc_18008797A
0x18008783a  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x18008783f  lea     r8, [rbp+2B0h+pszAlgId]; unsigned __int16 *
0x180087846  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x18008784d  call    GetSslStringFromRegistry
0x180087852  test    eax, eax
0x180087854  js      loc_180087970
0x18008785a  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x18008785f  lea     r8, [rsp+3B0h+var_37C]
0x180087864  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x18008786b  call    GetSslDWordFromRegistry
0x180087870  test    eax, eax
0x180087872  js      loc_180087970
0x180087878  lea     rcx, [rsp+3B0h+var_378]
0x18008787d  call    TlsCloseRegKey
0x180087882  xor     r9d, r9d; dwFlags
0x180087885  lea     rdx, [rbp+2B0h+pszAlgId]; pszAlgId
0x18008788c  xor     r8d, r8d; pszImplementation
0x18008788f  lea     rcx, [rsp+3B0h+phAlgorithm]; phAlgorithm
0x180087894  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008789a  test    eax, eax
0x18008789c  js      loc_18008797A
0x1800878a2  mov     rcx, [rsp+3B0h+phAlgorithm]; hObject
0x1800878a7  lea     rax, [rsp+3B0h+pcbResult]
0x1800878ac  mov     dword ptr [rsp+3B0h+ResultLength], esi; dwFlags
0x1800878b0  lea     r8, [rsp+3B0h+pbOutput]; pbOutput
0x1800878b5  mov     r9d, 4; cbOutput
0x1800878bb  mov     qword ptr [rsp+3B0h+Length], rax; pcbResult
0x1800878c0  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800878c7  call    cs:__imp_BCryptGetProperty
0x1800878cd  mov     rcx, [rsp+3B0h+phAlgorithm]; hAlgorithm
0x1800878d2  xor     edx, edx; dwFlags
0x1800878d4  test    eax, eax
0x1800878d6  jns     short loc_1800878E3
0x1800878d8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800878de  jmp     loc_18008797A
0x1800878e3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800878e9  mov     ecx, 18h
0x1800878ee  call    SafeAllocaAllocateFromHeap
0x1800878f3  mov     rbx, rax
0x1800878f6  test    rax, rax
0x1800878f9  jz      short loc_18008797A
0x1800878fb  xorps   xmm0, xmm0
0x1800878fe  xor     eax, eax
0x180087900  movups  xmmword ptr [rbx], xmm0
0x180087903  mov     rcx, r14
0x180087906  mov     [rbx+10h], rax
0x18008790a  call    SafeAllocaAllocateFromHeap
0x18008790f  mov     [rbx], rax
0x180087912  test    rax, rax
0x180087915  jnz     short loc_180087921
0x180087917  mov     rcx, rbx
0x18008791a  call    SchannelFree
0x18008791f  jmp     short loc_18008797A
0x180087921  lea     r8, [rbp+2B0h+pszAlgId]; Source
0x180087928  mov     edx, 40h ; '@'; SizeInWords
0x18008792d  mov     rcx, rax; Destination
0x180087930  call    wcscpy_s
0x180087935  mov     ecx, cs:g_dwHashInfoTotalCount
0x18008793b  lea     rdx, g_pHashInfo
0x180087942  mov     eax, dword ptr [rsp+3B0h+pbOutput]
0x180087946  mov     [rbx+8], eax
0x180087949  lea     eax, [rcx+8FF9h]
0x18008794f  mov     [rdx+rcx*8], rbx
0x180087953  mov     [rbx+10h], eax
0x180087956  lea     eax, [rcx-10000006h]
0x18008795c  mov     [rbx+0Ch], eax
0x18008795f  inc     ecx
0x180087961  mov     eax, [rsp+3B0h+var_37C]
0x180087965  mov     [rbx+14h], eax
0x180087968  mov     cs:g_dwHashInfoTotalCount, ecx
0x18008796e  jmp     short loc_180087980
0x180087970  lea     rcx, [rsp+3B0h+var_378]
0x180087975  call    TlsCloseRegKey
0x18008797a  mov     ecx, cs:g_dwHashInfoTotalCount
0x180087980  inc     edi
0x180087982  cmp     ecx, 10h
0x180087985  jb      loc_1800877A0
0x18008798b  lea     rcx, [rsp+3B0h+KeyHandle]
0x180087990  call    TlsCloseRegKey
0x180087995  mov     rcx, [rbp+2B0h+var_30]
0x18008799c  xor     rcx, rsp; StackCookie
0x18008799f  call    __security_check_cookie
0x1800879a4  add     rsp, 390h
0x1800879ab  pop     r14
0x1800879ad  pop     rdi
0x1800879ae  pop     rsi
0x1800879af  pop     rbx
0x1800879b0  pop     rbp
0x1800879b1  retn
```
