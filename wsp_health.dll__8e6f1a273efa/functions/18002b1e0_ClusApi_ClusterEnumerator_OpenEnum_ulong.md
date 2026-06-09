# ClusApi::ClusterEnumerator::OpenEnum(ulong)

- ea: `0x18002b1e0`
- end: `0x18002b267`
- name: `?OpenEnum@ClusterEnumerator@ClusApi@@MEAAKK@Z`
- size: `135`
- prototype: `unsigned int(ClusApi::ClusterEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002a92c`
- `0x18002b1e0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b246`
- `CLUSAPI!ClusterOpenEnumEx` at `0x18002b220`
- `CLUSAPI!ClusterOpenEnumEx` at `0x18002b220`

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
0x18002b1e0  mov     [rsp+arg_0], rbx
0x18002b1e5  mov     [rsp+arg_8], rsi
0x18002b1ea  push    rdi
0x18002b1eb  sub     rsp, 20h
0x18002b1ef  lea     rsi, [rcx+20h]
0x18002b1f3  xor     edi, edi
0x18002b1f5  mov     rax, [rsi]
0x18002b1f8  mov     ebx, edx
0x18002b1fa  inc     rax
0x18002b1fd  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b203  jnz     short loc_18002B254
0x18002b205  mov     rcx, [rcx+30h]
0x18002b209  mov     rax, [rcx]
0x18002b20c  mov     rax, [rax+188h]
0x18002b213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b218  mov     rcx, rax; hCluster
0x18002b21b  xor     r8d, r8d; pOptions
0x18002b21e  mov     edx, ebx; dwType
0x18002b220  call    cs:__imp_ClusterOpenEnumEx
0x18002b227  nop     dword ptr [rax+rax+00h]
0x18002b22c  mov     rcx, rsi
0x18002b22f  mov     rbx, rax
0x18002b232  call    ?Close@?$AutoHandle@PEAU_HCLUSENUMEX@@K$1?ClusterCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSENUMEX *,ulong,&ClusterCloseEnumEx(_HCLUSENUMEX *),0>::Close(void)
0x18002b237  lea     rax, [rbx+1]
0x18002b23b  mov     [rsi], rbx
0x18002b23e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b244  jnz     short loc_18002B254
0x18002b246  call    cs:__imp_GetLastError
0x18002b24d  nop     dword ptr [rax+rax+00h]
0x18002b252  mov     edi, eax
0x18002b254  mov     rbx, [rsp+28h+arg_0]
0x18002b259  mov     eax, edi
0x18002b25b  mov     rsi, [rsp+28h+arg_8]
0x18002b260  add     rsp, 20h
0x18002b264  pop     rdi
0x18002b265  retn
```
