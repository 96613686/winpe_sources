# ParseUTF8String

- ea: `0x18002ae70`
- end: `0x18002b038`
- name: `ParseUTF8String`
- size: `456`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027dac`
- `0x1800420f0`

## callees

- `0x18002ae70`
- `0x18002b22c`
- `0x18002c090`
- `0x18002c1b4`
- `0x18002c34c`
- `0x18002c394`
- `0x1800482c0`
- `0x18004de52`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002af10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b028`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002af10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b028`
- `CRYPT32!CryptDecodeObject` at `0x18002aebd`
- `CRYPT32!CryptDecodeObject` at `0x18002af6f`
- `CRYPT32!CryptDecodeObject` at `0x18002aebd`
- `CRYPT32!CryptDecodeObject` at `0x18002af6f`

## string_xrefs

- `0x18002aecc`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002af25`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002af7e`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x18002afe9`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall ParseUTF8String(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  DWORD v5; // r9d
  const BYTE *v6; // r8
  const char *v7; // r9
  __int64 unique_hlocal; // rax
  HLOCAL v10; // rcx
  const void **v11; // rbx
  unsigned int LastError; // edi
  __int64 v13; // rdx
  unsigned int v14; // r8d
  const char *v15; // r9
  __int64 v16; // r9
  __int64 v17; // rdx
  void *v18; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-38h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pcbStructInfo; // [rsp+60h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+10h] BYREF
  HLOCAL pvStructInfo; // [rsp+70h] [rbp+18h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  pcbStructInfo = 0;
  v5 = *(_DWORD *)v2;
  v6 = *(const BYTE **)(v2 + 8);
  pvStructInfo = 0;
  if ( !CryptDecodeObject(0x10001u, (LPCSTR)6, v6, v5, 0, 0, &pcbStructInfo) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x82D,
             (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
             v7);
  unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, pcbStructInfo);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
    &pvStructInfo,
    unique_hlocal);
  v10 = hMem;
  hMem = 0;
  if ( v10 )
    LocalFree(v10);
  v11 = (const void **)pvStructInfo;
  if ( pvStructInfo )
  {
    if ( CryptDecodeObject(
           0x10001u,
           (LPCSTR)6,
           *(const BYTE **)(*(_QWORD *)(a1 + 16) + 8LL),
           **(_DWORD **)(a1 + 16),
           0,
           pvStructInfo,
           &pcbStructInfo) )
    {
      v16 = 13;
      if ( *(_DWORD *)v11 == 13 )
      {
        if ( *((_DWORD *)v11 + 2) <= 0xFFFFu )
        {
          v18 = (void *)MincryptAlloc(*((unsigned int *)v11 + 2), v13);
          *(_QWORD *)(a2 + 8) = v18;
          if ( v18 )
          {
            memcpy_0(v18, v11[2], *((unsigned int *)v11 + 2));
            *(_WORD *)a2 = *((_WORD *)v11 + 4);
            *(_WORD *)(a2 + 2) = *((_WORD *)v11 + 4);
            LastError = 0;
          }
          else
          {
            LastError = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x846,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
              (const char *)0x8007000ELL,
              dwFlagsa);
          }
          goto LABEL_18;
        }
        v17 = 2114;
        v16 = 111;
      }
      else
      {
        v17 = 2109;
      }
      LastError = wil::details::in1diag3::Return_Win32(retaddr, (void *)v17, v14, (const char *)v16, dwFlagsa);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x839,
                    (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
                    v15);
      if ( !v11 )
        return LastError;
    }
LABEL_18:
    LocalFree(v11);
    return LastError;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x830,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
    (const char *)0x8007000ELL,
    dwFlags);
  return LastError;
}

