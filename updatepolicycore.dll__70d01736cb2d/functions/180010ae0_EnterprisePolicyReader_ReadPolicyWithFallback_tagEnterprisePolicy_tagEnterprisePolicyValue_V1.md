# EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)

- ea: `0x180010ae0`
- end: `0x180010c14`
- name: `?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(unsigned int, __int64 *)`
- caller_count: `8`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000c9e0`
- `0x180016eb0`
- `0x180017b30`
- `0x180017bd0`
- `0x180017c70`
- `0x180018020`
- `0x1800183d0`
- `0x18001f0ec`

## callees

- `0x18000aac0`
- `0x180010ae0`
- `0x180010c1c`
- `0x18001efb4`
- `0x18001f290`
- `0x18001f44c`
- `0x180030734`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180010bef`
- `OLEAUT32!__imp_VariantClear` at `0x180010bef`

## pseudocode

```c
__int64 __fastcall EnterprisePolicyReader::ReadPolicyWithFallback(unsigned int a1, __int64 *a2)
{
  unsigned __int64 v3; // rsi
  __int64 v4; // rdi
  int PolicyWithFallbackInternal; // ebx
  struct tagEnterprisePolicyValue_V1 *v6; // rax
  _QWORD *v7; // rax
  _BYTE *v8; // rcx
  int SkuUpdateManagementGroupHelper; // eax
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = (int)a1;
  v4 = 0;
  if ( a2 )
  {
    if ( a1 > 0x55 )
    {
      PolicyWithFallbackInternal = -2147024809;
    }
    else
    {
      v6 = (struct tagEnterprisePolicyValue_V1 *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v6 )
      {
        *(_OWORD *)v6 = 0;
        *((_OWORD *)v6 + 1) = 0;
        *((_OWORD *)v6 + 2) = 0;
        v4 = (__int64)v6;
        PolicyHelpers::InitPolicyState(v6);
        PolicyWithFallbackInternal = 0;
        v7 = (_QWORD *)*((_QWORD *)Block + 1);
        v8 = Block;
        while ( !*((_BYTE *)v7 + 25) )
        {
          if ( *((_DWORD *)v7 + 7) >= (int)v3 )
            v8 = v7;
          else
            v7 += 2;
          v7 = (_QWORD *)*v7;
        }
        if ( v8[25] || (int)v3 < *((_DWORD *)v8 + 7) )
          v8 = Block;
        if ( v8 == Block
          && ((SkuUpdateManagementGroupHelper = PolicyHelpers::GetSkuUpdateManagementGroupHelper(v8),
               (unsigned int)v3 <= 0x39)
           && (v10 = 0x20000010001E020LL, _bittest64(&v10, v3))
           || SkuUpdateManagementGroupHelper) )
        {
          PolicyWithFallbackInternal = EnterprisePolicyReader::ReadPolicyWithFallbackInternal(v3, v4);
        }
        else
        {
          PolicyHelpers::SetPolicyInapplicableState((unsigned int)v3, v4);
        }
      }
      else
      {
        PolicyWithFallbackInternal = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\inc\\PolicyHelpers.h",
          (const char *)0x8007000ELL,
          v12);
      }
    }
  }
  else
  {
    PolicyWithFallbackInternal = -2147467261;
  }
  if ( v4 )
  {
    if ( PolicyWithFallbackInternal < 0 )
    {
      VariantClear((VARIANTARG *)(v4 + 16));
      *(_QWORD *)(v4 + 4) = 0;
      *(_DWORD *)v4 = v3;
      PolicyWithFallbackInternal = 0;
    }
    *a2 = v4;
  }
  return (unsigned int)PolicyWithFallbackInternal;
}

```

## disassembly

