# CDataTransferBroker::_CleanupExtensionsAndDataFormats(void)

- ea: `0x18006d0e8`
- end: `0x18006d158`
- name: `?_CleanupExtensionsAndDataFormats@CDataTransferBroker@@AEAAXXZ`
- size: `112`
- prototype: `void __fastcall(CDataTransferBroker *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005e6e8`
- `0x18006c570`

## callees

- `0x180020e10`
- `0x18006d0e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006d10b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006d131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006d10b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006d131`

## pseudocode

```c
void __fastcall CDataTransferBroker::_CleanupExtensionsAndDataFormats(CDataTransferBroker *this)
{
  char *v1; // rsi
  LPVOID *v3; // rbx
  LPVOID *v4; // rdi
  char *v5; // rdi
  LPVOID *v6; // rbx
  LPVOID *v7; // rbp

  v1 = (char *)this + 256;
  v3 = (LPVOID *)*((_QWORD *)this + 32);
  v4 = &v3[*((_QWORD *)this + 33)];
  while ( v3 != v4 )
    CoTaskMemFree(*v3++);
  v5 = (char *)this + 288;
  v6 = (LPVOID *)*((_QWORD *)this + 36);
  v7 = &v6[*((_QWORD *)this + 37)];
  while ( v6 != v7 )
    CoTaskMemFree(*v6++);
  CTSimpleArray<CServiceHostComponent::ISC_SERVICE,4294967294,CTPolicyCoTaskMem<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardCompareHelper<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardMergeHelper<CServiceHostComponent::ISC_SERVICE>>::RemoveAll(v1);
  CTSimpleArray<CServiceHostComponent::ISC_SERVICE,4294967294,CTPolicyCoTaskMem<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardCompareHelper<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardMergeHelper<CServiceHostComponent::ISC_SERVICE>>::RemoveAll(v5);
}

```

## disassembly

```asm
0x18006d0e8  push    rbx
0x18006d0ea  push    rbp
0x18006d0eb  push    rsi
0x18006d0ec  push    rdi
0x18006d0ed  sub     rsp, 28h
0x18006d0f1  lea     rsi, [rcx+100h]
0x18006d0f8  mov     rbp, rcx
0x18006d0fb  mov     rbx, [rsi]
0x18006d0fe  mov     rax, [rsi+8]
0x18006d102  lea     rdi, [rbx+rax*8]
0x18006d106  jmp     short loc_18006D115
0x18006d108  mov     rcx, [rbx]; pv
0x18006d10b  call    cs:__imp_CoTaskMemFree
0x18006d111  add     rbx, 8
0x18006d115  cmp     rbx, rdi
0x18006d118  jnz     short loc_18006D108
0x18006d11a  lea     rdi, [rbp+120h]
0x18006d121  mov     rbx, [rdi]
0x18006d124  mov     rax, [rdi+8]
0x18006d128  lea     rbp, [rbx+rax*8]
0x18006d12c  jmp     short loc_18006D13B
0x18006d12e  mov     rcx, [rbx]; pv
0x18006d131  call    cs:__imp_CoTaskMemFree
0x18006d137  add     rbx, 8
0x18006d13b  cmp     rbx, rbp
0x18006d13e  jnz     short loc_18006D12E
0x18006d140  mov     rcx, rsi
0x18006d143  call    ?RemoveAll@?$CTSimpleArray@UISC_SERVICE@CServiceHostComponent@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UISC_SERVICE@CServiceHostComponent@@@@V?$CSimpleArrayStandardCompareHelper@UISC_SERVICE@CServiceHostComponent@@@@V?$CSimpleArrayStandardMergeHelper@UISC_SERVICE@CServiceHostComponent@@@@@@QEAAXXZ; CTSimpleArray<CServiceHostComponent::ISC_SERVICE,4294967294,CTPolicyCoTaskMem<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardCompareHelper<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardMergeHelper<CServiceHostComponent::ISC_SERVICE>>::RemoveAll(void)
0x18006d148  mov     rcx, rdi
0x18006d14b  add     rsp, 28h
0x18006d14f  pop     rdi
0x18006d150  pop     rsi
0x18006d151  pop     rbp
0x18006d152  pop     rbx
0x18006d153  jmp     ?RemoveAll@?$CTSimpleArray@UISC_SERVICE@CServiceHostComponent@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UISC_SERVICE@CServiceHostComponent@@@@V?$CSimpleArrayStandardCompareHelper@UISC_SERVICE@CServiceHostComponent@@@@V?$CSimpleArrayStandardMergeHelper@UISC_SERVICE@CServiceHostComponent@@@@@@QEAAXXZ; CTSimpleArray<CServiceHostComponent::ISC_SERVICE,4294967294,CTPolicyCoTaskMem<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardCompareHelper<CServiceHostComponent::ISC_SERVICE>,CSimpleArrayStandardMergeHelper<CServiceHostComponent::ISC_SERVICE>>::RemoveAll(void)
```