```

## disassembly

```asm
0x18002ae70  mov     r11, rsp
0x18002ae73  push    rbx
0x18002ae74  push    rsi
0x18002ae75  push    rdi
0x18002ae76  sub     rsp, 40h
0x18002ae7a  mov     r8, [rcx+10h]
0x18002ae7e  lea     rax, [r11+8]
0x18002ae82  mov     [rsp+58h+arg_0], 0
0x18002ae8a  mov     rdi, rdx
0x18002ae8d  mov     [r11-28h], rax
0x18002ae91  mov     rsi, rcx
0x18002ae94  mov     qword ptr [r11-30h], 0
0x18002ae9c  mov     edx, 6; lpszStructType
0x18002aea1  mov     r9d, [r8]; cbEncoded
0x18002aea4  mov     ecx, 10001h; dwCertEncodingType
0x18002aea9  mov     r8, [r8+8]; pbEncoded
0x18002aead  mov     qword ptr [r11+18h], 0
0x18002aeb5  mov     [rsp+58h+dwFlags], 0; int
0x18002aebd  call    cs:__imp_CryptDecodeObject
0x18002aec3  test    eax, eax
0x18002aec5  jnz     short loc_18002AEE2
0x18002aec7  mov     rcx, [rsp+58h]; this
0x18002aecc  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002aed3  mov     edx, 82Dh; void *
0x18002aed8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002aedd  jmp     loc_18002B030
0x18002aee2  mov     edx, [rsp+58h+arg_0]
0x18002aee6  lea     rcx, [rsp+58h+hMem]
0x18002aeeb  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18002aef0  mov     rdx, rax
0x18002aef3  lea     rcx, [rsp+58h+arg_10]
0x18002aef8  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18002aefd  mov     rcx, [rsp+58h+hMem]; hMem
0x18002af02  mov     [rsp+58h+hMem], 0
0x18002af0b  test    rcx, rcx
0x18002af0e  jz      short loc_18002AF16
0x18002af10  call    cs:__imp_LocalFree
0x18002af16  mov     rbx, [rsp+58h+arg_10]
0x18002af1b  test    rbx, rbx
0x18002af1e  jnz     short loc_18002AF43
0x18002af20  mov     rcx, [rsp+58h]; this
0x18002af25  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002af2c  mov     edi, 8007000Eh
0x18002af31  mov     edx, 830h; void *
0x18002af36  mov     r9d, edi; char *
0x18002af39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002af3e  jmp     loc_18002B02E
0x18002af43  mov     r8, [rsi+10h]
0x18002af47  lea     rax, [rsp+58h+arg_0]
0x18002af4c  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x18002af51  mov     edx, 6; lpszStructType
0x18002af56  mov     [rsp+58h+pvStructInfo], rbx; pvStructInfo
0x18002af5b  mov     ecx, 10001h; dwCertEncodingType
0x18002af60  mov     [rsp+58h+dwFlags], 0; int
0x18002af68  mov     r9d, [r8]; cbEncoded
0x18002af6b  mov     r8, [r8+8]; pbEncoded
0x18002af6f  call    cs:__imp_CryptDecodeObject
0x18002af75  test    eax, eax
0x18002af77  jnz     short loc_18002AF9F
0x18002af79  mov     rcx, [rsp+58h]; this
0x18002af7e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002af85  mov     edx, 839h; void *
0x18002af8a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002af8f  mov     edi, eax
0x18002af91  test    rbx, rbx
0x18002af94  jz      loc_18002B02E
0x18002af9a  jmp     loc_18002B025
0x18002af9f  mov     r9d, 0Dh
0x18002afa5  cmp     [rbx], r9d
0x18002afa8  jz      short loc_18002AFB1
0x18002afaa  mov     edx, 83Dh
0x18002afaf  jmp     short loc_18002AFC5
0x18002afb1  cmp     dword ptr [rbx+8], 0FFFFh
0x18002afb8  jbe     short loc_18002AFD3
0x18002afba  mov     edx, 842h; void *
0x18002afbf  mov     r9d, 6Fh ; 'o'; char *
0x18002afc5  mov     rcx, [rsp+58h]; this
0x18002afca  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002afcf  mov     edi, eax
0x18002afd1  jmp     short loc_18002B025
0x18002afd3  mov     ecx, [rbx+8]
0x18002afd6  call    MincryptAlloc
0x18002afdb  mov     [rdi+8], rax
0x18002afdf  test    rax, rax
0x18002afe2  jnz     short loc_18002B004
0x18002afe4  mov     rcx, [rsp+58h]; this
0x18002afe9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x18002aff0  mov     edi, 8007000Eh
0x18002aff5  mov     edx, 846h; void *
0x18002affa  mov     r9d, edi; char *
0x18002affd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b002  jmp     short loc_18002B025
0x18002b004  mov     r8d, [rbx+8]; Size
0x18002b008  mov     rcx, rax; void *
0x18002b00b  mov     rdx, [rbx+10h]; Src
0x18002b00f  call    memcpy_0
0x18002b014  movzx   eax, word ptr [rbx+8]
0x18002b018  mov     [rdi], ax
0x18002b01b  movzx   eax, word ptr [rbx+8]
0x18002b01f  mov     [rdi+2], ax
0x18002b023  xor     edi, edi
0x18002b025  mov     rcx, rbx; hMem
0x18002b028  call    cs:__imp_LocalFree
0x18002b02e  mov     eax, edi
0x18002b030  add     rsp, 40h
0x18002b034  pop     rdi
0x18002b035  pop     rsi
0x18002b036  pop     rbx
0x18002b037  retn
```
