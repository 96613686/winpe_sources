# wil_details_IsEnabledFallback

- ea: `0x1400176c0`
- end: `0x140017738`
- name: `wil_details_IsEnabledFallback`
- size: `120`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140012be8`
- `0x1400189fc`
- `0x140018a40`
- `0x14001ac34`

## callees

- `0x14001726c`
- `0x140017404`
- `0x14001751c`
- `0x1400176c0`

## pseudocode

```c
__int64 __fastcall wil_details_IsEnabledFallback(__int64 a1, int a2, volatile signed __int32 **a3)
{
  char v5; // bl
  __int64 v6; // rdi

  v5 = a1;
  if ( (a1 & 2) != 0 )
  {
    v6 = (unsigned int)a1;
  }
  else
  {
    v6 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*a3, a1, (__int64)a3);
    v5 = v6;
  }
  if ( a2 )
  {
    wil_details_FeatureReporting_ReportUsageToService((__int64)a3, v6, a2);
    if ( (unsigned int)(a2 - 3) <= 1 )
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v6, a2, (__int64)a3);
  }
  return v5 & 1;
}

```

## disassembly

```asm
0x1400176c0  push    rbx
0x1400176c2  push    rsi
0x1400176c3  push    rdi
0x1400176c4  push    r14
0x1400176c6  sub     rsp, 28h
0x1400176ca  mov     [rsp+48h+arg_0], 0
0x1400176d3  mov     r14, r8
0x1400176d6  mov     dword ptr [rsp+48h+arg_0], ecx
0x1400176da  mov     esi, edx
0x1400176dc  mov     rbx, rcx
0x1400176df  test    cl, 2
0x1400176e2  jnz     short loc_1400176FD
0x1400176e4  mov     rdx, rcx
0x1400176e7  mov     rcx, [r8]
0x1400176ea  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x1400176ef  mov     [rsp+48h+arg_0], rax
0x1400176f4  mov     rdi, rax
0x1400176f7  mov     ebx, dword ptr [rsp+48h+arg_0]
0x1400176fb  jmp     short loc_140017702
0x1400176fd  mov     rdi, [rsp+48h+arg_0]
0x140017702  test    esi, esi
0x140017704  jz      short loc_140017729
0x140017706  mov     r8d, esi
0x140017709  mov     rdx, rdi
0x14001770c  mov     rcx, r14
0x14001770f  call    wil_details_FeatureReporting_ReportUsageToService
0x140017714  lea     eax, [rsi-3]
0x140017717  cmp     eax, 1
0x14001771a  ja      short loc_140017729
0x14001771c  mov     r8, r14
0x14001771f  mov     edx, esi
0x140017721  mov     rcx, rdi
0x140017724  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140017729  and     ebx, 1
0x14001772c  mov     eax, ebx
0x14001772e  add     rsp, 28h
0x140017732  pop     r14
0x140017734  pop     rdi
0x140017735  pop     rsi
0x140017736  pop     rbx
0x140017737  retn
```
