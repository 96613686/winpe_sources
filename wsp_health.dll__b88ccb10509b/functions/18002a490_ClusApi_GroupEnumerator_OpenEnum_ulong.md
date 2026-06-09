# ClusApi::GroupEnumerator::OpenEnum(ulong)

- ea: `0x18002a490`
- end: `0x18002a507`
- name: `?OpenEnum@GroupEnumerator@ClusApi@@MEAAKK@Z`
- size: `119`
- prototype: `unsigned int(ClusApi::GroupEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180029c18`
- `0x18002a490`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4ed`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002a4cd`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002a4cd`

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
0x18002a490  mov     [rsp+arg_0], rbx
0x18002a495  mov     [rsp+arg_8], rsi
0x18002a49a  push    rdi
0x18002a49b  sub     rsp, 20h
0x18002a49f  lea     rsi, [rcx+60h]
0x18002a4a3  xor     edi, edi
0x18002a4a5  mov     rax, [rsi]
0x18002a4a8  mov     ebx, edx
0x18002a4aa  inc     rax
0x18002a4ad  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a4b3  jnz     short loc_18002A4F5
0x18002a4b5  mov     rcx, [rcx+68h]
0x18002a4b9  mov     rax, [rcx]
0x18002a4bc  mov     rax, [rax+0B8h]
0x18002a4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4c8  mov     rcx, rax; hGroup
0x18002a4cb  mov     edx, ebx; dwType
0x18002a4cd  call    cs:__imp_ClusterGroupOpenEnum
0x18002a4d3  mov     rcx, rsi
0x18002a4d6  mov     rbx, rax
0x18002a4d9  call    ?Close@?$AutoHandle@PEAU_HGROUPENUM@@K$1?ClusterGroupCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUPENUM *,ulong,&ClusterGroupCloseEnum(_HGROUPENUM *),0>::Close(void)
0x18002a4de  lea     rax, [rbx+1]
0x18002a4e2  mov     [rsi], rbx
0x18002a4e5  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a4eb  jnz     short loc_18002A4F5
0x18002a4ed  call    cs:__imp_GetLastError
0x18002a4f3  mov     edi, eax
0x18002a4f5  mov     rbx, [rsp+28h+arg_0]
0x18002a4fa  mov     eax, edi
0x18002a4fc  mov     rsi, [rsp+28h+arg_8]
0x18002a501  add     rsp, 20h
0x18002a505  pop     rdi
0x18002a506  retn
```
