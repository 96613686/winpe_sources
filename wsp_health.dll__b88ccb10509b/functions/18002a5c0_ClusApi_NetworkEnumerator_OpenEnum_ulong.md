# ClusApi::NetworkEnumerator::OpenEnum(ulong)

- ea: `0x18002a5c0`
- end: `0x18002a637`
- name: `?OpenEnum@NetworkEnumerator@ClusApi@@MEAAKK@Z`
- size: `119`
- prototype: `unsigned int(ClusApi::NetworkEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180029c78`
- `0x18002a5c0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a61d`
- `CLUSAPI!ClusterNetworkOpenEnum` at `0x18002a5fd`
- `CLUSAPI!ClusterNetworkOpenEnum` at `0x18002a5fd`

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
0x18002a5c0  mov     [rsp+arg_0], rbx
0x18002a5c5  mov     [rsp+arg_8], rsi
0x18002a5ca  push    rdi
0x18002a5cb  sub     rsp, 20h
0x18002a5cf  lea     rsi, [rcx+60h]
0x18002a5d3  xor     edi, edi
0x18002a5d5  mov     rax, [rsi]
0x18002a5d8  mov     ebx, edx
0x18002a5da  inc     rax
0x18002a5dd  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a5e3  jnz     short loc_18002A625
0x18002a5e5  mov     rcx, [rcx+68h]
0x18002a5e9  mov     rax, [rcx]
0x18002a5ec  mov     rax, [rax+80h]
0x18002a5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5f8  mov     rcx, rax; hNetwork
0x18002a5fb  mov     edx, ebx; dwType
0x18002a5fd  call    cs:__imp_ClusterNetworkOpenEnum
0x18002a603  mov     rcx, rsi
0x18002a606  mov     rbx, rax
0x18002a609  call    ?Close@?$AutoHandle@PEAU_HNETWORKENUM@@K$1?ClusterNetworkCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETWORKENUM *,ulong,&ClusterNetworkCloseEnum(_HNETWORKENUM *),0>::Close(void)
0x18002a60e  lea     rax, [rbx+1]
0x18002a612  mov     [rsi], rbx
0x18002a615  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a61b  jnz     short loc_18002A625
0x18002a61d  call    cs:__imp_GetLastError
0x18002a623  mov     edi, eax
0x18002a625  mov     rbx, [rsp+28h+arg_0]
0x18002a62a  mov     eax, edi
0x18002a62c  mov     rsi, [rsp+28h+arg_8]
0x18002a631  add     rsp, 20h
0x18002a635  pop     rdi
0x18002a636  retn
```
