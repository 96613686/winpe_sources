# ClRtlCleanupNode

- ea: `0x18007f620`
- end: `0x18007f723`
- name: `ClRtlCleanupNode`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030990`

## callees

- `0x18007f620`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007f710`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007f710`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18007f6ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18007f6ce`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007f63b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007f63b`

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
0x18007f620  push    rbx
0x18007f622  push    rbp
0x18007f623  push    rsi
0x18007f624  push    rdi
0x18007f625  push    r14
0x18007f627  sub     rsp, 70h
0x18007f62b  mov     r14d, edx
0x18007f62e  mov     rbx, rcx
0x18007f631  mov     edx, 4; dwCoInit
0x18007f636  xor     ecx, ecx; pvReserved
0x18007f638  mov     ebp, r8d
0x18007f63b  call    cs:__imp_CoInitializeEx
0x18007f641  mov     edi, eax
0x18007f643  cmp     eax, 80010106h
0x18007f648  jz      short loc_18007F656
0x18007f64a  cmp     eax, 1
0x18007f64d  jbe     short loc_18007F656
0x18007f64f  mov     esi, eax
0x18007f651  jmp     loc_18007F716
0x18007f656  mov     [rsp+98h+var_68.pItf], 0
0x18007f65f  xorps   xmm0, xmm0
0x18007f662  mov     [rsp+98h+var_68.hr], 0
0x18007f66a  lea     rax, IID_IClusterCleanup
0x18007f671  mov     [rsp+98h+var_68.pIID], rax
0x18007f676  movups  xmmword ptr [rsp+98h+pServerInfo.dwReserved1], xmm0
0x18007f67b  movups  xmmword ptr [rsp+98h+pServerInfo.pAuthInfo], xmm0
0x18007f680  test    rbx, rbx
0x18007f683  jnz     short loc_18007F68A
0x18007f685  xor     r9d, r9d
0x18007f688  jmp     short loc_18007F6A5
0x18007f68a  lea     r9, [rsp+98h+pServerInfo]; pServerInfo
0x18007f68f  mov     [rsp+98h+pServerInfo.pwszName], rbx
0x18007f694  mov     [rsp+98h+pServerInfo.pAuthInfo], 0
0x18007f69d  mov     [rsp+98h+pServerInfo.dwReserved2], 0
0x18007f6a5  lea     rax, [rsp+98h+var_68]
0x18007f6aa  neg     rbx
0x18007f6ad  mov     [rsp+98h+pResults], rax; pResults
0x18007f6b2  lea     rcx, CLSID_ClusterCleanup; Clsid
0x18007f6b9  sbb     r8d, r8d
0x18007f6bc  mov     [rsp+98h+dwCount], 1; dwCount
0x18007f6c4  and     r8d, 0Ch
0x18007f6c8  xor     edx, edx; punkOuter
0x18007f6ca  add     r8d, 4; dwClsCtx
0x18007f6ce  call    cs:__imp_CoCreateInstanceEx
0x18007f6d4  mov     esi, eax
0x18007f6d6  test    eax, eax
0x18007f6d8  js      short loc_18007F708
0x18007f6da  mov     rbx, [rsp+98h+var_68.pItf]
0x18007f6df  xor     r9d, r9d
0x18007f6e2  mov     r8d, ebp
0x18007f6e5  mov     edx, r14d
0x18007f6e8  mov     rcx, rbx
0x18007f6eb  mov     rax, [rbx]
0x18007f6ee  mov     rax, [rax+18h]
0x18007f6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f6f7  mov     esi, eax
0x18007f6f9  mov     rax, [rbx]
0x18007f6fc  mov     rcx, rbx
0x18007f6ff  mov     rax, [rax+10h]
0x18007f703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f708  cmp     edi, 80010106h
0x18007f70e  jz      short loc_18007F716
0x18007f710  call    cs:__imp_CoUninitialize
0x18007f716  mov     eax, esi
0x18007f718  add     rsp, 70h
0x18007f71c  pop     r14
0x18007f71e  pop     rdi
0x18007f71f  pop     rsi
0x18007f720  pop     rbp
0x18007f721  pop     rbx
0x18007f722  retn
```
