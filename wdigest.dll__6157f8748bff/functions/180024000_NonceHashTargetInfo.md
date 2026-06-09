# NonceHashTargetInfo

- ea: `0x180024000`
- end: `0x180024320`
- name: `NonceHashTargetInfo`
- size: `800`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, BYTE *pbData)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024328`
- `0x180024d4c`

## callees

- `0x180006d00`
- `0x18000c6f0`
- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x180024000`
- `0x180033500`
- `0x180033768`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002423b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002428c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002423b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002428c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800241c5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180024210`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800241c5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180024210`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180024162`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180024162`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800242bd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800242bd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180024261`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180024261`
- `ntdll!RtlLengthSid` at `0x1800241fd`
- `ntdll!RtlLengthSid` at `0x1800241fd`
- `ntdll!RtlUpcaseUnicodeString` at `0x1800240f3`
- `ntdll!RtlUpcaseUnicodeString` at `0x1800240f3`

## pseudocode

```c
__int64 __fastcall NonceHashTargetInfo(PCUNICODE_STRING SourceString, BYTE *pbData, __int64 a3)
{
  unsigned int v3; // ebx
  const BYTE *Buffer; // r14
  DWORD v5; // edi
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 Length; // rdx
  DWORD LastError; // eax
  __int64 v14; // rdx
  DWORD v15; // eax
  HCRYPTHASH hHash; // [rsp+30h] [rbp-50h] BYREF
  DWORD pdwDataLen; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  BYTE pbDataa[32]; // [rsp+50h] [rbp-30h] BYREF

  pdwDataLen = 32;
  hHash = 0;
  v3 = 0;
  Buffer = 0;
  v5 = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
  DestinationString = 0;
  if ( !SourceString->Buffer || !SourceString->Length )
  {
LABEL_18:
    if ( CryptCreateHash(g_hCryptProvAES, 0x800Cu, 0, 0, &hHash) )
    {
      if ( !v5 || CryptHashData(hHash, Buffer, v5, 0) )
      {
        if ( !pbData || (v15 = RtlLengthSid(pbData), CryptHashData(hHash, pbData, v15, 0)) )
        {
          if ( CryptGetHashParam(hHash, 2u, pbDataa, &pdwDataLen, 0) )
          {
            BinToHex(pbDataa, 16, a3);
            goto LABEL_39;
          }
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_23:
            v3 = -1073741595;
            goto LABEL_39;
          }
          LastError = GetLastError();
          v14 = 50;
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_23;
          LastError = GetLastError();
          v14 = 49;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_23;
        LastError = GetLastError();
        v14 = 48;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      LastError = GetLastError();
      v14 = 47;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids, LastError);
    goto LABEL_23;
  }
  v9 = UnicodeStringAllocate((__int64)&DestinationString, SourceString->Length >> 1);
  v3 = v9;
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 45;
LABEL_10:
      WPP_SF_d(v10[2], v11, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids, (unsigned int)v9);
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  v9 = RtlUpcaseUnicodeString(&DestinationString, SourceString, 0);
  v3 = v9;
  if ( v9 >= 0 )
  {
    Length = 30;
    if ( DestinationString.Length < 0x1Eu )
      Length = DestinationString.Length;
    Buffer = (const BYTE *)DestinationString.Buffer;
    v5 = 2 * (unsigned __int16)ustrlencounted(DestinationString.Buffer, Length);
    goto LABEL_18;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 46;
    goto LABEL_10;
  }
LABEL_39:
  if ( hHash )
  {
    CryptDestroyHash(hHash);
    hHash = 0;
  }
  UnicodeStringFree(&DestinationString);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x180024000  mov     [rsp-38h+arg_18], rbx
0x180024005  push    rbp
0x180024006  push    rsi
0x180024007  push    rdi
0x180024008  push    r12
0x18002400a  push    r13
0x18002400c  push    r14
0x18002400e  push    r15
0x180024010  mov     rbp, rsp
0x180024013  sub     rsp, 80h
0x18002401a  mov     rax, cs:__security_cookie
0x180024021  xor     rax, rsp
0x180024024  mov     [rbp+var_10], rax
0x180024028  xor     r13d, r13d
0x18002402b  mov     [rbp+pdwDataLen], 20h ; ' '
0x180024032  xorps   xmm0, xmm0
0x180024035  mov     [rbp+hHash], r13
0x180024039  mov     ebx, r13d
0x18002403c  mov     r14d, r13d
0x18002403f  mov     edi, r13d
0x180024042  mov     r12, r8
0x180024045  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180024049  mov     r15, rdx
0x18002404c  mov     rsi, rcx
0x18002404f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024056  lea     rax, WPP_GLOBAL_Control
0x18002405d  cmp     rcx, rax
0x180024060  jz      short loc_18002407C
0x180024062  test    byte ptr [rcx+1Ch], 80h
0x180024066  jz      short loc_18002407C
0x180024068  mov     rcx, [rcx+10h]
0x18002406c  lea     edx, [r13+2Ch]
0x180024070  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x180024077  call    WPP_SF_
0x18002407c  xorps   xmm0, xmm0
0x18002407f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180024083  cmp     [rsi+8], r13
0x180024087  jz      loc_180024147
0x18002408d  movzx   edx, word ptr [rsi]
0x180024090  test    dx, dx
0x180024093  jz      loc_180024147
0x180024099  shr     dx, 1
0x18002409c  lea     rcx, [rbp+DestinationString]
0x1800240a0  call    UnicodeStringAllocate
0x1800240a5  mov     ebx, eax
0x1800240a7  test    eax, eax
0x1800240a9  jns     short loc_1800240E9
0x1800240ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240b2  lea     rdi, WPP_GLOBAL_Control
0x1800240b9  cmp     rcx, rdi
0x1800240bc  jz      loc_1800242B4
0x1800240c2  test    byte ptr [rcx+1Ch], 1
0x1800240c6  jz      loc_1800242B4
0x1800240cc  mov     edx, 2Dh ; '-'
0x1800240d1  mov     rcx, [rcx+10h]
0x1800240d5  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x1800240dc  mov     r9d, eax
0x1800240df  call    WPP_SF_d
0x1800240e4  jmp     loc_1800242B4
0x1800240e9  xor     r8d, r8d; AllocateDestinationString
0x1800240ec  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800240f0  mov     rdx, rsi; SourceString
0x1800240f3  call    cs:__imp_RtlUpcaseUnicodeString
0x1800240f9  mov     ebx, eax
0x1800240fb  test    eax, eax
0x1800240fd  jns     short loc_180024127
0x1800240ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180024106  lea     rdi, WPP_GLOBAL_Control
0x18002410d  cmp     rcx, rdi
0x180024110  jz      loc_1800242B4
0x180024116  test    byte ptr [rcx+1Ch], 1
0x18002411a  jz      loc_1800242B4
0x180024120  mov     edx, 2Eh ; '.'
0x180024125  jmp     short loc_1800240D1
0x180024127  mov     edx, 1Eh
0x18002412c  cmp     [rbp+DestinationString.Length], dx
0x180024130  jnb     short loc_180024136
0x180024132  movzx   edx, [rbp+DestinationString.Length]
0x180024136  mov     r14, [rbp+DestinationString.Buffer]
0x18002413a  mov     rcx, r14
0x18002413d  call    ustrlencounted
0x180024142  movzx   edi, ax
0x180024145  add     edi, edi
0x180024147  mov     rcx, cs:?g_hCryptProvAES@@3_KA; hProv
0x18002414e  lea     rax, [rbp+hHash]
0x180024152  xor     r9d, r9d; dwFlags
0x180024155  mov     [rsp+80h+phHash], rax; phHash
0x18002415a  xor     r8d, r8d; hKey
0x18002415d  mov     edx, 800Ch; Algid
0x180024162  call    cs:__imp_CryptCreateHash
0x180024168  test    eax, eax
0x18002416a  jnz     short loc_1800241B4
0x18002416c  mov     rax, cs:WPP_GLOBAL_Control
0x180024173  lea     rdi, WPP_GLOBAL_Control
0x18002417a  cmp     rax, rdi
0x18002417d  jz      short loc_1800241AA
0x18002417f  test    byte ptr [rax+1Ch], 1
0x180024183  jz      short loc_1800241AA
0x180024185  call    cs:__imp_GetLastError
0x18002418b  mov     edx, 2Fh ; '/'
0x180024190  mov     rcx, cs:WPP_GLOBAL_Control
0x180024197  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x18002419e  mov     r9d, eax
0x1800241a1  mov     rcx, [rcx+10h]
0x1800241a5  call    WPP_SF_d
0x1800241aa  mov     ebx, 0C00000E5h
0x1800241af  jmp     loc_1800242B4
0x1800241b4  test    edi, edi
0x1800241b6  jz      short loc_1800241F5
0x1800241b8  mov     rcx, [rbp+hHash]; hHash
0x1800241bc  xor     r9d, r9d; dwFlags
0x1800241bf  mov     r8d, edi; dwDataLen
0x1800241c2  mov     rdx, r14; pbData
0x1800241c5  call    cs:__imp_CryptHashData
0x1800241cb  test    eax, eax
0x1800241cd  jnz     short loc_1800241F5
0x1800241cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800241d6  lea     rdi, WPP_GLOBAL_Control
0x1800241dd  cmp     rax, rdi
0x1800241e0  jz      short loc_1800241AA
0x1800241e2  test    byte ptr [rax+1Ch], 1
0x1800241e6  jz      short loc_1800241AA
0x1800241e8  call    cs:__imp_GetLastError
0x1800241ee  mov     edx, 30h ; '0'
0x1800241f3  jmp     short loc_180024190
0x1800241f5  test    r15, r15
0x1800241f8  jz      short loc_18002424B
0x1800241fa  mov     rcx, r15; Sid
0x1800241fd  call    cs:__imp_RtlLengthSid
0x180024203  mov     rcx, [rbp+hHash]; hHash
0x180024207  xor     r9d, r9d; dwFlags
0x18002420a  mov     r8d, eax; dwDataLen
0x18002420d  mov     rdx, r15; pbData
0x180024210  call    cs:__imp_CryptHashData
0x180024216  test    eax, eax
0x180024218  jnz     short loc_18002424B
0x18002421a  mov     rax, cs:WPP_GLOBAL_Control
0x180024221  lea     rdi, WPP_GLOBAL_Control
0x180024228  cmp     rax, rdi
0x18002422b  jz      loc_1800241AA
0x180024231  test    byte ptr [rax+1Ch], 1
0x180024235  jz      loc_1800241AA
0x18002423b  call    cs:__imp_GetLastError
0x180024241  mov     edx, 31h ; '1'
0x180024246  jmp     loc_180024190
0x18002424b  mov     rcx, [rbp+hHash]; hHash
0x18002424f  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180024253  lea     r8, [rbp+pbData]; pbData
0x180024257  mov     dword ptr [rsp+80h+phHash], r13d; dwFlags
0x18002425c  mov     edx, 2; dwParam
0x180024261  call    cs:__imp_CryptGetHashParam
0x180024267  test    eax, eax
0x180024269  jnz     short loc_18002429C
0x18002426b  mov     rax, cs:WPP_GLOBAL_Control
0x180024272  lea     rdi, WPP_GLOBAL_Control
0x180024279  cmp     rax, rdi
0x18002427c  jz      loc_1800241AA
0x180024282  test    byte ptr [rax+1Ch], 1
0x180024286  jz      loc_1800241AA
0x18002428c  call    cs:__imp_GetLastError
0x180024292  mov     edx, 32h ; '2'
0x180024297  jmp     loc_180024190
0x18002429c  mov     r8, r12
0x18002429f  lea     rcx, [rbp+pbData]
0x1800242a3  mov     edx, 10h
0x1800242a8  call    BinToHex
0x1800242ad  lea     rdi, WPP_GLOBAL_Control
0x1800242b4  mov     rcx, [rbp+hHash]; hHash
0x1800242b8  test    rcx, rcx
0x1800242bb  jz      short loc_1800242C7
0x1800242bd  call    cs:__imp_CryptDestroyHash
0x1800242c3  mov     [rbp+hHash], r13
0x1800242c7  lea     rcx, [rbp+DestinationString]
0x1800242cb  call    UnicodeStringFree
0x1800242d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242d7  cmp     rcx, rdi
0x1800242da  jz      short loc_1800242F7
0x1800242dc  test    byte ptr [rcx+1Ch], 80h
0x1800242e0  jz      short loc_1800242F7
0x1800242e2  mov     rcx, [rcx+10h]
0x1800242e6  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x1800242ed  mov     edx, 33h ; '3'
0x1800242f2  call    WPP_SF_
0x1800242f7  mov     eax, ebx
0x1800242f9  mov     rcx, [rbp+var_10]
0x1800242fd  xor     rcx, rsp; StackCookie
0x180024300  call    __security_check_cookie
0x180024305  mov     rbx, [rsp+80h+arg_18]
0x18002430d  add     rsp, 80h
0x180024314  pop     r15
0x180024316  pop     r14
0x180024318  pop     r13
0x18002431a  pop     r12
0x18002431c  pop     rdi
0x18002431d  pop     rsi
0x18002431e  pop     rbp
0x18002431f  retn
```
