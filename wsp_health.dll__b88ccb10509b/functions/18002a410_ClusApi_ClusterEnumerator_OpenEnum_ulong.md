# ClusApi::ClusterEnumerator::OpenEnum(ulong)

- ea: `0x18002a410`
- end: `0x18002a48a`
- name: `?OpenEnum@ClusterEnumerator@ClusApi@@MEAAKK@Z`
- size: `122`
- prototype: `unsigned int(ClusApi::ClusterEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180029be8`
- `0x18002a410`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a470`
- `CLUSAPI!ClusterOpenEnumEx` at `0x18002a450`
- `CLUSAPI!ClusterOpenEnumEx` at `0x18002a450`

## pseudocode

```c
__int64 __fastcall ClusApi::ClusterEnumerator::OpenEnum(ClusApi::ClusterEnumerator *this, DWORD a2)
{
  HCLUSENUMEX *v2; // rsi
  unsigned int v3; // edi
  struct _HCLUSTER *v5; // rax
  HCLUSENUMEX v6; // rbx

  v2 = (HCLUSENUMEX *)((char *)this + 32);
  v3 = 0;
  if ( ((*((_QWORD *)this + 4) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = (struct _HCLUSTER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 392LL))(*((_QWORD *)this + 6));
    v6 = ClusterOpenEnumEx(v5, a2, 0);
    cxl::AutoHandle<_HCLUSENUMEX *,unsigned long,&unsigned long ClusterCloseEnumEx(_HCLUSENUMEX *),0>::Close(v2);
    *v2 = v6;
    if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x18002a410  mov     [rsp+arg_0], rbx
0x18002a415  mov     [rsp+arg_8], rsi
0x18002a41a  push    rdi
0x18002a41b  sub     rsp, 20h
0x18002a41f  lea     rsi, [rcx+20h]
0x18002a423  xor     edi, edi
0x18002a425  mov     rax, [rsi]
0x18002a428  mov     ebx, edx
0x18002a42a  inc     rax
0x18002a42d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a433  jnz     short loc_18002A478
0x18002a435  mov     rcx, [rcx+30h]
0x18002a439  mov     rax, [rcx]
0x18002a43c  mov     rax, [rax+188h]
0x18002a443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a448  mov     rcx, rax; hCluster
0x18002a44b  xor     r8d, r8d; pOptions
0x18002a44e  mov     edx, ebx; dwType
0x18002a450  call    cs:__imp_ClusterOpenEnumEx
0x18002a456  mov     rcx, rsi
0x18002a459  mov     rbx, rax
0x18002a45c  call    ?Close@?$AutoHandle@PEAU_HCLUSENUMEX@@K$1?ClusterCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSENUMEX *,ulong,&ClusterCloseEnumEx(_HCLUSENUMEX *),0>::Close(void)
0x18002a461  lea     rax, [rbx+1]
0x18002a465  mov     [rsi], rbx
0x18002a468  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a46e  jnz     short loc_18002A478
0x18002a470  call    cs:__imp_GetLastError
0x18002a476  mov     edi, eax
0x18002a478  mov     rbx, [rsp+28h+arg_0]
0x18002a47d  mov     eax, edi
0x18002a47f  mov     rsi, [rsp+28h+arg_8]
0x18002a484  add     rsp, 20h
0x18002a488  pop     rdi
0x18002a489  retn
```
