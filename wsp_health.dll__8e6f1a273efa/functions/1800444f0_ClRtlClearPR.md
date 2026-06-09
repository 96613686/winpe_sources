# ClRtlClearPR

- ea: `0x1800444f0`
- end: `0x1800445f7`
- name: `ClRtlClearPR`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002db80`

## callees

- `0x1800444f0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18004459e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18004459e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800445df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800445df`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180044505`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180044505`

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
0x1800444f0  push    rbx
0x1800444f2  push    rbp
0x1800444f3  push    rsi
0x1800444f4  push    rdi
0x1800444f5  sub     rsp, 78h
0x1800444f9  mov     ebp, edx
0x1800444fb  mov     rbx, rcx
0x1800444fe  mov     edx, 4; dwCoInit
0x180044503  xor     ecx, ecx; pvReserved
0x180044505  call    cs:__imp_CoInitializeEx
0x18004450c  nop     dword ptr [rax+rax+00h]
0x180044511  mov     edi, eax
0x180044513  cmp     eax, 80010106h
0x180044518  jz      short loc_180044526
0x18004451a  cmp     eax, 1
0x18004451d  jbe     short loc_180044526
0x18004451f  mov     esi, eax
0x180044521  jmp     loc_1800445EB
0x180044526  mov     [rsp+98h+var_68.pItf], 0
0x18004452f  xorps   xmm0, xmm0
0x180044532  mov     [rsp+98h+var_68.hr], 0
0x18004453a  lea     rax, IID_IClusterCleanup
0x180044541  mov     [rsp+98h+var_68.pIID], rax
0x180044546  movups  xmmword ptr [rsp+98h+pServerInfo.dwReserved1], xmm0
0x18004454b  movups  xmmword ptr [rsp+98h+pServerInfo.pAuthInfo], xmm0
0x180044550  test    rbx, rbx
0x180044553  jnz     short loc_18004455A
0x180044555  xor     r9d, r9d
0x180044558  jmp     short loc_180044575
0x18004455a  lea     r9, [rsp+98h+pServerInfo]; pServerInfo
0x18004455f  mov     [rsp+98h+pServerInfo.pwszName], rbx
0x180044564  mov     [rsp+98h+pServerInfo.pAuthInfo], 0
0x18004456d  mov     [rsp+98h+pServerInfo.dwReserved2], 0
0x180044575  lea     rax, [rsp+98h+var_68]
0x18004457a  neg     rbx
0x18004457d  mov     [rsp+98h+pResults], rax; pResults
0x180044582  lea     rcx, CLSID_ClusterCleanup; Clsid
0x180044589  sbb     r8d, r8d
0x18004458c  mov     [rsp+98h+dwCount], 1; dwCount
0x180044594  and     r8d, 0Ch
0x180044598  xor     edx, edx; punkOuter
0x18004459a  add     r8d, 4; dwClsCtx
0x18004459e  call    cs:__imp_CoCreateInstanceEx
0x1800445a5  nop     dword ptr [rax+rax+00h]
0x1800445aa  mov     esi, eax
0x1800445ac  test    eax, eax
0x1800445ae  js      short loc_1800445D7
0x1800445b0  mov     rbx, [rsp+98h+var_68.pItf]
0x1800445b5  mov     edx, ebp
0x1800445b7  mov     rcx, rbx
0x1800445ba  mov     rax, [rbx]
0x1800445bd  mov     rax, [rax+20h]
0x1800445c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445c6  mov     esi, eax
0x1800445c8  mov     rax, [rbx]
0x1800445cb  mov     rcx, rbx
0x1800445ce  mov     rax, [rax+10h]
0x1800445d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445d7  cmp     edi, 80010106h
0x1800445dd  jz      short loc_1800445EB
0x1800445df  call    cs:__imp_CoUninitialize
0x1800445e6  nop     dword ptr [rax+rax+00h]
0x1800445eb  mov     eax, esi
0x1800445ed  add     rsp, 78h
0x1800445f1  pop     rdi
0x1800445f2  pop     rsi
0x1800445f3  pop     rbp
0x1800445f4  pop     rbx
0x1800445f5  retn
```
