# EnterprisePolicyReader::ReadGPPolicy(wchar_t const *,wchar_t const *,ulong,ulong,ulong,ulong,tagEnterprisePolicyValue_V1 *)

- ea: `0x1800118d4`
- end: `0x180011b26`
- name: `?ReadGPPolicy@EnterprisePolicyReader@@CAJPEB_W0KKKKPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, unsigned int, unsigned int, unsigned int, unsigned int, struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010c1c`

## callees

- `0x18000aac0`
- `0x1800118d4`
- `0x180011b2c`
- `0x180011cf8`
- `0x1800163f8`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180011947`
- `OLEAUT32!__imp_VariantInit` at `0x18001196e`
- `OLEAUT32!__imp_VariantInit` at `0x180011947`
- `OLEAUT32!__imp_VariantInit` at `0x18001196e`
- `OLEAUT32!__imp_VariantClear` at `0x1800119fc`
- `OLEAUT32!__imp_VariantClear` at `0x180011af1`
- `OLEAUT32!__imp_VariantClear` at `0x180011aff`
- `OLEAUT32!__imp_VariantClear` at `0x1800119fc`
- `OLEAUT32!__imp_VariantClear` at `0x180011af1`
- `OLEAUT32!__imp_VariantClear` at `0x180011aff`
- `OLEAUT32!__imp_VariantCopy` at `0x180011a1b`
- `OLEAUT32!__imp_VariantCopy` at `0x180011a1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001195a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001197f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001195a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001197f`

## string_xrefs

- `0x1800119a0`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`
- `0x180011a4b`: `C:\__w\1\s\src\Client\policy\src\Enterprise\PolicyReader.cpp`
- `0x180011ad6`: `C:\__w\1\s\src\Client\policy\src\Enterprise\PolicyReader.cpp`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadGPPolicy(
        wchar_t *a1,
        const wchar_t *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        struct tagEnterprisePolicyValue_V1 *a7)
{
  int GPPolicyByType; // edi
  __int64 v8; // rdx
  struct tagEnterprisePolicyValue_V1 *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r9
  HRESULT v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // eax
  unsigned int v17; // [rsp+20h] [rbp-E0h]
  wchar_t *v18; // [rsp+30h] [rbp-D0h]
  _QWORD v19[10]; // [rsp+40h] [rbp-C0h] BYREF
  char v20; // [rsp+90h] [rbp-70h]
  wchar_t *v21; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v22; // [rsp+A0h] [rbp-60h] BYREF
  struct tagEnterprisePolicyValue_V1 *v23; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v24; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v25; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v26[3]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v27[3]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v21 = a1;
  v24 = a3;
  v25 = a4;
  v23 = a7;
  v22 = (wchar_t *)&psz;
  memset(v27, 0, sizeof(v27));
  memset(v26, 0, sizeof(v26));
  VariantInit((VARIANTARG *)&v26[1]);
  *(_QWORD *)((char *)v26 + 4) = 0;
  LODWORD(v26[0]) = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&v26[2] + 1);
  memset(v27, 0, sizeof(v27));
  VariantInit((VARIANTARG *)&v27[1]);
  *(_QWORD *)((char *)v27 + 4) = 0;
  LODWORD(v27[0]) = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&v27[2] + 1);
  v19[8] = v26;
  v19[9] = v27;
  v20 = 1;
  GPPolicyByType = EnterprisePolicyReader::ReadGPPolicyByType(
                     v21,
                     &psz,
                     v24,
                     v25,
                     a5,
                     (struct tagEnterprisePolicyValue_V1 *)v26,
                     L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate",
                     a6);
  if ( GPPolicyByType < 0 )
  {
    v8 = 771;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyReader.cpp",
      (const char *)(unsigned int)GPPolicyByType,
      v17);
    goto LABEL_12;
  }
  v9 = v23;
  if ( !v23 )
  {
    GPPolicyByType = -2147024809;
    v10 = 56;
    v11 = 2147942487LL;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\inc\\PolicyHelpers.h",
      (const char *)v11,
      v17);
    v8 = 772;
    goto LABEL_8;
  }
  *(_QWORD *)((char *)v23 + 4) = 0;
  VariantClear((VARIANTARG *)((char *)v9 + 16));
  *(_QWORD *)v9 = *(_QWORD *)&v26[0];
  *((_DWORD *)v9 + 2) = DWORD2(v26[0]);
  v12 = VariantCopy((VARIANTARG *)((char *)v9 + 16), (const VARIANTARG *)&v26[1]);
  GPPolicyByType = v12;
  v11 = (unsigned int)v12;
  if ( v12 < 0 )
  {
    v10 = 63;
    goto LABEL_7;
  }
  if ( !DWORD1(v26[0]) )
  {
    v19[0] = &v21;
    v19[1] = &v22;
    v19[2] = &v24;
    v19[3] = &v25;
    v19[4] = &a5;
    v19[5] = v27;
    v19[6] = &a6;
    v19[7] = &v23;
    v15 = lambda_f42496e0d419d423fb7a39fd731914ee_::operator()(v19, v13, v14, (unsigned int)v12);
    LODWORD(v18) = -2147024893;
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x326,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyReader.cpp",
      (const char *)v15,
      2,
      0x80070002,
      v18);
  }
  GPPolicyByType = 0;
