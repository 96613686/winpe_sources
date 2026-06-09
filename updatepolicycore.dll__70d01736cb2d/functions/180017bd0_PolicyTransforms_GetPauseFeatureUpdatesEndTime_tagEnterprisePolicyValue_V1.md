# PolicyTransforms::GetPauseFeatureUpdatesEndTime(tagEnterprisePolicyValue_V1 *)

- ea: `0x180017bd0`
- end: `0x180017c5b`
- name: `?GetPauseFeatureUpdatesEndTime@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x180010ae0`
- `0x180017994`
- `0x180017bd0`
- `0x18001f09c`
- `0x18003002c`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::GetPauseFeatureUpdatesEndTime(struct tagEnterprisePolicyValue_V1 *a1)
{
  bool v2; // si
  unsigned int v3; // edx
  int PolicyWithFallback; // edi
  void *Block; // [rsp+20h] [rbp-18h] BYREF

  v2 = 1;
  if ( *((_DWORD *)a1 + 2) != 1 )
    v2 = *((_DWORD *)a1 + 2) == 2;
  Block = 0;
  PolicyWithFallback = EnterprisePolicyReader::ReadPolicyWithFallback(0xEu, (__int64 *)&Block);
  if ( PolicyWithFallback >= 0 )
  {
    PolicyWithFallback = PolicyTransforms::GetPauseUpdatesEndTime(
                           (struct tagEnterprisePolicyValue_V1 *)Block,
                           v3,
                           a1,
                           v2);
    if ( PolicyWithFallback >= 0 )
      PolicyHelpers::IsPolicyConfiguredAndEnabled(a1);
  }
  if ( Block )
    operator delete(Block);
  return (unsigned int)PolicyWithFallback;
}

```

## disassembly

```asm
0x180017bd0  mov     [rsp+arg_8], rbp
0x180017bd5  mov     [rsp+arg_10], rsi
0x180017bda  push    rdi
0x180017bdb  sub     rsp, 30h
0x180017bdf  mov     rbp, rcx
0x180017be2  mov     esi, 1
0x180017be7  cmp     [rcx+8], esi
0x180017bea  jz      short loc_180017BF5
0x180017bec  cmp     dword ptr [rcx+8], 2
0x180017bf0  jz      short loc_180017BF5
0x180017bf2  xor     sil, sil
0x180017bf5  mov     [rsp+38h+Block], 0
0x180017bfe  lea     rdx, [rsp+38h+Block]
0x180017c03  mov     ecx, 0Eh
0x180017c08  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x180017c0d  mov     edi, eax
0x180017c0f  test    eax, eax
0x180017c11  js      short loc_180017C32
0x180017c13  mov     r9b, sil; bool
0x180017c16  mov     r8, rbp; struct tagEnterprisePolicyValue_V1 *
0x180017c19  mov     rcx, [rsp+38h+Block]; struct tagEnterprisePolicyValue_V1 *
0x180017c1e  call    ?GetPauseUpdatesEndTime@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@K0_N@Z; PolicyTransforms::GetPauseUpdatesEndTime(tagEnterprisePolicyValue_V1 *,ulong,tagEnterprisePolicyValue_V1 *,bool)
0x180017c23  mov     edi, eax
0x180017c25  test    eax, eax
0x180017c27  js      short loc_180017C32
0x180017c29  mov     rcx, rbp; struct tagUpdatePolicyValue_V1 *
0x180017c2c  call    ?IsPolicyConfiguredAndEnabled@PolicyHelpers@@SAHPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::IsPolicyConfiguredAndEnabled(tagUpdatePolicyValue_V1 *)
0x180017c31  nop
0x180017c32  cmp     [rsp+38h+Block], 0
0x180017c38  jz      short loc_180017C49
0x180017c3a  mov     edx, 30h ; '0'
0x180017c3f  mov     rcx, [rsp+38h+Block]; Block
0x180017c44  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017c49  mov     eax, edi
0x180017c4b  mov     rbp, [rsp+38h+arg_8]
0x180017c50  mov     rsi, [rsp+38h+arg_10]
0x180017c55  add     rsp, 30h
0x180017c59  pop     rdi
0x180017c5a  retn
```
