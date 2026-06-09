# ClRtlClearPR

- ea: `0x180042cf4`
- end: `0x180042de8`
- name: `ClRtlClearPR`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002cca0`

## callees

- `0x180042cf4`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180042d9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180042d9c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042dd7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042dd7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180042d09`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180042d09`

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
0x180042cf4  push    rbx
0x180042cf6  push    rbp
0x180042cf7  push    rsi
0x180042cf8  push    rdi
0x180042cf9  sub     rsp, 78h
0x180042cfd  mov     ebp, edx
0x180042cff  mov     rbx, rcx
0x180042d02  mov     edx, 4; dwCoInit
0x180042d07  xor     ecx, ecx; pvReserved
0x180042d09  call    cs:__imp_CoInitializeEx
0x180042d0f  mov     edi, eax
0x180042d11  cmp     eax, 80010106h
0x180042d16  jz      short loc_180042D24
0x180042d18  cmp     eax, 1
0x180042d1b  jbe     short loc_180042D24
0x180042d1d  mov     esi, eax
0x180042d1f  jmp     loc_180042DDD
0x180042d24  mov     [rsp+98h+var_68.pItf], 0
0x180042d2d  xorps   xmm0, xmm0
0x180042d30  mov     [rsp+98h+var_68.hr], 0
0x180042d38  lea     rax, IID_IClusterCleanup
0x180042d3f  mov     [rsp+98h+var_68.pIID], rax
0x180042d44  movups  xmmword ptr [rsp+98h+pServerInfo.dwReserved1], xmm0
0x180042d49  movups  xmmword ptr [rsp+98h+pServerInfo.pAuthInfo], xmm0
0x180042d4e  test    rbx, rbx
0x180042d51  jnz     short loc_180042D58
0x180042d53  xor     r9d, r9d
0x180042d56  jmp     short loc_180042D73
0x180042d58  lea     r9, [rsp+98h+pServerInfo]; pServerInfo
0x180042d5d  mov     [rsp+98h+pServerInfo.pwszName], rbx
0x180042d62  mov     [rsp+98h+pServerInfo.pAuthInfo], 0
0x180042d6b  mov     [rsp+98h+pServerInfo.dwReserved2], 0
0x180042d73  lea     rax, [rsp+98h+var_68]
0x180042d78  neg     rbx
0x180042d7b  mov     [rsp+98h+pResults], rax; pResults
0x180042d80  lea     rcx, CLSID_ClusterCleanup; Clsid
0x180042d87  sbb     r8d, r8d
0x180042d8a  mov     [rsp+98h+dwCount], 1; dwCount
0x180042d92  and     r8d, 0Ch
0x180042d96  xor     edx, edx; punkOuter
0x180042d98  add     r8d, 4; dwClsCtx
0x180042d9c  call    cs:__imp_CoCreateInstanceEx
0x180042da2  mov     esi, eax
0x180042da4  test    eax, eax
0x180042da6  js      short loc_180042DCF
0x180042da8  mov     rbx, [rsp+98h+var_68.pItf]
0x180042dad  mov     edx, ebp
0x180042daf  mov     rcx, rbx
0x180042db2  mov     rax, [rbx]
0x180042db5  mov     rax, [rax+20h]
0x180042db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042dbe  mov     esi, eax
0x180042dc0  mov     rax, [rbx]
0x180042dc3  mov     rcx, rbx
0x180042dc6  mov     rax, [rax+10h]
0x180042dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042dcf  cmp     edi, 80010106h
0x180042dd5  jz      short loc_180042DDD
0x180042dd7  call    cs:__imp_CoUninitialize
0x180042ddd  mov     eax, esi
0x180042ddf  add     rsp, 78h
0x180042de3  pop     rdi
0x180042de4  pop     rsi
0x180042de5  pop     rbp
0x180042de6  pop     rbx
0x180042de7  retn
```
