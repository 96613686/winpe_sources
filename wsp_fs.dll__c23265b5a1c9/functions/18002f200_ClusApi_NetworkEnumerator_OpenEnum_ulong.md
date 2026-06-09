# ClusApi::NetworkEnumerator::OpenEnum(ulong)

- ea: `0x18002f200`
- end: `0x18002f284`
- name: `?OpenEnum@NetworkEnumerator@ClusApi@@MEAAKK@Z`
- size: `132`
- prototype: `unsigned int(ClusApi::NetworkEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e814`
- `0x18002f200`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f263`
- `CLUSAPI!ClusterNetworkOpenEnum` at `0x18002f23d`
- `CLUSAPI!ClusterNetworkOpenEnum` at `0x18002f23d`

## pseudocode

```c
__int64 __fastcall ClusApi::NetworkEnumerator::OpenEnum(ClusApi::NetworkEnumerator *this, DWORD a2)
{
  HNETWORKENUM *v2; // rsi
  unsigned int v3; // edi
  struct _HNETWORK *v5; // rax
  HNETWORKENUM v6; // rbx

  v2 = (HNETWORKENUM *)((char *)this + 96);
  v3 = 0;
  if ( ((*((_QWORD *)this + 12) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = (struct _HNETWORK *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 128LL))(*((_QWORD *)this + 13));
    v6 = ClusterNetworkOpenEnum(v5, a2);
    cxl::AutoHandle<_HNETWORKENUM *,unsigned long,&unsigned long ClusterNetworkCloseEnum(_HNETWORKENUM *),0>::Close(v2);
    *v2 = v6;
    if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x18002f200  mov     [rsp+arg_0], rbx
0x18002f205  mov     [rsp+arg_8], rsi
0x18002f20a  push    rdi
0x18002f20b  sub     rsp, 20h
0x18002f20f  lea     rsi, [rcx+60h]
0x18002f213  xor     edi, edi
0x18002f215  mov     rax, [rsi]
0x18002f218  mov     ebx, edx
0x18002f21a  inc     rax
0x18002f21d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f223  jnz     short loc_18002F271
0x18002f225  mov     rcx, [rcx+68h]
0x18002f229  mov     rax, [rcx]
0x18002f22c  mov     rax, [rax+80h]
0x18002f233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f238  mov     rcx, rax; hNetwork
0x18002f23b  mov     edx, ebx; dwType
0x18002f23d  call    cs:__imp_ClusterNetworkOpenEnum
0x18002f244  nop     dword ptr [rax+rax+00h]
0x18002f249  mov     rcx, rsi
0x18002f24c  mov     rbx, rax
0x18002f24f  call    ?Close@?$AutoHandle@PEAU_HNETWORKENUM@@K$1?ClusterNetworkCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETWORKENUM *,ulong,&ClusterNetworkCloseEnum(_HNETWORKENUM *),0>::Close(void)
0x18002f254  lea     rax, [rbx+1]
0x18002f258  mov     [rsi], rbx
0x18002f25b  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f261  jnz     short loc_18002F271
0x18002f263  call    cs:__imp_GetLastError
0x18002f26a  nop     dword ptr [rax+rax+00h]
0x18002f26f  mov     edi, eax
0x18002f271  mov     rbx, [rsp+28h+arg_0]
0x18002f276  mov     eax, edi
0x18002f278  mov     rsi, [rsp+28h+arg_8]
0x18002f27d  add     rsp, 20h
0x18002f281  pop     rdi
0x18002f282  retn
```
