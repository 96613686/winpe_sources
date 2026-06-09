# WdcConnectServer(void *)

- ea: `0x180044f60`
- end: `0x18004507d`
- name: `?WdcConnectServer@@YAKPEAX@Z`
- size: `285`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b854`
- `0x180044f60`
- `0x180086010`

## import_xrefs

- `USER32!PostMessageW` at `0x18004506c`
- `USER32!PostMessageW` at `0x18004506c`
- `ole32!CoUninitialize` at `0x180045055`
- `ole32!CoUninitialize` at `0x180045055`
- `ole32!CoInitialize` at `0x180044fe3`
- `ole32!CoInitialize` at `0x180044fe3`
- `ole32!CoCreateInstanceEx` at `0x180045012`
- `ole32!CoCreateInstanceEx` at `0x180045012`
- `PLA!PlaGetServerCapabilities` at `0x180044f98`
- `PLA!PlaGetServerCapabilities` at `0x180044f98`

## pseudocode

```c
__int64 __fastcall WdcConnectServer(PVOID Parameter)
{
  OLECHAR *v2; // rcx
  int v3; // esi
  HRESULT ServerCapabilities; // eax
  unsigned int hr; // ebx
  DWORD v6; // eax
  HWND v7; // rcx
  __int64 dwCount; // [rsp+20h] [rbp-58h]
  MULTI_QI pResults; // [rsp+30h] [rbp-48h] BYREF
  COSERVERINFO pServerInfo; // [rsp+48h] [rbp-30h] BYREF
  DWORD Capabilites; // [rsp+A0h] [rbp+28h] BYREF

  Capabilites = 0;
  v2 = (OLECHAR *)*((_QWORD *)Parameter + 1);
  v3 = 0;
  memset(&pServerInfo, 0, sizeof(pServerInfo));
  memset(&pResults, 0, sizeof(pResults));
  ServerCapabilities = PlaGetServerCapabilities(v2, &Capabilites);
  hr = ServerCapabilities;
  if ( ServerCapabilities < 0 )
    goto LABEL_2;
  v6 = Capabilites;
  if ( (Capabilites & 1) != 0 )
  {
    pServerInfo.pwszName = (LPWSTR)*((_QWORD *)Parameter + 1);
    pResults.pIID = &IID_IDataCollectorSet;
    ServerCapabilities = CoInitialize(0);
    hr = ServerCapabilities;
    if ( ServerCapabilities < 0
      || (v3 = 1,
          ServerCapabilities = CoCreateInstanceEx(&CLSID_DataCollectorSet, 0, 0x10u, &pServerInfo, 1u, &pResults),
          hr = ServerCapabilities,
          ServerCapabilities < 0) )
    {
LABEL_2:
      LODWORD(dwCount) = ServerCapabilities;
LABEL_3:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp",
        "WdcConnectServer",
        0,
        L"FAILURE: 0x%08x",
        dwCount);
      goto LABEL_11;
    }
    hr = pResults.hr;
    if ( pResults.hr < 0 )
    {
      LODWORD(dwCount) = pResults.hr;
      goto LABEL_3;
    }
    v6 = Capabilites;
  }
  *((_DWORD *)Parameter + 4) = v6;
LABEL_11:
  if ( pResults.pItf )
  {
    ((void (__fastcall *)(IUnknown *))pResults.pItf->lpVtbl->Release)(pResults.pItf);
    pResults.pItf = 0;
  }
  if ( v3 )
    CoUninitialize();
  v7 = *(HWND *)Parameter;
  *((_DWORD *)Parameter + 5) = hr;
  PostMessageW(v7, 0x7E9u, 0, 0);
  return hr;
}

