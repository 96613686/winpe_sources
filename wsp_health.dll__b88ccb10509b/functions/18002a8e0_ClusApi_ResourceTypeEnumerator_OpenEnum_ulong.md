# ClusApi::ResourceTypeEnumerator::OpenEnum(ulong)

- ea: `0x18002a8e0`
- end: `0x18002a963`
- name: `?OpenEnum@ResourceTypeEnumerator@ClusApi@@MEAAKK@Z`
- size: `131`
- prototype: `unsigned int(ClusApi::ResourceTypeEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000d618`
- `0x180029d38`
- `0x18002a8e0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a950`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x18002a930`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x18002a930`

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
0x18002a8e0  push    rbx
0x18002a8e2  push    rbp
0x18002a8e3  push    rsi
0x18002a8e4  push    rdi
0x18002a8e5  sub     rsp, 28h
0x18002a8e9  lea     rsi, [rcx+80h]
0x18002a8f0  xor     edi, edi
0x18002a8f2  mov     rax, [rsi]
0x18002a8f5  mov     ebp, edx
0x18002a8f7  inc     rax
0x18002a8fa  mov     r8, rcx
0x18002a8fd  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a903  jnz     short loc_18002A958
0x18002a905  add     rcx, 60h ; '`'
0x18002a909  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002a90e  mov     rcx, [r8+88h]
0x18002a915  mov     rbx, rax
0x18002a918  mov     rax, [rcx]
0x18002a91b  mov     rax, [rax+188h]
0x18002a922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a927  mov     r8d, ebp; dwType
0x18002a92a  mov     rdx, rbx; lpszResourceTypeName
0x18002a92d  mov     rcx, rax; hCluster
0x18002a930  call    cs:__imp_ClusterResourceTypeOpenEnum
0x18002a936  mov     rcx, rsi
0x18002a939  mov     rbx, rax
0x18002a93c  call    ?Close@?$AutoHandle@PEAU_HRESTYPEENUM@@K$1?ClusterResourceTypeCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESTYPEENUM *,ulong,&ClusterResourceTypeCloseEnum(_HRESTYPEENUM *),0>::Close(void)
0x18002a941  lea     rax, [rbx+1]
0x18002a945  mov     [rsi], rbx
0x18002a948  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a94e  jnz     short loc_18002A958
0x18002a950  call    cs:__imp_GetLastError
0x18002a956  mov     edi, eax
0x18002a958  mov     eax, edi
0x18002a95a  add     rsp, 28h
0x18002a95e  pop     rdi
0x18002a95f  pop     rsi
0x18002a960  pop     rbp
0x18002a961  pop     rbx
0x18002a962  retn
```
