# UpdatePolicyReader::ReadMDMPolicy_FillEmptyContentUrls(tagUpdatePolicyValue_V1 *)

- ea: `0x18001d380`
- end: `0x18001d52d`
- name: `?ReadMDMPolicy_FillEmptyContentUrls@UpdatePolicyReader@@CAJPEAUtagUpdatePolicyValue_V1@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(struct tagUpdatePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ccf0`

## callees

- `0x18001d380`
- `0x18001e7e4`
- `0x18001e9e8`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001d44f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001d4a3`
- `OLEAUT32!__imp_SysStringLen` at `0x18001d44f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001d4a3`
- `OLEAUT32!__imp_VariantInit` at `0x18001d3d9`
- `OLEAUT32!__imp_VariantInit` at `0x18001d3f9`
- `OLEAUT32!__imp_VariantInit` at `0x18001d3d9`
- `OLEAUT32!__imp_VariantInit` at `0x18001d3f9`
- `OLEAUT32!__imp_VariantClear` at `0x18001d4ec`
- `OLEAUT32!__imp_VariantClear` at `0x18001d4f6`
- `OLEAUT32!__imp_VariantClear` at `0x18001d500`
- `OLEAUT32!__imp_VariantClear` at `0x18001d4ec`
- `OLEAUT32!__imp_VariantClear` at `0x18001d4f6`
- `OLEAUT32!__imp_VariantClear` at `0x18001d500`

## string_xrefs

- `0x18001d407`: `UpdateServiceUrl`
- `0x18001d46b`: `UpdateServiceUrlAlternate`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadMDMPolicy_FillEmptyContentUrls(struct tagUpdatePolicyValue_V1 *a1)
{
  const wchar_t *v2; // rdx
  const wchar_t *v3; // rdx
  int CspPolicy; // edi
  bool v5; // zf
  bool v6; // zf
  _BYTE v8[40]; // [rsp+38h] [rbp-9h] BYREF
  _BYTE v9[40]; // [rsp+60h] [rbp+1Fh] BYREF

  memset(v8, 0, sizeof(v8));
  memset(v9, 0, sizeof(v9));
  VariantInit((VARIANTARG *)&v8[16]);
  *(_QWORD *)&v8[4] = 0;
  *(_DWORD *)v8 = 0;
  memset(v9, 0, sizeof(v9));
  VariantInit((VARIANTARG *)&v9[16]);
  *(_QWORD *)&v9[4] = 0;
  *(_DWORD *)v9 = 0;
  CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"UpdateServiceUrl", v2, (struct tagUpdatePolicyValue_V1 *)v8);
  if ( CspPolicy < 0 )
    goto LABEL_22;
  if ( *(_DWORD *)&v8[4] != 1 )
    goto LABEL_21;
  switch ( *(_WORD *)&v8[16] )
  {
    case 3:
      v5 = *(_DWORD *)&v8[24] == 0;
      break;
    case 8:
      v5 = SysStringLen(*(BSTR *)&v8[24]) == 0;
      break;
    case 0x15:
      v5 = *(_QWORD *)&v8[24] == 0;
      break;
    default:
      goto LABEL_21;
  }
  if ( v5 )
    goto LABEL_21;
  CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"UpdateServiceUrlAlternate", v3, (struct tagUpdatePolicyValue_V1 *)v9);
  if ( CspPolicy < 0 )
  {
LABEL_22:
    *(_QWORD *)((char *)a1 + 4) = 0;
    VariantClear((VARIANTARG *)((char *)a1 + 16));
    goto LABEL_23;
  }
  if ( *(_DWORD *)&v9[4] != 1 )
  {
LABEL_21:
    CspPolicy = -2145124326;
    goto LABEL_22;
  }
  switch ( *(_WORD *)&v9[16] )
  {
    case 3:
      v6 = *(_DWORD *)&v9[24] == 0;
      break;
    case 8:
      v6 = SysStringLen(*(BSTR *)&v9[24]) == 0;
      break;
    case 0x15:
      v6 = *(_QWORD *)&v9[24] == 0;
      break;
    default:
      goto LABEL_21;
  }
  if ( v6 )
    goto LABEL_21;
  CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"FillEmptyContentUrls", 0, 0, 1u, a1);
  if ( CspPolicy < 0 )
    goto LABEL_22;
LABEL_23:
  VariantClear((VARIANTARG *)&v8[16]);
  VariantClear((VARIANTARG *)&v9[16]);
  return (unsigned int)CspPolicy;
}

```

## disassembly

