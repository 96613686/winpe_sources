# Windows::ActionDeferredDurationEvaluator::CleanupFeatureMapContext(Windows::ActionDeferredDurationEvaluator::FeatureMapContext &)

- ea: `0x1800c3b68`
- end: `0x1800c3bc2`
- name: `?CleanupFeatureMapContext@ActionDeferredDurationEvaluator@Windows@@YAXAEAUFeatureMapContext@12@@Z`
- size: `90`
- prototype: `void __fastcall(Windows::ActionDeferredDurationEvaluator *__hidden this, struct Windows::ActionDeferredDurationEvaluator::FeatureMapContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c3bc8`
- `0x1800c4b74`

## callees

- `0x1800c3b68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3ba3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c3b93`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c3b93`

## pseudocode

```c
void __fastcall Windows::ActionDeferredDurationEvaluator::CleanupFeatureMapContext(
        Windows::ActionDeferredDurationEvaluator *this,
        struct Windows::ActionDeferredDurationEvaluator::FeatureMapContext *a2)
{
  unsigned int i; // edi
  OLECHAR *v4; // rcx

  if ( *(_QWORD *)this )
  {
    for ( i = 0; i < *((_DWORD *)this + 2); ++i )
    {
      v4 = *(OLECHAR **)(*(_QWORD *)this + 16LL * i);
      if ( v4 )
        SysFreeString(v4);
    }
    CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x1800c3b68  mov     [rsp+arg_0], rbx
0x1800c3b6d  push    rdi
0x1800c3b6e  sub     rsp, 20h
0x1800c3b72  cmp     qword ptr [rcx], 0
0x1800c3b76  mov     rbx, rcx
0x1800c3b79  jz      short loc_1800C3BB7
0x1800c3b7b  xor     edi, edi
0x1800c3b7d  cmp     [rcx+8], edi
0x1800c3b80  jbe     short loc_1800C3BA0
0x1800c3b82  mov     rax, [rbx]
0x1800c3b85  mov     edx, edi
0x1800c3b87  add     rdx, rdx
0x1800c3b8a  mov     rcx, [rax+rdx*8]; bstrString
0x1800c3b8e  test    rcx, rcx
0x1800c3b91  jz      short loc_1800C3B99
0x1800c3b93  call    cs:__imp_SysFreeString
0x1800c3b99  inc     edi
0x1800c3b9b  cmp     edi, [rbx+8]
0x1800c3b9e  jb      short loc_1800C3B82
0x1800c3ba0  mov     rcx, [rbx]; pv
0x1800c3ba3  call    cs:__imp_CoTaskMemFree
0x1800c3ba9  mov     qword ptr [rbx], 0
0x1800c3bb0  mov     dword ptr [rbx+8], 0
0x1800c3bb7  mov     rbx, [rsp+28h+arg_0]
0x1800c3bbc  add     rsp, 20h
0x1800c3bc0  pop     rdi
0x1800c3bc1  retn
```