LABEL_12:
  *(_QWORD *)((char *)v26 + 4) = 0;
  VariantClear((VARIANTARG *)&v26[1]);
  *(_QWORD *)((char *)v27 + 4) = 0;
  VariantClear((VARIANTARG *)&v27[1]);
  return (unsigned int)GPPolicyByType;
}

```

## disassembly

```asm
0x1800118d4  mov     [rsp-8+arg_8], rbx
0x1800118d9  push    rbp
0x1800118da  push    rsi
0x1800118db  push    rdi
0x1800118dc  lea     rbp, [rsp-30h]
0x1800118e1  sub     rsp, 130h
0x1800118e8  mov     rax, cs:__security_cookie
0x1800118ef  xor     rax, rsp
0x1800118f2  mov     [rbp+40h+var_20], rax
0x1800118f6  mov     [rbp+40h+var_A8], rcx
0x1800118fa  mov     [rbp+40h+var_90], r8d
0x1800118fe  mov     [rbp+40h+var_88], r9d
0x180011902  mov     rax, [rbp+40h+arg_30]
0x180011909  mov     [rbp+40h+var_98], rax
0x18001190d  lea     rax, psz
0x180011914  mov     [rbp+40h+var_A0], rax
0x180011918  xorps   xmm0, xmm0
0x18001191b  movups  [rbp+40h+var_50], xmm0
0x18001191f  movups  xmmword ptr [rbp+40h+var_40], xmm0
0x180011923  movups  xmmword ptr [rbp+40h+var_40+10h], xmm0
0x180011927  xorps   xmm1, xmm1
0x18001192a  movups  [rbp+40h+var_80], xmm1
0x18001192e  movups  xmmword ptr [rbp+40h+pvarg], xmm1
0x180011932  movups  xmmword ptr [rbp+40h+pvarg+10h], xmm1
0x180011936  lea     rdi, [rbp+40h+var_80]
0x18001193a  xor     eax, eax
0x18001193c  lea     ebx, [rax+30h]
0x18001193f  mov     ecx, ebx
0x180011941  rep stosb
0x180011943  lea     rcx, [rbp+40h+pvarg]; pvarg
0x180011947  call    cs:__imp_VariantInit
0x18001194d  xor     esi, esi
0x18001194f  mov     qword ptr [rbp+40h+var_80+4], rsi
0x180011953  mov     dword ptr [rbp+40h+var_80], esi
0x180011956  lea     rcx, [rbp+40h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001195a  call    cs:__imp_GetSystemTimeAsFileTime
0x180011960  lea     rdi, [rbp+40h+var_50]
0x180011964  xor     eax, eax
0x180011966  mov     ecx, ebx
0x180011968  rep stosb
0x18001196a  lea     rcx, [rbp+40h+var_40]; pvarg
0x18001196e  call    cs:__imp_VariantInit
0x180011974  mov     qword ptr [rbp+40h+var_50+4], rsi
0x180011978  mov     dword ptr [rbp+40h+var_50], esi
0x18001197b  lea     rcx, [rbp+40h+var_28]; lpSystemTimeAsFileTime
0x18001197f  call    cs:__imp_GetSystemTimeAsFileTime
0x180011985  lea     rax, [rbp+40h+var_80]
0x180011989  mov     [rbp+40h+var_C0], rax
0x18001198d  lea     rax, [rbp+40h+var_50]
0x180011991  mov     [rbp+40h+var_B8], rax
0x180011995  mov     [rbp+40h+var_B0], 1
0x180011999  mov     eax, [rbp+40h+arg_28]
0x18001199c  mov     [rsp+140h+var_108], eax; unsigned int
0x1800119a0  lea     rax, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800119a7  mov     [rsp+140h+var_110], rax; wchar_t *
0x1800119ac  lea     rax, [rbp+40h+var_80]
0x1800119b0  mov     [rsp+140h+var_118], rax; struct tagEnterprisePolicyValue_V1 *
0x1800119b5  mov     eax, [rbp+40h+arg_20]
0x1800119b8  mov     [rsp+140h+var_120], eax; int
0x1800119bc  mov     r9d, [rbp+40h+var_88]; unsigned int
0x1800119c0  mov     r8d, [rbp+40h+var_90]; unsigned int
0x1800119c4  mov     rdx, [rbp+40h+var_A0]; wchar_t *
0x1800119c8  mov     rcx, [rbp+40h+var_A8]; wchar_t *
0x1800119cc  call    ?ReadGPPolicyByType@EnterprisePolicyReader@@CAJPEB_W0KKKPEAUtagEnterprisePolicyValue_V1@@0K@Z; EnterprisePolicyReader::ReadGPPolicyByType(wchar_t const *,wchar_t const *,ulong,ulong,ulong,tagEnterprisePolicyValue_V1 *,wchar_t const *,ulong)
0x1800119d1  mov     edi, eax
0x1800119d3  test    eax, eax
0x1800119d5  jns     short loc_1800119DE
0x1800119d7  mov     edx, 303h
0x1800119dc  jmp     short loc_180011A44
0x1800119de  mov     rbx, [rbp+40h+var_98]
0x1800119e2  test    rbx, rbx
0x1800119e5  jnz     short loc_1800119F4
0x1800119e7  mov     edi, 80070057h
0x1800119ec  lea     edx, [rbx+38h]
0x1800119ef  mov     r9d, edi
0x1800119f2  jmp     short loc_180011A2F
0x1800119f4  mov     [rbx+4], rsi
0x1800119f8  lea     rcx, [rbx+10h]; pvarg
0x1800119fc  call    cs:__imp_VariantClear
0x180011a02  mov     eax, dword ptr [rbp+40h+var_80+4]
0x180011a05  mov     [rbx+4], eax
0x180011a08  mov     eax, dword ptr [rbp+40h+var_80]
0x180011a0b  mov     [rbx], eax
0x180011a0d  mov     eax, dword ptr [rbp+40h+var_80+8]
0x180011a10  mov     [rbx+8], eax
0x180011a13  lea     rdx, [rbp+40h+pvarg]; pvargSrc
0x180011a17  lea     rcx, [rbx+10h]; pvargDest
0x180011a1b  call    cs:__imp_VariantCopy
0x180011a21  mov     edi, eax
0x180011a23  mov     r9d, eax; char *
0x180011a26  test    eax, eax
0x180011a28  jns     short loc_180011A5C
0x180011a2a  mov     edx, 3Fh ; '?'; void *
0x180011a2f  lea     r8, aCW1SSrcClientP_5; "C:\\__w\\1\\s\\src\\Client\\policy\\inc"...
0x180011a36  mov     rcx, [rbp+48h]; this
0x180011a3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a3f  mov     edx, 304h; void *
0x180011a44  mov     rcx, [rbp+48h]; this
0x180011a48  mov     r9d, edi; char *
0x180011a4b  lea     r8, aCW1SSrcClientP_4; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180011a52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a57  jmp     loc_180011AE9
0x180011a5c  cmp     dword ptr [rbp+40h+var_80+4], esi
0x180011a5f  jnz     loc_180011AE7
0x180011a65  lea     rax, [rbp+40h+var_A8]
0x180011a69  mov     [rsp+140h+var_100], rax
0x180011a6e  lea     rax, [rbp+40h+var_A0]
0x180011a72  mov     [rsp+140h+var_F8], rax
0x180011a77  lea     rax, [rbp+40h+var_90]
0x180011a7b  mov     [rsp+140h+var_F0], rax
0x180011a80  lea     rax, [rbp+40h+var_88]
0x180011a84  mov     [rsp+140h+var_E8], rax
0x180011a89  lea     rax, [rbp+40h+arg_20]
0x180011a8d  mov     [rsp+140h+var_E0], rax
0x180011a92  lea     rax, [rbp+40h+var_50]
0x180011a96  mov     [rsp+140h+var_D8], rax
0x180011a9b  lea     rax, [rbp+40h+arg_28]
0x180011a9f  mov     [rsp+140h+var_D0], rax
0x180011aa4  lea     rax, [rbp+40h+var_98]
0x180011aa8  mov     [rsp+140h+var_C8], rax
0x180011aad  lea     rcx, [rsp+140h+var_100]
0x180011ab2  call    _lambda_f42496e0d419d423fb7a39fd731914ee___operator__
0x180011ab7  mov     rcx, [rbp+48h]; this
0x180011abb  mov     dword ptr [rsp+140h+var_110], 80070003h
0x180011ac3  mov     dword ptr [rsp+140h+var_118], 80070002h; unsigned int
0x180011acb  mov     [rsp+140h+var_120], 2; int
0x180011ad3  mov     r9d, eax; char *
0x180011ad6  lea     r8, aCW1SSrcClientP_4; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180011add  mov     edx, 326h; void *
0x180011ae2  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180011ae7  mov     edi, esi
0x180011ae9  mov     qword ptr [rbp+40h+var_80+4], rsi
0x180011aed  lea     rcx, [rbp+40h+pvarg]; pvarg
0x180011af1  call    cs:__imp_VariantClear
0x180011af7  mov     qword ptr [rbp+40h+var_50+4], rsi
0x180011afb  lea     rcx, [rbp+40h+var_40]; pvarg
0x180011aff  call    cs:__imp_VariantClear
0x180011b05  mov     eax, edi
0x180011b07  mov     rcx, [rbp+40h+var_20]
0x180011b0b  xor     rcx, rsp; StackCookie
0x180011b0e  call    __security_check_cookie
0x180011b13  mov     rbx, [rsp+140h+arg_8]
0x180011b1b  add     rsp, 130h
0x180011b22  pop     rdi
0x180011b23  pop     rsi
0x180011b24  pop     rbp
0x180011b25  retn
```
