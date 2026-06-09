# CUpdatePolicyReader::ReadEnterprisePolicy(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 *)

- ea: `0x18000c9e0`
- end: `0x18000ca6d`
- name: `?ReadEnterprisePolicy@CUpdatePolicyReader@@UEAAJW4tagEnterprisePolicy@@PEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c9e0`
- `0x180010ae0`
- `0x1800122f0`
- `0x18001f290`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18000ca2b`
- `OLEAUT32!__imp_VariantCopy` at `0x18000ca2b`

## pseudocode

```c
__int64 __fastcall CUpdatePolicyReader::ReadEnterprisePolicy(__int64 a1, unsigned int a2, __int64 a3)
{
  HRESULT v5; // ecx
  int v6; // eax
  struct tagEnterprisePolicyValue_V1 *v7; // rdi
  struct tagEnterprisePolicyValue_V1 *v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  if ( a3 )
  {
    PolicyHelpers::InitPolicyState((struct tagEnterprisePolicyValue_V1 *)a3);
    v6 = EnterprisePolicyReader::ReadPolicyWithFallback(a2, &v9);
    v7 = v9;
    v5 = v6;
    if ( v6 >= 0 )
    {
      v5 = VariantCopy((VARIANTARG *)(a3 + 16), (const VARIANTARG *)((char *)v9 + 16));
      if ( v5 >= 0 )
      {
        *(_DWORD *)a3 = *(_DWORD *)v7;
        *(_DWORD *)(a3 + 4) = *((_DWORD *)v7 + 1);
        *(_DWORD *)(a3 + 8) = *((_DWORD *)v7 + 2);
        *(_QWORD *)(a3 + 40) = *((_QWORD *)v7 + 5);
      }
    }
    if ( v7 )
      return (unsigned int)EnterprisePolicyReader::ReleaseEnterprisePolicyValue(&v9);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c9e0  mov     [rsp+arg_0], rbx
0x18000c9e5  push    rdi
0x18000c9e6  sub     rsp, 20h
0x18000c9ea  mov     [rsp+28h+arg_10], 0
0x18000c9f3  mov     rbx, r8
0x18000c9f6  mov     edi, edx
0x18000c9f8  test    r8, r8
0x18000c9fb  jnz     short loc_18000CA04
0x18000c9fd  mov     ecx, 80004003h
0x18000ca02  jmp     short loc_18000CA60
0x18000ca04  mov     rcx, rbx; struct tagEnterprisePolicyValue_V1 *
0x18000ca07  call    ?InitPolicyState@PolicyHelpers@@SAXPEAUtagEnterprisePolicyValue_V1@@@Z; PolicyHelpers::InitPolicyState(tagEnterprisePolicyValue_V1 *)
0x18000ca0c  lea     rdx, [rsp+28h+arg_10]
0x18000ca11  mov     ecx, edi
0x18000ca13  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x18000ca18  mov     rdi, [rsp+28h+arg_10]
0x18000ca1d  mov     ecx, eax
0x18000ca1f  test    eax, eax
0x18000ca21  js      short loc_18000CA4F
0x18000ca23  lea     rdx, [rdi+10h]; pvargSrc
0x18000ca27  lea     rcx, [rbx+10h]; pvargDest
0x18000ca2b  call    cs:__imp_VariantCopy
0x18000ca31  mov     ecx, eax
0x18000ca33  test    eax, eax
0x18000ca35  js      short loc_18000CA4F
0x18000ca37  mov     eax, [rdi]
0x18000ca39  mov     [rbx], eax
0x18000ca3b  mov     eax, [rdi+4]
0x18000ca3e  mov     [rbx+4], eax
0x18000ca41  mov     eax, [rdi+8]
0x18000ca44  mov     [rbx+8], eax
0x18000ca47  mov     rax, [rdi+28h]
0x18000ca4b  mov     [rbx+28h], rax
0x18000ca4f  test    rdi, rdi
0x18000ca52  jz      short loc_18000CA60
0x18000ca54  lea     rcx, [rsp+28h+arg_10]; struct tagEnterprisePolicyValue_V1 **
0x18000ca59  call    ?ReleaseEnterprisePolicyValue@EnterprisePolicyReader@@SAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReleaseEnterprisePolicyValue(tagEnterprisePolicyValue_V1 * *)
0x18000ca5e  mov     ecx, eax
0x18000ca60  mov     rbx, [rsp+28h+arg_0]
0x18000ca65  mov     eax, ecx
0x18000ca67  add     rsp, 20h
0x18000ca6b  pop     rdi
0x18000ca6c  retn
```
