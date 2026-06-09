# ClusApi::ResourceEnumerator::OpenEnum(ulong)

- ea: `0x18002e4f0`
- end: `0x18002e567`
- name: `?OpenEnum@ResourceEnumerator@ClusApi@@MEAAKK@Z`
- size: `119`
- prototype: `unsigned int(ClusApi::ResourceEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002da18`
- `0x18002e4f0`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e54d`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18002e52d`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18002e52d`

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
0x18002e4f0  mov     [rsp+arg_0], rbx
0x18002e4f5  mov     [rsp+arg_8], rsi
0x18002e4fa  push    rdi
0x18002e4fb  sub     rsp, 20h
0x18002e4ff  lea     rsi, [rcx+60h]
0x18002e503  xor     edi, edi
0x18002e505  mov     rax, [rsi]
0x18002e508  mov     ebx, edx
0x18002e50a  inc     rax
0x18002e50d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e513  jnz     short loc_18002E555
0x18002e515  mov     rcx, [rcx+68h]
0x18002e519  mov     rax, [rcx]
0x18002e51c  mov     rax, [rax+150h]
0x18002e523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e528  mov     rcx, rax; hResource
0x18002e52b  mov     edx, ebx; dwType
0x18002e52d  call    cs:__imp_ClusterResourceOpenEnum
0x18002e533  mov     rcx, rsi
0x18002e536  mov     rbx, rax
0x18002e539  call    ?Close@?$AutoHandle@PEAU_HRESENUM@@K$1?ClusterResourceCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESENUM *,ulong,&ClusterResourceCloseEnum(_HRESENUM *),0>::Close(void)
0x18002e53e  lea     rax, [rbx+1]
0x18002e542  mov     [rsi], rbx
0x18002e545  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e54b  jnz     short loc_18002E555
0x18002e54d  call    cs:__imp_GetLastError
0x18002e553  mov     edi, eax
0x18002e555  mov     rbx, [rsp+28h+arg_0]
0x18002e55a  mov     eax, edi
0x18002e55c  mov     rsi, [rsp+28h+arg_8]
0x18002e561  add     rsp, 20h
0x18002e565  pop     rdi
0x18002e566  retn
```
