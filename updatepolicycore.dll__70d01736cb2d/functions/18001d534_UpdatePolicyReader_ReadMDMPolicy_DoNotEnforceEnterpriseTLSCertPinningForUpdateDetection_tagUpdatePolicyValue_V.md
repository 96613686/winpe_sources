# UpdatePolicyReader::ReadMDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection(tagUpdatePolicyValue_V1 *)

- ea: `0x18001d534`
- end: `0x18001d645`
- name: `?ReadMDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection@UpdatePolicyReader@@CAJPEAUtagUpdatePolicyValue_V1@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct tagUpdatePolicyValue_V1 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ccf0`

## callees

- `0x18001d534`
- `0x18001e7e4`
- `0x18001e9e8`
- `0x18002ffd0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001d5c8`
- `OLEAUT32!__imp_SysStringLen` at `0x18001d5c8`
- `OLEAUT32!__imp_VariantInit` at `0x18001d575`
- `OLEAUT32!__imp_VariantInit` at `0x18001d575`
- `OLEAUT32!__imp_VariantClear` at `0x18001d615`
- `OLEAUT32!__imp_VariantClear` at `0x18001d61f`
- `OLEAUT32!__imp_VariantClear` at `0x18001d615`
- `OLEAUT32!__imp_VariantClear` at `0x18001d61f`

## string_xrefs

- `0x18001d587`: `UpdateServiceUrl`
- `0x18001d5ee`: `DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadMDMPolicy_DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection(
        struct tagUpdatePolicyValue_V1 *a1)
{
  const wchar_t *v2; // rdx
  int CspPolicy; // edi
  int v4; // ecx
  bool v5; // zf
  UINT v6; // eax
  _BYTE v8[40]; // [rsp+30h] [rbp-30h] BYREF

  memset(v8, 0, sizeof(v8));
  VariantInit((VARIANTARG *)&v8[16]);
  *(_QWORD *)&v8[4] = 0;
  *(_DWORD *)v8 = 0;
  CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"UpdateServiceUrl", v2, (struct tagUpdatePolicyValue_V1 *)v8);
  if ( CspPolicy < 0 )
    goto LABEL_13;
  if ( *(_DWORD *)&v8[4] != 1 )
    goto LABEL_12;
  switch ( *(_WORD *)&v8[16] )
  {
    case 3:
      v4 = 0;
      v5 = *(_DWORD *)&v8[24] == 0;
      break;
    case 8:
      v6 = SysStringLen(*(BSTR *)&v8[24]);
      v4 = 0;
      v5 = v6 == 0;
      break;
    case 0x15:
      v4 = 0;
      v5 = *(_QWORD *)&v8[24] == 0;
      break;
    default:
LABEL_12:
      CspPolicy = -2145124326;
LABEL_13:
      *(_QWORD *)((char *)a1 + 4) = 0;
      VariantClear((VARIANTARG *)((char *)a1 + 16));
      goto LABEL_14;
  }
  LOBYTE(v4) = !v5;
  if ( !v4 )
    goto LABEL_12;
  CspPolicy = UpdatePolicyReader::ReadCspPolicy(L"DoNotEnforceEnterpriseTLSCertPinningForUpdateDetection", 0, 0, 1u, a1);
  if ( CspPolicy < 0 )
    goto LABEL_13;
LABEL_14:
  VariantClear((VARIANTARG *)&v8[16]);
  return (unsigned int)CspPolicy;
}

```

## disassembly

