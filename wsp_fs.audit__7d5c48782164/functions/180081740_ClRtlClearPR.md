# ClRtlClearPR

- ea: `0x180081740`
- end: `0x180081847`
- name: `ClRtlClearPR`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800319a0`

## callees

- `0x180081740`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008182f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008182f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800817ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800817ee`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180081755`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180081755`

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
0x180081740  push    rbx
0x180081742  push    rbp
0x180081743  push    rsi
0x180081744  push    rdi
0x180081745  sub     rsp, 78h
0x180081749  mov     ebp, edx
0x18008174b  mov     rbx, rcx
0x18008174e  mov     edx, 4; dwCoInit
0x180081753  xor     ecx, ecx; pvReserved
0x180081755  call    cs:__imp_CoInitializeEx
0x18008175c  nop     dword ptr [rax+rax+00h]
0x180081761  mov     edi, eax
0x180081763  cmp     eax, 80010106h
0x180081768  jz      short loc_180081776
0x18008176a  cmp     eax, 1
0x18008176d  jbe     short loc_180081776
0x18008176f  mov     esi, eax
0x180081771  jmp     loc_18008183B
0x180081776  mov     [rsp+98h+var_68.pItf], 0
0x18008177f  xorps   xmm0, xmm0
0x180081782  mov     [rsp+98h+var_68.hr], 0
0x18008178a  lea     rax, IID_IClusterCleanup
0x180081791  mov     [rsp+98h+var_68.pIID], rax
0x180081796  movups  xmmword ptr [rsp+98h+pServerInfo.dwReserved1], xmm0
0x18008179b  movups  xmmword ptr [rsp+98h+pServerInfo.pAuthInfo], xmm0
0x1800817a0  test    rbx, rbx
0x1800817a3  jnz     short loc_1800817AA
0x1800817a5  xor     r9d, r9d
0x1800817a8  jmp     short loc_1800817C5
0x1800817aa  lea     r9, [rsp+98h+pServerInfo]; pServerInfo
0x1800817af  mov     [rsp+98h+pServerInfo.pwszName], rbx
0x1800817b4  mov     [rsp+98h+pServerInfo.pAuthInfo], 0
0x1800817bd  mov     [rsp+98h+pServerInfo.dwReserved2], 0
0x1800817c5  lea     rax, [rsp+98h+var_68]
0x1800817ca  neg     rbx
0x1800817cd  mov     [rsp+98h+pResults], rax; pResults
0x1800817d2  lea     rcx, CLSID_ClusterCleanup; Clsid
0x1800817d9  sbb     r8d, r8d
0x1800817dc  mov     [rsp+98h+dwCount], 1; dwCount
0x1800817e4  and     r8d, 0Ch
0x1800817e8  xor     edx, edx; punkOuter
0x1800817ea  add     r8d, 4; dwClsCtx
0x1800817ee  call    cs:__imp_CoCreateInstanceEx
0x1800817f5  nop     dword ptr [rax+rax+00h]
0x1800817fa  mov     esi, eax
0x1800817fc  test    eax, eax
0x1800817fe  js      short loc_180081827
0x180081800  mov     rbx, [rsp+98h+var_68.pItf]
0x180081805  mov     edx, ebp
0x180081807  mov     rcx, rbx
0x18008180a  mov     rax, [rbx]
0x18008180d  mov     rax, [rax+20h]
0x180081811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081816  mov     esi, eax
0x180081818  mov     rax, [rbx]
0x18008181b  mov     rcx, rbx
0x18008181e  mov     rax, [rax+10h]
0x180081822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081827  cmp     edi, 80010106h
0x18008182d  jz      short loc_18008183B
0x18008182f  call    cs:__imp_CoUninitialize
0x180081836  nop     dword ptr [rax+rax+00h]
0x18008183b  mov     eax, esi
0x18008183d  add     rsp, 78h
0x180081841  pop     rdi
0x180081842  pop     rsi
0x180081843  pop     rbp
0x180081844  pop     rbx
0x180081845  retn
```
