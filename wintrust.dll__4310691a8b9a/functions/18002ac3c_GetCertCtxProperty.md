# GetCertCtxProperty

- ea: `0x18002ac3c`
- end: `0x18002ad31`
- name: `GetCertCtxProperty`
- size: `245`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b648`

## callees

- `0x18002ac3c`
- `0x18002b22c`
- `0x18002c090`
- `0x18002c1b4`
- `0x18002c34c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002acaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ad19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002acaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ad19`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002ac5e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002acef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002ac5e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002acef`

## string_xrefs

- `0x18002ac6d`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002acc4`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002acfe`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall GetCertCtxProperty(PCCERT_CONTEXT pCertContext, __int64 a2, _QWORD *a3, DWORD *a4)
{
  const char *v7; // r9
  __int64 unique_hlocal; // rax
  HLOCAL v10; // rcx
  void *v11; // rbx
  const char *v12; // r9
  unsigned int LastError; // edi
  HLOCAL hMem; // [rsp+20h] [rbp-38h] BYREF
  void *pvData; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  pvData = 0;
  if ( !CertGetCertificateContextProperty(pCertContext, 0x6Bu, 0, a4) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2C4,
             (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
             v7);
  unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, *a4);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
    &pvData,
    unique_hlocal);
  v10 = hMem;
  hMem = 0;
  if ( v10 )
    LocalFree(v10);
  v11 = pvData;
  if ( pvData )
  {
    if ( CertGetCertificateContextProperty(pCertContext, 0x6Bu, pvData, a4) )
    {
      *a3 = v11;
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2CC,
                    (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
                    v12);
      if ( v11 )
        LocalFree(v11);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
      (const char *)0x8007000ELL,
      (int)hMem);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18002ac3c  push    rbx
0x18002ac3e  push    rbp
0x18002ac3f  push    rsi
0x18002ac40  push    rdi
0x18002ac41  sub     rsp, 38h
0x18002ac45  mov     rsi, r8
0x18002ac48  mov     [rsp+58h+pvData], 0
0x18002ac51  xor     r8d, r8d; pvData
0x18002ac54  mov     rdi, r9
0x18002ac57  mov     rbp, rcx
0x18002ac5a  lea     edx, [r8+6Bh]; dwPropId
0x18002ac5e  call    cs:__imp_CertGetCertificateContextProperty
0x18002ac64  test    eax, eax
0x18002ac66  jnz     short loc_18002AC83
0x18002ac68  mov     rcx, [rsp+58h]; this
0x18002ac6d  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002ac74  mov     edx, 2C4h; void *
0x18002ac79  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ac7e  jmp     loc_18002AD28
0x18002ac83  mov     edx, [rdi]
0x18002ac85  lea     rcx, [rsp+58h+hMem]
0x18002ac8a  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18002ac8f  mov     rdx, rax
0x18002ac92  lea     rcx, [rsp+58h+pvData]
0x18002ac97  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18002ac9c  mov     rcx, [rsp+58h+hMem]; hMem
0x18002aca1  mov     [rsp+58h+hMem], 0; int
0x18002acaa  test    rcx, rcx
0x18002acad  jz      short loc_18002ACB5
0x18002acaf  call    cs:__imp_LocalFree
0x18002acb5  mov     rbx, [rsp+58h+pvData]
0x18002acba  test    rbx, rbx
0x18002acbd  jnz     short loc_18002ACE1
0x18002acbf  mov     rcx, [rsp+58h]; this
0x18002acc4  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002accb  mov     ebx, 8007000Eh
0x18002acd0  mov     edx, 2C7h; void *
0x18002acd5  mov     r9d, ebx; char *
0x18002acd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002acdd  mov     eax, ebx
0x18002acdf  jmp     short loc_18002AD28
0x18002ace1  mov     r9, rdi; pcbData
0x18002ace4  mov     r8, rbx; pvData
0x18002ace7  mov     edx, 6Bh ; 'k'; dwPropId
0x18002acec  mov     rcx, rbp; pCertContext
0x18002acef  call    cs:__imp_CertGetCertificateContextProperty
0x18002acf5  test    eax, eax
0x18002acf7  jnz     short loc_18002AD23
0x18002acf9  mov     rcx, [rsp+58h]; this
0x18002acfe  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002ad05  mov     edx, 2CCh; void *
0x18002ad0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ad0f  mov     edi, eax
0x18002ad11  test    rbx, rbx
0x18002ad14  jz      short loc_18002AD1F
0x18002ad16  mov     rcx, rbx; hMem
0x18002ad19  call    cs:__imp_LocalFree
0x18002ad1f  mov     eax, edi
0x18002ad21  jmp     short loc_18002AD28
0x18002ad23  mov     [rsi], rbx
0x18002ad26  xor     eax, eax
0x18002ad28  add     rsp, 38h
0x18002ad2c  pop     rdi
0x18002ad2d  pop     rsi
0x18002ad2e  pop     rbp
0x18002ad2f  pop     rbx
0x18002ad30  retn
```
