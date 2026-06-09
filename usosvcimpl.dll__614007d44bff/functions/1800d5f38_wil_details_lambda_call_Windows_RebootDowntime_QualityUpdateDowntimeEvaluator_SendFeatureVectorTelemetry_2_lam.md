# wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___

- ea: `0x1800d5f38`
- end: `0x1800d5f9d`
- name: `wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___`
- size: `101`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800d4e08`
- `0x1800d7bf4`
- `0x1800d8a18`
- `0x1800d9aa4`
- `0x1800f0541`
- `0x1800f06ee`

## callees

- `0x1800d5f38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5f8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5f8c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5f76`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5f76`

## pseudocode

```c
void __fastcall wil::details::lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___::_lambda_call__Windows::RebootDowntime::QualityUpdateDowntimeEvaluator::SendFeatureVectorTelemetry_::_2_::_lambda_4___(
        __int64 a1)
{
  unsigned int i; // edi
  OLECHAR *v3; // rcx

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    if ( **(_QWORD **)a1 )
    {
      for ( i = 0; i < **(_DWORD **)(a1 + 8); ++i )
      {
        v3 = *(OLECHAR **)(**(_QWORD **)a1 + 16LL * i);
        if ( v3 )
          SysFreeString(v3);
      }
      CoTaskMemFree(**(LPVOID **)a1);
    }
  }
}

```

## disassembly

```asm
0x1800d5f38  mov     [rsp+arg_0], rbx
0x1800d5f3d  push    rdi
0x1800d5f3e  sub     rsp, 20h
0x1800d5f42  cmp     byte ptr [rcx+10h], 0
0x1800d5f46  mov     rbx, rcx
0x1800d5f49  jz      short loc_1800D5F92
0x1800d5f4b  mov     byte ptr [rcx+10h], 0
0x1800d5f4f  mov     rax, [rcx]
0x1800d5f52  cmp     qword ptr [rax], 0
0x1800d5f56  jz      short loc_1800D5F92
0x1800d5f58  mov     rax, [rcx+8]
0x1800d5f5c  xor     edi, edi
0x1800d5f5e  cmp     [rax], edi
0x1800d5f60  jbe     short loc_1800D5F86
0x1800d5f62  mov     rax, [rbx]
0x1800d5f65  mov     edx, edi
0x1800d5f67  add     rdx, rdx
0x1800d5f6a  mov     rcx, [rax]
0x1800d5f6d  mov     rcx, [rcx+rdx*8]; bstrString
0x1800d5f71  test    rcx, rcx
0x1800d5f74  jz      short loc_1800D5F7C
0x1800d5f76  call    cs:__imp_SysFreeString
0x1800d5f7c  mov     rax, [rbx+8]
0x1800d5f80  inc     edi
0x1800d5f82  cmp     edi, [rax]
0x1800d5f84  jb      short loc_1800D5F62
0x1800d5f86  mov     rcx, [rbx]
0x1800d5f89  mov     rcx, [rcx]; pv
0x1800d5f8c  call    cs:__imp_CoTaskMemFree
0x1800d5f92  mov     rbx, [rsp+28h+arg_0]
0x1800d5f97  add     rsp, 20h
0x1800d5f9b  pop     rdi
0x1800d5f9c  retn
```
