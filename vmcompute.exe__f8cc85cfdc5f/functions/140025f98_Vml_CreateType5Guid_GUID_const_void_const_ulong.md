# Vml::CreateType5Guid(_GUID const &,void const *,ulong)

- ea: `0x140025f98`
- end: `0x1400261c0`
- name: `?CreateType5Guid@Vml@@YA?AU_GUID@@AEBU2@PEBXK@Z`
- size: `552`
- prototype: `struct _GUID *(Vml *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr, const struct _GUID *, const void *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001cd60`
- `0x140025e68`
- `0x1400d641c`

## callees

- `0x140025f98`
- `0x1401332f0`
- `0x140142dac`
- `0x140170774`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x140026105`
- `bcrypt!BCryptFinishHash` at `0x140026105`
- `bcrypt!BCryptHashData` at `0x140026097`
- `bcrypt!BCryptHashData` at `0x1400260cd`
- `bcrypt!BCryptHashData` at `0x140026097`
- `bcrypt!BCryptHashData` at `0x1400260cd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140025fe0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140025fe0`
- `bcrypt!BCryptCreateHash` at `0x140026038`
- `bcrypt!BCryptCreateHash` at `0x140026038`
- `bcrypt!BCryptDestroyHash` at `0x140026187`
- `bcrypt!BCryptDestroyHash` at `0x140026187`

## string_xrefs

- `0x140025ff7`: `onecore\vm\common\vml\VmGuid.h`
- `0x14002604f`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400260ae`: `onecore\vm\common\vml\VmGuid.h`
- `0x1400260e4`: `onecore\vm\common\vml\VmGuid.h`
- `0x14002611c`: `onecore\vm\common\vml\VmGuid.h`

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
  char v14; // r8
  unsigned __int64 v15; // rdx
  int pbSecret; // [rsp+20h] [rbp-60h]
  int pbSecreta; // [rsp+20h] [rbp-60h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-40h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-38h] BYREF
  UCHAR pbInput[16]; // [rsp+50h] [rbp-30h] BYREF
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-20h] BYREF
  __int16 v23; // [rsp+64h] [rbp-1Ch]
  unsigned __int16 v24; // [rsp+66h] [rbp-1Ah]
  char v25; // [rsp+68h] [rbp-18h]
  int v26; // [rsp+69h] [rbp-17h]
  __int16 v27; // [rsp+6Dh] [rbp-13h]
  char v28; // [rsp+6Fh] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v4 = (unsigned int)a4;
  phAlgorithm = 0;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x4CC,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v8,
      pbSecret);
  phHash = 0;
  v9 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
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
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x4E4,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v10,
      pbSecreta);
  v11 = BCryptHashData(phHash, a3, v4, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v11,
      pbSecreta);
  v12 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x4F4,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v12,
      pbSecreta);
  v13 = v23;
  v15 = v24;
  v14 = v25;
  *(_DWORD *)this = _byteswap_ulong(*(unsigned int *)pbOutput);
  *((_WORD *)this + 2) = __ROR2__(v13, 8);
  LOWORD(v15) = __ROR2__(v15, 8) & 0xFFF | 0x5000;
  *((_WORD *)this + 3) = v15;
  *((_BYTE *)this + 8) = v14 & 0x3F | 0x80;
  *(_DWORD *)((char *)this + 9) = v26;
  *(_WORD *)((char *)this + 13) = v27;
  *((_BYTE *)this + 15) = v28;
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    wil::details::BCryptCloseAlgorithmProviderNoFlags((wil::details *)phAlgorithm, (void *)v15);
  return (struct _GUID *)this;
}

