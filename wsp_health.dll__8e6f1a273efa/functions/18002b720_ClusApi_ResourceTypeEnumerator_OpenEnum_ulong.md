# ClusApi::ResourceTypeEnumerator::OpenEnum(ulong)

- ea: `0x18002b720`
- end: `0x18002b7b0`
- name: `?OpenEnum@ResourceTypeEnumerator@ClusApi@@MEAAKK@Z`
- size: `144`
- prototype: `unsigned int(ClusApi::ResourceTypeEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000da34`
- `0x18002aab4`
- `0x18002b720`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b796`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x18002b770`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x18002b770`

## pseudocode

```c
__int64 __fastcall ClusApi::ResourceTypeEnumerator::OpenEnum(ClusApi::ResourceTypeEnumerator *this, DWORD a2)
{
  HRESTYPEENUM *v2; // rsi
  unsigned int v3; // edi
  __int64 v5; // r8
  const WCHAR *v6; // rbx
  struct _HCLUSTER *v7; // rax
  HRESTYPEENUM v8; // rbx

  v2 = (HRESTYPEENUM *)((char *)this + 128);
  v3 = 0;
  if ( ((*((_QWORD *)this + 16) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 96);
    v7 = (struct _HCLUSTER *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 136) + 392LL))(*(_QWORD *)(v5 + 136));
    v8 = ClusterResourceTypeOpenEnum(v7, v6, a2);
    cxl::AutoHandle<_HRESTYPEENUM *,unsigned long,&unsigned long ClusterResourceTypeCloseEnum(_HRESTYPEENUM *),0>::Close(v2);
    *v2 = v8;
    if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x18002b720  push    rbx
0x18002b722  push    rbp
0x18002b723  push    rsi
0x18002b724  push    rdi
0x18002b725  sub     rsp, 28h
0x18002b729  lea     rsi, [rcx+80h]
0x18002b730  xor     edi, edi
0x18002b732  mov     rax, [rsi]
0x18002b735  mov     ebp, edx
0x18002b737  inc     rax
0x18002b73a  mov     r8, rcx
0x18002b73d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b743  jnz     short loc_18002B7A4
0x18002b745  add     rcx, 60h ; '`'
0x18002b749  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b74e  mov     rcx, [r8+88h]
0x18002b755  mov     rbx, rax
0x18002b758  mov     rax, [rcx]
0x18002b75b  mov     rax, [rax+188h]
0x18002b762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b767  mov     r8d, ebp; dwType
0x18002b76a  mov     rdx, rbx; lpszResourceTypeName
0x18002b76d  mov     rcx, rax; hCluster
0x18002b770  call    cs:__imp_ClusterResourceTypeOpenEnum
0x18002b777  nop     dword ptr [rax+rax+00h]
0x18002b77c  mov     rcx, rsi
0x18002b77f  mov     rbx, rax
0x18002b782  call    ?Close@?$AutoHandle@PEAU_HRESTYPEENUM@@K$1?ClusterResourceTypeCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESTYPEENUM *,ulong,&ClusterResourceTypeCloseEnum(_HRESTYPEENUM *),0>::Close(void)
0x18002b787  lea     rax, [rbx+1]
0x18002b78b  mov     [rsi], rbx
0x18002b78e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b794  jnz     short loc_18002B7A4
0x18002b796  call    cs:__imp_GetLastError
0x18002b79d  nop     dword ptr [rax+rax+00h]
0x18002b7a2  mov     edi, eax
0x18002b7a4  mov     eax, edi
0x18002b7a6  add     rsp, 28h
0x18002b7aa  pop     rdi
0x18002b7ab  pop     rsi
0x18002b7ac  pop     rbp
0x18002b7ad  pop     rbx
0x18002b7ae  retn
```
