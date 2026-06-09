# UpdatePolicyReader::ReadMDMPolicy_UpdateServiceUrlAlternate(tagUpdatePolicyValue_V1 *)

- ea: `0x18001d26c`
- end: `0x18001d378`
- name: `?ReadMDMPolicy_UpdateServiceUrlAlternate@UpdatePolicyReader@@CAJPEAUtagUpdatePolicyValue_V1@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct tagUpdatePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ccf0`

## callees

- `0x18001d26c`
- `0x18001e9e8`
- `0x18001f09c`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001d300`
- `OLEAUT32!__imp_SysStringLen` at `0x18001d300`
- `OLEAUT32!__imp_VariantInit` at `0x18001d2ad`
- `OLEAUT32!__imp_VariantInit` at `0x18001d2ad`
- `OLEAUT32!__imp_VariantClear` at `0x18001d34a`
- `OLEAUT32!__imp_VariantClear` at `0x18001d354`
- `OLEAUT32!__imp_VariantClear` at `0x18001d34a`
- `OLEAUT32!__imp_VariantClear` at `0x18001d354`

## string_xrefs

- `0x18001d2bf`: `UpdateServiceUrl`
- `0x18001d31b`: `UpdateServiceUrlAlternate`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadMDMPolicy_UpdateServiceUrlAlternate(struct tagUpdatePolicyValue_V1 *a1)
{
  const wchar_t *v2; // rdx
  const wchar_t *v3; // rdx
  int CspPolicy; // edi
  int v5; // ecx
  bool v6; // zf
  UINT v7; // eax
  _BYTE v9[40]; // [rsp+20h] [rbp-30h] BYREF

  memset(v9, 0, sizeof(v9));
  VariantInit((VARIANTARG *)&v9[16]);
  *(_QWORD *)&v9[4] = 0;
  *(_DWORD *)v9 = 0;
  CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"UpdateServiceUrl", v2, (struct tagUpdatePolicyValue_V1 *)v9);
  if ( CspPolicy < 0 )
    goto LABEL_13;
  if ( *(_DWORD *)&v9[4] != 1 )
    goto LABEL_12;
  switch ( *(_WORD *)&v9[16] )
  {
    case 3:
      v5 = 0;
      v6 = *(_DWORD *)&v9[24] == 0;
      break;
    case 8:
      v7 = SysStringLen(*(BSTR *)&v9[24]);
      v5 = 0;
      v6 = v7 == 0;
      break;
    case 0x15:
      v5 = 0;
      v6 = *(_QWORD *)&v9[24] == 0;
      break;
    default:
      goto LABEL_12;
  }
  LOBYTE(v5) = !v6;
  if ( !v5 )
    goto LABEL_12;
  CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"UpdateServiceUrlAlternate", v3, a1);
  if ( CspPolicy < 0 )
  {
LABEL_13:
    *(_QWORD *)((char *)a1 + 4) = 0;
    VariantClear((VARIANTARG *)((char *)a1 + 16));
    goto LABEL_14;
  }
  if ( !(unsigned int)PolicyHelpers::IsPolicyConfiguredAndEnabled(a1) )
  {
LABEL_12:
    CspPolicy = -2145124326;
    goto LABEL_13;
  }
LABEL_14:
  VariantClear((VARIANTARG *)&v9[16]);
  return (unsigned int)CspPolicy;
}

```

## disassembly

```asm
0x18001d26c  mov     [rsp-8+arg_8], rbx
0x18001d271  mov     [rsp-8+arg_10], rdi
0x18001d276  push    rbp
0x18001d277  mov     rbp, rsp
0x18001d27a  sub     rsp, 50h
0x18001d27e  mov     rax, cs:__security_cookie
0x18001d285  xor     rax, rsp
0x18001d288  mov     [rbp+var_8], rax
0x18001d28c  xor     eax, eax
0x18001d28e  lea     rdi, [rbp+var_30]
0x18001d292  mov     rbx, rcx
0x18001d295  mov     qword ptr [rbp+pvarg+10h], rax
0x18001d299  xorps   xmm0, xmm0
0x18001d29c  movups  [rbp+var_30], xmm0
0x18001d2a0  lea     ecx, [rax+28h]
0x18001d2a3  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001d2a7  rep stosb
0x18001d2a9  lea     rcx, [rbp+pvarg]; pvarg
0x18001d2ad  call    cs:__imp_VariantInit
0x18001d2b3  lea     r8, [rbp+var_30]; struct tagUpdatePolicyValue_V1 *
0x18001d2b7  mov     qword ptr [rbp+var_30+4], 0
0x18001d2bf  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001d2c6  mov     dword ptr [rbp+var_30], 0
0x18001d2cd  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d2d2  mov     edi, eax
0x18001d2d4  test    eax, eax
0x18001d2d6  js      short loc_18001D33E
0x18001d2d8  cmp     dword ptr [rbp+var_30+4], 1
0x18001d2dc  jnz     short loc_18001D339
0x18001d2de  movzx   eax, word ptr [rbp+pvarg]
0x18001d2e2  cmp     ax, 3
0x18001d2e6  jz      short loc_18001D30C
0x18001d2e8  cmp     ax, 8
0x18001d2ec  jz      short loc_18001D2FC
0x18001d2ee  cmp     ax, 15h
0x18001d2f2  jnz     short loc_18001D339
0x18001d2f4  xor     ecx, ecx
0x18001d2f6  cmp     qword ptr [rbp+pvarg+8], rcx
0x18001d2fa  jmp     short loc_18001D311
0x18001d2fc  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x18001d300  call    cs:__imp_SysStringLen
0x18001d306  xor     ecx, ecx
0x18001d308  test    eax, eax
0x18001d30a  jmp     short loc_18001D311
0x18001d30c  xor     ecx, ecx
0x18001d30e  cmp     dword ptr [rbp+pvarg+8], ecx
0x18001d311  setnz   cl
0x18001d314  test    ecx, ecx
0x18001d316  jz      short loc_18001D339
0x18001d318  mov     r8, rbx; struct tagUpdatePolicyValue_V1 *
0x18001d31b  lea     rcx, aUpdateserviceu; "UpdateServiceUrlAlternate"
0x18001d322  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d327  mov     edi, eax
0x18001d329  test    eax, eax
0x18001d32b  js      short loc_18001D33E
0x18001d32d  mov     rcx, rbx; struct tagUpdatePolicyValue_V1 *
0x18001d330  call    ?IsPolicyConfiguredAndEnabled@PolicyHelpers@@SAHPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::IsPolicyConfiguredAndEnabled(tagUpdatePolicyValue_V1 *)
0x18001d335  test    eax, eax
0x18001d337  jnz     short loc_18001D350
0x18001d339  mov     edi, 8024001Ah
0x18001d33e  lea     rcx, [rbx+10h]; pvarg
0x18001d342  mov     qword ptr [rbx+4], 0
0x18001d34a  call    cs:__imp_VariantClear
0x18001d350  lea     rcx, [rbp+pvarg]; pvarg
0x18001d354  call    cs:__imp_VariantClear
0x18001d35a  mov     eax, edi
0x18001d35c  mov     rcx, [rbp+var_8]
0x18001d360  xor     rcx, rsp; StackCookie
0x18001d363  call    __security_check_cookie
0x18001d368  mov     rbx, [rsp+50h+arg_8]
0x18001d36d  mov     rdi, [rsp+50h+arg_10]
0x18001d372  add     rsp, 50h
0x18001d376  pop     rbp
0x18001d377  retn
```
