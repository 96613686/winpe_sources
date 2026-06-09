# GetMessageParam

- ea: `0x18002ad38`
- end: `0x18002ae69`
- name: `GetMessageParam`
- size: `305`
- prototype: `__int64 __fastcall(HCRYPTMSG hCryptMsg, DWORD dwParamType)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bba0`

## callees

- `0x18002ad38`
- `0x18002b22c`
- `0x18002c090`
- `0x18002c1b4`
- `0x18002c34c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002adee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ae49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002adee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ae49`
- `CRYPT32!CryptMsgGetParam` at `0x18002ad6f`
- `CRYPT32!CryptMsgGetParam` at `0x18002ae1f`
- `CRYPT32!CryptMsgGetParam` at `0x18002ad6f`
- `CRYPT32!CryptMsgGetParam` at `0x18002ae1f`

## string_xrefs

- `0x18002ad7e`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002adab`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002ae2e`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall GetMessageParam(HCRYPTMSG hCryptMsg, DWORD dwParamType, _QWORD *a3, DWORD *a4)
{
  const char *v8; // r9
  __int64 result; // rax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 unique_hlocal; // rax
  HLOCAL v13; // rcx
  void *v14; // rbx
  const char *v15; // r9
  unsigned int LastError; // edi
  int pcbData; // [rsp+20h] [rbp-58h]
  DWORD v18; // [rsp+30h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-40h] BYREF
  void *pvData; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v18 = 0;
  pvData = 0;
  if ( !CryptMsgGetParam(hCryptMsg, dwParamType, 0, 0, &v18) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x32C,
             (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
             v8);
  if ( !v18 )
  {
    v10 = -2147024809;
    v11 = 813;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
      (const char *)v10,
      pcbData);
    return v10;
  }
  unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, v18);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
    &pvData,
    unique_hlocal);
  v13 = hMem;
  hMem = 0;
  if ( v13 )
    LocalFree(v13);
  v14 = pvData;
  if ( !pvData )
  {
    v10 = -2147024882;
    v11 = 816;
    goto LABEL_5;
  }
  if ( CryptMsgGetParam(hCryptMsg, dwParamType, 0, pvData, &v18) )
  {
    *a4 = v18;
    result = 0;
    *a3 = v14;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x336,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
                  v15);
    if ( v14 )
      LocalFree(v14);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x18002ad38  push    rbx
0x18002ad3a  push    rbp
0x18002ad3b  push    rsi
0x18002ad3c  push    rdi
0x18002ad3d  push    r14
0x18002ad3f  sub     rsp, 50h
0x18002ad43  mov     rdi, r9
0x18002ad46  mov     [rsp+78h+var_48], 0
0x18002ad4e  mov     rsi, r8
0x18002ad51  mov     [rsp+78h+pvData], 0
0x18002ad5a  lea     rax, [rsp+78h+var_48]
0x18002ad5f  xor     r9d, r9d; pvData
0x18002ad62  xor     r8d, r8d; dwIndex
0x18002ad65  mov     qword ptr [rsp+78h+pcbData], rax; int
0x18002ad6a  mov     ebp, edx
0x18002ad6c  mov     r14, rcx
0x18002ad6f  call    cs:__imp_CryptMsgGetParam
0x18002ad75  test    eax, eax
0x18002ad77  jnz     short loc_18002AD94
0x18002ad79  mov     rcx, [rsp+78h]; this
0x18002ad7e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002ad85  mov     edx, 32Ch; void *
0x18002ad8a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ad8f  jmp     loc_18002AE5E
0x18002ad94  mov     eax, [rsp+78h+var_48]
0x18002ad98  test    eax, eax
0x18002ad9a  jnz     short loc_18002ADC1
0x18002ad9c  mov     ebx, 80070057h
0x18002ada1  mov     edx, 32Dh; void *
0x18002ada6  mov     rcx, [rsp+78h]; this
0x18002adab  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002adb2  mov     r9d, ebx; char *
0x18002adb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002adba  mov     eax, ebx
0x18002adbc  jmp     loc_18002AE5E
0x18002adc1  mov     rdx, rax
0x18002adc4  lea     rcx, [rsp+78h+hMem]
0x18002adc9  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18002adce  mov     rdx, rax
0x18002add1  lea     rcx, [rsp+78h+pvData]
0x18002add6  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18002addb  mov     rcx, [rsp+78h+hMem]; hMem
0x18002ade0  mov     [rsp+78h+hMem], 0
0x18002ade9  test    rcx, rcx
0x18002adec  jz      short loc_18002ADF4
0x18002adee  call    cs:__imp_LocalFree
0x18002adf4  mov     rbx, [rsp+78h+pvData]
0x18002adf9  test    rbx, rbx
0x18002adfc  jnz     short loc_18002AE0A
0x18002adfe  mov     ebx, 8007000Eh
0x18002ae03  mov     edx, 330h
0x18002ae08  jmp     short loc_18002ADA6
0x18002ae0a  lea     rax, [rsp+78h+var_48]
0x18002ae0f  mov     r9, rbx; pvData
0x18002ae12  xor     r8d, r8d; dwIndex
0x18002ae15  mov     qword ptr [rsp+78h+pcbData], rax; pcbData
0x18002ae1a  mov     edx, ebp; dwParamType
0x18002ae1c  mov     rcx, r14; hCryptMsg
0x18002ae1f  call    cs:__imp_CryptMsgGetParam
0x18002ae25  test    eax, eax
0x18002ae27  jnz     short loc_18002AE53
0x18002ae29  mov     rcx, [rsp+78h]; this
0x18002ae2e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002ae35  mov     edx, 336h; void *
0x18002ae3a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ae3f  mov     edi, eax
0x18002ae41  test    rbx, rbx
0x18002ae44  jz      short loc_18002AE4F
0x18002ae46  mov     rcx, rbx; hMem
0x18002ae49  call    cs:__imp_LocalFree
0x18002ae4f  mov     eax, edi
0x18002ae51  jmp     short loc_18002AE5E
0x18002ae53  mov     eax, [rsp+78h+var_48]
0x18002ae57  mov     [rdi], eax
0x18002ae59  xor     eax, eax
0x18002ae5b  mov     [rsi], rbx
0x18002ae5e  add     rsp, 50h
0x18002ae62  pop     r14
0x18002ae64  pop     rdi
0x18002ae65  pop     rsi
0x18002ae66  pop     rbp
0x18002ae67  pop     rbx
0x18002ae68  retn
```
