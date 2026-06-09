# ClusApi::GroupEnumerator::OpenEnum(ulong)

- ea: `0x18002f0b0`
- end: `0x18002f134`
- name: `?OpenEnum@GroupEnumerator@ClusApi@@MEAAKK@Z`
- size: `132`
- prototype: `unsigned int(ClusApi::GroupEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e7a4`
- `0x18002f0b0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f113`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002f0ed`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002f0ed`

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
0x18002f0b0  mov     [rsp+arg_0], rbx
0x18002f0b5  mov     [rsp+arg_8], rsi
0x18002f0ba  push    rdi
0x18002f0bb  sub     rsp, 20h
0x18002f0bf  lea     rsi, [rcx+60h]
0x18002f0c3  xor     edi, edi
0x18002f0c5  mov     rax, [rsi]
0x18002f0c8  mov     ebx, edx
0x18002f0ca  inc     rax
0x18002f0cd  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f0d3  jnz     short loc_18002F121
0x18002f0d5  mov     rcx, [rcx+68h]
0x18002f0d9  mov     rax, [rcx]
0x18002f0dc  mov     rax, [rax+0B8h]
0x18002f0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0e8  mov     rcx, rax; hGroup
0x18002f0eb  mov     edx, ebx; dwType
0x18002f0ed  call    cs:__imp_ClusterGroupOpenEnum
0x18002f0f4  nop     dword ptr [rax+rax+00h]
0x18002f0f9  mov     rcx, rsi
0x18002f0fc  mov     rbx, rax
0x18002f0ff  call    ?Close@?$AutoHandle@PEAU_HGROUPENUM@@K$1?ClusterGroupCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUPENUM *,ulong,&ClusterGroupCloseEnum(_HGROUPENUM *),0>::Close(void)
0x18002f104  lea     rax, [rbx+1]
0x18002f108  mov     [rsi], rbx
0x18002f10b  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f111  jnz     short loc_18002F121
0x18002f113  call    cs:__imp_GetLastError
0x18002f11a  nop     dword ptr [rax+rax+00h]
0x18002f11f  mov     edi, eax
0x18002f121  mov     rbx, [rsp+28h+arg_0]
0x18002f126  mov     eax, edi
0x18002f128  mov     rsi, [rsp+28h+arg_8]
0x18002f12d  add     rsp, 20h
0x18002f131  pop     rdi
0x18002f132  retn
```
