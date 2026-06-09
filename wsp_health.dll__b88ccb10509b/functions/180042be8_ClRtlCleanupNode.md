# ClRtlCleanupNode

- ea: `0x180042be8`
- end: `0x180042ceb`
- name: `ClRtlCleanupNode`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002cc80`

## callees

- `0x180042be8`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180042c96`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180042c96`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042cd8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042cd8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180042c03`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180042c03`

## pseudocode

```c
__int64 __fastcall ClRtlCleanupNode(WCHAR *a1, unsigned int a2, unsigned int a3)
{
  unsigned int v6; // eax
  unsigned int v7; // edi
  HRESULT v8; // esi
  COSERVERINFO *p_pServerInfo; // r9
  IUnknown *pItf; // rbx
  MULTI_QI pResults; // [rsp+30h] [rbp-68h] BYREF
  COSERVERINFO pServerInfo; // [rsp+48h] [rbp-50h] BYREF

  v6 = CoInitializeEx(0, 4u);
  v7 = v6;
  if ( v6 == -2147417850 || v6 <= 1 )
  {
    pResults.pItf = 0;
    pResults.hr = 0;
    pResults.pIID = &IID_IClusterCleanup;
    memset(&pServerInfo, 0, sizeof(pServerInfo));
    if ( a1 )
    {
      p_pServerInfo = &pServerInfo;
      pServerInfo.pwszName = a1;
      pServerInfo.pAuthInfo = 0;
      pServerInfo.dwReserved2 = 0;
    }
    else
    {
      p_pServerInfo = 0;
    }
    v8 = CoCreateInstanceEx(&CLSID_ClusterCleanup, 0, a1 != 0 ? 16 : 4, p_pServerInfo, 1u, &pResults);
    if ( v8 >= 0 )
    {
      pItf = pResults.pItf;
      v8 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))pResults.pItf->lpVtbl[1].QueryInterface)(
             pResults.pItf,
             a2,
             a3,
             0);
      ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
    }
    if ( v7 != -2147417850 )
      CoUninitialize();
  }
  else
  {
    return v6;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180042be8  push    rbx
0x180042bea  push    rbp
0x180042beb  push    rsi
0x180042bec  push    rdi
0x180042bed  push    r14
0x180042bef  sub     rsp, 70h
0x180042bf3  mov     r14d, edx
0x180042bf6  mov     rbx, rcx
0x180042bf9  mov     edx, 4; dwCoInit
0x180042bfe  xor     ecx, ecx; pvReserved
0x180042c00  mov     ebp, r8d
0x180042c03  call    cs:__imp_CoInitializeEx
0x180042c09  mov     edi, eax
0x180042c0b  cmp     eax, 80010106h
0x180042c10  jz      short loc_180042C1E
0x180042c12  cmp     eax, 1
0x180042c15  jbe     short loc_180042C1E
0x180042c17  mov     esi, eax
0x180042c19  jmp     loc_180042CDE
0x180042c1e  mov     [rsp+98h+var_68.pItf], 0
0x180042c27  xorps   xmm0, xmm0
0x180042c2a  mov     [rsp+98h+var_68.hr], 0
0x180042c32  lea     rax, IID_IClusterCleanup
0x180042c39  mov     [rsp+98h+var_68.pIID], rax
0x180042c3e  movups  xmmword ptr [rsp+98h+pServerInfo.dwReserved1], xmm0
0x180042c43  movups  xmmword ptr [rsp+98h+pServerInfo.pAuthInfo], xmm0
0x180042c48  test    rbx, rbx
0x180042c4b  jnz     short loc_180042C52
0x180042c4d  xor     r9d, r9d
0x180042c50  jmp     short loc_180042C6D
0x180042c52  lea     r9, [rsp+98h+pServerInfo]; pServerInfo
0x180042c57  mov     [rsp+98h+pServerInfo.pwszName], rbx
0x180042c5c  mov     [rsp+98h+pServerInfo.pAuthInfo], 0
0x180042c65  mov     [rsp+98h+pServerInfo.dwReserved2], 0
0x180042c6d  lea     rax, [rsp+98h+var_68]
0x180042c72  neg     rbx
0x180042c75  mov     [rsp+98h+pResults], rax; pResults
0x180042c7a  lea     rcx, CLSID_ClusterCleanup; Clsid
0x180042c81  sbb     r8d, r8d
0x180042c84  mov     [rsp+98h+dwCount], 1; dwCount
0x180042c8c  and     r8d, 0Ch
0x180042c90  xor     edx, edx; punkOuter
0x180042c92  add     r8d, 4; dwClsCtx
0x180042c96  call    cs:__imp_CoCreateInstanceEx
0x180042c9c  mov     esi, eax
0x180042c9e  test    eax, eax
0x180042ca0  js      short loc_180042CD0
0x180042ca2  mov     rbx, [rsp+98h+var_68.pItf]
0x180042ca7  xor     r9d, r9d
0x180042caa  mov     r8d, ebp
0x180042cad  mov     edx, r14d
0x180042cb0  mov     rcx, rbx
0x180042cb3  mov     rax, [rbx]
0x180042cb6  mov     rax, [rax+18h]
0x180042cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cbf  mov     esi, eax
0x180042cc1  mov     rax, [rbx]
0x180042cc4  mov     rcx, rbx
0x180042cc7  mov     rax, [rax+10h]
0x180042ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cd0  cmp     edi, 80010106h
0x180042cd6  jz      short loc_180042CDE
0x180042cd8  call    cs:__imp_CoUninitialize
0x180042cde  mov     eax, esi
0x180042ce0  add     rsp, 70h
0x180042ce4  pop     r14
0x180042ce6  pop     rdi
0x180042ce7  pop     rsi
0x180042ce8  pop     rbp
0x180042ce9  pop     rbx
0x180042cea  retn
```
