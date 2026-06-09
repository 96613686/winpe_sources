# WdsSetEndpointSecurity

- ea: `0x180011ec0`
- end: `0x180011f04`
- name: `WdsSetEndpointSecurity`
- size: `68`
- prototype: `__int64 __fastcall(struct CRegEndpoint *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005df0`
- `0x180011ec0`
- `0x1800139c4`

## pseudocode

```c
__int64 __fastcall WdsSetEndpointSecurity(struct CRegEndpoint *a1, void *a2, int a3)
{
  int v3; // r9d
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8

  v3 = *((_DWORD *)a1 + 19);
  if ( !v3 )
    return 50;
  if ( v3 != 1 )
    return 6;
  v5 = CRpcHandler::SetSecurity(a1, a1, a2, a3);
  return ElValidateWin32_3(v5, v6, v7, 391);
}

```

## disassembly

```asm
0x180011ec0  sub     rsp, 28h
0x180011ec4  mov     r9d, [rcx+4Ch]
0x180011ec8  test    r9d, r9d
0x180011ecb  jz      short loc_180011EF9
0x180011ecd  cmp     r9d, 1
0x180011ed1  jz      short loc_180011EDA
0x180011ed3  mov     eax, 6
0x180011ed8  jmp     short loc_180011EFE
0x180011eda  mov     r9d, r8d; unsigned int
0x180011edd  mov     r8, rdx; void *
0x180011ee0  mov     rdx, rcx; struct CRegEndpoint *
0x180011ee3  call    ?SetSecurity@CRpcHandler@@QEAAKPEAVCRegEndpoint@@PEAXK@Z; CRpcHandler::SetSecurity(CRegEndpoint *,void *,ulong)
0x180011ee8  mov     ecx, eax
0x180011eea  mov     r9d, 187h
0x180011ef0  add     rsp, 28h
0x180011ef4  jmp     ElValidateWin32_3
0x180011ef9  mov     eax, 32h ; '2'
0x180011efe  add     rsp, 28h
0x180011f02  retn
```
