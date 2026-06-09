# ClusApi::ResourceEnumerator::OpenEnum(ulong)

- ea: `0x18002f410`
- end: `0x18002f494`
- name: `?OpenEnum@ResourceEnumerator@ClusApi@@MEAAKK@Z`
- size: `132`
- prototype: `unsigned int(ClusApi::ResourceEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e884`
- `0x18002f410`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f473`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18002f44d`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18002f44d`

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
0x18002f410  mov     [rsp+arg_0], rbx
0x18002f415  mov     [rsp+arg_8], rsi
0x18002f41a  push    rdi
0x18002f41b  sub     rsp, 20h
0x18002f41f  lea     rsi, [rcx+60h]
0x18002f423  xor     edi, edi
0x18002f425  mov     rax, [rsi]
0x18002f428  mov     ebx, edx
0x18002f42a  inc     rax
0x18002f42d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f433  jnz     short loc_18002F481
0x18002f435  mov     rcx, [rcx+68h]
0x18002f439  mov     rax, [rcx]
0x18002f43c  mov     rax, [rax+150h]
0x18002f443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f448  mov     rcx, rax; hResource
0x18002f44b  mov     edx, ebx; dwType
0x18002f44d  call    cs:__imp_ClusterResourceOpenEnum
0x18002f454  nop     dword ptr [rax+rax+00h]
0x18002f459  mov     rcx, rsi
0x18002f45c  mov     rbx, rax
0x18002f45f  call    ?Close@?$AutoHandle@PEAU_HRESENUM@@K$1?ClusterResourceCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESENUM *,ulong,&ClusterResourceCloseEnum(_HRESENUM *),0>::Close(void)
0x18002f464  lea     rax, [rbx+1]
0x18002f468  mov     [rsi], rbx
0x18002f46b  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f471  jnz     short loc_18002F481
0x18002f473  call    cs:__imp_GetLastError
0x18002f47a  nop     dword ptr [rax+rax+00h]
0x18002f47f  mov     edi, eax
0x18002f481  mov     rbx, [rsp+28h+arg_0]
0x18002f486  mov     eax, edi
0x18002f488  mov     rsi, [rsp+28h+arg_8]
0x18002f48d  add     rsp, 20h
0x18002f491  pop     rdi
0x18002f492  retn
```
