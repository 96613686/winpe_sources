# Vml::CreateType5Guid(_GUID const &,void const *,ulong)

- ea: `0x18002fbe0`
- end: `0x18002fe25`
- name: `?CreateType5Guid@Vml@@YA?AU_GUID@@AEBU2@PEBXK@Z`
- size: `581`
- prototype: `struct _GUID *(Vml *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr, const struct _GUID *, const void *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800365b0`
- `0x180047234`

## callees

- `0x180002f50`
- `0x18002fbe0`
- `0x180034674`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x18002fd09`
- `bcrypt!BCryptFinishHash` at `0x18002fd09`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002fc28`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002fc28`
- `bcrypt!BCryptCreateHash` at `0x18002fc6f`
- `bcrypt!BCryptCreateHash` at `0x18002fc6f`
- `bcrypt!BCryptHashData` at `0x18002fcbd`
- `bcrypt!BCryptHashData` at `0x18002fce2`
- `bcrypt!BCryptHashData` at `0x18002fcbd`
- `bcrypt!BCryptHashData` at `0x18002fce2`
- `bcrypt!BCryptDestroyHash` at `0x18002fd7a`
- `bcrypt!BCryptDestroyHash` at `0x18002fd7a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002fd92`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002fd92`

## string_xrefs

- `0x18002fdbf`: `onecore\vm\common\vml\VmGuid.h`
- `0x18002fdd4`: `onecore\vm\common\vml\VmGuid.h`
- `0x18002fde9`: `onecore\vm\common\vml\VmGuid.h`
- `0x18002fdfe`: `onecore\vm\common\vml\VmGuid.h`
- `0x18002fe13`: `onecore\vm\common\vml\VmGuid.h`

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
0x18002fbe0  push    rbp
0x18002fbe2  push    rbx
0x18002fbe3  push    rsi
0x18002fbe4  push    rdi
0x18002fbe5  push    r14
0x18002fbe7  mov     rbp, rsp
0x18002fbea  sub     rsp, 80h
0x18002fbf1  mov     rax, cs:__security_cookie
0x18002fbf8  xor     rax, rsp
0x18002fbfb  mov     [rbp+var_8], rax
0x18002fbff  mov     r14d, r9d
0x18002fc02  mov     rsi, r8
0x18002fc05  mov     rdi, rdx
0x18002fc08  mov     rbx, rcx
0x18002fc0b  mov     [rbp+phAlgorithm], 0
0x18002fc13  xor     r9d, r9d; dwFlags
0x18002fc16  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18002fc1d  lea     rdx, pszAlgId; "SHA1"
0x18002fc24  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18002fc28  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002fc2f  nop     dword ptr [rax+rax+00h]
0x18002fc34  mov     rcx, [rbp+28h]; this
0x18002fc38  test    eax, eax
0x18002fc3a  js      loc_18002FDD1
0x18002fc40  mov     [rbp+phHash], 0
0x18002fc48  mov     [rsp+80h+dwFlags], 0; dwFlags
0x18002fc50  mov     [rsp+80h+cbSecret], 0; cbSecret
0x18002fc58  mov     [rsp+80h+pbSecret], 0; int
0x18002fc61  xor     r9d, r9d; cbHashObject
0x18002fc64  xor     r8d, r8d; pbHashObject
0x18002fc67  lea     rdx, [rbp+phHash]; phHash
0x18002fc6b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18002fc6f  call    cs:__imp_BCryptCreateHash
0x18002fc76  nop     dword ptr [rax+rax+00h]
0x18002fc7b  mov     rcx, [rbp+28h]; this
0x18002fc7f  test    eax, eax
0x18002fc81  js      loc_18002FDE6
0x18002fc87  movups  xmm0, xmmword ptr [rdi]
0x18002fc8a  movdqu  xmmword ptr [rbp+pbInput], xmm0
0x18002fc8f  mov     eax, [rdi]
0x18002fc91  bswap   eax
0x18002fc93  mov     dword ptr [rbp+pbInput], eax
0x18002fc96  movzx   eax, word ptr [rdi+4]
0x18002fc9a  ror     ax, 8
0x18002fc9e  mov     word ptr [rbp+pbInput+4], ax
0x18002fca2  movzx   eax, word ptr [rdi+6]
0x18002fca6  ror     ax, 8
0x18002fcaa  mov     word ptr [rbp+pbInput+6], ax
0x18002fcae  xor     r9d, r9d; dwFlags
0x18002fcb1  lea     r8d, [r9+10h]; cbInput
0x18002fcb5  lea     rdx, [rbp+pbInput]; pbInput
0x18002fcb9  mov     rcx, [rbp+phHash]; hHash
0x18002fcbd  call    cs:__imp_BCryptHashData
0x18002fcc4  nop     dword ptr [rax+rax+00h]
0x18002fcc9  mov     rcx, [rbp+28h]; this
0x18002fccd  test    eax, eax
0x18002fccf  js      loc_18002FDFB
0x18002fcd5  xor     r9d, r9d; dwFlags
0x18002fcd8  mov     r8d, r14d; cbInput
0x18002fcdb  mov     rdx, rsi; pbInput
0x18002fcde  mov     rcx, [rbp+phHash]; hHash
0x18002fce2  call    cs:__imp_BCryptHashData
0x18002fce9  nop     dword ptr [rax+rax+00h]
0x18002fcee  mov     rcx, [rbp+28h]; this
0x18002fcf2  test    eax, eax
0x18002fcf4  js      loc_18002FE10
0x18002fcfa  xor     r9d, r9d; dwFlags
0x18002fcfd  lea     r8d, [r9+14h]; cbOutput
0x18002fd01  lea     rdx, [rbp+pbOutput]; pbOutput
0x18002fd05  mov     rcx, [rbp+phHash]; hHash
0x18002fd09  call    cs:__imp_BCryptFinishHash
0x18002fd10  nop     dword ptr [rax+rax+00h]
0x18002fd15  mov     rcx, [rbp+28h]; this
0x18002fd19  test    eax, eax
0x18002fd1b  js      loc_18002FDBC
0x18002fd21  mov     eax, dword ptr [rbp+pbOutput]
0x18002fd24  movzx   ecx, [rbp+var_1C]
0x18002fd28  movzx   edx, [rbp+var_1A]
0x18002fd2c  mov     r8b, [rbp+var_18]
0x18002fd30  bswap   eax
0x18002fd32  mov     [rbx], eax
0x18002fd34  ror     cx, 8
0x18002fd38  mov     [rbx+4], cx
0x18002fd3c  ror     dx, 8
0x18002fd40  mov     eax, 0FFFh
0x18002fd45  and     dx, ax
0x18002fd48  or      dx, 5000h
0x18002fd4d  mov     [rbx+6], dx
0x18002fd51  and     r8b, 3Fh
0x18002fd55  or      r8b, 80h
0x18002fd59  mov     [rbx+8], r8b
0x18002fd5d  mov     eax, [rbp+var_17]
0x18002fd60  mov     [rbx+9], eax
0x18002fd63  movzx   eax, [rbp+var_13]
0x18002fd67  mov     [rbx+0Dh], ax
0x18002fd6b  mov     al, [rbp+var_11]
0x18002fd6e  mov     [rbx+0Fh], al
0x18002fd71  mov     rcx, [rbp+phHash]; hHash
0x18002fd75  test    rcx, rcx
0x18002fd78  jz      short loc_18002FD87
0x18002fd7a  call    cs:__imp_BCryptDestroyHash
0x18002fd81  nop     dword ptr [rax+rax+00h]
0x18002fd86  nop
0x18002fd87  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18002fd8b  test    rcx, rcx
0x18002fd8e  jz      short loc_18002FD9E
0x18002fd90  xor     edx, edx; dwFlags
0x18002fd92  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002fd99  nop     dword ptr [rax+rax+00h]
0x18002fd9e  mov     rax, rbx
0x18002fda1  mov     rcx, [rbp+var_8]
0x18002fda5  xor     rcx, rsp; StackCookie
0x18002fda8  call    __security_check_cookie
0x18002fdad  add     rsp, 80h
0x18002fdb4  pop     r14
0x18002fdb6  pop     rdi
0x18002fdb7  pop     rsi
0x18002fdb8  pop     rbx
0x18002fdb9  pop     rbp
0x18002fdba  retn
0x18002fdbc  mov     r9d, eax; char *
0x18002fdbf  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x18002fdc6  mov     edx, 4F4h; void *
0x18002fdcb  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002fdd1  mov     r9d, eax; char *
0x18002fdd4  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x18002fddb  mov     edx, 4CCh; void *
0x18002fde0  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002fde6  mov     r9d, eax; char *
0x18002fde9  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x18002fdf0  mov     edx, 4D6h; void *
0x18002fdf5  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002fdfb  mov     r9d, eax; char *
0x18002fdfe  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x18002fe05  mov     edx, 4E4h; void *
0x18002fe0a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002fe10  mov     r9d, eax; char *
0x18002fe13  lea     r8, aOnecoreVmCommo_6; "onecore\\vm\\common\\vml\\VmGuid.h"
0x18002fe1a  mov     edx, 4EBh; void *
0x18002fe1f  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
