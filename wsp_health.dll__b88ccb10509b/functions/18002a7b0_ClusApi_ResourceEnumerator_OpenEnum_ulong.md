# ClusApi::ResourceEnumerator::OpenEnum(ulong)

- ea: `0x18002a7b0`
- end: `0x18002a827`
- name: `?OpenEnum@ResourceEnumerator@ClusApi@@MEAAKK@Z`
- size: `119`
- prototype: `unsigned int(ClusApi::ResourceEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180029cd8`
- `0x18002a7b0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a80d`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18002a7ed`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18002a7ed`

## pseudocode

```c
__int64 __fastcall ClusApi::ResourceEnumerator::OpenEnum(ClusApi::ResourceEnumerator *this, DWORD a2)
{
  HRESENUM *v2; // rsi
  unsigned int v3; // edi
  struct _HRESOURCE *v5; // rax
  HRESENUM v6; // rbx

  v2 = (HRESENUM *)((char *)this + 96);
  v3 = 0;
  if ( ((*((_QWORD *)this + 12) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = (struct _HRESOURCE *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 336LL))(*((_QWORD *)this + 13));
    v6 = ClusterResourceOpenEnum(v5, a2);
    cxl::AutoHandle<_HRESENUM *,unsigned long,&unsigned long ClusterResourceCloseEnum(_HRESENUM *),0>::Close(v2);
    *v2 = v6;
    if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x18002a7b0  mov     [rsp+arg_0], rbx
0x18002a7b5  mov     [rsp+arg_8], rsi
0x18002a7ba  push    rdi
0x18002a7bb  sub     rsp, 20h
0x18002a7bf  lea     rsi, [rcx+60h]
0x18002a7c3  xor     edi, edi
0x18002a7c5  mov     rax, [rsi]
0x18002a7c8  mov     ebx, edx
0x18002a7ca  inc     rax
0x18002a7cd  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a7d3  jnz     short loc_18002A815
0x18002a7d5  mov     rcx, [rcx+68h]
0x18002a7d9  mov     rax, [rcx]
0x18002a7dc  mov     rax, [rax+150h]
0x18002a7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7e8  mov     rcx, rax; hResource
0x18002a7eb  mov     edx, ebx; dwType
0x18002a7ed  call    cs:__imp_ClusterResourceOpenEnum
0x18002a7f3  mov     rcx, rsi
0x18002a7f6  mov     rbx, rax
0x18002a7f9  call    ?Close@?$AutoHandle@PEAU_HRESENUM@@K$1?ClusterResourceCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESENUM *,ulong,&ClusterResourceCloseEnum(_HRESENUM *),0>::Close(void)
0x18002a7fe  lea     rax, [rbx+1]
0x18002a802  mov     [rsi], rbx
0x18002a805  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a80b  jnz     short loc_18002A815
0x18002a80d  call    cs:__imp_GetLastError
0x18002a813  mov     edi, eax
0x18002a815  mov     rbx, [rsp+28h+arg_0]
0x18002a81a  mov     eax, edi
0x18002a81c  mov     rsi, [rsp+28h+arg_8]
0x18002a821  add     rsp, 20h
0x18002a825  pop     rdi
0x18002a826  retn
```
