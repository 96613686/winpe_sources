# PolicyTransforms::GetPauseQualityUpdatesEndTime(tagEnterprisePolicyValue_V1 *)

- ea: `0x180017b30`
- end: `0x180017bbb`
- name: `?GetPauseQualityUpdatesEndTime@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x180010ae0`
- `0x180017994`
- `0x180017b30`
- `0x18001f09c`
- `0x18003002c`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::GetPauseQualityUpdatesEndTime(struct tagEnterprisePolicyValue_V1 *a1)
{
  bool v2; // si
  unsigned int v3; // edx
  int PolicyWithFallback; // edi
  void *Block; // [rsp+20h] [rbp-18h] BYREF

  v2 = 1;
  if ( *((_DWORD *)a1 + 2) != 1 )
    v2 = *((_DWORD *)a1 + 2) == 2;
  Block = 0;
  PolicyWithFallback = EnterprisePolicyReader::ReadPolicyWithFallback(0xDu, (__int64 *)&Block);
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
0x180017b30  mov     [rsp+arg_8], rbp
0x180017b35  mov     [rsp+arg_10], rsi
0x180017b3a  push    rdi
0x180017b3b  sub     rsp, 30h
0x180017b3f  mov     rbp, rcx
0x180017b42  mov     esi, 1
0x180017b47  cmp     [rcx+8], esi
0x180017b4a  jz      short loc_180017B55
0x180017b4c  cmp     dword ptr [rcx+8], 2
0x180017b50  jz      short loc_180017B55
0x180017b52  xor     sil, sil
0x180017b55  mov     [rsp+38h+Block], 0
0x180017b5e  lea     rdx, [rsp+38h+Block]
0x180017b63  mov     ecx, 0Dh
0x180017b68  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x180017b6d  mov     edi, eax
0x180017b6f  test    eax, eax
0x180017b71  js      short loc_180017B92
0x180017b73  mov     r9b, sil; bool
0x180017b76  mov     r8, rbp; struct tagEnterprisePolicyValue_V1 *
0x180017b79  mov     rcx, [rsp+38h+Block]; struct tagEnterprisePolicyValue_V1 *
0x180017b7e  call    ?GetPauseUpdatesEndTime@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@K0_N@Z; PolicyTransforms::GetPauseUpdatesEndTime(tagEnterprisePolicyValue_V1 *,ulong,tagEnterprisePolicyValue_V1 *,bool)
0x180017b83  mov     edi, eax
0x180017b85  test    eax, eax
0x180017b87  js      short loc_180017B92
0x180017b89  mov     rcx, rbp; struct tagUpdatePolicyValue_V1 *
0x180017b8c  call    ?IsPolicyConfiguredAndEnabled@PolicyHelpers@@SAHPEAUtagUpdatePolicyValue_V1@@@Z; PolicyHelpers::IsPolicyConfiguredAndEnabled(tagUpdatePolicyValue_V1 *)
0x180017b91  nop
0x180017b92  cmp     [rsp+38h+Block], 0
0x180017b98  jz      short loc_180017BA9
0x180017b9a  mov     edx, 30h ; '0'
0x180017b9f  mov     rcx, [rsp+38h+Block]; Block
0x180017ba4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017ba9  mov     eax, edi
0x180017bab  mov     rbp, [rsp+38h+arg_8]
0x180017bb0  mov     rsi, [rsp+38h+arg_10]
0x180017bb5  add     rsp, 30h
0x180017bb9  pop     rdi
0x180017bba  retn
```
