# CShellLink::_ResetPersistData(void)

- ea: `0x1801d84d0`
- end: `0x1801d8659`
- name: `?_ResetPersistData@CShellLink@@AEAAXXZ`
- size: `393`
- prototype: `void __fastcall(CShellLink *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801052c0`
- `0x1801d7930`
- `0x1801d7970`
- `0x1801d7d50`
- `0x1801d8160`
- `0x180251bf4`
- `0x180288ca0`
- `0x1806235e0`

## callees

- `0x180106520`
- `0x1801d84d0`
- `0x180563064`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d8520`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d8520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d84ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d855c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d85aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d85c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d84ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d855c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d85aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d85c4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFreeDataBlockList` at `0x1801d85e3`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFreeDataBlockList` at `0x1801d85e3`

## pseudocode

```c
void __fastcall CShellLink::_ResetPersistData(CShellLink *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rcx

  v2 = (void *)_InterlockedExchange64((volatile __int64 *)this + 47, 0);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)_InterlockedExchange64((volatile __int64 *)this + 48, 0);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 49);
  if ( v4 )
  {
    LocalFree(v4);
    *((_QWORD *)this + 49) = 0;
  }
  CShellLink::_ClearTrackerData(this);
  CoTaskMemFree(*((LPVOID *)this + 50));
  v5 = (void *)*((_QWORD *)this + 51);
  *((_QWORD *)this + 50) = 0;
  CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 52);
  *((_QWORD *)this + 51) = 0;
  CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 53);
  *((_QWORD *)this + 52) = 0;
  CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)this + 54);
  *((_QWORD *)this + 53) = 0;
  CoTaskMemFree(v8);
  v9 = (void *)*((_QWORD *)this + 70);
  *((_QWORD *)this + 54) = 0;
  CoTaskMemFree(v9);
  v10 = *((_QWORD *)this + 57);
  *((_QWORD *)this + 70) = 0;
  if ( v10 )
  {
    SHFreeDataBlockList();
    *((_QWORD *)this + 57) = 0;
  }
  *(_OWORD *)((char *)this + 476) = 0;
  *(_OWORD *)((char *)this + 492) = 0;
  *(_OWORD *)((char *)this + 508) = 0;
  *(_OWORD *)((char *)this + 524) = 0;
  *(_OWORD *)((char *)this + 536) = 0;
  *((_DWORD *)this + 134) = 1;
  *((_DWORD *)this + 138) = 0;
  *((_DWORD *)this + 146) = 2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55840883>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55840883>::GetImpl'::`2'::impl) )
    *((_BYTE *)this + 296) = 1;
}

```

## disassembly

```asm
0x1801d84d0  mov     [rsp+arg_0], rbx
0x1801d84d5  push    rdi
0x1801d84d6  sub     rsp, 20h
0x1801d84da  mov     rbx, rcx
0x1801d84dd  xor     edi, edi
0x1801d84df  mov     ecx, edi
0x1801d84e1  xchg    rcx, [rbx+178h]; pv
0x1801d84e8  test    rcx, rcx
0x1801d84eb  jz      short loc_1801D84F9
0x1801d84ed  call    cs:__imp_CoTaskMemFree
0x1801d84f4  nop     dword ptr [rax+rax+00h]
0x1801d84f9  mov     rcx, rdi
0x1801d84fc  xchg    rcx, [rbx+180h]; pv
0x1801d8503  test    rcx, rcx
0x1801d8506  jz      short loc_1801D8514
0x1801d8508  call    cs:__imp_CoTaskMemFree
0x1801d850f  nop     dword ptr [rax+rax+00h]
0x1801d8514  mov     rcx, [rbx+188h]; hMem
0x1801d851b  test    rcx, rcx
0x1801d851e  jz      short loc_1801D8533
0x1801d8520  call    cs:__imp_LocalFree
0x1801d8527  nop     dword ptr [rax+rax+00h]
0x1801d852c  mov     [rbx+188h], rdi
0x1801d8533  mov     rcx, rbx; this
0x1801d8536  call    ?_ClearTrackerData@CShellLink@@AEAAXXZ; CShellLink::_ClearTrackerData(void)
0x1801d853b  mov     rcx, [rbx+190h]; pv
0x1801d8542  call    cs:__imp_CoTaskMemFree
0x1801d8549  nop     dword ptr [rax+rax+00h]
0x1801d854e  mov     rcx, [rbx+198h]; pv
0x1801d8555  mov     [rbx+190h], rdi
0x1801d855c  call    cs:__imp_CoTaskMemFree
0x1801d8563  nop     dword ptr [rax+rax+00h]
0x1801d8568  mov     rcx, [rbx+1A0h]; pv
0x1801d856f  mov     [rbx+198h], rdi
0x1801d8576  call    cs:__imp_CoTaskMemFree
0x1801d857d  nop     dword ptr [rax+rax+00h]
0x1801d8582  mov     rcx, [rbx+1A8h]; pv
0x1801d8589  mov     [rbx+1A0h], rdi
0x1801d8590  call    cs:__imp_CoTaskMemFree
0x1801d8597  nop     dword ptr [rax+rax+00h]
0x1801d859c  mov     rcx, [rbx+1B0h]; pv
0x1801d85a3  mov     [rbx+1A8h], rdi
0x1801d85aa  call    cs:__imp_CoTaskMemFree
0x1801d85b1  nop     dword ptr [rax+rax+00h]
0x1801d85b6  mov     rcx, [rbx+230h]; pv
0x1801d85bd  mov     [rbx+1B0h], rdi
0x1801d85c4  call    cs:__imp_CoTaskMemFree
0x1801d85cb  nop     dword ptr [rax+rax+00h]
0x1801d85d0  mov     rcx, [rbx+1C8h]
0x1801d85d7  mov     [rbx+230h], rdi
0x1801d85de  test    rcx, rcx
0x1801d85e1  jz      short loc_1801D85F6
0x1801d85e3  call    cs:__imp_SHFreeDataBlockList
0x1801d85ea  nop     dword ptr [rax+rax+00h]
0x1801d85ef  mov     [rbx+1C8h], rdi
0x1801d85f6  xorps   xmm0, xmm0
0x1801d85f9  movups  xmmword ptr [rbx+1DCh], xmm0
0x1801d8600  movups  xmmword ptr [rbx+1ECh], xmm0
0x1801d8607  movups  xmmword ptr [rbx+1FCh], xmm0
0x1801d860e  movups  xmmword ptr [rbx+20Ch], xmm0
0x1801d8615  movups  xmmword ptr [rbx+218h], xmm0
0x1801d861c  mov     dword ptr [rbx+218h], 1
0x1801d8626  mov     [rbx+228h], edi
0x1801d862c  mov     dword ptr [rbx+248h], 2
0x1801d8636  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55840883@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55840883@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55840883> `wil::Feature<__WilFeatureTraits_Feature_55840883>::GetImpl(void)'::`2'::impl
0x1801d863d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55840883@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55840883>::__private_IsEnabled(void)
0x1801d8642  test    al, al
0x1801d8644  jz      short loc_1801D864D
0x1801d8646  mov     byte ptr [rbx+128h], 1
0x1801d864d  mov     rbx, [rsp+28h+arg_0]
0x1801d8652  add     rsp, 20h
0x1801d8656  pop     rdi
0x1801d8657  retn
```
