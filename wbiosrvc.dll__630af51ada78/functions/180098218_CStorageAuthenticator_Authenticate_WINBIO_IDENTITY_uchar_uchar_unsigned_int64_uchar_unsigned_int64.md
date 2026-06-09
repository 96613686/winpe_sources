# CStorageAuthenticator::Authenticate(_WINBIO_IDENTITY *,uchar,uchar *,unsigned __int64,uchar *,unsigned __int64)

- ea: `0x180098218`
- end: `0x18009848f`
- name: `?Authenticate@CStorageAuthenticator@@QEAAJPEAU_WINBIO_IDENTITY@@EPEAE_K12@Z`
- size: `631`
- prototype: `int(CStorageAuthenticator *__hidden this, struct _WINBIO_IDENTITY *, unsigned __int8, unsigned __int8 *, unsigned __int64, unsigned __int8 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a2f0`
- `0x1800907a0`

## callees

- `0x180014854`
- `0x1800148b4`
- `0x180014914`
- `0x180060254`
- `0x180068f60`
- `0x18006b0a9`
- `0x18008177c`
- `0x180098218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800982ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800982ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009843b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009843b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180098389`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180098389`
- `CRYPT32!CryptUnprotectData` at `0x180098295`
- `CRYPT32!CryptUnprotectData` at `0x180098295`

## string_xrefs

- `0x1800983fa`: `Template hash size is invalid.`
- `0x180098393`: `Payload identity value is invalid for type WINBIO_ID_TYPE_SID.`
- `0x1800983f1`: `Template hash does not match.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageAuthenticator::Authenticate(
        CStorageAuthenticator *this,
        struct _WINBIO_IDENTITY *a2,
        __int64 a3,
        unsigned __int8 *a4,
        size_t Size,
        unsigned __int8 *a6,
        unsigned __int64 a7)
{
  char v8; // si
  BYTE *v10; // r10
  __int64 v11; // rcx
  signed int LastError; // eax
  unsigned int v13; // ebx
  const wchar_t *v14; // rcx
  BYTE *pbData; // rdi
  __int64 v16; // rdx
  WINBIO_IDENTITY_TYPE Type; // eax
  WINBIO_IDENTITY_TYPE v18; // eax
  WINBIO_IDENTITY_TYPE v19; // eax
  WINBIO_IDENTITY_TYPE v20; // eax
  __int64 v21; // rcx
  BYTE *v22; // rax
  __int64 cbData; // rcx
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-21h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-11h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-1h] BYREF

  v8 = a3;
  std::wstring::wstring(v27, a2, a3, a4);
  *(&pDataIn.cbData + 1) = 0;
  pDataOut = 0;
  pDataIn.pbData = v10;
  pDataIn.cbData = a7;
  if ( CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
  {
    if ( pDataOut.cbData >= 0x58 )
    {
      pbData = pDataOut.pbData;
      v16 = *((_QWORD *)pDataOut.pbData + 10);
      if ( pDataOut.cbData < (unsigned __int64)(v16 + 88) || v16 != Size )
      {
        v14 = L"Template hash size is invalid.";
        goto LABEL_33;
      }
      if ( v8 == -1 || v8 == pDataOut.pbData[76] )
      {
        Type = a2->Type;
        if ( a2->Type == *(_DWORD *)pDataOut.pbData )
        {
          if ( Type )
          {
            v18 = Type - 1;
            if ( v18 )
            {
              v19 = v18 - 1;
              if ( v19 )
              {
                v20 = v19 - 1;
                if ( v20 )
                {
                  if ( v20 != 1 )
                  {
                    v14 = L"Failed due to unknown identity type.";
                    goto LABEL_33;
                  }
                  if ( memcmp_0(&a2->Value, pDataOut.pbData + 4, 0x20u) )
                  {
                    v14 = L"Payload identity value is invalid for type WINBIO_ID_TYPE_SECURE_ID.";
                    goto LABEL_33;
                  }
                }
                else if ( !EqualSid(a2->Value.AccountSid.Data, pDataOut.pbData + 8) )
                {
                  v14 = L"Payload identity value is invalid for type WINBIO_ID_TYPE_SID.";
                  goto LABEL_33;
                }
              }
              else if ( *(_QWORD *)&a2->Value.Null != *(_QWORD *)(pDataOut.pbData + 4)
                     || *(_QWORD *)&a2->Value.AccountSid.Data[4] != *(_QWORD *)(pDataOut.pbData + 12) )
              {
                v14 = L"Payload identity value is invalid for type WINBIO_ID_TYPE_GUID.";
                goto LABEL_33;
              }
            }
            else if ( a2->Value.Null != *((_DWORD *)pDataOut.pbData + 1) )
            {
              v14 = L"Payload identity value is invalid for type WINBIO_ID_TYPE_WILDCARD.";
              goto LABEL_33;
            }
          }
          else if ( a2->Value.Null != *((_DWORD *)pDataOut.pbData + 1) )
          {
            v14 = L"Payload identity value is invalid for type WINBIO_ID_TYPE_NULL.";
            goto LABEL_33;
          }
          v13 = 0;
          if ( !memcmp_0(a4, pbData + 88, Size) )
            goto LABEL_34;
          v14 = L"Template hash does not match.";
          goto LABEL_33;
        }
        v14 = L"Payload identity type is invalid.";
      }
      else
      {
        v14 = L"Payload subfactor is invalid.";
      }
    }
    else
    {
      v14 = L"Size of plaintext blob elements is invalid.";
    }
LABEL_33:
    std::_WChar_traits<unsigned short>::length(v14);
    std::wstring::_Assign<unsigned short>(v27, v21);
    v13 = -2146861030;
    goto LABEL_34;
  }
  std::_WChar_traits<unsigned short>::length(L"Failed to unprotect data.");
  std::wstring::_Assign<unsigned short>(v27, v11);
  LastError = GetLastError();
  v13 = LastError;
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
LABEL_34:
  v22 = pDataOut.pbData;
  if ( pDataOut.pbData )
  {
    cbData = pDataOut.cbData;
    if ( pDataOut.cbData )
    {
      do
      {
        *v22++ = 0;
        --cbData;
      }
      while ( cbData );
    }
    LocalFree(pDataOut.pbData);
    pDataOut.pbData = 0;
    pDataOut.cbData = 0;
  }
  if ( (v13 & 0x80000000) != 0 )
    CBioTraceLogging::OnFailedAuthentication(v13, v27);
  std::wstring::_Tidy_deallocate(v27);
  return v13;
}