```

## disassembly

```asm
0x140025f98  push    rbp
0x140025f9a  push    rbx
0x140025f9b  push    rsi
0x140025f9c  push    rdi
0x140025f9d  push    r14
0x140025f9f  mov     rbp, rsp
0x140025fa2  sub     rsp, 80h
0x140025fa9  mov     rax, cs:__security_cookie
0x140025fb0  xor     rax, rsp
0x140025fb3  mov     [rbp+var_8], rax
0x140025fb7  mov     r14d, r9d
0x140025fba  mov     rsi, r8
0x140025fbd  mov     rdi, rdx
0x140025fc0  mov     rbx, rcx
0x140025fc3  mov     [rbp+phAlgorithm], 0
0x140025fcb  xor     r9d, r9d; dwFlags
0x140025fce  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140025fd5  lea     rdx, pszAlgId; "SHA1"
0x140025fdc  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140025fe0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140025fe7  nop     dword ptr [rax+rax+00h]
0x140025fec  mov     rcx, [rbp+28h]; this
0x140025ff0  test    eax, eax
0x140025ff2  jns     short loc_140026009
0x140025ff4  mov     r9d, eax; char *
0x140025ff7  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmGuid.h"
0x140025ffe  mov     edx, 4CCh; void *
0x140026003  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x140026009  mov     [rbp+phHash], 0
0x140026011  mov     [rsp+80h+dwFlags], 0; dwFlags
0x140026019  mov     [rsp+80h+cbSecret], 0; cbSecret
0x140026021  mov     [rsp+80h+pbSecret], 0; int
0x14002602a  xor     r9d, r9d; cbHashObject
0x14002602d  xor     r8d, r8d; pbHashObject
0x140026030  lea     rdx, [rbp+phHash]; phHash
0x140026034  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140026038  call    cs:__imp_BCryptCreateHash
0x14002603f  nop     dword ptr [rax+rax+00h]
0x140026044  mov     rcx, [rbp+28h]; this
0x140026048  test    eax, eax
0x14002604a  jns     short loc_140026061
0x14002604c  mov     r9d, eax; char *
0x14002604f  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmGuid.h"
0x140026056  mov     edx, 4D6h; void *
0x14002605b  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x140026061  movups  xmm0, xmmword ptr [rdi]
0x140026064  movdqu  xmmword ptr [rbp+pbInput], xmm0
0x140026069  mov     eax, [rdi]
0x14002606b  bswap   eax
0x14002606d  mov     dword ptr [rbp+pbInput], eax
0x140026070  movzx   eax, word ptr [rdi+4]
0x140026074  ror     ax, 8
0x140026078  mov     word ptr [rbp+pbInput+4], ax
0x14002607c  movzx   eax, word ptr [rdi+6]
0x140026080  ror     ax, 8
0x140026084  mov     word ptr [rbp+pbInput+6], ax
0x140026088  xor     r9d, r9d; dwFlags
0x14002608b  lea     r8d, [r9+10h]; cbInput
0x14002608f  lea     rdx, [rbp+pbInput]; pbInput
0x140026093  mov     rcx, [rbp+phHash]; hHash
0x140026097  call    cs:__imp_BCryptHashData
0x14002609e  nop     dword ptr [rax+rax+00h]
0x1400260a3  mov     rcx, [rbp+28h]; this
0x1400260a7  test    eax, eax
0x1400260a9  jns     short loc_1400260C0
0x1400260ab  mov     r9d, eax; char *
0x1400260ae  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmGuid.h"
0x1400260b5  mov     edx, 4E4h; void *
0x1400260ba  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400260c0  xor     r9d, r9d; dwFlags
0x1400260c3  mov     r8d, r14d; cbInput
0x1400260c6  mov     rdx, rsi; pbInput
0x1400260c9  mov     rcx, [rbp+phHash]; hHash
0x1400260cd  call    cs:__imp_BCryptHashData
0x1400260d4  nop     dword ptr [rax+rax+00h]
0x1400260d9  mov     rcx, [rbp+28h]; this
0x1400260dd  test    eax, eax
0x1400260df  jns     short loc_1400260F6
0x1400260e1  mov     r9d, eax; char *
0x1400260e4  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmGuid.h"
0x1400260eb  mov     edx, 4EBh; void *
0x1400260f0  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400260f6  xor     r9d, r9d; dwFlags
0x1400260f9  lea     r8d, [r9+14h]; cbOutput
0x1400260fd  lea     rdx, [rbp+pbOutput]; pbOutput
0x140026101  mov     rcx, [rbp+phHash]; hHash
0x140026105  call    cs:__imp_BCryptFinishHash
0x14002610c  nop     dword ptr [rax+rax+00h]
0x140026111  mov     rcx, [rbp+28h]; this
0x140026115  test    eax, eax
0x140026117  jns     short loc_14002612E
0x140026119  mov     r9d, eax; char *
0x14002611c  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmGuid.h"
0x140026123  mov     edx, 4F4h; void *
0x140026128  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14002612e  mov     eax, dword ptr [rbp+pbOutput]
0x140026131  movzx   ecx, [rbp+var_1C]
0x140026135  movzx   edx, [rbp+var_1A]
0x140026139  mov     r8b, [rbp+var_18]
0x14002613d  bswap   eax
0x14002613f  mov     [rbx], eax
0x140026141  ror     cx, 8
0x140026145  mov     [rbx+4], cx
0x140026149  ror     dx, 8
0x14002614d  mov     eax, 0FFFh
0x140026152  and     dx, ax
0x140026155  or      dx, 5000h
0x14002615a  mov     [rbx+6], dx
0x14002615e  and     r8b, 3Fh
0x140026162  or      r8b, 80h
0x140026166  mov     [rbx+8], r8b
0x14002616a  mov     eax, [rbp+var_17]
0x14002616d  mov     [rbx+9], eax
0x140026170  movzx   eax, [rbp+var_13]
0x140026174  mov     [rbx+0Dh], ax
0x140026178  mov     al, [rbp+var_11]
0x14002617b  mov     [rbx+0Fh], al
0x14002617e  mov     rcx, [rbp+phHash]; hHash
0x140026182  test    rcx, rcx
0x140026185  jz      short loc_140026194
0x140026187  call    cs:__imp_BCryptDestroyHash
0x14002618e  nop     dword ptr [rax+rax+00h]
0x140026193  nop
0x140026194  mov     rcx, [rbp+phAlgorithm]; this
0x140026198  test    rcx, rcx
0x14002619b  jz      short loc_1400261A2
0x14002619d  call    ?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAXPEAX@Z; wil::details::BCryptCloseAlgorithmProviderNoFlags(void *)
0x1400261a2  mov     rax, rbx
0x1400261a5  mov     rcx, [rbp+var_8]
0x1400261a9  xor     rcx, rsp; StackCookie
0x1400261ac  call    __security_check_cookie
0x1400261b1  add     rsp, 80h
0x1400261b8  pop     r14
0x1400261ba  pop     rdi
0x1400261bb  pop     rsi
0x1400261bc  pop     rbx
0x1400261bd  pop     rbp
0x1400261be  retn
```
