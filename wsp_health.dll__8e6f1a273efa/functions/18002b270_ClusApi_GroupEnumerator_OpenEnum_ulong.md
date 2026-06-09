# ClusApi::GroupEnumerator::OpenEnum(ulong)

- ea: `0x18002b270`
- end: `0x18002b2f4`
- name: `?OpenEnum@GroupEnumerator@ClusApi@@MEAAKK@Z`
- size: `132`
- prototype: `unsigned int(ClusApi::GroupEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002a964`
- `0x18002b270`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2d3`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002b2ad`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002b2ad`

## pseudocode

```c
__int64 __fastcall ClusApi::GroupEnumerator::OpenEnum(ClusApi::GroupEnumerator *this, DWORD a2)
{
  HGROUPENUM *v2; // rsi
  unsigned int v3; // edi
  struct _HGROUP *v5; // rax
  HGROUPENUM v6; // rbx

  v2 = (HGROUPENUM *)((char *)this + 96);
  v3 = 0;
  if ( ((*((_QWORD *)this + 12) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = (struct _HGROUP *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 184LL))(*((_QWORD *)this + 13));
    v6 = ClusterGroupOpenEnum(v5, a2);
    cxl::AutoHandle<_HGROUPENUM *,unsigned long,&unsigned long ClusterGroupCloseEnum(_HGROUPENUM *),0>::Close(v2);
    *v2 = v6;
    if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x18002b270  mov     [rsp+arg_0], rbx
0x18002b275  mov     [rsp+arg_8], rsi
0x18002b27a  push    rdi
0x18002b27b  sub     rsp, 20h
0x18002b27f  lea     rsi, [rcx+60h]
0x18002b283  xor     edi, edi
0x18002b285  mov     rax, [rsi]
0x18002b288  mov     ebx, edx
0x18002b28a  inc     rax
0x18002b28d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b293  jnz     short loc_18002B2E1
0x18002b295  mov     rcx, [rcx+68h]
0x18002b299  mov     rax, [rcx]
0x18002b29c  mov     rax, [rax+0B8h]
0x18002b2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2a8  mov     rcx, rax; hGroup
0x18002b2ab  mov     edx, ebx; dwType
0x18002b2ad  call    cs:__imp_ClusterGroupOpenEnum
0x18002b2b4  nop     dword ptr [rax+rax+00h]
0x18002b2b9  mov     rcx, rsi
0x18002b2bc  mov     rbx, rax
0x18002b2bf  call    ?Close@?$AutoHandle@PEAU_HGROUPENUM@@K$1?ClusterGroupCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUPENUM *,ulong,&ClusterGroupCloseEnum(_HGROUPENUM *),0>::Close(void)
0x18002b2c4  lea     rax, [rbx+1]
0x18002b2c8  mov     [rsi], rbx
0x18002b2cb  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b2d1  jnz     short loc_18002B2E1
0x18002b2d3  call    cs:__imp_GetLastError
0x18002b2da  nop     dword ptr [rax+rax+00h]
0x18002b2df  mov     edi, eax
0x18002b2e1  mov     rbx, [rsp+28h+arg_0]
0x18002b2e6  mov     eax, edi
0x18002b2e8  mov     rsi, [rsp+28h+arg_8]
0x18002b2ed  add     rsp, 20h
0x18002b2f1  pop     rdi
0x18002b2f2  retn
```
