# CLoggedOnPropStore::~CLoggedOnPropStore(void)

- ea: `0x1800075b0`
- end: `0x18000767d`
- name: `??1CLoggedOnPropStore@@AEAA@XZ`
- size: `205`
- prototype: `void __fastcall(CLoggedOnPropStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009b20`

## callees

- `0x1800075b0`
- `0x1800140ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000761a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000762e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000764c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007665`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000761a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000762e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000764c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007665`

## pseudocode

```c
void __fastcall CLoggedOnPropStore::~CLoggedOnPropStore(CLoggedOnPropStore *this)
{
  __int64 v1; // rdi
  void *v3; // rcx
  void *v4; // rcx

  v1 = *((_QWORD *)this + 4);
  *(_QWORD *)this = &CLoggedOnPropStore::`vftable'{for `IPropertyStore'};
  *((_QWORD *)this + 1) = &CLoggedOnPropStore::`vftable'{for `IPersistSerializedPropStorage'};
  if ( v1 )
  {
    _FreeUnicodeString((struct _UNICODE_STRING *)(v1 + 16));
    _FreeUnicodeString((struct _UNICODE_STRING *)(v1 + 32));
    _FreeUnicodeString((struct _UNICODE_STRING *)(v1 + 48));
    _FreeUnicodeString((struct _UNICODE_STRING *)(v1 + 88));
    _FreeUnicodeString((struct _UNICODE_STRING *)(v1 + 104));
    _FreeUnicodeString((struct _UNICODE_STRING *)(v1 + 120));
    v3 = *(void **)(v1 + 72);
    if ( v3 )
      CoTaskMemFree(v3);
  }
  CoTaskMemFree(*((LPVOID *)this + 3));
  CoTaskMemFree(*((LPVOID *)this + 5));
  CoTaskMemFree(*((LPVOID *)this + 6));
  CoTaskMemFree(*((LPVOID *)this + 9));
  CoTaskMemFree(*((LPVOID *)this + 10));
  CoTaskMemFree(*((LPVOID *)this + 11));
  v4 = (void *)*((_QWORD *)this + 12);
  if ( v4 )
    CoTaskMemFree(v4);
  _InterlockedDecrement(&g_cRefCount);
}

```

## disassembly

```asm
0x1800075b0  mov     [rsp+arg_0], rbx
0x1800075b5  push    rdi
0x1800075b6  sub     rsp, 20h
0x1800075ba  mov     rdi, [rcx+20h]
0x1800075be  lea     rax, ??_7CLoggedOnPropStore@@6BIPropertyStore@@@; const CLoggedOnPropStore::`vftable'{for `IPropertyStore'}
0x1800075c5  mov     [rcx], rax
0x1800075c8  lea     rax, ??_7CLoggedOnPropStore@@6BIPersistSerializedPropStorage@@@; const CLoggedOnPropStore::`vftable'{for `IPersistSerializedPropStorage'}
0x1800075cf  mov     [rcx+8], rax
0x1800075d3  mov     rbx, rcx
0x1800075d6  test    rdi, rdi
0x1800075d9  jz      short loc_180007620
0x1800075db  lea     rcx, [rdi+10h]; struct _UNICODE_STRING *
0x1800075df  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x1800075e4  lea     rcx, [rdi+20h]; struct _UNICODE_STRING *
0x1800075e8  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x1800075ed  lea     rcx, [rdi+30h]; struct _UNICODE_STRING *
0x1800075f1  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x1800075f6  lea     rcx, [rdi+58h]; struct _UNICODE_STRING *
0x1800075fa  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x1800075ff  lea     rcx, [rdi+68h]; struct _UNICODE_STRING *
0x180007603  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x180007608  lea     rcx, [rdi+78h]; struct _UNICODE_STRING *
0x18000760c  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x180007611  mov     rcx, [rdi+48h]; pv
0x180007615  test    rcx, rcx
0x180007618  jz      short loc_180007620
0x18000761a  call    cs:__imp_CoTaskMemFree
0x180007620  mov     rcx, [rbx+18h]; pv
0x180007624  call    cs:__imp_CoTaskMemFree
0x18000762a  mov     rcx, [rbx+28h]; pv
0x18000762e  call    cs:__imp_CoTaskMemFree
0x180007634  mov     rcx, [rbx+30h]; pv
0x180007638  call    cs:__imp_CoTaskMemFree
0x18000763e  mov     rcx, [rbx+48h]; pv
0x180007642  call    cs:__imp_CoTaskMemFree
0x180007648  mov     rcx, [rbx+50h]; pv
0x18000764c  call    cs:__imp_CoTaskMemFree
0x180007652  mov     rcx, [rbx+58h]; pv
0x180007656  call    cs:__imp_CoTaskMemFree
0x18000765c  mov     rcx, [rbx+60h]; pv
0x180007660  test    rcx, rcx
0x180007663  jz      short loc_18000766B
0x180007665  call    cs:__imp_CoTaskMemFree
0x18000766b  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x180007672  mov     rbx, [rsp+28h+arg_0]
0x180007677  add     rsp, 20h
0x18000767b  pop     rdi
0x18000767c  retn
```
