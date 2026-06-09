# ClusApi::ResourceTypeEnumerator::OpenEnum(ulong)

- ea: `0x18002e620`
- end: `0x18002e6a3`
- name: `?OpenEnum@ResourceTypeEnumerator@ClusApi@@MEAAKK@Z`
- size: `131`
- prototype: `unsigned int(ClusApi::ResourceTypeEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000dd74`
- `0x18002da78`
- `0x18002e620`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e690`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x18002e670`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x18002e670`

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
0x18002e620  push    rbx
0x18002e622  push    rbp
0x18002e623  push    rsi
0x18002e624  push    rdi
0x18002e625  sub     rsp, 28h
0x18002e629  lea     rsi, [rcx+80h]
0x18002e630  xor     edi, edi
0x18002e632  mov     rax, [rsi]
0x18002e635  mov     ebp, edx
0x18002e637  inc     rax
0x18002e63a  mov     r8, rcx
0x18002e63d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e643  jnz     short loc_18002E698
0x18002e645  add     rcx, 60h ; '`'
0x18002e649  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002e64e  mov     rcx, [r8+88h]
0x18002e655  mov     rbx, rax
0x18002e658  mov     rax, [rcx]
0x18002e65b  mov     rax, [rax+188h]
0x18002e662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e667  mov     r8d, ebp; dwType
0x18002e66a  mov     rdx, rbx; lpszResourceTypeName
0x18002e66d  mov     rcx, rax; hCluster
0x18002e670  call    cs:__imp_ClusterResourceTypeOpenEnum
0x18002e676  mov     rcx, rsi
0x18002e679  mov     rbx, rax
0x18002e67c  call    ?Close@?$AutoHandle@PEAU_HRESTYPEENUM@@K$1?ClusterResourceTypeCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESTYPEENUM *,ulong,&ClusterResourceTypeCloseEnum(_HRESTYPEENUM *),0>::Close(void)
0x18002e681  lea     rax, [rbx+1]
0x18002e685  mov     [rsi], rbx
0x18002e688  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e68e  jnz     short loc_18002E698
0x18002e690  call    cs:__imp_GetLastError
0x18002e696  mov     edi, eax
0x18002e698  mov     eax, edi
0x18002e69a  add     rsp, 28h
0x18002e69e  pop     rdi
0x18002e69f  pop     rsi
0x18002e6a0  pop     rbp
0x18002e6a1  pop     rbx
0x18002e6a2  retn
```
