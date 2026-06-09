# ClusApi::NetworkEnumerator::OpenEnum(ulong)

- ea: `0x18002e300`
- end: `0x18002e377`
- name: `?OpenEnum@NetworkEnumerator@ClusApi@@MEAAKK@Z`
- size: `119`
- prototype: `unsigned int(ClusApi::NetworkEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002d9b8`
- `0x18002e300`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e35d`
- `CLUSAPI!ClusterNetworkOpenEnum` at `0x18002e33d`
- `CLUSAPI!ClusterNetworkOpenEnum` at `0x18002e33d`

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
0x18002e300  mov     [rsp+arg_0], rbx
0x18002e305  mov     [rsp+arg_8], rsi
0x18002e30a  push    rdi
0x18002e30b  sub     rsp, 20h
0x18002e30f  lea     rsi, [rcx+60h]
0x18002e313  xor     edi, edi
0x18002e315  mov     rax, [rsi]
0x18002e318  mov     ebx, edx
0x18002e31a  inc     rax
0x18002e31d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e323  jnz     short loc_18002E365
0x18002e325  mov     rcx, [rcx+68h]
0x18002e329  mov     rax, [rcx]
0x18002e32c  mov     rax, [rax+80h]
0x18002e333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e338  mov     rcx, rax; hNetwork
0x18002e33b  mov     edx, ebx; dwType
0x18002e33d  call    cs:__imp_ClusterNetworkOpenEnum
0x18002e343  mov     rcx, rsi
0x18002e346  mov     rbx, rax
0x18002e349  call    ?Close@?$AutoHandle@PEAU_HNETWORKENUM@@K$1?ClusterNetworkCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETWORKENUM *,ulong,&ClusterNetworkCloseEnum(_HNETWORKENUM *),0>::Close(void)
0x18002e34e  lea     rax, [rbx+1]
0x18002e352  mov     [rsi], rbx
0x18002e355  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e35b  jnz     short loc_18002E365
0x18002e35d  call    cs:__imp_GetLastError
0x18002e363  mov     edi, eax
0x18002e365  mov     rbx, [rsp+28h+arg_0]
0x18002e36a  mov     eax, edi
0x18002e36c  mov     rsi, [rsp+28h+arg_8]
0x18002e371  add     rsp, 20h
0x18002e375  pop     rdi
0x18002e376  retn
```
