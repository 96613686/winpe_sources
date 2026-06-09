# wil_details_IsEnabledFallback

- ea: `0x18000b830`
- end: `0x18000b8af`
- name: `wil_details_IsEnabledFallback`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180006608`
- `0x18000661c`

## callees

- `0x18000b280`
- `0x18000b48c`
- `0x18000b5a4`
- `0x18000b830`

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
    wil_details_FeatureReporting_ReportUsageToService((__int64)a3, v6, a2, 1);
    if ( (unsigned int)(a2 - 3) <= 1 )
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v6, a2, (__int64)a3);
  }
  return v5 & 1;
}

```

## disassembly

```asm
0x18000b830  push    rbx
0x18000b832  push    rsi
0x18000b833  push    rdi
0x18000b834  push    r14
0x18000b836  sub     rsp, 28h
0x18000b83a  mov     [rsp+48h+arg_0], 0
0x18000b843  mov     r14, r8
0x18000b846  mov     dword ptr [rsp+48h+arg_0], ecx
0x18000b84a  mov     esi, edx
0x18000b84c  mov     rbx, rcx
0x18000b84f  test    cl, 2
0x18000b852  jnz     short loc_18000B86D
0x18000b854  mov     rdx, rcx
0x18000b857  mov     rcx, [r8]
0x18000b85a  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x18000b85f  mov     [rsp+48h+arg_0], rax
0x18000b864  mov     rdi, rax
0x18000b867  mov     ebx, dword ptr [rsp+48h+arg_0]
0x18000b86b  jmp     short loc_18000B872
0x18000b86d  mov     rdi, [rsp+48h+arg_0]
0x18000b872  test    esi, esi
0x18000b874  jz      short loc_18000B89F
0x18000b876  mov     r9d, 1
0x18000b87c  mov     r8d, esi
0x18000b87f  mov     rdx, rdi
0x18000b882  mov     rcx, r14
0x18000b885  call    wil_details_FeatureReporting_ReportUsageToService
0x18000b88a  lea     eax, [rsi-3]
0x18000b88d  cmp     eax, 1
0x18000b890  ja      short loc_18000B89F
0x18000b892  mov     r8, r14
0x18000b895  mov     edx, esi
0x18000b897  mov     rcx, rdi
0x18000b89a  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x18000b89f  and     ebx, 1
0x18000b8a2  mov     eax, ebx
0x18000b8a4  add     rsp, 28h
0x18000b8a8  pop     r14
0x18000b8aa  pop     rdi
0x18000b8ab  pop     rsi
0x18000b8ac  pop     rbx
0x18000b8ad  retn
```