```

## disassembly

```asm
0x180098218  mov     [rsp-8+arg_0], rbx
0x18009821d  mov     [rsp-8+arg_10], rsi
0x180098222  push    rbp
0x180098223  push    rdi
0x180098224  push    r14
0x180098226  lea     rbp, [rsp-2Fh]
0x18009822b  sub     rsp, 90h
0x180098232  mov     rax, cs:__security_cookie
0x180098239  xor     rax, rsp
0x18009823c  mov     [rbp+3Fh+var_20], rax
0x180098240  mov     r14, r9
0x180098243  mov     sil, r8b
0x180098246  mov     rbx, rdx
0x180098249  mov     r10, [rbp+3Fh+arg_28]
0x18009824d  lea     rcx, [rbp+3Fh+var_40]
0x180098251  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180098256  nop
0x180098257  mov     dword ptr [rbp+3Fh+pDataIn+4], 0
0x18009825e  xorps   xmm0, xmm0
0x180098261  movups  xmmword ptr [rbp+3Fh+var_60.cbData], xmm0
0x180098265  mov     [rbp+3Fh+pDataIn.pbData], r10
0x180098269  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x18009826c  mov     [rbp+3Fh+pDataIn.cbData], eax
0x18009826f  lea     rax, [rbp+3Fh+var_60]
0x180098273  mov     [rsp+0A0h+pDataOut], rax; pDataOut
0x180098278  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x180098280  mov     [rsp+0A0h+pPromptStruct], 0; pPromptStruct
0x180098289  xor     r9d, r9d; pvReserved
0x18009828c  xor     r8d, r8d; pOptionalEntropy
0x18009828f  xor     edx, edx; ppszDataDescr
0x180098291  lea     rcx, [rbp+3Fh+pDataIn]; pDataIn
0x180098295  call    cs:__imp_CryptUnprotectData
0x18009829b  test    eax, eax
0x18009829d  jnz     short loc_1800982D8
0x18009829f  lea     rcx, aFailedToUnprot; "Failed to unprotect data."
0x1800982a6  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800982ab  mov     r8, rax
0x1800982ae  mov     rdx, rcx
0x1800982b1  lea     rcx, [rbp+3Fh+var_40]
0x1800982b5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800982ba  call    cs:__imp_GetLastError
0x1800982c0  mov     ebx, eax
0x1800982c2  test    eax, eax
0x1800982c4  jle     loc_18009841A
0x1800982ca  movzx   ebx, ax
0x1800982cd  or      ebx, 80070000h
0x1800982d3  jmp     loc_18009841A
0x1800982d8  cmp     [rbp+3Fh+var_60.cbData], 58h ; 'X'
0x1800982dc  jnb     short loc_1800982EA
0x1800982de  lea     rcx, aSizeOfPlaintex; "Size of plaintext blob elements is inva"...
0x1800982e5  jmp     loc_180098401
0x1800982ea  mov     rdi, [rbp+3Fh+var_60.pbData]
0x1800982ee  mov     rdx, [rdi+50h]
0x1800982f2  lea     rcx, [rdx+58h]
0x1800982f6  mov     eax, [rbp+3Fh+var_60.cbData]
0x1800982f9  cmp     rax, rcx
0x1800982fc  jb      loc_1800983FA
0x180098302  cmp     rdx, [rbp+3Fh+Size]
0x180098306  jnz     loc_1800983FA
0x18009830c  cmp     sil, 0FFh
0x180098310  jz      short loc_180098324
0x180098312  cmp     sil, [rdi+4Ch]
0x180098316  jz      short loc_180098324
0x180098318  lea     rcx, aPayloadSubfact; "Payload subfactor is invalid."
0x18009831f  jmp     loc_180098401
0x180098324  mov     eax, [rbx]
0x180098326  cmp     eax, [rdi]
0x180098328  jz      short loc_180098336
0x18009832a  lea     rcx, aPayloadIdentit_4; "Payload identity type is invalid."
0x180098331  jmp     loc_180098401
0x180098336  test    eax, eax
0x180098338  jz      loc_1800983CA
0x18009833e  sub     eax, 1
0x180098341  jz      short loc_1800983B9
0x180098343  sub     eax, 1
0x180098346  jz      short loc_18009839C
0x180098348  sub     eax, 1
0x18009834b  jz      short loc_180098381
0x18009834d  cmp     eax, 1
0x180098350  jz      short loc_18009835E
0x180098352  lea     rcx, aFailedDueToUnk; "Failed due to unknown identity type."
0x180098359  jmp     loc_180098401
0x18009835e  lea     rdx, [rdi+4]; Buf2
0x180098362  lea     rcx, [rbx+4]; Buf1
0x180098366  mov     r8d, 20h ; ' '; Size
0x18009836c  call    memcmp_0
0x180098371  test    eax, eax
0x180098373  jz      short loc_1800983DB
0x180098375  lea     rcx, aPayloadIdentit_2; "Payload identity value is invalid for t"...
0x18009837c  jmp     loc_180098401
0x180098381  lea     rdx, [rdi+8]; pSid2
0x180098385  lea     rcx, [rbx+8]; pSid1
0x180098389  call    cs:__imp_EqualSid
0x18009838f  test    eax, eax
0x180098391  jnz     short loc_1800983DB
0x180098393  lea     rcx, aPayloadIdentit_0; "Payload identity value is invalid for t"...
0x18009839a  jmp     short loc_180098401
0x18009839c  mov     rax, [rbx+4]
0x1800983a0  cmp     rax, [rdi+4]
0x1800983a4  jnz     short loc_1800983B0
0x1800983a6  mov     rax, [rbx+0Ch]
0x1800983aa  cmp     rax, [rdi+0Ch]
0x1800983ae  jz      short loc_1800983DB
0x1800983b0  lea     rcx, aPayloadIdentit_3; "Payload identity value is invalid for t"...
0x1800983b7  jmp     short loc_180098401
0x1800983b9  mov     eax, [rdi+4]
0x1800983bc  cmp     [rbx+4], eax
0x1800983bf  jz      short loc_1800983DB
0x1800983c1  lea     rcx, aPayloadIdentit_1; "Payload identity value is invalid for t"...
0x1800983c8  jmp     short loc_180098401
0x1800983ca  mov     eax, [rdi+4]
0x1800983cd  cmp     [rbx+4], eax
0x1800983d0  jz      short loc_1800983DB
0x1800983d2  lea     rcx, aPayloadIdentit; "Payload identity value is invalid for t"...
0x1800983d9  jmp     short loc_180098401
0x1800983db  xor     ebx, ebx
0x1800983dd  lea     rdx, [rdi+58h]; Buf2
0x1800983e1  mov     r8, [rbp+3Fh+Size]; Size
0x1800983e5  mov     rcx, r14; Buf1
0x1800983e8  call    memcmp_0
0x1800983ed  test    eax, eax
0x1800983ef  jz      short loc_18009841A
0x1800983f1  lea     rcx, aTemplateHashDo; "Template hash does not match."
0x1800983f8  jmp     short loc_180098401
0x1800983fa  lea     rcx, aTemplateHashSi; "Template hash size is invalid."
0x180098401  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180098406  mov     rdx, rcx
0x180098409  mov     r8, rax
0x18009840c  lea     rcx, [rbp+3Fh+var_40]
0x180098410  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180098415  mov     ebx, 8009801Ah
0x18009841a  mov     rax, [rbp+3Fh+var_60.pbData]
0x18009841e  test    rax, rax
0x180098421  jz      short loc_180098450
0x180098423  mov     ecx, [rbp+3Fh+var_60.cbData]
0x180098426  test    rcx, rcx
0x180098429  jz      short loc_180098437
0x18009842b  mov     byte ptr [rax], 0
0x18009842e  inc     rax
0x180098431  sub     rcx, 1
0x180098435  jnz     short loc_18009842B
0x180098437  mov     rcx, [rbp+3Fh+var_60.pbData]; hMem
0x18009843b  call    cs:__imp_LocalFree
0x180098441  mov     [rbp+3Fh+var_60.pbData], 0
0x180098449  mov     [rbp+3Fh+var_60.cbData], 0
0x180098450  test    ebx, ebx
0x180098452  jns     short loc_180098460
0x180098454  lea     rdx, [rbp+3Fh+var_40]
0x180098458  mov     ecx, ebx
0x18009845a  call    ?OnFailedAuthentication@CBioTraceLogging@@SAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CBioTraceLogging::OnFailedAuthentication(long,std::wstring const &)
0x18009845f  nop
0x180098460  lea     rcx, [rbp+3Fh+var_40]
0x180098464  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180098469  mov     eax, ebx
0x18009846b  mov     rcx, [rbp+3Fh+var_20]
0x18009846f  xor     rcx, rsp; StackCookie
0x180098472  call    __security_check_cookie
0x180098477  lea     r11, [rsp+0A0h+var_10]
0x18009847f  mov     rbx, [r11+20h]
0x180098483  mov     rsi, [r11+30h]
0x180098487  mov     rsp, r11
0x18009848a  pop     r14
0x18009848c  pop     rdi
0x18009848d  pop     rbp
0x18009848e  retn
```
