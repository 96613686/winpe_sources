# ClRtlCleanupNode

- ea: `0x1800443d4`
- end: `0x1800444ea`
- name: `ClRtlCleanupNode`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002db60`

## callees

- `0x1800443d4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180044488`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180044488`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800444d0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800444d0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800443ef`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800443ef`

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
0x1800443d4  push    rbx
0x1800443d6  push    rbp
0x1800443d7  push    rsi
0x1800443d8  push    rdi
0x1800443d9  push    r14
0x1800443db  sub     rsp, 70h
0x1800443df  mov     r14d, edx
0x1800443e2  mov     rbx, rcx
0x1800443e5  mov     edx, 4; dwCoInit
0x1800443ea  xor     ecx, ecx; pvReserved
0x1800443ec  mov     ebp, r8d
0x1800443ef  call    cs:__imp_CoInitializeEx
0x1800443f6  nop     dword ptr [rax+rax+00h]
0x1800443fb  mov     edi, eax
0x1800443fd  cmp     eax, 80010106h
0x180044402  jz      short loc_180044410
0x180044404  cmp     eax, 1
0x180044407  jbe     short loc_180044410
0x180044409  mov     esi, eax
0x18004440b  jmp     loc_1800444DC
0x180044410  mov     [rsp+98h+var_68.pItf], 0
0x180044419  xorps   xmm0, xmm0
0x18004441c  mov     [rsp+98h+var_68.hr], 0
0x180044424  lea     rax, IID_IClusterCleanup
0x18004442b  mov     [rsp+98h+var_68.pIID], rax
0x180044430  movups  xmmword ptr [rsp+98h+pServerInfo.dwReserved1], xmm0
0x180044435  movups  xmmword ptr [rsp+98h+pServerInfo.pAuthInfo], xmm0
0x18004443a  test    rbx, rbx
0x18004443d  jnz     short loc_180044444
0x18004443f  xor     r9d, r9d
0x180044442  jmp     short loc_18004445F
0x180044444  lea     r9, [rsp+98h+pServerInfo]; pServerInfo
0x180044449  mov     [rsp+98h+pServerInfo.pwszName], rbx
0x18004444e  mov     [rsp+98h+pServerInfo.pAuthInfo], 0
0x180044457  mov     [rsp+98h+pServerInfo.dwReserved2], 0
0x18004445f  lea     rax, [rsp+98h+var_68]
0x180044464  neg     rbx
0x180044467  mov     [rsp+98h+pResults], rax; pResults
0x18004446c  lea     rcx, CLSID_ClusterCleanup; Clsid
0x180044473  sbb     r8d, r8d
0x180044476  mov     [rsp+98h+dwCount], 1; dwCount
0x18004447e  and     r8d, 0Ch
0x180044482  xor     edx, edx; punkOuter
0x180044484  add     r8d, 4; dwClsCtx
0x180044488  call    cs:__imp_CoCreateInstanceEx
0x18004448f  nop     dword ptr [rax+rax+00h]
0x180044494  mov     esi, eax
0x180044496  test    eax, eax
0x180044498  js      short loc_1800444C8
0x18004449a  mov     rbx, [rsp+98h+var_68.pItf]
0x18004449f  xor     r9d, r9d
0x1800444a2  mov     r8d, ebp
0x1800444a5  mov     edx, r14d
0x1800444a8  mov     rcx, rbx
0x1800444ab  mov     rax, [rbx]
0x1800444ae  mov     rax, [rax+18h]
0x1800444b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444b7  mov     esi, eax
0x1800444b9  mov     rax, [rbx]
0x1800444bc  mov     rcx, rbx
0x1800444bf  mov     rax, [rax+10h]
0x1800444c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444c8  cmp     edi, 80010106h
0x1800444ce  jz      short loc_1800444DC
0x1800444d0  call    cs:__imp_CoUninitialize
0x1800444d7  nop     dword ptr [rax+rax+00h]
0x1800444dc  mov     eax, esi
0x1800444de  add     rsp, 70h
0x1800444e2  pop     r14
0x1800444e4  pop     rdi
0x1800444e5  pop     rsi
0x1800444e6  pop     rbp
0x1800444e7  pop     rbx
0x1800444e8  retn
```