```asm
0x18001d380  mov     rax, rsp
0x18001d383  mov     [rax+10h], rbx
0x18001d387  mov     [rax+18h], rdi
0x18001d38b  mov     [rax+20h], r14
0x18001d38f  push    rbp
0x18001d390  lea     rbp, [rax-5Fh]
0x18001d394  sub     rsp, 90h
0x18001d39b  mov     rax, cs:__security_cookie
0x18001d3a2  xor     rax, rsp
0x18001d3a5  mov     [rbp+57h+var_10], rax
0x18001d3a9  xor     eax, eax
0x18001d3ab  lea     rdi, [rbp+57h+var_60]
0x18001d3af  mov     rbx, rcx
0x18001d3b2  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001d3b6  xorps   xmm0, xmm0
0x18001d3b9  mov     qword ptr [rbp+57h+var_28+10h], rax
0x18001d3bd  xorps   xmm1, xmm1
0x18001d3c0  lea     ecx, [rax+28h]
0x18001d3c3  movups  [rbp+57h+var_60], xmm0
0x18001d3c7  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001d3cb  rep stosb
0x18001d3cd  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001d3d1  movups  [rbp+57h+var_38], xmm1
0x18001d3d5  movups  xmmword ptr [rbp+57h+var_28], xmm1
0x18001d3d9  call    cs:__imp_VariantInit
0x18001d3df  xor     eax, eax
0x18001d3e1  lea     rdi, [rbp+57h+var_38]
0x18001d3e5  xor     r14d, r14d
0x18001d3e8  mov     qword ptr [rbp+57h+var_60+4], r14
0x18001d3ec  mov     dword ptr [rbp+57h+var_60], r14d
0x18001d3f0  lea     ecx, [rax+28h]
0x18001d3f3  rep stosb
0x18001d3f5  lea     rcx, [rbp+57h+var_28]; pvarg
0x18001d3f9  call    cs:__imp_VariantInit
0x18001d3ff  lea     r8, [rbp+57h+var_60]; struct tagUpdatePolicyValue_V1 *
0x18001d403  mov     qword ptr [rbp+57h+var_38+4], r14
0x18001d407  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001d40e  mov     dword ptr [rbp+57h+var_38], r14d
0x18001d412  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d417  mov     edi, eax
0x18001d419  test    eax, eax
0x18001d41b  js      loc_18001D4E4
0x18001d421  cmp     dword ptr [rbp+57h+var_60+4], 1
0x18001d425  jnz     loc_18001D4DF
0x18001d42b  movzx   eax, word ptr [rbp+57h+pvarg]
0x18001d42f  cmp     ax, 3
0x18001d433  jz      short loc_18001D459
0x18001d435  cmp     ax, 8
0x18001d439  jz      short loc_18001D44B
0x18001d43b  cmp     ax, 15h
0x18001d43f  jnz     loc_18001D4DF
0x18001d445  cmp     qword ptr [rbp+57h+pvarg+8], r14
0x18001d449  jmp     short loc_18001D45D
0x18001d44b  mov     rcx, qword ptr [rbp+57h+pvarg+8]; pbstr
0x18001d44f  call    cs:__imp_SysStringLen
0x18001d455  test    eax, eax
0x18001d457  jmp     short loc_18001D45D
0x18001d459  cmp     dword ptr [rbp+57h+pvarg+8], r14d
0x18001d45d  mov     ecx, r14d
0x18001d460  setnz   cl
0x18001d463  test    ecx, ecx
0x18001d465  jz      short loc_18001D4DF
0x18001d467  lea     r8, [rbp+57h+var_38]; struct tagUpdatePolicyValue_V1 *
0x18001d46b  lea     rcx, aUpdateserviceu; "UpdateServiceUrlAlternate"
0x18001d472  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d477  mov     edi, eax
0x18001d479  test    eax, eax
0x18001d47b  js      short loc_18001D4E4
0x18001d47d  cmp     dword ptr [rbp+57h+var_38+4], 1
0x18001d481  jnz     short loc_18001D4DF
0x18001d483  movzx   eax, word ptr [rbp+57h+var_28]
0x18001d487  cmp     ax, 3
0x18001d48b  jz      short loc_18001D4AD
0x18001d48d  cmp     ax, 8
0x18001d491  jz      short loc_18001D49F
0x18001d493  cmp     ax, 15h
0x18001d497  jnz     short loc_18001D4DF
0x18001d499  cmp     qword ptr [rbp+57h+var_28+8], r14
0x18001d49d  jmp     short loc_18001D4B1
0x18001d49f  mov     rcx, qword ptr [rbp+57h+var_28+8]; pbstr
0x18001d4a3  call    cs:__imp_SysStringLen
0x18001d4a9  test    eax, eax
0x18001d4ab  jmp     short loc_18001D4B1
0x18001d4ad  cmp     dword ptr [rbp+57h+var_28+8], r14d
0x18001d4b1  mov     ecx, r14d
0x18001d4b4  setnz   cl
0x18001d4b7  test    ecx, ecx
0x18001d4b9  jz      short loc_18001D4DF
0x18001d4bb  mov     r9d, 1; unsigned int
0x18001d4c1  mov     [rsp+90h+var_70], rbx; struct tagUpdatePolicyValue_V1 *
0x18001d4c6  xor     r8d, r8d; unsigned int
0x18001d4c9  lea     rcx, aFillemptyconte; "FillEmptyContentUrls"
0x18001d4d0  xor     edx, edx; unsigned int
0x18001d4d2  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001d4d7  mov     edi, eax
0x18001d4d9  test    eax, eax
0x18001d4db  jns     short loc_18001D4F2
0x18001d4dd  jmp     short loc_18001D4E4
0x18001d4df  mov     edi, 8024001Ah
0x18001d4e4  lea     rcx, [rbx+10h]; pvarg
0x18001d4e8  mov     [rbx+4], r14
0x18001d4ec  call    cs:__imp_VariantClear
0x18001d4f2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001d4f6  call    cs:__imp_VariantClear
0x18001d4fc  lea     rcx, [rbp+57h+var_28]; pvarg
0x18001d500  call    cs:__imp_VariantClear
0x18001d506  mov     eax, edi
0x18001d508  mov     rcx, [rbp+57h+var_10]
0x18001d50c  xor     rcx, rsp; StackCookie
0x18001d50f  call    __security_check_cookie
0x18001d514  lea     r11, [rsp+90h+var_s0]
0x18001d51c  mov     rbx, [r11+18h]
0x18001d520  mov     rdi, [r11+20h]
0x18001d524  mov     r14, [r11+28h]
0x18001d528  mov     rsp, r11
0x18001d52b  pop     rbp
0x18001d52c  retn
```
