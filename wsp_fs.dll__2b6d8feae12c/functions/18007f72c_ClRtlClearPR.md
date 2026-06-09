# ClRtlClearPR

- ea: `0x18007f72c`
- end: `0x18007f820`
- name: `ClRtlClearPR`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800309b0`

## callees

- `0x18007f72c`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007f80f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007f80f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18007f7d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18007f7d4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007f741`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007f741`

## pseudocode

```c
__int64 __fastcall ClRtlClearPR(WCHAR *a1, unsigned int a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  HRESULT v6; // esi
  COSERVERINFO *p_pServerInfo; // r9
  IUnknown *pItf; // rbx
  MULTI_QI pResults; // [rsp+30h] [rbp-68h] BYREF
  COSERVERINFO pServerInfo; // [rsp+48h] [rbp-50h] BYREF

  v4 = CoInitializeEx(0, 4u);
  v5 = v4;
  if ( v4 == -2147417850 || v4 <= 1 )
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
    v6 = CoCreateInstanceEx(&CLSID_ClusterCleanup, 0, a1 != 0 ? 16 : 4, p_pServerInfo, 1u, &pResults);
    if ( v6 >= 0 )
    {
      pItf = pResults.pItf;
      v6 = ((__int64 (__fastcall *)(IUnknown *, _QWORD))pResults.pItf->lpVtbl[1].AddRef)(pResults.pItf, a2);
      ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
    }
    if ( v5 != -2147417850 )
      CoUninitialize();
  }
  else
  {
    return v4;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007f72c  push    rbx
0x18007f72e  push    rbp
0x18007f72f  push    rsi
0x18007f730  push    rdi
0x18007f731  sub     rsp, 78h
0x18007f735  mov     ebp, edx
0x18007f737  mov     rbx, rcx
0x18007f73a  mov     edx, 4; dwCoInit
0x18007f73f  xor     ecx, ecx; pvReserved
0x18007f741  call    cs:__imp_CoInitializeEx
0x18007f747  mov     edi, eax
0x18007f749  cmp     eax, 80010106h
0x18007f74e  jz      short loc_18007F75C
0x18007f750  cmp     eax, 1
0x18007f753  jbe     short loc_18007F75C
0x18007f755  mov     esi, eax
0x18007f757  jmp     loc_18007F815
0x18007f75c  mov     [rsp+98h+var_68.pItf], 0
0x18007f765  xorps   xmm0, xmm0
0x18007f768  mov     [rsp+98h+var_68.hr], 0
0x18007f770  lea     rax, IID_IClusterCleanup
0x18007f777  mov     [rsp+98h+var_68.pIID], rax
0x18007f77c  movups  xmmword ptr [rsp+98h+pServerInfo.dwReserved1], xmm0
0x18007f781  movups  xmmword ptr [rsp+98h+pServerInfo.pAuthInfo], xmm0
0x18007f786  test    rbx, rbx
0x18007f789  jnz     short loc_18007F790
0x18007f78b  xor     r9d, r9d
0x18007f78e  jmp     short loc_18007F7AB
0x18007f790  lea     r9, [rsp+98h+pServerInfo]; pServerInfo
0x18007f795  mov     [rsp+98h+pServerInfo.pwszName], rbx
0x18007f79a  mov     [rsp+98h+pServerInfo.pAuthInfo], 0
0x18007f7a3  mov     [rsp+98h+pServerInfo.dwReserved2], 0
0x18007f7ab  lea     rax, [rsp+98h+var_68]
0x18007f7b0  neg     rbx
0x18007f7b3  mov     [rsp+98h+pResults], rax; pResults
0x18007f7b8  lea     rcx, CLSID_ClusterCleanup; Clsid
0x18007f7bf  sbb     r8d, r8d
0x18007f7c2  mov     [rsp+98h+dwCount], 1; dwCount
0x18007f7ca  and     r8d, 0Ch
0x18007f7ce  xor     edx, edx; punkOuter
0x18007f7d0  add     r8d, 4; dwClsCtx
0x18007f7d4  call    cs:__imp_CoCreateInstanceEx
0x18007f7da  mov     esi, eax
0x18007f7dc  test    eax, eax
0x18007f7de  js      short loc_18007F807
0x18007f7e0  mov     rbx, [rsp+98h+var_68.pItf]
0x18007f7e5  mov     edx, ebp
0x18007f7e7  mov     rcx, rbx
0x18007f7ea  mov     rax, [rbx]
0x18007f7ed  mov     rax, [rax+20h]
0x18007f7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f7f6  mov     esi, eax
0x18007f7f8  mov     rax, [rbx]
0x18007f7fb  mov     rcx, rbx
0x18007f7fe  mov     rax, [rax+10h]
0x18007f802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f807  cmp     edi, 80010106h
0x18007f80d  jz      short loc_18007F815
0x18007f80f  call    cs:__imp_CoUninitialize
0x18007f815  mov     eax, esi
0x18007f817  add     rsp, 78h
0x18007f81b  pop     rdi
0x18007f81c  pop     rsi
0x18007f81d  pop     rbp
0x18007f81e  pop     rbx
0x18007f81f  retn
```