```

## disassembly

```asm
0x180044f60  push    rbp
0x180044f62  push    rbx
0x180044f63  push    rsi
0x180044f64  push    rdi
0x180044f65  mov     rbp, rsp
0x180044f68  sub     rsp, 78h
0x180044f6c  xorps   xmm0, xmm0
0x180044f6f  mov     [rbp+Capabilites], 0
0x180044f76  mov     rdi, rcx
0x180044f79  lea     rdx, [rbp+Capabilites]; Capabilites
0x180044f7d  mov     rcx, [rcx+8]; Server
0x180044f81  xorps   xmm1, xmm1
0x180044f84  xor     eax, eax
0x180044f86  xor     esi, esi
0x180044f88  movups  xmmword ptr [rbp+pServerInfo.dwReserved1], xmm0
0x180044f8c  mov     qword ptr [rbp+var_48.hr], rax
0x180044f90  movups  xmmword ptr [rbp+pServerInfo.pAuthInfo], xmm0
0x180044f94  movups  xmmword ptr [rbp+var_48.pIID], xmm1
0x180044f98  call    cs:__imp_PlaGetServerCapabilities
0x180044f9e  mov     ebx, eax
0x180044fa0  test    eax, eax
0x180044fa2  jns     short loc_180044FC7
0x180044fa4  mov     dword ptr [rsp+78h+dwCount], eax
0x180044fa8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180044faf  xor     r8d, r8d; int
0x180044fb2  lea     rdx, aWdcconnectserv; "WdcConnectServer"
0x180044fb9  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x180044fc0  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180044fc5  jmp     short loc_180045034
0x180044fc7  mov     eax, [rbp+Capabilites]
0x180044fca  test    al, 1
0x180044fcc  jz      short loc_180045031
0x180044fce  mov     rax, [rdi+8]
0x180044fd2  xor     ecx, ecx; pvReserved
0x180044fd4  mov     [rbp+pServerInfo.pwszName], rax
0x180044fd8  lea     rax, IID_IDataCollectorSet
0x180044fdf  mov     [rbp+var_48.pIID], rax
0x180044fe3  call    cs:__imp_CoInitialize
0x180044fe9  mov     ebx, eax
0x180044feb  test    eax, eax
0x180044fed  js      short loc_180044FA4
0x180044fef  mov     esi, 1
0x180044ff4  lea     rax, [rbp+var_48]
0x180044ff8  mov     [rsp+78h+pResults], rax; pResults
0x180044ffd  lea     r9, [rbp+pServerInfo]; pServerInfo
0x180045001  xor     edx, edx; punkOuter
0x180045003  mov     dword ptr [rsp+78h+dwCount], esi; dwCount
0x180045007  lea     rcx, CLSID_DataCollectorSet; Clsid
0x18004500e  lea     r8d, [rsi+0Fh]; dwClsCtx
0x180045012  call    cs:__imp_CoCreateInstanceEx
0x180045018  mov     ebx, eax
0x18004501a  test    eax, eax
0x18004501c  js      short loc_180044FA4
0x18004501e  mov     ebx, [rbp+var_48.hr]
0x180045021  test    ebx, ebx
0x180045023  jns     short loc_18004502E
0x180045025  mov     dword ptr [rsp+78h+dwCount], ebx
0x180045029  jmp     loc_180044FA8
0x18004502e  mov     eax, [rbp+Capabilites]
0x180045031  mov     [rdi+10h], eax
0x180045034  mov     rcx, [rbp+var_48.pItf]
0x180045038  test    rcx, rcx
0x18004503b  jz      short loc_180045051
0x18004503d  mov     rax, [rcx]
0x180045040  mov     rax, [rax+10h]
0x180045044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045049  mov     [rbp+var_48.pItf], 0
0x180045051  test    esi, esi
0x180045053  jz      short loc_18004505B
0x180045055  call    cs:__imp_CoUninitialize
0x18004505b  mov     rcx, [rdi]; hWnd
0x18004505e  xor     r9d, r9d; lParam
0x180045061  xor     r8d, r8d; wParam
0x180045064  mov     [rdi+14h], ebx
0x180045067  mov     edx, 7E9h; Msg
0x18004506c  call    cs:__imp_PostMessageW
0x180045072  mov     eax, ebx
0x180045074  add     rsp, 78h
0x180045078  pop     rdi
0x180045079  pop     rsi
0x18004507a  pop     rbx
0x18004507b  pop     rbp
0x18004507c  retn
```