```asm
0x180010ae0  mov     [rsp+arg_10], rbx
0x180010ae5  push    rsi
0x180010ae6  push    rdi
0x180010ae7  push    r14
0x180010ae9  sub     rsp, 40h
0x180010aed  mov     r14, rdx
0x180010af0  movsxd  rsi, ecx
0x180010af3  xor     edi, edi
0x180010af5  test    rdx, rdx
0x180010af8  jnz     short loc_180010B04
0x180010afa  mov     ebx, 80004003h
0x180010aff  jmp     loc_180010BE2
0x180010b04  cmp     esi, 55h ; 'U'
0x180010b07  ja      loc_180010BDD
0x180010b0d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010b14  mov     ecx, 30h ; '0'; unsigned __int64
0x180010b19  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010b1e  test    rax, rax
0x180010b21  jz      loc_180010BBD
0x180010b27  xorps   xmm0, xmm0
0x180010b2a  movups  xmmword ptr [rax], xmm0
0x180010b2d  movups  xmmword ptr [rax+10h], xmm0
0x180010b31  movups  xmmword ptr [rax+20h], xmm0
0x180010b35  mov     rdi, rax
0x180010b38  mov     rcx, rax; struct tagEnterprisePolicyValue_V1 *
0x180010b3b  call    ?InitPolicyState@PolicyHelpers@@SAXPEAUtagEnterprisePolicyValue_V1@@@Z; PolicyHelpers::InitPolicyState(tagEnterprisePolicyValue_V1 *)
0x180010b40  mov     qword ptr [rsp+58h+var_38], rdi
0x180010b45  xor     ebx, ebx
0x180010b47  mov     rdx, cs:Block
0x180010b4e  mov     rax, [rdx+8]
0x180010b52  xor     ecx, ecx
0x180010b54  mov     [rsp+58h+var_24], ecx
0x180010b58  mov     rcx, rdx
0x180010b5b  jmp     short loc_180010B6E
0x180010b5d  cmp     [rax+1Ch], esi
0x180010b60  jge     short loc_180010B68
0x180010b62  add     rax, 10h
0x180010b66  jmp     short loc_180010B6B
0x180010b68  mov     rcx, rax
0x180010b6b  mov     rax, [rax]
0x180010b6e  cmp     [rax+19h], bl
0x180010b71  jz      short loc_180010B5D
0x180010b73  cmp     [rcx+19h], bl
0x180010b76  jnz     short loc_180010B7D
0x180010b78  cmp     esi, [rcx+1Ch]
0x180010b7b  jge     short loc_180010B80
0x180010b7d  mov     rcx, rdx
0x180010b80  cmp     rcx, rdx
0x180010b83  jz      short loc_180010B91
0x180010b85  mov     rdx, rdi
0x180010b88  mov     ecx, esi
0x180010b8a  call    ?SetPolicyInapplicableState@PolicyHelpers@@SAJW4tagEnterprisePolicy@@PEAUtagEnterprisePolicyValue_V1@@@Z; PolicyHelpers::SetPolicyInapplicableState(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 *)
0x180010b8f  jmp     short loc_180010BE2
0x180010b91  call    ?GetSkuUpdateManagementGroupHelper@PolicyHelpers@@SA?AW4tagUpdateManagementGroup@@XZ; PolicyHelpers::GetSkuUpdateManagementGroupHelper(void)
0x180010b96  cmp     esi, 39h ; '9'
0x180010b99  ja      short loc_180010BAB
0x180010b9b  mov     rdx, 20000010001E020h
0x180010ba5  bt      rdx, rsi
0x180010ba9  jb      short loc_180010BAF
0x180010bab  test    eax, eax
0x180010bad  jz      short loc_180010B85
0x180010baf  mov     rdx, rdi
0x180010bb2  mov     ecx, esi
0x180010bb4  call    ?ReadPolicyWithFallbackInternal@EnterprisePolicyReader@@CAJW4tagEnterprisePolicy@@PEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallbackInternal(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 *)
0x180010bb9  mov     ebx, eax
0x180010bbb  jmp     short loc_180010BE2
0x180010bbd  mov     ebx, 8007000Eh
0x180010bc2  mov     rcx, [rsp+58h]; this
0x180010bc7  mov     r9d, ebx; char *
0x180010bca  lea     r8, aCW1SSrcClientP_5; "C:\\__w\\1\\s\\src\\Client\\policy\\inc"...
0x180010bd1  mov     edx, 4Ah ; 'J'; void *
0x180010bd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bdb  jmp     short loc_180010BE2
0x180010bdd  mov     ebx, 80070057h
0x180010be2  test    rdi, rdi
0x180010be5  jz      short loc_180010C04
0x180010be7  test    ebx, ebx
0x180010be9  jns     short loc_180010C01
0x180010beb  lea     rcx, [rdi+10h]; pvarg
0x180010bef  call    cs:__imp_VariantClear
0x180010bf5  mov     qword ptr [rdi+4], 0
0x180010bfd  mov     [rdi], esi
0x180010bff  xor     ebx, ebx
0x180010c01  mov     [r14], rdi
0x180010c04  mov     eax, ebx
0x180010c06  mov     rbx, [rsp+58h+arg_10]
0x180010c0b  add     rsp, 40h
0x180010c0f  pop     r14
0x180010c11  pop     rdi
0x180010c12  pop     rsi
0x180010c13  retn
```
