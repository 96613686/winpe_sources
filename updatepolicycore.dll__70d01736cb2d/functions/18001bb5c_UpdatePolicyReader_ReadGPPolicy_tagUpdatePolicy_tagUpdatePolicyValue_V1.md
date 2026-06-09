# UpdatePolicyReader::ReadGPPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)

- ea: `0x18001bb5c`
- end: `0x18001bd29`
- name: `?ReadGPPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a320`

## callees

- `0x18000aac0`
- `0x1800163f8`
- `0x18001bb5c`
- `0x18001bd30`
- `0x18001bf44`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001bbb4`
- `OLEAUT32!__imp_VariantInit` at `0x18001bbd1`
- `OLEAUT32!__imp_VariantInit` at `0x18001bbb4`
- `OLEAUT32!__imp_VariantInit` at `0x18001bbd1`
- `OLEAUT32!__imp_VariantClear` at `0x18001bc37`
- `OLEAUT32!__imp_VariantClear` at `0x18001bcf4`
- `OLEAUT32!__imp_VariantClear` at `0x18001bd02`
- `OLEAUT32!__imp_VariantClear` at `0x18001bc37`
- `OLEAUT32!__imp_VariantClear` at `0x18001bcf4`
- `OLEAUT32!__imp_VariantClear` at `0x18001bd02`
- `OLEAUT32!__imp_VariantCopy` at `0x18001bc56`
- `OLEAUT32!__imp_VariantCopy` at `0x18001bc56`

## string_xrefs

- `0x18001bbf9`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`
- `0x18001bbf2`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU`
- `0x18001bc86`: `C:\__w\1\s\src\Client\policy\src\Update\PolicyReader.cpp`
- `0x18001bcd9`: `C:\__w\1\s\src\Client\policy\src\Update\PolicyReader.cpp`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadGPPolicy(unsigned int a1, __int64 a2)
{
  int GPPolicyCore; // edi
  __int64 v3; // rdx
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r9
  HRESULT v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // eax
  int v12; // [rsp+20h] [rbp-79h]
  _QWORD v13[5]; // [rsp+40h] [rbp-59h] BYREF
  char v14; // [rsp+68h] [rbp-31h]
  __int64 v15; // [rsp+70h] [rbp-29h] BYREF
  unsigned int v16; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v17[40]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v18[40]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v16 = a1;
  v15 = a2;
  memset(v18, 0, sizeof(v18));
  memset(v17, 0, sizeof(v17));
  VariantInit((VARIANTARG *)&v17[16]);
  *(_QWORD *)&v17[4] = 0;
  *(_DWORD *)v17 = 0;
  memset(v18, 0, sizeof(v18));
  VariantInit((VARIANTARG *)&v18[16]);
  *(_QWORD *)&v18[4] = 0;
  *(_DWORD *)v18 = 0;
  v13[3] = v17;
  v13[4] = v18;
  v14 = 1;
  GPPolicyCore = UpdatePolicyReader::ReadGPPolicyCore(
                   v16,
                   v17,
                   L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate",
                   L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate\\AU");
  if ( GPPolicyCore < 0 )
  {
    v3 = 735;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Update\\PolicyReader.cpp",
      (const char *)(unsigned int)GPPolicyCore,
      v12);
    goto LABEL_12;
  }
  v4 = v15;
  if ( !v15 )
  {
    GPPolicyCore = -2147024809;
    v5 = 56;
    v6 = 2147942487LL;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\inc\\PolicyHelpers.h",
      (const char *)v6,
      v12);
    v3 = 736;
    goto LABEL_8;
  }
  *(_QWORD *)(v15 + 4) = 0;
  VariantClear((VARIANTARG *)(v4 + 16));
  *(_QWORD *)v4 = *(_QWORD *)v17;
  *(_DWORD *)(v4 + 8) = *(_DWORD *)&v17[8];
  v7 = VariantCopy((VARIANTARG *)(v4 + 16), (const VARIANTARG *)&v17[16]);
  GPPolicyCore = v7;
  v6 = (unsigned int)v7;
  if ( v7 < 0 )
  {
    v5 = 63;
    goto LABEL_7;
  }
  if ( !*(_DWORD *)&v17[4] )
  {
    v13[0] = &v16;
    v13[1] = v18;
    v13[2] = &v15;
    v10 = lambda_2a40df9e8133e2652f1479e64240642f_::operator()(v13, v8, v9, (unsigned int)v7);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Update\\PolicyReader.cpp",
      (const char *)v10,
      2,
      0x80070002,
      -2147024893);
  }
  GPPolicyCore = 0;
LABEL_12:
  *(_QWORD *)&v17[4] = 0;
  VariantClear((VARIANTARG *)&v17[16]);
  *(_QWORD *)&v18[4] = 0;
  VariantClear((VARIANTARG *)&v18[16]);
  return (unsigned int)GPPolicyCore;
}

```

