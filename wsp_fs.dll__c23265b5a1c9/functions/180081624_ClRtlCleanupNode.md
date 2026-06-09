# ClRtlCleanupNode

- ea: `0x180081624`
- end: `0x18008173a`
- name: `ClRtlCleanupNode`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031980`

## callees

- `0x180081624`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180081720`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180081720`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800816d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800816d8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008163f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008163f`

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
0x180081624  push    rbx
0x180081626  push    rbp
0x180081627  push    rsi
0x180081628  push    rdi
0x180081629  push    r14
0x18008162b  sub     rsp, 70h
0x18008162f  mov     r14d, edx
0x180081632  mov     rbx, rcx
0x180081635  mov     edx, 4; dwCoInit
0x18008163a  xor     ecx, ecx; pvReserved
0x18008163c  mov     ebp, r8d
0x18008163f  call    cs:__imp_CoInitializeEx
0x180081646  nop     dword ptr [rax+rax+00h]
0x18008164b  mov     edi, eax
0x18008164d  cmp     eax, 80010106h
0x180081652  jz      short loc_180081660
0x180081654  cmp     eax, 1
0x180081657  jbe     short loc_180081660
0x180081659  mov     esi, eax
0x18008165b  jmp     loc_18008172C
0x180081660  mov     [rsp+98h+var_68.pItf], 0
0x180081669  xorps   xmm0, xmm0
0x18008166c  mov     [rsp+98h+var_68.hr], 0
0x180081674  lea     rax, IID_IClusterCleanup
0x18008167b  mov     [rsp+98h+var_68.pIID], rax
0x180081680  movups  xmmword ptr [rsp+98h+pServerInfo.dwReserved1], xmm0
0x180081685  movups  xmmword ptr [rsp+98h+pServerInfo.pAuthInfo], xmm0
0x18008168a  test    rbx, rbx
0x18008168d  jnz     short loc_180081694
0x18008168f  xor     r9d, r9d
0x180081692  jmp     short loc_1800816AF
0x180081694  lea     r9, [rsp+98h+pServerInfo]; pServerInfo
0x180081699  mov     [rsp+98h+pServerInfo.pwszName], rbx
0x18008169e  mov     [rsp+98h+pServerInfo.pAuthInfo], 0
0x1800816a7  mov     [rsp+98h+pServerInfo.dwReserved2], 0
0x1800816af  lea     rax, [rsp+98h+var_68]
0x1800816b4  neg     rbx
0x1800816b7  mov     [rsp+98h+pResults], rax; pResults
0x1800816bc  lea     rcx, CLSID_ClusterCleanup; Clsid
0x1800816c3  sbb     r8d, r8d
0x1800816c6  mov     [rsp+98h+dwCount], 1; dwCount
0x1800816ce  and     r8d, 0Ch
0x1800816d2  xor     edx, edx; punkOuter
0x1800816d4  add     r8d, 4; dwClsCtx
0x1800816d8  call    cs:__imp_CoCreateInstanceEx
0x1800816df  nop     dword ptr [rax+rax+00h]
0x1800816e4  mov     esi, eax
0x1800816e6  test    eax, eax
0x1800816e8  js      short loc_180081718
0x1800816ea  mov     rbx, [rsp+98h+var_68.pItf]
0x1800816ef  xor     r9d, r9d
0x1800816f2  mov     r8d, ebp
0x1800816f5  mov     edx, r14d
0x1800816f8  mov     rcx, rbx
0x1800816fb  mov     rax, [rbx]
0x1800816fe  mov     rax, [rax+18h]
0x180081702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081707  mov     esi, eax
0x180081709  mov     rax, [rbx]
0x18008170c  mov     rcx, rbx
0x18008170f  mov     rax, [rax+10h]
0x180081713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081718  cmp     edi, 80010106h
0x18008171e  jz      short loc_18008172C
0x180081720  call    cs:__imp_CoUninitialize
0x180081727  nop     dword ptr [rax+rax+00h]
0x18008172c  mov     eax, esi
0x18008172e  add     rsp, 70h
0x180081732  pop     r14
0x180081734  pop     rdi
0x180081735  pop     rsi
0x180081736  pop     rbp
0x180081737  pop     rbx
0x180081738  retn
```
