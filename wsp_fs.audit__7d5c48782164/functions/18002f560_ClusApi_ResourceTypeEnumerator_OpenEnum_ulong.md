# ClusApi::ResourceTypeEnumerator::OpenEnum(ulong)

- ea: `0x18002f560`
- end: `0x18002f5f0`
- name: `?OpenEnum@ResourceTypeEnumerator@ClusApi@@MEAAKK@Z`
- size: `144`
- prototype: `unsigned int(ClusApi::ResourceTypeEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e14c`
- `0x18002e8f4`
- `0x18002f560`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5d6`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x18002f5b0`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x18002f5b0`

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
0x18002f560  push    rbx
0x18002f562  push    rbp
0x18002f563  push    rsi
0x18002f564  push    rdi
0x18002f565  sub     rsp, 28h
0x18002f569  lea     rsi, [rcx+80h]
0x18002f570  xor     edi, edi
0x18002f572  mov     rax, [rsi]
0x18002f575  mov     ebp, edx
0x18002f577  inc     rax
0x18002f57a  mov     r8, rcx
0x18002f57d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f583  jnz     short loc_18002F5E4
0x18002f585  add     rcx, 60h ; '`'
0x18002f589  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002f58e  mov     rcx, [r8+88h]
0x18002f595  mov     rbx, rax
0x18002f598  mov     rax, [rcx]
0x18002f59b  mov     rax, [rax+188h]
0x18002f5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5a7  mov     r8d, ebp; dwType
0x18002f5aa  mov     rdx, rbx; lpszResourceTypeName
0x18002f5ad  mov     rcx, rax; hCluster
0x18002f5b0  call    cs:__imp_ClusterResourceTypeOpenEnum
0x18002f5b7  nop     dword ptr [rax+rax+00h]
0x18002f5bc  mov     rcx, rsi
0x18002f5bf  mov     rbx, rax
0x18002f5c2  call    ?Close@?$AutoHandle@PEAU_HRESTYPEENUM@@K$1?ClusterResourceTypeCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESTYPEENUM *,ulong,&ClusterResourceTypeCloseEnum(_HRESTYPEENUM *),0>::Close(void)
0x18002f5c7  lea     rax, [rbx+1]
0x18002f5cb  mov     [rsi], rbx
0x18002f5ce  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f5d4  jnz     short loc_18002F5E4
0x18002f5d6  call    cs:__imp_GetLastError
0x18002f5dd  nop     dword ptr [rax+rax+00h]
0x18002f5e2  mov     edi, eax
0x18002f5e4  mov     eax, edi
0x18002f5e6  add     rsp, 28h
0x18002f5ea  pop     rdi
0x18002f5eb  pop     rsi
0x18002f5ec  pop     rbp
0x18002f5ed  pop     rbx
0x18002f5ee  retn
```
