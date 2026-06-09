# Vml::CreateType5Guid(_GUID const &,void const *,ulong)

- ea: `0x140088bec`
- end: `0x140088e06`
- name: `?CreateType5Guid@Vml@@YA?AU_GUID@@AEBU2@PEBXK@Z`
- size: `538`
- prototype: `struct _GUID *(Vml *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr, const struct _GUID *, const void *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14008853c`
- `0x1400da178`

## callees

- `0x140005360`
- `0x140044adc`
- `0x140088bec`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x140088d68`
- `bcrypt!BCryptDestroyHash` at `0x140088d68`
- `bcrypt!BCryptCreateHash` at `0x140088c75`
- `bcrypt!BCryptCreateHash` at `0x140088c75`
- `bcrypt!BCryptFinishHash` at `0x140088cfd`
- `bcrypt!BCryptFinishHash` at `0x140088cfd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140088d7a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140088d7a`
- `bcrypt!BCryptHashData` at `0x140088cbd`
- `bcrypt!BCryptHashData` at `0x140088cdc`
- `bcrypt!BCryptHashData` at `0x140088cbd`
- `bcrypt!BCryptHashData` at `0x140088cdc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140088c34`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140088c34`

## string_xrefs

- `0x140088da0`: `onecore\vm\common\vml\VmGuid.h`
- `0x140088db5`: `onecore\vm\common\vml\VmGuid.h`
- `0x140088dca`: `onecore\vm\common\vml\VmGuid.h`
- `0x140088ddf`: `onecore\vm\common\vml\VmGuid.h`
- `0x140088df4`: `onecore\vm\common\vml\VmGuid.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _GUID *__fastcall Vml::CreateType5Guid(Vml *this, struct _GUID *__return_ptr retstr, UCHAR *a3, const void *a4)
{
  ULONG v4; // r14d
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  __int16 v13; // cx
  __int16 v14; // dx
  char v15; // r8
  int pbSecret; // [rsp+20h] [rbp-60h]
  int pbSecreta; // [rsp+20h] [rbp-60h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-40h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-38h] BYREF
  UCHAR pbInput[16]; // [rsp+50h] [rbp-30h] BYREF
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-20h] BYREF
  __int16 v23; // [rsp+64h] [rbp-1Ch]
  __int16 v24; // [rsp+66h] [rbp-1Ah]
  char v25; // [rsp+68h] [rbp-18h]
  int v26; // [rsp+69h] [rbp-17h]
  __int16 v27; // [rsp+6Dh] [rbp-13h]
  char v28; // [rsp+6Fh] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v4 = (unsigned int)a4;
  phAlgorithm = 0;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4CC,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v8,
      pbSecret);
  phHash = 0;
  v9 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4D6,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v9,
      pbSecreta);
  *(struct _GUID *)pbInput = *retstr;
  *(_DWORD *)pbInput = _byteswap_ulong(retstr->Data1);
  *(_WORD *)&pbInput[4] = __ROR2__(retstr->Data2, 8);
  *(_WORD *)&pbInput[6] = __ROR2__(retstr->Data3, 8);
  v10 = BCryptHashData(phHash, pbInput, 0x10u, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4E4,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v10,
      pbSecreta);
  v11 = BCryptHashData(phHash, a3, v4, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v11,
      pbSecreta);
  v12 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4F4,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v12,
      pbSecreta);
  v13 = v23;
  v14 = v24;
  v15 = v25;
  *(_DWORD *)this = _byteswap_ulong(*(unsigned int *)pbOutput);
  *((_WORD *)this + 2) = __ROR2__(v13, 8);
  *((_WORD *)this + 3) = __ROR2__(v14, 8) & 0xFFF | 0x5000;
  *((_BYTE *)this + 8) = v15 & 0x3F | 0x80;
  *(_DWORD *)((char *)this + 9) = v26;
  *(_WORD *)((char *)this + 13) = v27;
  *((_BYTE *)this + 15) = v28;
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (struct _GUID *)this;
}

```

## disassembly

