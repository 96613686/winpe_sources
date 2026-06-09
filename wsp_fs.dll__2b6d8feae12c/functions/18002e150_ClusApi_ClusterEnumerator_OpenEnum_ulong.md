# ClusApi::ClusterEnumerator::OpenEnum(ulong)

- ea: `0x18002e150`
- end: `0x18002e1ca`
- name: `?OpenEnum@ClusterEnumerator@ClusApi@@MEAAKK@Z`
- size: `122`
- prototype: `unsigned int(ClusApi::ClusterEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002d928`
- `0x18002e150`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1b0`
- `CLUSAPI!ClusterOpenEnumEx` at `0x18002e190`
- `CLUSAPI!ClusterOpenEnumEx` at `0x18002e190`

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
0x18002e150  mov     [rsp+arg_0], rbx
0x18002e155  mov     [rsp+arg_8], rsi
0x18002e15a  push    rdi
0x18002e15b  sub     rsp, 20h
0x18002e15f  lea     rsi, [rcx+20h]
0x18002e163  xor     edi, edi
0x18002e165  mov     rax, [rsi]
0x18002e168  mov     ebx, edx
0x18002e16a  inc     rax
0x18002e16d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e173  jnz     short loc_18002E1B8
0x18002e175  mov     rcx, [rcx+30h]
0x18002e179  mov     rax, [rcx]
0x18002e17c  mov     rax, [rax+188h]
0x18002e183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e188  mov     rcx, rax; hCluster
0x18002e18b  xor     r8d, r8d; pOptions
0x18002e18e  mov     edx, ebx; dwType
0x18002e190  call    cs:__imp_ClusterOpenEnumEx
0x18002e196  mov     rcx, rsi
0x18002e199  mov     rbx, rax
0x18002e19c  call    ?Close@?$AutoHandle@PEAU_HCLUSENUMEX@@K$1?ClusterCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSENUMEX *,ulong,&ClusterCloseEnumEx(_HCLUSENUMEX *),0>::Close(void)
0x18002e1a1  lea     rax, [rbx+1]
0x18002e1a5  mov     [rsi], rbx
0x18002e1a8  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e1ae  jnz     short loc_18002E1B8
0x18002e1b0  call    cs:__imp_GetLastError
0x18002e1b6  mov     edi, eax
0x18002e1b8  mov     rbx, [rsp+28h+arg_0]
0x18002e1bd  mov     eax, edi
0x18002e1bf  mov     rsi, [rsp+28h+arg_8]
0x18002e1c4  add     rsp, 20h
0x18002e1c8  pop     rdi
0x18002e1c9  retn
```
