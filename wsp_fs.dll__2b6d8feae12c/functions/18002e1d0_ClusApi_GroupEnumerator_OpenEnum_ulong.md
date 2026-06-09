# ClusApi::GroupEnumerator::OpenEnum(ulong)

- ea: `0x18002e1d0`
- end: `0x18002e247`
- name: `?OpenEnum@GroupEnumerator@ClusApi@@MEAAKK@Z`
- size: `119`
- prototype: `unsigned int(ClusApi::GroupEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002d958`
- `0x18002e1d0`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e22d`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002e20d`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002e20d`

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
0x18002e1d0  mov     [rsp+arg_0], rbx
0x18002e1d5  mov     [rsp+arg_8], rsi
0x18002e1da  push    rdi
0x18002e1db  sub     rsp, 20h
0x18002e1df  lea     rsi, [rcx+60h]
0x18002e1e3  xor     edi, edi
0x18002e1e5  mov     rax, [rsi]
0x18002e1e8  mov     ebx, edx
0x18002e1ea  inc     rax
0x18002e1ed  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e1f3  jnz     short loc_18002E235
0x18002e1f5  mov     rcx, [rcx+68h]
0x18002e1f9  mov     rax, [rcx]
0x18002e1fc  mov     rax, [rax+0B8h]
0x18002e203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e208  mov     rcx, rax; hGroup
0x18002e20b  mov     edx, ebx; dwType
0x18002e20d  call    cs:__imp_ClusterGroupOpenEnum
0x18002e213  mov     rcx, rsi
0x18002e216  mov     rbx, rax
0x18002e219  call    ?Close@?$AutoHandle@PEAU_HGROUPENUM@@K$1?ClusterGroupCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUPENUM *,ulong,&ClusterGroupCloseEnum(_HGROUPENUM *),0>::Close(void)
0x18002e21e  lea     rax, [rbx+1]
0x18002e222  mov     [rsi], rbx
0x18002e225  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e22b  jnz     short loc_18002E235
0x18002e22d  call    cs:__imp_GetLastError
0x18002e233  mov     edi, eax
0x18002e235  mov     rbx, [rsp+28h+arg_0]
0x18002e23a  mov     eax, edi
0x18002e23c  mov     rsi, [rsp+28h+arg_8]
0x18002e241  add     rsp, 20h
0x18002e245  pop     rdi
0x18002e246  retn
```