```asm
0x18001d534  mov     [rsp-8+arg_8], rbx
0x18001d539  mov     [rsp-8+arg_10], rdi
0x18001d53e  push    rbp
0x18001d53f  mov     rbp, rsp
0x18001d542  sub     rsp, 60h
0x18001d546  mov     rax, cs:__security_cookie
0x18001d54d  xor     rax, rsp
0x18001d550  mov     [rbp+var_8], rax
0x18001d554  xor     eax, eax
0x18001d556  lea     rdi, [rbp+var_30]
0x18001d55a  mov     rbx, rcx
0x18001d55d  mov     qword ptr [rbp+pvarg+10h], rax
0x18001d561  xorps   xmm0, xmm0
0x18001d564  movups  [rbp+var_30], xmm0
0x18001d568  lea     ecx, [rax+28h]
0x18001d56b  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001d56f  rep stosb
0x18001d571  lea     rcx, [rbp+pvarg]; pvarg
0x18001d575  call    cs:__imp_VariantInit
0x18001d57b  lea     r8, [rbp+var_30]; struct tagUpdatePolicyValue_V1 *
0x18001d57f  mov     qword ptr [rbp+var_30+4], 0
0x18001d587  lea     rcx, aUpdateserviceu_0; "UpdateServiceUrl"
0x18001d58e  mov     dword ptr [rbp+var_30], 0
0x18001d595  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_W0PEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)
0x18001d59a  mov     edi, eax
0x18001d59c  test    eax, eax
0x18001d59e  js      short loc_18001D609
0x18001d5a0  cmp     dword ptr [rbp+var_30+4], 1
0x18001d5a4  jnz     short loc_18001D604
0x18001d5a6  movzx   eax, word ptr [rbp+pvarg]
0x18001d5aa  cmp     ax, 3
0x18001d5ae  jz      short loc_18001D5D4
0x18001d5b0  cmp     ax, 8
0x18001d5b4  jz      short loc_18001D5C4
0x18001d5b6  cmp     ax, 15h
0x18001d5ba  jnz     short loc_18001D604
0x18001d5bc  xor     ecx, ecx
0x18001d5be  cmp     qword ptr [rbp+pvarg+8], rcx
0x18001d5c2  jmp     short loc_18001D5D9
0x18001d5c4  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x18001d5c8  call    cs:__imp_SysStringLen
0x18001d5ce  xor     ecx, ecx
0x18001d5d0  test    eax, eax
0x18001d5d2  jmp     short loc_18001D5D9
0x18001d5d4  xor     ecx, ecx
0x18001d5d6  cmp     dword ptr [rbp+pvarg+8], ecx
0x18001d5d9  setnz   cl
0x18001d5dc  test    ecx, ecx
0x18001d5de  jz      short loc_18001D604
0x18001d5e0  mov     r9d, 1; unsigned int
0x18001d5e6  mov     [rsp+60h+var_40], rbx; struct tagUpdatePolicyValue_V1 *
0x18001d5eb  xor     r8d, r8d; unsigned int
0x18001d5ee  lea     rcx, aDonotenforceen; "DoNotEnforceEnterpriseTLSCertPinningFor"...
0x18001d5f5  xor     edx, edx; unsigned int
0x18001d5f7  call    ?ReadCspPolicy@UpdatePolicyReader@@CAJPEB_WKKKPEAUtagUpdatePolicyValue_V1@@@Z; UpdatePolicyReader::ReadCspPolicy(wchar_t const *,ulong,ulong,ulong,tagUpdatePolicyValue_V1 *)
0x18001d5fc  mov     edi, eax
0x18001d5fe  test    eax, eax
0x18001d600  jns     short loc_18001D61B
0x18001d602  jmp     short loc_18001D609
0x18001d604  mov     edi, 8024001Ah
0x18001d609  lea     rcx, [rbx+10h]; pvarg
0x18001d60d  mov     qword ptr [rbx+4], 0
0x18001d615  call    cs:__imp_VariantClear
0x18001d61b  lea     rcx, [rbp+pvarg]; pvarg
0x18001d61f  call    cs:__imp_VariantClear
0x18001d625  mov     eax, edi
0x18001d627  mov     rcx, [rbp+var_8]
0x18001d62b  xor     rcx, rsp; StackCookie
0x18001d62e  call    __security_check_cookie
0x18001d633  lea     r11, [rsp+60h+var_s0]
0x18001d638  mov     rbx, [r11+18h]
0x18001d63c  mov     rdi, [r11+20h]
0x18001d640  mov     rsp, r11
0x18001d643  pop     rbp
0x18001d644  retn
```