```asm
0x140088bec  push    rbp
0x140088bee  push    rbx
0x140088bef  push    rsi
0x140088bf0  push    rdi
0x140088bf1  push    r14
0x140088bf3  mov     rbp, rsp
0x140088bf6  sub     rsp, 80h
0x140088bfd  mov     rax, cs:__security_cookie
0x140088c04  xor     rax, rsp
0x140088c07  mov     [rbp+var_8], rax
0x140088c0b  mov     r14d, r9d
0x140088c0e  mov     rsi, r8
0x140088c11  mov     rdi, rdx
0x140088c14  mov     rbx, rcx
0x140088c17  mov     [rbp+phAlgorithm], 0
0x140088c1f  xor     r9d, r9d; dwFlags
0x140088c22  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140088c29  lea     rdx, pszAlgId; "SHA1"
0x140088c30  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140088c34  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140088c3a  mov     rcx, [rbp+28h]; this
0x140088c3e  test    eax, eax
0x140088c40  js      loc_140088DB2
0x140088c46  mov     [rbp+phHash], 0
0x140088c4e  mov     [rsp+80h+dwFlags], 0; dwFlags
0x140088c56  mov     [rsp+80h+cbSecret], 0; cbSecret
0x140088c5e  mov     [rsp+80h+pbSecret], 0; int
0x140088c67  xor     r9d, r9d; cbHashObject
0x140088c6a  xor     r8d, r8d; pbHashObject
0x140088c6d  lea     rdx, [rbp+phHash]; phHash
0x140088c71  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140088c75  call    cs:__imp_BCryptCreateHash
0x140088c7b  mov     rcx, [rbp+28h]; this
0x140088c7f  test    eax, eax
0x140088c81  js      loc_140088DC7
0x140088c87  movups  xmm0, xmmword ptr [rdi]
0x140088c8a  movdqu  xmmword ptr [rbp+pbInput], xmm0
0x140088c8f  mov     eax, [rdi]
0x140088c91  bswap   eax
0x140088c93  mov     dword ptr [rbp+pbInput], eax
0x140088c96  movzx   eax, word ptr [rdi+4]
0x140088c9a  ror     ax, 8
0x140088c9e  mov     word ptr [rbp+pbInput+4], ax
0x140088ca2  movzx   eax, word ptr [rdi+6]
0x140088ca6  ror     ax, 8
0x140088caa  mov     word ptr [rbp+pbInput+6], ax
0x140088cae  xor     r9d, r9d; dwFlags
0x140088cb1  lea     r8d, [r9+10h]; cbInput
0x140088cb5  lea     rdx, [rbp+pbInput]; pbInput
0x140088cb9  mov     rcx, [rbp+phHash]; hHash
0x140088cbd  call    cs:__imp_BCryptHashData
0x140088cc3  mov     rcx, [rbp+28h]; this
0x140088cc7  test    eax, eax
0x140088cc9  js      loc_140088DDC
0x140088ccf  xor     r9d, r9d; dwFlags
0x140088cd2  mov     r8d, r14d; cbInput
0x140088cd5  mov     rdx, rsi; pbInput
0x140088cd8  mov     rcx, [rbp+phHash]; hHash
0x140088cdc  call    cs:__imp_BCryptHashData
0x140088ce2  mov     rcx, [rbp+28h]; this
0x140088ce6  test    eax, eax
0x140088ce8  js      loc_140088DF1
0x140088cee  xor     r9d, r9d; dwFlags
0x140088cf1  lea     r8d, [r9+14h]; cbOutput
0x140088cf5  lea     rdx, [rbp+pbOutput]; pbOutput
0x140088cf9  mov     rcx, [rbp+phHash]; hHash
0x140088cfd  call    cs:__imp_BCryptFinishHash
0x140088d03  mov     rcx, [rbp+28h]; this
0x140088d07  test    eax, eax
0x140088d09  js      loc_140088D9D
0x140088d0f  mov     eax, dword ptr [rbp+pbOutput]
0x140088d12  movzx   ecx, [rbp+var_1C]
0x140088d16  movzx   edx, [rbp+var_1A]
0x140088d1a  mov     r8b, [rbp+var_18]
0x140088d1e  bswap   eax
0x140088d20  mov     [rbx], eax
0x140088d22  ror     cx, 8
0x140088d26  mov     [rbx+4], cx
0x140088d2a  ror     dx, 8
0x140088d2e  mov     eax, 0FFFh
0x140088d33  and     dx, ax
0x140088d36  or      dx, 5000h
0x140088d3b  mov     [rbx+6], dx
0x140088d3f  and     r8b, 3Fh
0x140088d43  or      r8b, 80h
0x140088d47  mov     [rbx+8], r8b
0x140088d4b  mov     eax, [rbp+var_17]
0x140088d4e  mov     [rbx+9], eax
0x140088d51  movzx   eax, [rbp+var_13]
0x140088d55  mov     [rbx+0Dh], ax
0x140088d59  mov     al, [rbp+var_11]
0x140088d5c  mov     [rbx+0Fh], al
0x140088d5f  mov     rcx, [rbp+phHash]; hHash
0x140088d63  test    rcx, rcx
0x140088d66  jz      short loc_140088D6F
0x140088d68  call    cs:__imp_BCryptDestroyHash
0x140088d6e  nop
0x140088d6f  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140088d73  test    rcx, rcx
0x140088d76  jz      short loc_140088D80
0x140088d78  xor     edx, edx; dwFlags
0x140088d7a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140088d80  mov     rax, rbx
0x140088d83  mov     rcx, [rbp+var_8]
0x140088d87  xor     rcx, rsp; StackCookie
0x140088d8a  call    __security_check_cookie
0x140088d8f  add     rsp, 80h
0x140088d96  pop     r14
0x140088d98  pop     rdi
0x140088d99  pop     rsi
0x140088d9a  pop     rbx
0x140088d9b  pop     rbp
0x140088d9c  retn
0x140088d9d  mov     r9d, eax; char *
0x140088da0  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x140088da7  mov     edx, 4F4h; void *
0x140088dac  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140088db2  mov     r9d, eax; char *
0x140088db5  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x140088dbc  mov     edx, 4CCh; void *
0x140088dc1  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140088dc7  mov     r9d, eax; char *
0x140088dca  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x140088dd1  mov     edx, 4D6h; void *
0x140088dd6  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140088ddc  mov     r9d, eax; char *
0x140088ddf  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x140088de6  mov     edx, 4E4h; void *
0x140088deb  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140088df1  mov     r9d, eax; char *
0x140088df4  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x140088dfb  mov     edx, 4EBh; void *
0x140088e00  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
