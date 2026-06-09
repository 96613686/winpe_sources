# PolicyHelpers::IsDeferralAdjustmentForFlightingRequired(void)

- ea: `0x18001f0ec`
- end: `0x18001f289`
- name: `?IsDeferralAdjustmentForFlightingRequired@PolicyHelpers@@SA_NXZ`
- size: `413`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180017610`

## callees

- `0x180010ae0`
- `0x18001f0ec`
- `0x18002ffd0`
- `0x18003002c`
- `0x1800368f9`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f15a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f15a`
- `OLEAUT32!__imp_VariantClear` at `0x18001f243`
- `OLEAUT32!__imp_VariantClear` at `0x18001f243`

## string_xrefs

- `0x18001f14c`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\AllowAllReadinessLevelsForFlighting`

## pseudocode

```c
bool PolicyHelpers::IsDeferralAdjustmentForFlightingRequired(void)
{
  bool v0; // si
  __int64 v1; // rbx
  int v2; // eax
  __int64 v3; // rdi
  int v4; // eax
  bool v5; // r14
  int v6; // eax
  char v7; // cl
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  DWORD v10; // [rsp+38h] [rbp-18h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-14h] BYREF
  BYTE v12[8]; // [rsp+40h] [rbp-10h] BYREF

  v0 = 0;
  v1 = 0;
  v9 = 0;
  *(_DWORD *)v12 = 0;
  Type = 0;
  v10 = 4;
  if ( RegQueryValueExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test\\AllowAllReadinessLevelsForFlighting",
         0,
         &Type,
         v12,
         &v10)
    || v10 != 4
    || Type != 4
    || (v0 = *(_DWORD *)v12 != 0, !*(_DWORD *)v12) )
  {
    v2 = EnterprisePolicyReader::ReadPolicyWithFallback(5u, &v9);
    v1 = v9;
    if ( v2 >= 0 && *(_DWORD *)(v9 + 4) == 1 && *(_WORD *)(v9 + 16) == 8 )
    {
      v3 = *(_QWORD *)(v9 + 24);
      if ( v3 )
      {
        v4 = wcscmp_0(L"WIF", *(const wchar_t **)(v9 + 24));
        v5 = v4 == 0;
        if ( !v4 )
          goto LABEL_18;
        v6 = wcscmp_0(L"WIS", (const wchar_t *)v3);
        v7 = v5;
        if ( !v6 )
          v7 = 1;
        if ( v7
          || *(_WORD *)v3 == 82 && *(_WORD *)(v3 + 2) == 80 && !*(_WORD *)(v3 + 4)
          || !wcscmp_0(L"RPQU", (const wchar_t *)v3)
          || !wcscmp_0(L"Canary", (const wchar_t *)v3) )
        {
LABEL_18:
          v0 = 1;
        }
      }
    }
    if ( v1 )
      VariantClear((VARIANTARG *)(v1 + 16));
  }
  if ( v1 )
    operator delete((void *)v1);
  return v0;
}

