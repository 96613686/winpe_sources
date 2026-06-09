# ClusApi::NetworkEnumerator::OpenEnum(ulong)

- ea: `0x18002b3c0`
- end: `0x18002b444`
- name: `?OpenEnum@NetworkEnumerator@ClusApi@@MEAAKK@Z`
- size: `132`
- prototype: `unsigned int(ClusApi::NetworkEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002a9d4`
- `0x18002b3c0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b423`
- `CLUSAPI!ClusterNetworkOpenEnum` at `0x18002b3fd`
- `CLUSAPI!ClusterNetworkOpenEnum` at `0x18002b3fd`

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
0x18002b3c0  mov     [rsp+arg_0], rbx
0x18002b3c5  mov     [rsp+arg_8], rsi
0x18002b3ca  push    rdi
0x18002b3cb  sub     rsp, 20h
0x18002b3cf  lea     rsi, [rcx+60h]
0x18002b3d3  xor     edi, edi
0x18002b3d5  mov     rax, [rsi]
0x18002b3d8  mov     ebx, edx
0x18002b3da  inc     rax
0x18002b3dd  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b3e3  jnz     short loc_18002B431
0x18002b3e5  mov     rcx, [rcx+68h]
0x18002b3e9  mov     rax, [rcx]
0x18002b3ec  mov     rax, [rax+80h]
0x18002b3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3f8  mov     rcx, rax; hNetwork
0x18002b3fb  mov     edx, ebx; dwType
0x18002b3fd  call    cs:__imp_ClusterNetworkOpenEnum
0x18002b404  nop     dword ptr [rax+rax+00h]
0x18002b409  mov     rcx, rsi
0x18002b40c  mov     rbx, rax
0x18002b40f  call    ?Close@?$AutoHandle@PEAU_HNETWORKENUM@@K$1?ClusterNetworkCloseEnum@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETWORKENUM *,ulong,&ClusterNetworkCloseEnum(_HNETWORKENUM *),0>::Close(void)
0x18002b414  lea     rax, [rbx+1]
0x18002b418  mov     [rsi], rbx
0x18002b41b  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b421  jnz     short loc_18002B431
0x18002b423  call    cs:__imp_GetLastError
0x18002b42a  nop     dword ptr [rax+rax+00h]
0x18002b42f  mov     edi, eax
0x18002b431  mov     rbx, [rsp+28h+arg_0]
0x18002b436  mov     eax, edi
0x18002b438  mov     rsi, [rsp+28h+arg_8]
0x18002b43d  add     rsp, 20h
0x18002b441  pop     rdi
0x18002b442  retn
```