## disassembly

```asm
0x18001bb5c  mov     [rsp-8+arg_10], rbx
0x18001bb61  push    rbp
0x18001bb62  push    rsi
0x18001bb63  push    rdi
0x18001bb64  lea     rbp, [rsp-47h]
0x18001bb69  sub     rsp, 0E0h
0x18001bb70  mov     rax, cs:__security_cookie
0x18001bb77  xor     rax, rsp
0x18001bb7a  mov     [rbp+57h+var_20], rax
0x18001bb7e  mov     [rbp+57h+var_78], ecx
0x18001bb81  mov     [rbp+57h+var_80], rdx
0x18001bb85  xorps   xmm0, xmm0
0x18001bb88  xor     eax, eax
0x18001bb8a  movups  [rbp+57h+var_48], xmm0
0x18001bb8e  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x18001bb92  mov     qword ptr [rbp+57h+var_38+10h], rax
0x18001bb96  xorps   xmm1, xmm1
0x18001bb99  movups  [rbp+57h+var_70], xmm1
0x18001bb9d  movups  xmmword ptr [rbp+57h+pvarg], xmm1
0x18001bba1  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001bba5  lea     rdi, [rbp+57h+var_70]
0x18001bba9  lea     ebx, [rax+28h]
0x18001bbac  mov     ecx, ebx
0x18001bbae  rep stosb
0x18001bbb0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001bbb4  call    cs:__imp_VariantInit
0x18001bbba  xor     esi, esi
0x18001bbbc  mov     qword ptr [rbp+57h+var_70+4], rsi
0x18001bbc0  mov     dword ptr [rbp+57h+var_70], esi
0x18001bbc3  lea     rdi, [rbp+57h+var_48]
0x18001bbc7  xor     eax, eax
0x18001bbc9  mov     ecx, ebx
0x18001bbcb  rep stosb
0x18001bbcd  lea     rcx, [rbp+57h+var_38]; pvarg
0x18001bbd1  call    cs:__imp_VariantInit
0x18001bbd7  mov     qword ptr [rbp+57h+var_48+4], rsi
0x18001bbdb  mov     dword ptr [rbp+57h+var_48], esi
0x18001bbde  lea     rax, [rbp+57h+var_70]
0x18001bbe2  mov     [rbp+57h+var_98], rax
0x18001bbe6  lea     rax, [rbp+57h+var_48]
0x18001bbea  mov     [rbp+57h+var_90], rax
0x18001bbee  mov     [rbp+57h+var_88], 1
0x18001bbf2  lea     r9, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18001bbf9  lea     r8, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18001bc00  lea     rdx, [rbp+57h+var_70]
0x18001bc04  mov     ecx, [rbp+57h+var_78]
0x18001bc07  call    ?ReadGPPolicyCore@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@PEB_W2@Z; UpdatePolicyReader::ReadGPPolicyCore(tagUpdatePolicy,tagUpdatePolicyValue_V1 *,wchar_t const *,wchar_t const *)
0x18001bc0c  mov     edi, eax
0x18001bc0e  test    eax, eax
0x18001bc10  jns     short loc_18001BC19
0x18001bc12  mov     edx, 2DFh
0x18001bc17  jmp     short loc_18001BC7F
0x18001bc19  mov     rbx, [rbp+57h+var_80]
0x18001bc1d  test    rbx, rbx
0x18001bc20  jnz     short loc_18001BC2F
0x18001bc22  mov     edi, 80070057h
0x18001bc27  lea     edx, [rbx+38h]
0x18001bc2a  mov     r9d, edi
0x18001bc2d  jmp     short loc_18001BC6A
0x18001bc2f  mov     [rbx+4], rsi
0x18001bc33  lea     rcx, [rbx+10h]; pvarg
0x18001bc37  call    cs:__imp_VariantClear
0x18001bc3d  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18001bc40  mov     [rbx+4], eax
0x18001bc43  mov     eax, dword ptr [rbp+57h+var_70]
0x18001bc46  mov     [rbx], eax
0x18001bc48  mov     eax, dword ptr [rbp+57h+var_70+8]
0x18001bc4b  mov     [rbx+8], eax
0x18001bc4e  lea     rdx, [rbp+57h+pvarg]; pvargSrc
0x18001bc52  lea     rcx, [rbx+10h]; pvargDest
0x18001bc56  call    cs:__imp_VariantCopy
0x18001bc5c  mov     edi, eax
0x18001bc5e  mov     r9d, eax; char *
0x18001bc61  test    eax, eax
0x18001bc63  jns     short loc_18001BC94
0x18001bc65  mov     edx, 3Fh ; '?'; void *
0x18001bc6a  lea     r8, aCW1SSrcClientP_5; "C:\\__w\\1\\s\\src\\Client\\policy\\inc"...
0x18001bc71  mov     rcx, [rbp+5Fh]; this
0x18001bc75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc7a  mov     edx, 2E0h; void *
0x18001bc7f  mov     rcx, [rbp+5Fh]; this
0x18001bc83  mov     r9d, edi; char *
0x18001bc86  lea     r8, aCW1SSrcClientP_9; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001bc8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc92  jmp     short loc_18001BCEC
0x18001bc94  cmp     dword ptr [rbp+57h+var_70+4], esi
0x18001bc97  jnz     short loc_18001BCEA
0x18001bc99  lea     rax, [rbp+57h+var_78]
0x18001bc9d  mov     [rbp+57h+var_B0], rax
0x18001bca1  lea     rax, [rbp+57h+var_48]
0x18001bca5  mov     [rbp+57h+var_A8], rax
0x18001bca9  lea     rax, [rbp+57h+var_80]
0x18001bcad  mov     [rbp+57h+var_A0], rax
0x18001bcb1  lea     rcx, [rbp+57h+var_B0]
0x18001bcb5  call    _lambda_2a40df9e8133e2652f1479e64240642f___operator__
0x18001bcba  mov     rcx, [rbp+5Fh]; this
0x18001bcbe  mov     [rsp+0F0h+var_C0], 80070003h
0x18001bcc6  mov     [rsp+0F0h+var_C8], 80070002h; unsigned int
0x18001bcce  mov     [rsp+0F0h+var_D0], 2; int
0x18001bcd6  mov     r9d, eax; char *
0x18001bcd9  lea     r8, aCW1SSrcClientP_9; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001bce0  mov     edx, 2FFh; void *
0x18001bce5  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x18001bcea  mov     edi, esi
0x18001bcec  mov     qword ptr [rbp+57h+var_70+4], rsi
0x18001bcf0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001bcf4  call    cs:__imp_VariantClear
0x18001bcfa  mov     qword ptr [rbp+57h+var_48+4], rsi
0x18001bcfe  lea     rcx, [rbp+57h+var_38]; pvarg
0x18001bd02  call    cs:__imp_VariantClear
0x18001bd08  mov     eax, edi
0x18001bd0a  mov     rcx, [rbp+57h+var_20]
0x18001bd0e  xor     rcx, rsp; StackCookie
0x18001bd11  call    __security_check_cookie
0x18001bd16  mov     rbx, [rsp+0F0h+arg_10]
0x18001bd1e  add     rsp, 0E0h
0x18001bd25  pop     rdi
0x18001bd26  pop     rsi
0x18001bd27  pop     rbp
0x18001bd28  retn
```