```

## disassembly

```asm
0x18001f0ec  mov     r11, rsp
0x18001f0ef  mov     [r11+8], rbx
0x18001f0f3  mov     [r11+10h], rsi
0x18001f0f7  mov     [r11+18h], rdi
0x18001f0fb  mov     [r11+20h], r12
0x18001f0ff  push    rbp
0x18001f100  push    r14
0x18001f102  push    r15
0x18001f104  mov     rbp, rsp
0x18001f107  sub     rsp, 50h
0x18001f10b  mov     rax, cs:__security_cookie
0x18001f112  xor     rax, rsp
0x18001f115  mov     [rbp+var_8], rax
0x18001f119  xor     r15d, r15d
0x18001f11c  mov     sil, r15b
0x18001f11f  mov     ebx, r15d
0x18001f122  mov     [rbp+var_20], rbx
0x18001f126  mov     dword ptr [rbp+var_10], r15d
0x18001f12a  mov     [rbp+Type], r15d
0x18001f12e  mov     [rbp+var_18], 4
0x18001f135  lea     rax, [rbp+var_18]
0x18001f139  mov     [r11-40h], rax
0x18001f13d  lea     rax, [rbp+var_10]
0x18001f141  mov     [r11-48h], rax
0x18001f145  lea     r9, [rbp+Type]; lpType
0x18001f149  xor     r8d, r8d; lpReserved
0x18001f14c  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001f153  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f15a  call    cs:__imp_RegQueryValueExW
0x18001f160  test    eax, eax
0x18001f162  jnz     short loc_18001F181
0x18001f164  cmp     [rbp+var_18], 4
0x18001f168  jnz     short loc_18001F181
0x18001f16a  cmp     [rbp+Type], 4
0x18001f16e  jnz     short loc_18001F181
0x18001f170  mov     eax, dword ptr [rbp+var_10]
0x18001f173  test    eax, eax
0x18001f175  setnz   sil
0x18001f179  test    eax, eax
0x18001f17b  jnz     loc_18001F24A
0x18001f181  lea     rdx, [rbp+var_20]
0x18001f185  mov     ecx, 5
0x18001f18a  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x18001f18f  mov     rbx, [rbp+var_20]
0x18001f193  test    eax, eax
0x18001f195  js      loc_18001F23A
0x18001f19b  mov     r12d, 1
0x18001f1a1  cmp     [rbx+4], r12d
0x18001f1a5  jnz     loc_18001F23A
0x18001f1ab  cmp     word ptr [rbx+10h], 8
0x18001f1b0  jnz     loc_18001F23A
0x18001f1b6  mov     rdi, [rbx+18h]
0x18001f1ba  test    rdi, rdi
0x18001f1bd  jz      short loc_18001F23A
0x18001f1bf  mov     rdx, rdi; String2
0x18001f1c2  lea     rcx, aWif; "WIF"
0x18001f1c9  call    wcscmp_0
0x18001f1ce  test    eax, eax
0x18001f1d0  setz    r14b
0x18001f1d4  test    eax, eax
0x18001f1d6  jz      short loc_18001F237
0x18001f1d8  mov     rdx, rdi; String2
0x18001f1db  lea     rcx, aWis; "WIS"
0x18001f1e2  call    wcscmp_0
0x18001f1e7  movzx   ecx, r14b
0x18001f1eb  test    eax, eax
0x18001f1ed  cmovz   ecx, r12d
0x18001f1f1  test    cl, cl
0x18001f1f3  jnz     short loc_18001F237
0x18001f1f5  lea     eax, [r12+51h]
0x18001f1fa  cmp     ax, [rdi]
0x18001f1fd  jnz     short loc_18001F211
0x18001f1ff  lea     eax, [r12+4Fh]
0x18001f204  cmp     ax, [rdi+2]
0x18001f208  jnz     short loc_18001F211
0x18001f20a  cmp     r15w, [rdi+4]
0x18001f20f  jz      short loc_18001F237
0x18001f211  mov     rdx, rdi; String2
0x18001f214  lea     rcx, aRpqu; "RPQU"
0x18001f21b  call    wcscmp_0
0x18001f220  test    eax, eax
0x18001f222  jz      short loc_18001F237
0x18001f224  mov     rdx, rdi; String2
0x18001f227  lea     rcx, aCanary; "Canary"
0x18001f22e  call    wcscmp_0
0x18001f233  test    eax, eax
0x18001f235  jnz     short loc_18001F23A
0x18001f237  mov     sil, r12b
0x18001f23a  test    rbx, rbx
0x18001f23d  jz      short loc_18001F24A
0x18001f23f  lea     rcx, [rbx+10h]; pvarg
0x18001f243  call    cs:__imp_VariantClear
0x18001f249  nop
0x18001f24a  test    rbx, rbx
0x18001f24d  jz      short loc_18001F25C
0x18001f24f  mov     edx, 30h ; '0'
0x18001f254  mov     rcx, rbx; Block
0x18001f257  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f25c  mov     al, sil
0x18001f25f  mov     rcx, [rbp+var_8]
0x18001f263  xor     rcx, rsp; StackCookie
0x18001f266  call    __security_check_cookie
0x18001f26b  lea     r11, [rsp+50h+var_s0]
0x18001f270  mov     rbx, [r11+20h]
0x18001f274  mov     rsi, [r11+28h]
0x18001f278  mov     rdi, [r11+30h]
0x18001f27c  mov     r12, [r11+38h]
0x18001f280  mov     rsp, r11
0x18001f283  pop     r15
0x18001f285  pop     r14
0x18001f287  pop     rbp
0x18001f288  retn
```
